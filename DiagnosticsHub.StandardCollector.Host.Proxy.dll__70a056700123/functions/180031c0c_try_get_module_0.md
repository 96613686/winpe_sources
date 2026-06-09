# try_get_module_0

- ea: `0x180031c0c`
- end: `0x180031cee`
- name: `try_get_module_0`
- size: `226`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180013e70`
- `0x180031c0c`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180031cba`
- `KERNEL32!FreeLibrary` at `0x180031cba`
- `KERNEL32!GetLastError` at `0x180031c6f`
- `KERNEL32!GetLastError` at `0x180031c6f`
- `KERNEL32!LoadLibraryExW` at `0x180031c61`
- `KERNEL32!LoadLibraryExW` at `0x180031c99`
- `KERNEL32!LoadLibraryExW` at `0x180031c61`
- `KERNEL32!LoadLibraryExW` at `0x180031c99`

## pseudocode

```c
__int64 __fastcall try_get_module_0(unsigned int a1)
{
  __int64 v1; // rdi
  __int64 result; // rax
  const WCHAR *v3; // rsi
  HMODULE Library; // rbx

  v1 = a1;
  result = qword_1800790F0[a1];
  if ( result )
  {
    if ( result == -1 )
      return 0;
  }
  else
  {
    v3 = off_18006B048[a1];
    Library = LoadLibraryExW(v3, 0, 0x800u);
    if ( Library || GetLastError() == 87 && wcsncmp(v3, L"api-ms-", 7u) && (Library = LoadLibraryExW(v3, 0, 0)) != 0 )
    {
      if ( _InterlockedExchange64(&qword_1800790F0[v1], (__int64)Library) )
        FreeLibrary(Library);
      return (__int64)Library;
    }
    else
    {
      _InterlockedExchange64(&qword_1800790F0[v1], -1);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180031c0c  mov     rax, rsp
0x180031c0f  mov     [rax+8], rbx
0x180031c13  mov     [rax+10h], rbp
0x180031c17  mov     [rax+18h], rsi
0x180031c1b  mov     [rax+20h], rdi
0x180031c1f  push    r14
0x180031c21  sub     rsp, 20h
0x180031c25  mov     edi, ecx
0x180031c27  lea     r14, cs:180000000h
0x180031c2e  xor     ebp, ebp
0x180031c30  mov     rax, rva qword_1800790F0[r14+rdi*8]
0x180031c38  nop
0x180031c39  test    rax, rax
0x180031c3c  jz      short loc_180031C4E
0x180031c3e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180031c42  cmp     rax, rcx
0x180031c45  cmovz   rax, rbp
0x180031c49  jmp     loc_180031CD3
0x180031c4e  mov     rsi, ds:rva off_18006B048[r14+rdi*8]; "api-ms-win-core-fibers-l1-1-1" ...
0x180031c56  xor     edx, edx; hFile
0x180031c58  mov     rcx, rsi; lpLibFileName
0x180031c5b  mov     r8d, 800h; dwFlags
0x180031c61  call    cs:__imp_LoadLibraryExW
0x180031c67  mov     rbx, rax
0x180031c6a  test    rax, rax
0x180031c6d  jnz     short loc_180031CA7
0x180031c6f  call    cs:__imp_GetLastError
0x180031c75  cmp     eax, 57h ; 'W'
0x180031c78  jnz     short loc_180031CC5
0x180031c7a  lea     r8d, [rbx+7]; MaxCount
0x180031c7e  mov     rcx, rsi; String1
0x180031c81  lea     rdx, aApiMs; "api-ms-"
0x180031c88  call    wcsncmp
0x180031c8d  test    eax, eax
0x180031c8f  jz      short loc_180031CC5
0x180031c91  xor     r8d, r8d; dwFlags
0x180031c94  xor     edx, edx; hFile
0x180031c96  mov     rcx, rsi; lpLibFileName
0x180031c99  call    cs:__imp_LoadLibraryExW
0x180031c9f  mov     rbx, rax
0x180031ca2  test    rax, rax
0x180031ca5  jz      short loc_180031CC5
0x180031ca7  mov     rcx, rbx
0x180031caa  xchg    rcx, rva qword_1800790F0[r14+rdi*8]
0x180031cb2  test    rcx, rcx
0x180031cb5  jz      short loc_180031CC0
0x180031cb7  mov     rcx, rbx; hLibModule
0x180031cba  call    cs:__imp_FreeLibrary
0x180031cc0  mov     rax, rbx
0x180031cc3  jmp     short loc_180031CD3
0x180031cc5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180031cc9  xchg    rcx, rva qword_1800790F0[r14+rdi*8]
0x180031cd1  xor     eax, eax
0x180031cd3  mov     rbx, [rsp+28h+arg_0]
0x180031cd8  mov     rbp, [rsp+28h+arg_8]
0x180031cdd  mov     rsi, [rsp+28h+arg_10]
0x180031ce2  mov     rdi, [rsp+28h+arg_18]
0x180031ce7  add     rsp, 20h
0x180031ceb  pop     r14
0x180031ced  retn
```
