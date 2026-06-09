# try_get_function_slow

- ea: `0x18000c8f8`
- end: `0x18000caaa`
- name: `try_get_function_slow`
- size: `434`
- prototype: ``
- caller_count: `65`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000c0b4`
- `0x18000c0ec`
- `0x18000c124`
- `0x18000c15c`
- `0x18000c194`
- `0x18000c1cc`
- `0x18000c204`
- `0x18000c23c`
- `0x18000c274`
- `0x18000c2ac`
- `0x18000c2e4`
- `0x18000c31c`
- `0x18000c354`
- `0x18000c38c`
- `0x18000c3c4`
- `0x18000c3fc`
- `0x18000c434`
- `0x18000c46c`
- `0x18000c4a4`
- `0x18000c4dc`
- `0x18000c514`
- `0x18000c54c`
- `0x18000c584`
- `0x18000c5bc`
- `0x18000c5f4`
- `0x18000c62c`
- `0x18000c664`
- `0x18000c69c`
- `0x18000c6d4`
- `0x18000c70c`
- `0x18000c744`
- `0x18000c77c`
- `0x18000c8c8`
- `0x18000cd50`
- `0x18000cdac`
- `0x18000ce08`
- `0x18000ce64`
- `0x18000cec0`
- `0x18000cfd0`
- `0x18000d0a0`
- `0x18000d168`
- `0x18000d1b0`
- `0x18000d22c`
- `0x18000d2c0`
- `0x18000d31c`
- `0x18000d384`
- `0x18000d43c`
- `0x18000d4ac`
- `0x18000d51c`
- `0x18000d584`

## callees

- `0x1800069b8`
- `0x180006a18`
- `0x18000c8f8`
- `0x18000f790`
- `0x180013e70`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18000ca8a`
- `KERNEL32!FreeLibrary` at `0x18000ca8a`
- `KERNEL32!GetProcAddress` at `0x18000ca96`
- `KERNEL32!GetProcAddress` at `0x18000ca96`
- `KERNEL32!GetLastError` at `0x18000c977`
- `KERNEL32!GetLastError` at `0x18000c977`
- `KERNEL32!VirtualProtect` at `0x18000ca15`
- `KERNEL32!VirtualProtect` at `0x18000ca46`
- `KERNEL32!VirtualProtect` at `0x18000ca15`
- `KERNEL32!VirtualProtect` at `0x18000ca46`
- `KERNEL32!LoadLibraryExW` at `0x18000c965`
- `KERNEL32!LoadLibraryExW` at `0x18000c9b9`
- `KERNEL32!LoadLibraryExW` at `0x18000c965`
- `KERNEL32!LoadLibraryExW` at `0x18000c9b9`

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
    Library = (HMODULE)qword_180078480[v8];
    if ( !Library )
      break;
    if ( Library != (HMODULE)-1LL )
      goto LABEL_20;
LABEL_11:
    if ( ++v6 == a4 )
      goto LABEL_12;
  }
  v10 = off_180063AB0[v8];
  Library = LoadLibraryExW(v10, 0, 0x800u);
  if ( !Library
    && (GetLastError() != 87
     || !wcsncmp(v10, L"api-ms-", 7u)
     || !wcsncmp(v10, L"ext-ms-", 7u)
     || (Library = LoadLibraryExW(v10, 0, 0)) == 0) )
  {
    _InterlockedExchange64(&qword_180078480[v8], -1);
    goto LABEL_11;
  }
  if ( _InterlockedExchange64(&qword_180078480[v8], (__int64)Library) )
    FreeLibrary(Library);
LABEL_20:
  ProcAddress = GetProcAddress(Library, a2);
LABEL_13:
  _acrt_lock(14);
  flOldProtect = 0;
  if ( !VirtualProtect(qword_18007F000, 0x100u, 4u, &flOldProtect) )
    goto LABEL_21;
  v12 = (__int64)ProcAddress;
  if ( !ProcAddress )
    v12 = -1;
  _InterlockedExchange64(&qword_18007F000[v4], v12);
  if ( !VirtualProtect(qword_18007F000, 0x100u, 2u, &flOldProtect) )
LABEL_21:
    abort();
  _acrt_unlock(14);
  return ProcAddress;
}

