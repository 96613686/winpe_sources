# TokenManager::HandleSoftDisconnected(_GUID const &)

- ea: `0x1800df3fc`
- end: `0x1800df4e1`
- name: `?HandleSoftDisconnected@TokenManager@@SAXAEBU_GUID@@@Z`
- size: `229`
- prototype: `void __fastcall(const struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004880c`

## callees

- `0x180010080`
- `0x180027630`
- `0x18003c684`
- `0x180084f50`
- `0x1800de874`
- `0x1800de8b0`
- `0x1800df3fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800df473`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800df4a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800df473`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800df4a0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800df4b5`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800df4b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall TokenManager::HandleSoftDisconnected(const struct _GUID *a1)
{
  const char *v1; // r9
  std::_Ref_count_base *v2; // rbx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-48h] BYREF
  std::_Ref_count_base *v4; // [rsp+28h] [rbp-40h] BYREF
  __int128 v5; // [rsp+30h] [rbp-38h]
  std::_Ref_count_base *v6[2]; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *(_OWORD *)v6 = 0;
  std::weak_ptr<TokenManager>::lock(a1, v6);
  try
  {
    v2 = v6[0];
    if ( v6[0] )
    {
      v4 = v6[0];
      v5 = *(_OWORD *)v1;
      lpCriticalSection = 0;
      wil::EnterCriticalSection(&lpCriticalSection, (char *)v6[0] + 8);
      if ( *((_BYTE *)v2 + 272) )
      {
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
      }
      else
      {
        if ( *(_DWORD *)v2 == 1 )
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__TokenManager::HandleSoftDisconnected_::_6_::_lambda_1___(
            (char *)v2 + 152,
            &v4);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__TokenManager::HandleSoftDisconnected_::_6_::_lambda_1___(
            (char *)v2 + 232,
            &v4);
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
        _InterlockedIncrement64((volatile signed __int64 *)v2 + 17);
        SubmitThreadpoolWork(*((PTP_WORK *)v2 + 16));
      }
    }
    if ( v6[1] )
      std::_Ref_count_base::_Decref(v6[1]);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x111,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\tokenmanager\\lib\\tokenmanager.cpp",
      v1);
  }
}

```

## disassembly

```asm
0x1800df3fc  push    rbx
0x1800df3fe  sub     rsp, 60h
0x1800df402  mov     rax, cs:__security_cookie
0x1800df409  xor     rax, rsp
0x1800df40c  mov     [rsp+68h+var_18], rax
0x1800df411  mov     r9, rcx
0x1800df414  xorps   xmm0, xmm0
0x1800df417  movups  xmmword ptr [rsp+68h+var_28], xmm0
0x1800df41c  lea     rdx, [rsp+68h+var_28]
0x1800df421  call    ?lock@?$weak_ptr@VTokenManager@@@std@@QEBA?AV?$shared_ptr@VTokenManager@@@2@XZ; std::weak_ptr<TokenManager>::lock(void)
0x1800df426  nop
0x1800df427  mov     rbx, [rsp+68h+var_28]
0x1800df42c  test    rbx, rbx
0x1800df42f  jz      loc_1800DF4BC
0x1800df435  mov     [rsp+68h+var_40], rbx
0x1800df43a  movups  xmm0, xmmword ptr [r9]
0x1800df43e  movdqu  [rsp+68h+var_38], xmm0
0x1800df444  mov     [rsp+68h+lpCriticalSection], 0
0x1800df44d  lea     rdx, [rbx+8]
0x1800df451  lea     rcx, [rsp+68h+lpCriticalSection]
0x1800df456  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800df45b  nop
0x1800df45c  lea     rcx, [rbx+98h]
0x1800df463  cmp     byte ptr [rcx+78h], 0
0x1800df467  jz      short loc_1800DF47B
0x1800df469  mov     rcx, [rsp+68h+lpCriticalSection]; lpCriticalSection
0x1800df46e  test    rcx, rcx
0x1800df471  jz      short loc_1800DF4BC
0x1800df473  call    cs:__imp_LeaveCriticalSection
0x1800df479  jmp     short loc_1800DF4BC
0x1800df47b  lea     rdx, [rsp+68h+var_40]
0x1800df480  cmp     dword ptr [rbx], 1
0x1800df483  jnz     short loc_1800DF48C
0x1800df485  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__TokenManager__HandleSoftDisconnected____6____lambda_1___
0x1800df48a  jmp     short loc_1800DF496
0x1800df48c  add     rcx, 50h ; 'P'
0x1800df490  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__TokenManager__HandleSoftDisconnected____6____lambda_1___
0x1800df495  nop
0x1800df496  mov     rcx, [rsp+68h+lpCriticalSection]; lpCriticalSection
0x1800df49b  test    rcx, rcx
0x1800df49e  jz      short loc_1800DF4A6
0x1800df4a0  call    cs:__imp_LeaveCriticalSection
0x1800df4a6  lock inc qword ptr [rbx+88h]
0x1800df4ae  mov     rcx, [rbx+80h]; pwk
0x1800df4b5  call    cs:__imp_SubmitThreadpoolWork
0x1800df4bb  nop
0x1800df4bc  mov     rcx, [rsp+68h+var_28+8]; this
0x1800df4c1  test    rcx, rcx
0x1800df4c4  jz      short loc_1800DF4CC
0x1800df4c6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800df4cb  nop
0x1800df4cc  jmp     short $+2
0x1800df4ce  mov     rcx, [rsp+68h+var_18]
0x1800df4d3  xor     rcx, rsp; StackCookie
0x1800df4d6  call    __security_check_cookie
0x1800df4db  add     rsp, 60h
0x1800df4df  pop     rbx
0x1800df4e0  retn
```
