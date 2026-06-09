# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x14000c300`
- end: `0x14000c550`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `592`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14000d1b0`
- `0x140070170`

## callees

- `0x14000c300`
- `0x14000f6a0`
- `0x140014b04`
- `0x140071010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c4fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c4fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c52b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c52b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000c33b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000c33b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000c4f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000c4f0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000c523`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000c523`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000c51a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000c51a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000c50e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000c50e`

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
0x14000c300  push    rbx
0x14000c302  push    rbp
0x14000c303  push    rsi
0x14000c304  push    rdi
0x14000c305  push    r12
0x14000c307  push    r13
0x14000c309  push    r14
0x14000c30b  push    r15
0x14000c30d  sub     rsp, 78h
0x14000c311  mov     rax, cs:__security_cookie
0x14000c318  xor     rax, rsp
0x14000c31b  mov     [rsp+0B8h+var_50], rax
0x14000c320  mov     r14, rcx
0x14000c323  xor     eax, eax
0x14000c325  mov     [rcx], eax
0x14000c327  mov     rsi, [rcx+10h]
0x14000c32b  mov     [rsp+0B8h+var_88], rsi
0x14000c330  mov     [rcx+10h], rax
0x14000c334  lea     rbp, [rcx+8]
0x14000c338  mov     rcx, rbp; SRWLock
0x14000c33b  call    cs:__imp_AcquireSRWLockExclusive
0x14000c341  nop
0x14000c342  mov     rbx, [r14+20h]
0x14000c346  mov     rdi, [r14+28h]
0x14000c34a  mov     rax, rdi
0x14000c34d  sub     rax, rbx
0x14000c350  mov     r15d, 1
0x14000c356  cmp     rax, 10h
0x14000c35a  jb      loc_14000C4E8
0x14000c360  mov     r11d, 6
0x14000c366  mov     r12d, 1FFh
0x14000c36c  nop     dword ptr [rax+00h]
0x14000c370  cmp     rbx, rdi
0x14000c373  jz      loc_14000C4AC
0x14000c379  mov     r8, [rbx+8]
0x14000c37d  mov     r10d, [rbx]
0x14000c380  prefetchw byte ptr [r8]
0x14000c384  mov     eax, [r8]
0x14000c387  nop     word ptr [rax+rax+00000000h]
0x14000c390  mov     ecx, eax
0x14000c392  and     ecx, 0FFC0401Eh
0x14000c398  lock cmpxchg [r8], ecx
0x14000c39d  jnz     short loc_14000C390
0x14000c39f  mov     ecx, eax
0x14000c3a1  mov     r9d, eax
0x14000c3a4  shr     r9d, 1
0x14000c3a7  and     r9d, 0Fh
0x14000c3ab  jz      short loc_14000C3D4
0x14000c3ad  prefetchw byte ptr [r8+4]
0x14000c3b2  mov     eax, [r8+4]
0x14000c3b6  nop     word ptr [rax+rax+00000000h]
0x14000c3c0  mov     edx, eax
0x14000c3c2  or      edx, r9d
0x14000c3c5  lock cmpxchg [r8+4], edx
0x14000c3cb  jnz     short loc_14000C3C0
0x14000c3cd  not     eax
0x14000c3cf  and     eax, r9d
0x14000c3d2  jmp     short loc_14000C3D7
0x14000c3d4  mov     eax, r9d
0x14000c3d7  test    al, 1
0x14000c3d9  jz      short loc_14000C3EF
0x14000c3db  mov     [rsp+0B8h+var_80], r10d
0x14000c3e0  mov     [rsp+0B8h+var_7C], 10002h
0x14000c3e8  lea     rdx, [rsp+0B8h+var_78]
0x14000c3ed  jmp     short loc_14000C3F4
0x14000c3ef  lea     rdx, [rsp+0B8h+var_80]
0x14000c3f4  test    al, 2
0x14000c3f6  jz      short loc_14000C406
0x14000c3f8  mov     [rdx], r10d
0x14000c3fb  mov     dword ptr [rdx+4], 10006h
0x14000c402  add     rdx, 8
0x14000c406  test    al, 4
0x14000c408  jz      short loc_14000C418
0x14000c40a  mov     [rdx], r10d
0x14000c40d  mov     dword ptr [rdx+4], 10003h
0x14000c414  add     rdx, 8
0x14000c418  cmp     eax, 8
0x14000c41b  jb      short loc_14000C42B
0x14000c41d  mov     [rdx], r10d
0x14000c420  mov     dword ptr [rdx+4], 10007h
0x14000c427  add     rdx, 8
0x14000c42b  mov     r8d, ecx
0x14000c42e  shr     r8d, 5
0x14000c432  test    r12d, r8d
0x14000c435  jz      short loc_14000C458
0x14000c437  mov     [rdx], r10d
0x14000c43a  mov     eax, ecx
0x14000c43c  shr     eax, 0Eh
0x14000c43f  and     ax, 1
0x14000c443  shl     ax, 2
0x14000c447  mov     [rdx+4], ax
0x14000c44b  and     r8w, r12w; unsigned __int64
0x14000c44f  mov     [rdx+6], r8w
0x14000c454  add     rdx, 8
0x14000c458  mov     eax, ecx
0x14000c45a  shr     eax, 0Fh
0x14000c45d  test    al, 7Fh
0x14000c45f  jz      short loc_14000C482
0x14000c461  mov     [rdx], r10d
0x14000c464  shr     ecx, 16h
0x14000c467  and     cx, 1
0x14000c46b  shl     cx, 2
0x14000c46f  inc     cx
0x14000c472  mov     [rdx+4], cx
0x14000c476  and     ax, 7Fh
0x14000c47a  mov     [rdx+6], ax
0x14000c47e  add     rdx, 8
0x14000c482  lea     rax, [rsp+0B8h+var_80]
0x14000c487  sub     rdx, rax
0x14000c48a  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x14000c48e  test    rdx, rdx
0x14000c491  jle     short loc_14000C4A3
0x14000c493  lea     rcx, [rsp+0B8h+var_80]; this
0x14000c498  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x14000c49d  mov     r11d, 6
0x14000c4a3  add     rbx, 10h
0x14000c4a7  jmp     loc_14000C370
0x14000c4ac  mov     rax, [r14+20h]
0x14000c4b0  mov     [r14+28h], rax
0x14000c4b4  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x14000c4bb  test    rax, rax
0x14000c4be  mov     rsi, [rsp+0B8h+var_88]
0x14000c4c3  lea     rbp, [r14+8]
0x14000c4c7  jnz     short loc_14000C4D5
0x14000c4c9  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x14000c4d0  test    rax, rax
0x14000c4d3  jz      short loc_14000C4E8
0x14000c4d5  xor     r9d, r9d
0x14000c4d8  xor     r8d, r8d
0x14000c4db  mov     edx, 0FEh
0x14000c4e0  xor     ecx, ecx
0x14000c4e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c4e7  nop
0x14000c4e8  test    rbp, rbp
0x14000c4eb  jz      short loc_14000C4F6
0x14000c4ed  mov     rcx, rbp; SRWLock
0x14000c4f0  call    cs:__imp_ReleaseSRWLockExclusive
0x14000c4f6  test    rsi, rsi
0x14000c4f9  jz      short loc_14000C532
0x14000c4fb  call    cs:__imp_GetLastError
0x14000c501  mov     ebx, eax
0x14000c503  xor     r9d, r9d; msWindowLength
0x14000c506  xor     r8d, r8d; msPeriod
0x14000c509  xor     edx, edx; pftDueTime
0x14000c50b  mov     rcx, rsi; pti
0x14000c50e  call    cs:__imp_SetThreadpoolTimer
0x14000c514  mov     edx, r15d; fCancelPendingCallbacks
0x14000c517  mov     rcx, rsi; pti
0x14000c51a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000c520  mov     rcx, rsi; pti
0x14000c523  call    cs:__imp_CloseThreadpoolTimer
0x14000c529  mov     ecx, ebx; dwErrCode
0x14000c52b  call    cs:__imp_SetLastError
0x14000c531  nop
0x14000c532  mov     rcx, [rsp+0B8h+var_50]
0x14000c537  xor     rcx, rsp; StackCookie
0x14000c53a  call    __security_check_cookie
0x14000c53f  add     rsp, 78h
0x14000c543  pop     r15
0x14000c545  pop     r14
0x14000c547  pop     r13
0x14000c549  pop     r12
0x14000c54b  pop     rdi
0x14000c54c  pop     rsi
0x14000c54d  pop     rbp
0x14000c54e  pop     rbx
0x14000c54f  retn
```
