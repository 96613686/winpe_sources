# winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::EnsureModelIsCachedAsync(winrt::hstring)

- ea: `0x180005ba0`
- end: `0x180005d27`
- name: `?EnsureModelIsCachedAsync@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@QEAA?AUIAsyncAction@Foundation@57@Uhstring@7@@Z`
- size: `391`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, volatile signed __int32 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800093a0`

## callees

- `0x180005ba0`
- `0x180016298`
- `0x18001629e`
- `0x180017cfc`
- `0x1800181b0`
- `0x1800181fc`
- `0x18001ca20`
- `0x18001cdf0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180005d20`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180005d20`

## pseudocode

```c
_QWORD *__fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::EnsureModelIsCachedAsync(
        __int64 a1,
        _QWORD *a2,
        volatile signed __int32 **a3)
{
  _QWORD *v6; // rax
  char *v7; // rbx
  volatile signed __int32 *v8; // rax
  char *v9; // r14
  char *v10; // rcx
  volatile signed __int32 *v11; // rbx
  int v12; // eax
  HANDLE ProcessHeap; // rax

  v6 = operator new(0xD0u);
  v7 = (char *)(v6 + 14);
  v6[23] = a1;
  v8 = *a3;
  *a3 = 0;
  *((_QWORD *)v7 + 10) = v8;
  *(_QWORD *)v7 = winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::EnsureModelIsCachedAsync__ResumeCoro_1;
  *((_DWORD *)v7 + 2) = 65538;
  *((_OWORD *)v7 - 7) = 0;
  *((_OWORD *)v7 - 6) = 0;
  *((_OWORD *)v7 - 5) = 0;
  *((_OWORD *)v7 - 4) = 0;
  *((_OWORD *)v7 - 3) = 0;
  *((_OWORD *)v7 - 2) = 0;
  *((_QWORD *)v7 - 2) = 0;
  v9 = v7 - 96;
  *(_QWORD *)v9 = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction>::`vftable';
  *((_QWORD *)v9 + 1) = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *((_QWORD *)v7 - 13) = 1;
  *((_QWORD *)v7 - 10) = 0;
  *((_QWORD *)v7 - 9) = 0;
  *(v7 - 64) = 0;
  *((_QWORD *)v7 - 14) = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`vftable';
  v10 = v7 - 56;
  *(_QWORD *)v10 = 0;
  *((_QWORD *)v10 + 1) = 0;
  __ExceptionPtrCreate(v7 - 56);
  *((_QWORD *)v7 - 5) = 0;
  *((_QWORD *)v7 - 4) = 0;
  *((_QWORD *)v7 - 3) = 0;
  *((_DWORD *)v7 - 4) = 0;
  *(v7 - 12) = 0;
  *((_QWORD *)v7 - 14) = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`vftable';
  *a2 = v7 - 96;
  if ( v7 != (char *)96 )
    (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 8LL))(v7 - 96);
  v7[64] = 0;
  winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::EnsureModelIsCachedAsync__ResumeCoro_1(v7);
  v11 = *a3;
  if ( *a3 )
  {
    v12 = _InterlockedDecrement(v11 + 6);
    if ( v12 )
    {
      if ( v12 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v11);
    }
    *a3 = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x180005ba0  mov     [rsp+arg_0], rbx
0x180005ba5  push    rbp
0x180005ba6  push    rsi
0x180005ba7  push    rdi
0x180005ba8  push    r14
0x180005baa  push    r15
0x180005bac  sub     rsp, 50h
0x180005bb0  mov     rax, cs:__security_cookie
0x180005bb7  xor     rax, rsp
0x180005bba  mov     [rsp+78h+var_30], rax
0x180005bbf  mov     rdi, r8
0x180005bc2  mov     rsi, rdx
0x180005bc5  mov     rbp, rcx
0x180005bc8  mov     [rsp+78h+var_50], rdx
0x180005bcd  mov     [rsp+78h+var_48], r8
0x180005bd2  mov     r15d, 40h ; '@'
0x180005bd8  lea     rcx, [r15+90h]; Size
0x180005bdf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005be4  mov     [rsp+78h+var_58], rax
0x180005be9  lea     rbx, [rax+70h]
0x180005bed  mov     [rsp+78h+var_58], rbx
0x180005bf2  mov     [rbx+r15+8], rbp
0x180005bf7  mov     rax, [rdi]
0x180005bfa  xor     ebp, ebp
0x180005bfc  mov     [rdi], rbp
0x180005bff  mov     [rbx+r15+10h], rax
0x180005c04  lea     rax, winrt__Microsoft__Windows__Private__CacheManagement__implementation__ModelCacheManager__EnsureModelIsCachedAsync$_ResumeCoro$1
0x180005c0b  mov     [rbx], rax
0x180005c0e  mov     dword ptr [rbx+8], 10002h
0x180005c15  xorps   xmm0, xmm0
0x180005c18  xor     eax, eax
0x180005c1a  movups  xmmword ptr [rbx-70h], xmm0
0x180005c1e  movups  xmmword ptr [rbx-60h], xmm0
0x180005c22  movups  xmmword ptr [rbx-50h], xmm0
0x180005c26  movups  xmmword ptr [rbx-40h], xmm0
0x180005c2a  movups  xmmword ptr [rbx-30h], xmm0
0x180005c2e  movups  xmmword ptr [rbx-20h], xmm0
0x180005c32  mov     [rbx-10h], rax
0x180005c36  lea     r14, [rbx-60h]
0x180005c3a  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction>::`vftable'
0x180005c41  mov     [r14], rax
0x180005c44  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x180005c4b  mov     [r14+8], rax
0x180005c4f  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180005c56  mov     qword ptr [rbx-68h], 1
0x180005c5e  mov     [rbx-50h], rbp
0x180005c62  mov     [rbx-48h], rbp
0x180005c66  mov     [rbx-40h], bpl
0x180005c6a  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`vftable'
0x180005c71  mov     [rbx-70h], rax
0x180005c75  lea     rcx, [rbx-38h]; void *
0x180005c79  mov     [rcx], rbp
0x180005c7c  mov     [rcx+8], rbp
0x180005c80  call    ?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180005c85  mov     [rbx-28h], rbp
0x180005c89  mov     [rbx-20h], rbp
0x180005c8d  mov     [rbx-18h], rbp
0x180005c91  xor     eax, eax
0x180005c93  mov     [rbx-10h], eax
0x180005c96  mov     [rbx-0Ch], al
0x180005c99  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`vftable'
0x180005ca0  mov     [rbx-70h], rax
0x180005ca4  mov     [rsi], r14
0x180005ca7  test    r14, r14
0x180005caa  jz      short loc_180005CBD
0x180005cac  mov     rax, [r14]
0x180005caf  mov     rcx, r14
0x180005cb2  mov     rax, [rax+8]
0x180005cb6  call    cs:__guard_dispatch_icall_fptr
0x180005cbc  nop
0x180005cbd  xor     eax, eax
0x180005cbf  mov     [rbx+r15], al
0x180005cc3  mov     rcx, rbx
0x180005cc6  call    winrt__Microsoft__Windows__Private__CacheManagement__implementation__ModelCacheManager__EnsureModelIsCachedAsync$_ResumeCoro$1
0x180005ccb  nop
0x180005ccc  mov     rbx, [rdi]
0x180005ccf  test    rbx, rbx
0x180005cd2  jz      short loc_180005CF8
0x180005cd4  mov     eax, 0FFFFFFFFh
0x180005cd9  lock xadd [rbx+18h], eax
0x180005cde  sub     eax, 1
0x180005ce1  jnz     short loc_180005D1C
0x180005ce3  call    WINRT_IMPL_GetProcessHeap
0x180005ce8  mov     rcx, rax; hHeap
0x180005ceb  mov     r8, rbx; lpMem
0x180005cee  xor     edx, edx; dwFlags
0x180005cf0  call    WINRT_IMPL_HeapFree
0x180005cf5  mov     [rdi], rbp
0x180005cf8  mov     rax, rsi
0x180005cfb  mov     rcx, [rsp+78h+var_30]
0x180005d00  xor     rcx, rsp; StackCookie
0x180005d03  call    __security_check_cookie
0x180005d08  mov     rbx, [rsp+78h+arg_0]
0x180005d10  add     rsp, 50h
0x180005d14  pop     r15
0x180005d16  pop     r14
0x180005d18  pop     rdi
0x180005d19  pop     rsi
0x180005d1a  pop     rbp
0x180005d1b  retn
0x180005d1c  test    eax, eax
0x180005d1e  jns     short loc_180005CF5
0x180005d20  call    cs:__imp_abort
```
