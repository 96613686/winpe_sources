# try_get_function

- ea: `0x18000b19c`
- end: `0x18000b2eb`
- name: `try_get_function`
- size: `335`
- prototype: `FARPROC __fastcall(unsigned int, const CHAR *, unsigned int *, unsigned int *)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b2ec`
- `0x18000b334`
- `0x18000b37c`
- `0x18000b3c4`
- `0x18000b418`

## callees

- `0x18000b19c`
- `0x18000b622`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000b22f`
- `KERNEL32!GetLastError` at `0x18000b22f`
- `KERNEL32!GetProcAddress` at `0x18000b2d3`
- `KERNEL32!GetProcAddress` at `0x18000b2d3`
- `KERNEL32!LoadLibraryExW` at `0x18000b221`
- `KERNEL32!LoadLibraryExW` at `0x18000b259`
- `KERNEL32!LoadLibraryExW` at `0x18000b221`
- `KERNEL32!LoadLibraryExW` at `0x18000b259`
- `KERNEL32!FreeLibrary` at `0x18000b2c7`
- `KERNEL32!FreeLibrary` at `0x18000b2c7`

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
  result = (FARPROC)qword_180016230[a1];
  if ( result == (FARPROC)-1LL )
    return 0;
  if ( !result )
  {
    if ( a3 == a4 )
      goto LABEL_13;
    while ( 1 )
    {
      v9 = *v6;
      Library = (HMODULE)qword_180016218[v9];
      if ( Library )
      {
        if ( Library != (HMODULE)-1LL )
          goto LABEL_18;
      }
      else
      {
        v11 = off_18000E4B8[v9];
        Library = LoadLibraryExW(v11, 0, 0x800u);
        if ( Library
          || GetLastError() == 87 && wcsncmp_0(v11, L"api-ms-", 7u) && (Library = LoadLibraryExW(v11, 0, 0)) != 0 )
        {
          if ( _InterlockedExchange64(&qword_180016218[v9], (__int64)Library) )
            FreeLibrary(Library);
LABEL_18:
          result = GetProcAddress(Library, a2);
          if ( result )
          {
            _InterlockedExchange64(&qword_180016230[v4], (__int64)result);
            return result;
          }
LABEL_13:
          _InterlockedExchange64(&qword_180016230[v4], -1);
          return 0;
        }
        _InterlockedExchange64(&qword_180016218[v9], -1);
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
0x18000b19c  mov     [rsp+arg_0], rbx
0x18000b1a1  mov     [rsp+arg_8], rbp
0x18000b1a6  mov     [rsp+arg_10], rsi
0x18000b1ab  push    rdi
0x18000b1ac  push    r12
0x18000b1ae  push    r13
0x18000b1b0  push    r14
0x18000b1b2  push    r15
0x18000b1b4  sub     rsp, 20h
0x18000b1b8  mov     edi, ecx
0x18000b1ba  lea     r15, cs:180000000h
0x18000b1c1  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000b1c5  mov     r12, r9
0x18000b1c8  mov     rbp, r8
0x18000b1cb  mov     r13, rdx
0x18000b1ce  mov     rax, rva qword_180016230[r15+rdi*8]
0x18000b1d6  nop
0x18000b1d7  cmp     rax, r14
0x18000b1da  jz      loc_18000B28E
0x18000b1e0  test    rax, rax
0x18000b1e3  jnz     loc_18000B290
0x18000b1e9  cmp     r8, r9
0x18000b1ec  jz      loc_18000B286
0x18000b1f2  mov     esi, [rbp+0]
0x18000b1f5  mov     rbx, rva qword_180016218[r15+rsi*8]
0x18000b1fd  nop
0x18000b1fe  test    rbx, rbx
0x18000b201  jz      short loc_18000B20E
0x18000b203  cmp     rbx, r14
0x18000b206  jnz     loc_18000B2CD
0x18000b20c  jmp     short loc_18000B279
0x18000b20e  mov     r15, ds:rva off_18000E4B8[r15+rsi*8]; "api-ms-win-core-fibers-l1-1-1" ...
0x18000b216  xor     edx, edx; hFile
0x18000b218  mov     rcx, r15; lpLibFileName
0x18000b21b  mov     r8d, 800h; dwFlags
0x18000b221  call    cs:__imp_LoadLibraryExW
0x18000b227  mov     rbx, rax
0x18000b22a  test    rax, rax
0x18000b22d  jnz     short loc_18000B2AD
0x18000b22f  call    cs:__imp_GetLastError
0x18000b235  cmp     eax, 57h ; 'W'
0x18000b238  jnz     short loc_18000B267
0x18000b23a  lea     r8d, [rbx+7]; MaxCount
0x18000b23e  mov     rcx, r15; String1
0x18000b241  lea     rdx, aApiMs; "api-ms-"
0x18000b248  call    wcsncmp_0
0x18000b24d  test    eax, eax
0x18000b24f  jz      short loc_18000B267
0x18000b251  xor     r8d, r8d; dwFlags
0x18000b254  xor     edx, edx; hFile
0x18000b256  mov     rcx, r15; lpLibFileName
0x18000b259  call    cs:__imp_LoadLibraryExW
0x18000b25f  mov     rbx, rax
0x18000b262  test    rax, rax
0x18000b265  jnz     short loc_18000B2AD
0x18000b267  mov     rax, r14
0x18000b26a  lea     r15, cs:180000000h
0x18000b271  xchg    rax, rva qword_180016218[r15+rsi*8]
0x18000b279  add     rbp, 4
0x18000b27d  cmp     rbp, r12
0x18000b280  jnz     loc_18000B1F2
0x18000b286  xchg    r14, rva qword_180016230[r15+rdi*8]
0x18000b28e  xor     eax, eax
0x18000b290  mov     rbx, [rsp+48h+arg_0]
0x18000b295  mov     rbp, [rsp+48h+arg_8]
0x18000b29a  mov     rsi, [rsp+48h+arg_10]
0x18000b29f  add     rsp, 20h
0x18000b2a3  pop     r15
0x18000b2a5  pop     r14
0x18000b2a7  pop     r13
0x18000b2a9  pop     r12
0x18000b2ab  pop     rdi
0x18000b2ac  retn
0x18000b2ad  mov     rax, rbx
0x18000b2b0  lea     r15, cs:180000000h
0x18000b2b7  xchg    rax, rva qword_180016218[r15+rsi*8]
0x18000b2bf  test    rax, rax
0x18000b2c2  jz      short loc_18000B2CD
0x18000b2c4  mov     rcx, rbx; hLibModule
0x18000b2c7  call    cs:__imp_FreeLibrary
0x18000b2cd  mov     rdx, r13; lpProcName
0x18000b2d0  mov     rcx, rbx; hModule
0x18000b2d3  call    cs:__imp_GetProcAddress
0x18000b2d9  test    rax, rax
0x18000b2dc  jz      short loc_18000B286
0x18000b2de  mov     rcx, rax
0x18000b2e1  xchg    rcx, rva qword_180016230[r15+rdi*8]
0x18000b2e9  jmp     short loc_18000B290
```
