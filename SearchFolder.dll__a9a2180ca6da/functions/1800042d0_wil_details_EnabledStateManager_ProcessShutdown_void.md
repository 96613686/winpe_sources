# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x1800042d0`
- end: `0x180004520`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `592`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800050d0`
- `0x180050b60`

## callees

- `0x1800042d0`
- `0x180006900`
- `0x18000fa28`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000430b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000430b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800044c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800044c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800044fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800044fb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800044f3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800044f3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800044de`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800044de`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800044ea`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800044ea`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::details::EnabledStateManager::ProcessShutdown(RTL_SRWLOCK *this)
{
  struct _TP_TIMER *Ptr; // rsi
  RTL_SRWLOCK *v3; // rbp
  _QWORD *v4; // rbx
  _BYTE *v5; // rdi
  __int64 v6; // r8
  int v7; // r10d
  unsigned __int32 v8; // ecx
  unsigned __int32 v9; // eax
  char *v10; // rdx
  unsigned __int64 v11; // r8
  __int64 v12; // rdx
  void (__fastcall *v13)(_QWORD, __int64, _QWORD, _QWORD); // rax
  DWORD LastError; // ebx
  _DWORD v15[2]; // [rsp+38h] [rbp-80h] BYREF
  char v16; // [rsp+40h] [rbp-78h] BYREF

  LODWORD(this->Ptr) = 0;
  Ptr = (struct _TP_TIMER *)this[2].Ptr;
  this[2].Ptr = 0;
  v3 = this + 1;
  AcquireSRWLockExclusive(this + 1);
  v4 = this[4].Ptr;
  v5 = this[5].Ptr;
  if ( (unsigned __int64)(v5 - (_BYTE *)v4) >= 0x10 )
  {
    while ( v4 != (_QWORD *)v5 )
    {
      v6 = v4[1];
      v7 = *(_DWORD *)v4;
      _m_prefetchw((const void *)v6);
      v8 = _InterlockedAnd((volatile signed __int32 *)v6, 0xFFC0401E);
      if ( ((v8 >> 1) & 0xF) != 0 )
      {
        _m_prefetchw((const void *)(v6 + 4));
        v9 = (v8 >> 1) & 0xF & ~_InterlockedOr((volatile signed __int32 *)(v6 + 4), (v8 >> 1) & 0xF);
      }
      else
      {
        v9 = 0;
      }
      if ( (v9 & 1) != 0 )
      {
        v15[0] = v7;
        v15[1] = 65538;
        v10 = &v16;
      }
      else
      {
        v10 = (char *)v15;
      }
      if ( (v9 & 2) != 0 )
      {
        *(_DWORD *)v10 = v7;
        *((_DWORD *)v10 + 1) = 65542;
        v10 += 8;
      }
      if ( (v9 & 4) != 0 )
      {
        *(_DWORD *)v10 = v7;
        *((_DWORD *)v10 + 1) = 65539;
        v10 += 8;
      }
      if ( v9 >= 8 )
      {
        *(_DWORD *)v10 = v7;
        *((_DWORD *)v10 + 1) = 65543;
        v10 += 8;
      }
      v11 = v8 >> 5;
      if ( (v11 & 0x1FF) != 0 )
      {
        *(_DWORD *)v10 = v7;
        *((_WORD *)v10 + 2) = 4 * ((v8 >> 14) & 1);
        LOWORD(v11) = v11 & 0x1FF;
        *((_WORD *)v10 + 3) = v11;
        v10 += 8;
      }
      if ( ((v8 >> 15) & 0x7F) != 0 )
      {
        *(_DWORD *)v10 = v7;
        *((_WORD *)v10 + 2) = 4 * ((v8 >> 22) & 1) + 1;
        *((_WORD *)v10 + 3) = (v8 >> 15) & 0x7F;
        v10 += 8;
      }
      v12 = (v10 - (char *)v15) >> 3;
      if ( v12 > 0 )
        wil::details::WilApi_RecordFeatureUsageReports(
          (wil::details *)v15,
          (struct __WIL_RTL_FEATURE_USAGE_DATA *)v12,
          v11);
      v4 += 2;
    }
    this[5].Ptr = this[4].Ptr;
    v13 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    v3 = this + 1;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v13 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v13(0, 254, 0, 0);
    }
  }
  if ( v3 )
    ReleaseSRWLockExclusive(v3);
  if ( Ptr )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(Ptr, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(Ptr, 1);
    CloseThreadpoolTimer(Ptr);
    SetLastError(LastError);
  }
}

```

