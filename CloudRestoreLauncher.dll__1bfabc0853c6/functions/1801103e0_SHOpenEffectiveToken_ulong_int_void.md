# SHOpenEffectiveToken(ulong,int,void * *)

- ea: `0x1801103e0`
- end: `0x180110447`
- name: `?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z`
- size: `103`
- prototype: `int(unsigned int, int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1801102cc`

## callees

- `0x1800beb8c`
- `0x1801103e0`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x1801103f0`
- `KERNEL32!GetCurrentThread` at `0x1801103f0`
- `KERNEL32!GetCurrentProcess` at `0x180110419`
- `KERNEL32!GetCurrentProcess` at `0x180110419`
- `ADVAPI32!OpenThreadToken` at `0x180110403`
- `ADVAPI32!OpenThreadToken` at `0x180110403`
- `ADVAPI32!OpenProcessToken` at `0x18011042a`
- `ADVAPI32!OpenProcessToken` at `0x18011042a`

## pseudocode

```c
__int64 __fastcall SHOpenEffectiveToken(__int64 a1, __int64 a2, void **a3)
{
  HANDLE CurrentThread; // rax
  __int64 result; // rax
  HANDLE CurrentProcess; // rax

  *a3 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x28u, 0, a3) )
    return 0;
  result = ResultFromKnownLastError();
  if ( (_DWORD)result != -2147023888 )
    return result;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, a3) )
    return 0;
  else
    return ResultFromKnownLastError();
}

```

## disassembly

```asm
0x1801103e0  push    rbx
0x1801103e2  sub     rsp, 20h
0x1801103e6  mov     rbx, r8
0x1801103e9  mov     qword ptr [r8], 0
0x1801103f0  call    cs:__imp_GetCurrentThread
0x1801103f6  xor     r8d, r8d; OpenAsSelf
0x1801103f9  mov     r9, rbx; TokenHandle
0x1801103fc  mov     rcx, rax; ThreadHandle
0x1801103ff  lea     edx, [r8+28h]; DesiredAccess
0x180110403  call    cs:__imp_OpenThreadToken
0x180110409  test    eax, eax
0x18011040b  jnz     short loc_180110434
0x18011040d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180110412  cmp     eax, 800703F0h
0x180110417  jnz     short loc_180110441
0x180110419  call    cs:__imp_GetCurrentProcess
0x18011041f  mov     r8, rbx; TokenHandle
0x180110422  mov     edx, 28h ; '('; DesiredAccess
0x180110427  mov     rcx, rax; ProcessHandle
0x18011042a  call    cs:__imp_OpenProcessToken
0x180110430  test    eax, eax
0x180110432  jz      short loc_18011043C
0x180110434  xor     eax, eax
0x180110436  add     rsp, 20h
0x18011043a  pop     rbx
0x18011043b  retn
0x18011043c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180110441  add     rsp, 20h
0x180110445  pop     rbx
0x180110446  retn
```
