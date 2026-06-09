# NLInternal::CSharedRecoActivation::StartSharedReco(int)

- ea: `0x14001f020`
- end: `0x14001f13f`
- name: `?StartSharedReco@CSharedRecoActivation@NLInternal@@UEAAJH@Z`
- size: `287`
- prototype: `__int64 __fastcall(NLInternal::CSharedRecoActivation *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140011ea8`
- `0x14001f020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14001f0f9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14001f0f9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001f04f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001f04f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f05e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f0d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f10f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f05e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f0d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f10f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14001f0c7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14001f0c7`

## pseudocode

```c
__int64 __fastcall NLInternal::CSharedRecoActivation::StartSharedReco(NLInternal::CSharedRecoActivation *this)
{
  HANDLE EventW; // rax
  signed int v4; // eax
  unsigned int v5; // ebx
  const wchar_t *v6; // rax
  signed int v7; // eax
  DWORD v8; // eax
  signed int LastError; // eax
  DWORD ThreadId; // [rsp+50h] [rbp+18h] BYREF

  ThreadId = 0;
  if ( !qword_14004DDD0 )
    return 2147549183LL;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 2) = EventW;
  if ( EventW )
  {
    if ( CreateThread(0, 0, (LPTHREAD_START_ROUTINE)NLInternal::SharedRecoExecutionThread, this, 0, &ThreadId) )
    {
      v8 = WaitForSingleObject(*((HANDLE *)this + 2), 0x1388u);
      if ( v8 )
      {
        if ( v8 == -1 )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v5 = -2147467259;
          if ( LastError < 0 )
            return (unsigned int)LastError;
        }
        else
        {
          return (unsigned int)-2147200911;
        }
      }
      else
      {
        return *((unsigned int *)this + 6);
      }
      return v5;
    }
    v7 = GetLastError();
    v5 = v7;
    if ( v7 > 0 )
      v5 = (unsigned __int16)v7 | 0x80070000;
    v6 = L"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\sharedrecosvr\\sharedrecoactivation.cpp(119)";
  }
  else
  {
    v4 = GetLastError();
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    v6 = L"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\sharedrecosvr\\sharedrecoactivation.cpp(118)";
  }
  DoTraceMessage(
    2,
    "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
    &NLInternal::s_tracingPrefix,
    L"NLInternal::CSharedRecoActivation::StartSharedReco",
    v6,
    v5);
  return v5;
}

```

## disassembly

```asm
0x14001f020  push    rbx
0x14001f022  sub     rsp, 30h
0x14001f026  cmp     cs:qword_14004DDD0, 0
0x14001f02e  mov     rbx, rcx
0x14001f031  mov     [rsp+38h+ThreadId], 0
0x14001f039  jnz     short loc_14001F045
0x14001f03b  mov     eax, 8000FFFFh
0x14001f040  jmp     loc_14001F139
0x14001f045  xor     r9d, r9d; lpName
0x14001f048  xor     r8d, r8d; bInitialState
0x14001f04b  xor     edx, edx; bManualReset
0x14001f04d  xor     ecx, ecx; lpEventAttributes
0x14001f04f  call    cs:__imp_CreateEventW
0x14001f055  mov     [rbx+10h], rax
0x14001f059  test    rax, rax
0x14001f05c  jnz     short loc_14001F0A7
0x14001f05e  call    cs:__imp_GetLastError
0x14001f064  mov     ebx, eax
0x14001f066  test    eax, eax
0x14001f068  jle     short loc_14001F073
0x14001f06a  movzx   ebx, ax
0x14001f06d  or      ebx, 80070000h
0x14001f073  lea     rax, aOnecoreuapEndu_58; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14001f07a  mov     dword ptr [rsp+38h+lpThreadId], ebx
0x14001f07e  lea     r9, aNlinternalCsha_4; "NLInternal::CSharedRecoActivation::Star"...
0x14001f085  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14001f08c  mov     qword ptr [rsp+38h+dwCreationFlags], rax
0x14001f091  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14001f098  mov     ecx, 2; int
0x14001f09d  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14001f0a2  jmp     loc_14001F137
0x14001f0a7  lea     rax, [rsp+38h+ThreadId]
0x14001f0ac  mov     r9, rbx; lpParameter
0x14001f0af  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x14001f0b4  lea     r8, ?SharedRecoExecutionThread@NLInternal@@YAKPEAK@Z; lpStartAddress
0x14001f0bb  xor     edx, edx; dwStackSize
0x14001f0bd  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x14001f0c5  xor     ecx, ecx; lpThreadAttributes
0x14001f0c7  call    cs:__imp_CreateThread
0x14001f0cd  test    rax, rax
0x14001f0d0  jnz     short loc_14001F0F0
0x14001f0d2  call    cs:__imp_GetLastError
0x14001f0d8  mov     ebx, eax
0x14001f0da  test    eax, eax
0x14001f0dc  jle     short loc_14001F0E7
0x14001f0de  movzx   ebx, ax
0x14001f0e1  or      ebx, 80070000h
0x14001f0e7  lea     rax, aOnecoreuapEndu_78; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14001f0ee  jmp     short loc_14001F07A
0x14001f0f0  mov     rcx, [rbx+10h]; hHandle
0x14001f0f4  mov     edx, 1388h; dwMilliseconds
0x14001f0f9  call    cs:__imp_WaitForSingleObject
0x14001f0ff  test    eax, eax
0x14001f101  jz      short loc_14001F134
0x14001f103  cmp     eax, 102h
0x14001f108  jz      short loc_14001F12D
0x14001f10a  cmp     eax, 0FFFFFFFFh
0x14001f10d  jnz     short loc_14001F12D
0x14001f10f  call    cs:__imp_GetLastError
0x14001f115  test    eax, eax
0x14001f117  jle     short loc_14001F121
0x14001f119  movzx   eax, ax
0x14001f11c  or      eax, 80070000h
0x14001f121  test    eax, eax
0x14001f123  mov     ebx, 80004005h
0x14001f128  cmovs   ebx, eax
0x14001f12b  jmp     short loc_14001F137
0x14001f12d  mov     ebx, 80045071h
0x14001f132  jmp     short loc_14001F137
0x14001f134  mov     ebx, [rbx+18h]
0x14001f137  mov     eax, ebx
0x14001f139  add     rsp, 30h
0x14001f13d  pop     rbx
0x14001f13e  retn
```
