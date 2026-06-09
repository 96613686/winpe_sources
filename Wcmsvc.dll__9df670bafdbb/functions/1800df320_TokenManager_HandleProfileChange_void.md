# TokenManager::HandleProfileChange(void)

- ea: `0x1800df320`
- end: `0x1800df3f4`
- name: `?HandleProfileChange@TokenManager@@SAXXZ`
- size: `212`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002ec10`

## callees

- `0x180010080`
- `0x180027630`
- `0x18003c684`
- `0x180084f50`
- `0x1800de708`
- `0x1800de7bc`
- `0x1800df320`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800df386`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800df3b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800df386`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800df3b3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800df3c8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800df3c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall TokenManager::HandleProfileChange(__int64 a1)
{
  const char *v1; // r9
  std::_Ref_count_base *v2; // rbx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-38h] BYREF
  std::_Ref_count_base *v4; // [rsp+28h] [rbp-30h] BYREF
  std::_Ref_count_base *v5[2]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *(_OWORD *)v5 = 0;
  std::weak_ptr<TokenManager>::lock(a1, v5);
  try
  {
    v2 = v5[0];
    if ( v5[0] )
    {
      v4 = v5[0];
      lpCriticalSection = 0;
      wil::EnterCriticalSection(&lpCriticalSection, (char *)v5[0] + 8);
      if ( *((_BYTE *)v2 + 272) )
      {
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
      }
      else
      {
        if ( *(_DWORD *)v2 == 1 )
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__TokenManager::HandleProfileChange_::_6_::_lambda_1___(
            (char *)v2 + 152,
            &v4);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__TokenManager::HandleProfileChange_::_6_::_lambda_1___(
            (char *)v2 + 232,
            &v4);
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
        _InterlockedIncrement64((volatile signed __int64 *)v2 + 17);
        SubmitThreadpoolWork(*((PTP_WORK *)v2 + 16));
      }
    }
    if ( v5[1] )
      std::_Ref_count_base::_Decref(v5[1]);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x120,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\tokenmanager\\lib\\tokenmanager.cpp",
      v1);
  }
}

```

## disassembly

```asm
0x1800df320  push    rbx
0x1800df322  sub     rsp, 50h
0x1800df326  mov     rax, cs:__security_cookie
0x1800df32d  xor     rax, rsp
0x1800df330  mov     [rsp+58h+var_18], rax
0x1800df335  xorps   xmm0, xmm0
0x1800df338  movups  xmmword ptr [rsp+58h+var_28], xmm0
0x1800df33d  lea     rdx, [rsp+58h+var_28]
0x1800df342  call    ?lock@?$weak_ptr@VTokenManager@@@std@@QEBA?AV?$shared_ptr@VTokenManager@@@2@XZ; std::weak_ptr<TokenManager>::lock(void)
0x1800df347  nop
0x1800df348  mov     rbx, [rsp+58h+var_28]
0x1800df34d  test    rbx, rbx
0x1800df350  jz      short loc_1800DF3CF
0x1800df352  mov     [rsp+58h+var_30], rbx
0x1800df357  mov     [rsp+58h+lpCriticalSection], 0
0x1800df360  lea     rdx, [rbx+8]
0x1800df364  lea     rcx, [rsp+58h+lpCriticalSection]
0x1800df369  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800df36e  nop
0x1800df36f  lea     rcx, [rbx+98h]
0x1800df376  cmp     byte ptr [rcx+78h], 0
0x1800df37a  jz      short loc_1800DF38E
0x1800df37c  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x1800df381  test    rcx, rcx
0x1800df384  jz      short loc_1800DF3CF
0x1800df386  call    cs:__imp_LeaveCriticalSection
0x1800df38c  jmp     short loc_1800DF3CF
0x1800df38e  lea     rdx, [rsp+58h+var_30]
0x1800df393  cmp     dword ptr [rbx], 1
0x1800df396  jnz     short loc_1800DF39F
0x1800df398  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__TokenManager__HandleProfileChange____6____lambda_1___
0x1800df39d  jmp     short loc_1800DF3A9
0x1800df39f  add     rcx, 50h ; 'P'
0x1800df3a3  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__TokenManager__HandleProfileChange____6____lambda_1___
0x1800df3a8  nop
0x1800df3a9  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x1800df3ae  test    rcx, rcx
0x1800df3b1  jz      short loc_1800DF3B9
0x1800df3b3  call    cs:__imp_LeaveCriticalSection
0x1800df3b9  lock inc qword ptr [rbx+88h]
0x1800df3c1  mov     rcx, [rbx+80h]; pwk
0x1800df3c8  call    cs:__imp_SubmitThreadpoolWork
0x1800df3ce  nop
0x1800df3cf  mov     rcx, [rsp+58h+var_28+8]; this
0x1800df3d4  test    rcx, rcx
0x1800df3d7  jz      short loc_1800DF3DF
0x1800df3d9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800df3de  nop
0x1800df3df  jmp     short $+2
0x1800df3e1  mov     rcx, [rsp+58h+var_18]
0x1800df3e6  xor     rcx, rsp; StackCookie
0x1800df3e9  call    __security_check_cookie
0x1800df3ee  add     rsp, 50h
0x1800df3f2  pop     rbx
0x1800df3f3  retn
```
