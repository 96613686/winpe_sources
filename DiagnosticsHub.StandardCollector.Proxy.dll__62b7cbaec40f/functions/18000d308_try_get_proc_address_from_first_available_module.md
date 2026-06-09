# try_get_proc_address_from_first_available_module

- ea: `0x18000d308`
- end: `0x18000d432`
- name: `try_get_proc_address_from_first_available_module`
- size: `298`
- prototype: `__int64 __fastcall(LPCSTR lpProcName)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000d308`
- `0x1800145d0`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18000d370`
- `KERNEL32!LoadLibraryExW` at `0x18000d3c3`
- `KERNEL32!LoadLibraryExW` at `0x18000d370`
- `KERNEL32!LoadLibraryExW` at `0x18000d3c3`
- `KERNEL32!FreeLibrary` at `0x18000d41e`
- `KERNEL32!FreeLibrary` at `0x18000d41e`
- `KERNEL32!GetProcAddress` at `0x18000d42a`
- `KERNEL32!GetProcAddress` at `0x18000d42a`
- `KERNEL32!GetLastError` at `0x18000d382`
- `KERNEL32!GetLastError` at `0x18000d382`

## pseudocode

```c
FARPROC __fastcall try_get_proc_address_from_first_available_module(LPCSTR lpProcName, unsigned int *a2, unsigned int *a3)
{
  unsigned int *v4; // rdi
  __int64 v6; // rsi
  HMODULE Library; // rbx
  const WCHAR *v8; // rbp

  v4 = a2;
  if ( a2 == a3 )
    return 0;
  while ( 1 )
  {
    v6 = *v4;
    Library = (HMODULE)qword_18007BF30[v6];
    if ( !Library )
      break;
    if ( Library != (HMODULE)-1LL )
      return GetProcAddress(Library, lpProcName);
LABEL_11:
    if ( ++v4 == a3 )
      return 0;
  }
  v8 = off_180067190[v6];
  Library = LoadLibraryExW(v8, 0, 0x800u);
  if ( !Library
    && (GetLastError() != 87
     || !wcsncmp(v8, L"api-ms-", 7u)
     || !wcsncmp(v8, L"ext-ms-", 7u)
     || (Library = LoadLibraryExW(v8, 0, 0)) == 0) )
  {
    _InterlockedExchange64(&qword_18007BF30[v6], -1);
    goto LABEL_11;
  }
  if ( _InterlockedExchange64(&qword_18007BF30[v6], (__int64)Library) )
    FreeLibrary(Library);
  return GetProcAddress(Library, lpProcName);
}

```

## disassembly

```asm
0x18000d308  mov     rax, rsp
0x18000d30b  mov     [rax+8], rbx
0x18000d30f  mov     [rax+10h], rbp
0x18000d313  mov     [rax+18h], rsi
0x18000d317  mov     [rax+20h], rdi
0x18000d31b  push    r12
0x18000d31d  push    r14
0x18000d31f  push    r15
0x18000d321  sub     rsp, 20h
0x18000d325  mov     r14, r8
0x18000d328  mov     rdi, rdx
0x18000d32b  mov     r15, rcx
0x18000d32e  cmp     rdx, r8
0x18000d331  jz      loc_18000D3EA
0x18000d337  lea     r12, cs:180000000h
0x18000d33e  mov     esi, [rdi]
0x18000d340  mov     rbx, rva qword_18007BF30[r12+rsi*8]
0x18000d348  nop
0x18000d349  test    rbx, rbx
0x18000d34c  jz      short loc_18000D35D
0x18000d34e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000d352  jnz     loc_18000D424
0x18000d358  jmp     loc_18000D3DD
0x18000d35d  mov     rbp, ds:rva off_180067190[r12+rsi*8]; "api-ms-win-core-datetime-l1-1-1" ...
0x18000d365  xor     edx, edx; hFile
0x18000d367  mov     rcx, rbp; lpLibFileName
0x18000d36a  mov     r8d, 800h; dwFlags
0x18000d370  call    cs:__imp_LoadLibraryExW
0x18000d376  mov     rbx, rax
0x18000d379  test    rax, rax
0x18000d37c  jnz     loc_18000D40B
0x18000d382  call    cs:__imp_GetLastError
0x18000d388  cmp     eax, 57h ; 'W'
0x18000d38b  jnz     short loc_18000D3D1
0x18000d38d  lea     r8d, [rbx+7]; MaxCount
0x18000d391  mov     rcx, rbp; String1
0x18000d394  lea     rdx, aApiMs; "api-ms-"
0x18000d39b  call    wcsncmp
0x18000d3a0  test    eax, eax
0x18000d3a2  jz      short loc_18000D3D1
0x18000d3a4  lea     r8d, [rbx+7]; MaxCount
0x18000d3a8  mov     rcx, rbp; String1
0x18000d3ab  lea     rdx, aExtMs; "ext-ms-"
0x18000d3b2  call    wcsncmp
0x18000d3b7  test    eax, eax
0x18000d3b9  jz      short loc_18000D3D1
0x18000d3bb  xor     r8d, r8d; dwFlags
0x18000d3be  xor     edx, edx; hFile
0x18000d3c0  mov     rcx, rbp; lpLibFileName
0x18000d3c3  call    cs:__imp_LoadLibraryExW
0x18000d3c9  mov     rbx, rax
0x18000d3cc  test    rax, rax
0x18000d3cf  jnz     short loc_18000D40B
0x18000d3d1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d3d5  xchg    rax, rva qword_18007BF30[r12+rsi*8]
0x18000d3dd  add     rdi, 4
0x18000d3e1  cmp     rdi, r14
0x18000d3e4  jnz     loc_18000D33E
0x18000d3ea  xor     eax, eax
0x18000d3ec  mov     rbx, [rsp+38h+arg_0]
0x18000d3f1  mov     rbp, [rsp+38h+arg_8]
0x18000d3f6  mov     rsi, [rsp+38h+arg_10]
0x18000d3fb  mov     rdi, [rsp+38h+arg_18]
0x18000d400  add     rsp, 20h
0x18000d404  pop     r15
0x18000d406  pop     r14
0x18000d408  pop     r12
0x18000d40a  retn
0x18000d40b  mov     rax, rbx
0x18000d40e  xchg    rax, rva qword_18007BF30[r12+rsi*8]
0x18000d416  test    rax, rax
0x18000d419  jz      short loc_18000D424
0x18000d41b  mov     rcx, rbx; hLibModule
0x18000d41e  call    cs:__imp_FreeLibrary
0x18000d424  mov     rdx, r15; lpProcName
0x18000d427  mov     rcx, rbx; hModule
0x18000d42a  call    cs:__imp_GetProcAddress
0x18000d430  jmp     short loc_18000D3EC
```
