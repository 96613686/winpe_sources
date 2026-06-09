# _winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::EnqueueAllPackagesForCacheWork_::_1_::dtor$9

- ea: `0x18001dd00`
- end: `0x18001dd26`
- name: `_winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::EnqueueAllPackagesForCacheWork_::_1_::dtor$9`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004e00`
- `0x18001dd00`

## pseudocode

```c
void __fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::EnqueueAllPackagesForCacheWork_::_1_::dtor_9(
        __int64 a1,
        __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 96) & 2) != 0 )
  {
    *(_DWORD *)(a2 + 96) &= ~2u;
    winrt::Windows::Foundation::IAsyncAction::~IAsyncAction((winrt::Windows::Foundation::IAsyncAction *)(a2 + 120));
  }
}

```

## disassembly

```asm
0x18001dd00  push    rbp
0x18001dd02  sub     rsp, 20h
0x18001dd06  mov     rbp, rdx
0x18001dd09  mov     eax, [rbp+60h]
0x18001dd0c  and     eax, 2
0x18001dd0f  test    eax, eax
0x18001dd11  jz      short loc_18001DD20
0x18001dd13  and     dword ptr [rbp+60h], 0FFFFFFFDh
0x18001dd17  lea     rcx, [rbp+78h]; this
0x18001dd1b  call    ??1IAsyncAction@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncAction::~IAsyncAction(void)
0x18001dd20  add     rsp, 20h
0x18001dd24  pop     rbp
0x18001dd25  retn
```
