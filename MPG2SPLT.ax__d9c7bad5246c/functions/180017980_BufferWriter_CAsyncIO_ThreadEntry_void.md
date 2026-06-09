# BufferWriter::CAsyncIO::ThreadEntry(void *)

- ea: `0x180017980`
- end: `0x180017a20`
- name: `?ThreadEntry@CAsyncIO@BufferWriter@@SAKPEAX@Z`
- size: `160`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180017980`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetQueuedCompletionStatus` at `0x1800179c5`
- `KERNEL32!GetQueuedCompletionStatus` at `0x1800179c5`
- `KERNEL32!SetEvent` at `0x180017a01`
- `KERNEL32!SetEvent` at `0x180017a01`
- `KERNEL32!LeaveCriticalSection` at `0x180017a0b`
- `KERNEL32!LeaveCriticalSection` at `0x180017a0b`
- `KERNEL32!EnterCriticalSection` at `0x1800179f1`
- `KERNEL32!EnterCriticalSection` at `0x1800179f1`

## pseudocode

```c
__int64 __fastcall BufferWriter::CAsyncIO::ThreadEntry(char *lpThreadParameter)
{
  bool v1; // zf
  DWORD NumberOfBytesTransferred; // [rsp+50h] [rbp+8h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+60h] [rbp+18h] BYREF
  unsigned __int64 CompletionKey; // [rsp+68h] [rbp+20h] BYREF

  v1 = *((_DWORD *)lpThreadParameter + 14) == 0;
  NumberOfBytesTransferred = 0;
  CompletionKey = 0;
  Overlapped = 0;
  if ( v1 )
  {
    do
    {
      if ( GetQueuedCompletionStatus(
             *((HANDLE *)lpThreadParameter + 1),
             &NumberOfBytesTransferred,
             &CompletionKey,
             &Overlapped,
             0x12Cu) )
      {
        (*(void (__fastcall **)(char *, unsigned __int64, _QWORD, LPOVERLAPPED))(*(_QWORD *)lpThreadParameter + 8LL))(
          lpThreadParameter,
          CompletionKey,
          NumberOfBytesTransferred,
          Overlapped);
        EnterCriticalSection((LPCRITICAL_SECTION)(lpThreadParameter + 88));
        v1 = (*((_DWORD *)lpThreadParameter + 20))-- == 1;
        if ( v1 )
          SetEvent(*((HANDLE *)lpThreadParameter + 9));
        LeaveCriticalSection((LPCRITICAL_SECTION)(lpThreadParameter + 88));
      }
    }
    while ( !*((_DWORD *)lpThreadParameter + 14) );
  }
  return 0;
}

```

## disassembly

```asm
0x180017980  push    rbx
0x180017982  push    rdi
0x180017983  sub     rsp, 38h
0x180017987  cmp     dword ptr [rcx+38h], 0
0x18001798b  mov     rbx, rcx
0x18001798e  mov     [rsp+48h+NumberOfBytesTransferred], 0
0x180017996  mov     [rsp+48h+CompletionKey], 0
0x18001799f  mov     [rsp+48h+Overlapped], 0
0x1800179a8  jnz     short loc_180017A17
0x1800179aa  mov     rcx, [rbx+8]; CompletionPort
0x1800179ae  lea     r9, [rsp+48h+Overlapped]; lpOverlapped
0x1800179b3  lea     r8, [rsp+48h+CompletionKey]; lpCompletionKey
0x1800179b8  mov     [rsp+48h+dwMilliseconds], 12Ch; dwMilliseconds
0x1800179c0  lea     rdx, [rsp+48h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1800179c5  call    cs:__imp_GetQueuedCompletionStatus
0x1800179cb  test    eax, eax
0x1800179cd  jz      short loc_180017A11
0x1800179cf  mov     rax, [rbx]
0x1800179d2  mov     rcx, rbx
0x1800179d5  mov     r9, [rsp+48h+Overlapped]
0x1800179da  mov     r8d, [rsp+48h+NumberOfBytesTransferred]
0x1800179df  mov     rdx, [rsp+48h+CompletionKey]
0x1800179e4  mov     rax, [rax+8]
0x1800179e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179ed  lea     rcx, [rbx+58h]; lpCriticalSection
0x1800179f1  call    cs:__imp_EnterCriticalSection
0x1800179f7  sub     dword ptr [rbx+50h], 1
0x1800179fb  jnz     short loc_180017A07
0x1800179fd  mov     rcx, [rbx+48h]; hEvent
0x180017a01  call    cs:__imp_SetEvent
0x180017a07  lea     rcx, [rbx+58h]; lpCriticalSection
0x180017a0b  call    cs:__imp_LeaveCriticalSection
0x180017a11  cmp     dword ptr [rbx+38h], 0
0x180017a15  jz      short loc_1800179AA
0x180017a17  xor     eax, eax
0x180017a19  add     rsp, 38h
0x180017a1d  pop     rdi
0x180017a1e  pop     rbx
0x180017a1f  retn
```
