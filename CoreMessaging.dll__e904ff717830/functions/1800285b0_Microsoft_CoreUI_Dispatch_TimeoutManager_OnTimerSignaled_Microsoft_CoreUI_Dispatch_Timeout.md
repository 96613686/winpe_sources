# Microsoft::CoreUI::Dispatch::TimeoutManager::OnTimerSignaled(Microsoft::CoreUI::Dispatch::Timeout *)

- ea: `0x1800285b0`
- end: `0x180028a15`
- name: `?OnTimerSignaled@TimeoutManager@Dispatch@CoreUI@Microsoft@@QEAAXPEAVTimeout@234@@Z`
- size: `1125`
- prototype: `void __fastcall(Microsoft::CoreUI::Dispatch::TimeoutManager *__hidden this, struct Microsoft::CoreUI::Dispatch::Timeout *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180028360`

## callees

- `0x18000b130`
- `0x18000ec10`
- `0x180010ed0`
- `0x1800285b0`
- `0x180028a1c`
- `0x180028a60`
- `0x180028b74`
- `0x180028c34`
- `0x180028cb0`
- `0x18008ae1c`
- `0x18008f584`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18002864a`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18002864a`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180028617`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180028617`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180028722`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180028722`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Microsoft::CoreUI::Dispatch::TimeoutManager::OnTimerSignaled(
        Microsoft::CoreUI::Dispatch::TimeoutManager *this,
        struct Microsoft::CoreUI::Dispatch::Timeout *a2)
{
  char v4; // bl
  HANDLE WaitableTimer; // rax
  System::Object *v6; // rsi
  BOOL fResume; // ecx
  __int64 v8; // rcx
  unsigned int *i; // r15
  int v10; // eax
  unsigned __int64 v11; // rcx
  int v12; // r12d
  __int64 v13; // r12
  const char16_t *v14; // rcx
  System::Object *QuadPart; // rbx
  int v16; // edx
  int v17; // ecx
  __int64 v18; // r14
  unsigned int *v19; // rdi
  System::Object *v20; // rcx
  System::Object *v21; // rbx
  __int64 v22; // rdx
  const char16_t *v23; // rcx
  __int64 v24; // rdx
  int v25; // eax
  System::Object *v26; // rcx
  int v27; // eax
  System::Object *v28; // rcx
  __int64 v29; // rax
  System::Object *v30; // rcx
  int j; // edi
  int v32; // eax
  __int64 v33; // rax
  const char16_t *v34; // rcx
  System::Object *v35; // rsi
  struct System::Object *v36; // r15
  int v37; // eax
  int LowPart; // eax
  int v39; // eax
  System::Object *v40; // rcx
  System::Object *v41; // rax
  int v42; // ecx
  System::Object *v43; // rcx
  int v44; // eax
  LARGE_INTEGER DueTime; // [rsp+98h] [rbp+48h] BYREF
  int v46; // [rsp+A0h] [rbp+50h]
  System::Object *v47; // [rsp+A8h] [rbp+58h] BYREF

