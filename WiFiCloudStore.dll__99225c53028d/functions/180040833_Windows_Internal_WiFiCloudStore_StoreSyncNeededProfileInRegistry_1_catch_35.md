# _Windows::Internal::WiFiCloudStore::StoreSyncNeededProfileInRegistry_::_1_::catch$35

- ea: `0x180040833`
- end: `0x18004086c`
- name: `_Windows::Internal::WiFiCloudStore::StoreSyncNeededProfileInRegistry_::_1_::catch$35`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18002e55c`

## string_xrefs

- `0x180040847`: `onecore\net\wificloudstore\registry\lib\wificdsproducerreg.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::WiFiCloudStore::StoreSyncNeededProfileInRegistry_::_1_::catch_35(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 104) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 376),
                            (void *)0xB9,
                            (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsproducerreg.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x180040833  mov     [rsp+arg_8], rdx
0x180040838  push    rbp
0x180040839  sub     rsp, 60h
0x18004083d  mov     rbp, rdx
0x180040840  mov     rcx, [rbp+178h]; this
0x180040847  lea     r8, aOnecoreNetWifi_0; "onecore\\net\\wificloudstore\\registry"...
0x18004084e  mov     edx, 0B9h; void *
0x180040853  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180040858  mov     [rbp+68h], eax
0x18004085b  mov     rax, 0
0x180040865  add     rsp, 60h
0x180040869  pop     rbp
0x18004086a  retn
```
