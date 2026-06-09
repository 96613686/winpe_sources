# winrt::Microsoft::Windows::Workloads::Internal::implementation::CacheManagerInternal::EnsureModelIsCachedAsync$_ResumeCoro$1

- ea: `0x18003b980`
- end: `0x18003beb0`
- name: `winrt::Microsoft::Windows::Workloads::Internal::implementation::CacheManagerInternal::EnsureModelIsCachedAsync$_ResumeCoro$1`
- size: `1328`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002c290`

## callees

- `0x1800040a0`
- `0x180004810`
- `0x180007150`
- `0x18000c530`
- `0x180013b90`
- `0x1800157c0`
- `0x1800182e0`
- `0x18001c360`
- `0x18001d220`
- `0x180030ae5`
- `0x180030aeb`
- `0x1800323c8`
- `0x1800342c4`
- `0x180034ef0`
- `0x18003509c`
- `0x180036f4c`
- `0x18003b980`
- `0x18003bed0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18003bc85`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18003bdb4`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18003be46`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18003bc85`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18003bdb4`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18003be46`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall winrt::Microsoft::Windows::Workloads::Internal::implementation::CacheManagerInternal::EnsureModelIsCachedAsync__ResumeCoro_1(
        __int64 a1)
{
  _WORD *v2; // r13
  struct winrt::impl::hstring_header *v3; // rdx
  void *v4; // rcx
  _QWORD *v5; // rax
  struct winrt::impl::hstring_header *v6; // rbx
  __int64 (__fastcall *v7)(_QWORD, struct winrt::impl::hstring_header *, __int64); // rax
  int v8; // eax
  __int64 v9; // r8
  __int64 v10; // r15
  __int64 v11; // rax
  __int64 v12; // rcx
  void (__fastcall *v13)(_QWORD, __int64 *, __int64); // rax
  __int64 v14; // r15
  __int64 v15; // rbx
  int v16; // eax
  __int64 (__fastcall *v17)(_QWORD); // rax
  int v18; // eax
  int v19; // eax
  HANDLE ProcessHeap; // rax
  _QWORD *v21; // rax
  __int64 v22; // rax
  __int64 v23; // rdx
  int v24; // eax
  volatile signed __int32 *v25; // rax
  int v26; // ecx
  volatile signed __int32 *v27; // rbx
  HANDLE v28; // rax
  _BYTE pExceptionObject[24]; // [rsp+58h] [rbp-F0h] BYREF
  __int128 v30; // [rsp+70h] [rbp-D8h]
  LPVOID v31; // [rsp+A0h] [rbp-A8h]
  _QWORD *v32; // [rsp+A8h] [rbp-A0h]
  __int64 v33; // [rsp+B0h] [rbp-98h]
  void (__fastcall ***v35)(_QWORD, __int64 *, __int64); // [rsp+C0h] [rbp-88h]
  struct winrt::impl::hstring_header *v36; // [rsp+C8h] [rbp-80h]

  v2 = (_WORD *)(a1 + 8);
  v3 = (struct winrt::impl::hstring_header *)0x180000000LL;
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
    case 5:
      goto LABEL_52;
    case 2:
      *(_BYTE *)(a1 + 12) = 0;
      if ( *(_DWORD *)(a1 - 16) == 2 )
      {
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)pExceptionObject);
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *v2 = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(a1, a1);
      break;
    case 4:
      v4 = qword_180059D50;
      v5 = (_QWORD *)*((_QWORD *)qword_180059D50 + 1);
      if ( !*((_BYTE *)v5 + 25) )
      {
        v3 = (struct winrt::impl::hstring_header *)*(unsigned int *)(a1 + 212);
        do
        {
          if ( *((_DWORD *)v5 + 8) >= (int)v3 )
            v4 = v5;
          else
            v5 += 2;
          v5 = (_QWORD *)*v5;
        }
        while ( !*((_BYTE *)v5 + 25) );
      }
      if ( *((_BYTE *)v4 + 25) || *(_DWORD *)(a1 + 212) < *((_DWORD *)v4 + 8) )
        std::_Xout_of_range("invalid map<K, T> key");
      v6 = winrt::impl::duplicate_hstring(*((winrt::impl **)v4 + 5), v3);
      *(_QWORD *)(a1 + 16) = v6;
      winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::GetDefault(a1 + 24);
      *(_QWORD *)(a1 + 152) = 0;
      v7 = *(__int64 (__fastcall **)(_QWORD, struct winrt::impl::hstring_header *, __int64))(**(_QWORD **)(a1 + 24)
                                                                                           + 64LL);
      v36 = v6;
      v8 = v7(*(_QWORD *)(a1 + 24), v6, a1 + 152);
      if ( v8 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v8);
      }
      *(_QWORD *)(a1 + 32) = *(_QWORD *)(a1 + 152);
      if ( *(_QWORD *)(a1 + 24) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 24);
      v10 = *(_QWORD *)(a1 + 152) - 16LL;
      if ( !*(_QWORD *)(a1 + 152) )
        v10 = 0;
      *(_OWORD *)(a1 + 40) = 0;
      v30 = 0;
      *(_OWORD *)(a1 + 128) = 0;
      LOBYTE(v9) = 1;
      winrt::Microsoft::Windows::Workloads::implementation::ApiInfo::ActivateSession(v10, a1 + 56, v9);
      if ( *(_QWORD *)(a1 + 56) )
      {
        *(_QWORD *)(a1 + 160) = 0;
        v35 = *(void (__fastcall ****)(_QWORD, __int64 *, __int64))(a1 + 56);
        v13 = **v35;
        v35 = *(void (__fastcall ****)(_QWORD, __int64 *, __int64))(a1 + 56);
        v13(v35, winrt::impl::guid_v<winrt::Microsoft::Windows::PrivateCommon::IModelManager2>, a1 + 160);
        v12 = *(_QWORD *)(a1 + 160);
        v11 = v12;
        v33 = v12;
      }
      else
      {
        v11 = 0;
        v12 = 0;
      }
      *(_QWORD *)(a1 + 64) = v12;
      if ( v11 )
      {
        v14 = *(_QWORD *)(v10 + 120);
        *(_QWORD *)(a1 + 72) = v14;
        if ( v14 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
        v15 = a1 + 176;
        *(_QWORD *)(a1 + 176) = 0;
        v16 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 64LL))(v14, a1 + 176);
        if ( v16 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v16);
        }
        *(_QWORD *)(a1 + 80) = *(_QWORD *)v15;
        v17 = *(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 64) + 48LL);
        v31 = *(LPVOID *)v15;
        v18 = v17(*(_QWORD *)(a1 + 64));
        if ( v18 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v18);
        }
        if ( *(_QWORD *)v15 )
        {
          v19 = _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)v15 + 24LL));
          if ( v19 )
          {
            if ( v19 < 0 )
              abort();
          }
          else
          {
            v31 = *(LPVOID *)v15;
            ProcessHeap = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(ProcessHeap, 0, v31);
          }
        }
        if ( v14 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 72);
        *(_QWORD *)(a1 + 88) = 0;
        *(_QWORD *)(a1 + 200) = 0;
        (***(void (__fastcall ****)(_QWORD, __int64 *, __int64))(a1 + 64))(
          *(_QWORD *)(a1 + 64),
          winrt::impl::guid_v<winrt::Microsoft::Windows::PrivateCommon::IModelManager>,
          a1 + 200);
        v21 = *(_QWORD **)(a1 + 200);
        *(_QWORD *)(a1 + 192) = v21;
        v32 = v21;
        v22 = *v21;
        v23 = *(_QWORD *)(a1 + 88);
        v32 = *(_QWORD **)(a1 + 200);
        v24 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(v22 + 56))(v32, v23);
        if ( v24 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v24);
        }
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 192);
        v11 = *(_QWORD *)(a1 + 64);
      }
      if ( v11 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 64);
      v35 = *(void (__fastcall ****)(_QWORD, __int64 *, __int64))(a1 + 56);
      if ( v35 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 56);
      if ( *(_QWORD *)(a1 + 152) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 32);
      if ( *(_QWORD *)(a1 + 16) )
      {
        v25 = *(volatile signed __int32 **)(a1 + 16);
        v26 = _InterlockedDecrement(v25 + 6);
        if ( v26 )
        {
          if ( v26 < 0 )
            abort();
        }
        else
        {
          v27 = v25;
          v36 = (struct winrt::impl::hstring_header *)v25;
          v28 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v28, 0, (LPVOID)v27);
        }
      }
      *(_QWORD *)(a1 + 120) = a1 - 112;
      *v2 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::Workload *>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::final_suspend_awaiter::await_suspend(a1 + 120) )
      {
LABEL_52:
        if ( *(_QWORD *)(a1 - 24) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 - 24);
        if ( *(_QWORD *)(a1 - 32) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 - 32);
        __ExceptionPtrDestroy((void *)(a1 - 56));
        winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::Workload *>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Windows::Foundation::IAsyncInfo>::subtract_final_reference(a1 - 112);
        if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
          abort();
        if ( *(_WORD *)(a1 + 10) )
          operator delete((void *)(a1 - 112));
      }
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x18003b980  mov     r11, rsp
0x18003b983  mov     [r11+10h], rbx
0x18003b987  mov     [r11+18h], rsi
0x18003b98b  mov     [r11+8], rcx
0x18003b98f  push    rdi
0x18003b990  push    r12
0x18003b992  push    r13
0x18003b994  push    r14
0x18003b996  push    r15
0x18003b998  sub     rsp, 120h
0x18003b99f  mov     rax, cs:__security_cookie
0x18003b9a6  xor     rax, rsp
0x18003b9a9  mov     [rsp+148h+var_38], rax
0x18003b9b1  mov     rdi, rcx
0x18003b9b4  mov     [rsp+148h+var_100], rcx
0x18003b9b9  lea     r13, [rdi+8]
0x18003b9bd  mov     [rsp+148h+var_F8], r13
0x18003b9c2  movzx   eax, word ptr [r13+0]
0x18003b9c7  mov     [rsp+148h+var_110], ax
0x18003b9cc  inc     ax; switch 7 cases
0x18003b9cf  cmp     ax, 6
0x18003b9d3  ja      def_18003B9EE; jumptable 000000018003B9EE default case, case 0
0x18003b9d9  movsx   rax, ax
0x18003b9dd  lea     rdx, cs:180000000h
0x18003b9e4  mov     ecx, ds:(jpt_18003B9EE - 180000000h)[rdx+rax*4]
0x18003b9eb  add     rcx, rdx
0x18003b9ee  jmp     rcx; switch jump
0x18003b9f0  mov     esi, 0FFFFFFFFh; jumptable 000000018003B9EE case 3
0x18003b9f5  jmp     loc_18003BE05
0x18003b9fa  mov     byte ptr [rdi+0Ch], 0; jumptable 000000018003B9EE case 2
0x18003b9fe  mov     eax, [rdi-10h]
0x18003ba01  cmp     eax, 2
0x18003ba04  jnz     short loc_18003BA21
0x18003ba06  lea     rcx, [rsp+148h+pExceptionObject]; this
0x18003ba0b  call    ??0hresult_canceled@winrt@@QEAA@XZ; winrt::hresult_canceled::hresult_canceled(void)
0x18003ba10  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18003ba17  lea     rcx, [rsp+148h+pExceptionObject]; pExceptionObject
0x18003ba1c  call    _CxxThrowException
0x18003ba21  mov     eax, 4
0x18003ba26  mov     [r13+0], ax
0x18003ba2b  mov     rdx, rdi
0x18003ba2e  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@experimental@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::experimental::coroutine_handle<void>)
0x18003ba33  jmp     loc_18003BE65
0x18003ba38  mov     esi, 0FFFFFFFFh; jumptable 000000018003B9EE case 5
0x18003ba3d  jmp     loc_18003BE05
0x18003ba42  mov     rcx, cs:qword_180059D50; jumptable 000000018003B9EE case 4
0x18003ba49  mov     rax, [rcx+8]
0x18003ba4d  cmp     byte ptr [rax+19h], 0
0x18003ba51  jnz     short loc_18003BA77
0x18003ba53  mov     edx, [rdi+0D4h]; struct winrt::impl::hstring_header *
0x18003ba59  nop     dword ptr [rax+00000000h]
0x18003ba60  cmp     [rax+20h], edx
0x18003ba63  jge     short loc_18003BA6B
0x18003ba65  add     rax, 10h
0x18003ba69  jmp     short loc_18003BA6E
0x18003ba6b  mov     rcx, rax
0x18003ba6e  mov     rax, [rax]
0x18003ba71  cmp     byte ptr [rax+19h], 0
0x18003ba75  jz      short loc_18003BA60
0x18003ba77  cmp     byte ptr [rcx+19h], 0
0x18003ba7b  jnz     loc_18003BDBD
0x18003ba81  mov     eax, [rcx+20h]
0x18003ba84  cmp     [rdi+0D4h], eax
0x18003ba8a  jl      loc_18003BDBD
0x18003ba90  mov     rcx, [rcx+28h]; this
0x18003ba94  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x18003ba99  mov     rbx, rax
0x18003ba9c  mov     [rdi+10h], rax
0x18003baa0  lea     rcx, [rdi+18h]
0x18003baa4  call    ?GetDefault@WorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@SA?AU13456@XZ; winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::GetDefault(void)
0x18003baa9  nop
0x18003baaa  xor     r14d, r14d
0x18003baad  mov     [rdi+98h], r14
0x18003bab4  mov     rax, [rdi+18h]
0x18003bab8  mov     [rsp+148h+var_108], rax
0x18003babd  mov     rcx, [rax]
0x18003bac0  mov     rax, [rcx+40h]
0x18003bac4  mov     [rsp+148h+var_80], rbx
0x18003bacc  mov     rcx, [rdi+18h]
0x18003bad0  mov     [rsp+148h+var_108], rcx
0x18003bad5  lea     r8, [rdi+98h]
0x18003badc  mov     rdx, rbx
0x18003badf  call    cs:__guard_dispatch_icall_fptr
0x18003bae5  test    eax, eax
0x18003bae7  jns     short loc_18003BAF3
0x18003bae9  lfence
0x18003baec  mov     ecx, eax
0x18003baee  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x18003baf3  mov     rax, [rdi+98h]
0x18003bafa  mov     [rdi+20h], rax
0x18003bafe  mov     rax, [rdi+18h]
0x18003bb02  mov     [rsp+148h+var_108], rax
0x18003bb07  test    rax, rax
0x18003bb0a  jz      short loc_18003BB15
0x18003bb0c  lea     rcx, [rdi+18h]
0x18003bb10  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003bb15  mov     r15, [rdi+98h]
0x18003bb1c  sub     r15, 10h
0x18003bb20  cmp     qword ptr [rdi+98h], 0
0x18003bb28  cmovz   r15, r14
0x18003bb2c  xorps   xmm0, xmm0
0x18003bb2f  lea     r9, [rdi+80h]
0x18003bb36  movups  xmmword ptr [rdi+28h], xmm0
0x18003bb3a  movups  [rsp+148h+var_D8], xmm0
0x18003bb3f  movaps  xmmword ptr [r9], xmm0
0x18003bb43  mov     [rsp+148h+var_128], 0
0x18003bb48  mov     r8b, 1
0x18003bb4b  lea     rdx, [rdi+38h]
0x18003bb4f  mov     rcx, r15
0x18003bb52  call    ?ActivateSession@ApiInfo@implementation@Workloads@Windows@Microsoft@winrt@@QEAA?AUIInspectable@Foundation@46@_NUguid@6@0@Z; winrt::Microsoft::Windows::Workloads::implementation::ApiInfo::ActivateSession(bool,winrt::guid,bool)
0x18003bb57  nop
0x18003bb58  cmp     qword ptr [rdi+38h], 0
0x18003bb5d  jnz     short loc_18003BB67
0x18003bb5f  mov     rax, r14
0x18003bb62  mov     rcx, r14
0x18003bb65  jmp     short loc_18003BBB2
0x18003bb67  mov     [rdi+0A0h], r14
0x18003bb6e  mov     rax, [rdi+38h]
0x18003bb72  mov     [rsp+148h+var_88], rax
0x18003bb7a  mov     rcx, [rax]
0x18003bb7d  mov     rax, [rcx]
0x18003bb80  mov     rcx, [rdi+38h]
0x18003bb84  mov     [rsp+148h+var_88], rcx
0x18003bb8c  lea     r8, [rdi+0A0h]
0x18003bb93  lea     rdx, ??$guid_v@UIModelManager2@PrivateCommon@Windows@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Windows::PrivateCommon::IModelManager2>
0x18003bb9a  call    cs:__guard_dispatch_icall_fptr
0x18003bba0  mov     rcx, [rdi+0A0h]
0x18003bba7  mov     rax, rcx
0x18003bbaa  mov     [rsp+148h+var_98], rcx
0x18003bbb2  mov     [rdi+40h], rcx
0x18003bbb6  test    rax, rax
0x18003bbb9  jz      loc_18003BD2D
0x18003bbbf  mov     r15, [r15+78h]
0x18003bbc3  mov     [rdi+48h], r15
0x18003bbc7  test    r15, r15
0x18003bbca  jz      short loc_18003BBDD
0x18003bbcc  mov     rax, [r15]
0x18003bbcf  mov     rcx, r15
0x18003bbd2  mov     rax, [rax+8]
0x18003bbd6  call    cs:__guard_dispatch_icall_fptr
0x18003bbdc  nop
0x18003bbdd  lea     rbx, [rdi+0B0h]
0x18003bbe4  mov     [rbx], r14
0x18003bbe7  mov     rax, [r15]
0x18003bbea  mov     rdx, rbx
0x18003bbed  mov     rcx, r15
0x18003bbf0  mov     rax, [rax+40h]
0x18003bbf4  call    cs:__guard_dispatch_icall_fptr
0x18003bbfa  test    eax, eax
0x18003bbfc  jns     short loc_18003BC08
0x18003bbfe  lfence
0x18003bc01  mov     ecx, eax
0x18003bc03  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x18003bc08  mov     rax, [rbx]
0x18003bc0b  mov     [rdi+50h], rax
0x18003bc0f  mov     rax, [rdi+40h]
0x18003bc13  mov     [rsp+148h+var_118], rax
0x18003bc18  mov     rcx, [rax]
0x18003bc1b  mov     rax, [rcx+30h]
0x18003bc1f  mov     rdx, [rbx]
0x18003bc22  mov     [rsp+148h+var_A8], rdx
0x18003bc2a  mov     rcx, [rdi+40h]
0x18003bc2e  mov     [rsp+148h+var_118], rcx
0x18003bc33  call    cs:__guard_dispatch_icall_fptr
0x18003bc39  test    eax, eax
0x18003bc3b  jns     short loc_18003BC48
0x18003bc3d  lfence
0x18003bc40  mov     ecx, eax
0x18003bc42  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x18003bc48  mov     esi, 0FFFFFFFFh
0x18003bc4d  cmp     qword ptr [rbx], 0
0x18003bc51  jz      short loc_18003BC8C
0x18003bc53  mov     rcx, [rbx]
0x18003bc56  mov     eax, esi
0x18003bc58  lock xadd [rcx+18h], eax
0x18003bc5d  sub     eax, 1
0x18003bc60  jnz     short loc_18003BC81
0x18003bc62  mov     rbx, [rbx]
0x18003bc65  mov     [rsp+148h+var_A8], rbx
0x18003bc6d  call    WINRT_IMPL_GetProcessHeap
0x18003bc72  mov     rcx, rax; hHeap
0x18003bc75  mov     r8, rbx; lpMem
0x18003bc78  xor     edx, edx; dwFlags
0x18003bc7a  call    WINRT_IMPL_HeapFree
0x18003bc7f  jmp     short loc_18003BC8C
0x18003bc81  test    eax, eax
0x18003bc83  jns     short loc_18003BC8C
0x18003bc85  call    cs:__imp_abort
0x18003bc8c  test    r15, r15
0x18003bc8f  jz      short loc_18003BC9A
0x18003bc91  lea     rcx, [rdi+48h]
0x18003bc95  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003bc9a  mov     [rdi+58h], r14
0x18003bc9e  mov     [rdi+0C8h], r14
0x18003bca5  mov     rax, [rdi+40h]
0x18003bca9  mov     [rsp+148h+var_118], rax
0x18003bcae  mov     rcx, [rax]
0x18003bcb1  mov     rax, [rcx]
0x18003bcb4  mov     rcx, [rdi+40h]
0x18003bcb8  mov     [rsp+148h+var_118], rcx
0x18003bcbd  lea     r8, [rdi+0C8h]
0x18003bcc4  lea     rdx, ??$guid_v@UIModelManager@PrivateCommon@Windows@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Windows::PrivateCommon::IModelManager>
0x18003bccb  call    cs:__guard_dispatch_icall_fptr
0x18003bcd1  mov     rax, [rdi+0C8h]
0x18003bcd8  mov     [rdi+0C0h], rax
0x18003bcdf  mov     [rsp+148h+var_A0], rax
0x18003bce7  mov     rax, [rax]
0x18003bcea  mov     rdx, [rdi+58h]
0x18003bcee  mov     rcx, [rdi+0C8h]
0x18003bcf5  mov     [rsp+148h+var_A0], rcx
0x18003bcfd  mov     rax, [rax+38h]
0x18003bd01  call    cs:__guard_dispatch_icall_fptr
0x18003bd07  test    eax, eax
0x18003bd09  jns     short loc_18003BD16
0x18003bd0b  lfence
0x18003bd0e  mov     ecx, eax
0x18003bd10  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x18003bd16  lea     rcx, [rdi+0C0h]
0x18003bd1d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003bd22  mov     rax, [rdi+40h]
0x18003bd26  mov     [rsp+148h+var_118], rax
0x18003bd2b  jmp     short loc_18003BD32
0x18003bd2d  mov     esi, 0FFFFFFFFh
0x18003bd32  test    rax, rax
0x18003bd35  jz      short loc_18003BD41
0x18003bd37  lea     rcx, [rdi+40h]
0x18003bd3b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003bd40  nop
0x18003bd41  mov     rax, [rdi+38h]
0x18003bd45  mov     [rsp+148h+var_88], rax
0x18003bd4d  test    rax, rax
0x18003bd50  jz      short loc_18003BD5C
0x18003bd52  lea     rcx, [rdi+38h]
0x18003bd56  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003bd5b  nop
0x18003bd5c  mov     rax, [rdi+98h]
0x18003bd63  mov     [rsp+148h+var_90], rax
0x18003bd6b  test    rax, rax
0x18003bd6e  jz      short loc_18003BD7A
0x18003bd70  lea     rcx, [rdi+20h]
0x18003bd74  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003bd79  nop
0x18003bd7a  cmp     qword ptr [rdi+10h], 0
0x18003bd7f  jz      short loc_18003BDBB
0x18003bd81  mov     rax, [rdi+10h]
0x18003bd85  mov     ecx, esi
0x18003bd87  lock xadd [rax+18h], ecx
0x18003bd8c  sub     ecx, 1
0x18003bd8f  jnz     short loc_18003BDB0
0x18003bd91  mov     rbx, rax
0x18003bd94  mov     [rsp+148h+var_80], rax
0x18003bd9c  call    WINRT_IMPL_GetProcessHeap
0x18003bda1  mov     rcx, rax; hHeap
0x18003bda4  mov     r8, rbx; lpMem
0x18003bda7  xor     edx, edx; dwFlags
0x18003bda9  call    WINRT_IMPL_HeapFree
0x18003bdae  jmp     short loc_18003BDBB
0x18003bdb0  test    ecx, ecx
0x18003bdb2  jns     short loc_18003BDBB
0x18003bdb4  call    cs:__imp_abort
0x18003bdbb  jmp     short loc_18003BDD9
0x18003bdbd  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x18003bdc4  call    ?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18003bdca  mov     esi, 0FFFFFFFFh
0x18003bdcf  mov     rdi, [rsp+148h+var_100]
0x18003bdd4  mov     r13, [rsp+148h+var_F8]
0x18003bdd9  lea     rcx, [rdi+78h]
0x18003bddd  lea     rax, [rdi-70h]
0x18003bde1  mov     [rcx], rax
0x18003bde4  xor     eax, eax
0x18003bde6  mov     [r13+0], ax
0x18003bdeb  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@PEAUWorkload@implementation@Workloads@3Microsoft@4@@experimental@std@@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@UPackageDeploymentProgress@Deployment@Management@7Microsoft@8@@impl@winrt@@QEBA_NU?$coroutine_handle@X@experimental@std@@@Z; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::Workload *>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::final_suspend_awaiter::await_suspend(std::experimental::coroutine_handle<void>)
0x18003bdf0  test    al, al
0x18003bdf2  jz      short loc_18003BE05
0x18003bdf4  jmp     short loc_18003BE65
0x18003be00  mov     esi, 0FFFFFFFFh; jumptable 000000018003B9EE cases -1,1
0x18003be05  lea     rcx, [rdi-18h]
0x18003be09  cmp     qword ptr [rcx], 0
0x18003be0d  jz      short loc_18003BE14
0x18003be0f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003be14  lea     rcx, [rdi-20h]
0x18003be18  cmp     qword ptr [rcx], 0
0x18003be1c  jz      short loc_18003BE23
0x18003be1e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003be23  lea     rcx, [rdi-38h]; void *
0x18003be27  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18003be2c  lea     rcx, [rdi-70h]
0x18003be30  call    ?subtract_final_reference@?$root_implements@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@PEAUWorkload@implementation@Workloads@3Microsoft@4@@experimental@std@@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@UIAsyncInfo@678@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::Workload *>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Windows::Foundation::IAsyncInfo>::subtract_final_reference(void)
0x18003be35  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, esi; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18003be3d  sub     esi, 1
0x18003be40  jz      short loc_18003BE4D
0x18003be42  test    esi, esi
0x18003be44  jns     short loc_18003BE4D
0x18003be46  call    cs:__imp_abort
0x18003be4d  cmp     word ptr [rdi+0Ah], 0
0x18003be52  jz      short loc_18003BE65
0x18003be54  mov     edx, 150h; unsigned __int64
0x18003be59  lea     rcx, [rdi-70h]; void *
0x18003be5d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003be62  jmp     short loc_18003BE65
  ... truncated ...
```