```

## disassembly

```asm
0x18000c8f8  mov     [rsp+arg_0], rbx
0x18000c8fd  mov     [rsp+arg_8], rbp
0x18000c902  mov     [rsp+arg_18], rsi
0x18000c907  push    rdi
0x18000c908  push    r12
0x18000c90a  push    r13
0x18000c90c  push    r14
0x18000c90e  push    r15
0x18000c910  sub     rsp, 20h
0x18000c914  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c918  mov     r12d, ecx
0x18000c91b  mov     r14, r9
0x18000c91e  mov     rsi, r8
0x18000c921  mov     r15, rdx
0x18000c924  cmp     r8, r9
0x18000c927  jz      loc_18000C9E8
0x18000c92d  lea     r13, cs:180000000h
0x18000c934  mov     edi, [rsi]
0x18000c936  mov     rbx, rva qword_180078480[r13+rdi*8]
0x18000c93e  nop
0x18000c93f  test    rbx, rbx
0x18000c942  jz      short loc_18000C952
0x18000c944  cmp     rbx, rax
0x18000c947  jnz     loc_18000CA90
0x18000c94d  jmp     loc_18000C9DB
0x18000c952  mov     rbp, ds:rva off_180063AB0[r13+rdi*8]; "api-ms-win-core-datetime-l1-1-1" ...
0x18000c95a  xor     edx, edx; hFile
0x18000c95c  mov     rcx, rbp; lpLibFileName
0x18000c95f  mov     r8d, 800h; dwFlags
0x18000c965  call    cs:__imp_LoadLibraryExW
0x18000c96b  mov     rbx, rax
0x18000c96e  test    rax, rax
0x18000c971  jnz     loc_18000CA77
0x18000c977  call    cs:__imp_GetLastError
0x18000c97d  cmp     eax, 57h ; 'W'
0x18000c980  jnz     short loc_18000C9CB
0x18000c982  lea     ebx, [rax-50h]
0x18000c985  mov     rcx, rbp; String1
0x18000c988  mov     r8d, ebx; MaxCount
0x18000c98b  lea     rdx, aApiMs; "api-ms-"
0x18000c992  call    wcsncmp
0x18000c997  test    eax, eax
0x18000c999  jz      short loc_18000C9CB
0x18000c99b  mov     r8d, ebx; MaxCount
0x18000c99e  lea     rdx, aExtMs; "ext-ms-"
0x18000c9a5  mov     rcx, rbp; String1
0x18000c9a8  call    wcsncmp
0x18000c9ad  test    eax, eax
0x18000c9af  jz      short loc_18000C9CB
0x18000c9b1  xor     r8d, r8d; dwFlags
0x18000c9b4  xor     edx, edx; hFile
0x18000c9b6  mov     rcx, rbp; lpLibFileName
0x18000c9b9  call    cs:__imp_LoadLibraryExW
0x18000c9bf  mov     rbx, rax
0x18000c9c2  test    rax, rax
0x18000c9c5  jnz     loc_18000CA77
0x18000c9cb  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c9cf  xchg    rax, rva qword_180078480[r13+rdi*8]
0x18000c9d7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c9db  add     rsi, 4
0x18000c9df  cmp     rsi, r14
0x18000c9e2  jnz     loc_18000C934
0x18000c9e8  xor     ebx, ebx
0x18000c9ea  mov     edi, 0Eh
0x18000c9ef  mov     ecx, edi
0x18000c9f1  call    __acrt_lock
0x18000c9f6  and     [rsp+48h+flOldProtect], 0
0x18000c9fb  lea     rsi, qword_18007F000
0x18000ca02  mov     ebp, 100h
0x18000ca07  lea     r9, [rsp+48h+flOldProtect]; lpflOldProtect
0x18000ca0c  mov     edx, ebp; dwSize
0x18000ca0e  lea     r8d, [rdi-0Ah]; flNewProtect
0x18000ca12  mov     rcx, rsi; lpAddress
0x18000ca15  call    cs:__imp_VirtualProtect
0x18000ca1b  test    eax, eax
0x18000ca1d  jz      loc_18000CAA4
0x18000ca23  test    rbx, rbx
0x18000ca26  mov     rax, rbx
0x18000ca29  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000ca30  cmovz   rax, rcx
0x18000ca34  xchg    rax, [rsi+r12*8]
0x18000ca38  lea     r9, [rsp+48h+flOldProtect]; lpflOldProtect
0x18000ca3d  mov     edx, ebp; dwSize
0x18000ca3f  lea     r8d, [rdi-0Ch]; flNewProtect
0x18000ca43  mov     rcx, rsi; lpAddress
0x18000ca46  call    cs:__imp_VirtualProtect
0x18000ca4c  test    eax, eax
0x18000ca4e  jz      short loc_18000CAA4
0x18000ca50  mov     ecx, edi
0x18000ca52  call    __acrt_unlock
0x18000ca57  mov     rbp, [rsp+48h+arg_8]
0x18000ca5c  mov     rax, rbx
0x18000ca5f  mov     rbx, [rsp+48h+arg_0]
0x18000ca64  mov     rsi, [rsp+48h+arg_18]
0x18000ca69  add     rsp, 20h
0x18000ca6d  pop     r15
0x18000ca6f  pop     r14
0x18000ca71  pop     r13
0x18000ca73  pop     r12
0x18000ca75  pop     rdi
0x18000ca76  retn
0x18000ca77  mov     rax, rbx
0x18000ca7a  xchg    rax, rva qword_180078480[r13+rdi*8]
0x18000ca82  test    rax, rax
0x18000ca85  jz      short loc_18000CA90
0x18000ca87  mov     rcx, rbx; hLibModule
0x18000ca8a  call    cs:__imp_FreeLibrary
0x18000ca90  mov     rdx, r15; lpProcName
0x18000ca93  mov     rcx, rbx; hModule
0x18000ca96  call    cs:__imp_GetProcAddress
0x18000ca9c  mov     rbx, rax
0x18000ca9f  jmp     loc_18000C9EA
0x18000caa4  call    abort
```
