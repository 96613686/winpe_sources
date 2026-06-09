# PolicyEngineController::RunSinglePolicyEvaluation(EvaluationTrigger)

- ea: `0x18001c238`
- end: `0x18001c4b5`
- name: `?RunSinglePolicyEvaluation@PolicyEngineController@@QEAAJW4EvaluationTrigger@@@Z`
- size: `637`
- prototype: `__int64 __fastcall(__int64 **, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c0c0`

## callees

- `0x180003530`
- `0x180005120`
- `0x180008a38`
- `0x18000f454`
- `0x1800113d8`
- `0x180012294`
- `0x180017244`
- `0x18001be34`
- `0x18001c238`
- `0x18001c554`
- `0x18001c60c`
- `0x180026010`

## string_xrefs

- `0x18001c2c2`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\policyenginecontroller.cpp`
- `0x18001c33e`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\policyenginecontroller.cpp`
- `0x18001c409`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\policyenginecontroller.cpp`

## pseudocode

```c
__int64 __fastcall PolicyEngineController::RunSinglePolicyEvaluation(__int64 **a1, unsigned int a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  _QWORD *v7; // rcx
  __int64 *v8; // rdi
  _QWORD *v9; // rdx
  __int64 *v10; // r14
  __int64 v11; // rbx
  int v12; // eax
  unsigned int v13; // ebx
  __int64 *v14; // rdi
  __int64 *v15; // rsi
  __int64 v16; // rbx
  int v17; // eax
  unsigned int v18; // ebx
  int v19; // [rsp+20h] [rbp-1A8h]
  __int64 v20; // [rsp+30h] [rbp-198h] BYREF
  _QWORD *v21; // [rsp+38h] [rbp-190h] BYREF
  _QWORD *v22; // [rsp+40h] [rbp-188h]
  _QWORD v23[42]; // [rsp+50h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v23,
    "SinglePolicyEvaluation");
  v23[0] = &PolicyTelemetry::SinglePolicyEvaluation::`vftable';
  PolicyTelemetry::SinglePolicyEvaluation::StartActivity((PolicyTelemetry::SinglePolicyEvaluation *)v23, a2);
  std::vector<SessionUserInfo>::vector<SessionUserInfo>(&v21);
  v4 = (*(__int64 (__fastcall **)(__int64 *, _QWORD **))(*a1[10] + 32))(a1[10], &v21);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v7 = v21;
    v8 = v21;
    v9 = v22;
    v10 = v22;
    while ( v8 != v10 )
    {
      v20 = *v8;
      v11 = v20;
      Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>::InternalAddRef(&v20);
      v12 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 88LL))(v11, 0);
      v13 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x44,
          (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\policyenginecontroller.cpp",
          (const char *)(unsigned int)v12,
          v19);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
        std::vector<Microsoft::WRL::ComPtr<IUserAccount>>::_Tidy(&v21);
        PolicyTelemetry::SinglePolicyEvaluation::~SinglePolicyEvaluation((PolicyTelemetry::SinglePolicyEvaluation *)v23);
        return v13;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
      ++v8;
      v9 = v22;
      v7 = v21;
    }
    if ( v9 - v7 )
    {
      v14 = a1[7];
      v15 = a1[8];
      while ( v14 != v15 )
      {
        v16 = *v14;
        v20 = v16;
        if ( v16 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
        v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **, __int64))(*(_QWORD *)v16 + 32LL))(
                v16,
                a2,
                &v21,
                v23[34] + 8LL);
        v18 = v17;
        if ( v17 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4C,
            (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\policyenginecontroller.cpp",
            (const char *)(unsigned int)v17,
            v19);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
          std::vector<Microsoft::WRL::ComPtr<IUserAccount>>::_Tidy(&v21);
          PolicyTelemetry::SinglePolicyEvaluation::~SinglePolicyEvaluation((PolicyTelemetry::SinglePolicyEvaluation *)v23);
          return v18;
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
        ++v14;
        v9 = v22;
        v7 = v21;
      }
    }
    PolicyTelemetry::SinglePolicyEvaluation::Stop((PolicyTelemetry::SinglePolicyEvaluation *)v23, v9 - v7);
    std::vector<Microsoft::WRL::ComPtr<IUserAccount>>::_Tidy(&v21);
    PolicyTelemetry::SinglePolicyEvaluation::~SinglePolicyEvaluation((PolicyTelemetry::SinglePolicyEvaluation *)v23);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\policyenginecontroller.cpp",
      (const char *)(unsigned int)v4,
      v19);
    std::vector<Microsoft::WRL::ComPtr<IUserAccount>>::_Tidy(&v21);
    PolicyTelemetry::SinglePolicyEvaluation::~SinglePolicyEvaluation((PolicyTelemetry::SinglePolicyEvaluation *)v23);
    return v5;
  }
}

```

## disassembly

