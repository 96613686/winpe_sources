# winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Workloads::Internal::ModelKind>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::Completed(winrt::Windows::Foundation::AsyncActionCompletedHandler const &)

- ea: `0x18002c9c0`
- end: `0x18002cbc7`
- name: `?Completed@?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@W4ModelKind@Internal@Workloads@3Microsoft@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@QEAAXAEBUAsyncActionCompletedHandler@Foundation@Windows@3@@Z`
- size: `519`
- prototype: `void __fastcall(__int64, char **)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002c6f0`

## callees

- `0x1800040a0`
- `0x1800196b0`
- `0x18001af50`
- `0x18002c9c0`
- `0x180030af1`
- `0x180030af7`
- `0x180034ef0`
- `0x180035060`
- `0x180036f4c`
- `0x1800398b1`
- `0x18003bed0`

## pseudocode

```c
void __fastcall winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,enum winrt::Microsoft::Windows::Workloads::Internal::ModelKind>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::Completed(
        __int64 a1,
        char **a2)
{
  RTL_SRWLOCK *v4; // rdi
  char *v5; // rcx
  bool v6; // r14
  char *v7; // rbx
  char *v8; // r14
  __int64 v9; // r15
  char **v10; // rsi
  char *v11; // [rsp+20h] [rbp-39h] BYREF
  char *v12; // [rsp+28h] [rbp-31h]
  _OWORD pExceptionObject[3]; // [rsp+30h] [rbp-29h] BYREF
  __int64 v14; // [rsp+60h] [rbp+7h] BYREF
  __int64 v15; // [rsp+68h] [rbp+Fh] BYREF
  __int128 v16; // [rsp+70h] [rbp+17h] BYREF

  v4 = (RTL_SRWLOCK *)(a1 + 72);
  v12 = (char *)(a1 + 72);
  WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)(a1 + 72));
  if ( *(_BYTE *)(a1 + 100) )
  {
    winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment((winrt::hresult_illegal_delegate_assignment *)pExceptionObject);
    throw (winrt::hresult_illegal_delegate_assignment *)pExceptionObject;
  }
  *(_BYTE *)(a1 + 100) = 1;
  LODWORD(v15) = *(_DWORD *)(a1 + 96);
  if ( !(_DWORD)v15 )
  {
    v5 = *a2;
    if ( *a2 )
    {
      v14 = 0;
      (**(void (__fastcall ***)(char *, __int64 *, __int64 *))v5)(
        v5,
        &winrt::impl::guid_v<winrt::impl::IAgileObject>,
        &v14);
      v6 = v14 != 0;
      if ( v14 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v14);
      if ( v6 )
      {
        v7 = *a2;
        v11 = v7;
        if ( v7 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))(v7);
        v8 = v7;
        goto LABEL_16;
      }
    }
    v16 = winrt::impl::guid_v<winrt::Windows::Foundation::AsyncActionCompletedHandler>;
    v15 = 0;
    WINRT_IMPL_RoGetAgileReference(0, &v16, *a2, &v15);
    v9 = v15;
    if ( v15 )
    {
      v15 = 0;
      pExceptionObject[0] = v16;
      v7 = (char *)operator new(0x28u);
      v12 = v7;
      v8 = v7;
      *((_DWORD *)v7 + 2) = 1;
      *((_QWORD *)v7 + 2) = v9;
      *(_OWORD *)(v7 + 24) = pExceptionObject[0];
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      *(_QWORD *)v7 = &winrt::impl::delegate<winrt::Windows::Foundation::AsyncActionCompletedHandler,_lambda_dc4921c5914f1dac0ac69065375e73ef_>::`vftable';
      v11 = v7;
    }
    else
    {
      v7 = *a2;
      v11 = v7;
      v8 = v7;
      if ( !v7 )
      {
LABEL_16:
        v10 = (char **)(a1 + 80);
        if ( v10 == &v11 )
        {
          if ( v8 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v11);
        }
        else
        {
          if ( *v10 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v10);
          *v10 = v7;
        }
        ReleaseSRWLockExclusive_0(v4);
        return;
      }
      (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))(v7);
    }
    if ( v15 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v15);
    goto LABEL_16;
  }
  ReleaseSRWLockExclusive_0(v4);
  if ( *a2 )
    winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationWithProgressCompletedHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::Workload *>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,enum winrt::Windows::Foundation::AsyncStatus>(
      a2,
      a1,
      (unsigned int *)&v15);
}

