# try_get_proc_address_from_first_available_module_0

- ea: `0x180031cf0`
- end: `0x180031dfc`
- name: `try_get_proc_address_from_first_available_module_0`
- size: `268`
- prototype: `__int64 __fastcall(LPCSTR lpProcName)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180013e70`
- `0x180031cf0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180031de8`
- `KERNEL32!FreeLibrary` at `0x180031de8`
- `KERNEL32!GetProcAddress` at `0x180031df4`
- `KERNEL32!GetProcAddress` at `0x180031df4`
- `KERNEL32!GetLastError` at `0x180031d63`
- `KERNEL32!GetLastError` at `0x180031d63`
- `KERNEL32!LoadLibraryExW` at `0x180031d55`
- `KERNEL32!LoadLibraryExW` at `0x180031d8d`
- `KERNEL32!LoadLibraryExW` at `0x180031d55`
- `KERNEL32!LoadLibraryExW` at `0x180031d8d`

## pseudocode

```c
FARPROC __fastcall try_get_proc_address_from_first_available_module_0(LPCSTR lpProcName, unsigned int *a2, unsigned int *a3)
{
  unsigned int *v4; // rdi
  __int64 v6; // rsi
  HMODULE Library; // rbx
  const WCHAR *v8; // r14

  v4 = a2;
  if ( a2 == a3 )
    return 0;
  while ( 1 )
  {
    v6 = *v4;
    Library = (HMODULE)qword_1800790F0[v6];
    if ( !Library )
      break;
    if ( Library != (HMODULE)-1LL )
      return GetProcAddress(Library, lpProcName);
LABEL_10:
    if ( ++v4 == a3 )
      return 0;
  }
  v8 = off_18006B048[v6];
  Library = LoadLibraryExW(v8, 0, 0x800u);
  if ( !Library && (GetLastError() != 87 || !wcsncmp(v8, L"api-ms-", 7u) || (Library = LoadLibraryExW(v8, 0, 0)) == 0) )
  {
    _InterlockedExchange64(&qword_1800790F0[v6], -1);
    goto LABEL_10;
  }
  if ( _InterlockedExchange64(&qword_1800790F0[v6], (__int64)Library) )
    FreeLibrary(Library);
  return GetProcAddress(Library, lpProcName);
}

```

## disassembly

```asm
0x180031cf0  mov     rax, rsp
0x180031cf3  mov     [rax+8], rbx
0x180031cf7  mov     [rax+10h], rbp
0x180031cfb  mov     [rax+18h], rsi
0x180031cff  mov     [rax+20h], rdi
0x180031d03  push    r12
0x180031d05  push    r14
0x180031d07  push    r15
0x180031d09  sub     rsp, 20h
0x180031d0d  mov     rbp, r8
0x180031d10  mov     rdi, rdx
0x180031d13  mov     r15, rcx
0x180031d16  cmp     rdx, r8
0x180031d19  jz      loc_180031DB4
0x180031d1f  lea     r12, cs:180000000h
0x180031d26  mov     esi, [rdi]
0x180031d28  mov     rbx, rva qword_1800790F0[r12+rsi*8]
0x180031d30  nop
0x180031d31  test    rbx, rbx
0x180031d34  jz      short loc_180031D42
0x180031d36  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180031d3a  jnz     loc_180031DEE
0x180031d40  jmp     short loc_180031DA7
0x180031d42  mov     r14, ds:rva off_18006B048[r12+rsi*8]; "api-ms-win-core-fibers-l1-1-1" ...
0x180031d4a  xor     edx, edx; hFile
0x180031d4c  mov     rcx, r14; lpLibFileName
0x180031d4f  mov     r8d, 800h; dwFlags
0x180031d55  call    cs:__imp_LoadLibraryExW
0x180031d5b  mov     rbx, rax
0x180031d5e  test    rax, rax
0x180031d61  jnz     short loc_180031DD5
0x180031d63  call    cs:__imp_GetLastError
0x180031d69  cmp     eax, 57h ; 'W'
0x180031d6c  jnz     short loc_180031D9B
0x180031d6e  lea     r8d, [rbx+7]; MaxCount
0x180031d72  mov     rcx, r14; String1
0x180031d75  lea     rdx, aApiMs; "api-ms-"
0x180031d7c  call    wcsncmp
0x180031d81  test    eax, eax
0x180031d83  jz      short loc_180031D9B
0x180031d85  xor     r8d, r8d; dwFlags
0x180031d88  xor     edx, edx; hFile
0x180031d8a  mov     rcx, r14; lpLibFileName
0x180031d8d  call    cs:__imp_LoadLibraryExW
0x180031d93  mov     rbx, rax
0x180031d96  test    rax, rax
0x180031d99  jnz     short loc_180031DD5
0x180031d9b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180031d9f  xchg    rax, rva qword_1800790F0[r12+rsi*8]
0x180031da7  add     rdi, 4
0x180031dab  cmp     rdi, rbp
0x180031dae  jnz     loc_180031D26
0x180031db4  xor     eax, eax
0x180031db6  mov     rbx, [rsp+38h+arg_0]
0x180031dbb  mov     rbp, [rsp+38h+arg_8]
0x180031dc0  mov     rsi, [rsp+38h+arg_10]
0x180031dc5  mov     rdi, [rsp+38h+arg_18]
0x180031dca  add     rsp, 20h
0x180031dce  pop     r15
0x180031dd0  pop     r14
0x180031dd2  pop     r12
0x180031dd4  retn
0x180031dd5  mov     rax, rbx
0x180031dd8  xchg    rax, rva qword_1800790F0[r12+rsi*8]
0x180031de0  test    rax, rax
0x180031de3  jz      short loc_180031DEE
0x180031de5  mov     rcx, rbx; hLibModule
0x180031de8  call    cs:__imp_FreeLibrary
0x180031dee  mov     rdx, r15; lpProcName
0x180031df1  mov     rcx, rbx; hModule
0x180031df4  call    cs:__imp_GetProcAddress
0x180031dfa  jmp     short loc_180031DB6
```
