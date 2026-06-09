# CWaitTask::_Process(bool)

- ea: `0x18002f5bc`
- end: `0x18002f69e`
- name: `?_Process@CWaitTask@@AEAAX_N@Z`
- size: `226`
- prototype: `void __fastcall(CWaitTask *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18002ffa0`

## callees

- `0x18002d608`
- `0x18002f5bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f601`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f601`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f638`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f638`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f5d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f676`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f5d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f676`
- `USER32!AttachThreadInput` at `0x18002f5e7`
- `USER32!AttachThreadInput` at `0x18002f684`
- `USER32!AttachThreadInput` at `0x18002f5e7`
- `USER32!AttachThreadInput` at `0x18002f684`
- `USER32!LoadCursorW` at `0x18002f61e`
- `USER32!LoadCursorW` at `0x18002f61e`
- `USER32!SetCursor` at `0x18002f627`
- `USER32!SetCursor` at `0x18002f663`
- `USER32!SetCursor` at `0x18002f627`
- `USER32!SetCursor` at `0x18002f663`

## pseudocode

```c
void __fastcall CWaitTask::_Process(CWaitTask *this, char a2)
{
  DWORD CurrentThreadId; // eax
  BOOL v4; // eax
  unsigned int v5; // r9d
  HCURSOR *v6; // rsi
  HWND v7; // rcx
  HCURSOR CursorW; // rax
  HCURSOR v9; // rax
  DWORD v10; // eax
  unsigned int v11; // [rsp+20h] [rbp-18h]
  unsigned int v12; // [rsp+28h] [rbp-10h]
  void *v13; // [rsp+50h] [rbp+18h] BYREF

  if ( a2 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v4 = AttachThreadInput(*((_DWORD *)this + 8), CurrentThreadId, 1);
    v6 = (HCURSOR *)((char *)this + 24);
    LOBYTE(v7) = v4;
    *((_BYTE *)this + 36) = v4;
    if ( v4 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
      CursorW = LoadCursorW(0, (LPCWSTR)(*((_DWORD *)this + 10) != 0 ? 32650LL : 32514LL));
      v9 = SetCursor(CursorW);
      *((_BYTE *)this + 88) = 1;
      *v6 = v9;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    }
    v13 = (void *)*((_QWORD *)this + 2);
    SHProcessMessagesUntilEventsEx(v7, &v13, v13 != 0, v5, v11, v12);
    if ( *v6 )
    {
      SetCursor(*v6);
      *v6 = 0;
    }
    if ( *((_BYTE *)this + 36) )
    {
      v10 = GetCurrentThreadId();
      AttachThreadInput(*((_DWORD *)this + 8), v10, 0);
      *((_BYTE *)this + 36) = 0;
    }
  }
}

```

## disassembly

```asm
0x18002f5bc  test    dl, dl
0x18002f5be  jz      locret_18002F69D
0x18002f5c4  mov     [rsp+arg_0], rbx
0x18002f5c9  mov     [rsp+arg_8], rsi
0x18002f5ce  push    rdi
0x18002f5cf  sub     rsp, 30h
0x18002f5d3  mov     rdi, rcx
0x18002f5d6  call    cs:__imp_GetCurrentThreadId
0x18002f5dc  mov     ecx, [rdi+20h]; idAttach
0x18002f5df  mov     r8d, 1; fAttach
0x18002f5e5  mov     edx, eax; idAttachTo
0x18002f5e7  call    cs:__imp_AttachThreadInput
0x18002f5ed  test    eax, eax
0x18002f5ef  lea     rsi, [rdi+18h]
0x18002f5f3  setnz   cl
0x18002f5f6  mov     [rdi+24h], cl
0x18002f5f9  test    eax, eax
0x18002f5fb  jz      short loc_18002F63E
0x18002f5fd  lea     rcx, [rdi+30h]; lpCriticalSection
0x18002f601  call    cs:__imp_EnterCriticalSection
0x18002f607  mov     eax, [rdi+28h]
0x18002f60a  neg     eax
0x18002f60c  sbb     rdx, rdx
0x18002f60f  xor     ecx, ecx; hInstance
0x18002f611  and     edx, 88h
0x18002f617  add     rdx, 7F02h; lpCursorName
0x18002f61e  call    cs:__imp_LoadCursorW
0x18002f624  mov     rcx, rax; hCursor
0x18002f627  call    cs:__imp_SetCursor
0x18002f62d  lea     rcx, [rdi+30h]; lpCriticalSection
0x18002f631  mov     byte ptr [rdi+58h], 1
0x18002f635  mov     [rsi], rax
0x18002f638  call    cs:__imp_LeaveCriticalSection
0x18002f63e  mov     rax, [rdi+10h]
0x18002f642  lea     rdx, [rsp+38h+arg_10]; void **
0x18002f647  xor     r8d, r8d
0x18002f64a  mov     [rsp+38h+arg_10], rax
0x18002f64f  test    rax, rax
0x18002f652  setnz   r8b; unsigned int
0x18002f656  call    ?SHProcessMessagesUntilEventsEx@@YAKPEAUHWND__@@PEAPEAXKKKK@Z; SHProcessMessagesUntilEventsEx(HWND__ *,void * *,ulong,ulong,ulong,ulong)
0x18002f65b  mov     rcx, [rsi]; hCursor
0x18002f65e  test    rcx, rcx
0x18002f661  jz      short loc_18002F670
0x18002f663  call    cs:__imp_SetCursor
0x18002f669  mov     qword ptr [rsi], 0
0x18002f670  cmp     byte ptr [rdi+24h], 0
0x18002f674  jz      short loc_18002F68E
0x18002f676  call    cs:__imp_GetCurrentThreadId
0x18002f67c  mov     ecx, [rdi+20h]; idAttach
0x18002f67f  xor     r8d, r8d; fAttach
0x18002f682  mov     edx, eax; idAttachTo
0x18002f684  call    cs:__imp_AttachThreadInput
0x18002f68a  mov     byte ptr [rdi+24h], 0
0x18002f68e  mov     rbx, [rsp+38h+arg_0]
0x18002f693  mov     rsi, [rsp+38h+arg_8]
0x18002f698  add     rsp, 30h
0x18002f69c  pop     rdi
0x18002f69d  retn
```
