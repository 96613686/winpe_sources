# try_get_module

- ea: `0x18000d20c`
- end: `0x18000d306`
- name: `try_get_module`
- size: `250`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000d20c`
- `0x1800145d0`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18000d261`
- `KERNEL32!LoadLibraryExW` at `0x18000d2b1`
- `KERNEL32!LoadLibraryExW` at `0x18000d261`
- `KERNEL32!LoadLibraryExW` at `0x18000d2b1`
- `KERNEL32!FreeLibrary` at `0x18000d2d2`
- `KERNEL32!FreeLibrary` at `0x18000d2d2`
- `KERNEL32!GetLastError` at `0x18000d26f`
- `KERNEL32!GetLastError` at `0x18000d26f`

## pseudocode

```c
__int64 __fastcall try_get_module(unsigned int a1)
{
  __int64 v1; // rdi
  __int64 result; // rax
  const WCHAR *v3; // rsi
  HMODULE Library; // rbx

  v1 = a1;
  result = qword_18007BF30[a1];
  if ( result )
  {
    if ( result == -1 )
      return 0;
  }
  else
  {
    v3 = off_180067190[a1];
    Library = LoadLibraryExW(v3, 0, 0x800u);
    if ( Library
      || GetLastError() == 87
      && wcsncmp(v3, L"api-ms-", 7u)
      && wcsncmp(v3, L"ext-ms-", 7u)
      && (Library = LoadLibraryExW(v3, 0, 0)) != 0 )
    {
      if ( _InterlockedExchange64(&qword_18007BF30[v1], (__int64)Library) )
        FreeLibrary(Library);
      return (__int64)Library;
    }
    else
    {
      _InterlockedExchange64(&qword_18007BF30[v1], -1);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000d20c  mov     rax, rsp
0x18000d20f  mov     [rax+8], rbx
0x18000d213  mov     [rax+10h], rbp
0x18000d217  mov     [rax+18h], rsi
0x18000d21b  mov     [rax+20h], rdi
0x18000d21f  push    r14
0x18000d221  sub     rsp, 20h
0x18000d225  mov     edi, ecx
0x18000d227  lea     r14, cs:180000000h
0x18000d22e  xor     ebp, ebp
0x18000d230  mov     rax, rva qword_18007BF30[r14+rdi*8]
0x18000d238  nop
0x18000d239  test    rax, rax
0x18000d23c  jz      short loc_18000D24E
0x18000d23e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000d242  cmp     rax, rcx
0x18000d245  cmovz   rax, rbp
0x18000d249  jmp     loc_18000D2EB
0x18000d24e  mov     rsi, ds:rva off_180067190[r14+rdi*8]; "api-ms-win-core-datetime-l1-1-1" ...
0x18000d256  xor     edx, edx; hFile
0x18000d258  mov     rcx, rsi; lpLibFileName
0x18000d25b  mov     r8d, 800h; dwFlags
0x18000d261  call    cs:__imp_LoadLibraryExW
0x18000d267  mov     rbx, rax
0x18000d26a  test    rax, rax
0x18000d26d  jnz     short loc_18000D2BF
0x18000d26f  call    cs:__imp_GetLastError
0x18000d275  cmp     eax, 57h ; 'W'
0x18000d278  jnz     short loc_18000D2DD
0x18000d27a  lea     ebx, [rax-50h]
0x18000d27d  mov     rcx, rsi; String1
0x18000d280  mov     r8d, ebx; MaxCount
0x18000d283  lea     rdx, aApiMs; "api-ms-"
0x18000d28a  call    wcsncmp
0x18000d28f  test    eax, eax
0x18000d291  jz      short loc_18000D2DD
0x18000d293  mov     r8d, ebx; MaxCount
0x18000d296  lea     rdx, aExtMs; "ext-ms-"
0x18000d29d  mov     rcx, rsi; String1
0x18000d2a0  call    wcsncmp
0x18000d2a5  test    eax, eax
0x18000d2a7  jz      short loc_18000D2DD
0x18000d2a9  xor     r8d, r8d; dwFlags
0x18000d2ac  xor     edx, edx; hFile
0x18000d2ae  mov     rcx, rsi; lpLibFileName
0x18000d2b1  call    cs:__imp_LoadLibraryExW
0x18000d2b7  mov     rbx, rax
0x18000d2ba  test    rax, rax
0x18000d2bd  jz      short loc_18000D2DD
0x18000d2bf  mov     rcx, rbx
0x18000d2c2  xchg    rcx, rva qword_18007BF30[r14+rdi*8]
0x18000d2ca  test    rcx, rcx
0x18000d2cd  jz      short loc_18000D2D8
0x18000d2cf  mov     rcx, rbx; hLibModule
0x18000d2d2  call    cs:__imp_FreeLibrary
0x18000d2d8  mov     rax, rbx
0x18000d2db  jmp     short loc_18000D2EB
0x18000d2dd  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000d2e1  xchg    rcx, rva qword_18007BF30[r14+rdi*8]
0x18000d2e9  xor     eax, eax
0x18000d2eb  mov     rbx, [rsp+28h+arg_0]
0x18000d2f0  mov     rbp, [rsp+28h+arg_8]
0x18000d2f5  mov     rsi, [rsp+28h+arg_10]
0x18000d2fa  mov     rdi, [rsp+28h+arg_18]
0x18000d2ff  add     rsp, 20h
0x18000d303  pop     r14
0x18000d305  retn
```
