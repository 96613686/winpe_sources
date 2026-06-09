# Microsoft::CoreUI::Dispatch::Timeout::InterfaceImplementation$::_Microsoft_CoreUI_IExportMessageTimer::Dispatcher::SetRelative(System::Object *,__int64,__int64)

- ea: `0x180027f50`
- end: `0x18002815a`
- name: `?SetRelative@Dispatcher@_Microsoft_CoreUI_IExportMessageTimer@InterfaceImplementation$@Timeout@Dispatch@CoreUI@Microsoft@@UEBAXPEAVObject@System@@_J1@Z`
- size: `522`
- prototype: `void(Microsoft::CoreUI::Dispatch::Timeout::InterfaceImplementation$::_Microsoft_CoreUI_IExportMessageTimer::Dispatcher *__hidden this, struct System::Object *, __int64, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x18000cb50`
- `0x18000ec10`
- `0x1800111dc`
- `0x180027f50`
- `0x180028160`
- `0x180028218`
- `0x1800728d8`
- `0x18007abdc`
- `0x18008ae1c`
- `0x18008f584`
- `0x1800a9824`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x1800280e4`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x1800280e4`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x1800280a9`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x1800280a9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Microsoft::CoreUI::Dispatch::Timeout::InterfaceImplementation$::_Microsoft_CoreUI_IExportMessageTimer::Dispatcher::SetRelative(
        const char16_t *this,
        LARGE_INTEGER *a2,
        __int64 a3,
        __int64 a4)
{
  LARGE_INTEGER v7; // rdi
  DWORD v8; // r8d
  int v9; // edx
  __int64 v10; // rax
  System::Object *QuadPart; // rdi
  Microsoft::CoreUI::Support::SkipList *v12; // rsi
  Microsoft::CoreUI::Dispatch::TimeoutManager *v13; // rcx
  bool v14; // r15
  char16_t *v15; // rcx
  int v16; // eax
  __int64 v17; // rsi
  HANDLE WaitableTimer; // rax
  System::Exception **ArgumentInvalid; // rax
  LARGE_INTEGER DueTime; // [rsp+70h] [rbp+18h] BYREF
  Microsoft::CoreUI::Support::SkipList *v21; // [rsp+78h] [rbp+20h]

  if ( a4 < 0 || a3 < 0 )
  {
    ArgumentInvalid = (System::Exception **)Microsoft::CoreUI::ValidationException::get_ArgumentInvalid(&DueTime);
    System::Exception::Throw$(*ArgumentInvalid);
    JUMPOUT(0x180028159LL);
  }
  v7 = a2[5];
  DueTime = v7;
  if ( v7.QuadPart )
    ++*(_DWORD *)(v7.QuadPart + 16);
  if ( LOBYTE(a2[12].LowPart) )
  {
    v12 = *(Microsoft::CoreUI::Support::SkipList **)(v7.QuadPart + 72);
    v21 = v12;
    if ( v12 )
      ++*((_DWORD *)v12 + 4);
    v14 = Microsoft::CoreUI::Support::SkipList::Remove(v12, (struct System::Object *)a2);
    if ( v12 )
      System::Object::ReleaseNotFrozen$(v12);
    if ( v14 )
    {
      if ( Microsoft::CoreUI::Support::SkipList::get_IsEmpty(*(Microsoft::CoreUI::Support::SkipList **)(v7.QuadPart + 72)) )
        ((void (__fastcall *)(_QWORD, _QWORD))Microsoft::CoreUI::Dispatch::DispatchItem::ForceWakeLevel)(
          (LARGE_INTEGER)v7.QuadPart,
          0);
    }
    else
    {
      Microsoft::CoreUI::Dispatch::TimeoutManager::DisableTimer(v13, (struct Microsoft::CoreUI::Dispatch::Timeout *)a2);
    }
  }
  v8 = *(_DWORD *)(v7.QuadPart + 80);
  v9 = 1;
  if ( v8 != -1 )
    v9 = v8 + 1;
  *(_DWORD *)(v7.QuadPart + 80) = v9;
  LOBYTE(a2[12].LowPart) = 0;
  a2[8].LowPart = v8;
  if ( v7.QuadPart )
    System::Object::ReleaseNotFrozen$((System::Object *)v7.QuadPart);
  if ( LOBYTE(a2[12].LowPart) )
    CFlat::Abandonment::Fail(this);
  BYTE1(a2[12].LowPart) = 1;
  a2[9].QuadPart = 0;
  v10 = a4;
  if ( a3 )
    v10 = a3;
  a2[11].QuadPart = v10;
  a2[10].QuadPart = a4;
  QuadPart = (System::Object *)a2[5].QuadPart;
  if ( QuadPart )
    ++*((_DWORD *)QuadPart + 4);
  if ( LOBYTE(a2[12].LowPart) )
    CFlat::Abandonment::Fail(this);
  v15 = (char16_t *)*((unsigned int *)QuadPart + 20);
  v16 = 1;
  if ( BYTE1(a2[12].LowPart) )
  {
    if ( (_DWORD)v15 != -1 )
      v16 = (_DWORD)v15 + 1;
    *((_DWORD *)QuadPart + 20) = v16;
    LOBYTE(a2[12].LowPart) = 1;
    a2[8].LowPart = (unsigned int)v15;
    v17 = a2[11].QuadPart;
    WaitableTimer = (HANDLE)a2[7].QuadPart;
    if ( !WaitableTimer )
    {
      WaitableTimer = CreateWaitableTimerExW(0, 0, 1u, 0x1F0003u);
      if ( !WaitableTimer )
        Cn::FailFast::ForWin32();
      a2[7].QuadPart = (LONGLONG)WaitableTimer;
    }
    if ( v17 < 0 )
      CFlat::Abandonment::Fail(v15);
    DueTime.QuadPart = -v17;
    if ( !SetWaitableTimer(WaitableTimer, &DueTime, 0, 0, 0, 0) )
      Cn::FailFast::ForWin32();
  }
  else
  {
    if ( (_DWORD)v15 != -1 )
      v16 = (_DWORD)v15 + 1;
    *((_DWORD *)QuadPart + 20) = v16;
    LOBYTE(a2[12].LowPart) = 1;
    a2[8].LowPart = (unsigned int)v15;
    Microsoft::CoreUI::Dispatch::TimeoutManager::EnableAbsoluteTimer(
      (Microsoft::CoreUI::Dispatch::TimeoutManager *)v15,
      (struct Microsoft::CoreUI::Dispatch::Timeout *)a2);
  }
  if ( QuadPart )
    System::Object::ReleaseNotFrozen$(QuadPart);
}

```

