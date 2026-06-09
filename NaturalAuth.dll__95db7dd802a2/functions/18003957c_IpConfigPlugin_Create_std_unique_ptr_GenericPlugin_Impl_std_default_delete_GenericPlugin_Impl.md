# IpConfigPlugin::Create(std::unique_ptr<GenericPlugin::Impl,std::default_delete<GenericPlugin::Impl>> *)

- ea: `0x18003957c`
- end: `0x180039601`
- name: `?Create@IpConfigPlugin@@SAJPEAV?$unique_ptr@VImpl@GenericPlugin@@U?$default_delete@VImpl@GenericPlugin@@@std@@@std@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180021040`

## callees

- `0x180004960`
- `0x18000b7b8`
- `0x18001fb2c`
- `0x1800248f8`
- `0x18003957c`

## string_xrefs

- `0x1800395a7`: `<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema" version="1.0">  <xs:element name="signal">    <xs:complexType>      <xs:sequence>        <xs:element name="ipv4Prefix" type="xs:string" minOccurs="0"/>        <xs:element name="ipv4Gateway" type="xs:string" minOccurs="0"/>        <xs:element name="ipv4DhcpServer" type="xs:string" minOccurs="0"/>        <xs:element name="ipv4DnsServer" type="xs:string" minOccurs="0" maxOccurs="unbounded"/>        <xs:element name="ipv6Prefix" type="xs:string"`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IpConfigPlugin::Create(__int64 *a1)
{
  _QWORD *v2; // rbx
  _bstr_t *v3; // rax
  __int64 v4; // r8
  __int64 v5; // rdx
  char v7; // [rsp+40h] [rbp+8h] BYREF
  _QWORD *v8; // [rsp+48h] [rbp+10h]

  v2 = operator new(0x60u, (const struct std::nothrow_t *)std::nothrow);
  v8 = v2;
  if ( v2 )
  {
    v3 = _bstr_t::_bstr_t((_bstr_t *)&v7, aXsSchemaXmlnsX_2);
    GenericPlugin::DefaultImpl::DefaultImpl((__int64)v2, v3, v4, (__int64)off_18005C600, (__int64)&qword_18004E888);
    *v2 = &IpConfigPlugin::`vftable';
  }
  else
  {
    v2 = 0;
  }
  v5 = *a1;
  *a1 = (__int64)v2;
  if ( v5 )
    std::default_delete<NASignal>::operator()();
  return 0;
}

```

## disassembly

```asm
0x18003957c  mov     [rsp+arg_10], rbx
0x180039581  push    rdi
0x180039582  sub     rsp, 30h
0x180039586  mov     rdi, rcx
0x180039589  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180039590  mov     ecx, 60h ; '`'; unsigned __int64
0x180039595  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003959a  mov     rbx, rax
0x18003959d  mov     [rsp+38h+arg_8], rax
0x1800395a2  test    rax, rax
0x1800395a5  jz      short loc_1800395E2
0x1800395a7  lea     rdx, aXsSchemaXmlnsX_2; "<xs:schema xmlns:xs=\"http://www.w3.org"...
0x1800395ae  lea     rcx, [rsp+38h+arg_0]; this
0x1800395b3  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800395b8  lea     rcx, qword_18004E888
0x1800395bf  mov     [rsp+38h+var_18], rcx
0x1800395c4  lea     r9, off_18005C600; "ipConfig"
0x1800395cb  mov     rdx, rax
0x1800395ce  mov     rcx, rbx
0x1800395d1  call    ??0DefaultImpl@GenericPlugin@@QEAA@V_bstr_t@@KPEAPEBGPEBW4NA_SIGNAL_TYPE_INFO@@@Z; GenericPlugin::DefaultImpl::DefaultImpl(_bstr_t,ulong,ushort const * *,NA_SIGNAL_TYPE_INFO const *)
0x1800395d6  lea     rax, ??_7IpConfigPlugin@@6B@; const IpConfigPlugin::`vftable'
0x1800395dd  mov     [rbx], rax
0x1800395e0  jmp     short loc_1800395E4
0x1800395e2  xor     ebx, ebx
0x1800395e4  mov     rdx, [rdi]
0x1800395e7  mov     [rdi], rbx
0x1800395ea  test    rdx, rdx
0x1800395ed  jz      short loc_1800395F4
0x1800395ef  call    ??R?$default_delete@VNASignal@@@std@@QEBAXPEAVNASignal@@@Z; std::default_delete<NASignal>::operator()(NASignal *)
0x1800395f4  xor     eax, eax
0x1800395f6  mov     rbx, [rsp+38h+arg_10]
0x1800395fb  add     rsp, 30h
0x1800395ff  pop     rdi
0x180039600  retn
```
