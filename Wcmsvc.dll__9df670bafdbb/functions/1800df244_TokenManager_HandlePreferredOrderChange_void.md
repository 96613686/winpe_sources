# TokenManager::HandlePreferredOrderChange(void)

- ea: `0x1800df244`
- end: `0x1800df318`
- name: `?HandlePreferredOrderChange@TokenManager@@SAXXZ`
- size: `212`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18008ab94`

## callees

- `0x180010080`
- `0x180027630`
- `0x18003c684`
- `0x180084f50`
- `0x1800de59c`
- `0x1800de650`
- `0x1800df244`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800df2aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800df2d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800df2aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800df2d7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800df2ec`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800df2ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall TokenManager::HandlePreferredOrderChange(__int64 a1)
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
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__TokenManager::HandlePreferredOrderChange_::_6_::_lambda_1___(
            (char *)v2 + 152,
            &v4);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__TokenManager::HandlePreferredOrderChange_::_6_::_lambda_1___(
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
      (void *)0x12F,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\tokenmanager\\lib\\tokenmanager.cpp",
      v1);
  }
}

```

## disassembly

```asm
0x1800df244  push    rbx
0x1800df246  sub     rsp, 50h
0x1800df24a  mov     rax, cs:__security_cookie
0x1800df251  xor     rax, rsp
0x1800df254  mov     [rsp+58h+var_18], rax
0x1800df259  xorps   xmm0, xmm0
0x1800df25c  movups  xmmword ptr [rsp+58h+var_28], xmm0
0x1800df261  lea     rdx, [rsp+58h+var_28]
0x1800df266  call    ?lock@?$weak_ptr@VTokenManager@@@std@@QEBA?AV?$shared_ptr@VTokenManager@@@2@XZ; std::weak_ptr<TokenManager>::lock(void)
0x1800df26b  nop
0x1800df26c  mov     rbx, [rsp+58h+var_28]
0x1800df271  test    rbx, rbx
0x1800df274  jz      short loc_1800DF2F3
0x1800df276  mov     [rsp+58h+var_30], rbx
0x1800df27b  mov     [rsp+58h+lpCriticalSection], 0
0x1800df284  lea     rdx, [rbx+8]
0x1800df288  lea     rcx, [rsp+58h+lpCriticalSection]
0x1800df28d  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800df292  nop
0x1800df293  lea     rcx, [rbx+98h]
0x1800df29a  cmp     byte ptr [rcx+78h], 0
0x1800df29e  jz      short loc_1800DF2B2
0x1800df2a0  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x1800df2a5  test    rcx, rcx
0x1800df2a8  jz      short loc_1800DF2F3
0x1800df2aa  call    cs:__imp_LeaveCriticalSection
0x1800df2b0  jmp     short loc_1800DF2F3
0x1800df2b2  lea     rdx, [rsp+58h+var_30]
0x1800df2b7  cmp     dword ptr [rbx], 1
0x1800df2ba  jnz     short loc_1800DF2C3
0x1800df2bc  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__TokenManager__HandlePreferredOrderChange____6____lambda_1___
0x1800df2c1  jmp     short loc_1800DF2CD
0x1800df2c3  add     rcx, 50h ; 'P'
0x1800df2c7  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__TokenManager__HandlePreferredOrderChange____6____lambda_1___
0x1800df2cc  nop
0x1800df2cd  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x1800df2d2  test    rcx, rcx
0x1800df2d5  jz      short loc_1800DF2DD
0x1800df2d7  call    cs:__imp_LeaveCriticalSection
0x1800df2dd  lock inc qword ptr [rbx+88h]
0x1800df2e5  mov     rcx, [rbx+80h]; pwk
0x1800df2ec  call    cs:__imp_SubmitThreadpoolWork
0x1800df2f2  nop
0x1800df2f3  mov     rcx, [rsp+58h+var_28+8]; this
0x1800df2f8  test    rcx, rcx
0x1800df2fb  jz      short loc_1800DF303
0x1800df2fd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800df302  nop
0x1800df303  jmp     short $+2
0x1800df305  mov     rcx, [rsp+58h+var_18]
0x1800df30a  xor     rcx, rsp; StackCookie
0x1800df30d  call    __security_check_cookie
0x1800df312  add     rsp, 50h
0x1800df316  pop     rbx
0x1800df317  retn
```
