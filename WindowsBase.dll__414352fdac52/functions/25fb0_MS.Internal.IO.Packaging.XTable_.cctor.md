# MS.Internal.IO.Packaging.XTable::.cctor

- ea: `0x25fb0`
- end: `0x2627b`
- name: `MS.Internal.IO.Packaging.XTable::.cctor`
- size: `715`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x57200`

## string_xrefs

- `0x25ff0`: `http://www.w3.org/2000/09/xmldsig#`
- `0x25fba`: `http://schemas.openxmlformats.org/package/2006/digital-signature`
- `0x25fde`: `xmlns:opc`
- `0x26002`: `http://schemas.openxmlformats.org/package/2006/RelationshipTransform`
- `0x2609a`: `Manifest`

## pseudocode

```c

```

## disassembly

```asm
0x25fb0  ldc.i4.s 0x24
0x25fb2  newarr   TableEntry
0x25fb7  dup
0x25fb8  ldc.i4.0
0x25fb9  ldc.i4.0
0x25fba  ldstr    aHttpSchemasOpe_2// "http://schemas.openxmlformats.org/packa"...
0x25fbf  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x25fc4  stelem   TableEntry
0x25fc9  dup
0x25fca  ldc.i4.1
0x25fcb  ldc.i4.1
0x25fcc  ldstr    aOpc// "opc"
0x25fd1  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x25fd6  stelem   TableEntry
0x25fdb  dup
0x25fdc  ldc.i4.2
0x25fdd  ldc.i4.2
0x25fde  ldstr    aXmlnsOpc// "xmlns:opc"
0x25fe3  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x25fe8  stelem   TableEntry
0x25fed  dup
0x25fee  ldc.i4.3
0x25fef  ldc.i4.3
0x25ff0  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/09/xmldsig#"
0x25ff5  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x25ffa  stelem   TableEntry
0x25fff  dup
0x26000  ldc.i4.4
0x26001  ldc.i4.4
0x26002  ldstr    aHttpSchemasOpe_3// "http://schemas.openxmlformats.org/packa"...
0x26007  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x2600c  stelem   TableEntry
0x26011  dup
0x26012  ldc.i4.5
0x26013  ldc.i4.5
0x26014  ldstr    aSignature// "Signature"
0x26019  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x2601e  stelem   TableEntry
0x26023  dup
0x26024  ldc.i4.6
0x26025  ldc.i4.6
0x26026  ldstr    aSignatureidval// "SignatureIdValue"
0x2602b  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x26030  stelem   TableEntry
0x26035  dup
0x26036  ldc.i4.7
0x26037  ldc.i4.7
0x26038  ldstr    aSignedinfo// "SignedInfo"
0x2603d  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x26042  stelem   TableEntry
0x26047  dup
0x26048  ldc.i4.8
0x26049  ldc.i4.8
0x2604a  ldstr    aReference// "Reference"
0x2604f  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x26054  stelem   TableEntry
0x26059  dup
0x2605a  ldc.i4.s 9
0x2605c  ldc.i4.s 9
0x2605e  ldstr    aSignaturemetho// "SignatureMethod"
0x26063  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x26068  stelem   TableEntry
0x2606d  dup
0x2606e  ldc.i4.s 0xA
0x26070  ldc.i4.s 0xA
0x26072  ldstr    aObject// "Object"
0x26077  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x2607c  stelem   TableEntry
0x26081  dup
0x26082  ldc.i4.s 0xB
0x26084  ldc.i4.s 0xB
0x26086  ldstr    aKeyinfo// "KeyInfo"
0x2608b  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x26090  stelem   TableEntry
0x26095  dup
0x26096  ldc.i4.s 0xC
0x26098  ldc.i4.s 0xC
0x2609a  ldstr    aManifest// "Manifest"
0x2609f  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x260a4  stelem   TableEntry
0x260a9  dup
0x260aa  ldc.i4.s 0xD
0x260ac  ldc.i4.s 0xD
0x260ae  ldstr    aTransform// "Transform"
0x260b3  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x260b8  stelem   TableEntry
0x260bd  dup
0x260be  ldc.i4.s 0xE
0x260c0  ldc.i4.s 0xE
0x260c2  ldstr    aTransforms// "Transforms"
0x260c7  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x260cc  stelem   TableEntry
0x260d1  dup
0x260d2  ldc.i4.s 0xF
0x260d4  ldc.i4.s 0xF
0x260d6  ldstr    aAlgorithm// "Algorithm"
0x260db  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x260e0  stelem   TableEntry
0x260e5  dup
0x260e6  ldc.i4.s 0x10
0x260e8  ldc.i4.s 0x10
0x260ea  ldstr    aSourceid// "SourceId"
0x260ef  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x260f4  stelem   TableEntry
0x260f9  dup
0x260fa  ldc.i4.s 0x11
0x260fc  ldc.i4.s 0x11
0x260fe  ldstr    aIdpackageobjec// "idPackageObject"
0x26103  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x26108  stelem   TableEntry
0x2610d  dup
0x2610e  ldc.i4.s 0x12
0x26110  ldc.i4.s 0x12
0x26112  ldstr    aIdpackageobjec_0// "#idPackageObject"
0x26117  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x2611c  stelem   TableEntry
0x26121  dup
0x26122  ldc.i4.s 0x13
0x26124  ldc.i4.s 0x13
0x26126  ldstr    aTarget_0// "Target"
0x2612b  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x26130  stelem   TableEntry
0x26135  dup
0x26136  ldc.i4.s 0x14
0x26138  ldc.i4.s 0x14
0x2613a  ldstr    aSignaturevalue// "SignatureValue"
0x2613f  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x26144  stelem   TableEntry
0x26149  dup
0x2614a  ldc.i4.s 0x15
0x2614c  ldc.i4.s 0x15
0x2614e  ldstr    aUri// "URI"
0x26153  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x26158  stelem   TableEntry
0x2615d  dup
0x2615e  ldc.i4.s 0x16
0x26160  ldc.i4.s 0x16
0x26162  ldstr    aDigestmethod// "DigestMethod"
0x26167  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x2616c  stelem   TableEntry
0x26171  dup
0x26172  ldc.i4.s 0x17
0x26174  ldc.i4.s 0x17
0x26176  ldstr    aDigestvalue// "DigestValue"
0x2617b  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x26180  stelem   TableEntry
0x26185  dup
0x26186  ldc.i4.s 0x18
0x26188  ldc.i4.s 0x18
0x2618a  ldstr    aSignatureprope// "SignatureProperties"
0x2618f  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x26194  stelem   TableEntry
0x26199  dup
0x2619a  ldc.i4.s 0x19
0x2619c  ldc.i4.s 0x19
0x2619e  ldstr    aSignatureprope_0// "SignatureProperty"
0x261a3  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x261a8  stelem   TableEntry
0x261ad  dup
0x261ae  ldc.i4.s 0x1A
0x261b0  ldc.i4.s 0x1A
0x261b2  ldstr    aSignaturetime// "SignatureTime"
0x261b7  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x261bc  stelem   TableEntry
0x261c1  dup
0x261c2  ldc.i4.s 0x1B
0x261c4  ldc.i4.s 0x1B
0x261c6  ldstr    aFormat// "Format"
0x261cb  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x261d0  stelem   TableEntry
0x261d5  dup
0x261d6  ldc.i4.s 0x1C
0x261d8  ldc.i4.s 0x1C
0x261da  ldstr    aValue_0// "Value"
0x261df  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x261e4  stelem   TableEntry
0x261e9  dup
0x261ea  ldc.i4.s 0x1D
0x261ec  ldc.i4.s 0x1D
0x261ee  ldstr    aRelationships// "Relationships"
0x261f3  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x261f8  stelem   TableEntry
0x261fd  dup
0x261fe  ldc.i4.s 0x1E
0x26200  ldc.i4.s 0x1E
0x26202  ldstr    aRelationshipre// "RelationshipReference"
0x26207  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x2620c  stelem   TableEntry
0x26211  dup
0x26212  ldc.i4.s 0x1F
0x26214  ldc.i4.s 0x1F
0x26216  ldstr    aRelationshipsg// "RelationshipsGroupReference"
0x2621b  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x26220  stelem   TableEntry
0x26225  dup
0x26226  ldc.i4.s 0x20
0x26228  ldc.i4.s 0x20
0x2622a  ldstr    aSourcetype// "SourceType"
0x2622f  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x26234  stelem   TableEntry
0x26239  dup
0x2623a  ldc.i4.s 0x21
0x2623c  ldc.i4.s 0x21
0x2623e  ldstr    aId_0// "Id"
0x26243  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x26248  stelem   TableEntry
0x2624d  dup
0x2624e  ldc.i4.s 0x22
0x26250  ldc.i4.s 0x22
0x26252  ldstr    aIdsignaturetim// "idSignatureTime"
0x26257  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x2625c  stelem   TableEntry
0x26261  dup
0x26262  ldc.i4.s 0x23
0x26264  ldc.i4.s 0x23
0x26266  ldstr    asc_5D1C4// ""
0x2626b  newobj   instance void TableEntry::.ctor(valuetype ID index, string str)
0x26270  stelem   TableEntry
0x26275  stsfld   valuetype TableEntry[] MS.Internal.IO.Packaging.XTable::_table
0x2627a  ret
```
