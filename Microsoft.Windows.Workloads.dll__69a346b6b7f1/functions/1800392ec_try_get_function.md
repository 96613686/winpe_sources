# try_get_function

- ea: `0x1800392ec`
- end: `0x18003943b`
- name: `try_get_function`
- size: `335`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003943c`
- `0x180039484`
- `0x1800394cc`
- `0x180039514`
- `0x180039568`

## callees

- `0x1800392ec`
- `0x1800397a5`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003937f`
- `KERNEL32!GetLastError` at `0x18003937f`
- `KERNEL32!FreeLibrary` at `0x180039417`
- `KERNEL32!FreeLibrary` at `0x180039417`
- `KERNEL32!GetProcAddress` at `0x180039423`
- `KERNEL32!GetProcAddress` at `0x180039423`
- `KERNEL32!LoadLibraryExW` at `0x180039371`
- `KERNEL32!LoadLibraryExW` at `0x1800393a9`
- `KERNEL32!LoadLibraryExW` at `0x180039371`
- `KERNEL32!LoadLibraryExW` at `0x1800393a9`

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
  result = (FARPROC)qword_180059C30[a1];
  if ( result == (FARPROC)-1LL )
    return 0;
  if ( !result )
  {
    if ( a3 == a4 )
      goto LABEL_13;
    while ( 1 )
    {
      v9 = *v6;
      Library = (HMODULE)qword_180059C18[v9];
      if ( Library )
      {
        if ( Library != (HMODULE)-1LL )
          goto LABEL_18;
      }
      else
      {
        v11 = off_180047930[v9];
        Library = LoadLibraryExW(v11, 0, 0x800u);
        if ( Library
          || GetLastError() == 87 && wcsncmp_0(v11, L"api-ms-", 7u) && (Library = LoadLibraryExW(v11, 0, 0)) != 0 )
        {
          if ( _InterlockedExchange64(&qword_180059C18[v9], (__int64)Library) )
            FreeLibrary(Library);
LABEL_18:
          result = GetProcAddress(Library, a2);
          if ( result )
          {
            _InterlockedExchange64(&qword_180059C30[v4], (__int64)result);
            return result;
          }
LABEL_13:
          _InterlockedExchange64(&qword_180059C30[v4], -1);
          return 0;
        }
        _InterlockedExchange64(&qword_180059C18[v9], -1);
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
0x1800392ec  mov     [rsp+arg_0], rbx
0x1800392f1  mov     [rsp+arg_8], rbp
0x1800392f6  mov     [rsp+arg_10], rsi
0x1800392fb  push    rdi
0x1800392fc  push    r12
0x1800392fe  push    r13
0x180039300  push    r14
0x180039302  push    r15
0x180039304  sub     rsp, 20h
0x180039308  mov     edi, ecx
0x18003930a  lea     r15, cs:180000000h
0x180039311  or      r14, 0FFFFFFFFFFFFFFFFh
0x180039315  mov     r12, r9
0x180039318  mov     rbp, r8
0x18003931b  mov     r13, rdx
0x18003931e  mov     rax, rva qword_180059C30[r15+rdi*8]
0x180039326  nop
0x180039327  cmp     rax, r14
0x18003932a  jz      loc_1800393DE
0x180039330  test    rax, rax
0x180039333  jnz     loc_1800393E0
0x180039339  cmp     r8, r9
0x18003933c  jz      loc_1800393D6
0x180039342  mov     esi, [rbp+0]
0x180039345  mov     rbx, rva qword_180059C18[r15+rsi*8]
0x18003934d  nop
0x18003934e  test    rbx, rbx
0x180039351  jz      short loc_18003935E
0x180039353  cmp     rbx, r14
0x180039356  jnz     loc_18003941D
0x18003935c  jmp     short loc_1800393C9
0x18003935e  mov     r15, ds:rva off_180047930[r15+rsi*8]; "api-ms-win-core-fibers-l1-1-1" ...
0x180039366  xor     edx, edx; hFile
0x180039368  mov     rcx, r15; lpLibFileName
0x18003936b  mov     r8d, 800h; dwFlags
0x180039371  call    cs:__imp_LoadLibraryExW
0x180039377  mov     rbx, rax
0x18003937a  test    rax, rax
0x18003937d  jnz     short loc_1800393FD
0x18003937f  call    cs:__imp_GetLastError
0x180039385  cmp     eax, 57h ; 'W'
0x180039388  jnz     short loc_1800393B7
0x18003938a  lea     r8d, [rbx+7]; MaxCount
0x18003938e  mov     rcx, r15; String1
0x180039391  lea     rdx, aApiMs; "api-ms-"
0x180039398  call    wcsncmp_0
0x18003939d  test    eax, eax
0x18003939f  jz      short loc_1800393B7
0x1800393a1  xor     r8d, r8d; dwFlags
0x1800393a4  xor     edx, edx; hFile
0x1800393a6  mov     rcx, r15; lpLibFileName
0x1800393a9  call    cs:__imp_LoadLibraryExW
0x1800393af  mov     rbx, rax
0x1800393b2  test    rax, rax
0x1800393b5  jnz     short loc_1800393FD
0x1800393b7  mov     rax, r14
0x1800393ba  lea     r15, cs:180000000h
0x1800393c1  xchg    rax, rva qword_180059C18[r15+rsi*8]
0x1800393c9  add     rbp, 4
0x1800393cd  cmp     rbp, r12
0x1800393d0  jnz     loc_180039342
0x1800393d6  xchg    r14, rva qword_180059C30[r15+rdi*8]
0x1800393de  xor     eax, eax
0x1800393e0  mov     rbx, [rsp+48h+arg_0]
0x1800393e5  mov     rbp, [rsp+48h+arg_8]
0x1800393ea  mov     rsi, [rsp+48h+arg_10]
0x1800393ef  add     rsp, 20h
0x1800393f3  pop     r15
0x1800393f5  pop     r14
0x1800393f7  pop     r13
0x1800393f9  pop     r12
0x1800393fb  pop     rdi
0x1800393fc  retn
0x1800393fd  mov     rax, rbx
0x180039400  lea     r15, cs:180000000h
0x180039407  xchg    rax, rva qword_180059C18[r15+rsi*8]
0x18003940f  test    rax, rax
0x180039412  jz      short loc_18003941D
0x180039414  mov     rcx, rbx; hLibModule
0x180039417  call    cs:__imp_FreeLibrary
0x18003941d  mov     rdx, r13; lpProcName
0x180039420  mov     rcx, rbx; hModule
0x180039423  call    cs:__imp_GetProcAddress
0x180039429  test    rax, rax
0x18003942c  jz      short loc_1800393D6
0x18003942e  mov     rcx, rax
0x180039431  xchg    rcx, rva qword_180059C30[r15+rdi*8]
0x180039439  jmp     short loc_1800393E0
```
