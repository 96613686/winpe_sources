# try_get_module

- ea: `0x18000caac`
- end: `0x18000cba6`
- name: `try_get_module`
- size: `250`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000caac`
- `0x180013e70`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18000cb72`
- `KERNEL32!FreeLibrary` at `0x18000cb72`
- `KERNEL32!GetLastError` at `0x18000cb0f`
- `KERNEL32!GetLastError` at `0x18000cb0f`
- `KERNEL32!LoadLibraryExW` at `0x18000cb01`
- `KERNEL32!LoadLibraryExW` at `0x18000cb51`
- `KERNEL32!LoadLibraryExW` at `0x18000cb01`
- `KERNEL32!LoadLibraryExW` at `0x18000cb51`

## pseudocode

```c
__int64 __fastcall try_get_module(unsigned int a1)
{
  __int64 v1; // rdi
  __int64 result; // rax
  const WCHAR *v3; // rsi
  HMODULE Library; // rbx

  v1 = a1;
  result = qword_180078480[a1];
  if ( result )
  {
    if ( result == -1 )
      return 0;
  }
  else
  {
    v3 = off_180063AB0[a1];
    Library = LoadLibraryExW(v3, 0, 0x800u);
    if ( Library
      || GetLastError() == 87
      && wcsncmp(v3, L"api-ms-", 7u)
      && wcsncmp(v3, L"ext-ms-", 7u)
      && (Library = LoadLibraryExW(v3, 0, 0)) != 0 )
    {
      if ( _InterlockedExchange64(&qword_180078480[v1], (__int64)Library) )
        FreeLibrary(Library);
      return (__int64)Library;
    }
    else
    {
      _InterlockedExchange64(&qword_180078480[v1], -1);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000caac  mov     rax, rsp
0x18000caaf  mov     [rax+8], rbx
0x18000cab3  mov     [rax+10h], rbp
0x18000cab7  mov     [rax+18h], rsi
0x18000cabb  mov     [rax+20h], rdi
0x18000cabf  push    r14
0x18000cac1  sub     rsp, 20h
0x18000cac5  mov     edi, ecx
0x18000cac7  lea     r14, cs:180000000h
0x18000cace  xor     ebp, ebp
0x18000cad0  mov     rax, rva qword_180078480[r14+rdi*8]
0x18000cad8  nop
0x18000cad9  test    rax, rax
0x18000cadc  jz      short loc_18000CAEE
0x18000cade  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000cae2  cmp     rax, rcx
0x18000cae5  cmovz   rax, rbp
0x18000cae9  jmp     loc_18000CB8B
0x18000caee  mov     rsi, ds:rva off_180063AB0[r14+rdi*8]; "api-ms-win-core-datetime-l1-1-1" ...
0x18000caf6  xor     edx, edx; hFile
0x18000caf8  mov     rcx, rsi; lpLibFileName
0x18000cafb  mov     r8d, 800h; dwFlags
0x18000cb01  call    cs:__imp_LoadLibraryExW
0x18000cb07  mov     rbx, rax
0x18000cb0a  test    rax, rax
0x18000cb0d  jnz     short loc_18000CB5F
0x18000cb0f  call    cs:__imp_GetLastError
0x18000cb15  cmp     eax, 57h ; 'W'
0x18000cb18  jnz     short loc_18000CB7D
0x18000cb1a  lea     ebx, [rax-50h]
0x18000cb1d  mov     rcx, rsi; String1
0x18000cb20  mov     r8d, ebx; MaxCount
0x18000cb23  lea     rdx, aApiMs; "api-ms-"
0x18000cb2a  call    wcsncmp
0x18000cb2f  test    eax, eax
0x18000cb31  jz      short loc_18000CB7D
0x18000cb33  mov     r8d, ebx; MaxCount
0x18000cb36  lea     rdx, aExtMs; "ext-ms-"
0x18000cb3d  mov     rcx, rsi; String1
0x18000cb40  call    wcsncmp
0x18000cb45  test    eax, eax
0x18000cb47  jz      short loc_18000CB7D
0x18000cb49  xor     r8d, r8d; dwFlags
0x18000cb4c  xor     edx, edx; hFile
0x18000cb4e  mov     rcx, rsi; lpLibFileName
0x18000cb51  call    cs:__imp_LoadLibraryExW
0x18000cb57  mov     rbx, rax
0x18000cb5a  test    rax, rax
0x18000cb5d  jz      short loc_18000CB7D
0x18000cb5f  mov     rcx, rbx
0x18000cb62  xchg    rcx, rva qword_180078480[r14+rdi*8]
0x18000cb6a  test    rcx, rcx
0x18000cb6d  jz      short loc_18000CB78
0x18000cb6f  mov     rcx, rbx; hLibModule
0x18000cb72  call    cs:__imp_FreeLibrary
0x18000cb78  mov     rax, rbx
0x18000cb7b  jmp     short loc_18000CB8B
0x18000cb7d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000cb81  xchg    rcx, rva qword_180078480[r14+rdi*8]
0x18000cb89  xor     eax, eax
0x18000cb8b  mov     rbx, [rsp+28h+arg_0]
0x18000cb90  mov     rbp, [rsp+28h+arg_8]
0x18000cb95  mov     rsi, [rsp+28h+arg_10]
0x18000cb9a  mov     rdi, [rsp+28h+arg_18]
0x18000cb9f  add     rsp, 20h
0x18000cba3  pop     r14
0x18000cba5  retn
```
