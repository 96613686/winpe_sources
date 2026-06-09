# winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::subtract_final_reference(void)

- ea: `0x180009b70`
- end: `0x180009bf0`
- name: `?subtract_final_reference@?$root_implements@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@U134567@UIModelCacheManager2@34567@@impl@winrt@@IEAAIXZ`
- size: `128`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `13`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800050f0`
- `0x180005190`
- `0x180005d90`
- `0x180005df0`
- `0x1800085a0`
- `0x180008710`
- `0x180008a30`
- `0x180008f70`
- `0x180009070`
- `0x180009ed0`
- `0x18000ac20`
- `0x18001c7a0`
- `0x18001ca20`

## callees

- `0x180009b70`
- `0x180018238`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180009be9`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180009be9`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::subtract_final_reference(
        __int64 a1)
{
  signed __int64 v1; // rax
  unsigned int v2; // edx
  signed __int64 v3; // rtt
  volatile signed __int32 *v4; // rcx
  unsigned __int32 v5; // ebx

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 < 0 )
  {
LABEL_4:
    v4 = (volatile signed __int32 *)(2 * v1);
    v5 = _InterlockedDecrement((volatile signed __int32 *)(2 * v1 + 24));
    if ( !v5 && _InterlockedExchangeAdd(v4 + 7, 0xFFFFFFFF) == 1 && v4 )
    {
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      operator delete((void *)v4);
    }
    return v5;
  }
  else
  {
    while ( 1 )
    {
      v2 = v1 - 1;
      v3 = v1;
      v1 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 8), v1 - 1, v1);
      if ( v3 == v1 )
        return v2;
      if ( v1 < 0 )
        goto LABEL_4;
    }
  }
}

```

## disassembly

```asm
0x180009b70  sub     rsp, 28h
0x180009b74  mov     rax, [rcx+8]
0x180009b78  test    rax, rax
0x180009b7b  js      short loc_180009B91
0x180009b7d  nop     dword ptr [rax]
0x180009b80  lea     rdx, [rax-1]
0x180009b84  lock cmpxchg [rcx+8], rdx
0x180009b8a  jz      short loc_180009BDE
0x180009b8c  test    rax, rax
0x180009b8f  jns     short loc_180009B80
0x180009b91  mov     edx, 0FFFFFFFFh
0x180009b96  mov     [rsp+28h+var_8], rbx
0x180009b9b  mov     ebx, edx
0x180009b9d  lea     rcx, [rax+rax]; void *
0x180009ba1  lock xadd [rcx+18h], ebx
0x180009ba6  sub     ebx, 1
0x180009ba9  jnz     short loc_180009BD2
0x180009bab  mov     eax, edx
0x180009bad  lock xadd [rcx+1Ch], eax
0x180009bb2  cmp     eax, 1
0x180009bb5  jnz     short loc_180009BD2
0x180009bb7  test    rcx, rcx
0x180009bba  jz      short loc_180009BD2
0x180009bbc  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, edx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180009bc4  sub     edx, eax
0x180009bc6  jnz     short loc_180009BE5
0x180009bc8  mov     edx, 20h ; ' '; unsigned __int64
0x180009bcd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009bd2  mov     eax, ebx
0x180009bd4  mov     rbx, [rsp+28h+var_8]
0x180009bd9  add     rsp, 28h
0x180009bdd  retn
0x180009bde  mov     eax, edx
0x180009be0  add     rsp, 28h
0x180009be4  retn
0x180009be5  test    edx, edx
0x180009be7  jns     short loc_180009BC8
0x180009be9  call    cs:__imp_abort
```
