# CRWLock::AcquireReaderLock(void)

- ea: `0x1800041a0`
- end: `0x1800045e8`
- name: `?AcquireReaderLock@CRWLock@@QEAAJXZ`
- size: `1096`
- prototype: `__int64 __fastcall(CRWLock *__hidden this)`
- caller_count: `18`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180003090`
- `0x1800039a0`
- `0x180003d60`
- `0x180004dc0`
- `0x180004fe4`
- `0x1800055a0`
- `0x18000f270`
- `0x18000fa88`
- `0x1800581d4`
- `0x18006540c`
- `0x180065b30`
- `0x1800676b8`
- `0x180067e20`
- `0x180068130`
- `0x180068950`
- `0x18006c490`
- `0x18006c550`
- `0x18006c994`

## callees

- `0x1800041a0`
- `0x18000cddc`
- `0x18000d5f4`
- `0x18000d7ec`
- `0x180012b28`
- `0x18001d138`
- `0x18007ca98`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800043f0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800044fc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800043f0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800044fc`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180004405`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180004405`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000439e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000439e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800041c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800041d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004312`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800041c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800041d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004312`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000454f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000454f`

## string_xrefs

- `0x180004391`: `Failed to acquire reader lock`

## pseudocode

```c
__int64 __fastcall CRWLock::AcquireReaderLock(CRWLock *this)
{
  int v2; // edi
  DWORD CurrentThreadId; // r14d
  char *v4; // rdi
  void **v5; // rdx
  char *v6; // rsi
  __int64 v7; // rbp
  __int64 v8; // r15
  char *v9; // rcx
  __int64 v10; // r8
  signed int v11; // r14d
  __int64 v12; // r9
  unsigned __int32 v13; // ebp
  __int64 v14; // rdx
  CLockEntry *v15; // rbx
  unsigned int v16; // ebx
  signed int LastError; // eax
  unsigned int v19; // ecx
  signed __int32 v20; // ecx
  unsigned int v21; // r12d
  void *v22; // r13
  DWORD v23; // r15d
  void *ReaderEvent; // rax
  DWORD v25; // eax
  CLockEntry *v26; // rax
  void **v27; // [rsp+20h] [rbp-58h] BYREF
  __int64 v28; // [rsp+28h] [rbp-50h]
  __int64 v29; // [rsp+30h] [rbp-48h]
  char *v30; // [rsp+38h] [rbp-40h]
  __int64 v31; // [rsp+80h] [rbp+8h] BYREF
  CLockEntry *v32; // [rsp+88h] [rbp+10h]

  if ( (*((_BYTE *)this + 92) & 1) == 0 )
    (**(void (__fastcall ***)(CRWLock *))this)(this);
  v2 = *((_DWORD *)this + 21);
  if ( v2 == GetCurrentThreadId() )
    return (unsigned int)CRWLock::AcquireWriterLock(this);
  CurrentThreadId = GetCurrentThreadId();
  v4 = (char *)this + 8;
  (**((void (__fastcall ***)(char *))this + 1))((char *)this + 8);
  v5 = &UTStaticList2Iterator<CTimeoutTableRow *>::`vftable';
  v27 = &UTStaticList2Iterator<CTimeoutTableRow *>::`vftable';
  v6 = (char *)this + 96;
  v30 = (char *)this + 96;
  v29 = 0;
  v28 = *((_QWORD *)this + 14);
  v7 = 0;
  v28 = *((_QWORD *)this + 14);
  while ( ((unsigned int (__fastcall *)(void ***))v5[2])(&v27) )
  {
    v8 = ((__int64 (__fastcall *)(void ***))v27[1])(&v27);
    ((void (__fastcall *)(void ***, _QWORD))v27[3])(&v27, 0);
    if ( CurrentThreadId == *(_DWORD *)(v8 + 48) )
    {
      v7 = v8;
      break;
    }
    v5 = v27;
  }
  v27 = &UTStaticList2Iterator<CTimeoutTableRow *>::`vftable';
  v9 = (char *)this + 8;
  if ( v7 )
  {
    v16 = 0;
    ++*(_DWORD *)(v7 + 56);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v9);
    return v16;
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v9);
  v11 = 0;
  v12 = 0;
  LODWORD(v31) = 0;
  v13 = *((_DWORD *)this + 20);
  while ( 1 )
  {
    v14 = v13;
    if ( v13 < 0x3FF
      || (v10 = v13 & 0x3FF, (v13 & 0x1400) == 0x400) && (unsigned int)v10 + ((v13 >> 13) & 0x3FF) <= 0x3FD )
    {
      v13 = _InterlockedCompareExchange((volatile signed __int32 *)this + 20, v13 + 1, v13);
      if ( v13 == (_DWORD)v14 )
        goto LABEL_12;
      goto LABEL_19;
    }
    if ( (v13 & 0x7FE000) == 8380416 || (_DWORD)v10 == 1023 || (v13 & 0xC00) == 0x400 )
    {
      Sleep(0x3E8u);
      v12 = 0;
      LODWORD(v31) = 0;
LABEL_49:
      v13 = *((_DWORD *)this + 20);
      goto LABEL_19;
    }
    v12 = (unsigned int)(v12 + 1);
    LODWORD(v31) = v12;
    if ( (unsigned int)v12 <= gdwDefaultSpinCount )
      goto LABEL_49;
    v13 = _InterlockedCompareExchange((volatile signed __int32 *)this + 20, v13 + 0x2000, v13);
    if ( v13 == (_DWORD)v14 )
      break;
LABEL_19:
    if ( v11 == -2147417825 )
    {
      v11 = 0;
      DtcDebugBreak();
      v12 = (unsigned int)v31;
    }
    else if ( v11 < 0 )
    {
      goto LABEL_21;
    }
  }
  ReaderEvent = CRWLock::GetReaderEvent(this);
  v22 = ReaderEvent;
  if ( ReaderEvent )
  {
    v25 = WaitForSingleObject(ReaderEvent, 0xFFFFFFFF);
    v23 = v25;
    if ( !v25 )
    {
      v19 = -8191;
      goto LABEL_25;
    }
    if ( v25 == 258 )
    {
      v11 = -2147417825;
    }
    else
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    v23 = -1;
    v11 = -2147417855;
  }
  v19 = -8192;
LABEL_25:
  v20 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 20, v19);
  if ( (v20 & 0x7FE000) == 0x2000 && (v20 & 0x400) != 0 )
  {
    v21 = -1024;
    if ( v23 )
    {
      if ( !v22 )
        v22 = CRWLock::GetReaderEvent(this);
      v23 = WaitForSingleObject(v22, 0xFFFFFFFF);
      v21 = -1023;
      v11 = 0;
    }
    if ( !ResetEvent(v22) )
      DtcInternalErrorW(L"ResetEvent failed");
    _InterlockedAdd((volatile signed __int32 *)this + 20, v21);
  }
  if ( v23 )
  {
    v12 = (unsigned int)v31;
    goto LABEL_19;
  }
LABEL_12:
  if ( v11 < 0 )
LABEL_21:
    DtcInternalErrorW(L"Failed to acquire reader lock");
  v31 = 0;
  (**(void (__fastcall ***)(char *, __int64, __int64, __int64, void **, __int64, __int64, char *))v4)(
    (char *)this + 8,
    v14,
    v10,
    v12,
    v27,
    v28,
    v29,
    v30);
  if ( (*(unsigned int (__fastcall **)(char *, __int64 *))(*((_QWORD *)this + 16) + 40LL))((char *)this + 128, &v31) )
  {
    v15 = *(CLockEntry **)(v31 + 8);
    *((_DWORD *)v15 + 12) = GetCurrentThreadId();
    *(_QWORD *)((char *)v15 + 52) = 0;
  }
  else
  {
    v26 = (CLockEntry *)operator new(0x40u);
    v32 = v26;
    if ( v26 )
      v15 = CLockEntry::CLockEntry(v26);
    else
      v15 = 0;
  }
  if ( !v15 )
  {
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
    goto LABEL_21;
  }
  *((_DWORD *)v15 + 14) = 1;
  (*(void (__fastcall **)(char *, CLockEntry *))(*(_QWORD *)v6 + 8LL))(v6, v15);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
  return 0;
}

```

## disassembly

```asm
0x1800041a0  mov     [rsp+arg_10], rbx
0x1800041a5  push    rbp
0x1800041a6  push    rsi
0x1800041a7  push    rdi
0x1800041a8  push    r12
0x1800041aa  push    r13
0x1800041ac  push    r14
0x1800041ae  push    r15
0x1800041b0  sub     rsp, 40h
0x1800041b4  mov     rbx, rcx
0x1800041b7  test    byte ptr [rcx+5Ch], 1
0x1800041bb  jz      loc_180004431
0x1800041c1  mov     edi, [rbx+54h]
0x1800041c4  call    cs:__imp_GetCurrentThreadId
0x1800041ca  cmp     edi, eax
0x1800041cc  jz      loc_180004441
0x1800041d2  call    cs:__imp_GetCurrentThreadId
0x1800041d8  mov     r14d, eax
0x1800041db  lea     rdi, [rbx+8]
0x1800041df  mov     rcx, [rdi]
0x1800041e2  mov     rax, [rcx]
0x1800041e5  mov     rcx, rdi
0x1800041e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041ed  lea     r12, ??_7?$UTStaticList2Iterator@PEAVCTimeoutTableRow@@@@6B@; const UTStaticList2Iterator<CTimeoutTableRow *>::`vftable'
0x1800041f4  mov     rdx, r12
0x1800041f7  mov     [rsp+78h+var_58], rdx
0x1800041fc  lea     rsi, [rbx+60h]
0x180004200  mov     [rsp+78h+var_40], rsi
0x180004205  xor     r15d, r15d
0x180004208  mov     [rsp+78h+var_48], r15
0x18000420d  mov     rax, [rsi+10h]
0x180004211  mov     [rsp+78h+var_50], rax
0x180004216  mov     ebp, r15d
0x180004219  mov     [rsp+78h+var_48], r15
0x18000421e  mov     rax, [rsi+10h]
0x180004222  mov     [rsp+78h+var_50], rax
0x180004227  lea     rcx, [rsp+78h+var_58]
0x18000422c  mov     rax, [rdx+10h]
0x180004230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004235  test    eax, eax
0x180004237  jz      short loc_180004271
0x180004239  mov     rax, [rsp+78h+var_58]
0x18000423e  lea     rcx, [rsp+78h+var_58]
0x180004243  mov     rax, [rax+8]
0x180004247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000424c  mov     r15, rax
0x18000424f  mov     rcx, [rsp+78h+var_58]
0x180004254  mov     rax, [rcx+18h]
0x180004258  xor     edx, edx
0x18000425a  lea     rcx, [rsp+78h+var_58]
0x18000425f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004264  cmp     r14d, [r15+30h]
0x180004268  jnz     loc_180004371
0x18000426e  mov     rbp, r15
0x180004271  mov     [rsp+78h+var_58], r12
0x180004276  mov     rcx, rdi
0x180004279  test    rbp, rbp
0x18000427c  jnz     loc_1800045D2
0x180004282  mov     rax, [rdi]
0x180004285  mov     rax, [rax+8]
0x180004289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000428e  xor     r15d, r15d
0x180004291  mov     r14d, r15d
0x180004294  mov     r9d, r15d
0x180004297  mov     dword ptr [rsp+78h+arg_0], r15d
0x18000429f  mov     ebp, [rbx+50h]
0x1800042a2  mov     edx, ebp
0x1800042a4  cmp     ebp, 3FFh
0x1800042aa  jnb     loc_180004450
0x1800042b0  lea     ecx, [rbp+1]
0x1800042b3  mov     eax, ebp
0x1800042b5  lock cmpxchg [rbx+50h], ecx
0x1800042ba  mov     ebp, eax
0x1800042bc  cmp     eax, edx
0x1800042be  jnz     loc_18000437B
0x1800042c4  test    r14d, r14d
0x1800042c7  js      loc_180004391
0x1800042cd  mov     [rsp+78h+arg_0], r15
0x1800042d5  mov     rax, [rdi]
0x1800042d8  mov     rcx, rdi
0x1800042db  mov     rax, [rax]
0x1800042de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042e3  lea     rcx, [rbx+80h]
0x1800042ea  mov     rax, [rcx]
0x1800042ed  lea     rdx, [rsp+78h+arg_0]
0x1800042f5  mov     rax, [rax+28h]
0x1800042f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042fe  test    eax, eax
0x180004300  jz      loc_180004592
0x180004306  mov     rax, [rsp+78h+arg_0]
0x18000430e  mov     rbx, [rax+8]
0x180004312  call    cs:__imp_GetCurrentThreadId
0x180004318  mov     [rbx+30h], eax
0x18000431b  mov     qword ptr [rbx+34h], 0
0x180004323  test    rbx, rbx
0x180004326  jz      loc_1800045BE
0x18000432c  mov     dword ptr [rbx+38h], 1
0x180004333  mov     rax, [rsi]
0x180004336  mov     rdx, rbx
0x180004339  mov     rcx, rsi
0x18000433c  mov     rax, [rax+8]
0x180004340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004345  mov     rax, [rdi]
0x180004348  mov     rcx, rdi
0x18000434b  mov     rax, [rax+8]
0x18000434f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004354  mov     ebx, r15d
0x180004357  mov     eax, ebx
0x180004359  mov     rbx, [rsp+78h+arg_10]
0x180004361  add     rsp, 40h
0x180004365  pop     r15
0x180004367  pop     r14
0x180004369  pop     r13
0x18000436b  pop     r12
0x18000436d  pop     rdi
0x18000436e  pop     rsi
0x18000436f  pop     rbp
0x180004370  retn
0x180004371  mov     rdx, [rsp+78h+var_58]
0x180004376  jmp     loc_180004227
0x18000437b  cmp     r14d, 8001011Fh
0x180004382  jz      loc_180004568
0x180004388  test    r14d, r14d
0x18000438b  jns     loc_1800042A2
0x180004391  lea     rcx, aFailedToAcquir; "Failed to acquire reader lock"
0x180004398  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18000439e  call    cs:__imp_GetLastError
0x1800043a4  mov     r14d, eax
0x1800043a7  test    eax, eax
0x1800043a9  jg      loc_180004529
0x1800043af  mov     ecx, 0FFFFE000h
0x1800043b4  lock xadd [rbx+50h], ecx
0x1800043b9  mov     eax, ecx
0x1800043bb  and     eax, 7FE000h
0x1800043c0  cmp     eax, 2000h
0x1800043c5  jnz     short loc_180004418
0x1800043c7  bt      ecx, 0Ah
0x1800043cb  jnb     short loc_180004418
0x1800043cd  mov     r12d, 0FFFFFC00h
0x1800043d3  test    r15d, r15d
0x1800043d6  jz      short loc_180004402
0x1800043d8  test    r13, r13
0x1800043db  jnz     short loc_1800043E8
0x1800043dd  mov     rcx, rbx; this
0x1800043e0  call    ?GetReaderEvent@CRWLock@@AEAAPEAXXZ; CRWLock::GetReaderEvent(void)
0x1800043e5  mov     r13, rax
0x1800043e8  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1800043ed  mov     rcx, r13; hHandle
0x1800043f0  call    cs:__imp_WaitForSingleObject
0x1800043f6  mov     r15d, eax
0x1800043f9  mov     r12d, 0FFFFFC01h
0x1800043ff  xor     r14d, r14d
0x180004402  mov     rcx, r13; hEvent
0x180004405  call    cs:__imp_ResetEvent
0x18000440b  test    eax, eax
0x18000440d  jz      loc_18000457D
0x180004413  lock add [rbx+50h], r12d
0x180004418  test    r15d, r15d
0x18000441b  jz      loc_18000458A
0x180004421  mov     r9d, dword ptr [rsp+78h+arg_0]
0x180004429  xor     r15d, r15d
0x18000442c  jmp     loc_18000437B
0x180004431  mov     rax, [rcx]
0x180004434  mov     rax, [rax]
0x180004437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000443c  jmp     loc_1800041C1
0x180004441  mov     rcx, rbx; this
0x180004444  call    ?AcquireWriterLock@CRWLock@@QEAAJXZ; CRWLock::AcquireWriterLock(void)
0x180004449  mov     ebx, eax
0x18000444b  jmp     loc_180004357
0x180004450  mov     r8d, ebp
0x180004453  and     r8d, 3FFh
0x18000445a  mov     eax, ebp
0x18000445c  and     eax, 1400h
0x180004461  cmp     eax, 400h
0x180004466  jnz     short loc_180004480
0x180004468  mov     eax, ebp
0x18000446a  shr     eax, 0Dh
0x18000446d  and     eax, 3FFh
0x180004472  add     eax, r8d
0x180004475  cmp     eax, 3FDh
0x18000447a  jbe     loc_1800042B0
0x180004480  mov     eax, ebp
0x180004482  and     eax, 7FE000h
0x180004487  cmp     eax, 7FE000h
0x18000448c  setnz   cl
0x18000448f  cmp     r8d, 3FFh
0x180004496  setnz   al
0x180004499  test    al, cl
0x18000449b  jz      loc_18000454A
0x1800044a1  mov     ecx, ebp
0x1800044a3  and     ecx, 0C00h
0x1800044a9  cmp     ecx, 400h
0x1800044af  jz      loc_18000454A
0x1800044b5  inc     r9d
0x1800044b8  mov     dword ptr [rsp+78h+arg_0], r9d
0x1800044c0  cmp     r9d, cs:?gdwDefaultSpinCount@@3KA; ulong gdwDefaultSpinCount
0x1800044c7  jbe     loc_180004560
0x1800044cd  lea     ecx, [rbp+2000h]
0x1800044d3  mov     eax, ebp
0x1800044d5  lock cmpxchg [rbx+50h], ecx
0x1800044da  mov     ebp, eax
0x1800044dc  cmp     eax, edx
0x1800044de  jnz     loc_18000437B
0x1800044e4  mov     rcx, rbx; this
0x1800044e7  call    ?GetReaderEvent@CRWLock@@AEAAPEAXXZ; CRWLock::GetReaderEvent(void)
0x1800044ec  mov     r13, rax
0x1800044ef  test    rax, rax
0x1800044f2  jz      short loc_180004539
0x1800044f4  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1800044f9  mov     rcx, rax; hHandle
0x1800044fc  call    cs:__imp_WaitForSingleObject
0x180004502  mov     r15d, eax
0x180004505  test    eax, eax
0x180004507  jnz     short loc_180004513
0x180004509  mov     ecx, 0FFFFE001h
0x18000450e  jmp     loc_1800043B4
0x180004513  cmp     eax, 102h
0x180004518  jnz     loc_18000439E
0x18000451e  mov     r14d, 8001011Fh
0x180004524  jmp     loc_1800043AF
0x180004529  movzx   r14d, ax
0x18000452d  or      r14d, 80070000h
0x180004534  jmp     loc_1800043AF
0x180004539  mov     r15d, 0FFFFFFFFh
0x18000453f  mov     r14d, 80010101h
0x180004545  jmp     loc_1800043AF
0x18000454a  mov     ecx, 3E8h; dwMilliseconds
0x18000454f  call    cs:__imp_Sleep
0x180004555  mov     r9d, r15d
0x180004558  mov     dword ptr [rsp+78h+arg_0], r15d
0x180004560  mov     ebp, [rbx+50h]
0x180004563  jmp     loc_18000437B
0x180004568  mov     r14d, r15d
0x18000456b  call    ?DtcDebugBreak@@YAXXZ; DtcDebugBreak(void)
0x180004570  mov     r9d, dword ptr [rsp+78h+arg_0]
0x180004578  jmp     loc_1800042A2
0x18000457d  lea     rcx, aReseteventFail; "ResetEvent failed"
0x180004584  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18000458a  xor     r15d, r15d
0x18000458d  jmp     loc_1800042C4
0x180004592  mov     ecx, 40h ; '@'; Size
0x180004597  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000459c  mov     [rsp+78h+arg_8], rax
0x1800045a4  test    rax, rax
0x1800045a7  jz      short loc_1800045B6
0x1800045a9  mov     rcx, rax; this
0x1800045ac  call    ??0CLockEntry@@QEAA@XZ; CLockEntry::CLockEntry(void)
0x1800045b1  mov     rbx, rax
0x1800045b4  jmp     short loc_1800045B9
0x1800045b6  mov     rbx, r15
0x1800045b9  jmp     loc_180004323
0x1800045be  mov     rax, [rdi]
0x1800045c1  mov     rcx, rdi
0x1800045c4  mov     rax, [rax+8]
0x1800045c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045cd  jmp     loc_180004391
0x1800045d2  xor     ebx, ebx
0x1800045d4  inc     dword ptr [rbp+38h]
0x1800045d7  mov     rax, [rdi]
0x1800045da  mov     rax, [rax+8]
0x1800045de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045e3  jmp     loc_180004357
```
