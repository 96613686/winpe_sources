# CWorkflowSession::GetPrintTicket(ulong,ulong *,uchar * *)

- ea: `0x180019840`
- end: `0x1800199d6`
- name: `?GetPrintTicket@CWorkflowSession@@UEAAJKPEAKPEAPEAE@Z`
- size: `406`
- prototype: `int(CWorkflowSession *__hidden this, unsigned int, unsigned int *, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004944`
- `0x18000b390`
- `0x180010b0c`
- `0x180018f90`
- `0x180019840`
- `0x180019da0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001995b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001995b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001998f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800199b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001998f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800199b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800198f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800198f9`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800198e3`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800198e3`

## string_xrefs

- `0x18001986b`: `onecoreuap\printscan\print\workflow\broker\lib\workflowsession.cpp`
- `0x180019936`: `onecoreuap\printscan\print\workflow\broker\lib\workflowsession.cpp`
- `0x180019975`: `onecoreuap\printscan\print\workflow\broker\lib\workflowsession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWorkflowSession::GetPrintTicket(
        CWorkflowSession *this,
        DWORD a2,
        unsigned int *a3,
        unsigned __int8 **a4)
{
  __int64 v8; // rdx
  unsigned int v9; // ebx
  int v10; // eax
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  DWORD v13; // eax
  DWORD v14; // eax
  signed int LastError; // eax
  unsigned __int8 *v16; // rax
  HANDLE Handles[2]; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v19[3]; // [rsp+30h] [rbp-28h] BYREF
  void *v20; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]
  PSRWLOCK SRWLock; // [rsp+A0h] [rbp+48h] BYREF

  if ( a3 )
  {
    if ( !a4 )
    {
      v8 = 521;
      goto LABEL_3;
    }
    v19[0] = &EventList::EventListNode::`vftable';
    v20 = 0;
    v10 = EventList::EventListNode::InitializeAndAddToList(
            (EventList::EventListNode *)v19,
            (CWorkflowSession *)((char *)this + 184));
    v9 = v10;
    if ( v10 >= 0 )
    {
      Handles[0] = *((HANDLE *)this + 19);
      Handles[1] = v20;
      v13 = WaitForMultipleObjects(2u, Handles, 0, a2);
      if ( !v13 )
      {
        Microsoft::WRL::Wrappers::SRWLock::LockShared(&SRWLock, (char *)this + 248);
        v16 = (unsigned __int8 *)CoTaskMemAlloc(*((unsigned int *)this + 22));
        *a4 = v16;
        if ( v16 )
        {
          memcpy_0(v16, *((const void **)this + 10), *((unsigned int *)this + 22));
          *a3 = *((_DWORD *)this + 22);
          if ( SRWLock )
            ReleaseSRWLockShared(SRWLock);
          v9 = 0;
        }
        else
        {
          v9 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x220,
            (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowsession.cpp",
            (const char *)0x8007000ELL,
            (int)Handles[0]);
          if ( SRWLock )
            ReleaseSRWLockShared(SRWLock);
        }
        goto LABEL_25;
      }
      v14 = v13 - 1;
      if ( v14 )
      {
        if ( v14 == 257 )
        {
          v9 = -2147024638;
          v12 = 555;
        }
        else
        {
          LastError = GetLastError();
          v9 = LastError;
          if ( LastError > 0 )
            v9 = (unsigned __int16)LastError | 0x80070000;
          if ( (v9 & 0x80000000) == 0 )
            goto LABEL_25;
          v12 = 558;
        }
      }
      else
      {
        v9 = -2147019873;
        v12 = 552;
      }
      v11 = v9;
    }
    else
    {
      v11 = (unsigned int)v10;
      v12 = 524;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowsession.cpp",
      (const char *)v11,
      (int)Handles[0]);
LABEL_25:
    EventList::EventListNode::~EventListNode((EventList::EventListNode *)v19);
    return v9;
  }
  v8 = 520;
LABEL_3:
  v9 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowsession.cpp",
    (const char *)0x80004003LL,
    (int)Handles[0]);
  return v9;
}

