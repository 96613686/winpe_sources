# CModelDownloadComponent::WaitForCopyJobToComplete(void)

- ea: `0x140012b68`
- end: `0x140012d13`
- name: `?WaitForCopyJobToComplete@CModelDownloadComponent@@AEAAJXZ`
- size: `427`
- prototype: `__int64 __fastcall(CModelDownloadComponent *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000d5a4`

## callees

- `0x14000985c`
- `0x140012b68`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x140012cf5`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x140012cf5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140012bcc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140012bcc`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x140012bb7`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x140012bb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012cfe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012cfe`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x140012b8c`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x140012b8c`

## string_xrefs

- `0x140012cca`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(735)`
- `0x140012cd1`: `CModelDownloadComponent::WaitForCopyJobToComplete`
- `0x140012c15`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(739)`
- `0x140012cbd`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(744)`
- `0x140012cb0`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(747)`
- `0x140012c4b`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(751)`

## pseudocode

```c
__int64 __fastcall CModelDownloadComponent::WaitForCopyJobToComplete(CModelDownloadComponent *this)
{
  HANDLE WaitableTimerW; // rsi
  int *v3; // r14
  int v4; // eax
  unsigned int v5; // ebx
  int v6; // ecx
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  LARGE_INTEGER DueTime; // [rsp+70h] [rbp+8h] BYREF

  DueTime.QuadPart = -10000000;
  WaitableTimerW = CreateWaitableTimerW(0, 0, L"SpeechModelDownloadTimer");
  SetWaitableTimer(WaitableTimerW, &DueTime, 1000, 0, 0, 0);
  v3 = (int *)((char *)this + 68);
  while ( 1 )
  {
    WaitForSingleObject(WaitableTimerW, 0xFFFFFFFF);
    v4 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 1) + 112LL))(
           *((_QWORD *)this + 1),
           (char *)this + 68);
    v5 = v4;
    if ( v4 < 0 )
      break;
    v6 = *v3;
    if ( *v3 == 6 )
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 72LL))(*((_QWORD *)this + 1));
      v5 = v7;
      if ( v7 < 0 )
      {
        DoTraceMessage(
          2,
          "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
          &NLInternal::s_tracingPrefix,
          L"CModelDownloadComponent::WaitForCopyJobToComplete",
          L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(739)",
          v7);
        goto LABEL_17;
      }
    }
    else if ( (unsigned int)(v6 - 4) <= 1 )
    {
      v9 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 1) + 120LL))(
             *((_QWORD *)this + 1),
             (char *)this + 16);
      v5 = v9;
      if ( v9 < 0 )
      {
        DoTraceMessage(
          2,
          "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
          &NLInternal::s_tracingPrefix,
          L"CModelDownloadComponent::WaitForCopyJobToComplete",
          L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(744)",
          v9);
        goto LABEL_17;
      }
      (*(void (__fastcall **)(_QWORD, char *, char *))(**((_QWORD **)this + 2) + 24LL))(
        *((_QWORD *)this + 2),
        (char *)this + 96,
        (char *)this + 100);
      v10 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 64LL))(*((_QWORD *)this + 1));
      v5 = v10;
      if ( v10 < 0 )
      {
        DoTraceMessage(
          2,
          "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
          &NLInternal::s_tracingPrefix,
          L"CModelDownloadComponent::WaitForCopyJobToComplete",
          L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(747)",
          v10);
        goto LABEL_17;
      }
    }
    else if ( v6 == 2 )
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 1) + 96LL))(
             *((_QWORD *)this + 1),
             (char *)this + 72);
      v5 = v8;
      if ( v8 < 0 )
      {
        DoTraceMessage(
          2,
          "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
          &NLInternal::s_tracingPrefix,
          L"CModelDownloadComponent::WaitForCopyJobToComplete",
          L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(751)",
          v8);
        goto LABEL_17;
      }
    }
    if ( (unsigned int)(*v3 - 4) <= 2 )
      goto LABEL_17;
  }
  DoTraceMessage(
    2,
    "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
    &NLInternal::s_tracingPrefix,
    L"CModelDownloadComponent::WaitForCopyJobToComplete",
    L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(735)",
    v4);
LABEL_17:
  CancelWaitableTimer(WaitableTimerW);
  CloseHandle(WaitableTimerW);
  return v5;
}

