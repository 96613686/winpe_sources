# try_get_function_slow

- ea: `0x18021b238`
- end: `0x18021b3ea`
- name: `try_get_function_slow`
- size: `434`
- prototype: `FARPROC __fastcall(unsigned int, const CHAR *, unsigned int *, unsigned int *)`
- caller_count: `17`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18021b200`
- `0x18021b3ec`
- `0x18021b448`
- `0x18021b4a4`
- `0x18021b5b4`
- `0x18021b684`
- `0x18021b74c`
- `0x18021b7e0`
- `0x18021b898`
- `0x18021b910`
- `0x18021b978`
- `0x18021ba00`
- `0x18021baf4`
- `0x18021bb58`
- `0x18021bba8`
- `0x18021bc00`
- `0x18021bde0`

## callees

- `0x180206a58`
- `0x1802132c8`
- `0x180213328`
- `0x180217aa0`
- `0x18021b238`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18021b2b7`
- `KERNEL32!GetLastError` at `0x18021b2b7`
- `KERNEL32!GetProcAddress` at `0x18021b3d6`
- `KERNEL32!GetProcAddress` at `0x18021b3d6`
- `KERNEL32!VirtualProtect` at `0x18021b355`
- `KERNEL32!VirtualProtect` at `0x18021b386`
- `KERNEL32!VirtualProtect` at `0x18021b355`
- `KERNEL32!VirtualProtect` at `0x18021b386`
- `KERNEL32!FreeLibrary` at `0x18021b3ca`
- `KERNEL32!FreeLibrary` at `0x18021b3ca`
- `KERNEL32!LoadLibraryExW` at `0x18021b2a5`
- `KERNEL32!LoadLibraryExW` at `0x18021b2f9`
- `KERNEL32!LoadLibraryExW` at `0x18021b2a5`
- `KERNEL32!LoadLibraryExW` at `0x18021b2f9`

## pseudocode

```c
FARPROC __fastcall try_get_function_slow(unsigned int a1, const CHAR *a2, unsigned int *a3, unsigned int *a4)
{
  __int64 v4; // r12
  unsigned int *v6; // rsi
  __int64 v8; // rdi
  HMODULE Library; // rbx
  const WCHAR *v10; // rbp
  FARPROC ProcAddress; // rbx
  __int64 v12; // rax
  DWORD flOldProtect; // [rsp+60h] [rbp+18h] BYREF

  v4 = a1;
  v6 = a3;
  if ( a3 == a4 )
  {
LABEL_12:
    ProcAddress = 0;
    goto LABEL_13;
  }
  while ( 1 )
  {
    v8 = *v6;
    Library = (HMODULE)qword_1803E23F0[v8];
    if ( !Library )
      break;
    if ( Library != (HMODULE)-1LL )
      goto LABEL_20;
LABEL_11:
    if ( ++v6 == a4 )
      goto LABEL_12;
  }
  v10 = off_180291B10[v8];
  Library = LoadLibraryExW(v10, 0, 0x800u);
  if ( !Library
    && (GetLastError() != 87
     || !wcsncmp(v10, L"api-ms-", 7u)
     || !wcsncmp(v10, L"ext-ms-", 7u)
     || (Library = LoadLibraryExW(v10, 0, 0)) == 0) )
  {
    _InterlockedExchange64(&qword_1803E23F0[v8], -1);
    goto LABEL_11;
  }
  if ( _InterlockedExchange64(&qword_1803E23F0[v8], (__int64)Library) )
    FreeLibrary(Library);
LABEL_20:
  ProcAddress = GetProcAddress(Library, a2);
LABEL_13:
  _acrt_lock(14);
  flOldProtect = 0;
  if ( !VirtualProtect(qword_1803FF000, 0x100u, 4u, &flOldProtect) )
    goto LABEL_21;
  v12 = (__int64)ProcAddress;
  if ( !ProcAddress )
    v12 = -1;
  _InterlockedExchange64(&qword_1803FF000[v4], v12);
  if ( !VirtualProtect(qword_1803FF000, 0x100u, 2u, &flOldProtect) )
LABEL_21:
    abort();
  _acrt_unlock(14);
  return ProcAddress;
}

```

## disassembly

