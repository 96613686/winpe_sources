# TimePlugin::TimePlugin(void)

- ea: `0x180024988`
- end: `0x1800249d7`
- name: `??0TimePlugin@@AEAA@XZ`
- size: `79`
- prototype: `TimePlugin *__fastcall(TimePlugin *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180024cb4`

## callees

- `0x18001fb2c`
- `0x1800248f8`

## string_xrefs

- `0x180024995`: `<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema" version="1.0"><xs:complexType name="dayOfWeekType"><xs:attribute name="startTime" type="xs:time"/><xs:attribute name="endTime" type="xs:time"/></xs:complexType><xs:complexType name="weeklyType"><xs:sequence><xs:element name="sun" minOccurs="0" type="dayOfWeekType"/><xs:element name="mon" minOccurs="0" type="dayOfWeekType"/><xs:element name="tue" minOccurs="0" type="dayOfWeekType"/><xs:element name="wed" minOccurs="0" type="dayOfWeekType"/><x`

## pseudocode

```c
TimePlugin *__fastcall TimePlugin::TimePlugin(TimePlugin *this)
{
  _bstr_t *v2; // rax
  __int64 v3; // r8
  TimePlugin *v5; // [rsp+40h] [rbp+8h] BYREF

  v5 = this;
  v2 = _bstr_t::_bstr_t((_bstr_t *)&v5, aXsSchemaXmlnsX_1);
  GenericPlugin::DefaultImpl::DefaultImpl((__int64)this, v2, v3, (__int64)off_18005C5F8, (__int64)&qword_18004C650);
  *(_QWORD *)this = &TimePlugin::`vftable';
  return this;
}

```

## disassembly

```asm
0x180024988  mov     [rsp+arg_0], rcx
0x18002498d  push    rbx
0x18002498e  sub     rsp, 30h
0x180024992  mov     rbx, rcx
0x180024995  lea     rdx, aXsSchemaXmlnsX_1; "<xs:schema xmlns:xs=\"http://www.w3.org"...
0x18002499c  lea     rcx, [rsp+38h+arg_0]; this
0x1800249a1  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800249a6  lea     rcx, qword_18004C650
0x1800249ad  mov     rdx, rax
0x1800249b0  mov     [rsp+38h+var_18], rcx
0x1800249b5  lea     r9, off_18005C5F8; "time"
0x1800249bc  mov     rcx, rbx
0x1800249bf  call    ??0DefaultImpl@GenericPlugin@@QEAA@V_bstr_t@@KPEAPEBGPEBW4NA_SIGNAL_TYPE_INFO@@@Z; GenericPlugin::DefaultImpl::DefaultImpl(_bstr_t,ulong,ushort const * *,NA_SIGNAL_TYPE_INFO const *)
0x1800249c4  lea     rax, ??_7TimePlugin@@6B@; const TimePlugin::`vftable'
0x1800249cb  mov     [rbx], rax
0x1800249ce  mov     rax, rbx
0x1800249d1  add     rsp, 30h
0x1800249d5  pop     rbx
0x1800249d6  retn
```
