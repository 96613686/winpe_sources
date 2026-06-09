# _Windows::Internal::WiFiCloudStore::TriggerTask_::_1_::catch$12

- ea: `0x18003ff0a`
- end: `0x18003ff46`
- name: `_Windows::Internal::WiFiCloudStore::TriggerTask_::_1_::catch$12`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18002e55c`

## string_xrefs

- `0x18003ff1e`: `onecore\net\wificloudstore\registry\lib\cdsproducercommonreg.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::WiFiCloudStore::TriggerTask_::_1_::catch_12(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 264) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 248),
                            (void *)0x48,
                            (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x18003ff0a  mov     [rsp+arg_8], rdx
0x18003ff0f  push    rbp
0x18003ff10  sub     rsp, 30h
0x18003ff14  mov     rbp, rdx
0x18003ff17  mov     rcx, [rbp+0F8h]; this
0x18003ff1e  lea     r8, aOnecoreNetWifi_2; "onecore\\net\\wificloudstore\\registry"...
0x18003ff25  mov     edx, 48h ; 'H'; void *
0x18003ff2a  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18003ff2f  mov     [rbp+108h], eax
0x18003ff35  mov     rax, 0
0x18003ff3f  add     rsp, 30h
0x18003ff43  pop     rbp
0x18003ff44  retn
```
