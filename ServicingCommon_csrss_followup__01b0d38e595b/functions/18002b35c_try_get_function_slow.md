# try_get_function_slow

- ea: `0x18002b35c`
- end: `0x18002b4ff`
- name: `try_get_function_slow`
- size: `419`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18002b508`
- `0x18002b56c`
- `0x18002b61c`
- `0x18002b700`
- `0x18002b7ac`

## callees

- `0x180028c54`
- `0x180029b20`
- `0x180029b80`
- `0x18002b35c`
- `0x18002bfe0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002b3d0`
- `KERNEL32!GetLastError` at `0x18002b3d0`
- `KERNEL32!LoadLibraryExW` at `0x18002b3be`
- `KERNEL32!LoadLibraryExW` at `0x18002b412`
- `KERNEL32!LoadLibraryExW` at `0x18002b3be`
- `KERNEL32!LoadLibraryExW` at `0x18002b412`
- `KERNEL32!GetProcAddress` at `0x18002b4eb`
- `KERNEL32!GetProcAddress` at `0x18002b4eb`
- `KERNEL32!FreeLibrary` at `0x18002b4df`
- `KERNEL32!FreeLibrary` at `0x18002b4df`
- `KERNEL32!VirtualProtect` at `0x18002b477`
- `KERNEL32!VirtualProtect` at `0x18002b4a7`
- `KERNEL32!VirtualProtect` at `0x18002b477`
- `KERNEL32!VirtualProtect` at `0x18002b4a7`

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
  DWORD flOldProtect; // [rsp+80h] [rbp+18h] BYREF

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
    Library = (HMODULE)qword_1800D1F80[v8];
    if ( !Library )
      break;
    if ( Library != (HMODULE)-1LL )
      goto LABEL_20;
LABEL_11:
    if ( ++v6 == a4 )
      goto LABEL_12;
  }
  v10 = off_18009F7B0[v8];
  Library = LoadLibraryExW(v10, 0, 0x800u);
  if ( !Library
    && (GetLastError() != 87
     || !wcsncmp(v10, L"api-ms-", 7u)
     || !wcsncmp(v10, L"ext-ms-", 7u)
     || (Library = LoadLibraryExW(v10, 0, 0)) == 0) )
  {
    _InterlockedExchange64(&qword_1800D1F80[v8], -1);
    goto LABEL_11;
  }
  if ( _InterlockedExchange64(&qword_1800D1F80[v8], (__int64)Library) )
    FreeLibrary(Library);
LABEL_20:
  ProcAddress = GetProcAddress(Library, a2);
LABEL_13:
  _acrt_lock(14);
  flOldProtect = 0;
  if ( !VirtualProtect(qword_1800DB000, 0x100u, 4u, &flOldProtect) )
    goto LABEL_21;
  v12 = (__int64)ProcAddress;
  if ( !ProcAddress )
    v12 = -1;
  _InterlockedExchange64(&qword_1800DB000[v4], v12);
  if ( !VirtualProtect(qword_1800DB000, 0x100u, 2u, &flOldProtect) )
LABEL_21:
    abort();
  _acrt_unlock(14);
  return ProcAddress;
}

```

## disassembly

