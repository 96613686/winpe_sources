# try_get_first_available_module

- ea: `0x18000c7b4`
- end: `0x18000c8c7`
- name: `try_get_first_available_module`
- size: `275`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000c7b4`
- `0x180013e70`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18000c8bc`
- `KERNEL32!FreeLibrary` at `0x18000c8bc`
- `KERNEL32!GetLastError` at `0x18000c826`
- `KERNEL32!GetLastError` at `0x18000c826`
- `KERNEL32!LoadLibraryExW` at `0x18000c814`
- `KERNEL32!LoadLibraryExW` at `0x18000c867`
- `KERNEL32!LoadLibraryExW` at `0x18000c814`
- `KERNEL32!LoadLibraryExW` at `0x18000c867`

## pseudocode

```c
HMODULE __fastcall try_get_first_available_module(unsigned int *a1, unsigned int *a2)
{
  unsigned int *v3; // rdi
  __int64 v4; // rsi
  HMODULE Library; // rbx
  const WCHAR *v6; // r14

  v3 = a1;
  if ( a1 == a2 )
    return 0;
  while ( 1 )
  {
    v4 = *v3;
    Library = (HMODULE)qword_180078480[v4];
    if ( !Library )
      break;
    if ( Library != (HMODULE)-1LL )
      return Library;
LABEL_11:
    if ( ++v3 == a2 )
      return 0;
  }
  v6 = off_180063AB0[v4];
  Library = LoadLibraryExW(v6, 0, 0x800u);
  if ( !Library
    && (GetLastError() != 87
     || !wcsncmp(v6, L"api-ms-", 7u)
     || !wcsncmp(v6, L"ext-ms-", 7u)
     || (Library = LoadLibraryExW(v6, 0, 0)) == 0) )
  {
    _InterlockedExchange64(&qword_180078480[v4], -1);
    goto LABEL_11;
  }
  if ( _InterlockedExchange64(&qword_180078480[v4], (__int64)Library) )
    FreeLibrary(Library);
  return Library;
}

```

## disassembly

```asm
0x18000c7b4  mov     [rsp+arg_0], rbx
0x18000c7b9  mov     [rsp+arg_8], rbp
0x18000c7be  mov     [rsp+arg_10], rsi
0x18000c7c3  push    rdi
0x18000c7c4  push    r14
0x18000c7c6  push    r15
0x18000c7c8  sub     rsp, 20h
0x18000c7cc  mov     rbp, rdx
0x18000c7cf  mov     rdi, rcx
0x18000c7d2  cmp     rcx, rdx
0x18000c7d5  jz      loc_18000C88E
0x18000c7db  lea     r15, cs:180000000h
0x18000c7e2  mov     esi, [rdi]
0x18000c7e4  mov     rbx, rva qword_180078480[r15+rsi*8]
0x18000c7ec  nop
0x18000c7ed  test    rbx, rbx
0x18000c7f0  jz      short loc_18000C801
0x18000c7f2  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000c7f6  jnz     loc_18000C8C2
0x18000c7fc  jmp     loc_18000C881
0x18000c801  mov     r14, ds:rva off_180063AB0[r15+rsi*8]; "api-ms-win-core-datetime-l1-1-1" ...
0x18000c809  xor     edx, edx; hFile
0x18000c80b  mov     rcx, r14; lpLibFileName
0x18000c80e  mov     r8d, 800h; dwFlags
0x18000c814  call    cs:__imp_LoadLibraryExW
0x18000c81a  mov     rbx, rax
0x18000c81d  test    rax, rax
0x18000c820  jnz     loc_18000C8A9
0x18000c826  call    cs:__imp_GetLastError
0x18000c82c  cmp     eax, 57h ; 'W'
0x18000c82f  jnz     short loc_18000C875
0x18000c831  lea     r8d, [rbx+7]; MaxCount
0x18000c835  mov     rcx, r14; String1
0x18000c838  lea     rdx, aApiMs; "api-ms-"
0x18000c83f  call    wcsncmp
0x18000c844  test    eax, eax
0x18000c846  jz      short loc_18000C875
0x18000c848  lea     r8d, [rbx+7]; MaxCount
0x18000c84c  mov     rcx, r14; String1
0x18000c84f  lea     rdx, aExtMs; "ext-ms-"
0x18000c856  call    wcsncmp
0x18000c85b  test    eax, eax
0x18000c85d  jz      short loc_18000C875
0x18000c85f  xor     r8d, r8d; dwFlags
0x18000c862  xor     edx, edx; hFile
0x18000c864  mov     rcx, r14; lpLibFileName
0x18000c867  call    cs:__imp_LoadLibraryExW
0x18000c86d  mov     rbx, rax
0x18000c870  test    rax, rax
0x18000c873  jnz     short loc_18000C8A9
0x18000c875  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c879  xchg    rax, rva qword_180078480[r15+rsi*8]
0x18000c881  add     rdi, 4
0x18000c885  cmp     rdi, rbp
0x18000c888  jnz     loc_18000C7E2
0x18000c88e  xor     eax, eax
0x18000c890  mov     rbx, [rsp+38h+arg_0]
0x18000c895  mov     rbp, [rsp+38h+arg_8]
0x18000c89a  mov     rsi, [rsp+38h+arg_10]
0x18000c89f  add     rsp, 20h
0x18000c8a3  pop     r15
0x18000c8a5  pop     r14
0x18000c8a7  pop     rdi
0x18000c8a8  retn
0x18000c8a9  mov     rcx, rbx
0x18000c8ac  xchg    rcx, rva qword_180078480[r15+rsi*8]
0x18000c8b4  test    rcx, rcx
0x18000c8b7  jz      short loc_18000C8C2
0x18000c8b9  mov     rcx, rbx; hLibModule
0x18000c8bc  call    cs:__imp_FreeLibrary
0x18000c8c2  mov     rax, rbx
0x18000c8c5  jmp     short loc_18000C890
```
