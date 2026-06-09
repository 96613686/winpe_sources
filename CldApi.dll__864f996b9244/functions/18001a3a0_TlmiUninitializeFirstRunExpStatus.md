# TlmiUninitializeFirstRunExpStatus

- ea: `0x18001a3a0`
- end: `0x18001a436`
- name: `TlmiUninitializeFirstRunExpStatus`
- size: `150`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001101c`
- `0x180011d18`
- `0x180018680`

## callees

- `0x18001a3a0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001a3ab`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001a3ab`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001a42f`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18001a3e2`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18001a3e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a3ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a40c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a3ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a40c`

## pseudocode

```c
__int64 TlmiUninitializeFirstRunExpStatus()
{
  LARGE_INTEGER DueTime; // [rsp+40h] [rbp+8h] BYREF

  RtlAcquireSRWLockExclusive(&qword_180028970);
  if ( hTimer )
  {
    DueTime.QuadPart = 1;
    SetWaitableTimer(hTimer, &DueTime, 0, 0, 0, 0);
    CloseHandle(hTimer);
    hTimer = 0;
  }
  if ( qword_1800289A0 )
  {
    CloseHandle(qword_1800289A0);
    qword_1800289A0 = 0;
  }
  byte_180028968 = 0;
  return RtlReleaseSRWLockExclusive(&qword_180028970);
}

```

## disassembly

```asm
0x18001a3a0  sub     rsp, 38h
0x18001a3a4  lea     rcx, qword_180028970
0x18001a3ab  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001a3b1  mov     rcx, cs:hTimer; hTimer
0x18001a3b8  test    rcx, rcx
0x18001a3bb  jz      short loc_18001A400
0x18001a3bd  mov     [rsp+38h+fResume], 0; fResume
0x18001a3c5  lea     rdx, [rsp+38h+DueTime]; lpDueTime
0x18001a3ca  xor     r9d, r9d; pfnCompletionRoutine
0x18001a3cd  mov     [rsp+38h+lpArgToCompletionRoutine], 0; lpArgToCompletionRoutine
0x18001a3d6  xor     r8d, r8d; lPeriod
0x18001a3d9  mov     qword ptr [rsp+38h+DueTime], 1
0x18001a3e2  call    cs:__imp_SetWaitableTimer
0x18001a3e8  mov     rcx, cs:hTimer; hObject
0x18001a3ef  call    cs:__imp_CloseHandle
0x18001a3f5  mov     cs:hTimer, 0
0x18001a400  mov     rcx, cs:qword_1800289A0; hObject
0x18001a407  test    rcx, rcx
0x18001a40a  jz      short loc_18001A41D
0x18001a40c  call    cs:__imp_CloseHandle
0x18001a412  mov     cs:qword_1800289A0, 0
0x18001a41d  lea     rcx, qword_180028970
0x18001a424  mov     cs:byte_180028968, 0
0x18001a42b  add     rsp, 38h
0x18001a42f  jmp     cs:__imp_RtlReleaseSRWLockExclusive
```