```

## disassembly

```asm
0x140012b68  push    rbx
0x140012b6a  push    rbp
0x140012b6b  push    rsi
0x140012b6c  push    rdi
0x140012b6d  push    r14
0x140012b6f  push    r15
0x140012b71  sub     rsp, 38h
0x140012b75  mov     rdi, rcx
0x140012b78  mov     qword ptr [rsp+68h+DueTime], 0FFFFFFFFFF676980h
0x140012b81  xor     ecx, ecx; lpTimerAttributes
0x140012b83  lea     r8, TimerName; "SpeechModelDownloadTimer"
0x140012b8a  xor     edx, edx; bManualReset
0x140012b8c  call    cs:__imp_CreateWaitableTimerW
0x140012b92  mov     [rsp+68h+fResume], 0; fResume
0x140012b9a  lea     rdx, [rsp+68h+DueTime]; lpDueTime
0x140012b9f  mov     rcx, rax; hTimer
0x140012ba2  mov     [rsp+68h+lpArgToCompletionRoutine], 0; lpArgToCompletionRoutine
0x140012bab  xor     r9d, r9d; pfnCompletionRoutine
0x140012bae  mov     r8d, 3E8h; lPeriod
0x140012bb4  mov     rsi, rax
0x140012bb7  call    cs:__imp_SetWaitableTimer
0x140012bbd  lea     r14, [rdi+44h]
0x140012bc1  mov     ebp, 2
0x140012bc6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140012bc9  mov     rcx, rsi; hHandle
0x140012bcc  call    cs:__imp_WaitForSingleObject
0x140012bd2  mov     rcx, [rdi+8]
0x140012bd6  mov     rdx, r14
0x140012bd9  mov     rax, [rcx]
0x140012bdc  mov     rax, [rax+70h]
0x140012be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012be5  mov     ebx, eax
0x140012be7  test    eax, eax
0x140012be9  js      loc_140012CC6
0x140012bef  mov     ecx, [r14]
0x140012bf2  cmp     ecx, 6
0x140012bf5  jnz     short loc_140012C21
0x140012bf7  mov     rcx, [rdi+8]
0x140012bfb  mov     rax, [rcx]
0x140012bfe  mov     rax, [rax+48h]
0x140012c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012c07  mov     ebx, eax
0x140012c09  test    eax, eax
0x140012c0b  jns     loc_140012C9C
0x140012c11  mov     [rsp+68h+fResume], eax
0x140012c15  lea     rax, aOnecoreuapEndu_143; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x140012c1c  jmp     loc_140012CD1
0x140012c21  lea     eax, [rcx-4]
0x140012c24  cmp     eax, 1
0x140012c27  jbe     short loc_140012C54
0x140012c29  cmp     ecx, ebp
0x140012c2b  jnz     short loc_140012C9C
0x140012c2d  mov     rcx, [rdi+8]
0x140012c31  lea     rdx, [rdi+48h]
0x140012c35  mov     rax, [rcx]
0x140012c38  mov     rax, [rax+60h]
0x140012c3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012c41  mov     ebx, eax
0x140012c43  test    eax, eax
0x140012c45  jns     short loc_140012C9C
0x140012c47  mov     [rsp+68h+fResume], eax
0x140012c4b  lea     rax, aOnecoreuapEndu_14; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x140012c52  jmp     short loc_140012CD1
0x140012c54  mov     rcx, [rdi+8]
0x140012c58  lea     rdx, [rdi+10h]
0x140012c5c  mov     rax, [rcx]
0x140012c5f  mov     rax, [rax+78h]
0x140012c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012c68  mov     ebx, eax
0x140012c6a  test    eax, eax
0x140012c6c  js      short loc_140012CB9
0x140012c6e  mov     rcx, [rdi+10h]
0x140012c72  lea     r8, [rdi+64h]
0x140012c76  lea     rdx, [rdi+60h]
0x140012c7a  mov     rax, [rcx]
0x140012c7d  mov     rax, [rax+18h]
0x140012c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012c86  mov     rcx, [rdi+8]
0x140012c8a  mov     rax, [rcx]
0x140012c8d  mov     rax, [rax+40h]
0x140012c91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012c96  mov     ebx, eax
0x140012c98  test    eax, eax
0x140012c9a  js      short loc_140012CAC
0x140012c9c  mov     eax, [r14]
0x140012c9f  sub     eax, 4
0x140012ca2  cmp     eax, ebp
0x140012ca4  ja      loc_140012BC6
0x140012caa  jmp     short loc_140012CF2
0x140012cac  mov     [rsp+68h+fResume], eax
0x140012cb0  lea     rax, aOnecoreuapEndu_90; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x140012cb7  jmp     short loc_140012CD1
0x140012cb9  mov     [rsp+68h+fResume], eax
0x140012cbd  lea     rax, aOnecoreuapEndu_148; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x140012cc4  jmp     short loc_140012CD1
0x140012cc6  mov     [rsp+68h+fResume], eax
0x140012cca  lea     rax, aOnecoreuapEndu_151; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x140012cd1  lea     r9, aCmodeldownload_21; "CModelDownloadComponent::WaitForCopyJob"...
0x140012cd8  mov     [rsp+68h+lpArgToCompletionRoutine], rax
0x140012cdd  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x140012ce4  mov     ecx, ebp; int
0x140012ce6  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x140012ced  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x140012cf2  mov     rcx, rsi; hTimer
0x140012cf5  call    cs:__imp_CancelWaitableTimer
0x140012cfb  mov     rcx, rsi; hObject
0x140012cfe  call    cs:__imp_CloseHandle
0x140012d04  mov     eax, ebx
0x140012d06  add     rsp, 38h
0x140012d0a  pop     r15
0x140012d0c  pop     r14
0x140012d0e  pop     rdi
0x140012d0f  pop     rsi
0x140012d10  pop     rbp
0x140012d11  pop     rbx
0x140012d12  retn
```
