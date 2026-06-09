# CdfPlugin::CdfPlugin(void)

- ea: `0x18003fcdc`
- end: `0x18003fd6d`
- name: `??0CdfPlugin@@QEAA@XZ`
- size: `145`
- prototype: `CdfPlugin *__fastcall(_QWORD *pv)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003f9f8`

## callees

- `0x18001fb2c`
- `0x1800248f8`
- `0x1800317e8`
- `0x180033134`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003fd4c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003fd4c`

## string_xrefs

- `0x18003fcee`: `<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema" version="1.0">  <xs:complexType name="deviceListType">    <xs:sequence minOccurs="1" maxOccurs="unbounded">      <xs:element name="device">        <xs:complexType>          <xs:attribute name="id" type="xs:string" use="required"/>        </xs:complexType>      </xs:element>    </xs:sequence>  </xs:complexType>  <xs:element name="signal">    <xs:complexType>      <xs:choice minOccurs="0" maxOccurs="1">        <xs:element name="exclude" type="`

## pseudocode

```c
CdfPlugin *__fastcall CdfPlugin::CdfPlugin(_QWORD *pv)
{
  _bstr_t *v2; // rax
  __int64 v3; // r8
  PTP_TIMER ThreadpoolTimer; // rax
  char v6; // [rsp+48h] [rbp+10h] BYREF

  v2 = _bstr_t::_bstr_t((_bstr_t *)&v6, aXsSchemaXmlnsX_5);
  GenericPlugin::DefaultImpl::DefaultImpl(pv, v2, v3, &off_18005C618, &qword_18004EE98);
  *pv = &CdfPlugin::`vftable';
  pv[12] = 0;
  std::atomic<bool>::atomic<bool>(pv + 13);
  pv[14] = 0;
  ThreadpoolTimer = CreateThreadpoolTimer(CdfPlugin::DevicePresenceUpdateThrottleTimerCallback, pv, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    pv + 12,
    ThreadpoolTimer);
  return (CdfPlugin *)pv;
}

```

## disassembly

```asm
0x18003fcdc  mov     [rsp+arg_10], rbx
0x18003fce1  mov     [rsp+arg_0], rcx
0x18003fce6  push    rdi
0x18003fce7  sub     rsp, 30h
0x18003fceb  mov     rdi, rcx
0x18003fcee  lea     rdx, aXsSchemaXmlnsX_5; "<xs:schema xmlns:xs=\"http://www.w3.org"...
0x18003fcf5  lea     rcx, [rsp+38h+arg_8]; this
0x18003fcfa  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18003fcff  lea     rcx, qword_18004EE98
0x18003fd06  mov     [rsp+38h+var_18], rcx
0x18003fd0b  lea     r9, off_18005C618; "cdf"
0x18003fd12  mov     rdx, rax
0x18003fd15  mov     rcx, rdi
0x18003fd18  call    ??0DefaultImpl@GenericPlugin@@QEAA@V_bstr_t@@KPEAPEBGPEBW4NA_SIGNAL_TYPE_INFO@@@Z; GenericPlugin::DefaultImpl::DefaultImpl(_bstr_t,ulong,ushort const * *,NA_SIGNAL_TYPE_INFO const *)
0x18003fd1d  nop
0x18003fd1e  lea     rax, ??_7CdfPlugin@@6B@; const CdfPlugin::`vftable'
0x18003fd25  mov     [rdi], rax
0x18003fd28  mov     qword ptr [rdi+60h], 0
0x18003fd30  lea     rcx, [rdi+68h]
0x18003fd34  call    ??0?$atomic@_N@std@@QEAA@_N@Z; std::atomic<bool>::atomic<bool>(bool)
0x18003fd39  xor     eax, eax
0x18003fd3b  mov     [rdi+70h], rax
0x18003fd3f  xor     r8d, r8d; pcbe
0x18003fd42  mov     rdx, rdi; pv
0x18003fd45  lea     rcx, ?DevicePresenceUpdateThrottleTimerCallback@CdfPlugin@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18003fd4c  call    cs:__imp_CreateThreadpoolTimer
0x18003fd52  mov     rdx, rax
0x18003fd55  lea     rcx, [rdi+60h]
0x18003fd59  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18003fd5e  nop
0x18003fd5f  mov     rax, rdi
0x18003fd62  mov     rbx, [rsp+38h+arg_10]
0x18003fd67  add     rsp, 30h
0x18003fd6b  pop     rdi
0x18003fd6c  retn
```