```asm
0x18002b35c  push    rbx
0x18002b35e  push    rbp
0x18002b35f  push    rsi
0x18002b360  push    rdi
0x18002b361  push    r12
0x18002b363  push    r13
0x18002b365  push    r14
0x18002b367  push    r15
0x18002b369  sub     rsp, 28h
0x18002b36d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b371  mov     r12d, ecx
0x18002b374  mov     r14, r9
0x18002b377  mov     rsi, r8
0x18002b37a  mov     r15, rdx
0x18002b37d  cmp     r8, r9
0x18002b380  jz      loc_18002B441
0x18002b386  lea     r13, __ImageBase
0x18002b38d  mov     edi, [rsi]
0x18002b38f  mov     rbx, rva qword_1800D1F80[r13+rdi*8]
0x18002b397  nop
0x18002b398  test    rbx, rbx
0x18002b39b  jz      short loc_18002B3AB
0x18002b39d  cmp     rbx, rax
0x18002b3a0  jnz     loc_18002B4E5
0x18002b3a6  jmp     loc_18002B434
0x18002b3ab  mov     rbp, ds:rva off_18009F7B0[r13+rdi*8]; "api-ms-win-core-datetime-l1-1-1" ...
0x18002b3b3  xor     edx, edx; hFile
0x18002b3b5  mov     rcx, rbp; lpLibFileName
0x18002b3b8  mov     r8d, 800h; dwFlags
0x18002b3be  call    cs:__imp_LoadLibraryExW
0x18002b3c4  mov     rbx, rax
0x18002b3c7  test    rax, rax
0x18002b3ca  jnz     loc_18002B4CC
0x18002b3d0  call    cs:__imp_GetLastError
0x18002b3d6  cmp     eax, 57h ; 'W'
0x18002b3d9  jnz     short loc_18002B424
0x18002b3db  lea     ebx, [rax-50h]
0x18002b3de  mov     rcx, rbp; String1
0x18002b3e1  mov     r8d, ebx; MaxCount
0x18002b3e4  lea     rdx, aApiMs; "api-ms-"
0x18002b3eb  call    wcsncmp
0x18002b3f0  test    eax, eax
0x18002b3f2  jz      short loc_18002B424
0x18002b3f4  mov     r8d, ebx; MaxCount
0x18002b3f7  lea     rdx, aExtMs; "ext-ms-"
0x18002b3fe  mov     rcx, rbp; String1
0x18002b401  call    wcsncmp
0x18002b406  test    eax, eax
0x18002b408  jz      short loc_18002B424
0x18002b40a  xor     r8d, r8d; dwFlags
0x18002b40d  xor     edx, edx; hFile
0x18002b40f  mov     rcx, rbp; lpLibFileName
0x18002b412  call    cs:__imp_LoadLibraryExW
0x18002b418  mov     rbx, rax
0x18002b41b  test    rax, rax
0x18002b41e  jnz     loc_18002B4CC
0x18002b424  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b428  xchg    rax, rva qword_1800D1F80[r13+rdi*8]
0x18002b430  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b434  add     rsi, 4
0x18002b438  cmp     rsi, r14
0x18002b43b  jnz     loc_18002B38D
0x18002b441  xor     ebx, ebx
0x18002b443  mov     edi, 0Eh
0x18002b448  mov     ecx, edi
0x18002b44a  call    __acrt_lock
0x18002b44f  mov     ebp, 100h
0x18002b454  mov     [rsp+68h+flOldProtect], 0
0x18002b45f  lea     rsi, qword_1800DB000
0x18002b466  mov     edx, ebp; dwSize
0x18002b468  mov     rcx, rsi; lpAddress
0x18002b46b  lea     r9, [rsp+68h+flOldProtect]; lpflOldProtect
0x18002b473  lea     r8d, [rdi-0Ah]; flNewProtect
0x18002b477  call    cs:__imp_VirtualProtect
0x18002b47d  test    eax, eax
0x18002b47f  jz      short loc_18002B4F9
0x18002b481  test    rbx, rbx
0x18002b484  mov     rax, rbx
0x18002b487  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002b48e  cmovz   rax, rcx
0x18002b492  xchg    rax, [rsi+r12*8]
0x18002b496  lea     r9, [rsp+68h+flOldProtect]; lpflOldProtect
0x18002b49e  mov     edx, ebp; dwSize
0x18002b4a0  lea     r8d, [rdi-0Ch]; flNewProtect
0x18002b4a4  mov     rcx, rsi; lpAddress
0x18002b4a7  call    cs:__imp_VirtualProtect
0x18002b4ad  test    eax, eax
0x18002b4af  jz      short loc_18002B4F9
0x18002b4b1  mov     ecx, edi
0x18002b4b3  call    __acrt_unlock
0x18002b4b8  mov     rax, rbx
0x18002b4bb  add     rsp, 28h
0x18002b4bf  pop     r15
0x18002b4c1  pop     r14
0x18002b4c3  pop     r13
0x18002b4c5  pop     r12
0x18002b4c7  pop     rdi
0x18002b4c8  pop     rsi
0x18002b4c9  pop     rbp
0x18002b4ca  pop     rbx
0x18002b4cb  retn
0x18002b4cc  mov     rax, rbx
0x18002b4cf  xchg    rax, rva qword_1800D1F80[r13+rdi*8]
0x18002b4d7  test    rax, rax
0x18002b4da  jz      short loc_18002B4E5
0x18002b4dc  mov     rcx, rbx; hLibModule
0x18002b4df  call    cs:__imp_FreeLibrary
0x18002b4e5  mov     rdx, r15; lpProcName
0x18002b4e8  mov     rcx, rbx; hModule
0x18002b4eb  call    cs:__imp_GetProcAddress
0x18002b4f1  mov     rbx, rax
0x18002b4f4  jmp     loc_18002B443
0x18002b4f9  call    abort
```
