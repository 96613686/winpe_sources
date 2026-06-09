# try_get_first_available_module

- ea: `0x18000cf14`
- end: `0x18000d027`
- name: `try_get_first_available_module`
- size: `275`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000cf14`
- `0x1800145d0`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18000cf74`
- `KERNEL32!LoadLibraryExW` at `0x18000cfc7`
- `KERNEL32!LoadLibraryExW` at `0x18000cf74`
- `KERNEL32!LoadLibraryExW` at `0x18000cfc7`
- `KERNEL32!FreeLibrary` at `0x18000d01c`
- `KERNEL32!FreeLibrary` at `0x18000d01c`
- `KERNEL32!GetLastError` at `0x18000cf86`
- `KERNEL32!GetLastError` at `0x18000cf86`

## pseudocode

```c
HMODULE __fastcall try_get_first_available_module(unsigned int *a1, unsigned int *a2)
{
  unsigned int *v3; // rdi
  __int64 v4; // rsi
  HMODULE Library; // rbx
  const WCHAR *v6; // r14

  v3 = a1;
  if ( a1 == a2 )
    return 0;
  while ( 1 )
  {
    v4 = *v3;
    Library = (HMODULE)qword_18007BF30[v4];
    if ( !Library )
      break;
    if ( Library != (HMODULE)-1LL )
      return Library;
LABEL_11:
    if ( ++v3 == a2 )
      return 0;
  }
  v6 = off_180067190[v4];
  Library = LoadLibraryExW(v6, 0, 0x800u);
  if ( !Library
    && (GetLastError() != 87
     || !wcsncmp(v6, L"api-ms-", 7u)
     || !wcsncmp(v6, L"ext-ms-", 7u)
     || (Library = LoadLibraryExW(v6, 0, 0)) == 0) )
  {
    _InterlockedExchange64(&qword_18007BF30[v4], -1);
    goto LABEL_11;
  }
  if ( _InterlockedExchange64(&qword_18007BF30[v4], (__int64)Library) )
    FreeLibrary(Library);
  return Library;
}

```

## disassembly

```asm
0x18000cf14  mov     [rsp+arg_0], rbx
0x18000cf19  mov     [rsp+arg_8], rbp
0x18000cf1e  mov     [rsp+arg_10], rsi
0x18000cf23  push    rdi
0x18000cf24  push    r14
0x18000cf26  push    r15
0x18000cf28  sub     rsp, 20h
0x18000cf2c  mov     rbp, rdx
0x18000cf2f  mov     rdi, rcx
0x18000cf32  cmp     rcx, rdx
0x18000cf35  jz      loc_18000CFEE
0x18000cf3b  lea     r15, cs:180000000h
0x18000cf42  mov     esi, [rdi]
0x18000cf44  mov     rbx, rva qword_18007BF30[r15+rsi*8]
0x18000cf4c  nop
0x18000cf4d  test    rbx, rbx
0x18000cf50  jz      short loc_18000CF61
0x18000cf52  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000cf56  jnz     loc_18000D022
0x18000cf5c  jmp     loc_18000CFE1
0x18000cf61  mov     r14, ds:rva off_180067190[r15+rsi*8]; "api-ms-win-core-datetime-l1-1-1" ...
0x18000cf69  xor     edx, edx; hFile
0x18000cf6b  mov     rcx, r14; lpLibFileName
0x18000cf6e  mov     r8d, 800h; dwFlags
0x18000cf74  call    cs:__imp_LoadLibraryExW
0x18000cf7a  mov     rbx, rax
0x18000cf7d  test    rax, rax
0x18000cf80  jnz     loc_18000D009
0x18000cf86  call    cs:__imp_GetLastError
0x18000cf8c  cmp     eax, 57h ; 'W'
0x18000cf8f  jnz     short loc_18000CFD5
0x18000cf91  lea     r8d, [rbx+7]; MaxCount
0x18000cf95  mov     rcx, r14; String1
0x18000cf98  lea     rdx, aApiMs; "api-ms-"
0x18000cf9f  call    wcsncmp
0x18000cfa4  test    eax, eax
0x18000cfa6  jz      short loc_18000CFD5
0x18000cfa8  lea     r8d, [rbx+7]; MaxCount
0x18000cfac  mov     rcx, r14; String1
0x18000cfaf  lea     rdx, aExtMs; "ext-ms-"
0x18000cfb6  call    wcsncmp
0x18000cfbb  test    eax, eax
0x18000cfbd  jz      short loc_18000CFD5
0x18000cfbf  xor     r8d, r8d; dwFlags
0x18000cfc2  xor     edx, edx; hFile
0x18000cfc4  mov     rcx, r14; lpLibFileName
0x18000cfc7  call    cs:__imp_LoadLibraryExW
0x18000cfcd  mov     rbx, rax
0x18000cfd0  test    rax, rax
0x18000cfd3  jnz     short loc_18000D009
0x18000cfd5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000cfd9  xchg    rax, rva qword_18007BF30[r15+rsi*8]
0x18000cfe1  add     rdi, 4
0x18000cfe5  cmp     rdi, rbp
0x18000cfe8  jnz     loc_18000CF42
0x18000cfee  xor     eax, eax
0x18000cff0  mov     rbx, [rsp+38h+arg_0]
0x18000cff5  mov     rbp, [rsp+38h+arg_8]
0x18000cffa  mov     rsi, [rsp+38h+arg_10]
0x18000cfff  add     rsp, 20h
0x18000d003  pop     r15
0x18000d005  pop     r14
0x18000d007  pop     rdi
0x18000d008  retn
0x18000d009  mov     rcx, rbx
0x18000d00c  xchg    rcx, rva qword_18007BF30[r15+rsi*8]
0x18000d014  test    rcx, rcx
0x18000d017  jz      short loc_18000D022
0x18000d019  mov     rcx, rbx; hLibModule
0x18000d01c  call    cs:__imp_FreeLibrary
0x18000d022  mov     rax, rbx
0x18000d025  jmp     short loc_18000CFF0
```
