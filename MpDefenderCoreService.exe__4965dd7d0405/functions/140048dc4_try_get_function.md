# try_get_function

- ea: `0x140048dc4`
- end: `0x140048f13`
- name: `try_get_function`
- size: `335`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140048f14`
- `0x140048f5c`
- `0x140048fa4`
- `0x140048fec`
- `0x140049040`

## callees

- `0x140048dc4`
- `0x14005d2d0`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x140048e49`
- `KERNEL32!LoadLibraryExW` at `0x140048e81`
- `KERNEL32!LoadLibraryExW` at `0x140048e49`
- `KERNEL32!LoadLibraryExW` at `0x140048e81`
- `KERNEL32!GetLastError` at `0x140048e57`
- `KERNEL32!GetLastError` at `0x140048e57`
- `KERNEL32!FreeLibrary` at `0x140048eef`
- `KERNEL32!FreeLibrary` at `0x140048eef`
- `KERNEL32!GetProcAddress` at `0x140048efb`
- `KERNEL32!GetProcAddress` at `0x140048efb`

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
  result = (FARPROC)qword_1401E4E10[a1];
  if ( result == (FARPROC)-1LL )
    return 0;
  if ( !result )
  {
    if ( a3 == a4 )
      goto LABEL_13;
    while ( 1 )
    {
      v9 = *v6;
      Library = (HMODULE)qword_1401E4DF8[v9];
      if ( Library )
      {
        if ( Library != (HMODULE)-1LL )
          goto LABEL_18;
      }
      else
      {
        v11 = off_14017F290[v9];
        Library = LoadLibraryExW(v11, 0, 0x800u);
        if ( Library
          || GetLastError() == 87 && wcsncmp(v11, L"api-ms-", 7u) && (Library = LoadLibraryExW(v11, 0, 0)) != 0 )
        {
          if ( _InterlockedExchange64(&qword_1401E4DF8[v9], (__int64)Library) )
            FreeLibrary(Library);
LABEL_18:
          result = GetProcAddress(Library, a2);
          if ( result )
          {
            _InterlockedExchange64(&qword_1401E4E10[v4], (__int64)result);
            return result;
          }
LABEL_13:
          _InterlockedExchange64(&qword_1401E4E10[v4], -1);
          return 0;
        }
        _InterlockedExchange64(&qword_1401E4DF8[v9], -1);
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
0x140048dc4  mov     [rsp+arg_0], rbx
0x140048dc9  mov     [rsp+arg_8], rbp
0x140048dce  mov     [rsp+arg_10], rsi
0x140048dd3  push    rdi
0x140048dd4  push    r12
0x140048dd6  push    r13
0x140048dd8  push    r14
0x140048dda  push    r15
0x140048ddc  sub     rsp, 20h
0x140048de0  mov     edi, ecx
0x140048de2  lea     r15, cs:140000000h
0x140048de9  or      r14, 0FFFFFFFFFFFFFFFFh
0x140048ded  mov     r12, r9
0x140048df0  mov     rbp, r8
0x140048df3  mov     r13, rdx
0x140048df6  mov     rax, rva qword_1401E4E10[r15+rdi*8]
0x140048dfe  nop
0x140048dff  cmp     rax, r14
0x140048e02  jz      loc_140048EB6
0x140048e08  test    rax, rax
0x140048e0b  jnz     loc_140048EB8
0x140048e11  cmp     r8, r9
0x140048e14  jz      loc_140048EAE
0x140048e1a  mov     esi, [rbp+0]
0x140048e1d  mov     rbx, rva qword_1401E4DF8[r15+rsi*8]
0x140048e25  nop
0x140048e26  test    rbx, rbx
0x140048e29  jz      short loc_140048E36
0x140048e2b  cmp     rbx, r14
0x140048e2e  jnz     loc_140048EF5
0x140048e34  jmp     short loc_140048EA1
0x140048e36  mov     r15, ds:rva off_14017F290[r15+rsi*8]
0x140048e3e  xor     edx, edx; hFile
0x140048e40  mov     rcx, r15; lpLibFileName
0x140048e43  mov     r8d, 800h; dwFlags
0x140048e49  call    cs:__imp_LoadLibraryExW
0x140048e4f  mov     rbx, rax
0x140048e52  test    rax, rax
0x140048e55  jnz     short loc_140048ED5
0x140048e57  call    cs:__imp_GetLastError
0x140048e5d  cmp     eax, 57h ; 'W'
0x140048e60  jnz     short loc_140048E8F
0x140048e62  lea     r8d, [rbx+7]; MaxCount
0x140048e66  mov     rcx, r15; String1
0x140048e69  lea     rdx, aApiMs
0x140048e70  call    wcsncmp
0x140048e75  test    eax, eax
0x140048e77  jz      short loc_140048E8F
0x140048e79  xor     r8d, r8d; dwFlags
0x140048e7c  xor     edx, edx; hFile
0x140048e7e  mov     rcx, r15; lpLibFileName
0x140048e81  call    cs:__imp_LoadLibraryExW
0x140048e87  mov     rbx, rax
0x140048e8a  test    rax, rax
0x140048e8d  jnz     short loc_140048ED5
0x140048e8f  mov     rax, r14
0x140048e92  lea     r15, cs:140000000h
0x140048e99  xchg    rax, rva qword_1401E4DF8[r15+rsi*8]
0x140048ea1  add     rbp, 4
0x140048ea5  cmp     rbp, r12
0x140048ea8  jnz     loc_140048E1A
0x140048eae  xchg    r14, rva qword_1401E4E10[r15+rdi*8]
0x140048eb6  xor     eax, eax
0x140048eb8  mov     rbx, [rsp+48h+arg_0]
0x140048ebd  mov     rbp, [rsp+48h+arg_8]
0x140048ec2  mov     rsi, [rsp+48h+arg_10]
0x140048ec7  add     rsp, 20h
0x140048ecb  pop     r15
0x140048ecd  pop     r14
0x140048ecf  pop     r13
0x140048ed1  pop     r12
0x140048ed3  pop     rdi
0x140048ed4  retn
0x140048ed5  mov     rax, rbx
0x140048ed8  lea     r15, cs:140000000h
0x140048edf  xchg    rax, rva qword_1401E4DF8[r15+rsi*8]
0x140048ee7  test    rax, rax
0x140048eea  jz      short loc_140048EF5
0x140048eec  mov     rcx, rbx; hLibModule
0x140048eef  call    cs:__imp_FreeLibrary
0x140048ef5  mov     rdx, r13; lpProcName
0x140048ef8  mov     rcx, rbx; hModule
0x140048efb  call    cs:__imp_GetProcAddress
0x140048f01  test    rax, rax
0x140048f04  jz      short loc_140048EAE
0x140048f06  mov     rcx, rax
0x140048f09  xchg    rcx, rva qword_1401E4E10[r15+rdi*8]
0x140048f11  jmp     short loc_140048EB8
```
