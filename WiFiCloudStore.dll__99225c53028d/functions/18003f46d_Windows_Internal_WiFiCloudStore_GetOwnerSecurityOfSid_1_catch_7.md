# _Windows::Internal::WiFiCloudStore::GetOwnerSecurityOfSid_::_1_::catch$7

- ea: `0x18003f46d`
- end: `0x18003f4a1`
- name: `_Windows::Internal::WiFiCloudStore::GetOwnerSecurityOfSid_::_1_::catch$7`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800310a8`

## string_xrefs

- `0x18003f47e`: `onecore\net\wificloudstore\registry\lib\wificdscommonreg.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::WiFiCloudStore::GetOwnerSecurityOfSid_::_1_::catch_7(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 120),
    (void *)0x68,
    (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdscommonreg.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x18003f46d  mov     [rsp+arg_8], rdx
0x18003f472  push    rbp
0x18003f473  sub     rsp, 40h
0x18003f477  mov     rbp, rdx
0x18003f47a  mov     rcx, [rbp+78h]; this
0x18003f47e  lea     r8, aOnecoreNetWifi_1; "onecore\\net\\wificloudstore\\registry"...
0x18003f485  mov     edx, 68h ; 'h'; void *
0x18003f48a  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18003f48f  nop
0x18003f490  mov     rax, 0
0x18003f49a  add     rsp, 40h
0x18003f49e  pop     rbp
0x18003f49f  retn
```
