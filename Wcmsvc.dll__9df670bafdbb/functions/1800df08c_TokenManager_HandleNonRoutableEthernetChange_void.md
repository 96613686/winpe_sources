# TokenManager::HandleNonRoutableEthernetChange(void)

- ea: `0x1800df08c`
- end: `0x1800df160`
- name: `?HandleNonRoutableEthernetChange@TokenManager@@SAXXZ`
- size: `212`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005a350`

## callees

- `0x180010080`
- `0x180027630`
- `0x18003c684`
- `0x180084f50`
- `0x1800ddfec`
- `0x1800de0a0`
- `0x1800df08c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800df0f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800df11f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800df0f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800df11f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800df134`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800df134`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall TokenManager::HandleNonRoutableEthernetChange(__int64 a1)
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
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__TokenManager::HandleNonRoutableEthernetChange_::_6_::_lambda_1___(
            (char *)v2 + 152,
            &v4);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__TokenManager::HandleNonRoutableEthernetChange_::_6_::_lambda_1___(
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
      (void *)0x1BC,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\tokenmanager\\lib\\tokenmanager.cpp",
      v1);
  }
}

```

## disassembly

```asm
0x1800df08c  push    rbx
0x1800df08e  sub     rsp, 50h
0x1800df092  mov     rax, cs:__security_cookie
0x1800df099  xor     rax, rsp
0x1800df09c  mov     [rsp+58h+var_18], rax
0x1800df0a1  xorps   xmm0, xmm0
0x1800df0a4  movups  xmmword ptr [rsp+58h+var_28], xmm0
0x1800df0a9  lea     rdx, [rsp+58h+var_28]
0x1800df0ae  call    ?lock@?$weak_ptr@VTokenManager@@@std@@QEBA?AV?$shared_ptr@VTokenManager@@@2@XZ; std::weak_ptr<TokenManager>::lock(void)
0x1800df0b3  nop
0x1800df0b4  mov     rbx, [rsp+58h+var_28]
0x1800df0b9  test    rbx, rbx
0x1800df0bc  jz      short loc_1800DF13B
0x1800df0be  mov     [rsp+58h+var_30], rbx
0x1800df0c3  mov     [rsp+58h+lpCriticalSection], 0
0x1800df0cc  lea     rdx, [rbx+8]
0x1800df0d0  lea     rcx, [rsp+58h+lpCriticalSection]
0x1800df0d5  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800df0da  nop
0x1800df0db  lea     rcx, [rbx+98h]
0x1800df0e2  cmp     byte ptr [rcx+78h], 0
0x1800df0e6  jz      short loc_1800DF0FA
0x1800df0e8  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x1800df0ed  test    rcx, rcx
0x1800df0f0  jz      short loc_1800DF13B
0x1800df0f2  call    cs:__imp_LeaveCriticalSection
0x1800df0f8  jmp     short loc_1800DF13B
0x1800df0fa  lea     rdx, [rsp+58h+var_30]
0x1800df0ff  cmp     dword ptr [rbx], 1
0x1800df102  jnz     short loc_1800DF10B
0x1800df104  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__TokenManager__HandleNonRoutableEthernetChange____6____lambda_1___
0x1800df109  jmp     short loc_1800DF115
0x1800df10b  add     rcx, 50h ; 'P'
0x1800df10f  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__TokenManager__HandleNonRoutableEthernetChange____6____lambda_1___
0x1800df114  nop
0x1800df115  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x1800df11a  test    rcx, rcx
0x1800df11d  jz      short loc_1800DF125
0x1800df11f  call    cs:__imp_LeaveCriticalSection
0x1800df125  lock inc qword ptr [rbx+88h]
0x1800df12d  mov     rcx, [rbx+80h]; pwk
0x1800df134  call    cs:__imp_SubmitThreadpoolWork
0x1800df13a  nop
0x1800df13b  mov     rcx, [rsp+58h+var_28+8]; this
0x1800df140  test    rcx, rcx
0x1800df143  jz      short loc_1800DF14B
0x1800df145  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800df14a  nop
0x1800df14b  jmp     short $+2
0x1800df14d  mov     rcx, [rsp+58h+var_18]
0x1800df152  xor     rcx, rsp; StackCookie
0x1800df155  call    __security_check_cookie
0x1800df15a  add     rsp, 50h
0x1800df15e  pop     rbx
0x1800df15f  retn
```
