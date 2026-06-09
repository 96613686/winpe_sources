# try_get_first_available_module_0

- ea: `0x1800319c4`
- end: `0x180031ab9`
- name: `try_get_first_available_module_0`
- size: `245`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180013e70`
- `0x1800319c4`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180031aae`
- `KERNEL32!FreeLibrary` at `0x180031aae`
- `KERNEL32!GetLastError` at `0x180031a2f`
- `KERNEL32!GetLastError` at `0x180031a2f`
- `KERNEL32!LoadLibraryExW` at `0x180031a21`
- `KERNEL32!LoadLibraryExW` at `0x180031a59`
- `KERNEL32!LoadLibraryExW` at `0x180031a21`
- `KERNEL32!LoadLibraryExW` at `0x180031a59`

## pseudocode

```c
HMODULE __fastcall try_get_first_available_module_0(unsigned int *a1, unsigned int *a2)
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
    Library = (HMODULE)qword_1800790F0[v4];
    if ( !Library )
      break;
    if ( Library != (HMODULE)-1LL )
      return Library;
LABEL_10:
    if ( ++v3 == a2 )
      return 0;
  }
  v6 = off_18006B048[v4];
  Library = LoadLibraryExW(v6, 0, 0x800u);
  if ( !Library && (GetLastError() != 87 || !wcsncmp(v6, L"api-ms-", 7u) || (Library = LoadLibraryExW(v6, 0, 0)) == 0) )
  {
    _InterlockedExchange64(&qword_1800790F0[v4], -1);
    goto LABEL_10;
  }
  if ( _InterlockedExchange64(&qword_1800790F0[v4], (__int64)Library) )
    FreeLibrary(Library);
  return Library;
}

```

## disassembly

```asm
0x1800319c4  mov     [rsp+arg_0], rbx
0x1800319c9  mov     [rsp+arg_8], rbp
0x1800319ce  mov     [rsp+arg_10], rsi
0x1800319d3  push    rdi
0x1800319d4  push    r14
0x1800319d6  push    r15
0x1800319d8  sub     rsp, 20h
0x1800319dc  mov     rbp, rdx
0x1800319df  mov     rdi, rcx
0x1800319e2  cmp     rcx, rdx
0x1800319e5  jz      loc_180031A80
0x1800319eb  lea     r15, cs:180000000h
0x1800319f2  mov     esi, [rdi]
0x1800319f4  mov     rbx, rva qword_1800790F0[r15+rsi*8]
0x1800319fc  nop
0x1800319fd  test    rbx, rbx
0x180031a00  jz      short loc_180031A0E
0x180031a02  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180031a06  jnz     loc_180031AB4
0x180031a0c  jmp     short loc_180031A73
0x180031a0e  mov     r14, ds:rva off_18006B048[r15+rsi*8]; "api-ms-win-core-fibers-l1-1-1" ...
0x180031a16  xor     edx, edx; hFile
0x180031a18  mov     rcx, r14; lpLibFileName
0x180031a1b  mov     r8d, 800h; dwFlags
0x180031a21  call    cs:__imp_LoadLibraryExW
0x180031a27  mov     rbx, rax
0x180031a2a  test    rax, rax
0x180031a2d  jnz     short loc_180031A9B
0x180031a2f  call    cs:__imp_GetLastError
0x180031a35  cmp     eax, 57h ; 'W'
0x180031a38  jnz     short loc_180031A67
0x180031a3a  lea     r8d, [rbx+7]; MaxCount
0x180031a3e  mov     rcx, r14; String1
0x180031a41  lea     rdx, aApiMs; "api-ms-"
0x180031a48  call    wcsncmp
0x180031a4d  test    eax, eax
0x180031a4f  jz      short loc_180031A67
0x180031a51  xor     r8d, r8d; dwFlags
0x180031a54  xor     edx, edx; hFile
0x180031a56  mov     rcx, r14; lpLibFileName
0x180031a59  call    cs:__imp_LoadLibraryExW
0x180031a5f  mov     rbx, rax
0x180031a62  test    rax, rax
0x180031a65  jnz     short loc_180031A9B
0x180031a67  or      rax, 0FFFFFFFFFFFFFFFFh
0x180031a6b  xchg    rax, rva qword_1800790F0[r15+rsi*8]
0x180031a73  add     rdi, 4
0x180031a77  cmp     rdi, rbp
0x180031a7a  jnz     loc_1800319F2
0x180031a80  xor     eax, eax
0x180031a82  mov     rbx, [rsp+38h+arg_0]
0x180031a87  mov     rbp, [rsp+38h+arg_8]
0x180031a8c  mov     rsi, [rsp+38h+arg_10]
0x180031a91  add     rsp, 20h
0x180031a95  pop     r15
0x180031a97  pop     r14
0x180031a99  pop     rdi
0x180031a9a  retn
0x180031a9b  mov     rcx, rbx
0x180031a9e  xchg    rcx, rva qword_1800790F0[r15+rsi*8]
0x180031aa6  test    rcx, rcx
0x180031aa9  jz      short loc_180031AB4
0x180031aab  mov     rcx, rbx; hLibModule
0x180031aae  call    cs:__imp_FreeLibrary
0x180031ab4  mov     rax, rbx
0x180031ab7  jmp     short loc_180031A82
```