```

## disassembly

```asm
0x180019840  push    rbp
0x180019842  push    rbx
0x180019843  push    rsi
0x180019844  push    rdi
0x180019845  push    r14
0x180019847  push    r15
0x180019849  mov     rbp, rsp
0x18001984c  sub     rsp, 58h
0x180019850  mov     rsi, r9
0x180019853  mov     r14, r8
0x180019856  mov     r15d, edx
0x180019859  mov     rdi, rcx
0x18001985c  test    r8, r8
0x18001985f  jnz     short loc_180019883
0x180019861  mov     edx, 208h; void *
0x180019866  mov     ebx, 80004003h
0x18001986b  lea     r8, aOnecoreuapPrin_11; "onecoreuap\\printscan\\print\\workflow"...
0x180019872  mov     r9d, ebx; char *
0x180019875  mov     rcx, [rbp+30h]; this
0x180019879  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001987e  jmp     loc_1800199C7
0x180019883  test    rsi, rsi
0x180019886  jnz     short loc_18001988F
0x180019888  mov     edx, 209h
0x18001988d  jmp     short loc_180019866
0x18001988f  lea     rax, ??_7EventListNode@EventList@@6B@; const EventList::EventListNode::`vftable'
0x180019896  mov     [rbp+var_28], rax
0x18001989a  mov     [rbp+var_10], 0
0x1800198a2  lea     rdx, [rcx+0B8h]; struct EventList *
0x1800198a9  lea     rcx, [rbp+var_28]; this
0x1800198ad  call    ?InitializeAndAddToList@EventListNode@EventList@@QEAAJPEAV2@@Z; EventList::EventListNode::InitializeAndAddToList(EventList *)
0x1800198b2  mov     ebx, eax
0x1800198b4  test    eax, eax
0x1800198b6  jns     short loc_1800198C2
0x1800198b8  mov     r9d, eax
0x1800198bb  mov     edx, 20Ch
0x1800198c0  jmp     short loc_180019936
0x1800198c2  mov     rax, [rdi+98h]
0x1800198c9  mov     [rbp+Handles], rax
0x1800198cd  mov     rax, [rbp+var_10]
0x1800198d1  mov     [rbp+var_30], rax
0x1800198d5  mov     r9d, r15d; dwMilliseconds
0x1800198d8  xor     r8d, r8d; bWaitAll
0x1800198db  lea     rdx, [rbp+Handles]; lpHandles
0x1800198df  lea     ecx, [r8+2]; nCount
0x1800198e3  call    cs:__imp_WaitForMultipleObjects
0x1800198e9  test    eax, eax
0x1800198eb  jz      short loc_180019948
0x1800198ed  sub     eax, 1
0x1800198f0  jz      short loc_180019929
0x1800198f2  cmp     eax, 101h
0x1800198f7  jz      short loc_18001991D
0x1800198f9  call    cs:__imp_GetLastError
0x1800198ff  mov     ebx, eax
0x180019901  test    eax, eax
0x180019903  jle     short loc_18001990E
0x180019905  movzx   ebx, ax
0x180019908  or      ebx, 80070000h
0x18001990e  test    ebx, ebx
0x180019910  jns     loc_1800199BE
0x180019916  mov     edx, 22Eh
0x18001991b  jmp     short loc_180019933
0x18001991d  mov     ebx, 80070102h
0x180019922  mov     edx, 22Bh
0x180019927  jmp     short loc_180019933
0x180019929  mov     ebx, 8007139Fh
0x18001992e  mov     edx, 228h; void *
0x180019933  mov     r9d, ebx; char *
0x180019936  lea     r8, aOnecoreuapPrin_11; "onecoreuap\\printscan\\print\\workflow"...
0x18001993d  mov     rcx, [rbp+30h]; this
0x180019941  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019946  jmp     short loc_1800199BE
0x180019948  lea     rdx, [rdi+0F8h]
0x18001994f  lea     rcx, [rbp+SRWLock]
0x180019953  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x180019958  mov     ecx, [rdi+58h]; cb
0x18001995b  call    cs:__imp_CoTaskMemAlloc
0x180019961  mov     [rsi], rax
0x180019964  test    rax, rax
0x180019967  jnz     short loc_180019997
0x180019969  mov     rcx, [rbp+30h]; this
0x18001996d  mov     ebx, 8007000Eh
0x180019972  mov     r9d, ebx; char *
0x180019975  lea     r8, aOnecoreuapPrin_11; "onecoreuap\\printscan\\print\\workflow"...
0x18001997c  mov     edx, 220h; void *
0x180019981  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019986  mov     rcx, [rbp+SRWLock]; SRWLock
0x18001998a  test    rcx, rcx
0x18001998d  jz      short loc_1800199BE
0x18001998f  call    cs:__imp_ReleaseSRWLockShared
0x180019995  jmp     short loc_1800199BE
0x180019997  mov     r8d, [rdi+58h]; Size
0x18001999b  mov     rdx, [rdi+50h]; Src
0x18001999f  mov     rcx, rax; void *
0x1800199a2  call    memcpy_0
0x1800199a7  mov     eax, [rdi+58h]
0x1800199aa  mov     [r14], eax
0x1800199ad  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800199b1  test    rcx, rcx
0x1800199b4  jz      short loc_1800199BC
0x1800199b6  call    cs:__imp_ReleaseSRWLockShared
0x1800199bc  xor     ebx, ebx
0x1800199be  lea     rcx, [rbp+var_28]; this
0x1800199c2  call    ??1EventListNode@EventList@@UEAA@XZ; EventList::EventListNode::~EventListNode(void)
0x1800199c7  mov     eax, ebx
0x1800199c9  add     rsp, 58h
0x1800199cd  pop     r15
0x1800199cf  pop     r14
0x1800199d1  pop     rdi
0x1800199d2  pop     rsi
0x1800199d3  pop     rbx
0x1800199d4  pop     rbp
0x1800199d5  retn
```
