# WinSAT::TraceDisk::ProcessTrace(WinSAT::TraceDiskConsumer *,void *)

- ea: `0x14006e508`
- end: `0x14006e625`
- name: `?ProcessTrace@TraceDisk@WinSAT@@QEAA_NPEAVTraceDiskConsumer@2@PEAX@Z`
- size: `285`
- prototype: `bool __fastcall(WinSAT::TraceDisk *__hidden this, struct WinSAT::TraceDiskConsumer *, void *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x14006bb04`
- `0x14006c0c8`
- `0x14006c494`
- `0x14006c890`

## callees

- `0x140003611`
- `0x14006e508`
- `0x140113220`
- `0x14011a010`

## import_xrefs

- `ADVAPI32!OpenTraceW` at `0x14006e5ad`
- `ADVAPI32!OpenTraceW` at `0x14006e5ad`
- `ADVAPI32!CloseTrace` at `0x14006e5e3`
- `ADVAPI32!CloseTrace` at `0x14006e5e3`
- `ADVAPI32!ProcessTrace` at `0x14006e5d8`
- `ADVAPI32!ProcessTrace` at `0x14006e5d8`
- `KERNEL32!SetLastError` at `0x14006e5c1`
- `KERNEL32!SetLastError` at `0x14006e5c1`

## pseudocode

```c
bool __fastcall WinSAT::TraceDisk::ProcessTrace(
        WinSAT::TraceDisk *this,
        struct WinSAT::TraceDiskConsumer *a2,
        void *a3)
{
  WCHAR *v7; // rcx
  __int64 v8; // rdx
  ULONG64 HandleArray[2]; // [rsp+20h] [rbp-1E8h] BYREF
  struct _EVENT_TRACE_LOGFILEW Logfile; // [rsp+30h] [rbp-1D8h] BYREF

  memset_0(&Logfile, 0, sizeof(Logfile));
  HandleArray[0] = -1;
  *((_QWORD *)this + 3) = a2;
  *((_QWORD *)this + 4) = a3;
  if ( !(**(unsigned __int8 (__fastcall ***)(struct WinSAT::TraceDiskConsumer *, void *))a2)(a2, a3) )
    return 0;
  v7 = *(WCHAR **)(*((_QWORD *)this + 1) + 24LL);
  Logfile.BufferCallback = (PEVENT_TRACE_BUFFER_CALLBACKW)WinSAT::TraceDisk::TraceBufferCB;
  Logfile.LogFileName = v7;
  Logfile.EventCallback = (PEVENT_CALLBACK)WinSAT::TraceDisk::TraceEventCB;
  Logfile.LoggerName = 0;
  HandleArray[0] = OpenTraceW(&Logfile);
  if ( HandleArray[0] == -1 )
  {
    SetLastError(6u);
    return 0;
  }
  ProcessTrace(HandleArray, 1u, 0, 0);
  CloseTrace(HandleArray[0]);
  LOBYTE(v8) = *((_BYTE *)this + 40);
  return (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 3) + 16LL))(
           *((_QWORD *)this + 3),
           v8,
           *((_QWORD *)this + 4));
}

```

## disassembly

```asm
0x14006e508  mov     [rsp+arg_8], rbx
0x14006e50d  mov     [rsp+arg_10], rsi
0x14006e512  push    rdi
0x14006e513  sub     rsp, 200h
0x14006e51a  mov     rax, cs:__security_cookie
0x14006e521  xor     rax, rsp
0x14006e524  mov     [rsp+208h+var_18], rax
0x14006e52c  mov     rbx, r8
0x14006e52f  mov     rdi, rdx
0x14006e532  mov     rsi, rcx
0x14006e535  xor     edx, edx; Val
0x14006e537  mov     r8d, 1C0h; Size
0x14006e53d  lea     rcx, [rsp+208h+Logfile]; void *
0x14006e542  call    memset_0
0x14006e547  mov     [rsp+208h+HandleArray], 0FFFFFFFFFFFFFFFFh
0x14006e550  mov     rdx, rbx
0x14006e553  mov     [rsi+18h], rdi
0x14006e557  mov     rcx, rdi
0x14006e55a  mov     [rsi+20h], rbx
0x14006e55e  mov     rax, [rdi]
0x14006e561  mov     rax, [rax]
0x14006e564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006e569  test    al, al
0x14006e56b  jnz     short loc_14006E574
0x14006e56d  xor     al, al
0x14006e56f  jmp     loc_14006E600
0x14006e574  mov     rax, [rsi+8]
0x14006e578  mov     rcx, [rax+18h]
0x14006e57c  lea     rax, ?TraceBufferCB@TraceDisk@WinSAT@@CAKPEAU_EVENT_TRACE_LOGFILEW@@@Z; WinSAT::TraceDisk::TraceBufferCB(_EVENT_TRACE_LOGFILEW *)
0x14006e583  mov     [rsp+208h+Logfile.BufferCallback], rax
0x14006e58b  lea     rax, ?TraceEventCB@TraceDisk@WinSAT@@CAXPEAU_EVENT_TRACE@@@Z; WinSAT::TraceDisk::TraceEventCB(_EVENT_TRACE *)
0x14006e592  mov     [rsp+208h+Logfile.LogFileName], rcx
0x14006e597  lea     rcx, [rsp+208h+Logfile]; Logfile
0x14006e59c  mov     qword ptr [rsp+208h+Logfile.1A8h], rax
0x14006e5a4  mov     [rsp+208h+Logfile.LoggerName], 0
0x14006e5ad  call    cs:__imp_OpenTraceW
0x14006e5b3  mov     [rsp+208h+HandleArray], rax
0x14006e5b8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14006e5bc  jnz     short loc_14006E5C9
0x14006e5be  lea     ecx, [rax+7]; dwErrCode
0x14006e5c1  call    cs:__imp_SetLastError
0x14006e5c7  jmp     short loc_14006E56D
0x14006e5c9  xor     r9d, r9d; EndTime
0x14006e5cc  lea     rcx, [rsp+208h+HandleArray]; HandleArray
0x14006e5d1  xor     r8d, r8d; StartTime
0x14006e5d4  lea     edx, [r9+1]; HandleCount
0x14006e5d8  call    cs:__imp_ProcessTrace
0x14006e5de  mov     rcx, [rsp+208h+HandleArray]; TraceHandle
0x14006e5e3  call    cs:__imp_CloseTrace
0x14006e5e9  mov     rcx, [rsi+18h]
0x14006e5ed  mov     r8, [rsi+20h]
0x14006e5f1  mov     dl, [rsi+28h]
0x14006e5f4  mov     rax, [rcx]
0x14006e5f7  mov     rax, [rax+10h]
0x14006e5fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006e600  mov     rcx, [rsp+208h+var_18]
0x14006e608  xor     rcx, rsp; StackCookie
0x14006e60b  call    __security_check_cookie
0x14006e610  lea     r11, [rsp+208h+var_8]
0x14006e618  mov     rbx, [r11+18h]
0x14006e61c  mov     rsi, [r11+20h]
0x14006e620  mov     rsp, r11
0x14006e623  pop     rdi
0x14006e624  retn
```
