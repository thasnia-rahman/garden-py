# garden-py
import spacy

gardenpathSentences = ["The old man the boat.", 
        "The complex houses married and single soldiers and their families.", 
        "The horse raced past the barn fell.", 
        "The florist sent the flowers was pleased.", 
        "The cotton clothing is made of grows in Mississippi.", 
        "The sour drink from the ocean."]

nlp = spacy.load("en_core_web_sm")

for sample in gardenpathSentences:
    doc = nlp(sample)
#tokenisation
    print([token.orth_ for token in doc])
#Recognises Entity
    print([(i, i.label_, i.label) for i in doc.ents]) 


#Unusual entity: The fifth sentence Spacy gave mississipi as an entity.