```

## disassembly

```asm
0x18002c9c0  mov     [rsp-8+arg_10], rbx
0x18002c9c5  mov     [rsp-8+arg_18], rsi
0x18002c9ca  push    rbp
0x18002c9cb  push    rdi
0x18002c9cc  push    r12
0x18002c9ce  push    r14
0x18002c9d0  push    r15
0x18002c9d2  lea     rbp, [rsp-37h]
0x18002c9d7  sub     rsp, 90h
0x18002c9de  mov     rax, cs:__security_cookie
0x18002c9e5  xor     rax, rsp
0x18002c9e8  mov     [rbp+57h+var_30], rax
0x18002c9ec  mov     rbx, rdx
0x18002c9ef  mov     rsi, rcx
0x18002c9f2  xor     r12d, r12d
0x18002c9f5  lea     rdi, [rcx+48h]
0x18002c9f9  mov     [rbp+57h+var_88], rdi
0x18002c9fd  mov     rcx, rdi; SRWLock
0x18002ca00  call    WINRT_IMPL_AcquireSRWLockExclusive
0x18002ca05  nop
0x18002ca06  cmp     [rsi+64h], r12b
0x18002ca0a  jnz     loc_18002CBAD
0x18002ca10  mov     byte ptr [rsi+64h], 1
0x18002ca14  mov     eax, [rsi+60h]
0x18002ca17  mov     dword ptr [rbp+57h+var_48], eax
0x18002ca1a  test    eax, eax
0x18002ca1c  jnz     loc_18002CB68
0x18002ca22  mov     rcx, [rbx]
0x18002ca25  test    rcx, rcx
0x18002ca28  jz      short loc_18002CA8B
0x18002ca2a  mov     [rbp+57h+var_50], r12
0x18002ca2e  mov     rax, [rcx]
0x18002ca31  lea     r8, [rbp+57h+var_50]
0x18002ca35  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18002ca3c  mov     rax, [rax]
0x18002ca3f  call    cs:__guard_dispatch_icall_fptr
0x18002ca45  mov     rax, [rbp+57h+var_50]
0x18002ca49  mov     [rbp+57h+var_50], rax
0x18002ca4d  test    rax, rax
0x18002ca50  setnz   r14b
0x18002ca54  test    rax, rax
0x18002ca57  jz      short loc_18002CA62
0x18002ca59  lea     rcx, [rbp+57h+var_50]
0x18002ca5d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002ca62  test    r14b, r14b
0x18002ca65  jz      short loc_18002CA8B
0x18002ca67  mov     rbx, [rbx]
0x18002ca6a  mov     [rbp+57h+var_90], rbx
0x18002ca6e  test    rbx, rbx
0x18002ca71  jz      short loc_18002CA83
0x18002ca73  mov     rax, [rbx]
0x18002ca76  mov     rcx, rbx
0x18002ca79  mov     rax, [rax+8]
0x18002ca7d  call    cs:__guard_dispatch_icall_fptr
0x18002ca83  mov     r14, rbx
0x18002ca86  jmp     loc_18002CB2F
0x18002ca8b  movups  xmm0, cs:??$guid_v@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::AsyncActionCompletedHandler>
0x18002ca92  movups  [rbp+57h+var_40], xmm0
0x18002ca96  mov     [rbp+57h+var_48], r12
0x18002ca9a  lea     r9, [rbp+57h+var_48]
0x18002ca9e  mov     r8, [rbx]
0x18002caa1  lea     rdx, [rbp+57h+var_40]
0x18002caa5  xor     ecx, ecx
0x18002caa7  call    WINRT_IMPL_RoGetAgileReference
0x18002caac  mov     r15, [rbp+57h+var_48]
0x18002cab0  test    r15, r15
0x18002cab3  jz      short loc_18002CAFF
0x18002cab5  mov     [rbp+57h+var_48], r12
0x18002cab9  movups  xmm0, [rbp+57h+var_40]
0x18002cabd  movups  [rbp+57h+pExceptionObject], xmm0
0x18002cac1  mov     ecx, 28h ; '('; Size
0x18002cac6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002cacb  mov     rbx, rax
0x18002cace  mov     [rbp+57h+var_88], rax
0x18002cad2  mov     r14, rax
0x18002cad5  mov     dword ptr [rax+8], 1
0x18002cadc  mov     [rax+10h], r15
0x18002cae0  movups  xmm0, [rbp+57h+pExceptionObject]
0x18002cae4  movups  xmmword ptr [rax+18h], xmm0
0x18002cae8  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18002caef  lea     rax, ??_7?$delegate@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@V_lambda_dc4921c5914f1dac0ac69065375e73ef_@@@impl@winrt@@6B@; const winrt::impl::delegate<winrt::Windows::Foundation::AsyncActionCompletedHandler,_lambda_dc4921c5914f1dac0ac69065375e73ef_>::`vftable'
0x18002caf6  mov     [rbx], rax
0x18002caf9  mov     [rbp+57h+var_90], rbx
0x18002cafd  jmp     short loc_18002CB1E
0x18002caff  mov     rbx, [rbx]
0x18002cb02  mov     [rbp+57h+var_90], rbx
0x18002cb06  mov     r14, rbx
0x18002cb09  test    rbx, rbx
0x18002cb0c  jz      short loc_18002CB2F
0x18002cb0e  mov     rax, [rbx]
0x18002cb11  mov     rcx, rbx
0x18002cb14  mov     rax, [rax+8]
0x18002cb18  call    cs:__guard_dispatch_icall_fptr
0x18002cb1e  cmp     [rbp+57h+var_48], 0
0x18002cb23  jz      short loc_18002CB2F
0x18002cb25  lea     rcx, [rbp+57h+var_48]
0x18002cb29  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002cb2e  nop
0x18002cb2f  add     rsi, 50h ; 'P'
0x18002cb33  lea     rax, [rbp+57h+var_90]
0x18002cb37  cmp     rsi, rax
0x18002cb3a  jz      short loc_18002CB4F
0x18002cb3c  cmp     qword ptr [rsi], 0
0x18002cb40  jz      short loc_18002CB4A
0x18002cb42  mov     rcx, rsi
0x18002cb45  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002cb4a  mov     [rsi], rbx
0x18002cb4d  jmp     short loc_18002CB5E
0x18002cb4f  test    r14, r14
0x18002cb52  jz      short loc_18002CB5E
0x18002cb54  lea     rcx, [rbp+57h+var_90]
0x18002cb58  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002cb5d  nop
0x18002cb5e  mov     rcx, rdi; SRWLock
0x18002cb61  call    ReleaseSRWLockExclusive_0
0x18002cb66  jmp     short loc_18002CB85
0x18002cb68  mov     rcx, rdi; SRWLock
0x18002cb6b  call    ReleaseSRWLockExclusive_0
0x18002cb70  cmp     qword ptr [rbx], 0
0x18002cb74  jz      short loc_18002CB85
0x18002cb76  lea     r8, [rbp+57h+var_48]
0x18002cb7a  mov     rdx, rsi
0x18002cb7d  mov     rcx, rbx
0x18002cb80  call    ??$invoke@U?$AsyncOperationWithProgressCompletedHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@U?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@PEAUWorkload@implementation@Workloads@3Microsoft@4@@experimental@std@@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@UPackageDeploymentProgress@Deployment@Management@7Microsoft@8@@impl@4@W4AsyncStatus@234@@impl@winrt@@YA_NAEBU?$AsyncOperationWithProgressCompletedHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@1@AEBU?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@PEAUWorkload@implementation@Workloads@3Microsoft@4@@experimental@std@@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@UPackageDeploymentProgress@Deployment@Management@7Microsoft@8@@01@AEBW4AsyncStatus@341@@Z; winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationWithProgressCompletedHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::Workload *>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Windows::Foundation::AsyncStatus>(winrt::Windows::Foundation::AsyncOperationWithProgressCompletedHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress> const &,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::Workload *>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress> const &,winrt::Windows::Foundation::AsyncStatus const &)
0x18002cb85  mov     rcx, [rbp+57h+var_30]
0x18002cb89  xor     rcx, rsp; StackCookie
0x18002cb8c  call    __security_check_cookie
0x18002cb91  lea     r11, [rsp+0B0h+var_20]
0x18002cb99  mov     rbx, [r11+40h]
0x18002cb9d  mov     rsi, [r11+48h]
0x18002cba1  mov     rsp, r11
0x18002cba4  pop     r15
0x18002cba6  pop     r14
0x18002cba8  pop     r12
0x18002cbaa  pop     rdi
0x18002cbab  pop     rbp
0x18002cbac  retn
0x18002cbad  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18002cbb1  call    ??0hresult_illegal_delegate_assignment@winrt@@QEAA@XZ; winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(void)
0x18002cbb6  lea     rdx, _TI2?AUhresult_illegal_delegate_assignment@winrt@@; pThrowInfo
0x18002cbbd  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002cbc1  call    _CxxThrowException
```
