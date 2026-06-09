# FacetsCompiler::.cctor

- ea: `0x124b50`
- end: `0x124bf4`
- name: `FacetsCompiler::.cctor`
- size: `164`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x127760`

## string_xrefs

- `0x124b5a`: `\p{_xmlC}`
- `0x124b6d`: `\P{_xmlC}`
- `0x124b80`: `\p{_xmlD}`
- `0x124b93`: `\P{_xmlD}`
- `0x124ba6`: `\p{_xmlI}`
- `0x124bb9`: `\P{_xmlI}`
- `0x124bcc`: `\p{_xmlW}`
- `0x124bdf`: `\P{_xmlW}`

## pseudocode

```c

```

## disassembly

```asm
0x124b50  ldc.i4.8
0x124b51  newarr   Map
0x124b56  dup
0x124b57  ldc.i4.0
0x124b58  ldc.i4.s 0x63
0x124b5a  ldstr    aPXmlc// "\\p{_xmlC}"
0x124b5f  newobj   instance void Map::.ctor(char m, string r)
0x124b64  stelem   Map
0x124b69  dup
0x124b6a  ldc.i4.1
0x124b6b  ldc.i4.s 0x43
0x124b6d  ldstr    aPXmlc_0// "\\P{_xmlC}"
0x124b72  newobj   instance void Map::.ctor(char m, string r)
0x124b77  stelem   Map
0x124b7c  dup
0x124b7d  ldc.i4.2
0x124b7e  ldc.i4.s 0x64
0x124b80  ldstr    aPXmld// "\\p{_xmlD}"
0x124b85  newobj   instance void Map::.ctor(char m, string r)
0x124b8a  stelem   Map
0x124b8f  dup
0x124b90  ldc.i4.3
0x124b91  ldc.i4.s 0x44
0x124b93  ldstr    aPXmld_0// "\\P{_xmlD}"
0x124b98  newobj   instance void Map::.ctor(char m, string r)
0x124b9d  stelem   Map
0x124ba2  dup
0x124ba3  ldc.i4.4
0x124ba4  ldc.i4.s 0x69
0x124ba6  ldstr    aPXmli// "\\p{_xmlI}"
0x124bab  newobj   instance void Map::.ctor(char m, string r)
0x124bb0  stelem   Map
0x124bb5  dup
0x124bb6  ldc.i4.5
0x124bb7  ldc.i4.s 0x49
0x124bb9  ldstr    aPXmli_0// "\\P{_xmlI}"
0x124bbe  newobj   instance void Map::.ctor(char m, string r)
0x124bc3  stelem   Map
0x124bc8  dup
0x124bc9  ldc.i4.6
0x124bca  ldc.i4.s 0x77
0x124bcc  ldstr    aPXmlw// "\\p{_xmlW}"
0x124bd1  newobj   instance void Map::.ctor(char m, string r)
0x124bd6  stelem   Map
0x124bdb  dup
0x124bdc  ldc.i4.7
0x124bdd  ldc.i4.s 0x57
0x124bdf  ldstr    aPXmlw_0// "\\P{_xmlW}"
0x124be4  newobj   instance void Map::.ctor(char m, string r)
0x124be9  stelem   Map
0x124bee  stsfld   valuetype Map[] FacetsCompiler::c_map
0x124bf3  ret
```
