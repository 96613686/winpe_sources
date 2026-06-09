# winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheModelWithOfflineDriverAsync(winrt::hstring,winrt::hstring)

- ea: `0x180005e70`
- end: `0x180006039`
- name: `?CacheModelWithOfflineDriverAsync@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@QEAA?AUIAsyncAction@Foundation@57@Uhstring@7@0@Z`
- size: `457`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, volatile signed __int32 **, volatile signed __int32 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180009310`

## callees

- `0x180005e70`
- `0x180016298`
- `0x18001629e`
- `0x180017cfc`
- `0x1800181b0`
- `0x1800181fc`
- `0x18001c7a0`
- `0x18001cdf0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006027`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006032`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006027`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006032`

## pseudocode

```c
_QWORD *__fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheModelWithOfflineDriverAsync(
        __int64 a1,
        _QWORD *a2,
        volatile signed __int32 **a3,
        volatile signed __int32 **a4)
{
  _QWORD *v8; // rax
  char *v9; // rbx
  volatile signed __int32 *v10; // rax
  volatile signed __int32 *v11; // rax
  char *v12; // rdi
  char *v13; // rcx
  volatile signed __int32 *v14; // rbx
  int v15; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v17; // rbx
  int v18; // edi
  HANDLE v19; // rax

  v8 = operator new(0x150u);
  v9 = (char *)(v8 + 14);
  v8[39] = a1;
  v10 = *a3;
  *a3 = 0;
  *((_QWORD *)v9 + 26) = v10;
  v11 = *a4;
  *a4 = 0;
  *((_QWORD *)v9 + 27) = v11;
  *(_QWORD *)v9 = winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheModelWithOfflineDriverAsync__ResumeCoro_1;
  *((_DWORD *)v9 + 2) = 65538;
  *((_OWORD *)v9 - 7) = 0;
  *((_OWORD *)v9 - 6) = 0;
  *((_OWORD *)v9 - 5) = 0;
  *((_OWORD *)v9 - 4) = 0;
  *((_OWORD *)v9 - 3) = 0;
  *((_OWORD *)v9 - 2) = 0;
  *((_QWORD *)v9 - 2) = 0;
  v12 = v9 - 96;
  *(_QWORD *)v12 = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction>::`vftable';
  *((_QWORD *)v12 + 1) = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *((_QWORD *)v9 - 13) = 1;
  *((_QWORD *)v9 - 10) = 0;
  *((_QWORD *)v9 - 9) = 0;
  *(v9 - 64) = 0;
  *((_QWORD *)v9 - 14) = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`vftable';
  v13 = v9 - 56;
  *(_QWORD *)v13 = 0;
  *((_QWORD *)v13 + 1) = 0;
  __ExceptionPtrCreate(v9 - 56);
  *((_QWORD *)v9 - 5) = 0;
  *((_QWORD *)v9 - 4) = 0;
  *((_QWORD *)v9 - 3) = 0;
  *((_DWORD *)v9 - 4) = 0;
  *(v9 - 12) = 0;
  *((_QWORD *)v9 - 14) = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`vftable';
  *a2 = v9 - 96;
  if ( v9 != (char *)96 )
    (*(void (__fastcall **)(char *))(*(_QWORD *)v12 + 8LL))(v9 - 96);
  v9[192] = 0;
  winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheModelWithOfflineDriverAsync__ResumeCoro_1(v9);
  v14 = *a3;
  if ( *a3 )
  {
    v15 = _InterlockedDecrement(v14 + 6);
    if ( v15 )
    {
      if ( v15 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v14);
    }
    *a3 = 0;
  }
  v17 = *a4;
  if ( *a4 )
  {
    v18 = _InterlockedDecrement(v17 + 6);
    if ( v18 )
    {
      if ( v18 < 0 )
        abort();
    }
    else
    {
      v19 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v19, 0, (LPVOID)v17);
    }
    *a4 = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x180005e70  push    rbx
