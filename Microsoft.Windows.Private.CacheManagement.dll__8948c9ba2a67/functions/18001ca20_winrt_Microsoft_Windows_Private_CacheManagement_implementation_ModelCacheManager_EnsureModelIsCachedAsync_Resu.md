# winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::EnsureModelIsCachedAsync$_ResumeCoro$1

- ea: `0x18001ca20`
- end: `0x18001cca0`
- name: `winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::EnsureModelIsCachedAsync$_ResumeCoro$1`
- size: `640`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005ba0`

## callees

- `0x180003840`
- `0x180007410`
- `0x1800085a0`
- `0x180009b70`
- `0x180011e30`
- `0x1800127e0`
- `0x1800128a0`
- `0x180016298`
- `0x18001629e`
- `0x180017d94`
- `0x1800181b0`
- `0x180018238`
- `0x180019c0c`
- `0x18001ca20`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18001cb88`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18001cc53`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18001cb88`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18001cc53`

## pseudocode

```c
void __fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::EnsureModelIsCachedAsync__ResumeCoro_1(
        __int64 a1)
{
  _WORD *v2; // r14
  winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *v3; // rcx
  volatile signed __int32 *v4; // r15
  int v5; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v7; // r15
  int v8; // eax
  HANDLE v9; // rax
  volatile signed __int32 *v10; // r14
  int v11; // edi
  HANDLE v12; // rax
  _BYTE pExceptionObject[24]; // [rsp+38h] [rbp-60h] BYREF
  __int64 v14; // [rsp+50h] [rbp-48h]
  volatile signed __int32 *v15; // [rsp+58h] [rbp-40h]

  v2 = (_WORD *)(a1 + 8);
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
    case 5:
      goto LABEL_17;
    case 2:
      if ( *(_DWORD *)(a1 - 16) == 2 )
      {
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)pExceptionObject);
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *v2 = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(a1, a1);
      return;
    case 4:
      *(_QWORD *)(a1 + 16) = winrt::impl::duplicate_hstring(
                               *(winrt::impl **)(a1 + 80),
                               (struct winrt::impl::hstring_header *)0x180000000LL);
      *(_BYTE *)(a1 + 32) = 0;
      *(_BYTE *)(a1 + 40) = 1;
      winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::StartWorkloadSessionAndCacheModels(
        v3,
        (const struct winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *)(a1 + 16));
      if ( !*(_BYTE *)(a1 + 32) )
        goto LABEL_11;
      v4 = *(volatile signed __int32 **)(a1 + 24);
      v15 = v4;
      if ( !v4 )
        goto LABEL_11;
      v15 = *(volatile signed __int32 **)(a1 + 24);
      v5 = _InterlockedDecrement(v15 + 6);
      if ( v5 )
      {
        if ( v5 < 0 )
          goto LABEL_15;
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v4);
      }
      *(_QWORD *)(a1 + 24) = 0;
LABEL_11:
      v7 = *(volatile signed __int32 **)(a1 + 16);
      if ( v7 )
      {
        v14 = *(_QWORD *)(a1 + 16);
        v8 = _InterlockedDecrement(v7 + 6);
        if ( !v8 )
        {
          v9 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v9, 0, (LPVOID)v7);
          goto LABEL_16;
        }
        if ( v8 < 0 )
LABEL_15:
          abort();
      }
LABEL_16:
      *(_QWORD *)(a1 + 48) = a1 - 112;
      *v2 = 0;
      if ( (unsigned __int8)winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend() )
        return;
LABEL_17:
      if ( *(_QWORD *)(a1 - 24) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 - 24);
      if ( *(_QWORD *)(a1 - 32) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 - 32);
      __ExceptionPtrDestroy((void *)(a1 - 56));
      winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::subtract_final_reference(a1 - 112);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        goto LABEL_29;
      v10 = *(volatile signed __int32 **)(a1 + 80);
      if ( !v10 )
        goto LABEL_27;
      v11 = _InterlockedDecrement(v10 + 6);
      if ( v11 )
      {
        if ( v11 >= 0 )
          goto LABEL_26;
LABEL_29:
        abort();
      }
      v12 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v12, 0, (LPVOID)v10);
LABEL_26:
      *(_QWORD *)(a1 + 80) = 0;
LABEL_27:
      if ( *(_WORD *)(a1 + 10) )
        operator delete((void *)(a1 - 112), 0xD0u);
      return;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x18001ca20  mov     r11, rsp
