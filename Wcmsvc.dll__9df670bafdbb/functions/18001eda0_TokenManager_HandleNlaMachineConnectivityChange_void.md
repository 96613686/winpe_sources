# TokenManager::HandleNlaMachineConnectivityChange(void)

- ea: `0x18001eda0`
- end: `0x18001ee7e`
- name: `?HandleNlaMachineConnectivityChange@TokenManager@@SAXXZ`
- size: `222`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180050bb0`

## callees

- `0x180010080`
- `0x18001eda0`
- `0x18001f820`
- `0x1800ddd84`
- `0x1800dde38`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001edf0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001edf0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ee20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ee74`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ee20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ee74`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001ee35`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001ee35`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall TokenManager::HandleNlaMachineConnectivityChange(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  __m128i v4; // xmm6
  std::_Ref_count_base *v5; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v7; // [rsp+50h] [rbp+8h] BYREF
  __int64 v8; // [rsp+58h] [rbp+10h]

  v4 = 0;
  if ( *((_QWORD *)&g_weakReference + 1)
    && std::_Ref_count_base::_Incref_nz(*((std::_Ref_count_base **)&g_weakReference + 1)) )
  {
    v4 = (__m128i)g_weakReference;
  }
  try
  {
    if ( v4.m128i_i64[0] )
    {
      v7 = v4.m128i_i64[0];
      EnterCriticalSection((LPCRITICAL_SECTION)(v4.m128i_i64[0] + 8));
      v8 = v4.m128i_i64[0] + 8;
      if ( *(_BYTE *)(v4.m128i_i64[0] + 272) )
      {
        if ( v4.m128i_i64[0] != -8 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v4.m128i_i64[0] + 8));
      }
      else
      {
        if ( *(_DWORD *)v4.m128i_i64[0] == 1 )
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__TokenManager::HandleNlaMachineConnectivityChange_::_6_::_lambda_1___(
            v4.m128i_i64[0] + 152,
            &v7);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__TokenManager::HandleNlaMachineConnectivityChange_::_6_::_lambda_1___(
            v4.m128i_i64[0] + 232,
            &v7);
        if ( v4.m128i_i64[0] != -8 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v4.m128i_i64[0] + 8));
        _InterlockedIncrement64((volatile signed __int64 *)(v4.m128i_i64[0] + 136));
        SubmitThreadpoolWork(*(PTP_WORK *)(v4.m128i_i64[0] + 128));
      }
    }
    v5 = (std::_Ref_count_base *)_mm_srli_si128(v4, 8).m128i_u64[0];
    if ( v5 )
      std::_Ref_count_base::_Decref(v5);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x14D,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\tokenmanager\\lib\\tokenmanager.cpp",
      a4);
  }
}

```

## disassembly

```asm
0x18001eda0  mov     [rsp+arg_10], rbx
0x18001eda5  push    rdi
0x18001eda6  sub     rsp, 40h
0x18001edaa  movaps  [rsp+48h+var_18], xmm6
0x18001edaf  xorps   xmm6, xmm6
0x18001edb2  movdqu  [rsp+48h+var_28], xmm6
0x18001edb8  mov     rcx, qword ptr cs:?g_weakReference@@3V?$weak_ptr@VTokenManager@@@std@@A+8; this
0x18001edbf  test    rcx, rcx
0x18001edc2  jz      short loc_18001EDDA
0x18001edc4  call    ?_Incref_nz@_Ref_count_base@std@@QEAA_NXZ; std::_Ref_count_base::_Incref_nz(void)
0x18001edc9  test    al, al
0x18001edcb  jz      short loc_18001EDDA
0x18001edcd  movups  xmm6, cs:?g_weakReference@@3V?$weak_ptr@VTokenManager@@@std@@A; std::weak_ptr<TokenManager> g_weakReference
0x18001edd4  movdqu  [rsp+48h+var_28], xmm6
0x18001edda  movq    rbx, xmm6
0x18001eddf  test    rbx, rbx
0x18001ede2  jz      short loc_18001EE3C
0x18001ede4  mov     [rsp+48h+arg_0], rbx
0x18001ede9  lea     rdi, [rbx+8]
0x18001eded  mov     rcx, rdi; lpCriticalSection
0x18001edf0  call    cs:__imp_EnterCriticalSection
0x18001edf6  mov     [rsp+48h+arg_8], rdi
0x18001edfb  lea     rcx, [rbx+98h]
0x18001ee02  cmp     byte ptr [rcx+78h], 0
0x18001ee06  jnz     short loc_18001EE6C
0x18001ee08  lea     rdx, [rsp+48h+arg_0]
0x18001ee0d  cmp     dword ptr [rbx], 1
0x18001ee10  jnz     short loc_18001EE61
0x18001ee12  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__TokenManager__HandleNlaMachineConnectivityChange____6____lambda_1___
0x18001ee17  nop
0x18001ee18  test    rdi, rdi
0x18001ee1b  jz      short loc_18001EE26
0x18001ee1d  mov     rcx, rdi; lpCriticalSection
0x18001ee20  call    cs:__imp_LeaveCriticalSection
0x18001ee26  lock inc qword ptr [rbx+88h]
0x18001ee2e  mov     rcx, [rbx+80h]; pwk
0x18001ee35  call    cs:__imp_SubmitThreadpoolWork
0x18001ee3b  nop
0x18001ee3c  psrldq  xmm6, 8
0x18001ee41  movq    rcx, xmm6; this
0x18001ee46  test    rcx, rcx
0x18001ee49  jz      short loc_18001EE51
0x18001ee4b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001ee50  nop
0x18001ee51  mov     rbx, [rsp+48h+arg_10]
0x18001ee56  movaps  xmm6, [rsp+48h+var_18]
0x18001ee5b  add     rsp, 40h
0x18001ee5f  pop     rdi
0x18001ee60  retn
0x18001ee61  add     rcx, 50h ; 'P'
0x18001ee65  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__TokenManager__HandleNlaMachineConnectivityChange____6____lambda_1___
0x18001ee6a  jmp     short loc_18001EE18
0x18001ee6c  test    rdi, rdi
0x18001ee6f  jz      short loc_18001EE3C
0x18001ee71  mov     rcx, rdi; lpCriticalSection
0x18001ee74  call    cs:__imp_LeaveCriticalSection
0x18001ee7a  jmp     short loc_18001EE3C
0x18001ee7c  jmp     short loc_18001EE51
```
