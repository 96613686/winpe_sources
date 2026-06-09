# System.Xml.XmlTextWriter::AutoComplete

- ea: `0x36270`
- end: `0x364eb`
- name: `System.Xml.XmlTextWriter::AutoComplete`
- size: `635`
- prototype: ``
- caller_count: `21`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x355a0`
- `0x356d0`
- `0x358d0`
- `0x35b60`
- `0x35b80`
- `0x35bf0`
- `0x35c70`
- `0x35ce0`
- `0x35d10`
- `0x35d40`
- `0x35d90`
- `0x35dc0`
- `0x35df0`
- `0x35e20`
- `0x35e50`
- `0x35e80`
- `0x35ed0`
- `0x35f70`
- `0x35f90`
- `0x36110`
- `0x36510`

## callees

- `0x36270`
- `0x36640`
- `0x36810`
- `0x36840`
- `0x36f70`
- `0x622f0`
- `0x62370`

## string_xrefs

- `0x364cc`: `Xml_InvalidOperation`
- `0x3627a`: `Xml_Closed`
- `0x36293`: `Xml_WrongToken`
- `0x362d3`: `Xml_WrongToken`

## pseudocode

```c

```

## disassembly

```asm
0x36270  ldarg.0
0x36271  ldfld    valuetype State System.Xml.XmlTextWriter::currentState
0x36276  ldc.i4.s 9
0x36278  bne.un.s loc_3628A
0x3627a  ldstr    aXmlClosed// "Xml_Closed"
0x3627f  call     string System.Xml.Res::GetString(string name)
0x36284  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x36289  throw
0x3628a  ldarg.0
0x3628b  ldfld    valuetype State System.Xml.XmlTextWriter::currentState
0x36290  ldc.i4.8
0x36291  bne.un.s loc_362BD
0x36293  ldstr    aXmlWrongtoken// "Xml_WrongToken"
0x36298  ldc.i4.2
0x36299  newarr   [mscorlib]System.Object
0x3629e  dup
0x3629f  ldc.i4.0
0x362a0  ldsfld   string[] System.Xml.XmlTextWriter::tokenName
0x362a5  ldarg.1
0x362a6  ldelem.ref
0x362a7  stelem.ref
0x362a8  dup
0x362a9  ldc.i4.1
0x362aa  ldsfld   string[] System.Xml.XmlTextWriter::stateName
0x362af  ldc.i4.8
0x362b0  ldelem.ref
0x362b1  stelem.ref
0x362b2  call     string System.Xml.Res::GetString(string name, object[] args)
0x362b7  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x362bc  throw
0x362bd  ldarg.0
0x362be  ldfld    valuetype State[] System.Xml.XmlTextWriter::stateTable
0x362c3  ldarg.1
0x362c4  ldc.i4.8
0x362c5  mul
0x362c6  ldarg.0
0x362c7  ldfld    valuetype State System.Xml.XmlTextWriter::currentState
0x362cc  add
0x362cd  ldelem.i4
0x362ce  stloc.0
0x362cf  ldloc.0
0x362d0  ldc.i4.8
0x362d1  bne.un.s loc_36302
0x362d3  ldstr    aXmlWrongtoken// "Xml_WrongToken"
0x362d8  ldc.i4.2
0x362d9  newarr   [mscorlib]System.Object
0x362de  dup
0x362df  ldc.i4.0
0x362e0  ldsfld   string[] System.Xml.XmlTextWriter::tokenName
0x362e5  ldarg.1
0x362e6  ldelem.ref
0x362e7  stelem.ref
0x362e8  dup
0x362e9  ldc.i4.1
0x362ea  ldsfld   string[] System.Xml.XmlTextWriter::stateName
0x362ef  ldarg.0
0x362f0  ldfld    valuetype State System.Xml.XmlTextWriter::currentState
0x362f5  ldelem.ref
0x362f6  stelem.ref
0x362f7  call     string System.Xml.Res::GetString(string name, object[] args)
0x362fc  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x36301  throw
0x36302  ldarg.1
0x36303  switch   loc_36363, loc_36341, loc_36363, loc_36363, loc_36363, loc_363CD, loc_363CD, loc_36425, loc_3646C, loc_36482, loc_36482, loc_36482, loc_36482
0x3633c  br       loc_364CC
0x36341  ldarg.0
0x36342  ldfld    bool System.Xml.XmlTextWriter::indented
0x36347  brfalse  loc_364DC
0x3634c  ldarg.0
0x3634d  ldfld    valuetype State System.Xml.XmlTextWriter::currentState
0x36352  brfalse  loc_364DC
0x36357  ldarg.0
0x36358  ldc.i4.0
0x36359  call     instance void System.Xml.XmlTextWriter::Indent(bool beforeEndElement)
0x3635e  br       loc_364DC
0x36363  ldarg.0
0x36364  ldfld    valuetype State System.Xml.XmlTextWriter::currentState
0x36369  ldc.i4.4
0x3636a  bne.un.s loc_3637B
0x3636c  ldarg.0
0x3636d  call     instance void System.Xml.XmlTextWriter::WriteEndAttributeQuote()
0x36372  ldarg.0
0x36373  ldc.i4.0
0x36374  call     instance void System.Xml.XmlTextWriter::WriteEndStartTag(bool empty)
0x36379  br.s     loc_3638B
0x3637b  ldarg.0
0x3637c  ldfld    valuetype State System.Xml.XmlTextWriter::currentState
0x36381  ldc.i4.3
0x36382  bne.un.s loc_3638B
0x36384  ldarg.0
0x36385  ldc.i4.0
0x36386  call     instance void System.Xml.XmlTextWriter::WriteEndStartTag(bool empty)
0x3638b  ldarg.1
0x3638c  ldc.i4.3
0x3638d  bne.un.s loc_363AB
0x3638f  ldarg.0
0x36390  ldfld    valuetype TagInfo[] System.Xml.XmlTextWriter::stack
0x36395  ldarg.0
0x36396  ldfld    int32 System.Xml.XmlTextWriter::top
0x3639b  ldelema  TagInfo
0x363a0  ldc.i4.1
0x363a1  stfld    bool TagInfo::mixed
0x363a6  br       loc_364DC
0x363ab  ldarg.0
0x363ac  ldfld    bool System.Xml.XmlTextWriter::indented
0x363b1  brfalse  loc_364DC
0x363b6  ldarg.0
0x363b7  ldfld    valuetype State System.Xml.XmlTextWriter::currentState
0x363bc  brfalse  loc_364DC
0x363c1  ldarg.0
0x363c2  ldc.i4.0
0x363c3  call     instance void System.Xml.XmlTextWriter::Indent(bool beforeEndElement)
0x363c8  br       loc_364DC
0x363cd  ldarg.0
0x363ce  ldfld    bool System.Xml.XmlTextWriter::flush
0x363d3  brfalse.s loc_363DB
0x363d5  ldarg.0
0x363d6  call     instance void System.Xml.XmlTextWriter::FlushEncoders()
0x363db  ldarg.0
0x363dc  ldfld    valuetype State System.Xml.XmlTextWriter::currentState
0x363e1  ldc.i4.4
0x363e2  bne.un.s loc_363EA
0x363e4  ldarg.0
0x363e5  call     instance void System.Xml.XmlTextWriter::WriteEndAttributeQuote()
0x363ea  ldarg.0
0x363eb  ldfld    valuetype State System.Xml.XmlTextWriter::currentState
0x363f0  ldc.i4.5
0x363f1  bne.un.s loc_363F8
0x363f3  ldc.i4.6
0x363f4  starg.s  1
0x363f6  br.s     loc_36402
0x363f8  ldarg.0
0x363f9  ldarg.1
0x363fa  ldc.i4.5
0x363fb  ceq
0x363fd  call     instance void System.Xml.XmlTextWriter::WriteEndStartTag(bool empty)
0x36402  ldsfld   valuetype State[] System.Xml.XmlTextWriter::stateTableDocument
0x36407  ldarg.0
0x36408  ldfld    valuetype State[] System.Xml.XmlTextWriter::stateTable
0x3640d  bne.un   loc_364DC
0x36412  ldarg.0
0x36413  ldfld    int32 System.Xml.XmlTextWriter::top
0x36418  ldc.i4.1
0x36419  bne.un   loc_364DC
0x3641e  ldc.i4.7
0x3641f  stloc.0
0x36420  br       loc_364DC
0x36425  ldarg.0
0x36426  ldfld    bool System.Xml.XmlTextWriter::flush
0x3642b  brfalse.s loc_36433
0x3642d  ldarg.0
0x3642e  call     instance void System.Xml.XmlTextWriter::FlushEncoders()
0x36433  ldarg.0
0x36434  ldfld    valuetype State System.Xml.XmlTextWriter::currentState
0x36439  ldc.i4.4
0x3643a  bne.un.s loc_36454
0x3643c  ldarg.0
0x3643d  call     instance void System.Xml.XmlTextWriter::WriteEndAttributeQuote()
0x36442  ldarg.0
0x36443  ldfld    class [mscorlib]System.IO.TextWriter System.Xml.XmlTextWriter::textWriter
0x36448  ldc.i4.s 0x20
0x3644a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x3644f  br       loc_364DC
0x36454  ldarg.0
0x36455  ldfld    valuetype State System.Xml.XmlTextWriter::currentState
0x3645a  ldc.i4.3
0x3645b  bne.un.s loc_364DC
0x3645d  ldarg.0
0x3645e  ldfld    class [mscorlib]System.IO.TextWriter System.Xml.XmlTextWriter::textWriter
0x36463  ldc.i4.s 0x20
0x36465  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x3646a  br.s     loc_364DC
0x3646c  ldarg.0
0x3646d  ldfld    bool System.Xml.XmlTextWriter::flush
0x36472  brfalse.s loc_3647A
0x36474  ldarg.0
0x36475  call     instance void System.Xml.XmlTextWriter::FlushEncoders()
0x3647a  ldarg.0
0x3647b  call     instance void System.Xml.XmlTextWriter::WriteEndAttributeQuote()
0x36480  br.s     loc_364DC
0x36482  ldarg.1
0x36483  ldc.i4.s 0xA
0x36485  beq.s    loc_36495
0x36487  ldarg.0
0x36488  ldfld    bool System.Xml.XmlTextWriter::flush
0x3648d  brfalse.s loc_36495
0x3648f  ldarg.0
0x36490  call     instance void System.Xml.XmlTextWriter::FlushEncoders()
0x36495  ldarg.0
0x36496  ldfld    valuetype State System.Xml.XmlTextWriter::currentState
0x3649b  ldc.i4.3
0x3649c  bne.un.s loc_364AF
0x3649e  ldarg.0
0x3649f  ldfld    valuetype Token System.Xml.XmlTextWriter::lastToken
0x364a4  ldc.i4.s 9
0x364a6  beq.s    loc_364AF
0x364a8  ldarg.0
0x364a9  ldc.i4.0
0x364aa  call     instance void System.Xml.XmlTextWriter::WriteEndStartTag(bool empty)
0x364af  ldloc.0
0x364b0  ldc.i4.5
0x364b1  bne.un.s loc_364DC
0x364b3  ldarg.0
0x364b4  ldfld    valuetype TagInfo[] System.Xml.XmlTextWriter::stack
0x364b9  ldarg.0
0x364ba  ldfld    int32 System.Xml.XmlTextWriter::top
0x364bf  ldelema  TagInfo
0x364c4  ldc.i4.1
0x364c5  stfld    bool TagInfo::mixed
0x364ca  br.s     loc_364DC
0x364cc  ldstr    aXmlInvalidoper// "Xml_InvalidOperation"
0x364d1  call     string System.Xml.Res::GetString(string name)
0x364d6  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x364db  throw
0x364dc  ldarg.0
0x364dd  ldloc.0
0x364de  stfld    valuetype State System.Xml.XmlTextWriter::currentState
0x364e3  ldarg.0
0x364e4  ldarg.1
0x364e5  stfld    valuetype Token System.Xml.XmlTextWriter::lastToken
0x364ea  ret
```
