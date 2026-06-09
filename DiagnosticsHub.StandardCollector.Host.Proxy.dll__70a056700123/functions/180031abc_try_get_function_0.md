# try_get_function_0

- ea: `0x180031abc`
- end: `0x180031c0b`
- name: `try_get_function_0`
- size: `335`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180031928`
- `0x180031944`
- `0x180031964`
- `0x180031984`
- `0x1800319a4`
- `0x180031e58`
- `0x180031ea0`
- `0x180031ee8`
- `0x180031f30`
- `0x180031f84`

## callees

- `0x180013e70`
- `0x180031abc`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180031be7`
- `KERNEL32!FreeLibrary` at `0x180031be7`
- `KERNEL32!GetProcAddress` at `0x180031bf3`
- `KERNEL32!GetProcAddress` at `0x180031bf3`
- `KERNEL32!GetLastError` at `0x180031b4f`
- `KERNEL32!GetLastError` at `0x180031b4f`
- `KERNEL32!LoadLibraryExW` at `0x180031b41`
- `KERNEL32!LoadLibraryExW` at `0x180031b79`
- `KERNEL32!LoadLibraryExW` at `0x180031b41`
- `KERNEL32!LoadLibraryExW` at `0x180031b79`

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
  result = (FARPROC)qword_180079108[a1];
  if ( result == (FARPROC)-1LL )
    return 0;
  if ( !result )
  {
    if ( a3 == a4 )
      goto LABEL_13;
    while ( 1 )
    {
      v9 = *v6;
      Library = (HMODULE)qword_1800790F0[v9];
      if ( Library )
      {
        if ( Library != (HMODULE)-1LL )
          goto LABEL_18;
      }
      else
      {
        v11 = off_18006B048[v9];
        Library = LoadLibraryExW(v11, 0, 0x800u);
        if ( Library
          || GetLastError() == 87 && wcsncmp(v11, L"api-ms-", 7u) && (Library = LoadLibraryExW(v11, 0, 0)) != 0 )
        {
          if ( _InterlockedExchange64(&qword_1800790F0[v9], (__int64)Library) )
            FreeLibrary(Library);
LABEL_18:
          result = GetProcAddress(Library, a2);
          if ( result )
          {
            _InterlockedExchange64(&qword_180079108[v4], (__int64)result);
            return result;
          }
LABEL_13:
          _InterlockedExchange64(&qword_180079108[v4], -1);
          return 0;
        }
        _InterlockedExchange64(&qword_1800790F0[v9], -1);
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
0x180031abc  mov     [rsp+arg_0], rbx
0x180031ac1  mov     [rsp+arg_8], rbp
0x180031ac6  mov     [rsp+arg_10], rsi
0x180031acb  push    rdi
0x180031acc  push    r12
0x180031ace  push    r13
0x180031ad0  push    r14
0x180031ad2  push    r15
0x180031ad4  sub     rsp, 20h
0x180031ad8  mov     edi, ecx
0x180031ada  lea     r15, cs:180000000h
0x180031ae1  or      r14, 0FFFFFFFFFFFFFFFFh
0x180031ae5  mov     r12, r9
0x180031ae8  mov     rbp, r8
0x180031aeb  mov     r13, rdx
0x180031aee  mov     rax, rva qword_180079108[r15+rdi*8]
0x180031af6  nop
0x180031af7  cmp     rax, r14
0x180031afa  jz      loc_180031BAE
0x180031b00  test    rax, rax
0x180031b03  jnz     loc_180031BB0
0x180031b09  cmp     r8, r9
0x180031b0c  jz      loc_180031BA6
0x180031b12  mov     esi, [rbp+0]
0x180031b15  mov     rbx, rva qword_1800790F0[r15+rsi*8]
0x180031b1d  nop
0x180031b1e  test    rbx, rbx
0x180031b21  jz      short loc_180031B2E
0x180031b23  cmp     rbx, r14
0x180031b26  jnz     loc_180031BED
0x180031b2c  jmp     short loc_180031B99
0x180031b2e  mov     r15, ds:rva off_18006B048[r15+rsi*8]; "api-ms-win-core-fibers-l1-1-1" ...
0x180031b36  xor     edx, edx; hFile
0x180031b38  mov     rcx, r15; lpLibFileName
0x180031b3b  mov     r8d, 800h; dwFlags
0x180031b41  call    cs:__imp_LoadLibraryExW
0x180031b47  mov     rbx, rax
0x180031b4a  test    rax, rax
0x180031b4d  jnz     short loc_180031BCD
0x180031b4f  call    cs:__imp_GetLastError
0x180031b55  cmp     eax, 57h ; 'W'
0x180031b58  jnz     short loc_180031B87
0x180031b5a  lea     r8d, [rbx+7]; MaxCount
0x180031b5e  mov     rcx, r15; String1
0x180031b61  lea     rdx, aApiMs; "api-ms-"
0x180031b68  call    wcsncmp
0x180031b6d  test    eax, eax
0x180031b6f  jz      short loc_180031B87
0x180031b71  xor     r8d, r8d; dwFlags
0x180031b74  xor     edx, edx; hFile
0x180031b76  mov     rcx, r15; lpLibFileName
0x180031b79  call    cs:__imp_LoadLibraryExW
0x180031b7f  mov     rbx, rax
0x180031b82  test    rax, rax
0x180031b85  jnz     short loc_180031BCD
0x180031b87  mov     rax, r14
0x180031b8a  lea     r15, cs:180000000h
0x180031b91  xchg    rax, rva qword_1800790F0[r15+rsi*8]
0x180031b99  add     rbp, 4
0x180031b9d  cmp     rbp, r12
0x180031ba0  jnz     loc_180031B12
0x180031ba6  xchg    r14, rva qword_180079108[r15+rdi*8]
0x180031bae  xor     eax, eax
0x180031bb0  mov     rbx, [rsp+48h+arg_0]
0x180031bb5  mov     rbp, [rsp+48h+arg_8]
0x180031bba  mov     rsi, [rsp+48h+arg_10]
0x180031bbf  add     rsp, 20h
0x180031bc3  pop     r15
0x180031bc5  pop     r14
0x180031bc7  pop     r13
0x180031bc9  pop     r12
0x180031bcb  pop     rdi
0x180031bcc  retn
0x180031bcd  mov     rax, rbx
0x180031bd0  lea     r15, cs:180000000h
0x180031bd7  xchg    rax, rva qword_1800790F0[r15+rsi*8]
0x180031bdf  test    rax, rax
0x180031be2  jz      short loc_180031BED
0x180031be4  mov     rcx, rbx; hLibModule
0x180031be7  call    cs:__imp_FreeLibrary
0x180031bed  mov     rdx, r13; lpProcName
0x180031bf0  mov     rcx, rbx; hModule
0x180031bf3  call    cs:__imp_GetProcAddress
0x180031bf9  test    rax, rax
0x180031bfc  jz      short loc_180031BA6
0x180031bfe  mov     rcx, rax
0x180031c01  xchg    rcx, rva qword_180079108[r15+rdi*8]
0x180031c09  jmp     short loc_180031BB0
```
