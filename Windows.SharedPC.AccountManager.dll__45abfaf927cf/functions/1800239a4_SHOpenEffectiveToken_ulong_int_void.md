# SHOpenEffectiveToken(ulong,int,void * *)

- ea: `0x1800239a4`
- end: `0x180023a3a`
- name: `?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z`
- size: `150`
- prototype: `int(unsigned int, int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18002381c`

## callees

- `0x180018070`
- `0x1800239a4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023a0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023a0c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800239c7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800239f6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800239c7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800239f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800239b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800239e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800239b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800239e1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180023a1d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180023a1d`

## pseudocode

```c
__int64 __fastcall SHOpenEffectiveToken(__int64 a1, __int64 a2, void **a3)
{
  HANDLE CurrentThread; // rax
  __int64 result; // rax
  HANDLE v6; // rax
  HANDLE CurrentProcess; // rax

  *a3 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, a3) )
    return 0;
  result = ResultFromKnownLastError();
  if ( (int)result >= 0 )
    return result;
  if ( (_DWORD)result == -2147024891 )
  {
    v6 = GetCurrentThread();
    if ( !OpenThreadToken(v6, 8u, 1, a3) )
    {
      result = ResultFromKnownLastError();
      goto LABEL_6;
    }
    return 0;
  }
LABEL_6:
  if ( (_DWORD)result != -2147023888 )
    return result;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, a3) )
    return 0;
  return ResultFromKnownLastError();
}

```

## disassembly

```asm
0x1800239a4  push    rbx
0x1800239a6  sub     rsp, 20h
0x1800239aa  mov     rbx, r8
0x1800239ad  mov     qword ptr [r8], 0
0x1800239b4  call    cs:__imp_GetCurrentThread
0x1800239ba  xor     r8d, r8d; OpenAsSelf
0x1800239bd  mov     r9, rbx; TokenHandle
0x1800239c0  mov     rcx, rax; ThreadHandle
0x1800239c3  lea     edx, [r8+8]; DesiredAccess
0x1800239c7  call    cs:__imp_OpenThreadToken
0x1800239cd  test    eax, eax
0x1800239cf  jnz     short loc_180023A27
0x1800239d1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800239d6  test    eax, eax
0x1800239d8  jns     short loc_180023A34
0x1800239da  cmp     eax, 80070005h
0x1800239df  jnz     short loc_180023A05
0x1800239e1  call    cs:__imp_GetCurrentThread
0x1800239e7  mov     edx, 8; DesiredAccess
0x1800239ec  mov     r9, rbx; TokenHandle
0x1800239ef  mov     rcx, rax; ThreadHandle
0x1800239f2  lea     r8d, [rdx-7]; OpenAsSelf
0x1800239f6  call    cs:__imp_OpenThreadToken
0x1800239fc  test    eax, eax
0x1800239fe  jnz     short loc_180023A27
0x180023a00  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180023a05  cmp     eax, 800703F0h
0x180023a0a  jnz     short loc_180023A34
0x180023a0c  call    cs:__imp_GetCurrentProcess
0x180023a12  mov     r8, rbx; TokenHandle
0x180023a15  mov     edx, 8; DesiredAccess
0x180023a1a  mov     rcx, rax; ProcessHandle
0x180023a1d  call    cs:__imp_OpenProcessToken
0x180023a23  test    eax, eax
0x180023a25  jz      short loc_180023A2F
0x180023a27  xor     eax, eax
0x180023a29  add     rsp, 20h
0x180023a2d  pop     rbx
0x180023a2e  retn
0x180023a2f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180023a34  add     rsp, 20h
0x180023a38  pop     rbx
0x180023a39  retn
```
