# try_get_function_slow

- ea: `0x18000d058`
- end: `0x18000d20a`
- name: `try_get_function_slow`
- size: `434`
- prototype: ``
- caller_count: `65`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000c814`
- `0x18000c84c`
- `0x18000c884`
- `0x18000c8bc`
- `0x18000c8f4`
- `0x18000c92c`
- `0x18000c964`
- `0x18000c99c`
- `0x18000c9d4`
- `0x18000ca0c`
- `0x18000ca44`
- `0x18000ca7c`
- `0x18000cab4`
- `0x18000caec`
- `0x18000cb24`
- `0x18000cb5c`
- `0x18000cb94`
- `0x18000cbcc`
- `0x18000cc04`
- `0x18000cc3c`
- `0x18000cc74`
- `0x18000ccac`
- `0x18000cce4`
- `0x18000cd1c`
- `0x18000cd54`
- `0x18000cd8c`
- `0x18000cdc4`
- `0x18000cdfc`
- `0x18000ce34`
- `0x18000ce6c`
- `0x18000cea4`
- `0x18000cedc`
- `0x18000d028`
- `0x18000d4b0`
- `0x18000d50c`
- `0x18000d568`
- `0x18000d5c4`
- `0x18000d620`
- `0x18000d730`
- `0x18000d800`
- `0x18000d8c8`
- `0x18000d910`
- `0x18000d98c`
- `0x18000da20`
- `0x18000da7c`
- `0x18000dae4`
- `0x18000db9c`
- `0x18000dc0c`
- `0x18000dc7c`
- `0x18000dce4`

## callees

- `0x180007118`
- `0x180007178`
- `0x18000d058`
- `0x18000fef0`
- `0x1800145d0`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18000d0c5`
- `KERNEL32!LoadLibraryExW` at `0x18000d119`
- `KERNEL32!LoadLibraryExW` at `0x18000d0c5`
- `KERNEL32!LoadLibraryExW` at `0x18000d119`
- `KERNEL32!VirtualProtect` at `0x18000d175`
- `KERNEL32!VirtualProtect` at `0x18000d1a6`
- `KERNEL32!VirtualProtect` at `0x18000d175`
- `KERNEL32!VirtualProtect` at `0x18000d1a6`
- `KERNEL32!FreeLibrary` at `0x18000d1ea`
- `KERNEL32!FreeLibrary` at `0x18000d1ea`
- `KERNEL32!GetProcAddress` at `0x18000d1f6`
- `KERNEL32!GetProcAddress` at `0x18000d1f6`
- `KERNEL32!GetLastError` at `0x18000d0d7`
- `KERNEL32!GetLastError` at `0x18000d0d7`

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
    Library = (HMODULE)qword_18007BF30[v8];
    if ( !Library )
      break;
    if ( Library != (HMODULE)-1LL )
      goto LABEL_20;
LABEL_11:
    if ( ++v6 == a4 )
      goto LABEL_12;
  }
  v10 = off_180067190[v8];
  Library = LoadLibraryExW(v10, 0, 0x800u);
  if ( !Library
    && (GetLastError() != 87
     || !wcsncmp(v10, L"api-ms-", 7u)
     || !wcsncmp(v10, L"ext-ms-", 7u)
     || (Library = LoadLibraryExW(v10, 0, 0)) == 0) )
  {
    _InterlockedExchange64(&qword_18007BF30[v8], -1);
    goto LABEL_11;
  }
  if ( _InterlockedExchange64(&qword_18007BF30[v8], (__int64)Library) )
    FreeLibrary(Library);
LABEL_20:
  ProcAddress = GetProcAddress(Library, a2);
LABEL_13:
  _acrt_lock(14);
  flOldProtect = 0;
  if ( !VirtualProtect(qword_180082000, 0x100u, 4u, &flOldProtect) )
    goto LABEL_21;
  v12 = (__int64)ProcAddress;
  if ( !ProcAddress )
    v12 = -1;
  _InterlockedExchange64(&qword_180082000[v4], v12);
  if ( !VirtualProtect(qword_180082000, 0x100u, 2u, &flOldProtect) )
LABEL_21:
    abort();
  _acrt_unlock(14);
  return ProcAddress;
}

