# Mpeg2DemuxAttributes::TCProducerConsumer<Mpeg2DemuxAttributes::CDemuxIMediaSample *>::Pop(Mpeg2DemuxAttributes::CDemuxIMediaSample * *)

- ea: `0x180019294`
- end: `0x18001944b`
- name: `?Pop@?$TCProducerConsumer@PEAVCDemuxIMediaSample@Mpeg2DemuxAttributes@@@Mpeg2DemuxAttributes@@QEAAKPEAPEAVCDemuxIMediaSample@2@@Z`
- size: `439`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001818c`
- `0x180018c74`

## callees

- `0x180001008`
- `0x180001048`
- `0x180019294`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1800193cc`
- `KERNEL32!WaitForSingleObject` at `0x1800193cc`
- `KERNEL32!ResetEvent` at `0x180019358`
- `KERNEL32!ResetEvent` at `0x180019358`
- `KERNEL32!CreateEventW` at `0x18001937c`
- `KERNEL32!CreateEventW` at `0x18001937c`
- `KERNEL32!LeaveCriticalSection` at `0x1800193c0`
- `KERNEL32!LeaveCriticalSection` at `0x180019434`
- `KERNEL32!LeaveCriticalSection` at `0x1800193c0`
- `KERNEL32!LeaveCriticalSection` at `0x180019434`
- `KERNEL32!EnterCriticalSection` at `0x1800192b0`
- `KERNEL32!EnterCriticalSection` at `0x1800193d9`
- `KERNEL32!EnterCriticalSection` at `0x1800193f5`
- `KERNEL32!EnterCriticalSection` at `0x1800192b0`
- `KERNEL32!EnterCriticalSection` at `0x1800193d9`
- `KERNEL32!EnterCriticalSection` at `0x1800193f5`

## pseudocode

```c
__int64 __fastcall Mpeg2DemuxAttributes::TCProducerConsumer<Mpeg2DemuxAttributes::CDemuxIMediaSample *>::Pop(
        LPCRITICAL_SECTION lpCriticalSection,
        _QWORD *a2)
{
  struct _RTL_CRITICAL_SECTION_DEBUG *SpinCount; // rcx
  __int64 v5; // r8
  struct _RTL_CRITICAL_SECTION *CriticalSection; // rax
  DWORD *p_Flags; // r8
  int DebugInfo; // eax
  PRTL_CRITICAL_SECTION_DEBUG v9; // rax
  unsigned int v10; // edi
  HANDLE *p_OwningThread; // r14
  HANDLE *OwningThread; // rsi
  HANDLE *v13; // rax
  _QWORD *v14; // rcx
  HANDLE *v15; // rsi
  HANDLE EventW; // rax
  _QWORD *v17; // rax
  HANDLE *v18; // r15
  _QWORD *v19; // rax

  *a2 = 0;
  EnterCriticalSection(lpCriticalSection);
  SpinCount = (struct _RTL_CRITICAL_SECTION_DEBUG *)lpCriticalSection[1].SpinCount;
  if ( SpinCount != (struct _RTL_CRITICAL_SECTION_DEBUG *)&lpCriticalSection[1].SpinCount )
  {
    v5 = *(_QWORD *)&SpinCount->Type;
    CriticalSection = SpinCount->CriticalSection;
    CriticalSection->DebugInfo = *(PRTL_CRITICAL_SECTION_DEBUG *)&SpinCount->Type;
    *(_QWORD *)(v5 + 8) = CriticalSection;
    p_Flags = &SpinCount[-1].Flags;
    if ( SpinCount != (struct _RTL_CRITICAL_SECTION_DEBUG *)8 )
    {
      --LODWORD(lpCriticalSection[2].SpinCount);
      *a2 = *(_QWORD *)p_Flags;
      DebugInfo = (int)lpCriticalSection[3].DebugInfo;
      if ( DebugInfo >= SHIDWORD(lpCriticalSection[2].SpinCount) )
      {
        operator delete(&SpinCount[-1].Flags, 0x18u);
      }
      else
      {
        LODWORD(lpCriticalSection[3].DebugInfo) = DebugInfo + 1;
        v9 = lpCriticalSection[1].DebugInfo;
        *(_QWORD *)&SpinCount->Type = v9;
        *((_QWORD *)p_Flags + 2) = lpCriticalSection + 1;
        v9->CriticalSection = (struct _RTL_CRITICAL_SECTION *)SpinCount;
        lpCriticalSection[1].DebugInfo = SpinCount;
      }
      v10 = 0;
      goto LABEL_23;
    }
  }
  if ( !LODWORD(lpCriticalSection[2].LockSemaphore) )
    goto LABEL_22;
  p_OwningThread = &lpCriticalSection[1].OwningThread;
  OwningThread = (HANDLE *)lpCriticalSection[1].OwningThread;
  if ( OwningThread == &lpCriticalSection[1].OwningThread
    || (v13 = (HANDLE *)OwningThread[1],
        v14 = *OwningThread,
        *v13 = *OwningThread,
        v14[1] = v13,
        (v15 = OwningThread - 3) == 0) )
  {
    v15 = (HANDLE *)operator new(0x28u);
    if ( v15 )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      *v15 = EventW;
      if ( !EventW )
      {
        operator delete(v15, 0x28u);
        v15 = 0;
      }
    }
    if ( v15 )
      goto LABEL_15;
LABEL_22:
    v10 = 31;
    goto LABEL_23;
  }
  --lpCriticalSection[3].LockCount;
  ResetEvent(*v15);
LABEL_15:
  v17 = lpCriticalSection[2].OwningThread;
  v18 = v15 + 3;
  v15[3] = &lpCriticalSection[2].LockCount;
  v15[4] = v17;
  *v17 = v15 + 3;
  ++HIDWORD(lpCriticalSection[2].LockSemaphore);
  lpCriticalSection[2].OwningThread = v15 + 3;
  LeaveCriticalSection(lpCriticalSection);
  if ( WaitForSingleObject(*v15, 0xFFFFFFFF) )
  {
    v10 = 31;
    EnterCriticalSection(lpCriticalSection);
  }
  else
  {
    EnterCriticalSection(lpCriticalSection);
    v10 = *((_DWORD *)v15 + 2);
    if ( !v10 )
      *a2 = v15[2];
  }
  if ( lpCriticalSection[3].LockCount >= SHIDWORD(lpCriticalSection[3].DebugInfo) )
  {
    operator delete(v15, 0x28u);
  }
  else
  {
    v19 = *p_OwningThread;
    *v18 = *p_OwningThread;
    v15[4] = p_OwningThread;
    v19[1] = v18;
    ++lpCriticalSection[3].LockCount;
    *p_OwningThread = v18;
  }
LABEL_23:
  LeaveCriticalSection(lpCriticalSection);
  return v10;
}

```

