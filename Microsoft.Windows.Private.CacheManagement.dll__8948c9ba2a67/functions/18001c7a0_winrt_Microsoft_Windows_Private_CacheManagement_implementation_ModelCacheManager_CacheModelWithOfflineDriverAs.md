# winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheModelWithOfflineDriverAsync$_ResumeCoro$1

- ea: `0x18001c7a0`
- end: `0x18001ca18`
- name: `winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheModelWithOfflineDriverAsync$_ResumeCoro$1`
- size: `632`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005e70`

## callees

- `0x180003840`
- `0x180006040`
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
- `0x18001c7a0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18001c92a`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18001c9a7`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18001c92a`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18001c9a7`

## pseudocode

```c
void __fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheModelWithOfflineDriverAsync__ResumeCoro_1(
        __int64 a1)
{
  _WORD *v2; // r14
  struct winrt::impl::hstring_header *v3; // rdx
  winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *v4; // rcx
  volatile signed __int32 *v5; // r15
  int v6; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v8; // r15
  int v9; // eax
  HANDLE v10; // rax
  _BYTE pExceptionObject[72]; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v12; // [rsp+B0h] [rbp-58h]
  volatile signed __int32 *v13; // [rsp+B8h] [rbp-50h]

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
                               *(winrt::impl **)(a1 + 208),
                               (struct winrt::impl::hstring_header *)0x180000000LL);
      *(_QWORD *)(a1 + 24) = winrt::impl::duplicate_hstring(*(winrt::impl **)(a1 + 216), v3);
      *(_BYTE *)(a1 + 32) = 1;
      *(_BYTE *)(a1 + 40) = 1;
      winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::StartWorkloadSessionAndCacheModels(
        v4,
        (const struct winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *)(a1 + 16));
      if ( !*(_BYTE *)(a1 + 32) )
        goto LABEL_11;
      v5 = *(volatile signed __int32 **)(a1 + 24);
      v13 = v5;
      if ( !v5 )
        goto LABEL_11;
      v13 = *(volatile signed __int32 **)(a1 + 24);
      v6 = _InterlockedDecrement(v13 + 6);
      if ( v6 )
      {
        if ( v6 < 0 )
          goto LABEL_15;
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v5);
      }
      *(_QWORD *)(a1 + 24) = 0;
LABEL_11:
      v8 = *(volatile signed __int32 **)(a1 + 16);
      if ( !v8 )
        goto LABEL_16;
      v12 = *(_QWORD *)(a1 + 16);
      v9 = _InterlockedDecrement(v8 + 6);
      if ( !v9 )
      {
        v10 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v10, 0, (LPVOID)v8);
        goto LABEL_16;
      }
      if ( v9 < 0 )
LABEL_15:
        abort();
LABEL_16:
      *(_QWORD *)(a1 + 176) = a1 - 112;
      *v2 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend() )
      {
LABEL_17:
        if ( *(_QWORD *)(a1 - 24) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref();
        if ( *(_QWORD *)(a1 - 32) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref();
        __ExceptionPtrDestroy((void *)(a1 - 56));
        winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::subtract_final_reference(a1 - 112);
        if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
          abort();
        winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheModelWithOfflineDriverAsync_::_22_::_parameters_::__parameters_(v2 + 96);
        if ( *(_WORD *)(a1 + 10) )
          operator delete((void *)(a1 - 112), 0x150u);
      }
      return;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x18001c7a0  mov     r11, rsp
0x18001c7a3  mov     [r11+10h], rbx
0x18001c7a7  mov     [r11+18h], rsi
0x18001c7ab  mov     [r11+8], rcx
0x18001c7af  push    rdi
0x18001c7b0  push    r14
0x18001c7b2  push    r15
0x18001c7b4  sub     rsp, 0F0h
0x18001c7bb  mov     rax, cs:__security_cookie
0x18001c7c2  xor     rax, rsp
0x18001c7c5  mov     [rsp+108h+var_20], rax
0x18001c7cd  mov     rbx, rcx
0x18001c7d0  mov     [rsp+108h+var_D0], rcx
0x18001c7d5  lea     r14, [rbx+8]
0x18001c7d9  mov     [rsp+108h+var_C0], r14
0x18001c7de  movzx   eax, word ptr [r14]
0x18001c7e2  mov     [rsp+108h+var_C8], ax
0x18001c7e7  inc     ax; switch 7 cases
0x18001c7ea  cmp     ax, 6
0x18001c7ee  ja      def_18001C809; jumptable 000000018001C809 default case, case 0
0x18001c7f4  movsx   rax, ax
0x18001c7f8  lea     rdx, cs:180000000h; struct winrt::impl::hstring_header *
0x18001c7ff  mov     ecx, ds:(jpt_18001C809 - 180000000h)[rdx+rax*4]
0x18001c806  add     rcx, rdx
0x18001c809  jmp     rcx; switch jump
0x18001c80b  mov     edi, 0FFFFFFFFh; jumptable 000000018001C809 case 3
0x18001c810  jmp     loc_18001C966
0x18001c815  mov     [rsp+108h+var_D8], 0; jumptable 000000018001C809 case 2
0x18001c81a  mov     eax, [rbx-10h]
0x18001c81d  cmp     eax, 2
0x18001c820  jnz     short loc_18001C83D
0x18001c822  lea     rcx, [rsp+108h+pExceptionObject]; this
0x18001c827  call    ??0hresult_canceled@winrt@@QEAA@XZ; winrt::hresult_canceled::hresult_canceled(void)
0x18001c82c  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18001c833  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18001c838  call    _CxxThrowException
0x18001c83d  mov     eax, 4
0x18001c842  mov     [r14], ax
0x18001c846  mov     rdx, rbx
0x18001c849  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@experimental@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::experimental::coroutine_handle<void>)
0x18001c84e  jmp     loc_18001C9D2
0x18001c853  mov     edi, 0FFFFFFFFh; jumptable 000000018001C809 case 5
0x18001c858  jmp     loc_18001C966
0x18001c85d  mov     rcx, [rbx+0D0h]; jumptable 000000018001C809 case 4
0x18001c864  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x18001c869  mov     [rbx+10h], rax
0x18001c86d  mov     rcx, [rbx+0D8h]; this
0x18001c874  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x18001c879  mov     [rbx+18h], rax
0x18001c87d  mov     byte ptr [rbx+20h], 1
0x18001c881  mov     byte ptr [rbx+28h], 1
0x18001c885  lea     rdx, [rbx+10h]; struct winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *
0x18001c889  call    ?StartWorkloadSessionAndCacheModels@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@AEAAXAEBUCacheQueueItem@1234567@@Z; winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::StartWorkloadSessionAndCacheModels(winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem const &)
0x18001c88e  nop
0x18001c88f  movzx   eax, byte ptr [rbx+20h]
0x18001c893  mov     [rsp+108h+var_48], al
0x18001c89a  test    al, al
0x18001c89c  jz      short loc_18001C8EE
0x18001c89e  mov     r15, [rbx+18h]
0x18001c8a2  mov     [rsp+108h+var_50], r15
0x18001c8aa  test    r15, r15
0x18001c8ad  jz      short loc_18001C8EE
0x18001c8af  mov     rcx, [rbx+18h]
0x18001c8b3  mov     [rsp+108h+var_50], rcx
0x18001c8bb  mov     edi, 0FFFFFFFFh
0x18001c8c0  mov     eax, edi
0x18001c8c2  lock xadd [rcx+18h], eax
0x18001c8c7  sub     eax, 1
0x18001c8ca  jnz     short loc_18001C8E0
0x18001c8cc  call    WINRT_IMPL_GetProcessHeap
0x18001c8d1  mov     rcx, rax; hHeap
0x18001c8d4  mov     r8, r15; lpMem
0x18001c8d7  xor     edx, edx; dwFlags
0x18001c8d9  call    WINRT_IMPL_HeapFree
0x18001c8de  jmp     short loc_18001C8E4
0x18001c8e0  test    eax, eax
0x18001c8e2  js      short loc_18001C92A
0x18001c8e4  mov     qword ptr [rbx+18h], 0
0x18001c8ec  jmp     short loc_18001C8F3
0x18001c8ee  mov     edi, 0FFFFFFFFh
0x18001c8f3  mov     r15, [rbx+10h]
0x18001c8f7  cmp     r15, 0
0x18001c8fb  jz      short loc_18001C931
0x18001c8fd  mov     [rsp+108h+var_58], r15
0x18001c905  mov     eax, edi
0x18001c907  lock xadd [r15+18h], eax
0x18001c90d  sub     eax, 1
0x18001c910  jnz     short loc_18001C926
0x18001c912  call    WINRT_IMPL_GetProcessHeap
0x18001c917  mov     rcx, rax; hHeap
0x18001c91a  mov     r8, r15; lpMem
0x18001c91d  xor     edx, edx; dwFlags
0x18001c91f  call    WINRT_IMPL_HeapFree
0x18001c924  jmp     short loc_18001C931
0x18001c926  test    eax, eax
0x18001c928  jns     short loc_18001C931
0x18001c92a  call    cs:__imp_abort
0x18001c931  jmp     short loc_18001C942
0x18001c933  mov     edi, 0FFFFFFFFh
0x18001c938  mov     r14, [rsp+108h+var_C0]
0x18001c93d  mov     rbx, [rsp+108h+var_D0]
0x18001c942  lea     rcx, [rbx+0B0h]
0x18001c949  lea     rax, [rbx-70h]
0x18001c94d  mov     [rcx], rax
0x18001c950  xor     eax, eax
0x18001c952  mov     [r14], ax
0x18001c956  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@experimental@std@@@Z; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend(std::experimental::coroutine_handle<void>)
0x18001c95b  test    al, al
0x18001c95d  jz      short loc_18001C966
0x18001c95f  jmp     short loc_18001C9D2
0x18001c961  mov     edi, 0FFFFFFFFh; jumptable 000000018001C809 cases -1,1
0x18001c966  lea     rcx, [rbx-18h]
0x18001c96a  cmp     qword ptr [rcx], 0
0x18001c96e  jz      short loc_18001C975
0x18001c970  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001c975  lea     rcx, [rbx-20h]
0x18001c979  cmp     qword ptr [rcx], 0
0x18001c97d  jz      short loc_18001C984
0x18001c97f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001c984  lea     rcx, [rbx-38h]; void *
0x18001c988  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18001c98d  lea     rcx, [rbx-70h]
0x18001c991  call    ?subtract_final_reference@?$root_implements@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@U134567@UIModelCacheManager2@34567@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::subtract_final_reference(void)
0x18001c996  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, edi; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001c99e  sub     edi, 1
0x18001c9a1  jz      short loc_18001C9AE
0x18001c9a3  test    edi, edi
0x18001c9a5  jns     short loc_18001C9AE
0x18001c9a7  call    cs:__imp_abort
0x18001c9ae  lea     rcx, [r14+0C0h]
0x18001c9b5  call    _winrt__Microsoft__Windows__Private__CacheManagement__implementation__ModelCacheManager__CacheModelWithOfflineDriverAsync____22____parameters_____parameters_
0x18001c9ba  cmp     word ptr [rbx+0Ah], 0
0x18001c9bf  jz      short loc_18001C9D2
0x18001c9c1  mov     edx, 150h; unsigned __int64
0x18001c9c6  lea     rcx, [rbx-70h]; void *
0x18001c9ca  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001c9cf  jmp     short loc_18001C9D2
0x18001c9d1  int     3; Trap to Debugger
0x18001c9d2  mov     rcx, [rsp+108h+var_20]
0x18001c9da  xor     rcx, rsp; StackCookie
0x18001c9dd  call    __security_check_cookie
0x18001c9e2  lea     r11, [rsp+108h+var_18]
0x18001c9ea  mov     rbx, [r11+28h]
0x18001c9ee  mov     rsi, [r11+30h]
0x18001c9f2  mov     rsp, r11
0x18001c9f5  pop     r15
0x18001c9f7  pop     r14
0x18001c9f9  pop     rdi
0x18001c9fa  retn
```