```

## disassembly

```asm
0x18000d058  mov     [rsp+arg_0], rbx
0x18000d05d  mov     [rsp+arg_8], rbp
0x18000d062  mov     [rsp+arg_18], rsi
0x18000d067  push    rdi
0x18000d068  push    r12
0x18000d06a  push    r13
0x18000d06c  push    r14
0x18000d06e  push    r15
0x18000d070  sub     rsp, 20h
0x18000d074  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d078  mov     r12d, ecx
0x18000d07b  mov     r14, r9
0x18000d07e  mov     rsi, r8
0x18000d081  mov     r15, rdx
0x18000d084  cmp     r8, r9
0x18000d087  jz      loc_18000D148
0x18000d08d  lea     r13, cs:180000000h
0x18000d094  mov     edi, [rsi]
0x18000d096  mov     rbx, rva qword_18007BF30[r13+rdi*8]
0x18000d09e  nop
0x18000d09f  test    rbx, rbx
0x18000d0a2  jz      short loc_18000D0B2
0x18000d0a4  cmp     rbx, rax
0x18000d0a7  jnz     loc_18000D1F0
0x18000d0ad  jmp     loc_18000D13B
0x18000d0b2  mov     rbp, ds:rva off_180067190[r13+rdi*8]; "api-ms-win-core-datetime-l1-1-1" ...
0x18000d0ba  xor     edx, edx; hFile
0x18000d0bc  mov     rcx, rbp; lpLibFileName
0x18000d0bf  mov     r8d, 800h; dwFlags
0x18000d0c5  call    cs:__imp_LoadLibraryExW
0x18000d0cb  mov     rbx, rax
0x18000d0ce  test    rax, rax
0x18000d0d1  jnz     loc_18000D1D7
0x18000d0d7  call    cs:__imp_GetLastError
0x18000d0dd  cmp     eax, 57h ; 'W'
0x18000d0e0  jnz     short loc_18000D12B
0x18000d0e2  lea     ebx, [rax-50h]
0x18000d0e5  mov     rcx, rbp; String1
0x18000d0e8  mov     r8d, ebx; MaxCount
0x18000d0eb  lea     rdx, aApiMs; "api-ms-"
0x18000d0f2  call    wcsncmp
0x18000d0f7  test    eax, eax
0x18000d0f9  jz      short loc_18000D12B
0x18000d0fb  mov     r8d, ebx; MaxCount
0x18000d0fe  lea     rdx, aExtMs; "ext-ms-"
0x18000d105  mov     rcx, rbp; String1
0x18000d108  call    wcsncmp
0x18000d10d  test    eax, eax
0x18000d10f  jz      short loc_18000D12B
0x18000d111  xor     r8d, r8d; dwFlags
0x18000d114  xor     edx, edx; hFile
0x18000d116  mov     rcx, rbp; lpLibFileName
0x18000d119  call    cs:__imp_LoadLibraryExW
0x18000d11f  mov     rbx, rax
0x18000d122  test    rax, rax
0x18000d125  jnz     loc_18000D1D7
0x18000d12b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d12f  xchg    rax, rva qword_18007BF30[r13+rdi*8]
0x18000d137  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d13b  add     rsi, 4
0x18000d13f  cmp     rsi, r14
0x18000d142  jnz     loc_18000D094
0x18000d148  xor     ebx, ebx
0x18000d14a  mov     edi, 0Eh
0x18000d14f  mov     ecx, edi
0x18000d151  call    __acrt_lock
0x18000d156  and     [rsp+48h+flOldProtect], 0
0x18000d15b  lea     rsi, qword_180082000
0x18000d162  mov     ebp, 100h
0x18000d167  lea     r9, [rsp+48h+flOldProtect]; lpflOldProtect
0x18000d16c  mov     edx, ebp; dwSize
0x18000d16e  lea     r8d, [rdi-0Ah]; flNewProtect
0x18000d172  mov     rcx, rsi; lpAddress
0x18000d175  call    cs:__imp_VirtualProtect
0x18000d17b  test    eax, eax
0x18000d17d  jz      loc_18000D204
0x18000d183  test    rbx, rbx
0x18000d186  mov     rax, rbx
0x18000d189  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000d190  cmovz   rax, rcx
0x18000d194  xchg    rax, [rsi+r12*8]
0x18000d198  lea     r9, [rsp+48h+flOldProtect]; lpflOldProtect
0x18000d19d  mov     edx, ebp; dwSize
0x18000d19f  lea     r8d, [rdi-0Ch]; flNewProtect
0x18000d1a3  mov     rcx, rsi; lpAddress
0x18000d1a6  call    cs:__imp_VirtualProtect
0x18000d1ac  test    eax, eax
0x18000d1ae  jz      short loc_18000D204
0x18000d1b0  mov     ecx, edi
0x18000d1b2  call    __acrt_unlock
0x18000d1b7  mov     rbp, [rsp+48h+arg_8]
0x18000d1bc  mov     rax, rbx
0x18000d1bf  mov     rbx, [rsp+48h+arg_0]
0x18000d1c4  mov     rsi, [rsp+48h+arg_18]
0x18000d1c9  add     rsp, 20h
0x18000d1cd  pop     r15
0x18000d1cf  pop     r14
0x18000d1d1  pop     r13
0x18000d1d3  pop     r12
0x18000d1d5  pop     rdi
0x18000d1d6  retn
0x18000d1d7  mov     rax, rbx
0x18000d1da  xchg    rax, rva qword_18007BF30[r13+rdi*8]
0x18000d1e2  test    rax, rax
0x18000d1e5  jz      short loc_18000D1F0
0x18000d1e7  mov     rcx, rbx; hLibModule
0x18000d1ea  call    cs:__imp_FreeLibrary
0x18000d1f0  mov     rdx, r15; lpProcName
0x18000d1f3  mov     rcx, rbx; hModule
0x18000d1f6  call    cs:__imp_GetProcAddress
0x18000d1fc  mov     rbx, rax
0x18000d1ff  jmp     loc_18000D14A
0x18000d204  call    abort
```
