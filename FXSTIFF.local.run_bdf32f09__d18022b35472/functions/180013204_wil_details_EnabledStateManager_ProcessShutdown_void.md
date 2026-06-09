# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x180013204`
- end: `0x180013432`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `558`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800107c0`
- `0x180018090`

## callees

- `0x180013204`
- `0x1800158d4`
- `0x180017c00`
- `0x180019010`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800133fb`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800133fb`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800133d1`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800133d1`
- `KERNEL32!CloseThreadpoolTimer` at `0x180013404`
- `KERNEL32!CloseThreadpoolTimer` at `0x180013404`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180013240`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180013240`
- `KERNEL32!SetThreadpoolTimer` at `0x1800133ef`
- `KERNEL32!SetThreadpoolTimer` at `0x1800133ef`
- `KERNEL32!GetLastError` at `0x1800133dc`
- `KERNEL32!GetLastError` at `0x1800133dc`
- `KERNEL32!SetLastError` at `0x18001340d`
- `KERNEL32!SetLastError` at `0x18001340d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::details::EnabledStateManager::ProcessShutdown(RTL_SRWLOCK *this)
{
  struct _TP_TIMER *Ptr; // rdi
  RTL_SRWLOCK *v3; // rbp
  _QWORD *v4; // rbx
  _BYTE *v5; // rsi
  __int64 v6; // r8
  int v7; // r10d
  unsigned __int32 v8; // ecx
  unsigned __int32 v9; // eax
  char *v10; // rdx
  unsigned __int64 v11; // r8
  __int64 v12; // rdx
  void (__fastcall *v13)(_QWORD, __int64, _QWORD, _QWORD); // rax
  DWORD LastError; // ebx
  _DWORD v15[2]; // [rsp+30h] [rbp-88h] BYREF
  char v16; // [rsp+38h] [rbp-80h] BYREF

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
0x180013204  push    rbx
0x180013206  push    rbp
0x180013207  push    rsi
0x180013208  push    rdi
0x180013209  push    r12
0x18001320b  push    r13
0x18001320d  push    r14
0x18001320f  push    r15
0x180013211  sub     rsp, 78h
0x180013215  mov     rax, cs:__security_cookie
0x18001321c  xor     rax, rsp
0x18001321f  mov     [rsp+0B8h+var_58], rax
0x180013224  mov     r14, rcx
0x180013227  mov     dword ptr [rcx], 0
0x18001322d  mov     rdi, [rcx+10h]
0x180013231  mov     qword ptr [rcx+10h], 0
0x180013239  lea     rbp, [rcx+8]
0x18001323d  mov     rcx, rbp; SRWLock
0x180013240  call    cs:__imp_AcquireSRWLockExclusive
0x180013246  nop
0x180013247  mov     rbx, [r14+20h]
0x18001324b  mov     rsi, [r14+28h]
0x18001324f  mov     rax, rsi
0x180013252  sub     rax, rbx
0x180013255  mov     r15d, 1
0x18001325b  cmp     rax, 10h
0x18001325f  jb      loc_1800133C9
0x180013265  lea     r12d, [r15+1]
0x180013269  mov     r13d, 1FFh
0x18001326f  cmp     rbx, rsi
0x180013272  jz      loc_180013396
0x180013278  mov     r8, [rbx+8]
0x18001327c  mov     r10d, [rbx]
0x18001327f  prefetchw byte ptr [r8]
0x180013283  mov     eax, [r8]
0x180013286  mov     ecx, eax
0x180013288  and     ecx, 0FFC0401Eh
0x18001328e  lock cmpxchg [r8], ecx
0x180013293  jnz     short loc_180013286
0x180013295  mov     ecx, eax
0x180013297  mov     r9d, eax
0x18001329a  shr     r9d, 1
0x18001329d  and     r9d, 0Fh
0x1800132a1  jz      short loc_1800132C0
0x1800132a3  prefetchw byte ptr [r8+4]
0x1800132a8  mov     eax, [r8+4]
0x1800132ac  mov     edx, eax
0x1800132ae  or      edx, r9d
0x1800132b1  lock cmpxchg [r8+4], edx
0x1800132b7  jnz     short loc_1800132AC
0x1800132b9  not     eax
0x1800132bb  and     eax, r9d
0x1800132be  jmp     short loc_1800132C3
0x1800132c0  mov     eax, r9d
0x1800132c3  test    r15b, al
0x1800132c6  jz      short loc_1800132DC
0x1800132c8  mov     [rsp+0B8h+var_88], r10d
0x1800132cd  mov     [rsp+0B8h+var_84], 10002h
0x1800132d5  lea     rdx, [rsp+0B8h+var_80]
0x1800132da  jmp     short loc_1800132E1
0x1800132dc  lea     rdx, [rsp+0B8h+var_88]
0x1800132e1  test    r12b, al
0x1800132e4  jz      short loc_1800132F4
0x1800132e6  mov     [rdx], r10d
0x1800132e9  mov     dword ptr [rdx+4], 10006h
0x1800132f0  add     rdx, 8
0x1800132f4  test    al, 4
0x1800132f6  jz      short loc_180013306
0x1800132f8  mov     [rdx], r10d
0x1800132fb  mov     dword ptr [rdx+4], 10003h
0x180013302  add     rdx, 8
0x180013306  cmp     eax, 8
0x180013309  jb      short loc_180013319
0x18001330b  mov     [rdx], r10d
0x18001330e  mov     dword ptr [rdx+4], 10007h
0x180013315  add     rdx, 8
0x180013319  mov     r8d, ecx
0x18001331c  shr     r8d, 5
0x180013320  test    r13d, r8d
0x180013323  jz      short loc_180013346
0x180013325  mov     [rdx], r10d
0x180013328  mov     eax, ecx
0x18001332a  shr     eax, 0Eh
0x18001332d  and     ax, r15w
0x180013331  shl     ax, 2
0x180013335  mov     [rdx+4], ax
0x180013339  and     r8w, r13w; unsigned __int64
0x18001333d  mov     [rdx+6], r8w
0x180013342  add     rdx, 8
0x180013346  mov     eax, ecx
0x180013348  shr     eax, 0Fh
0x18001334b  test    al, 7Fh
0x18001334d  jz      short loc_180013371
0x18001334f  mov     [rdx], r10d
0x180013352  shr     ecx, 16h
0x180013355  and     cx, r15w
0x180013359  shl     cx, 2
0x18001335d  add     cx, r15w
0x180013361  mov     [rdx+4], cx
0x180013365  and     ax, 7Fh
0x180013369  mov     [rdx+6], ax
0x18001336d  add     rdx, 8
0x180013371  lea     rax, [rsp+0B8h+var_88]
0x180013376  sub     rdx, rax
0x180013379  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18001337d  test    rdx, rdx
0x180013380  jle     short loc_18001338D
0x180013382  lea     rcx, [rsp+0B8h+var_88]; this
0x180013387  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18001338c  nop
0x18001338d  add     rbx, 10h
0x180013391  jmp     loc_18001326F
0x180013396  mov     rax, [r14+20h]
0x18001339a  mov     [r14+28h], rax
0x18001339e  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1800133a5  test    rax, rax
0x1800133a8  jnz     short loc_1800133B6
0x1800133aa  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1800133b1  test    rax, rax
0x1800133b4  jz      short loc_1800133C9
0x1800133b6  xor     r9d, r9d
0x1800133b9  xor     r8d, r8d
0x1800133bc  mov     edx, 0FEh
0x1800133c1  xor     ecx, ecx
0x1800133c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133c8  nop
0x1800133c9  test    rbp, rbp
0x1800133cc  jz      short loc_1800133D7
0x1800133ce  mov     rcx, rbp; SRWLock
0x1800133d1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800133d7  test    rdi, rdi
0x1800133da  jz      short loc_180013414
0x1800133dc  call    cs:__imp_GetLastError
0x1800133e2  mov     ebx, eax
0x1800133e4  xor     r9d, r9d; msWindowLength
0x1800133e7  xor     r8d, r8d; msPeriod
0x1800133ea  xor     edx, edx; pftDueTime
0x1800133ec  mov     rcx, rdi; pti
0x1800133ef  call    cs:__imp_SetThreadpoolTimer
0x1800133f5  mov     edx, r15d; fCancelPendingCallbacks
0x1800133f8  mov     rcx, rdi; pti
0x1800133fb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180013401  mov     rcx, rdi; pti
0x180013404  call    cs:__imp_CloseThreadpoolTimer
0x18001340a  nop
0x18001340b  mov     ecx, ebx; dwErrCode
0x18001340d  call    cs:__imp_SetLastError
0x180013413  nop
0x180013414  mov     rcx, [rsp+0B8h+var_58]
0x180013419  xor     rcx, rsp; StackCookie
0x18001341c  call    __security_check_cookie
0x180013421  add     rsp, 78h
0x180013425  pop     r15
0x180013427  pop     r14
0x180013429  pop     r13
0x18001342b  pop     r12
0x18001342d  pop     rdi
0x18001342e  pop     rsi
0x18001342f  pop     rbp
0x180013430  pop     rbx
0x180013431  retn
```
