# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x1800139fc`
- end: `0x180013c5b`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `607`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180010e6c`
- `0x180018e60`

## callees

- `0x1800139fc`
- `0x180016378`
- `0x18001695c`
- `0x1800189d0`
- `0x180019010`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180013c18`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180013c18`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180013bd9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180013bd9`
- `KERNEL32!CloseThreadpoolTimer` at `0x180013c27`
- `KERNEL32!CloseThreadpoolTimer` at `0x180013c27`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180013a42`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180013a42`
- `KERNEL32!SetThreadpoolTimer` at `0x180013c06`
- `KERNEL32!SetThreadpoolTimer` at `0x180013c06`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::details::EnabledStateManager::ProcessShutdown(wil::details::EnabledStateManager *this)
{
  RTL_SRWLOCK *v2; // rbp
  int *v3; // rbx
  int *v4; // rdi
  __int64 v5; // r8
  int v6; // r10d
  unsigned __int32 v7; // ecx
  unsigned __int32 v8; // eax
  char *v9; // rdx
  unsigned __int64 v10; // r8
  __int64 v11; // rdx
  void (__fastcall *v12)(_QWORD, __int64, _QWORD, _QWORD); // rax
  struct _TP_TIMER *v13; // rbx
  PTP_TIMER pti; // [rsp+30h] [rbp-68h] BYREF
  _DWORD v15[2]; // [rsp+38h] [rbp-60h] BYREF
  char v16; // [rsp+40h] [rbp-58h] BYREF

  *(_DWORD *)this = 0;
  pti = (PTP_TIMER)*((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = 0;
  v2 = (RTL_SRWLOCK *)((char *)this + 8);
  AcquireSRWLockExclusive((PSRWLOCK)this + 1);
  v3 = (int *)*((_QWORD *)this + 6);
  v4 = (int *)*((_QWORD *)this + 7);
  if ( (unsigned __int64)((char *)v4 - (char *)v3) >= 0x10 )
  {
    while ( v3 != v4 )
    {
      v5 = *((_QWORD *)v3 + 1);
      v6 = *v3;
      _m_prefetchw((const void *)v5);
      v7 = _InterlockedAnd((volatile signed __int32 *)v5, 0xFFC0401E);
      if ( ((v7 >> 1) & 0xF) != 0 )
      {
        _m_prefetchw((const void *)(v5 + 4));
        v8 = (v7 >> 1) & 0xF & ~_InterlockedOr((volatile signed __int32 *)(v5 + 4), (v7 >> 1) & 0xF);
      }
      else
      {
        v8 = 0;
      }
      if ( (v8 & 1) != 0 )
      {
        v15[0] = v6;
        v15[1] = 65538;
        v9 = &v16;
      }
      else
      {
        v9 = (char *)v15;
      }
      if ( (v8 & 2) != 0 )
      {
        *(_DWORD *)v9 = v6;
        *((_DWORD *)v9 + 1) = 65542;
        v9 += 8;
      }
      if ( (v8 & 4) != 0 )
      {
        *(_DWORD *)v9 = v6;
        *((_DWORD *)v9 + 1) = 65539;
        v9 += 8;
      }
      if ( v8 >= 8 )
      {
        *(_DWORD *)v9 = v6;
        *((_DWORD *)v9 + 1) = 65543;
        v9 += 8;
      }
      v10 = v7 >> 5;
      if ( (v10 & 0x1FF) != 0 )
      {
        *(_DWORD *)v9 = v6;
        *((_WORD *)v9 + 2) = 4 * ((v7 >> 14) & 1);
        LOWORD(v10) = v10 & 0x1FF;
        *((_WORD *)v9 + 3) = v10;
        v9 += 8;
      }
      if ( ((v7 >> 15) & 0x7F) != 0 )
      {
        *(_DWORD *)v9 = v6;
        *((_WORD *)v9 + 2) = 4 * ((v7 >> 22) & 1) + 1;
        *((_WORD *)v9 + 3) = (v7 >> 15) & 0x7F;
        v9 += 8;
      }
      v11 = (v9 - (char *)v15) >> 3;
      if ( v11 > 0 )
        wil::details::WilApi_RecordFeatureUsageReports(
          (wil::details *)v15,
          (struct __WIL_RTL_FEATURE_USAGE_DATA *)v11,
          v10);
      v3 += 4;
    }
    *((_QWORD *)this + 7) = *((_QWORD *)this + 6);
    v12 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v12 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v12(0, 254, 0, 0);
    }
  }
  if ( v2 )
    ReleaseSRWLockExclusive(v2);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    &pti,
    0);
  v13 = pti;
  if ( pti )
  {
    SetThreadpoolTimer(pti, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v13, 1);
    CloseThreadpoolTimer(v13);
  }
}

