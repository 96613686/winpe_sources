# SHOpenEffectiveToken(ulong,int,void * *)

- ea: `0x18004eec0`
- end: `0x18004ef27`
- name: `?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z`
- size: `103`
- prototype: `int(unsigned int, int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18004ed94`

## callees

- `0x180012e54`
- `0x18004eec0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004ef0a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004ef0a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004eee3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004eee3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004eef9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004eef9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004eed0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004eed0`

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
0x18004eec0  push    rbx
0x18004eec2  sub     rsp, 20h
0x18004eec6  mov     rbx, r8
0x18004eec9  mov     qword ptr [r8], 0
0x18004eed0  call    cs:__imp_GetCurrentThread
0x18004eed6  xor     r8d, r8d; OpenAsSelf
0x18004eed9  mov     r9, rbx; TokenHandle
0x18004eedc  mov     rcx, rax; ThreadHandle
0x18004eedf  lea     edx, [r8+8]; DesiredAccess
0x18004eee3  call    cs:__imp_OpenThreadToken
0x18004eee9  test    eax, eax
0x18004eeeb  jnz     short loc_18004EF14
0x18004eeed  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004eef2  cmp     eax, 800703F0h
0x18004eef7  jnz     short loc_18004EF21
0x18004eef9  call    cs:__imp_GetCurrentProcess
0x18004eeff  mov     r8, rbx; TokenHandle
0x18004ef02  mov     edx, 8; DesiredAccess
0x18004ef07  mov     rcx, rax; ProcessHandle
0x18004ef0a  call    cs:__imp_OpenProcessToken
0x18004ef10  test    eax, eax
0x18004ef12  jz      short loc_18004EF1C
0x18004ef14  xor     eax, eax
0x18004ef16  add     rsp, 20h
0x18004ef1a  pop     rbx
0x18004ef1b  retn
0x18004ef1c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004ef21  add     rsp, 20h
0x18004ef25  pop     rbx
0x18004ef26  retn
```