0x180005e72  push    rbp
0x180005e73  push    rsi
0x180005e74  push    rdi
0x180005e75  push    r12
0x180005e77  push    r14
0x180005e79  push    r15
0x180005e7b  sub     rsp, 60h
0x180005e7f  mov     rax, cs:__security_cookie
0x180005e86  xor     rax, rsp
0x180005e89  mov     [rsp+98h+var_48], rax
0x180005e8e  mov     rsi, r9
0x180005e91  mov     r14, r8
0x180005e94  mov     r15, rdx
0x180005e97  mov     rdi, rcx
0x180005e9a  mov     [rsp+98h+var_70], rdx
0x180005e9f  mov     [rsp+98h+var_68], r8
0x180005ea4  mov     [rsp+98h+var_60], r9
0x180005ea9  mov     r12d, 0C0h
0x180005eaf  lea     rcx, [r12+90h]; Size
0x180005eb7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005ebc  mov     [rsp+98h+var_78], rax
0x180005ec1  lea     rbx, [rax+70h]
0x180005ec5  mov     [rsp+98h+var_78], rbx
0x180005eca  mov     [rbx+r12+8], rdi
0x180005ecf  mov     rax, [r14]
0x180005ed2  xor     ebp, ebp
0x180005ed4  mov     [r14], rbp
0x180005ed7  mov     [rbx+r12+10h], rax
0x180005edc  mov     rax, [rsi]
0x180005edf  mov     [rsi], rbp
0x180005ee2  mov     [rbx+r12+18h], rax
0x180005ee7  lea     rax, winrt__Microsoft__Windows__Private__CacheManagement__implementation__ModelCacheManager__CacheModelWithOfflineDriverAsync$_ResumeCoro$1
0x180005eee  mov     [rbx], rax
0x180005ef1  mov     dword ptr [rbx+8], 10002h
0x180005ef8  xorps   xmm0, xmm0
0x180005efb  xor     eax, eax
0x180005efd  movups  xmmword ptr [rbx-70h], xmm0
0x180005f01  movups  xmmword ptr [rbx-60h], xmm0
0x180005f05  movups  xmmword ptr [rbx-50h], xmm0
0x180005f09  movups  xmmword ptr [rbx-40h], xmm0
0x180005f0d  movups  xmmword ptr [rbx-30h], xmm0
0x180005f11  movups  xmmword ptr [rbx-20h], xmm0
0x180005f15  mov     [rbx-10h], rax
0x180005f19  lea     rdi, [rbx-60h]
0x180005f1d  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction>::`vftable'
0x180005f24  mov     [rdi], rax
0x180005f27  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x180005f2e  mov     [rdi+8], rax
0x180005f32  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180005f39  mov     qword ptr [rbx-68h], 1
0x180005f41  mov     [rbx-50h], rbp
0x180005f45  mov     [rbx-48h], rbp
0x180005f49  mov     [rbx-40h], bpl
0x180005f4d  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`vftable'
0x180005f54  mov     [rbx-70h], rax
0x180005f58  lea     rcx, [rbx-38h]; void *
0x180005f5c  mov     [rcx], rbp
0x180005f5f  mov     [rcx+8], rbp
0x180005f63  call    ?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180005f68  mov     [rbx-28h], rbp
0x180005f6c  mov     [rbx-20h], rbp
0x180005f70  mov     [rbx-18h], rbp
0x180005f74  xor     eax, eax
0x180005f76  mov     [rbx-10h], eax
0x180005f79  mov     [rbx-0Ch], al
0x180005f7c  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`vftable'
0x180005f83  mov     [rbx-70h], rax
0x180005f87  mov     [r15], rdi
0x180005f8a  test    rdi, rdi
0x180005f8d  jz      short loc_180005FA0
0x180005f8f  mov     rax, [rdi]
0x180005f92  mov     rcx, rdi
0x180005f95  mov     rax, [rax+8]
0x180005f99  call    cs:__guard_dispatch_icall_fptr
0x180005f9f  nop
0x180005fa0  xor     eax, eax
0x180005fa2  mov     [rbx+r12], al
0x180005fa6  mov     rcx, rbx
0x180005fa9  call    winrt__Microsoft__Windows__Private__CacheManagement__implementation__ModelCacheManager__CacheModelWithOfflineDriverAsync$_ResumeCoro$1
0x180005fae  nop
0x180005faf  mov     rbx, [r14]
0x180005fb2  mov     edi, 0FFFFFFFFh
0x180005fb7  test    rbx, rbx
0x180005fba  jz      short loc_180005FDD
0x180005fbc  mov     eax, edi
0x180005fbe  lock xadd [rbx+18h], eax
0x180005fc3  sub     eax, 1
0x180005fc6  jnz     short loc_180006023
0x180005fc8  call    WINRT_IMPL_GetProcessHeap
0x180005fcd  mov     rcx, rax; hHeap
0x180005fd0  mov     r8, rbx; lpMem
0x180005fd3  xor     edx, edx; dwFlags
0x180005fd5  call    WINRT_IMPL_HeapFree
0x180005fda  mov     [r14], rbp
0x180005fdd  mov     rbx, [rsi]
0x180005fe0  test    rbx, rbx
0x180005fe3  jz      short loc_180006004
0x180005fe5  lock xadd [rbx+18h], edi
0x180005fea  sub     edi, 1
0x180005fed  jnz     short loc_18000602E
0x180005fef  call    WINRT_IMPL_GetProcessHeap
0x180005ff4  mov     rcx, rax; hHeap
0x180005ff7  mov     r8, rbx; lpMem
0x180005ffa  xor     edx, edx; dwFlags
0x180005ffc  call    WINRT_IMPL_HeapFree
0x180006001  mov     [rsi], rbp
0x180006004  mov     rax, r15
0x180006007  mov     rcx, [rsp+98h+var_48]
0x18000600c  xor     rcx, rsp; StackCookie
0x18000600f  call    __security_check_cookie
0x180006014  add     rsp, 60h
0x180006018  pop     r15
0x18000601a  pop     r14
0x18000601c  pop     r12
0x18000601e  pop     rdi
0x18000601f  pop     rsi
0x180006020  pop     rbp
0x180006021  pop     rbx
0x180006022  retn
0x180006023  test    eax, eax
0x180006025  jns     short loc_180005FDA
0x180006027  call    cs:__imp_abort
0x18000602e  test    edi, edi
0x180006030  jns     short loc_180006001
0x180006032  call    cs:__imp_abort
```
