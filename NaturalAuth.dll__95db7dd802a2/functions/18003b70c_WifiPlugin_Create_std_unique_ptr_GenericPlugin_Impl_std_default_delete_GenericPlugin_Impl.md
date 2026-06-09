# WifiPlugin::Create(std::unique_ptr<GenericPlugin::Impl,std::default_delete<GenericPlugin::Impl>> *)

- ea: `0x18003b70c`
- end: `0x18003b791`
- name: `?Create@WifiPlugin@@SAJPEAV?$unique_ptr@VImpl@GenericPlugin@@U?$default_delete@VImpl@GenericPlugin@@@std@@@std@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180021260`

## callees

- `0x180004960`
- `0x18000b7b8`
- `0x18001fb2c`
- `0x1800248f8`
- `0x18003b70c`

## string_xrefs

- `0x18003b737`: `<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema" version="1.0">  <xs:simpleType name="securityType">    <xs:restriction base="xs:string">      <xs:enumeration value="Open"/>      <xs:enumeration value="WEP"/>      <xs:enumeration value="WPA-Personal"/>      <xs:enumeration value="WPA-Enterprise"/>      <xs:enumeration value="WPA2-Personal"/>      <xs:enumeration value="WPA2-Enterprise"/>      <xs:enumeration value="WPA3-Personal"/>      <xs:enumeration value="WPA3-Enterprise"/>      <xs:en`

## pseudocode

```c
__int64 __fastcall WifiPlugin::Create(__int64 *a1)
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
    v3 = _bstr_t::_bstr_t((_bstr_t *)&v7, aXsSchemaXmlnsX_3);
    GenericPlugin::DefaultImpl::DefaultImpl((__int64)v2, v3, v4, (__int64)off_18005C608, (__int64)&qword_18004EB18);
    *v2 = &WifiPlugin::`vftable';
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
0x18003b70c  mov     [rsp+arg_10], rbx
0x18003b711  push    rdi
0x18003b712  sub     rsp, 30h
0x18003b716  mov     rdi, rcx
0x18003b719  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003b720  mov     ecx, 60h ; '`'; unsigned __int64
0x18003b725  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003b72a  mov     rbx, rax
0x18003b72d  mov     [rsp+38h+arg_8], rax
0x18003b732  test    rax, rax
0x18003b735  jz      short loc_18003B772
0x18003b737  lea     rdx, aXsSchemaXmlnsX_3; "<xs:schema xmlns:xs=\"http://www.w3.org"...
0x18003b73e  lea     rcx, [rsp+38h+arg_0]; this
0x18003b743  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18003b748  lea     rcx, qword_18004EB18
0x18003b74f  mov     [rsp+38h+var_18], rcx
0x18003b754  lea     r9, off_18005C608; "wifi"
0x18003b75b  mov     rdx, rax
0x18003b75e  mov     rcx, rbx
0x18003b761  call    ??0DefaultImpl@GenericPlugin@@QEAA@V_bstr_t@@KPEAPEBGPEBW4NA_SIGNAL_TYPE_INFO@@@Z; GenericPlugin::DefaultImpl::DefaultImpl(_bstr_t,ulong,ushort const * *,NA_SIGNAL_TYPE_INFO const *)
0x18003b766  lea     rax, ??_7WifiPlugin@@6B@; const WifiPlugin::`vftable'
0x18003b76d  mov     [rbx], rax
0x18003b770  jmp     short loc_18003B774
0x18003b772  xor     ebx, ebx
0x18003b774  mov     rdx, [rdi]
0x18003b777  mov     [rdi], rbx
0x18003b77a  test    rdx, rdx
0x18003b77d  jz      short loc_18003B784
0x18003b77f  call    ??R?$default_delete@VNASignal@@@std@@QEBAXPEAVNASignal@@@Z; std::default_delete<NASignal>::operator()(NASignal *)
0x18003b784  xor     eax, eax
0x18003b786  mov     rbx, [rsp+38h+arg_10]
0x18003b78b  add     rsp, 30h
0x18003b78f  pop     rdi
0x18003b790  retn
```
