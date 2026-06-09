# try_get_module_0

- ea: `0x18003236c`
- end: `0x18003244e`
- name: `try_get_module_0`
- size: `226`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800145d0`
- `0x18003236c`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800323c1`
- `KERNEL32!LoadLibraryExW` at `0x1800323f9`
- `KERNEL32!LoadLibraryExW` at `0x1800323c1`
- `KERNEL32!LoadLibraryExW` at `0x1800323f9`
- `KERNEL32!FreeLibrary` at `0x18003241a`
- `KERNEL32!FreeLibrary` at `0x18003241a`
- `KERNEL32!GetLastError` at `0x1800323cf`
- `KERNEL32!GetLastError` at `0x1800323cf`

## pseudocode

```c
__int64 __fastcall try_get_module_0(unsigned int a1)
{
  __int64 v1; // rdi
  __int64 result; // rax
  const WCHAR *v3; // rsi
  HMODULE Library; // rbx

  v1 = a1;
  result = qword_18007CBA0[a1];
  if ( result )
  {
    if ( result == -1 )
      return 0;
  }
  else
  {
    v3 = off_18006E728[a1];
    Library = LoadLibraryExW(v3, 0, 0x800u);
    if ( Library || GetLastError() == 87 && wcsncmp(v3, L"api-ms-", 7u) && (Library = LoadLibraryExW(v3, 0, 0)) != 0 )
    {
      if ( _InterlockedExchange64(&qword_18007CBA0[v1], (__int64)Library) )
        FreeLibrary(Library);
      return (__int64)Library;
    }
    else
    {
      _InterlockedExchange64(&qword_18007CBA0[v1], -1);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003236c  mov     rax, rsp
0x18003236f  mov     [rax+8], rbx
0x180032373  mov     [rax+10h], rbp
0x180032377  mov     [rax+18h], rsi
0x18003237b  mov     [rax+20h], rdi
0x18003237f  push    r14
0x180032381  sub     rsp, 20h
0x180032385  mov     edi, ecx
0x180032387  lea     r14, cs:180000000h
0x18003238e  xor     ebp, ebp
0x180032390  mov     rax, rva qword_18007CBA0[r14+rdi*8]
0x180032398  nop
0x180032399  test    rax, rax
0x18003239c  jz      short loc_1800323AE
0x18003239e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800323a2  cmp     rax, rcx
0x1800323a5  cmovz   rax, rbp
0x1800323a9  jmp     loc_180032433
0x1800323ae  mov     rsi, ds:rva off_18006E728[r14+rdi*8]; "api-ms-win-core-fibers-l1-1-1" ...
0x1800323b6  xor     edx, edx; hFile
0x1800323b8  mov     rcx, rsi; lpLibFileName
0x1800323bb  mov     r8d, 800h; dwFlags
0x1800323c1  call    cs:__imp_LoadLibraryExW
0x1800323c7  mov     rbx, rax
0x1800323ca  test    rax, rax
0x1800323cd  jnz     short loc_180032407
0x1800323cf  call    cs:__imp_GetLastError
0x1800323d5  cmp     eax, 57h ; 'W'
0x1800323d8  jnz     short loc_180032425
0x1800323da  lea     r8d, [rbx+7]; MaxCount
0x1800323de  mov     rcx, rsi; String1
0x1800323e1  lea     rdx, aApiMs; "api-ms-"
0x1800323e8  call    wcsncmp
0x1800323ed  test    eax, eax
0x1800323ef  jz      short loc_180032425
0x1800323f1  xor     r8d, r8d; dwFlags
0x1800323f4  xor     edx, edx; hFile
0x1800323f6  mov     rcx, rsi; lpLibFileName
0x1800323f9  call    cs:__imp_LoadLibraryExW
0x1800323ff  mov     rbx, rax
0x180032402  test    rax, rax
0x180032405  jz      short loc_180032425
0x180032407  mov     rcx, rbx
0x18003240a  xchg    rcx, rva qword_18007CBA0[r14+rdi*8]
0x180032412  test    rcx, rcx
0x180032415  jz      short loc_180032420
0x180032417  mov     rcx, rbx; hLibModule
0x18003241a  call    cs:__imp_FreeLibrary
0x180032420  mov     rax, rbx
0x180032423  jmp     short loc_180032433
0x180032425  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180032429  xchg    rcx, rva qword_18007CBA0[r14+rdi*8]
0x180032431  xor     eax, eax
0x180032433  mov     rbx, [rsp+28h+arg_0]
0x180032438  mov     rbp, [rsp+28h+arg_8]
0x18003243d  mov     rsi, [rsp+28h+arg_10]
0x180032442  mov     rdi, [rsp+28h+arg_18]
0x180032447  add     rsp, 20h
0x18003244b  pop     r14
0x18003244d  retn
```
