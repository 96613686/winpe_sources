# try_get_function_0

- ea: `0x18003221c`
- end: `0x18003236b`
- name: `try_get_function_0`
- size: `335`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180032088`
- `0x1800320a4`
- `0x1800320c4`
- `0x1800320e4`
- `0x180032104`
- `0x1800325b8`
- `0x180032600`
- `0x180032648`
- `0x180032690`
- `0x1800326e4`

## callees

- `0x1800145d0`
- `0x18003221c`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800322a1`
- `KERNEL32!LoadLibraryExW` at `0x1800322d9`
- `KERNEL32!LoadLibraryExW` at `0x1800322a1`
- `KERNEL32!LoadLibraryExW` at `0x1800322d9`
- `KERNEL32!FreeLibrary` at `0x180032347`
- `KERNEL32!FreeLibrary` at `0x180032347`
- `KERNEL32!GetProcAddress` at `0x180032353`
- `KERNEL32!GetProcAddress` at `0x180032353`
- `KERNEL32!GetLastError` at `0x1800322af`
- `KERNEL32!GetLastError` at `0x1800322af`

## pseudocode

```c
FARPROC __fastcall try_get_function_0(unsigned int a1, const CHAR *a2, unsigned int *a3, unsigned int *a4)
{
  __int64 v4; // rdi
  unsigned int *v6; // rbp
  FARPROC result; // rax
  __int64 v9; // rsi
  HMODULE Library; // rbx
  const WCHAR *v11; // r15

  v4 = a1;
  v6 = a3;
  result = (FARPROC)qword_18007CBB8[a1];
  if ( result == (FARPROC)-1LL )
    return 0;
  if ( !result )
  {
    if ( a3 == a4 )
      goto LABEL_13;
    while ( 1 )
    {
      v9 = *v6;
      Library = (HMODULE)qword_18007CBA0[v9];
      if ( Library )
      {
        if ( Library != (HMODULE)-1LL )
          goto LABEL_18;
      }
      else
      {
        v11 = off_18006E728[v9];
        Library = LoadLibraryExW(v11, 0, 0x800u);
        if ( Library
          || GetLastError() == 87 && wcsncmp(v11, L"api-ms-", 7u) && (Library = LoadLibraryExW(v11, 0, 0)) != 0 )
        {
          if ( _InterlockedExchange64(&qword_18007CBA0[v9], (__int64)Library) )
            FreeLibrary(Library);
LABEL_18:
          result = GetProcAddress(Library, a2);
          if ( result )
          {
            _InterlockedExchange64(&qword_18007CBB8[v4], (__int64)result);
            return result;
          }
LABEL_13:
          _InterlockedExchange64(&qword_18007CBB8[v4], -1);
          return 0;
        }
        _InterlockedExchange64(&qword_18007CBA0[v9], -1);
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
0x18003221c  mov     [rsp+arg_0], rbx
0x180032221  mov     [rsp+arg_8], rbp
0x180032226  mov     [rsp+arg_10], rsi
0x18003222b  push    rdi
0x18003222c  push    r12
0x18003222e  push    r13
0x180032230  push    r14
0x180032232  push    r15
0x180032234  sub     rsp, 20h
0x180032238  mov     edi, ecx
0x18003223a  lea     r15, cs:180000000h
0x180032241  or      r14, 0FFFFFFFFFFFFFFFFh
0x180032245  mov     r12, r9
0x180032248  mov     rbp, r8
0x18003224b  mov     r13, rdx
0x18003224e  mov     rax, rva qword_18007CBB8[r15+rdi*8]
0x180032256  nop
0x180032257  cmp     rax, r14
0x18003225a  jz      loc_18003230E
0x180032260  test    rax, rax
0x180032263  jnz     loc_180032310
0x180032269  cmp     r8, r9
0x18003226c  jz      loc_180032306
0x180032272  mov     esi, [rbp+0]
0x180032275  mov     rbx, rva qword_18007CBA0[r15+rsi*8]
0x18003227d  nop
0x18003227e  test    rbx, rbx
0x180032281  jz      short loc_18003228E
0x180032283  cmp     rbx, r14
0x180032286  jnz     loc_18003234D
0x18003228c  jmp     short loc_1800322F9
0x18003228e  mov     r15, ds:rva off_18006E728[r15+rsi*8]; "api-ms-win-core-fibers-l1-1-1" ...
0x180032296  xor     edx, edx; hFile
0x180032298  mov     rcx, r15; lpLibFileName
0x18003229b  mov     r8d, 800h; dwFlags
0x1800322a1  call    cs:__imp_LoadLibraryExW
0x1800322a7  mov     rbx, rax
0x1800322aa  test    rax, rax
0x1800322ad  jnz     short loc_18003232D
0x1800322af  call    cs:__imp_GetLastError
0x1800322b5  cmp     eax, 57h ; 'W'
0x1800322b8  jnz     short loc_1800322E7
0x1800322ba  lea     r8d, [rbx+7]; MaxCount
0x1800322be  mov     rcx, r15; String1
0x1800322c1  lea     rdx, aApiMs; "api-ms-"
0x1800322c8  call    wcsncmp
0x1800322cd  test    eax, eax
0x1800322cf  jz      short loc_1800322E7
0x1800322d1  xor     r8d, r8d; dwFlags
0x1800322d4  xor     edx, edx; hFile
0x1800322d6  mov     rcx, r15; lpLibFileName
0x1800322d9  call    cs:__imp_LoadLibraryExW
0x1800322df  mov     rbx, rax
0x1800322e2  test    rax, rax
0x1800322e5  jnz     short loc_18003232D
0x1800322e7  mov     rax, r14
0x1800322ea  lea     r15, cs:180000000h
0x1800322f1  xchg    rax, rva qword_18007CBA0[r15+rsi*8]
0x1800322f9  add     rbp, 4
0x1800322fd  cmp     rbp, r12
0x180032300  jnz     loc_180032272
0x180032306  xchg    r14, rva qword_18007CBB8[r15+rdi*8]
0x18003230e  xor     eax, eax
0x180032310  mov     rbx, [rsp+48h+arg_0]
0x180032315  mov     rbp, [rsp+48h+arg_8]
0x18003231a  mov     rsi, [rsp+48h+arg_10]
0x18003231f  add     rsp, 20h
0x180032323  pop     r15
0x180032325  pop     r14
0x180032327  pop     r13
0x180032329  pop     r12
0x18003232b  pop     rdi
0x18003232c  retn
0x18003232d  mov     rax, rbx
0x180032330  lea     r15, cs:180000000h
0x180032337  xchg    rax, rva qword_18007CBA0[r15+rsi*8]
0x18003233f  test    rax, rax
0x180032342  jz      short loc_18003234D
0x180032344  mov     rcx, rbx; hLibModule
0x180032347  call    cs:__imp_FreeLibrary
0x18003234d  mov     rdx, r13; lpProcName
0x180032350  mov     rcx, rbx; hModule
0x180032353  call    cs:__imp_GetProcAddress
0x180032359  test    rax, rax
0x18003235c  jz      short loc_180032306
0x18003235e  mov     rcx, rax
0x180032361  xchg    rcx, rva qword_18007CBB8[r15+rdi*8]
0x180032369  jmp     short loc_180032310
```