0x18001ca23  mov     [r11+10h], rbx
0x18001ca27  mov     [r11+18h], rsi
0x18001ca2b  mov     [r11+8], rcx
0x18001ca2f  push    rdi
0x18001ca30  push    r14
0x18001ca32  push    r15
0x18001ca34  sub     rsp, 80h
0x18001ca3b  mov     rax, cs:__security_cookie
0x18001ca42  xor     rax, rsp
0x18001ca45  mov     [rsp+98h+var_20], rax
0x18001ca4a  mov     rbx, rcx
0x18001ca4d  mov     [rsp+98h+var_70], rcx
0x18001ca52  lea     r14, [rbx+8]
0x18001ca56  mov     [rsp+98h+var_68], r14
0x18001ca5b  movzx   eax, word ptr [r14]
0x18001ca5f  mov     [rsp+98h+var_76], ax
0x18001ca64  inc     ax; switch 7 cases
0x18001ca67  cmp     ax, 6
0x18001ca6b  ja      def_18001CA86; jumptable 000000018001CA86 default case, case 0
0x18001ca71  movsx   rax, ax
0x18001ca75  lea     rdx, cs:180000000h; struct winrt::impl::hstring_header *
0x18001ca7c  mov     ecx, ds:(jpt_18001CA86 - 180000000h)[rdx+rax*4]
0x18001ca83  add     rcx, rdx
0x18001ca86  jmp     rcx; switch jump
0x18001ca88  mov     edi, 0FFFFFFFFh; jumptable 000000018001CA86 case 3
0x18001ca8d  jmp     loc_18001CBC5
0x18001ca92  mov     [rsp+98h+var_78], 0; jumptable 000000018001CA86 case 2
0x18001ca97  mov     eax, [rbx-10h]
0x18001ca9a  cmp     eax, 2
0x18001ca9d  jnz     short loc_18001CABA
0x18001ca9f  lea     rcx, [rsp+98h+pExceptionObject]; this
0x18001caa4  call    ??0hresult_canceled@winrt@@QEAA@XZ; winrt::hresult_canceled::hresult_canceled(void)
0x18001caa9  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18001cab0  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18001cab5  call    _CxxThrowException
0x18001caba  mov     eax, 4
0x18001cabf  mov     [r14], ax
0x18001cac3  mov     rdx, rbx
0x18001cac6  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@experimental@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::experimental::coroutine_handle<void>)
0x18001cacb  jmp     loc_18001CC5B
0x18001cad0  mov     edi, 0FFFFFFFFh; jumptable 000000018001CA86 case 5
0x18001cad5  jmp     loc_18001CBC5
0x18001cada  mov     rcx, [rbx+50h]; jumptable 000000018001CA86 case 4
0x18001cade  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x18001cae3  mov     [rbx+10h], rax
0x18001cae7  mov     byte ptr [rbx+20h], 0
0x18001caeb  mov     byte ptr [rbx+28h], 1
0x18001caef  lea     rdx, [rbx+10h]; struct winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *
0x18001caf3  call    ?StartWorkloadSessionAndCacheModels@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@AEAAXAEBUCacheQueueItem@1234567@@Z; winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::StartWorkloadSessionAndCacheModels(winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem const &)
0x18001caf8  nop
0x18001caf9  movzx   eax, byte ptr [rbx+20h]
0x18001cafd  mov     [rsp+98h+var_38], al
0x18001cb01  test    al, al
0x18001cb03  jz      short loc_18001CB4F
0x18001cb05  mov     r15, [rbx+18h]
0x18001cb09  mov     [rsp+98h+var_40], r15
0x18001cb0e  test    r15, r15
0x18001cb11  jz      short loc_18001CB4F
0x18001cb13  mov     rcx, [rbx+18h]
0x18001cb17  mov     [rsp+98h+var_40], rcx
0x18001cb1c  mov     edi, 0FFFFFFFFh
0x18001cb21  mov     eax, edi
0x18001cb23  lock xadd [rcx+18h], eax
0x18001cb28  sub     eax, 1
0x18001cb2b  jnz     short loc_18001CB41
0x18001cb2d  call    WINRT_IMPL_GetProcessHeap
0x18001cb32  mov     rcx, rax; hHeap
0x18001cb35  mov     r8, r15; lpMem
0x18001cb38  xor     edx, edx; dwFlags
0x18001cb3a  call    WINRT_IMPL_HeapFree
0x18001cb3f  jmp     short loc_18001CB45
0x18001cb41  test    eax, eax
0x18001cb43  js      short loc_18001CB88
0x18001cb45  mov     qword ptr [rbx+18h], 0
0x18001cb4d  jmp     short loc_18001CB54
0x18001cb4f  mov     edi, 0FFFFFFFFh
0x18001cb54  mov     r15, [rbx+10h]
0x18001cb58  cmp     r15, 0
0x18001cb5c  jz      short loc_18001CB8F
0x18001cb5e  mov     [rsp+98h+var_48], r15
0x18001cb63  mov     eax, edi
0x18001cb65  lock xadd [r15+18h], eax
0x18001cb6b  sub     eax, 1
0x18001cb6e  jnz     short loc_18001CB84
0x18001cb70  call    WINRT_IMPL_GetProcessHeap
0x18001cb75  mov     rcx, rax; hHeap
0x18001cb78  mov     r8, r15; lpMem
0x18001cb7b  xor     edx, edx; dwFlags
0x18001cb7d  call    WINRT_IMPL_HeapFree
0x18001cb82  jmp     short loc_18001CB8F
0x18001cb84  test    eax, eax
0x18001cb86  jns     short loc_18001CB8F
0x18001cb88  call    cs:__imp_abort
0x18001cb8f  jmp     short loc_18001CBA0
0x18001cb91  mov     edi, 0FFFFFFFFh
0x18001cb96  mov     r14, [rsp+98h+var_68]
0x18001cb9b  mov     rbx, [rsp+98h+var_70]
0x18001cba0  lea     rcx, [rbx+30h]
0x18001cba4  lea     rax, [rbx-70h]
0x18001cba8  mov     [rcx], rax
0x18001cbab  xor     eax, eax
0x18001cbad  mov     [r14], ax
0x18001cbb1  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@experimental@std@@@Z; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend(std::experimental::coroutine_handle<void>)
0x18001cbb6  test    al, al
0x18001cbb8  jz      short loc_18001CBC5
0x18001cbba  jmp     loc_18001CC5B
0x18001cbc0  mov     edi, 0FFFFFFFFh; jumptable 000000018001CA86 cases -1,1
0x18001cbc5  lea     rcx, [rbx-18h]
0x18001cbc9  cmp     qword ptr [rcx], 0
0x18001cbcd  jz      short loc_18001CBD4
0x18001cbcf  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001cbd4  lea     rcx, [rbx-20h]
0x18001cbd8  cmp     qword ptr [rcx], 0
0x18001cbdc  jz      short loc_18001CBE3
0x18001cbde  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001cbe3  lea     rcx, [rbx-38h]; void *
0x18001cbe7  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18001cbec  lea     rcx, [rbx-70h]
0x18001cbf0  call    ?subtract_final_reference@?$root_implements@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@U134567@UIModelCacheManager2@34567@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::subtract_final_reference(void)
0x18001cbf5  mov     eax, edi
0x18001cbf7  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001cbff  sub     eax, 1
0x18001cc02  jz      short loc_18001CC08
0x18001cc04  test    eax, eax
0x18001cc06  js      short loc_18001CC53
0x18001cc08  mov     r14, [rbx+50h]
0x18001cc0c  test    r14, r14
0x18001cc0f  jz      short loc_18001CC3C
0x18001cc11  lock xadd [r14+18h], edi
0x18001cc17  sub     edi, 1
0x18001cc1a  jnz     short loc_18001CC30
0x18001cc1c  call    WINRT_IMPL_GetProcessHeap
0x18001cc21  mov     rcx, rax; hHeap
0x18001cc24  mov     r8, r14; lpMem
0x18001cc27  xor     edx, edx; dwFlags
0x18001cc29  call    WINRT_IMPL_HeapFree
0x18001cc2e  jmp     short loc_18001CC34
0x18001cc30  test    edi, edi
0x18001cc32  js      short loc_18001CC53
0x18001cc34  mov     qword ptr [rbx+50h], 0
0x18001cc3c  cmp     word ptr [rbx+0Ah], 0
0x18001cc41  jz      short loc_18001CC5B
0x18001cc43  mov     edx, 0D0h; unsigned __int64
0x18001cc48  lea     rcx, [rbx-70h]; void *
0x18001cc4c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001cc51  jmp     short loc_18001CC5B
0x18001cc53  call    cs:__imp_abort
0x18001cc5a  int     3; Trap to Debugger
0x18001cc5b  mov     rcx, [rsp+98h+var_20]
0x18001cc60  xor     rcx, rsp; StackCookie
0x18001cc63  call    __security_check_cookie
0x18001cc68  lea     r11, [rsp+98h+var_18]
0x18001cc70  mov     rbx, [r11+28h]
0x18001cc74  mov     rsi, [r11+30h]
0x18001cc78  mov     rsp, r11
0x18001cc7b  pop     r15
0x18001cc7d  pop     r14
0x18001cc7f  pop     rdi
0x18001cc80  retn
```
