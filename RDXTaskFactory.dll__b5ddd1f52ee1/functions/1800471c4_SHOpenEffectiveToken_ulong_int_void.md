# SHOpenEffectiveToken(ulong,int,void * *)

- ea: `0x1800471c4`
- end: `0x18004722b`
- name: `?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z`
- size: `103`
- prototype: `int(unsigned int, int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18004706c`

## callees

- `0x180025cd8`
- `0x1800471c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800471d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800471d4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800471e7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800471e7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004720e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004720e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800471fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800471fd`

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
0x1800471c4  push    rbx
0x1800471c6  sub     rsp, 20h
0x1800471ca  mov     rbx, r8
0x1800471cd  mov     qword ptr [r8], 0
0x1800471d4  call    cs:__imp_GetCurrentThread
0x1800471da  xor     r8d, r8d; OpenAsSelf
0x1800471dd  mov     r9, rbx; TokenHandle
0x1800471e0  mov     rcx, rax; ThreadHandle
0x1800471e3  lea     edx, [r8+8]; DesiredAccess
0x1800471e7  call    cs:__imp_OpenThreadToken
0x1800471ed  test    eax, eax
0x1800471ef  jnz     short loc_180047218
0x1800471f1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800471f6  cmp     eax, 800703F0h
0x1800471fb  jnz     short loc_180047225
0x1800471fd  call    cs:__imp_GetCurrentProcess
0x180047203  mov     r8, rbx; TokenHandle
0x180047206  mov     edx, 8; DesiredAccess
0x18004720b  mov     rcx, rax; ProcessHandle
0x18004720e  call    cs:__imp_OpenProcessToken
0x180047214  test    eax, eax
0x180047216  jz      short loc_180047220
0x180047218  xor     eax, eax
0x18004721a  add     rsp, 20h
0x18004721e  pop     rbx
0x18004721f  retn
0x180047220  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180047225  add     rsp, 20h
0x180047229  pop     rbx
0x18004722a  retn
```