  v4 = *((_BYTE *)a2 + 97);
  WaitableTimer = (HANDLE)*((_QWORD *)a2 + 7);
  v6 = 0;
  if ( !WaitableTimer )
  {
    WaitableTimer = CreateWaitableTimerExW(0, 0, 1u, 0x1F0003u);
    if ( !WaitableTimer )
      Cn::FailFast::ForWin32();
    *((_QWORD *)a2 + 7) = WaitableTimer;
  }
  DueTime.QuadPart = 0x7FFFFFFFFFFFFFFFLL;
  if ( v4 )
  {
    DueTime.QuadPart = 0x8000000000000001uLL;
    fResume = 0;
  }
  else
  {
    fResume = 1;
  }
  if ( !SetWaitableTimer(WaitableTimer, &DueTime, 0, 0, 0, fResume) )
    Cn::FailFast::ForWin32();
  v8 = *(_QWORD *)(*((_QWORD *)this + 9) + 32LL);
  if ( !*(_DWORD *)(v8 + 24) )
    CFlat::Abandonment::Fail((const char16_t *)v8);
  if ( !*(_QWORD *)(v8 + 32) )
    Microsoft::CoreUI::Dispatch::DispatchItem::Activate(this, 11);
  if ( !*((_BYTE *)a2 + 96) )
    CFlat::Abandonment::Fail((const char16_t *)v8);
  if ( *((_BYTE *)a2 + 97) )
  {
    v16 = *((_DWORD *)this + 20);
    v17 = 1;
    if ( v16 != -1 )
      v17 = v16 + 1;
    *((_DWORD *)this + 20) = v17;
    *((_BYTE *)a2 + 96) = 1;
    *((_DWORD *)a2 + 16) = v16;
    DueTime.QuadPart = 0;
    GetSystemTimeAsFileTime((LPFILETIME)&DueTime);
    *((_QWORD *)a2 + 9) = (DueTime.QuadPart + 504911232000000000LL) | 0x4000000000000000LL;
  }
  v18 = *((_QWORD *)this + 9);
  if ( v18 )
    ++*(_DWORD *)(v18 + 16);
  v46 = Microsoft::CoreUI::Support::SkipList::ChooseNodeHeight((Microsoft::CoreUI::Support::SkipList *)v18);
  v19 = *(unsigned int **)(v18 + 32);
  if ( v19 )
  {
    v11 = v19[4];
    if ( (int)v11 > 0 )
    {
      v11 = (unsigned int)(v11 + 1);
      v19[4] = v11;
    }
  }
  v12 = *(_DWORD *)(v18 + 64) - 1;
  for ( i = v19; v12 >= 0; --v12 )
  {
    if ( v12 >= i[6] )
      CFlat::Abandonment::Fail((const char16_t *)v11);
    CFlat::Cast::Checked<CFlat::SmartPtr<CFlat::Array$2<CFlat::SmartPtr<System::Object>,1>>,CFlat::SmartPtr<System::Object> &>(
      &v47,
      &i[2 * v12 + 8]);
    v21 = v47;
    if ( v47 != v6 )
    {
      while ( v21 )
      {
        v23 = (const char16_t *)*((int *)v21 + 6);
        if ( (unsigned int)((_DWORD)v23 - 1) >= *((_DWORD *)v21 + 6) )
          CFlat::Abandonment::Fail(v23);
        v36 = (struct System::Object *)*((_QWORD *)v21 + (_QWORD)v23 + 3);
        DueTime.QuadPart = (LONGLONG)v36;
        if ( v36 )
        {
          v37 = *((_DWORD *)v36 + 4);
          if ( v37 > 0 )
            *((_DWORD *)v36 + 4) = v37 + 1;
        }
        LowPart = Microsoft::CoreUI::Support::SkipList::CompareValues(
                    (Microsoft::CoreUI::Support::SkipList *)v18,
                    v36,
                    a2);
        DueTime.LowPart = LowPart;
        if ( v36 )
        {
          System::Object::Release$(v36);
          LowPart = DueTime.LowPart;
        }
        if ( LowPart >= 1 )
        {
          v44 = *((_DWORD *)v21 + 4);
          if ( v44 > 0 )
            *((_DWORD *)v21 + 4) = v44 + 1;
          break;
        }
        v39 = *((_DWORD *)v21 + 4);
        if ( v39 > 0 )
          *((_DWORD *)v21 + 4) = v39 + 1;
        v40 = (System::Object *)v19;
        v19 = (unsigned int *)v21;
        if ( v40 )
          System::Object::Release$(v40);
        if ( (unsigned int)v12 >= *((_DWORD *)v21 + 6) )
          CFlat::Abandonment::Fail((const char16_t *)v40);
        v41 = (System::Object *)CFlat::Cast::Checked<CFlat::Array$2<CFlat::SmartPtr<System::Object>,1> *,CFlat::SmartPtr<System::Object> &>((char *)v21 + 8 * v12 + 32);
        if ( v41 )
        {
          v42 = *((_DWORD *)v41 + 4);
          if ( v42 > 0 )
            *((_DWORD *)v41 + 4) = v42 + 1;
        }
        v43 = v21;
        v21 = v41;
        v47 = v41;
        System::Object::Release$(v43);
      }
      v20 = v6;
      v6 = v21;
      if ( v20 )
        System::Object::Release$(v20);
    }
    v22 = *(_QWORD *)(v18 + 40);
    if ( (unsigned int)v12 >= *(_DWORD *)(v22 + 24) )
      CFlat::Abandonment::Fail((const char16_t *)v20);
    i = v19;
    if ( v19 )
    {
      v10 = v19[4];
      if ( v10 > 0 )
        v19[4] = v10 + 1;
    }
    v11 = *(_QWORD *)(v22 + 8LL * v12 + 32);
    *(_QWORD *)(v22 + 8LL * v12 + 32) = v19;
    if ( v11 )
      System::Object::Release$((System::Object *)v11);
    if ( v21 )
      System::Object::Release$(v21);
  }
  if ( v6 )
    System::Object::Release$(v6);
  if ( i )
    System::Object::Release$((System::Object *)v19);
  v13 = v46;
  CFlat::Array$2<CFlat::SmartPtr<System::Object>,1>::Create(&DueTime, (unsigned int)(v46 + 1));
  QuadPart = (System::Object *)DueTime.QuadPart;
  if ( (unsigned int)v13 >= *(_DWORD *)(DueTime.QuadPart + 24) )
    CFlat::Abandonment::Fail(v14);
  v32 = *((_DWORD *)a2 + 4);
  if ( v32 > 0 )
    *((_DWORD *)a2 + 4) = v32 + 1;
  v30 = (System::Object *)*((_QWORD *)QuadPart + v13 + 4);
  *((_QWORD *)QuadPart + v13 + 4) = a2;
  if ( v30 )
    System::Object::Release$(v30);
  for ( j = 0; j < (int)v13; ++j )
  {
    v33 = *(_QWORD *)(v18 + 40);
    if ( (unsigned int)j >= *(_DWORD *)(v33 + 24) )
      CFlat::Abandonment::Fail((const char16_t *)v30);
    CFlat::Cast::Checked<CFlat::SmartPtr<CFlat::Array$2<CFlat::SmartPtr<System::Object>,1>>,CFlat::SmartPtr<System::Object> &>(
      &DueTime,
      v33 + 32 + 8LL * j);
    v35 = (System::Object *)DueTime.QuadPart;
    if ( (unsigned int)j >= *(_DWORD *)(DueTime.QuadPart + 24) )
      CFlat::Abandonment::Fail(v34);
    if ( (unsigned int)j >= *((_DWORD *)QuadPart + 6) )
      CFlat::Abandonment::Fail(v34);
    v24 = *(_QWORD *)(DueTime.QuadPart + 8LL * j + 32);
    if ( v24 )
    {
      v25 = *(_DWORD *)(v24 + 16);
      if ( v25 > 0 )
        *(_DWORD *)(v24 + 16) = v25 + 1;
    }
    v26 = (System::Object *)*((_QWORD *)QuadPart + j + 4);
    *((_QWORD *)QuadPart + j + 4) = v24;
    if ( v26 )
      System::Object::Release$(v26);
    if ( (unsigned int)j >= *((_DWORD *)v35 + 6) )
      CFlat::Abandonment::Fail((const char16_t *)v26);
    v27 = *((_DWORD *)QuadPart + 4);
    if ( v27 > 0 )
      *((_DWORD *)QuadPart + 4) = v27 + 1;
    v28 = (System::Object *)*((_QWORD *)v35 + j + 4);
    *((_QWORD *)v35 + j + 4) = QuadPart;
    if ( v28 )
      System::Object::Release$(v28);
    v29 = *(_QWORD *)(v18 + 40);
    if ( (unsigned int)j >= *(_DWORD *)(v29 + 24) )
      CFlat::Abandonment::Fail((const char16_t *)v28);
    v30 = *(System::Object **)(v29 + 8LL * j + 32);
    *(_QWORD *)(v29 + 8LL * j + 32) = 0;
    if ( v30 )
      System::Object::Release$(v30);
    if ( v35 )
      System::Object::Release$(v35);
  }
  ++*(_DWORD *)(v18 + 68);
  if ( QuadPart )
    System::Object::Release$(QuadPart);
  System::Object::ReleaseNotFrozen$((System::Object *)v18);
}

