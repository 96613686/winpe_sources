# _Windows::Internal::WiFiCloudStore::StoreSyncNeededProfileInRegistry_::_1_::catch$34

- ea: `0x1800407f6`
- end: `0x18004082d`
- name: `_Windows::Internal::WiFiCloudStore::StoreSyncNeededProfileInRegistry_::_1_::catch$34`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800310a8`

## string_xrefs

- `0x18004080a`: `onecore\net\wificloudstore\registry\lib\wificdsproducerreg.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::WiFiCloudStore::StoreSyncNeededProfileInRegistry_::_1_::catch_34(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 376),
    (void *)0xA9,
    (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsproducerreg.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x1800407f6  mov     [rsp+arg_8], rdx
0x1800407fb  push    rbp
0x1800407fc  sub     rsp, 60h
0x180040800  mov     rbp, rdx
0x180040803  mov     rcx, [rbp+178h]; this
0x18004080a  lea     r8, aOnecoreNetWifi_0; "onecore\\net\\wificloudstore\\registry"...
0x180040811  mov     edx, 0A9h; void *
0x180040816  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18004081b  nop
0x18004081c  mov     rax, 0
0x180040826  add     rsp, 60h
0x18004082a  pop     rbp
0x18004082b  retn
```