```asm
0x18021b238  mov     [rsp+arg_0], rbx
0x18021b23d  mov     [rsp+arg_8], rbp
0x18021b242  mov     [rsp+arg_18], rsi
0x18021b247  push    rdi
0x18021b248  push    r12
0x18021b24a  push    r13
0x18021b24c  push    r14
0x18021b24e  push    r15
0x18021b250  sub     rsp, 20h
0x18021b254  or      rax, 0FFFFFFFFFFFFFFFFh
0x18021b258  mov     r12d, ecx
0x18021b25b  mov     r14, r9
0x18021b25e  mov     rsi, r8
0x18021b261  mov     r15, rdx
0x18021b264  cmp     r8, r9
0x18021b267  jz      loc_18021B328
0x18021b26d  lea     r13, cs:180000000h
0x18021b274  mov     edi, [rsi]
0x18021b276  mov     rbx, rva qword_1803E23F0[r13+rdi*8]
0x18021b27e  nop
0x18021b27f  test    rbx, rbx
0x18021b282  jz      short loc_18021B292
0x18021b284  cmp     rbx, rax
0x18021b287  jnz     loc_18021B3D0
0x18021b28d  jmp     loc_18021B31B
0x18021b292  mov     rbp, ds:rva off_180291B10[r13+rdi*8]; "api-ms-win-core-datetime-l1-1-1" ...
0x18021b29a  xor     edx, edx; hFile
0x18021b29c  mov     rcx, rbp; lpLibFileName
0x18021b29f  mov     r8d, 800h; dwFlags
0x18021b2a5  call    cs:__imp_LoadLibraryExW
0x18021b2ab  mov     rbx, rax
0x18021b2ae  test    rax, rax
0x18021b2b1  jnz     loc_18021B3B7
0x18021b2b7  call    cs:__imp_GetLastError
0x18021b2bd  cmp     eax, 57h ; 'W'
0x18021b2c0  jnz     short loc_18021B30B
0x18021b2c2  lea     ebx, [rax-50h]
0x18021b2c5  mov     rcx, rbp; String1
0x18021b2c8  mov     r8d, ebx; MaxCount
0x18021b2cb  lea     rdx, aApiMs; "api-ms-"
0x18021b2d2  call    wcsncmp
0x18021b2d7  test    eax, eax
0x18021b2d9  jz      short loc_18021B30B
0x18021b2db  mov     r8d, ebx; MaxCount
0x18021b2de  lea     rdx, aExtMs; "ext-ms-"
0x18021b2e5  mov     rcx, rbp; String1
0x18021b2e8  call    wcsncmp
0x18021b2ed  test    eax, eax
0x18021b2ef  jz      short loc_18021B30B
0x18021b2f1  xor     r8d, r8d; dwFlags
0x18021b2f4  xor     edx, edx; hFile
0x18021b2f6  mov     rcx, rbp; lpLibFileName
0x18021b2f9  call    cs:__imp_LoadLibraryExW
0x18021b2ff  mov     rbx, rax
0x18021b302  test    rax, rax
0x18021b305  jnz     loc_18021B3B7
0x18021b30b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18021b30f  xchg    rax, rva qword_1803E23F0[r13+rdi*8]
0x18021b317  or      rax, 0FFFFFFFFFFFFFFFFh
0x18021b31b  add     rsi, 4
0x18021b31f  cmp     rsi, r14
0x18021b322  jnz     loc_18021B274
0x18021b328  xor     ebx, ebx
0x18021b32a  mov     edi, 0Eh
0x18021b32f  mov     ecx, edi
0x18021b331  call    __acrt_lock
0x18021b336  and     [rsp+48h+flOldProtect], 0
0x18021b33b  lea     rsi, qword_1803FF000
0x18021b342  mov     ebp, 100h
0x18021b347  lea     r9, [rsp+48h+flOldProtect]; lpflOldProtect
0x18021b34c  mov     edx, ebp; dwSize
0x18021b34e  lea     r8d, [rdi-0Ah]; flNewProtect
0x18021b352  mov     rcx, rsi; lpAddress
0x18021b355  call    cs:__imp_VirtualProtect
0x18021b35b  test    eax, eax
0x18021b35d  jz      loc_18021B3E4
0x18021b363  test    rbx, rbx
0x18021b366  mov     rax, rbx
0x18021b369  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18021b370  cmovz   rax, rcx
0x18021b374  xchg    rax, [rsi+r12*8]
0x18021b378  lea     r9, [rsp+48h+flOldProtect]; lpflOldProtect
0x18021b37d  mov     edx, ebp; dwSize
0x18021b37f  lea     r8d, [rdi-0Ch]; flNewProtect
0x18021b383  mov     rcx, rsi; lpAddress
0x18021b386  call    cs:__imp_VirtualProtect
0x18021b38c  test    eax, eax
0x18021b38e  jz      short loc_18021B3E4
0x18021b390  mov     ecx, edi
0x18021b392  call    __acrt_unlock
0x18021b397  mov     rbp, [rsp+48h+arg_8]
0x18021b39c  mov     rax, rbx
0x18021b39f  mov     rbx, [rsp+48h+arg_0]
0x18021b3a4  mov     rsi, [rsp+48h+arg_18]
0x18021b3a9  add     rsp, 20h
0x18021b3ad  pop     r15
0x18021b3af  pop     r14
0x18021b3b1  pop     r13
0x18021b3b3  pop     r12
0x18021b3b5  pop     rdi
0x18021b3b6  retn
0x18021b3b7  mov     rax, rbx
0x18021b3ba  xchg    rax, rva qword_1803E23F0[r13+rdi*8]
0x18021b3c2  test    rax, rax
0x18021b3c5  jz      short loc_18021B3D0
0x18021b3c7  mov     rcx, rbx; hLibModule
0x18021b3ca  call    cs:__imp_FreeLibrary
0x18021b3d0  mov     rdx, r15; lpProcName
0x18021b3d3  mov     rcx, rbx; hModule
0x18021b3d6  call    cs:__imp_GetProcAddress
0x18021b3dc  mov     rbx, rax
0x18021b3df  jmp     loc_18021B32A
0x18021b3e4  call    abort
```
