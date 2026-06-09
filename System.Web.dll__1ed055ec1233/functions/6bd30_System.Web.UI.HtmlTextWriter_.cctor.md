# System.Web.UI.HtmlTextWriter::.cctor

- ea: `0x6bd30`
- end: `0x6c50d`
- name: `System.Web.UI.HtmlTextWriter::.cctor`
- size: `2013`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x4eec0`
- `0x6bd30`
- `0x6cac0`
- `0x6cb30`
- `0x6cb40`

## string_xrefs

- `0x6c260`: `accesskey`
- `0x6c284`: `autocomplete`
- `0x6c3ed`: `readonly`

## pseudocode

```c

```

## disassembly

```asm
0x6bd30  ldc.i4.s 0x61
0x6bd32  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor(int32)
0x6bd37  stsfld   class [mscorlib]System.Collections.Hashtable System.Web.UI.HtmlTextWriter::_tagKeyLookupTable
0x6bd3c  ldc.i4.s 0x61
0x6bd3e  newarr   TagInformation
0x6bd43  stsfld   valuetype TagInformation[] System.Web.UI.HtmlTextWriter::_tagNameLookupArray
0x6bd48  ldsfld   string [mscorlib]System.String::Empty
0x6bd4d  ldc.i4.0
0x6bd4e  ldc.i4.2
0x6bd4f  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bd54  ldstr    aA_4// "a"
0x6bd59  ldc.i4.1
0x6bd5a  ldc.i4.0
0x6bd5b  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bd60  ldstr    aAcronym// "acronym"
0x6bd65  ldc.i4.2
0x6bd66  ldc.i4.0
0x6bd67  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bd6c  ldstr    aAddress// "address"
0x6bd71  ldc.i4.3
0x6bd72  ldc.i4.2
0x6bd73  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bd78  ldstr    aArea// "area"
0x6bd7d  ldc.i4.4
0x6bd7e  ldc.i4.1
0x6bd7f  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bd84  ldstr    aB_13// "b"
0x6bd89  ldc.i4.5
0x6bd8a  ldc.i4.0
0x6bd8b  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bd90  ldstr    aBase// "base"
0x6bd95  ldc.i4.6
0x6bd96  ldc.i4.1
0x6bd97  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bd9c  ldstr    aBasefont// "basefont"
0x6bda1  ldc.i4.7
0x6bda2  ldc.i4.1
0x6bda3  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bda8  ldstr    aBdo// "bdo"
0x6bdad  ldc.i4.8
0x6bdae  ldc.i4.0
0x6bdaf  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bdb4  ldstr    aBgsound// "bgsound"
0x6bdb9  ldc.i4.s 9
0x6bdbb  ldc.i4.1
0x6bdbc  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bdc1  ldstr    aBig// "big"
0x6bdc6  ldc.i4.s 0xA
0x6bdc8  ldc.i4.0
0x6bdc9  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bdce  ldstr    aBlockquote// "blockquote"
0x6bdd3  ldc.i4.s 0xB
0x6bdd5  ldc.i4.2
0x6bdd6  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bddb  ldstr    aBody_2// "body"
0x6bde0  ldc.i4.s 0xC
0x6bde2  ldc.i4.2
0x6bde3  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bde8  ldstr    aBr_5// "br"
0x6bded  ldc.i4.s 0xD
0x6bdef  ldsfld   class System.Web.Util.BinaryCompatibility System.Web.Util.BinaryCompatibility::Current
0x6bdf4  callvirt instance bool System.Web.Util.BinaryCompatibility::get_TargetsAtLeastFramework46()
0x6bdf9  brtrue.s loc_6BDFE
0x6bdfb  ldc.i4.2
0x6bdfc  br.s     loc_6BDFF
0x6bdfe  ldc.i4.1
0x6bdff  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6be04  ldstr    aButton// "button"
0x6be09  ldc.i4.s 0xE
0x6be0b  ldc.i4.0
0x6be0c  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6be11  ldstr    aCaption// "caption"
0x6be16  ldc.i4.s 0xF
0x6be18  ldc.i4.2
0x6be19  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6be1e  ldstr    aCenter// "center"
0x6be23  ldc.i4.s 0x10
0x6be25  ldc.i4.2
0x6be26  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6be2b  ldstr    aCite// "cite"
0x6be30  ldc.i4.s 0x11
0x6be32  ldc.i4.0
0x6be33  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6be38  ldstr    aCode// "code"
0x6be3d  ldc.i4.s 0x12
0x6be3f  ldc.i4.0
0x6be40  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6be45  ldstr    aCol// "col"
0x6be4a  ldc.i4.s 0x13
0x6be4c  ldc.i4.1
0x6be4d  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6be52  ldstr    aColgroup// "colgroup"
0x6be57  ldc.i4.s 0x14
0x6be59  ldc.i4.2
0x6be5a  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6be5f  ldstr    aDel// "del"
0x6be64  ldc.i4.s 0x16
0x6be66  ldc.i4.0
0x6be67  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6be6c  ldstr    aDd// "dd"
0x6be71  ldc.i4.s 0x15
0x6be73  ldc.i4.0
0x6be74  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6be79  ldstr    aDfn// "dfn"
0x6be7e  ldc.i4.s 0x17
0x6be80  ldc.i4.0
0x6be81  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6be86  ldstr    aDir// "dir"
0x6be8b  ldc.i4.s 0x18
0x6be8d  ldc.i4.2
0x6be8e  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6be93  ldstr    aDiv_3// "div"
0x6be98  ldc.i4.s 0x19
0x6be9a  ldc.i4.2
0x6be9b  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bea0  ldstr    aDl// "dl"
0x6bea5  ldc.i4.s 0x1A
0x6bea7  ldc.i4.2
0x6bea8  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bead  ldstr    aDt// "dt"
0x6beb2  ldc.i4.s 0x1B
0x6beb4  ldc.i4.0
0x6beb5  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6beba  ldstr    aEm// "em"
0x6bebf  ldc.i4.s 0x1C
0x6bec1  ldc.i4.0
0x6bec2  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bec7  ldstr    aEmbed// "embed"
0x6becc  ldc.i4.s 0x1D
0x6bece  ldc.i4.1
0x6becf  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bed4  ldstr    aFieldset// "fieldset"
0x6bed9  ldc.i4.s 0x1E
0x6bedb  ldc.i4.2
0x6bedc  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bee1  ldstr    aFont_2// "font"
0x6bee6  ldc.i4.s 0x1F
0x6bee8  ldc.i4.0
0x6bee9  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6beee  ldstr    aForm// "form"
0x6bef3  ldc.i4.s 0x20
0x6bef5  ldc.i4.2
0x6bef6  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6befb  ldstr    aFrame// "frame"
0x6bf00  ldc.i4.s 0x21
0x6bf02  ldc.i4.1
0x6bf03  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bf08  ldstr    aFrameset// "frameset"
0x6bf0d  ldc.i4.s 0x22
0x6bf0f  ldc.i4.2
0x6bf10  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bf15  ldstr    aH1_0// "h1"
0x6bf1a  ldc.i4.s 0x23
0x6bf1c  ldc.i4.2
0x6bf1d  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bf22  ldstr    aH2_0// "h2"
0x6bf27  ldc.i4.s 0x24
0x6bf29  ldc.i4.2
0x6bf2a  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bf2f  ldstr    aH3// "h3"
0x6bf34  ldc.i4.s 0x25
0x6bf36  ldc.i4.2
0x6bf37  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bf3c  ldstr    aH4// "h4"
0x6bf41  ldc.i4.s 0x26
0x6bf43  ldc.i4.2
0x6bf44  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bf49  ldstr    aH5// "h5"
0x6bf4e  ldc.i4.s 0x27
0x6bf50  ldc.i4.2
0x6bf51  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bf56  ldstr    aH6// "h6"
0x6bf5b  ldc.i4.s 0x28
0x6bf5d  ldc.i4.2
0x6bf5e  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bf63  ldstr    aHead_4// "head"
0x6bf68  ldc.i4.s 0x29
0x6bf6a  ldc.i4.2
0x6bf6b  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bf70  ldstr    aHr// "hr"
0x6bf75  ldc.i4.s 0x2A
0x6bf77  ldc.i4.1
0x6bf78  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bf7d  ldstr    aHtml_2// "html"
0x6bf82  ldc.i4.s 0x2B
0x6bf84  ldc.i4.2
0x6bf85  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bf8a  ldstr    aI// "i"
0x6bf8f  ldc.i4.s 0x2C
0x6bf91  ldc.i4.0
0x6bf92  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bf97  ldstr    aIframe// "iframe"
0x6bf9c  ldc.i4.s 0x2D
0x6bf9e  ldc.i4.2
0x6bf9f  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bfa4  ldstr    aImg// "img"
0x6bfa9  ldc.i4.s 0x2E
0x6bfab  ldc.i4.1
0x6bfac  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bfb1  ldstr    aInput// "input"
0x6bfb6  ldc.i4.s 0x2F
0x6bfb8  ldc.i4.1
0x6bfb9  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bfbe  ldstr    aIns// "ins"
0x6bfc3  ldc.i4.s 0x30
0x6bfc5  ldc.i4.0
0x6bfc6  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bfcb  ldstr    aIsindex// "isindex"
0x6bfd0  ldc.i4.s 0x31
0x6bfd2  ldc.i4.1
0x6bfd3  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bfd8  ldstr    aKbd// "kbd"
0x6bfdd  ldc.i4.s 0x32
0x6bfdf  ldc.i4.0
0x6bfe0  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bfe5  ldstr    aLabel// "label"
0x6bfea  ldc.i4.s 0x33
0x6bfec  ldc.i4.0
0x6bfed  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bff2  ldstr    aLegend// "legend"
0x6bff7  ldc.i4.s 0x34
0x6bff9  ldc.i4.2
0x6bffa  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6bfff  ldstr    aLi_1// "li"
0x6c004  ldc.i4.s 0x35
0x6c006  ldc.i4.0
0x6c007  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6c00c  ldstr    aLink// "link"
0x6c011  ldc.i4.s 0x36
0x6c013  ldc.i4.1
0x6c014  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6c019  ldstr    aMap// "map"
0x6c01e  ldc.i4.s 0x37
0x6c020  ldc.i4.2
0x6c021  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6c026  ldstr    aMarquee// "marquee"
0x6c02b  ldc.i4.s 0x38
0x6c02d  ldc.i4.2
0x6c02e  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6c033  ldstr    aMenu// "menu"
0x6c038  ldc.i4.s 0x39
0x6c03a  ldc.i4.2
0x6c03b  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6c040  ldstr    aMeta// "meta"
0x6c045  ldc.i4.s 0x3A
0x6c047  ldc.i4.1
0x6c048  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6c04d  ldstr    aNobr_0// "nobr"
0x6c052  ldc.i4.s 0x3B
0x6c054  ldc.i4.0
0x6c055  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6c05a  ldstr    aNoframes// "noframes"
0x6c05f  ldc.i4.s 0x3C
0x6c061  ldc.i4.2
0x6c062  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6c067  ldstr    aNoscript// "noscript"
0x6c06c  ldc.i4.s 0x3D
0x6c06e  ldc.i4.2
0x6c06f  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6c074  ldstr    aObject// "object"
0x6c079  ldc.i4.s 0x3E
0x6c07b  ldc.i4.2
0x6c07c  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6c081  ldstr    aOl_1// "ol"
0x6c086  ldc.i4.s 0x3F
0x6c088  ldc.i4.2
0x6c089  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6c08e  ldstr    aOption// "option"
0x6c093  ldc.i4.s 0x40
0x6c095  ldc.i4.2
0x6c096  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6c09b  ldstr    aP// "p"
0x6c0a0  ldc.i4.s 0x41
0x6c0a2  ldc.i4.0
0x6c0a3  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6c0a8  ldstr    aParam// "param"
0x6c0ad  ldc.i4.s 0x42
0x6c0af  ldc.i4.2
0x6c0b0  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6c0b5  ldstr    aPre_1// "pre"
0x6c0ba  ldc.i4.s 0x43
0x6c0bc  ldc.i4.2
0x6c0bd  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6c0c2  ldstr    aRuby// "ruby"
0x6c0c7  ldc.i4.s 0x46
0x6c0c9  ldc.i4.2
0x6c0ca  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6c0cf  ldstr    aRt// "rt"
0x6c0d4  ldc.i4.s 0x45
0x6c0d6  ldc.i4.2
0x6c0d7  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6c0dc  ldstr    aQ// "q"
0x6c0e1  ldc.i4.s 0x44
0x6c0e3  ldc.i4.0
0x6c0e4  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6c0e9  ldstr    aS_0// "s"
0x6c0ee  ldc.i4.s 0x47
0x6c0f0  ldc.i4.0
0x6c0f1  call     void System.Web.UI.HtmlTextWriter::RegisterTag(string name, valuetype System.Web.UI.HtmlTextWriterTag key, valuetype TagType type)
0x6c0f6  ldstr    aSamp// "samp"
  ... truncated ...
```
