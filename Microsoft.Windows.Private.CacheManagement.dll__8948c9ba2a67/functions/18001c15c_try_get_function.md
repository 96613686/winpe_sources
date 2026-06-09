# try_get_function

- ea: `0x18001c15c`
- end: `0x18001c2ab`
- name: `try_get_function`
- size: `335`
- prototype: `FARPROC __fastcall(unsigned int, const CHAR *, unsigned int *, unsigned int *)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001c2ac`
- `0x18001c2f4`
- `0x18001c33c`
- `0x18001c384`
- `0x18001c3d8`

## callees

- `0x18001c15c`
- `0x18001c5df`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18001c1e1`
- `KERNEL32!LoadLibraryExW` at `0x18001c219`
- `KERNEL32!LoadLibraryExW` at `0x18001c1e1`
- `KERNEL32!LoadLibraryExW` at `0x18001c219`
- `KERNEL32!GetProcAddress` at `0x18001c293`
- `KERNEL32!GetProcAddress` at `0x18001c293`
- `KERNEL32!GetLastError` at `0x18001c1ef`
- `KERNEL32!GetLastError` at `0x18001c1ef`
- `KERNEL32!FreeLibrary` at `0x18001c287`
- `KERNEL32!FreeLibrary` at `0x18001c287`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  result = (FARPROC)qword_18002E550[a1];
  if ( result == (FARPROC)-1LL )
    return 0;
  if ( !result )
  {
    if ( a3 == a4 )
      goto LABEL_13;
    while ( 1 )
    {
      v9 = *v6;
      Library = (HMODULE)qword_18002E538[v9];
      if ( Library )
      {
        if ( Library != (HMODULE)-1LL )
          goto LABEL_18;
      }
      else
      {
        v11 = off_180024F38[v9];
        Library = LoadLibraryExW(v11, 0, 0x800u);
        if ( Library
          || GetLastError() == 87 && wcsncmp_0(v11, L"api-ms-", 7u) && (Library = LoadLibraryExW(v11, 0, 0)) != 0 )
        {
          if ( _InterlockedExchange64(&qword_18002E538[v9], (__int64)Library) )
            FreeLibrary(Library);
LABEL_18:
          result = GetProcAddress(Library, a2);
          if ( result )
          {
            _InterlockedExchange64(&qword_18002E550[v4], (__int64)result);
            return result;
          }
LABEL_13:
          _InterlockedExchange64(&qword_18002E550[v4], -1);
          return 0;
        }
        _InterlockedExchange64(&qword_18002E538[v9], -1);
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
0x18001c15c  mov     [rsp+arg_0], rbx
0x18001c161  mov     [rsp+arg_8], rbp
0x18001c166  mov     [rsp+arg_10], rsi
0x18001c16b  push    rdi
0x18001c16c  push    r12
0x18001c16e  push    r13
0x18001c170  push    r14
0x18001c172  push    r15
0x18001c174  sub     rsp, 20h
0x18001c178  mov     edi, ecx
0x18001c17a  lea     r15, cs:180000000h
0x18001c181  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001c185  mov     r12, r9
0x18001c188  mov     rbp, r8
0x18001c18b  mov     r13, rdx
0x18001c18e  mov     rax, rva qword_18002E550[r15+rdi*8]
0x18001c196  nop
0x18001c197  cmp     rax, r14
0x18001c19a  jz      loc_18001C24E
0x18001c1a0  test    rax, rax
0x18001c1a3  jnz     loc_18001C250
0x18001c1a9  cmp     r8, r9
0x18001c1ac  jz      loc_18001C246
0x18001c1b2  mov     esi, [rbp+0]
0x18001c1b5  mov     rbx, rva qword_18002E538[r15+rsi*8]
0x18001c1bd  nop
0x18001c1be  test    rbx, rbx
0x18001c1c1  jz      short loc_18001C1CE
0x18001c1c3  cmp     rbx, r14
0x18001c1c6  jnz     loc_18001C28D
0x18001c1cc  jmp     short loc_18001C239
0x18001c1ce  mov     r15, ds:rva off_180024F38[r15+rsi*8]; "api-ms-win-core-fibers-l1-1-1" ...
0x18001c1d6  xor     edx, edx; hFile
0x18001c1d8  mov     rcx, r15; lpLibFileName
0x18001c1db  mov     r8d, 800h; dwFlags
0x18001c1e1  call    cs:__imp_LoadLibraryExW
0x18001c1e7  mov     rbx, rax
0x18001c1ea  test    rax, rax
0x18001c1ed  jnz     short loc_18001C26D
0x18001c1ef  call    cs:__imp_GetLastError
0x18001c1f5  cmp     eax, 57h ; 'W'
0x18001c1f8  jnz     short loc_18001C227
0x18001c1fa  lea     r8d, [rbx+7]; MaxCount
0x18001c1fe  mov     rcx, r15; String1
0x18001c201  lea     rdx, aApiMs; "api-ms-"
0x18001c208  call    wcsncmp_0
0x18001c20d  test    eax, eax
0x18001c20f  jz      short loc_18001C227
0x18001c211  xor     r8d, r8d; dwFlags
0x18001c214  xor     edx, edx; hFile
0x18001c216  mov     rcx, r15; lpLibFileName
0x18001c219  call    cs:__imp_LoadLibraryExW
0x18001c21f  mov     rbx, rax
0x18001c222  test    rax, rax
0x18001c225  jnz     short loc_18001C26D
0x18001c227  mov     rax, r14
0x18001c22a  lea     r15, cs:180000000h
0x18001c231  xchg    rax, rva qword_18002E538[r15+rsi*8]
0x18001c239  add     rbp, 4
0x18001c23d  cmp     rbp, r12
0x18001c240  jnz     loc_18001C1B2
0x18001c246  xchg    r14, rva qword_18002E550[r15+rdi*8]
0x18001c24e  xor     eax, eax
0x18001c250  mov     rbx, [rsp+48h+arg_0]
0x18001c255  mov     rbp, [rsp+48h+arg_8]
0x18001c25a  mov     rsi, [rsp+48h+arg_10]
0x18001c25f  add     rsp, 20h
0x18001c263  pop     r15
0x18001c265  pop     r14
0x18001c267  pop     r13
0x18001c269  pop     r12
0x18001c26b  pop     rdi
0x18001c26c  retn
0x18001c26d  mov     rax, rbx
0x18001c270  lea     r15, cs:180000000h
0x18001c277  xchg    rax, rva qword_18002E538[r15+rsi*8]
0x18001c27f  test    rax, rax
0x18001c282  jz      short loc_18001C28D
0x18001c284  mov     rcx, rbx; hLibModule
0x18001c287  call    cs:__imp_FreeLibrary
0x18001c28d  mov     rdx, r13; lpProcName
0x18001c290  mov     rcx, rbx; hModule
0x18001c293  call    cs:__imp_GetProcAddress
0x18001c299  test    rax, rax
0x18001c29c  jz      short loc_18001C246
0x18001c29e  mov     rcx, rax
0x18001c2a1  xchg    rcx, rva qword_18002E550[r15+rdi*8]
0x18001c2a9  jmp     short loc_18001C250
```
