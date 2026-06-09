# TokenManager::HandleNlaPropertyChange(_GUID const &,_WCM_MEDIA_TYPE)

- ea: `0x18001eef0`
- end: `0x18001efe6`
- name: `?HandleNlaPropertyChange@TokenManager@@SAXAEBU_GUID@@W4_WCM_MEDIA_TYPE@@@Z`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002ec10`

## callees

- `0x180010080`
- `0x18001eef0`
- `0x18001f820`
- `0x1800ddef0`
- `0x1800ddf2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ef55`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ef55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ef88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001efd1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ef88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001efd1`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001ef9d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001ef9d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall TokenManager::HandleNlaPropertyChange(const char *a1, int a2)
{
  int v2; // r8d
  const char *v3; // r9
  __m128i v4; // xmm6
  std::_Ref_count_base *v5; // rcx
  __int64 v6; // [rsp+30h] [rbp-38h] BYREF
  __int128 v7; // [rsp+38h] [rbp-30h]
  int v8; // [rsp+48h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v2 = a2;
  v3 = a1;
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
      v6 = v4.m128i_i64[0];
      v7 = *(_OWORD *)v3;
      v8 = v2;
      EnterCriticalSection((LPCRITICAL_SECTION)(v4.m128i_i64[0] + 8));
      if ( *(_BYTE *)(v4.m128i_i64[0] + 272) )
      {
        if ( v4.m128i_i64[0] != -8 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v4.m128i_i64[0] + 8));
      }
      else
      {
        if ( *(_DWORD *)v4.m128i_i64[0] == 1 )
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__TokenManager::HandleNlaPropertyChange_::_6_::_lambda_1___(
            v4.m128i_i64[0] + 152,
            &v6);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__TokenManager::HandleNlaPropertyChange_::_6_::_lambda_1___(
            v4.m128i_i64[0] + 232,
            &v6);
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
      (void *)0x13E,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\tokenmanager\\lib\\tokenmanager.cpp",
      v3);
  }
}

```

## disassembly

```asm
0x18001eef0  mov     [rsp+arg_0], rbx
0x18001eef5  push    rdi
0x18001eef6  sub     rsp, 60h
0x18001eefa  movaps  [rsp+68h+var_18], xmm6
0x18001eeff  mov     r8d, edx
0x18001ef02  mov     r9, rcx
0x18001ef05  xorps   xmm6, xmm6
0x18001ef08  movdqu  [rsp+68h+var_48], xmm6
0x18001ef0e  mov     rcx, qword ptr cs:?g_weakReference@@3V?$weak_ptr@VTokenManager@@@std@@A+8; this
0x18001ef15  test    rcx, rcx
0x18001ef18  jz      short loc_18001EF30
0x18001ef1a  call    ?_Incref_nz@_Ref_count_base@std@@QEAA_NXZ; std::_Ref_count_base::_Incref_nz(void)
0x18001ef1f  test    al, al
0x18001ef21  jz      short loc_18001EF30
0x18001ef23  movups  xmm6, cs:?g_weakReference@@3V?$weak_ptr@VTokenManager@@@std@@A; std::weak_ptr<TokenManager> g_weakReference
0x18001ef2a  movdqu  [rsp+68h+var_48], xmm6
0x18001ef30  movq    rbx, xmm6
0x18001ef35  test    rbx, rbx
0x18001ef38  jz      short loc_18001EFA4
0x18001ef3a  mov     [rsp+68h+var_38], rbx
0x18001ef3f  movups  xmm0, xmmword ptr [r9]
0x18001ef43  movdqu  [rsp+68h+var_30], xmm0
0x18001ef49  mov     [rsp+68h+var_20], r8d
0x18001ef4e  lea     rdi, [rbx+8]
0x18001ef52  mov     rcx, rdi; lpCriticalSection
0x18001ef55  call    cs:__imp_EnterCriticalSection
0x18001ef5b  mov     [rsp+68h+arg_10], rdi
0x18001ef63  lea     rcx, [rbx+98h]
0x18001ef6a  cmp     byte ptr [rcx+78h], 0
0x18001ef6e  jnz     short loc_18001EFC9
0x18001ef70  lea     rdx, [rsp+68h+var_38]
0x18001ef75  cmp     dword ptr [rbx], 1
0x18001ef78  jnz     short loc_18001EFD9
0x18001ef7a  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__TokenManager__HandleNlaPropertyChange____6____lambda_1___
0x18001ef7f  nop
0x18001ef80  test    rdi, rdi
0x18001ef83  jz      short loc_18001EF8E
0x18001ef85  mov     rcx, rdi; lpCriticalSection
0x18001ef88  call    cs:__imp_LeaveCriticalSection
0x18001ef8e  lock inc qword ptr [rbx+88h]
0x18001ef96  mov     rcx, [rbx+80h]; pwk
0x18001ef9d  call    cs:__imp_SubmitThreadpoolWork
0x18001efa3  nop
0x18001efa4  psrldq  xmm6, 8
0x18001efa9  movq    rcx, xmm6; this
0x18001efae  test    rcx, rcx
0x18001efb1  jz      short loc_18001EFB9
0x18001efb3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001efb8  nop
0x18001efb9  mov     rbx, [rsp+68h+arg_0]
0x18001efbe  movaps  xmm6, [rsp+68h+var_18]
0x18001efc3  add     rsp, 60h
0x18001efc7  pop     rdi
0x18001efc8  retn
0x18001efc9  test    rdi, rdi
0x18001efcc  jz      short loc_18001EFA4
0x18001efce  mov     rcx, rdi; lpCriticalSection
0x18001efd1  call    cs:__imp_LeaveCriticalSection
0x18001efd7  jmp     short loc_18001EFA4
0x18001efd9  add     rcx, 50h ; 'P'
0x18001efdd  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__TokenManager__HandleNlaPropertyChange____6____lambda_1___
0x18001efe2  jmp     short loc_18001EF80
0x18001efe4  jmp     short loc_18001EFB9
```
