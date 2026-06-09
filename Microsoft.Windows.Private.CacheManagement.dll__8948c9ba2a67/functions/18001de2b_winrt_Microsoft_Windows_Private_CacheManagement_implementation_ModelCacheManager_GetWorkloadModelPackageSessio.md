# _winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::GetWorkloadModelPackageSessionClassNames_::_1_::dtor$97

- ea: `0x18001de2b`
- end: `0x18001de56`
- name: `_winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::GetWorkloadModelPackageSessionClassNames_::_1_::dtor$97`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004e00`
- `0x18001de2b`

## pseudocode

```c
void __fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::GetWorkloadModelPackageSessionClassNames_::_1_::dtor_97(
        __int64 a1,
        __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 48) & 0x1000) != 0 )
  {
    *(_DWORD *)(a2 + 48) &= ~0x1000u;
    winrt::Windows::Foundation::IAsyncAction::~IAsyncAction((winrt::Windows::Foundation::IAsyncAction *)(a2 + 32));
  }
}

```

## disassembly

```asm
0x18001de2b  push    rbp
0x18001de2d  sub     rsp, 20h
0x18001de31  mov     rbp, rdx
0x18001de34  mov     eax, [rbp+30h]
0x18001de37  and     eax, 1000h
0x18001de3c  test    eax, eax
0x18001de3e  jz      short loc_18001DE50
0x18001de40  and     dword ptr [rbp+30h], 0FFFFEFFFh
0x18001de47  lea     rcx, [rbp+20h]; this
0x18001de4b  call    ??1IAsyncAction@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncAction::~IAsyncAction(void)
0x18001de50  add     rsp, 20h
0x18001de54  pop     rbp
0x18001de55  retn
```
