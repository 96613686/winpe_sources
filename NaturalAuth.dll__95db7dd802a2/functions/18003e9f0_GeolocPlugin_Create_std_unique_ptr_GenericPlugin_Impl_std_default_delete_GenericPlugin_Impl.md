# GeolocPlugin::Create(std::unique_ptr<GenericPlugin::Impl,std::default_delete<GenericPlugin::Impl>> *)

- ea: `0x18003e9f0`
- end: `0x18003ea93`
- name: `?Create@GeolocPlugin@@SAJPEAV?$unique_ptr@VImpl@GenericPlugin@@U?$default_delete@VImpl@GenericPlugin@@@std@@@std@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180020f30`

## callees

- `0x18000459c`
- `0x18000b7b8`
- `0x180012b0c`
- `0x18001fb2c`
- `0x1800248f8`
- `0x18003e2e4`
- `0x18003e9f0`

## string_xrefs

- `0x18003ea0d`: `<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema" version="1.0">  <xs:element name="signal">    <xs:complexType>      <xs:attribute name="type" type="xs:string" fixed="geoloc"/>      <xs:attribute name="latitude" use="required">        <xs:simpleType>          <xs:restriction base="xs:decimal">            <xs:maxInclusive value="90"/>            <xs:minInclusive value="-90"/>          </xs:restriction>        </xs:simpleType>      </xs:attribute>      <xs:attribute name="longitude" use="req`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GeolocPlugin::Create(struct GeolocPlugin **a1)
{
  struct GeolocPlugin *v2; // rdi
  _bstr_t *v3; // rax
  __int64 v4; // r8
  struct GeolocPlugin *v5; // rdx
  GeolocPlugin::Impl *v7; // [rsp+50h] [rbp+8h] BYREF
  struct GeolocPlugin *v8; // [rsp+58h] [rbp+10h]

  v2 = (struct GeolocPlugin *)operator new(0x68u);
  v8 = v2;
  v3 = _bstr_t::_bstr_t((_bstr_t *)&v7, aXsSchemaXmlnsX_4);
  GenericPlugin::DefaultImpl::DefaultImpl((__int64)v2, v3, v4, (__int64)off_18005C610, (__int64)qword_18004EDD0);
  *(_QWORD *)v2 = &GeolocPlugin::`vftable';
  v7 = (GeolocPlugin::Impl *)operator new(0x10u);
  *((_QWORD *)v2 + 12) = GeolocPlugin::Impl::Impl(v7, v2);
  v7 = 0;
  v5 = *a1;
  *a1 = v2;
  if ( v5 )
    std::default_delete<NASignal>::operator()();
  std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>((__int64 (__fastcall ****)(_QWORD, __int64))&v7);
  return 0;
}

```

## disassembly

```asm
0x18003e9f0  push    rbx
0x18003e9f2  push    rsi
0x18003e9f3  push    rdi
0x18003e9f4  sub     rsp, 30h
0x18003e9f8  mov     rsi, rcx
0x18003e9fb  mov     ecx, 68h ; 'h'; Size
0x18003ea00  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003ea05  mov     rdi, rax
0x18003ea08  mov     [rsp+48h+arg_8], rax
0x18003ea0d  lea     rdx, aXsSchemaXmlnsX_4; "<xs:schema xmlns:xs=\"http://www.w3.org"...
0x18003ea14  lea     rcx, [rsp+48h+arg_0]; this
0x18003ea19  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18003ea1e  lea     rcx, qword_18004EDD0
0x18003ea25  mov     [rsp+48h+var_28], rcx
0x18003ea2a  lea     r9, off_18005C610; "geoloc"
0x18003ea31  mov     rdx, rax
0x18003ea34  mov     rcx, rdi
0x18003ea37  call    ??0DefaultImpl@GenericPlugin@@QEAA@V_bstr_t@@KPEAPEBGPEBW4NA_SIGNAL_TYPE_INFO@@@Z; GenericPlugin::DefaultImpl::DefaultImpl(_bstr_t,ulong,ushort const * *,NA_SIGNAL_TYPE_INFO const *)
0x18003ea3c  nop
0x18003ea3d  lea     rax, ??_7GeolocPlugin@@6B@; const GeolocPlugin::`vftable'
0x18003ea44  mov     [rdi], rax
0x18003ea47  mov     ecx, 10h; Size
0x18003ea4c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003ea51  mov     [rsp+48h+arg_0], rax
0x18003ea56  mov     rdx, rdi; struct GeolocPlugin *
0x18003ea59  mov     rcx, rax; this
0x18003ea5c  call    ??0Impl@GeolocPlugin@@QEAA@PEAV1@@Z; GeolocPlugin::Impl::Impl(GeolocPlugin *)
0x18003ea61  nop
0x18003ea62  mov     [rdi+60h], rax
0x18003ea66  mov     [rsp+48h+arg_0], 0
0x18003ea6f  mov     rdx, [rsi]
0x18003ea72  mov     [rsi], rdi
0x18003ea75  test    rdx, rdx
0x18003ea78  jz      short loc_18003EA7F
0x18003ea7a  call    ??R?$default_delete@VNASignal@@@std@@QEBAXPEAVNASignal@@@Z; std::default_delete<NASignal>::operator()(NASignal *)
0x18003ea7f  lea     rcx, [rsp+48h+arg_0]
0x18003ea84  call    ??1?$unique_ptr@V_Facet_base@std@@U?$default_delete@V_Facet_base@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>(void)
0x18003ea89  xor     eax, eax
0x18003ea8b  add     rsp, 30h
0x18003ea8f  pop     rdi
0x18003ea90  pop     rsi
0x18003ea91  pop     rbx
0x18003ea92  retn
```
