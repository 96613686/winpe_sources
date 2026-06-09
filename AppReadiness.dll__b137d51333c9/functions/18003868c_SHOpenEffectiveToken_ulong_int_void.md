# SHOpenEffectiveToken(ulong,int,void * *)

- ea: `0x18003868c`
- end: `0x1800386f3`
- name: `?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z`
- size: `103`
- prototype: `int(unsigned int, int, void **)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18001218c`
- `0x1800122d0`
- `0x180012630`
- `0x18001e95c`

## callees

- `0x18003868c`
- `0x1800473d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800386af`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800386af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003869c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003869c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800386c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800386c5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800386d6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800386d6`

## pseudocode

```c
__int64 __fastcall SHOpenEffectiveToken(__int64 a1, __int64 a2, void **a3)
{
  HANDLE CurrentThread; // rax
  __int64 result; // rax
  HANDLE CurrentProcess; // rax

  *a3 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, a3) )
    return 0;
  result = ResultFromKnownLastError();
  if ( (_DWORD)result != -2147023888 )
    return result;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, a3) )
    return 0;
  else
    return ResultFromKnownLastError();
}

```

## disassembly

```asm
0x18003868c  push    rbx
0x18003868e  sub     rsp, 20h
0x180038692  mov     rbx, r8
0x180038695  mov     qword ptr [r8], 0
0x18003869c  call    cs:__imp_GetCurrentThread
0x1800386a2  xor     r8d, r8d; OpenAsSelf
0x1800386a5  mov     r9, rbx; TokenHandle
0x1800386a8  mov     rcx, rax; ThreadHandle
0x1800386ab  lea     edx, [r8+8]; DesiredAccess
0x1800386af  call    cs:__imp_OpenThreadToken
0x1800386b5  test    eax, eax
0x1800386b7  jnz     short loc_1800386E0
0x1800386b9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800386be  cmp     eax, 800703F0h
0x1800386c3  jnz     short loc_1800386ED
0x1800386c5  call    cs:__imp_GetCurrentProcess
0x1800386cb  mov     r8, rbx; TokenHandle
0x1800386ce  mov     edx, 8; DesiredAccess
0x1800386d3  mov     rcx, rax; ProcessHandle
0x1800386d6  call    cs:__imp_OpenProcessToken
0x1800386dc  test    eax, eax
0x1800386de  jz      short loc_1800386E8
0x1800386e0  xor     eax, eax
0x1800386e2  add     rsp, 20h
0x1800386e6  pop     rbx
0x1800386e7  retn
0x1800386e8  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800386ed  add     rsp, 20h
0x1800386f1  pop     rbx
0x1800386f2  retn
```
