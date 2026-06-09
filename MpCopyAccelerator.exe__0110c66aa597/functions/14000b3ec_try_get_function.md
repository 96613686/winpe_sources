# try_get_function

- ea: `0x14000b3ec`
- end: `0x14000b53b`
- name: `try_get_function`
- size: `335`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000b53c`
- `0x14000b584`
- `0x14000b5cc`
- `0x14000b614`
- `0x14000b668`

## callees

- `0x14000b3ec`
- `0x1400113c0`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x14000b471`
- `KERNEL32!LoadLibraryExW` at `0x14000b4a9`
- `KERNEL32!LoadLibraryExW` at `0x14000b471`
- `KERNEL32!LoadLibraryExW` at `0x14000b4a9`
- `KERNEL32!GetProcAddress` at `0x14000b523`
- `KERNEL32!GetProcAddress` at `0x14000b523`
- `KERNEL32!FreeLibrary` at `0x14000b517`
- `KERNEL32!FreeLibrary` at `0x14000b517`
- `KERNEL32!GetLastError` at `0x14000b47f`
- `KERNEL32!GetLastError` at `0x14000b47f`

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
  result = (FARPROC)qword_14003C840[a1];
  if ( result == (FARPROC)-1LL )
    return 0;
  if ( !result )
  {
    if ( a3 == a4 )
      goto LABEL_13;
    while ( 1 )
    {
      v9 = *v6;
      Library = (HMODULE)qword_14003C828[v9];
      if ( Library )
      {
        if ( Library != (HMODULE)-1LL )
          goto LABEL_18;
      }
      else
      {
        v11 = off_140029018[v9];
        Library = LoadLibraryExW(v11, 0, 0x800u);
        if ( Library
          || GetLastError() == 87 && wcsncmp(v11, L"api-ms-", 7u) && (Library = LoadLibraryExW(v11, 0, 0)) != 0 )
        {
          if ( _InterlockedExchange64(&qword_14003C828[v9], (__int64)Library) )
            FreeLibrary(Library);
LABEL_18:
          result = GetProcAddress(Library, a2);
          if ( result )
          {
            _InterlockedExchange64(&qword_14003C840[v4], (__int64)result);
            return result;
          }
LABEL_13:
          _InterlockedExchange64(&qword_14003C840[v4], -1);
          return 0;
        }
        _InterlockedExchange64(&qword_14003C828[v9], -1);
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
0x14000b3ec  mov     [rsp+arg_0], rbx
0x14000b3f1  mov     [rsp+arg_8], rbp
0x14000b3f6  mov     [rsp+arg_10], rsi
0x14000b3fb  push    rdi
0x14000b3fc  push    r12
0x14000b3fe  push    r13
0x14000b400  push    r14
0x14000b402  push    r15
0x14000b404  sub     rsp, 20h
0x14000b408  mov     edi, ecx
0x14000b40a  lea     r15, cs:140000000h
0x14000b411  or      r14, 0FFFFFFFFFFFFFFFFh
0x14000b415  mov     r12, r9
0x14000b418  mov     rbp, r8
0x14000b41b  mov     r13, rdx
0x14000b41e  mov     rax, rva qword_14003C840[r15+rdi*8]
0x14000b426  nop
0x14000b427  cmp     rax, r14
0x14000b42a  jz      loc_14000B4DE
0x14000b430  test    rax, rax
0x14000b433  jnz     loc_14000B4E0
0x14000b439  cmp     r8, r9
0x14000b43c  jz      loc_14000B4D6
0x14000b442  mov     esi, [rbp+0]
0x14000b445  mov     rbx, rva qword_14003C828[r15+rsi*8]
0x14000b44d  nop
0x14000b44e  test    rbx, rbx
0x14000b451  jz      short loc_14000B45E
0x14000b453  cmp     rbx, r14
0x14000b456  jnz     loc_14000B51D
0x14000b45c  jmp     short loc_14000B4C9
0x14000b45e  mov     r15, ds:rva off_140029018[r15+rsi*8]
0x14000b466  xor     edx, edx; hFile
0x14000b468  mov     rcx, r15; lpLibFileName
0x14000b46b  mov     r8d, 800h; dwFlags
0x14000b471  call    cs:__imp_LoadLibraryExW
0x14000b477  mov     rbx, rax
0x14000b47a  test    rax, rax
0x14000b47d  jnz     short loc_14000B4FD
0x14000b47f  call    cs:__imp_GetLastError
0x14000b485  cmp     eax, 57h ; 'W'
0x14000b488  jnz     short loc_14000B4B7
0x14000b48a  lea     r8d, [rbx+7]; MaxCount
0x14000b48e  mov     rcx, r15; String1
0x14000b491  lea     rdx, aApiMs
0x14000b498  call    wcsncmp
0x14000b49d  test    eax, eax
0x14000b49f  jz      short loc_14000B4B7
0x14000b4a1  xor     r8d, r8d; dwFlags
0x14000b4a4  xor     edx, edx; hFile
0x14000b4a6  mov     rcx, r15; lpLibFileName
0x14000b4a9  call    cs:__imp_LoadLibraryExW
0x14000b4af  mov     rbx, rax
0x14000b4b2  test    rax, rax
0x14000b4b5  jnz     short loc_14000B4FD
0x14000b4b7  mov     rax, r14
0x14000b4ba  lea     r15, cs:140000000h
0x14000b4c1  xchg    rax, rva qword_14003C828[r15+rsi*8]
0x14000b4c9  add     rbp, 4
0x14000b4cd  cmp     rbp, r12
0x14000b4d0  jnz     loc_14000B442
0x14000b4d6  xchg    r14, rva qword_14003C840[r15+rdi*8]
0x14000b4de  xor     eax, eax
0x14000b4e0  mov     rbx, [rsp+48h+arg_0]
0x14000b4e5  mov     rbp, [rsp+48h+arg_8]
0x14000b4ea  mov     rsi, [rsp+48h+arg_10]
0x14000b4ef  add     rsp, 20h
0x14000b4f3  pop     r15
0x14000b4f5  pop     r14
0x14000b4f7  pop     r13
0x14000b4f9  pop     r12
0x14000b4fb  pop     rdi
0x14000b4fc  retn
0x14000b4fd  mov     rax, rbx
0x14000b500  lea     r15, cs:140000000h
0x14000b507  xchg    rax, rva qword_14003C828[r15+rsi*8]
0x14000b50f  test    rax, rax
0x14000b512  jz      short loc_14000B51D
0x14000b514  mov     rcx, rbx; hLibModule
0x14000b517  call    cs:__imp_FreeLibrary
0x14000b51d  mov     rdx, r13; lpProcName
0x14000b520  mov     rcx, rbx; hModule
0x14000b523  call    cs:__imp_GetProcAddress
0x14000b529  test    rax, rax
0x14000b52c  jz      short loc_14000B4D6
0x14000b52e  mov     rcx, rax
0x14000b531  xchg    rcx, rva qword_14003C840[r15+rdi*8]
0x14000b539  jmp     short loc_14000B4E0
```
