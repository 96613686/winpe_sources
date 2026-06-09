# _winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::GetWorkloadModelPackageSessionClassNames_::_1_::dtor$78

- ea: `0x18001ddf4`
- end: `0x18001de1f`
- name: `_winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::GetWorkloadModelPackageSessionClassNames_::_1_::dtor$78`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004e00`
- `0x18001ddf4`

## pseudocode

```c
void __fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::GetWorkloadModelPackageSessionClassNames_::_1_::dtor_78(
        __int64 a1,
        __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 48) & 0x400) != 0 )
  {
    *(_DWORD *)(a2 + 48) &= ~0x400u;
    winrt::Windows::Foundation::IAsyncAction::~IAsyncAction((winrt::Windows::Foundation::IAsyncAction *)(a2 + 32));
  }
}

```

## disassembly

```asm
0x18001ddf4  push    rbp
0x18001ddf6  sub     rsp, 20h
0x18001ddfa  mov     rbp, rdx
0x18001ddfd  mov     eax, [rbp+30h]
0x18001de00  and     eax, 400h
0x18001de05  test    eax, eax
0x18001de07  jz      short loc_18001DE19
0x18001de09  and     dword ptr [rbp+30h], 0FFFFFBFFh
0x18001de10  lea     rcx, [rbp+20h]; this
0x18001de14  call    ??1IAsyncAction@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncAction::~IAsyncAction(void)
0x18001de19  add     rsp, 20h
0x18001de1d  pop     rbp
0x18001de1e  retn
```
