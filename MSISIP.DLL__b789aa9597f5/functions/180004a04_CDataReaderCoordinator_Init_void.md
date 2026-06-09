# CDataReaderCoordinator::Init(void)

- ea: `0x180004a04`
- end: `0x180004ac0`
- name: `?Init@CDataReaderCoordinator@@QEAAKXZ`
- size: `188`
- prototype: `unsigned int __fastcall(CDataReaderCoordinator *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003a70`

## callees

- `0x180004a04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004a40`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004a40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a28`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180004a14`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180004a14`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180004aa5`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180004aa5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateSemaphoreW` at `0x180004a59`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateSemaphoreW` at `0x180004a74`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateSemaphoreW` at `0x180004a59`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateSemaphoreW` at `0x180004a74`

## pseudocode

```c
DWORD __fastcall CDataReaderCoordinator::Init(CDataReaderCoordinator *this)
{
  HLOCAL v2; // rax
  HANDLE EventW; // rax
  HANDLE SemaphoreW; // rax
  HANDLE v6; // rax
  HANDLE Thread; // rax

  v2 = LocalAlloc(0, 0x10000u);
  *((_QWORD *)this + 5) = v2;
  if ( !v2 )
    return GetLastError();
  *((_DWORD *)this + 16) = 0x10000;
  EventW = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)this = EventW;
  if ( !EventW )
    return GetLastError();
  SemaphoreW = CreateSemaphoreW(0, 0, 2, 0);
  *((_QWORD *)this + 2) = SemaphoreW;
  if ( SemaphoreW
    && (v6 = CreateSemaphoreW(0, 2, 2, 0), (*((_QWORD *)this + 3) = v6) != 0)
    && (Thread = CreateThread(0, 0x1000u, CDataReaderCoordinator::StreamReaderThread, this, 0, 0),
        (*((_QWORD *)this + 1) = Thread) != 0) )
  {
    return 0;
  }
  else
  {
    return GetLastError();
  }
}

```

## disassembly

```asm
0x180004a04  push    rbx
0x180004a06  sub     rsp, 30h
0x180004a0a  mov     rbx, rcx
0x180004a0d  mov     edx, 10000h; uBytes
0x180004a12  xor     ecx, ecx; uFlags
0x180004a14  call    cs:__imp_LocalAlloc
0x180004a1a  mov     [rbx+28h], rax
0x180004a1e  test    rax, rax
0x180004a21  jnz     short loc_180004A2F
0x180004a23  add     rsp, 30h
0x180004a27  pop     rbx
0x180004a28  jmp     cs:__imp_GetLastError
0x180004a2f  xor     r9d, r9d; lpName
0x180004a32  mov     dword ptr [rbx+40h], 10000h
0x180004a39  xor     r8d, r8d; bInitialState
0x180004a3c  xor     edx, edx; bManualReset
0x180004a3e  xor     ecx, ecx; lpEventAttributes
0x180004a40  call    cs:__imp_CreateEventW
0x180004a46  mov     [rbx], rax
0x180004a49  test    rax, rax
0x180004a4c  jz      short loc_180004A23
0x180004a4e  xor     r9d, r9d; lpName
0x180004a51  xor     edx, edx; lInitialCount
0x180004a53  xor     ecx, ecx; lpSemaphoreAttributes
0x180004a55  lea     r8d, [r9+2]; lMaximumCount
0x180004a59  call    cs:__imp_CreateSemaphoreW
0x180004a5f  mov     [rbx+10h], rax
0x180004a63  test    rax, rax
0x180004a66  jz      short loc_180004A23
0x180004a68  xor     r9d, r9d; lpName
0x180004a6b  xor     ecx, ecx; lpSemaphoreAttributes
0x180004a6d  lea     edx, [r9+2]; lInitialCount
0x180004a71  mov     r8d, edx; lMaximumCount
0x180004a74  call    cs:__imp_CreateSemaphoreW
0x180004a7a  mov     [rbx+18h], rax
0x180004a7e  test    rax, rax
0x180004a81  jz      short loc_180004A23
0x180004a83  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180004a8c  lea     r8, ?StreamReaderThread@CDataReaderCoordinator@@KAKPEAX@Z; lpStartAddress
0x180004a93  mov     r9, rbx; lpParameter
0x180004a96  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180004a9e  mov     edx, 1000h; dwStackSize
0x180004aa3  xor     ecx, ecx; lpThreadAttributes
0x180004aa5  call    cs:__imp_CreateThread
0x180004aab  mov     [rbx+8], rax
0x180004aaf  test    rax, rax
0x180004ab2  jz      loc_180004A23
0x180004ab8  xor     eax, eax
0x180004aba  add     rsp, 30h
0x180004abe  pop     rbx
0x180004abf  retn
```