```asm
0x18001c238  mov     [rsp+arg_10], rbx
0x18001c23d  mov     [rsp+arg_18], rsi
0x18001c242  push    rdi
0x18001c243  push    r14
0x18001c245  push    r15
0x18001c247  sub     rsp, 1B0h
0x18001c24e  mov     rax, cs:__security_cookie
0x18001c255  xor     rax, rsp
0x18001c258  mov     [rsp+1C8h+var_28], rax
0x18001c260  mov     r15d, edx
0x18001c263  mov     rsi, rcx
0x18001c266  lea     rdx, aSinglepolicyev; "SinglePolicyEvaluation"
0x18001c26d  lea     rcx, [rsp+1C8h+var_178]
0x18001c272  call    ??0?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001c277  lea     rax, ??_7SinglePolicyEvaluation@PolicyTelemetry@@6B@; const PolicyTelemetry::SinglePolicyEvaluation::`vftable'
0x18001c27e  mov     [rsp+1C8h+var_178], rax
0x18001c283  mov     edx, r15d; unsigned int
0x18001c286  lea     rcx, [rsp+1C8h+var_178]; this
0x18001c28b  call    ?StartActivity@SinglePolicyEvaluation@PolicyTelemetry@@QEAAXI@Z; PolicyTelemetry::SinglePolicyEvaluation::StartActivity(uint)
0x18001c290  nop
0x18001c291  lea     rcx, [rsp+1C8h+var_190]
0x18001c296  call    ??0?$vector@USessionUserInfo@@V?$allocator@USessionUserInfo@@@std@@@std@@QEAA@XZ; std::vector<SessionUserInfo>::vector<SessionUserInfo>(void)
0x18001c29b  nop
0x18001c29c  mov     rcx, [rsi+50h]
0x18001c2a0  mov     rax, [rcx]
0x18001c2a3  lea     rdx, [rsp+1C8h+var_190]
0x18001c2a8  mov     rax, [rax+20h]
0x18001c2ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2b1  mov     ebx, eax
0x18001c2b3  test    eax, eax
0x18001c2b5  jns     short loc_18001C2F0
0x18001c2b7  mov     rcx, [rsp+1C8h]; this
0x18001c2bf  mov     r9d, eax; char *
0x18001c2c2  lea     r8, aShellcommonShe_3; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001c2c9  mov     edx, 41h ; 'A'; void *
0x18001c2ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c2d3  nop
0x18001c2d4  lea     rcx, [rsp+1C8h+var_190]
0x18001c2d9  call    ?_Tidy@?$vector@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@std@@@std@@AEAAXXZ; std::vector<Microsoft::WRL::ComPtr<IUserAccount>>::_Tidy(void)
0x18001c2de  nop
0x18001c2df  lea     rcx, [rsp+1C8h+var_178]; this
0x18001c2e4  call    ??1SinglePolicyEvaluation@PolicyTelemetry@@QEAA@XZ; PolicyTelemetry::SinglePolicyEvaluation::~SinglePolicyEvaluation(void)
0x18001c2e9  mov     eax, ebx
0x18001c2eb  jmp     loc_18001C48B
0x18001c2f0  mov     rcx, [rsp+1C8h+var_190]
0x18001c2f5  mov     rdi, rcx
0x18001c2f8  mov     rdx, [rsp+1C8h+var_188]
0x18001c2fd  mov     r14, rdx
0x18001c300  cmp     rdi, r14
0x18001c303  jz      loc_18001C394
0x18001c309  mov     rbx, [rdi]
0x18001c30c  mov     [rsp+1C8h+var_198], rbx
0x18001c311  lea     rcx, [rsp+1C8h+var_198]
0x18001c316  call    ?InternalAddRef@?$ComPtr@UIUserProfile@Internal@System@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>::InternalAddRef(void)
0x18001c31b  nop
0x18001c31c  mov     rax, [rbx]
0x18001c31f  xor     edx, edx
0x18001c321  mov     rcx, rbx
0x18001c324  mov     rax, [rax+58h]
0x18001c328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c32d  mov     ebx, eax
0x18001c32f  test    eax, eax
0x18001c331  jns     short loc_18001C377
0x18001c333  mov     rcx, [rsp+1C8h]; this
0x18001c33b  mov     r9d, eax; char *
0x18001c33e  lea     r8, aShellcommonShe_3; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001c345  mov     edx, 44h ; 'D'; void *
0x18001c34a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c34f  nop
0x18001c350  lea     rcx, [rsp+1C8h+var_198]
0x18001c355  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c35a  nop
0x18001c35b  lea     rcx, [rsp+1C8h+var_190]
0x18001c360  call    ?_Tidy@?$vector@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@std@@@std@@AEAAXXZ; std::vector<Microsoft::WRL::ComPtr<IUserAccount>>::_Tidy(void)
0x18001c365  nop
0x18001c366  lea     rcx, [rsp+1C8h+var_178]; this
0x18001c36b  call    ??1SinglePolicyEvaluation@PolicyTelemetry@@QEAA@XZ; PolicyTelemetry::SinglePolicyEvaluation::~SinglePolicyEvaluation(void)
0x18001c370  mov     eax, ebx
0x18001c372  jmp     loc_18001C48B
0x18001c377  lea     rcx, [rsp+1C8h+var_198]
0x18001c37c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c381  add     rdi, 8
0x18001c385  mov     rdx, [rsp+1C8h+var_188]
0x18001c38a  mov     rcx, [rsp+1C8h+var_190]
0x18001c38f  jmp     loc_18001C300
0x18001c394  mov     rax, rdx
0x18001c397  sub     rax, rcx
0x18001c39a  sar     rax, 3
0x18001c39e  test    rax, rax
0x18001c3a1  jz      loc_18001C45C
0x18001c3a7  mov     rdi, [rsi+38h]
0x18001c3ab  mov     rsi, [rsi+40h]
0x18001c3af  cmp     rdi, rsi
0x18001c3b2  jz      loc_18001C45C
0x18001c3b8  mov     rbx, [rdi]
0x18001c3bb  mov     [rsp+1C8h+var_198], rbx
0x18001c3c0  test    rbx, rbx
0x18001c3c3  jz      short loc_18001C3D5
0x18001c3c5  mov     rax, [rbx]
0x18001c3c8  mov     rcx, rbx
0x18001c3cb  mov     rax, [rax+8]
0x18001c3cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3d4  nop
0x18001c3d5  mov     rax, [rbx]
0x18001c3d8  mov     r9, [rsp+1C8h+var_68]
0x18001c3e0  add     r9, 8
0x18001c3e4  lea     r8, [rsp+1C8h+var_190]
0x18001c3e9  mov     edx, r15d
0x18001c3ec  mov     rcx, rbx
0x18001c3ef  mov     rax, [rax+20h]
0x18001c3f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3f8  mov     ebx, eax
0x18001c3fa  test    eax, eax
0x18001c3fc  jns     short loc_18001C43F
0x18001c3fe  mov     rcx, [rsp+1C8h]; this
0x18001c406  mov     r9d, eax; char *
0x18001c409  lea     r8, aShellcommonShe_3; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001c410  mov     edx, 4Ch ; 'L'; void *
0x18001c415  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c41a  nop
0x18001c41b  lea     rcx, [rsp+1C8h+var_198]
0x18001c420  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c425  nop
0x18001c426  lea     rcx, [rsp+1C8h+var_190]
0x18001c42b  call    ?_Tidy@?$vector@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@std@@@std@@AEAAXXZ; std::vector<Microsoft::WRL::ComPtr<IUserAccount>>::_Tidy(void)
0x18001c430  nop
0x18001c431  lea     rcx, [rsp+1C8h+var_178]; this
0x18001c436  call    ??1SinglePolicyEvaluation@PolicyTelemetry@@QEAA@XZ; PolicyTelemetry::SinglePolicyEvaluation::~SinglePolicyEvaluation(void)
0x18001c43b  mov     eax, ebx
0x18001c43d  jmp     short loc_18001C48B
0x18001c43f  lea     rcx, [rsp+1C8h+var_198]
0x18001c444  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c449  add     rdi, 8
0x18001c44d  mov     rdx, [rsp+1C8h+var_188]
0x18001c452  mov     rcx, [rsp+1C8h+var_190]
0x18001c457  jmp     loc_18001C3AF
0x18001c45c  sub     rdx, rcx
0x18001c45f  sar     rdx, 3; unsigned int
0x18001c463  lea     rcx, [rsp+1C8h+var_178]; this
0x18001c468  call    ?Stop@SinglePolicyEvaluation@PolicyTelemetry@@QEAAXI@Z; PolicyTelemetry::SinglePolicyEvaluation::Stop(uint)
0x18001c46d  nop
0x18001c46e  lea     rcx, [rsp+1C8h+var_190]
0x18001c473  call    ?_Tidy@?$vector@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@std@@@std@@AEAAXXZ; std::vector<Microsoft::WRL::ComPtr<IUserAccount>>::_Tidy(void)
0x18001c478  nop
0x18001c479  lea     rcx, [rsp+1C8h+var_178]; this
0x18001c47e  call    ??1SinglePolicyEvaluation@PolicyTelemetry@@QEAA@XZ; PolicyTelemetry::SinglePolicyEvaluation::~SinglePolicyEvaluation(void)
0x18001c483  xor     eax, eax
0x18001c485  jmp     short loc_18001C48B
0x18001c487  mov     eax, dword ptr [rsp+1C8h+var_198]
0x18001c48b  mov     rcx, [rsp+1C8h+var_28]
0x18001c493  xor     rcx, rsp; StackCookie
0x18001c496  call    __security_check_cookie
0x18001c49b  lea     r11, [rsp+1C8h+var_18]
0x18001c4a3  mov     rbx, [r11+30h]
0x18001c4a7  mov     rsi, [r11+38h]
0x18001c4ab  mov     rsp, r11
0x18001c4ae  pop     r15
0x18001c4b0  pop     r14
0x18001c4b2  pop     rdi
0x18001c4b3  retn
```