## disassembly

```asm
0x180019294  push    rbx
0x180019296  push    rbp
0x180019297  push    rsi
0x180019298  push    rdi
0x180019299  push    r12
0x18001929b  push    r14
0x18001929d  push    r15
0x18001929f  sub     rsp, 20h
0x1800192a3  mov     rbp, rdx
0x1800192a6  mov     qword ptr [rdx], 0
0x1800192ad  mov     rbx, rcx
0x1800192b0  call    cs:__imp_EnterCriticalSection
0x1800192b6  lea     rax, [rbx+48h]
0x1800192ba  mov     rcx, [rax]
0x1800192bd  cmp     rcx, rax
0x1800192c0  jz      short loc_18001931F
0x1800192c2  mov     r8, [rcx]
0x1800192c5  mov     rax, [rcx+8]
0x1800192c9  mov     [rax], r8
0x1800192cc  mov     [r8+8], rax
0x1800192d0  lea     r8, [rcx-8]
0x1800192d4  test    r8, r8
0x1800192d7  jz      short loc_18001931F
0x1800192d9  dec     dword ptr [rbx+70h]
0x1800192dc  mov     rax, [r8]
0x1800192df  mov     [rbp+0], rax
0x1800192e3  mov     eax, [rbx+78h]
0x1800192e6  cmp     eax, [rbx+74h]
0x1800192e9  jge     short loc_18001930B
0x1800192eb  lea     rdx, [rbx+28h]
0x1800192ef  inc     eax
0x1800192f1  mov     [rbx+78h], eax
0x1800192f4  lea     rcx, [r8+8]
0x1800192f8  mov     rax, [rdx]
0x1800192fb  mov     [rcx], rax
0x1800192fe  mov     [r8+10h], rdx
0x180019302  mov     [rax+8], rcx
0x180019306  mov     [rdx], rcx
0x180019309  jmp     short loc_180019318
0x18001930b  mov     edx, 18h; unsigned __int64
0x180019310  mov     rcx, r8; void *
0x180019313  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180019318  xor     edi, edi
0x18001931a  jmp     loc_180019431
0x18001931f  cmp     dword ptr [rbx+68h], 0
0x180019323  jz      loc_18001942C
0x180019329  lea     r14, [rbx+38h]
0x18001932d  mov     r12d, 28h ; '('
0x180019333  mov     rsi, [r14]
0x180019336  cmp     rsi, r14
0x180019339  jz      short loc_180019360
0x18001933b  mov     rax, [rsi+8]
0x18001933f  mov     rcx, [rsi]
0x180019342  mov     [rax], rcx
0x180019345  mov     [rcx+8], rax
0x180019349  add     rsi, 0FFFFFFFFFFFFFFE8h
0x18001934d  jz      short loc_180019360
0x18001934f  dec     dword ptr [rbx+80h]
0x180019355  mov     rcx, [rsi]; hEvent
0x180019358  call    cs:__imp_ResetEvent
0x18001935e  jmp     short loc_1800193A0
0x180019360  mov     rcx, r12; Size
0x180019363  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019368  mov     rsi, rax
0x18001936b  test    rax, rax
0x18001936e  jz      short loc_180019397
0x180019370  xor     r9d, r9d; lpName
0x180019373  xor     r8d, r8d; bInitialState
0x180019376  xor     ecx, ecx; lpEventAttributes
0x180019378  lea     edx, [r9+1]; bManualReset
0x18001937c  call    cs:__imp_CreateEventW
0x180019382  mov     [rsi], rax
0x180019385  test    rax, rax
0x180019388  jnz     short loc_180019397
0x18001938a  mov     rdx, r12; unsigned __int64
0x18001938d  mov     rcx, rsi; void *
0x180019390  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180019395  xor     esi, esi
0x180019397  test    rsi, rsi
0x18001939a  jz      loc_18001942C
0x1800193a0  lea     rcx, [rbx+58h]
0x1800193a4  mov     rax, [rcx+8]
0x1800193a8  lea     r15, [rsi+18h]
0x1800193ac  mov     [r15], rcx
0x1800193af  mov     [rsi+20h], rax
0x1800193b3  mov     [rax], r15
0x1800193b6  inc     dword ptr [rbx+6Ch]
0x1800193b9  mov     [rcx+8], r15
0x1800193bd  mov     rcx, rbx; lpCriticalSection
0x1800193c0  call    cs:__imp_LeaveCriticalSection
0x1800193c6  mov     rcx, [rsi]; hHandle
0x1800193c9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800193cc  call    cs:__imp_WaitForSingleObject
0x1800193d2  mov     rcx, rbx; lpCriticalSection
0x1800193d5  test    eax, eax
0x1800193d7  jnz     short loc_1800193F0
0x1800193d9  call    cs:__imp_EnterCriticalSection
0x1800193df  mov     edi, [rsi+8]
0x1800193e2  test    edi, edi
0x1800193e4  jnz     short loc_1800193FB
0x1800193e6  mov     rax, [rsi+10h]
0x1800193ea  mov     [rbp+0], rax
0x1800193ee  jmp     short loc_1800193FB
0x1800193f0  mov     edi, 1Fh
0x1800193f5  call    cs:__imp_EnterCriticalSection
0x1800193fb  mov     eax, [rbx+7Ch]
0x1800193fe  cmp     [rbx+80h], eax
0x180019404  jge     short loc_18001941F
0x180019406  mov     rax, [r14]
0x180019409  mov     [r15], rax
0x18001940c  mov     [rsi+20h], r14
0x180019410  mov     [rax+8], r15
0x180019414  inc     dword ptr [rbx+80h]
0x18001941a  mov     [r14], r15
0x18001941d  jmp     short loc_180019431
0x18001941f  mov     rdx, r12; unsigned __int64
0x180019422  mov     rcx, rsi; void *
0x180019425  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001942a  jmp     short loc_180019431
0x18001942c  mov     edi, 1Fh
0x180019431  mov     rcx, rbx; lpCriticalSection
0x180019434  call    cs:__imp_LeaveCriticalSection
0x18001943a  mov     eax, edi
0x18001943c  add     rsp, 20h
0x180019440  pop     r15
0x180019442  pop     r14
0x180019444  pop     r12
0x180019446  pop     rdi
0x180019447  pop     rsi
0x180019448  pop     rbp
0x180019449  pop     rbx
0x18001944a  retn
```
