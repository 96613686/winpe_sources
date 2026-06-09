# _Windows::Internal::WiFiCloudStore::StoreNlmSyncWithNetworkCategoryChangedForCurrentUser_::_1_::catch$2

- ea: `0x18003ff4c`
- end: `0x18003ff85`
- name: `_Windows::Internal::WiFiCloudStore::StoreNlmSyncWithNetworkCategoryChangedForCurrentUser_::_1_::catch$2`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18002e55c`

## string_xrefs

- `0x18003ff60`: `onecore\net\wificloudstore\registry\lib\wificdsconsumerreg.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::WiFiCloudStore::StoreNlmSyncWithNetworkCategoryChangedForCurrentUser_::_1_::catch_2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 168),
                           (void *)0x113,
                           (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsconsumerreg.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18003ff4c  mov     [rsp+arg_8], rdx
0x18003ff51  push    rbp
0x18003ff52  sub     rsp, 30h
0x18003ff56  mov     rbp, rdx
0x18003ff59  mov     rcx, [rbp+0A8h]; this
0x18003ff60  lea     r8, aOnecoreNetWifi; "onecore\\net\\wificloudstore\\registry"...
0x18003ff67  mov     edx, 113h; void *
0x18003ff6c  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18003ff71  mov     [rbp+30h], eax
0x18003ff74  mov     rax, 0
0x18003ff7e  add     rsp, 30h
0x18003ff82  pop     rbp
0x18003ff83  retn
```
