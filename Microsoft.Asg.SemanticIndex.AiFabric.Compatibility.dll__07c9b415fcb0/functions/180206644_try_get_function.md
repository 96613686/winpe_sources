# try_get_function

- ea: `0x180206644`
- end: `0x180206793`
- name: `try_get_function`
- size: `335`
- prototype: `FARPROC __fastcall(unsigned int, const CHAR *, unsigned int *, unsigned int *)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180206794`
- `0x1802067dc`
- `0x180206824`
- `0x18020686c`
- `0x1802068c0`

## callees

- `0x180206644`
- `0x180217aa0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1802066d7`
- `KERNEL32!GetLastError` at `0x1802066d7`
- `KERNEL32!GetProcAddress` at `0x18020677b`
- `KERNEL32!GetProcAddress` at `0x18020677b`
- `KERNEL32!FreeLibrary` at `0x18020676f`
- `KERNEL32!FreeLibrary` at `0x18020676f`
- `KERNEL32!LoadLibraryExW` at `0x1802066c9`
- `KERNEL32!LoadLibraryExW` at `0x180206701`
- `KERNEL32!LoadLibraryExW` at `0x1802066c9`
- `KERNEL32!LoadLibraryExW` at `0x180206701`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  result = (FARPROC)qword_1803E1B50[a1];
  if ( result == (FARPROC)-1LL )
    return 0;
  if ( !result )
  {
    if ( a3 == a4 )
      goto LABEL_13;
    while ( 1 )
    {
      v9 = *v6;
      Library = (HMODULE)qword_1803E1B38[v9];
      if ( Library )
      {
        if ( Library != (HMODULE)-1LL )
          goto LABEL_18;
      }
      else
      {
        v11 = off_18028F1C0[v9];
        Library = LoadLibraryExW(v11, 0, 0x800u);
        if ( Library
          || GetLastError() == 87 && wcsncmp(v11, L"api-ms-", 7u) && (Library = LoadLibraryExW(v11, 0, 0)) != 0 )
        {
          if ( _InterlockedExchange64(&qword_1803E1B38[v9], (__int64)Library) )
            FreeLibrary(Library);
LABEL_18:
          result = GetProcAddress(Library, a2);
          if ( result )
          {
            _InterlockedExchange64(&qword_1803E1B50[v4], (__int64)result);
            return result;
          }
LABEL_13:
          _InterlockedExchange64(&qword_1803E1B50[v4], -1);
          return 0;
        }
        _InterlockedExchange64(&qword_1803E1B38[v9], -1);
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
0x180206644  mov     [rsp+arg_0], rbx
0x180206649  mov     [rsp+arg_8], rbp
0x18020664e  mov     [rsp+arg_10], rsi
0x180206653  push    rdi
0x180206654  push    r12
0x180206656  push    r13
0x180206658  push    r14
0x18020665a  push    r15
0x18020665c  sub     rsp, 20h
0x180206660  mov     edi, ecx
0x180206662  lea     r15, cs:180000000h
0x180206669  or      r14, 0FFFFFFFFFFFFFFFFh
0x18020666d  mov     r12, r9
0x180206670  mov     rbp, r8
0x180206673  mov     r13, rdx
0x180206676  mov     rax, rva qword_1803E1B50[r15+rdi*8]
0x18020667e  nop
0x18020667f  cmp     rax, r14
0x180206682  jz      loc_180206736
0x180206688  test    rax, rax
0x18020668b  jnz     loc_180206738
0x180206691  cmp     r8, r9
0x180206694  jz      loc_18020672E
0x18020669a  mov     esi, [rbp+0]
0x18020669d  mov     rbx, rva qword_1803E1B38[r15+rsi*8]
0x1802066a5  nop
0x1802066a6  test    rbx, rbx
0x1802066a9  jz      short loc_1802066B6
0x1802066ab  cmp     rbx, r14
0x1802066ae  jnz     loc_180206775
0x1802066b4  jmp     short loc_180206721
0x1802066b6  mov     r15, ds:rva off_18028F1C0[r15+rsi*8]; "api-ms-win-core-fibers-l1-1-1" ...
0x1802066be  xor     edx, edx; hFile
0x1802066c0  mov     rcx, r15; lpLibFileName
0x1802066c3  mov     r8d, 800h; dwFlags
0x1802066c9  call    cs:__imp_LoadLibraryExW
0x1802066cf  mov     rbx, rax
0x1802066d2  test    rax, rax
0x1802066d5  jnz     short loc_180206755
0x1802066d7  call    cs:__imp_GetLastError
0x1802066dd  cmp     eax, 57h ; 'W'
0x1802066e0  jnz     short loc_18020670F
0x1802066e2  lea     r8d, [rbx+7]; MaxCount
0x1802066e6  mov     rcx, r15; String1
0x1802066e9  lea     rdx, aApiMs; "api-ms-"
0x1802066f0  call    wcsncmp
0x1802066f5  test    eax, eax
0x1802066f7  jz      short loc_18020670F
0x1802066f9  xor     r8d, r8d; dwFlags
0x1802066fc  xor     edx, edx; hFile
0x1802066fe  mov     rcx, r15; lpLibFileName
0x180206701  call    cs:__imp_LoadLibraryExW
0x180206707  mov     rbx, rax
0x18020670a  test    rax, rax
0x18020670d  jnz     short loc_180206755
0x18020670f  mov     rax, r14
0x180206712  lea     r15, cs:180000000h
0x180206719  xchg    rax, rva qword_1803E1B38[r15+rsi*8]
0x180206721  add     rbp, 4
0x180206725  cmp     rbp, r12
0x180206728  jnz     loc_18020669A
0x18020672e  xchg    r14, rva qword_1803E1B50[r15+rdi*8]
0x180206736  xor     eax, eax
0x180206738  mov     rbx, [rsp+48h+arg_0]
0x18020673d  mov     rbp, [rsp+48h+arg_8]
0x180206742  mov     rsi, [rsp+48h+arg_10]
0x180206747  add     rsp, 20h
0x18020674b  pop     r15
0x18020674d  pop     r14
0x18020674f  pop     r13
0x180206751  pop     r12
0x180206753  pop     rdi
0x180206754  retn
0x180206755  mov     rax, rbx
0x180206758  lea     r15, cs:180000000h
0x18020675f  xchg    rax, rva qword_1803E1B38[r15+rsi*8]
0x180206767  test    rax, rax
0x18020676a  jz      short loc_180206775
0x18020676c  mov     rcx, rbx; hLibModule
0x18020676f  call    cs:__imp_FreeLibrary
0x180206775  mov     rdx, r13; lpProcName
0x180206778  mov     rcx, rbx; hModule
0x18020677b  call    cs:__imp_GetProcAddress
0x180206781  test    rax, rax
0x180206784  jz      short loc_18020672E
0x180206786  mov     rcx, rax
0x180206789  xchg    rcx, rva qword_1803E1B50[r15+rdi*8]
0x180206791  jmp     short loc_180206738
```
