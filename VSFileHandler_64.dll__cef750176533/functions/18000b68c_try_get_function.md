# try_get_function

- ea: `0x18000b68c`
- end: `0x18000b7db`
- name: `try_get_function`
- size: `335`
- prototype: `FARPROC __fastcall(unsigned int, const CHAR *, unsigned int *, unsigned int *)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b7dc`
- `0x18000b824`
- `0x18000b86c`
- `0x18000b8b4`
- `0x18000b908`

## callees

- `0x18000b68c`
- `0x18000fe10`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18000b7b7`
- `KERNEL32!FreeLibrary` at `0x18000b7b7`
- `KERNEL32!LoadLibraryExW` at `0x18000b711`
- `KERNEL32!LoadLibraryExW` at `0x18000b749`
- `KERNEL32!LoadLibraryExW` at `0x18000b711`
- `KERNEL32!LoadLibraryExW` at `0x18000b749`
- `KERNEL32!GetLastError` at `0x18000b71f`
- `KERNEL32!GetLastError` at `0x18000b71f`
- `KERNEL32!GetProcAddress` at `0x18000b7c3`
- `KERNEL32!GetProcAddress` at `0x18000b7c3`

## pseudocode

```c
FARPROC __fastcall try_get_function(unsigned int a1, const CHAR *a2, unsigned int *a3, unsigned int *a4)
{
  __int64 v4; // rdi
  unsigned int *v6; // rbp
  FARPROC result; // rax
  __int64 v9; // rsi
  HMODULE Library; // rbx
  const WCHAR *v11; // r15

  v4 = a1;
  v6 = a3;
  result = (FARPROC)qword_18003E2D8[a1];
  if ( result == (FARPROC)-1LL )
    return 0;
  if ( !result )
  {
    if ( a3 == a4 )
      goto LABEL_13;
    while ( 1 )
    {
      v9 = *v6;
      Library = (HMODULE)qword_18003E2C0[v9];
      if ( Library )
      {
        if ( Library != (HMODULE)-1LL )
          goto LABEL_18;
      }
      else
      {
        v11 = off_1800276B8[v9];
        Library = LoadLibraryExW(v11, 0, 0x800u);
        if ( Library
          || GetLastError() == 87 && wcsncmp(v11, L"api-ms-", 7u) && (Library = LoadLibraryExW(v11, 0, 0)) != 0 )
        {
          if ( _InterlockedExchange64(&qword_18003E2C0[v9], (__int64)Library) )
            FreeLibrary(Library);
LABEL_18:
          result = GetProcAddress(Library, a2);
          if ( result )
          {
            _InterlockedExchange64(&qword_18003E2D8[v4], (__int64)result);
            return result;
          }
LABEL_13:
          _InterlockedExchange64(&qword_18003E2D8[v4], -1);
          return 0;
        }
        _InterlockedExchange64(&qword_18003E2C0[v9], -1);
      }
      if ( ++v6 == a4 )
        goto LABEL_13;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000b68c  mov     [rsp+arg_0], rbx
0x18000b691  mov     [rsp+arg_8], rbp
0x18000b696  mov     [rsp+arg_10], rsi
0x18000b69b  push    rdi
0x18000b69c  push    r12
0x18000b69e  push    r13
0x18000b6a0  push    r14
0x18000b6a2  push    r15
0x18000b6a4  sub     rsp, 20h
0x18000b6a8  mov     edi, ecx
0x18000b6aa  lea     r15, cs:180000000h
0x18000b6b1  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000b6b5  mov     r12, r9
0x18000b6b8  mov     rbp, r8
0x18000b6bb  mov     r13, rdx
0x18000b6be  mov     rax, rva qword_18003E2D8[r15+rdi*8]
0x18000b6c6  nop
0x18000b6c7  cmp     rax, r14
0x18000b6ca  jz      loc_18000B77E
0x18000b6d0  test    rax, rax
0x18000b6d3  jnz     loc_18000B780
0x18000b6d9  cmp     r8, r9
0x18000b6dc  jz      loc_18000B776
0x18000b6e2  mov     esi, [rbp+0]
0x18000b6e5  mov     rbx, rva qword_18003E2C0[r15+rsi*8]
0x18000b6ed  nop
0x18000b6ee  test    rbx, rbx
0x18000b6f1  jz      short loc_18000B6FE
0x18000b6f3  cmp     rbx, r14
0x18000b6f6  jnz     loc_18000B7BD
0x18000b6fc  jmp     short loc_18000B769
0x18000b6fe  mov     r15, ds:rva off_1800276B8[r15+rsi*8]; "api-ms-win-core-fibers-l1-1-1" ...
0x18000b706  xor     edx, edx; hFile
0x18000b708  mov     rcx, r15; lpLibFileName
0x18000b70b  mov     r8d, 800h; dwFlags
0x18000b711  call    cs:__imp_LoadLibraryExW
0x18000b717  mov     rbx, rax
0x18000b71a  test    rax, rax
0x18000b71d  jnz     short loc_18000B79D
0x18000b71f  call    cs:__imp_GetLastError
0x18000b725  cmp     eax, 57h ; 'W'
0x18000b728  jnz     short loc_18000B757
0x18000b72a  lea     r8d, [rbx+7]; MaxCount
0x18000b72e  mov     rcx, r15; String1
0x18000b731  lea     rdx, aApiMs; "api-ms-"
0x18000b738  call    wcsncmp
0x18000b73d  test    eax, eax
0x18000b73f  jz      short loc_18000B757
0x18000b741  xor     r8d, r8d; dwFlags
0x18000b744  xor     edx, edx; hFile
0x18000b746  mov     rcx, r15; lpLibFileName
0x18000b749  call    cs:__imp_LoadLibraryExW
0x18000b74f  mov     rbx, rax
0x18000b752  test    rax, rax
0x18000b755  jnz     short loc_18000B79D
0x18000b757  mov     rax, r14
0x18000b75a  lea     r15, cs:180000000h
0x18000b761  xchg    rax, rva qword_18003E2C0[r15+rsi*8]
0x18000b769  add     rbp, 4
0x18000b76d  cmp     rbp, r12
0x18000b770  jnz     loc_18000B6E2
0x18000b776  xchg    r14, rva qword_18003E2D8[r15+rdi*8]
0x18000b77e  xor     eax, eax
0x18000b780  mov     rbx, [rsp+48h+arg_0]
0x18000b785  mov     rbp, [rsp+48h+arg_8]
0x18000b78a  mov     rsi, [rsp+48h+arg_10]
0x18000b78f  add     rsp, 20h
0x18000b793  pop     r15
0x18000b795  pop     r14
0x18000b797  pop     r13
0x18000b799  pop     r12
0x18000b79b  pop     rdi
0x18000b79c  retn
0x18000b79d  mov     rax, rbx
0x18000b7a0  lea     r15, cs:180000000h
0x18000b7a7  xchg    rax, rva qword_18003E2C0[r15+rsi*8]
0x18000b7af  test    rax, rax
0x18000b7b2  jz      short loc_18000B7BD
0x18000b7b4  mov     rcx, rbx; hLibModule
0x18000b7b7  call    cs:__imp_FreeLibrary
0x18000b7bd  mov     rdx, r13; lpProcName
0x18000b7c0  mov     rcx, rbx; hModule
0x18000b7c3  call    cs:__imp_GetProcAddress
0x18000b7c9  test    rax, rax
0x18000b7cc  jz      short loc_18000B776
0x18000b7ce  mov     rcx, rax
0x18000b7d1  xchg    rcx, rva qword_18003E2D8[r15+rdi*8]
0x18000b7d9  jmp     short loc_18000B780
```
