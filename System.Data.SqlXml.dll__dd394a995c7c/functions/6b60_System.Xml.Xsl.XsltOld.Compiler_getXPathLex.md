# System.Xml.Xsl.XsltOld.Compiler::getXPathLex

- ea: `0x6b60`
- end: `0x6c3c`
- name: `System.Xml.Xsl.XsltOld.Compiler::getXPathLex`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6c40`

## callees

- `0x6b60`

## string_xrefs

- `0x6c20`: `Xslt_OpenLiteralAvt`
- `0x6c27`: `Xslt_OpenBracesAvt`

## pseudocode

```c

```

## disassembly

```asm
0x6b60  ldarg.0
0x6b61  callvirt instance int32 [mscorlib]System.String::get_Length()
0x6b66  stloc.0
0x6b67  ldc.i4.0
0x6b68  stloc.1
0x6b69  ldarg.1
0x6b6a  ldind.i4
0x6b6b  ldc.i4.1
0x6b6c  add
0x6b6d  stloc.2
0x6b6e  br       loc_6C16
0x6b73  ldarg.0
0x6b74  ldloc.2
0x6b75  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x6b7a  stloc.3
0x6b7b  ldloc.1
0x6b7c  switch   loc_6B92, loc_6C02, loc_6C0B
0x6b8d  br       loc_6C12
0x6b92  ldloc.3
0x6b93  ldc.i4.s 0x27
0x6b95  bgt.un.s loc_6BA3
0x6b97  ldloc.3
0x6b98  ldc.i4.s 0x22
0x6b9a  beq.s    loc_6BFE
0x6b9c  ldloc.3
0x6b9d  ldc.i4.s 0x27
0x6b9f  beq.s    loc_6BFA
0x6ba1  br.s     loc_6C12
0x6ba3  ldloc.3
0x6ba4  ldc.i4.s 0x7B
0x6ba6  beq.s    loc_6BAF
0x6ba8  ldloc.3
0x6ba9  ldc.i4.s 0x7D
0x6bab  beq.s    loc_6BC4
0x6bad  br.s     loc_6C12
0x6baf  ldstr    aXsltNestedavt// "Xslt_NestedAvt"
0x6bb4  ldc.i4.1
0x6bb5  newarr   [mscorlib]System.String
0x6bba  dup
0x6bbb  ldc.i4.0
0x6bbc  ldarg.0
0x6bbd  stelem.ref
0x6bbe  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0x6bc3  throw
0x6bc4  ldloc.2
0x6bc5  ldc.i4.1
0x6bc6  add
0x6bc7  stloc.2
0x6bc8  ldloc.2
0x6bc9  ldarg.1
0x6bca  ldind.i4
0x6bcb  ldc.i4.2
0x6bcc  add
0x6bcd  bne.un.s loc_6BE4
0x6bcf  ldstr    aXsltEmptyavtex// "Xslt_EmptyAvtExpr"
0x6bd4  ldc.i4.1
0x6bd5  newarr   [mscorlib]System.String
0x6bda  dup
0x6bdb  ldc.i4.0
0x6bdc  ldarg.0
0x6bdd  stelem.ref
0x6bde  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0x6be3  throw
0x6be4  ldarg.2
0x6be5  ldarg.0
0x6be6  ldarg.1
0x6be7  ldind.i4
0x6be8  ldc.i4.1
0x6be9  add
0x6bea  ldloc.2
0x6beb  ldarg.1
0x6bec  ldind.i4
0x6bed  sub
0x6bee  ldc.i4.2
0x6bef  sub
0x6bf0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string, int32, int32)
0x6bf5  pop
0x6bf6  ldarg.1
0x6bf7  ldloc.2
0x6bf8  stind.i4
0x6bf9  ret
0x6bfa  ldc.i4.1
0x6bfb  stloc.1
0x6bfc  br.s     loc_6C12
0x6bfe  ldc.i4.2
0x6bff  stloc.1
0x6c00  br.s     loc_6C12
0x6c02  ldloc.3
0x6c03  ldc.i4.s 0x27
0x6c05  bne.un.s loc_6C12
0x6c07  ldc.i4.0
0x6c08  stloc.1
0x6c09  br.s     loc_6C12
0x6c0b  ldloc.3
0x6c0c  ldc.i4.s 0x22
0x6c0e  bne.un.s loc_6C12
0x6c10  ldc.i4.0
0x6c11  stloc.1
0x6c12  ldloc.2
0x6c13  ldc.i4.1
0x6c14  add
0x6c15  stloc.2
0x6c16  ldloc.2
0x6c17  ldloc.0
0x6c18  blt      loc_6B73
0x6c1d  ldloc.1
0x6c1e  brfalse.s loc_6C27
0x6c20  ldstr    aXsltOpenlitera// "Xslt_OpenLiteralAvt"
0x6c25  br.s     loc_6C2C
0x6c27  ldstr    aXsltOpenbraces// "Xslt_OpenBracesAvt"
0x6c2c  ldc.i4.1
0x6c2d  newarr   [mscorlib]System.String
0x6c32  dup
0x6c33  ldc.i4.0
0x6c34  ldarg.0
0x6c35  stelem.ref
0x6c36  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0x6c3b  throw
```