## disassembly

```asm
0x1800042d0  push    rbx
0x1800042d2  push    rbp
0x1800042d3  push    rsi
0x1800042d4  push    rdi
0x1800042d5  push    r12
0x1800042d7  push    r13
0x1800042d9  push    r14
0x1800042db  push    r15
0x1800042dd  sub     rsp, 78h
0x1800042e1  mov     rax, cs:__security_cookie
0x1800042e8  xor     rax, rsp
0x1800042eb  mov     [rsp+0B8h+var_50], rax
0x1800042f0  mov     r14, rcx
0x1800042f3  xor     eax, eax
0x1800042f5  mov     [rcx], eax
0x1800042f7  mov     rsi, [rcx+10h]
0x1800042fb  mov     [rsp+0B8h+var_88], rsi
0x180004300  mov     [rcx+10h], rax
0x180004304  lea     rbp, [rcx+8]
0x180004308  mov     rcx, rbp; SRWLock
0x18000430b  call    cs:__imp_AcquireSRWLockExclusive
0x180004311  nop
0x180004312  mov     rbx, [r14+20h]
0x180004316  mov     rdi, [r14+28h]
0x18000431a  mov     rax, rdi
0x18000431d  sub     rax, rbx
0x180004320  mov     r15d, 1
0x180004326  cmp     rax, 10h
0x18000432a  jb      loc_1800044B8
0x180004330  mov     r11d, 6
0x180004336  mov     r12d, 1FFh
0x18000433c  nop     dword ptr [rax+00h]
0x180004340  cmp     rbx, rdi
0x180004343  jz      loc_18000447C
0x180004349  mov     r8, [rbx+8]
0x18000434d  mov     r10d, [rbx]
0x180004350  prefetchw byte ptr [r8]
0x180004354  mov     eax, [r8]
0x180004357  nop     word ptr [rax+rax+00000000h]
0x180004360  mov     ecx, eax
0x180004362  and     ecx, 0FFC0401Eh
0x180004368  lock cmpxchg [r8], ecx
0x18000436d  jnz     short loc_180004360
0x18000436f  mov     ecx, eax
0x180004371  mov     r9d, eax
0x180004374  shr     r9d, 1
0x180004377  and     r9d, 0Fh
0x18000437b  jz      short loc_1800043A4
0x18000437d  prefetchw byte ptr [r8+4]
0x180004382  mov     eax, [r8+4]
0x180004386  nop     word ptr [rax+rax+00000000h]
0x180004390  mov     edx, eax
0x180004392  or      edx, r9d
0x180004395  lock cmpxchg [r8+4], edx
0x18000439b  jnz     short loc_180004390
0x18000439d  not     eax
0x18000439f  and     eax, r9d
0x1800043a2  jmp     short loc_1800043A7
0x1800043a4  mov     eax, r9d
0x1800043a7  test    al, 1
0x1800043a9  jz      short loc_1800043BF
0x1800043ab  mov     [rsp+0B8h+var_80], r10d
0x1800043b0  mov     [rsp+0B8h+var_7C], 10002h
0x1800043b8  lea     rdx, [rsp+0B8h+var_78]
0x1800043bd  jmp     short loc_1800043C4
0x1800043bf  lea     rdx, [rsp+0B8h+var_80]
0x1800043c4  test    al, 2
0x1800043c6  jz      short loc_1800043D6
0x1800043c8  mov     [rdx], r10d
0x1800043cb  mov     dword ptr [rdx+4], 10006h
0x1800043d2  add     rdx, 8
0x1800043d6  test    al, 4
0x1800043d8  jz      short loc_1800043E8
0x1800043da  mov     [rdx], r10d
0x1800043dd  mov     dword ptr [rdx+4], 10003h
0x1800043e4  add     rdx, 8
0x1800043e8  cmp     eax, 8
0x1800043eb  jb      short loc_1800043FB
0x1800043ed  mov     [rdx], r10d
0x1800043f0  mov     dword ptr [rdx+4], 10007h
0x1800043f7  add     rdx, 8
0x1800043fb  mov     r8d, ecx
0x1800043fe  shr     r8d, 5
0x180004402  test    r12d, r8d
0x180004405  jz      short loc_180004428
0x180004407  mov     [rdx], r10d
0x18000440a  mov     eax, ecx
0x18000440c  shr     eax, 0Eh
0x18000440f  and     ax, 1
0x180004413  shl     ax, 2
0x180004417  mov     [rdx+4], ax
0x18000441b  and     r8w, r12w; unsigned __int64
0x18000441f  mov     [rdx+6], r8w
0x180004424  add     rdx, 8
0x180004428  mov     eax, ecx
0x18000442a  shr     eax, 0Fh
0x18000442d  test    al, 7Fh
0x18000442f  jz      short loc_180004452
0x180004431  mov     [rdx], r10d
0x180004434  shr     ecx, 16h
0x180004437  and     cx, 1
0x18000443b  shl     cx, 2
0x18000443f  inc     cx
0x180004442  mov     [rdx+4], cx
0x180004446  and     ax, 7Fh
0x18000444a  mov     [rdx+6], ax
0x18000444e  add     rdx, 8
0x180004452  lea     rax, [rsp+0B8h+var_80]
0x180004457  sub     rdx, rax
0x18000445a  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000445e  test    rdx, rdx
0x180004461  jle     short loc_180004473
0x180004463  lea     rcx, [rsp+0B8h+var_80]; this
0x180004468  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000446d  mov     r11d, 6
0x180004473  add     rbx, 10h
0x180004477  jmp     loc_180004340
0x18000447c  mov     rax, [r14+20h]
0x180004480  mov     [r14+28h], rax
0x180004484  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000448b  test    rax, rax
0x18000448e  mov     rsi, [rsp+0B8h+var_88]
0x180004493  lea     rbp, [r14+8]
0x180004497  jnz     short loc_1800044A5
0x180004499  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1800044a0  test    rax, rax
0x1800044a3  jz      short loc_1800044B8
0x1800044a5  xor     r9d, r9d
0x1800044a8  xor     r8d, r8d
0x1800044ab  mov     edx, 0FEh
0x1800044b0  xor     ecx, ecx
0x1800044b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044b7  nop
0x1800044b8  test    rbp, rbp
0x1800044bb  jz      short loc_1800044C6
0x1800044bd  mov     rcx, rbp; SRWLock
0x1800044c0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800044c6  test    rsi, rsi
0x1800044c9  jz      short loc_180004502
0x1800044cb  call    cs:__imp_GetLastError
0x1800044d1  mov     ebx, eax
0x1800044d3  xor     r9d, r9d; msWindowLength
0x1800044d6  xor     r8d, r8d; msPeriod
0x1800044d9  xor     edx, edx; pftDueTime
0x1800044db  mov     rcx, rsi; pti
0x1800044de  call    cs:__imp_SetThreadpoolTimer
0x1800044e4  mov     edx, r15d; fCancelPendingCallbacks
0x1800044e7  mov     rcx, rsi; pti
0x1800044ea  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800044f0  mov     rcx, rsi; pti
0x1800044f3  call    cs:__imp_CloseThreadpoolTimer
0x1800044f9  mov     ecx, ebx; dwErrCode
0x1800044fb  call    cs:__imp_SetLastError
0x180004501  nop
0x180004502  mov     rcx, [rsp+0B8h+var_50]
0x180004507  xor     rcx, rsp; StackCookie
0x18000450a  call    __security_check_cookie
0x18000450f  add     rsp, 78h
0x180004513  pop     r15
0x180004515  pop     r14
0x180004517  pop     r13
0x180004519  pop     r12
0x18000451b  pop     rdi
0x18000451c  pop     rsi
0x18000451d  pop     rbp
0x18000451e  pop     rbx
0x18000451f  retn
```