## disassembly

```asm
0x180027f50  mov     [rsp+arg_0], rbx
0x180027f55  mov     [rsp+arg_8], rbp
0x180027f5a  push    rsi
0x180027f5b  push    rdi
0x180027f5c  push    r13
0x180027f5e  push    r14
0x180027f60  push    r15
0x180027f62  sub     rsp, 30h
0x180027f66  mov     r14, r9
0x180027f69  mov     rbp, r8
0x180027f6c  mov     rbx, rdx
0x180027f6f  test    r9, r9
0x180027f72  js      loc_180028146
0x180027f78  test    r8, r8
0x180027f7b  js      loc_180028146
0x180027f81  mov     rdi, [rdx+28h]
0x180027f85  mov     qword ptr [rsp+58h+DueTime], rdi
0x180027f8a  mov     r13d, 1
0x180027f90  test    rdi, rdi
0x180027f93  jz      short loc_180027F99
0x180027f95  add     [rdi+10h], r13d
0x180027f99  cmp     byte ptr [rdx+60h], 0
0x180027f9d  jnz     short loc_18002800E
0x180027f9f  mov     r8d, [rdi+50h]
0x180027fa3  lea     eax, [r8+1]
0x180027fa7  mov     edx, r13d
0x180027faa  or      esi, 0FFFFFFFFh
0x180027fad  cmp     r8d, esi
0x180027fb0  cmovnz  edx, eax
0x180027fb3  mov     [rdi+50h], edx
0x180027fb6  mov     byte ptr [rbx+60h], 0
0x180027fba  mov     [rbx+40h], r8d
0x180027fbe  test    rdi, rdi
0x180027fc1  jz      short loc_180027FCB
0x180027fc3  mov     rcx, rdi; this
0x180027fc6  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180027fcb  cmp     byte ptr [rbx+60h], 0
0x180027fcf  jz      short loc_180027FD7
0x180027fd1  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x180027fd7  mov     [rbx+61h], r13b
0x180027fdb  mov     qword ptr [rbx+48h], 0
0x180027fe3  mov     rax, r14
0x180027fe6  test    rbp, rbp
0x180027fe9  cmovnz  rax, rbp
0x180027fed  mov     [rbx+58h], rax
0x180027ff1  mov     [rbx+50h], r14
0x180027ff5  mov     rdi, [rbx+28h]
0x180027ff9  test    rdi, rdi
0x180027ffc  jz      short loc_180028002
0x180027ffe  add     [rdi+10h], r13d
0x180028002  cmp     byte ptr [rbx+60h], 0
0x180028006  jz      short loc_18002804E
0x180028008  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18002800e  mov     rsi, [rdi+48h]
0x180028012  mov     [rsp+58h+arg_18], rsi
0x180028017  test    rsi, rsi
0x18002801a  jz      short loc_180028020
0x18002801c  add     [rsi+10h], r13d
0x180028020  mov     rcx, rsi; this
0x180028023  call    ?Remove@SkipList@Support@CoreUI@Microsoft@@QEAA_NPEAVObject@System@@@Z; Microsoft::CoreUI::Support::SkipList::Remove(System::Object *)
0x180028028  mov     r15b, al
0x18002802b  test    rsi, rsi
0x18002802e  jz      short loc_180028038
0x180028030  mov     rcx, rsi; this
0x180028033  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180028038  test    r15b, r15b
0x18002803b  jnz     loc_18002810A
0x180028041  mov     rdx, rbx; struct Microsoft::CoreUI::Dispatch::Timeout *
0x180028044  call    ?DisableTimer@TimeoutManager@Dispatch@CoreUI@Microsoft@@AEAAXPEAVTimeout@234@@Z; Microsoft::CoreUI::Dispatch::TimeoutManager::DisableTimer(Microsoft::CoreUI::Dispatch::Timeout *)
0x180028049  jmp     loc_180027F9F
0x18002804e  mov     ecx, [rdi+50h]; this
0x180028051  lea     edx, [rcx+1]
0x180028054  mov     eax, r13d
0x180028057  cmp     byte ptr [rbx+61h], 0
0x18002805b  jz      loc_18002812A
0x180028061  cmp     ecx, esi
0x180028063  cmovnz  eax, edx
0x180028066  mov     [rdi+50h], eax
0x180028069  mov     [rbx+60h], r13b
0x18002806d  mov     [rbx+40h], ecx
0x180028070  mov     rsi, [rbx+58h]
0x180028074  mov     rax, [rbx+38h]
0x180028078  test    rax, rax
0x18002807b  jz      short loc_1800280D7
0x18002807d  test    rsi, rsi
0x180028080  js      short loc_1800280F5
0x180028082  neg     rsi
0x180028085  mov     qword ptr [rsp+58h+DueTime], rsi
0x18002808a  mov     [rsp+58h+fResume], 0; fResume
0x180028092  mov     [rsp+58h+lpArgToCompletionRoutine], 0; lpArgToCompletionRoutine
0x18002809b  xor     r9d, r9d; pfnCompletionRoutine
0x18002809e  xor     r8d, r8d; lPeriod
0x1800280a1  lea     rdx, [rsp+58h+DueTime]; lpDueTime
0x1800280a6  mov     rcx, rax; hTimer
0x1800280a9  call    cs:__imp_SetWaitableTimer
0x1800280af  test    eax, eax
0x1800280b1  jz      short loc_1800280FB
0x1800280b3  test    rdi, rdi
0x1800280b6  jz      short loc_1800280C0
0x1800280b8  mov     rcx, rdi; this
0x1800280bb  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x1800280c0  mov     rbx, [rsp+58h+arg_0]
0x1800280c5  mov     rbp, [rsp+58h+arg_8]
0x1800280ca  add     rsp, 30h
0x1800280ce  pop     r15
0x1800280d0  pop     r14
0x1800280d2  pop     r13
0x1800280d4  pop     rdi
0x1800280d5  pop     rsi
0x1800280d6  retn
0x1800280d7  mov     r9d, 1F0003h; dwDesiredAccess
0x1800280dd  mov     r8d, r13d; dwFlags
0x1800280e0  xor     edx, edx; lpTimerName
0x1800280e2  xor     ecx, ecx; lpTimerAttributes
0x1800280e4  call    cs:__imp_CreateWaitableTimerExW
0x1800280ea  test    rax, rax
0x1800280ed  jnz     short loc_180028101
0x1800280ef  call    ?ForWin32@FailFast@Cn@@SAXXZ; Cn::FailFast::ForWin32(void)
0x1800280f5  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x1800280fb  call    ?ForWin32@FailFast@Cn@@SAXXZ; Cn::FailFast::ForWin32(void)
0x180028101  mov     [rbx+38h], rax
0x180028105  jmp     loc_18002807D
0x18002810a  mov     rcx, [rdi+48h]; this
0x18002810e  call    ?get_IsEmpty@SkipList@Support@CoreUI@Microsoft@@QEAA_NXZ; Microsoft::CoreUI::Support::SkipList::get_IsEmpty(void)
0x180028113  test    al, al
0x180028115  jz      loc_180027F9F
0x18002811b  xor     edx, edx
0x18002811d  mov     rcx, rdi
0x180028120  call    ?ForceWakeLevel@DispatchItem@Dispatch@CoreUI@Microsoft@@QEAAXW4InternalPriority@234@@Z; Microsoft::CoreUI::Dispatch::DispatchItem::ForceWakeLevel(Microsoft::CoreUI::Dispatch::InternalPriority)
0x180028125  jmp     loc_180027F9F
0x18002812a  cmp     ecx, esi
0x18002812c  cmovnz  eax, edx
0x18002812f  mov     [rdi+50h], eax
0x180028132  mov     [rbx+60h], r13b
0x180028136  mov     [rbx+40h], ecx
0x180028139  mov     rdx, rbx; struct Microsoft::CoreUI::Dispatch::Timeout *
0x18002813c  call    ?EnableAbsoluteTimer@TimeoutManager@Dispatch@CoreUI@Microsoft@@AEAAXPEAVTimeout@234@@Z; Microsoft::CoreUI::Dispatch::TimeoutManager::EnableAbsoluteTimer(Microsoft::CoreUI::Dispatch::Timeout *)
0x180028141  jmp     loc_1800280B3
0x180028146  lea     rcx, [rsp+58h+DueTime]
0x18002814b  call    ?get_ArgumentInvalid@ValidationException@CoreUI@Microsoft@@SA?AV?$SmartPtr@VValidationException@CoreUI@Microsoft@@@CFlat@@XZ; Microsoft::CoreUI::ValidationException::get_ArgumentInvalid(void)
0x180028150  nop
0x180028151  mov     rcx, [rax]; this
0x180028154  call    ?Throw$@Exception@System@@QEAAXXZ; System::Exception::Throw$(void)
```