```

## disassembly

```asm
0x1800139fc  mov     [rsp+arg_8], rbx
0x180013a01  mov     [rsp+arg_10], rbp
0x180013a06  push    rsi
0x180013a07  push    rdi
0x180013a08  push    r12
0x180013a0a  push    r14
0x180013a0c  push    r15
0x180013a0e  sub     rsp, 70h
0x180013a12  mov     rax, cs:__security_cookie
0x180013a19  xor     rax, rsp
0x180013a1c  mov     [rsp+98h+var_30], rax
0x180013a21  mov     rsi, rcx
0x180013a24  mov     dword ptr [rcx], 0
0x180013a2a  mov     rax, [rcx+10h]
0x180013a2e  mov     [rsp+98h+pti], rax
0x180013a33  mov     qword ptr [rcx+10h], 0
0x180013a3b  lea     rbp, [rcx+8]
0x180013a3f  mov     rcx, rbp; SRWLock
0x180013a42  call    cs:__imp_AcquireSRWLockExclusive
0x180013a49  nop     dword ptr [rax+rax+00h]
0x180013a4e  nop
0x180013a4f  mov     rbx, [rsi+30h]
0x180013a53  mov     rdi, [rsi+38h]
0x180013a57  mov     rax, rdi
0x180013a5a  sub     rax, rbx
0x180013a5d  mov     r14d, 1
0x180013a63  cmp     rax, 10h
0x180013a67  jb      loc_180013BD1
0x180013a6d  lea     r15d, [r14+1]
0x180013a71  mov     r12d, 1FFh
0x180013a77  cmp     rbx, rdi
0x180013a7a  jz      loc_180013B9E
0x180013a80  mov     r8, [rbx+8]
0x180013a84  mov     r10d, [rbx]
0x180013a87  prefetchw byte ptr [r8]
0x180013a8b  mov     eax, [r8]
0x180013a8e  mov     ecx, eax
0x180013a90  and     ecx, 0FFC0401Eh
0x180013a96  lock cmpxchg [r8], ecx
0x180013a9b  jnz     short loc_180013A8E
0x180013a9d  mov     ecx, eax
0x180013a9f  mov     r9d, eax
0x180013aa2  shr     r9d, 1
0x180013aa5  and     r9d, 0Fh
0x180013aa9  jz      short loc_180013AC8
0x180013aab  prefetchw byte ptr [r8+4]
0x180013ab0  mov     eax, [r8+4]
0x180013ab4  mov     edx, eax
0x180013ab6  or      edx, r9d
0x180013ab9  lock cmpxchg [r8+4], edx
0x180013abf  jnz     short loc_180013AB4
0x180013ac1  not     eax
0x180013ac3  and     eax, r9d
0x180013ac6  jmp     short loc_180013ACB
0x180013ac8  mov     eax, r9d
0x180013acb  test    r14b, al
0x180013ace  jz      short loc_180013AE4
0x180013ad0  mov     [rsp+98h+var_60], r10d
0x180013ad5  mov     [rsp+98h+var_5C], 10002h
0x180013add  lea     rdx, [rsp+98h+var_58]
0x180013ae2  jmp     short loc_180013AE9
0x180013ae4  lea     rdx, [rsp+98h+var_60]
0x180013ae9  test    r15b, al
0x180013aec  jz      short loc_180013AFC
0x180013aee  mov     [rdx], r10d
0x180013af1  mov     dword ptr [rdx+4], 10006h
0x180013af8  add     rdx, 8
0x180013afc  test    al, 4
0x180013afe  jz      short loc_180013B0E
0x180013b00  mov     [rdx], r10d
0x180013b03  mov     dword ptr [rdx+4], 10003h
0x180013b0a  add     rdx, 8
0x180013b0e  cmp     eax, 8
0x180013b11  jb      short loc_180013B21
0x180013b13  mov     [rdx], r10d
0x180013b16  mov     dword ptr [rdx+4], 10007h
0x180013b1d  add     rdx, 8
0x180013b21  mov     r8d, ecx
0x180013b24  shr     r8d, 5
0x180013b28  test    r12d, r8d
0x180013b2b  jz      short loc_180013B4E
0x180013b2d  mov     [rdx], r10d
0x180013b30  mov     eax, ecx
0x180013b32  shr     eax, 0Eh
0x180013b35  and     ax, r14w
0x180013b39  shl     ax, 2
0x180013b3d  mov     [rdx+4], ax
0x180013b41  and     r8w, r12w; unsigned __int64
0x180013b45  mov     [rdx+6], r8w
0x180013b4a  add     rdx, 8
0x180013b4e  mov     eax, ecx
0x180013b50  shr     eax, 0Fh
0x180013b53  test    al, 7Fh
0x180013b55  jz      short loc_180013B79
0x180013b57  mov     [rdx], r10d
0x180013b5a  shr     ecx, 16h
0x180013b5d  and     cx, r14w
0x180013b61  shl     cx, 2
0x180013b65  add     cx, r14w
0x180013b69  mov     [rdx+4], cx
0x180013b6d  and     ax, 7Fh
0x180013b71  mov     [rdx+6], ax
0x180013b75  add     rdx, 8
0x180013b79  lea     rax, [rsp+98h+var_60]
0x180013b7e  sub     rdx, rax
0x180013b81  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180013b85  test    rdx, rdx
0x180013b88  jle     short loc_180013B95
0x180013b8a  lea     rcx, [rsp+98h+var_60]; this
0x180013b8f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180013b94  nop
0x180013b95  add     rbx, 10h
0x180013b99  jmp     loc_180013A77
0x180013b9e  mov     rax, [rsi+30h]
0x180013ba2  mov     [rsi+38h], rax
0x180013ba6  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180013bad  test    rax, rax
0x180013bb0  jnz     short loc_180013BBE
0x180013bb2  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180013bb9  test    rax, rax
0x180013bbc  jz      short loc_180013BD1
0x180013bbe  xor     r9d, r9d
0x180013bc1  xor     r8d, r8d
0x180013bc4  mov     edx, 0FEh
0x180013bc9  xor     ecx, ecx
0x180013bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bd0  nop
0x180013bd1  test    rbp, rbp
0x180013bd4  jz      short loc_180013BE5
0x180013bd6  mov     rcx, rbp; SRWLock
0x180013bd9  call    cs:__imp_ReleaseSRWLockExclusive
0x180013be0  nop     dword ptr [rax+rax+00h]
0x180013be5  xor     edx, edx
0x180013be7  lea     rcx, [rsp+98h+pti]
0x180013bec  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180013bf1  mov     rbx, [rsp+98h+pti]
0x180013bf6  test    rbx, rbx
0x180013bf9  jz      short loc_180013C34
0x180013bfb  xor     r9d, r9d; msWindowLength
0x180013bfe  xor     r8d, r8d; msPeriod
0x180013c01  xor     edx, edx; pftDueTime
0x180013c03  mov     rcx, rbx; pti
0x180013c06  call    cs:__imp_SetThreadpoolTimer
0x180013c0d  nop     dword ptr [rax+rax+00h]
0x180013c12  mov     edx, r14d; fCancelPendingCallbacks
0x180013c15  mov     rcx, rbx; pti
0x180013c18  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180013c1f  nop     dword ptr [rax+rax+00h]
0x180013c24  mov     rcx, rbx; pti
0x180013c27  call    cs:__imp_CloseThreadpoolTimer
0x180013c2e  nop     dword ptr [rax+rax+00h]
0x180013c33  nop
0x180013c34  mov     rcx, [rsp+98h+var_30]
0x180013c39  xor     rcx, rsp; StackCookie
0x180013c3c  call    __security_check_cookie
0x180013c41  lea     r11, [rsp+98h+var_28]
0x180013c46  mov     rbx, [r11+38h]
0x180013c4a  mov     rbp, [r11+40h]
0x180013c4e  mov     rsp, r11
0x180013c51  pop     r15
0x180013c53  pop     r14
0x180013c55  pop     r12
0x180013c57  pop     rdi
0x180013c58  pop     rsi
0x180013c59  retn
```