```

## disassembly

```asm
0x1800285b0  mov     [rsp-38h+arg_0], rbx
0x1800285b5  push    rbp
0x1800285b6  push    rsi
0x1800285b7  push    rdi
0x1800285b8  push    r12
0x1800285ba  push    r13
0x1800285bc  push    r14
0x1800285be  push    r15
0x1800285c0  mov     rbp, rsp
0x1800285c3  sub     rsp, 50h
0x1800285c7  mov     r13, rdx
0x1800285ca  mov     r14, rcx
0x1800285cd  mov     bl, [rdx+61h]
0x1800285d0  mov     rax, [rdx+38h]
0x1800285d4  xor     esi, esi
0x1800285d6  lea     r15d, [rsi+1]
0x1800285da  test    rax, rax
0x1800285dd  jz      short loc_18002863D
0x1800285df  mov     rcx, 7FFFFFFFFFFFFFFFh
0x1800285e9  mov     qword ptr [rbp+DueTime], rcx
0x1800285ed  test    bl, bl
0x1800285ef  jz      short loc_180028638
0x1800285f1  mov     rcx, 8000000000000001h
0x1800285fb  mov     qword ptr [rbp+DueTime], rcx
0x1800285ff  mov     ecx, esi
0x180028601  mov     [rsp+50h+fResume], ecx; fResume
0x180028605  mov     [rsp+50h+lpArgToCompletionRoutine], rsi; lpArgToCompletionRoutine
0x18002860a  xor     r9d, r9d; pfnCompletionRoutine
0x18002860d  xor     r8d, r8d; lPeriod
0x180028610  lea     rdx, [rbp+DueTime]; lpDueTime
0x180028614  mov     rcx, rax; hTimer
0x180028617  call    cs:__imp_SetWaitableTimer
0x18002861d  test    eax, eax
0x18002861f  jz      short loc_18002865B
0x180028621  mov     rax, [r14+48h]
0x180028625  mov     rcx, [rax+20h]; char16_t *
0x180028629  cmp     [rcx+18h], esi
0x18002862c  ja      loc_18002891E
0x180028632  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x180028638  mov     ecx, r15d
0x18002863b  jmp     short loc_180028601
0x18002863d  mov     r9d, 1F0003h; dwDesiredAccess
0x180028643  mov     r8d, r15d; dwFlags
0x180028646  xor     edx, edx; lpTimerName
0x180028648  xor     ecx, ecx; lpTimerAttributes
0x18002864a  call    cs:__imp_CreateWaitableTimerExW
0x180028650  test    rax, rax
0x180028653  jnz     short loc_180028661
0x180028655  call    ?ForWin32@FailFast@Cn@@SAXXZ; Cn::FailFast::ForWin32(void)
0x18002865b  call    ?ForWin32@FailFast@Cn@@SAXXZ; Cn::FailFast::ForWin32(void)
0x180028661  mov     [r13+38h], rax
0x180028665  jmp     loc_1800285DF
0x18002866a  mov     r15, rdi
0x18002866d  test    rdi, rdi
0x180028670  jz      short loc_18002867E
0x180028672  mov     eax, [rdi+10h]
0x180028675  test    eax, eax
0x180028677  jle     short loc_18002867E
0x180028679  inc     eax
0x18002867b  mov     [rdi+10h], eax
0x18002867e  movsxd  rax, r12d
0x180028681  mov     rcx, [rdx+rax*8+20h]; this
0x180028686  mov     [rdx+rax*8+20h], rdi
0x18002868b  test    rcx, rcx
0x18002868e  jz      short loc_180028696
0x180028690  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x180028695  nop
0x180028696  test    rbx, rbx
0x180028699  jz      short loc_1800286A3
0x18002869b  mov     rcx, rbx; this
0x18002869e  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x1800286a3  sub     r12d, 1
0x1800286a7  jns     loc_180028790
0x1800286ad  test    rsi, rsi
0x1800286b0  jz      short loc_1800286BB
0x1800286b2  mov     rcx, rsi; this
0x1800286b5  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x1800286ba  nop
0x1800286bb  test    r15, r15
0x1800286be  jz      short loc_1800286C8
0x1800286c0  mov     rcx, rdi; this
0x1800286c3  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x1800286c8  movsxd  r12, [rbp+arg_10]
0x1800286cc  lea     edx, [r12+1]
0x1800286d1  lea     rcx, [rbp+DueTime]
0x1800286d5  call    ?Create@?$Array$2@V?$SmartPtr@VObject@System@@@CFlat@@$00@CFlat@@SA?AV?$SmartPtr@V?$Array$2@V?$SmartPtr@VObject@System@@@CFlat@@$00@CFlat@@@2@H@Z; CFlat::Array$2<CFlat::SmartPtr<System::Object>,1>::Create(int)
0x1800286da  mov     rbx, qword ptr [rbp+DueTime]
0x1800286de  cmp     r12d, [rbx+18h]
0x1800286e2  jb      loc_1800288B4
0x1800286e8  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x1800286ee  cmp     [r13+60h], sil
0x1800286f2  jz      loc_18002879C
0x1800286f8  cmp     [r13+61h], sil
0x1800286fc  jz      short loc_180028747
0x1800286fe  mov     edx, [r14+50h]
0x180028702  lea     eax, [rdx+1]
0x180028705  mov     ecx, r15d
0x180028708  cmp     edx, 0FFFFFFFFh
0x18002870b  cmovnz  ecx, eax
0x18002870e  mov     [r14+50h], ecx
0x180028712  mov     [r13+60h], r15b
0x180028716  mov     [r13+40h], edx
0x18002871a  mov     qword ptr [rbp+DueTime], rsi
0x18002871e  lea     rcx, [rbp+DueTime]; lpSystemTimeAsFileTime
0x180028722  call    cs:__imp_GetSystemTimeAsFileTime
0x180028728  mov     rcx, 701CE1722770000h
0x180028732  add     rcx, qword ptr [rbp+DueTime]
0x180028736  mov     rax, 4000000000000000h
0x180028740  or      rcx, rax
0x180028743  mov     [r13+48h], rcx
0x180028747  mov     r14, [r14+48h]
0x18002874b  mov     [rbp+var_10], r14
0x18002874f  test    r14, r14
0x180028752  jz      short loc_180028758
0x180028754  add     [r14+10h], r15d
0x180028758  mov     rcx, r14; this
0x18002875b  call    ?ChooseNodeHeight@SkipList@Support@CoreUI@Microsoft@@AEAAHXZ; Microsoft::CoreUI::Support::SkipList::ChooseNodeHeight(void)
0x180028760  mov     [rbp+arg_10], eax
0x180028763  mov     rdi, [r14+20h]
0x180028767  mov     [rbp+var_20], rdi
0x18002876b  test    rdi, rdi
0x18002876e  jz      short loc_18002877C
0x180028770  mov     ecx, [rdi+10h]
0x180028773  test    ecx, ecx
0x180028775  jle     short loc_18002877C
0x180028777  inc     ecx; char16_t *
0x180028779  mov     [rdi+10h], ecx
0x18002877c  mov     [rbp+var_18], rsi
0x180028780  mov     r12d, [r14+40h]
0x180028784  sub     r12d, r15d
0x180028787  mov     r15, rdi
0x18002878a  js      loc_1800286AD
0x180028790  cmp     r12d, [r15+18h]
0x180028794  jb      short loc_1800287A2
0x180028796  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18002879c  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x1800287a2  movsxd  rax, r12d
0x1800287a5  add     rax, 4
0x1800287a9  lea     rdx, [r15+rax*8]
0x1800287ad  lea     rcx, [rbp+arg_18]
0x1800287b1  call    ??$Checked@V?$SmartPtr@V?$Array$2@V?$SmartPtr@VObject@System@@@CFlat@@$00@CFlat@@@CFlat@@AEAV?$SmartPtr@VObject@System@@@2@@Cast@CFlat@@SA?A_PAEAV?$SmartPtr@VObject@System@@@1@@Z
0x1800287b6  nop
0x1800287b7  mov     rbx, [rbp+arg_18]
0x1800287bb  cmp     rbx, rsi
0x1800287be  jnz     short loc_1800287D4
0x1800287c0  mov     rdx, [r14+28h]
0x1800287c4  cmp     r12d, [rdx+18h]
0x1800287c8  jb      loc_18002866A
0x1800287ce  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x1800287d4  test    rbx, rbx
0x1800287d7  jz      loc_1800289F7
0x1800287dd  movsxd  rcx, dword ptr [rbx+18h]; char16_t *
0x1800287e1  lea     eax, [rcx-1]
0x1800287e4  cmp     eax, [rbx+18h]
0x1800287e7  jb      loc_18002893A
0x1800287ed  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x1800287f3  mov     rdx, [rsi+r15*8+20h]
0x1800287f8  test    rdx, rdx
0x1800287fb  jz      short loc_180028809
0x1800287fd  mov     eax, [rdx+10h]
0x180028800  test    eax, eax
0x180028802  jle     short loc_180028809
0x180028804  inc     eax
0x180028806  mov     [rdx+10h], eax
0x180028809  mov     rcx, [rbx+r15*8+20h]; this
0x18002880e  mov     [rbx+r15*8+20h], rdx
0x180028813  test    rcx, rcx
0x180028816  jz      short loc_18002881D
0x180028818  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x18002881d  cmp     edi, [rsi+18h]
0x180028820  jb      short loc_180028828
0x180028822  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x180028828  mov     eax, [rbx+10h]
0x18002882b  test    eax, eax
0x18002882d  jle     short loc_180028834
0x18002882f  inc     eax
0x180028831  mov     [rbx+10h], eax
0x180028834  mov     rcx, [rsi+r15*8+20h]; this
0x180028839  mov     [rsi+r15*8+20h], rbx
0x18002883e  test    rcx, rcx
0x180028841  jz      short loc_180028848
0x180028843  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x180028848  mov     rax, [r14+28h]
0x18002884c  cmp     edi, [rax+18h]
0x18002884f  jb      short loc_180028857
0x180028851  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x180028857  mov     rcx, [rax+r15*8+20h]; this
0x18002885c  mov     qword ptr [rax+r15*8+20h], 0
0x180028865  test    rcx, rcx
0x180028868  jz      short loc_18002886F
0x18002886a  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x18002886f  test    rsi, rsi
0x180028872  jz      short loc_18002887C
0x180028874  mov     rcx, rsi; this
0x180028877  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x18002887c  inc     edi
0x18002887e  cmp     edi, r12d
0x180028881  jl      short loc_1800288DD
0x180028883  inc     dword ptr [r14+44h]
0x180028887  test    rbx, rbx
0x18002888a  jz      short loc_180028895
0x18002888c  mov     rcx, rbx; this
0x18002888f  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x180028894  nop
0x180028895  mov     rcx, r14; this
0x180028898  mov     rbx, [rsp+50h+arg_0]
0x1800288a0  add     rsp, 50h
0x1800288a4  pop     r15
0x1800288a6  pop     r14
0x1800288a8  pop     r13
0x1800288aa  pop     r12
0x1800288ac  pop     rdi
0x1800288ad  pop     rsi
0x1800288ae  pop     rbp
0x1800288af  jmp     ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x1800288b4  mov     eax, [r13+10h]
0x1800288b8  test    eax, eax
0x1800288ba  jle     short loc_1800288C2
0x1800288bc  inc     eax
0x1800288be  mov     [r13+10h], eax
0x1800288c2  mov     rcx, [rbx+r12*8+20h]; this
0x1800288c7  mov     [rbx+r12*8+20h], r13
0x1800288cc  test    rcx, rcx
0x1800288cf  jz      short loc_1800288D6
0x1800288d1  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x1800288d6  xor     edi, edi
0x1800288d8  test    r12d, r12d
0x1800288db  jle     short loc_180028883
0x1800288dd  mov     rax, [r14+28h]
0x1800288e1  cmp     edi, [rax+18h]
0x1800288e4  jb      short loc_1800288EC
0x1800288e6  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x1800288ec  movsxd  r15, edi
0x1800288ef  lea     rdx, [rax+20h]
0x1800288f3  lea     rdx, [rdx+r15*8]
0x1800288f7  lea     rcx, [rbp+DueTime]
0x1800288fb  call    ??$Checked@V?$SmartPtr@V?$Array$2@V?$SmartPtr@VObject@System@@@CFlat@@$00@CFlat@@@CFlat@@AEAV?$SmartPtr@VObject@System@@@2@@Cast@CFlat@@SA?A_PAEAV?$SmartPtr@VObject@System@@@1@@Z
0x180028900  mov     rsi, qword ptr [rbp+DueTime]
0x180028904  cmp     edi, [rsi+18h]
0x180028907  jb      short loc_18002890F
0x180028909  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18002890f  cmp     edi, [rbx+18h]
0x180028912  jb      loc_1800287F3
0x180028918  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18002891e  cmp     [rcx+20h], rsi
0x180028922  jnz     loc_1800286EE
0x180028928  mov     edx, 0Bh
0x18002892d  mov     rcx, r14
0x180028930  call    ?Activate@DispatchItem@Dispatch@CoreUI@Microsoft@@QEAAXW4InternalPriority@234@@Z; Microsoft::CoreUI::Dispatch::DispatchItem::Activate(Microsoft::CoreUI::Dispatch::InternalPriority)
0x180028935  jmp     loc_1800286EE
0x18002893a  mov     r15, [rbx+rcx*8+18h]
0x18002893f  mov     qword ptr [rbp+DueTime], r15
0x180028943  test    r15, r15
0x180028946  jz      short loc_180028956
0x180028948  mov     eax, [r15+10h]
0x18002894c  test    eax, eax
0x18002894e  jle     short loc_180028956
0x180028950  inc     eax
0x180028952  mov     [r15+10h], eax
0x180028956  mov     r8, r13; struct System::Object *
0x180028959  mov     rdx, r15; struct System::Object *
0x18002895c  mov     rcx, r14; this
0x18002895f  call    ?CompareValues@SkipList@Support@CoreUI@Microsoft@@AEAAHPEAVObject@System@@0@Z; Microsoft::CoreUI::Support::SkipList::CompareValues(System::Object *,System::Object *)
0x180028964  mov     dword ptr [rbp+DueTime], eax
0x180028967  test    r15, r15
0x18002896a  jz      short loc_180028977
0x18002896c  mov     rcx, r15; this
0x18002896f  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x180028974  mov     eax, dword ptr [rbp+DueTime]
0x180028977  cmp     eax, 1
0x18002897a  jge     short loc_1800289E6
0x18002897c  mov     eax, [rbx+10h]
0x18002897f  test    eax, eax
0x180028981  jle     short loc_180028988
0x180028983  inc     eax
0x180028985  mov     [rbx+10h], eax
0x180028988  mov     rcx, rdi; this
0x18002898b  mov     rdi, rbx
0x18002898e  mov     [rbp+var_20], rbx
0x180028992  test    rcx, rcx
0x180028995  jz      short loc_18002899C
0x180028997  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x18002899c  cmp     r12d, [rbx+18h]
0x1800289a0  jb      short loc_1800289A8
0x1800289a2  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x1800289a8  movsxd  rax, r12d
0x1800289ab  add     rax, 4
0x1800289af  lea     rcx, [rbx+rax*8]
0x1800289b3  call    ??$Checked@PEAV?$Array$2@V?$SmartPtr@VObject@System@@@CFlat@@$00@CFlat@@AEAV?$SmartPtr@VObject@System@@@2@@Cast@CFlat@@SA?A_PAEAV?$SmartPtr@VObject@System@@@1@@Z
0x1800289b8  test    rax, rax
0x1800289bb  jz      short loc_1800289C9
0x1800289bd  mov     ecx, [rax+10h]
0x1800289c0  test    ecx, ecx
0x1800289c2  jle     short loc_1800289C9
0x1800289c4  inc     ecx
0x1800289c6  mov     [rax+10h], ecx
0x1800289c9  mov     rcx, rbx; this
0x1800289cc  mov     rbx, rax
0x1800289cf  mov     [rbp+arg_18], rax
0x1800289d3  test    rcx, rcx
  ... truncated ...
```
