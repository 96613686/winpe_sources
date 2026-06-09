# try_get_proc_address_from_first_available_module

- ea: `0x18000cba8`
- end: `0x18000ccd2`
- name: `try_get_proc_address_from_first_available_module`
- size: `298`
- prototype: `__int64 __fastcall(LPCSTR lpProcName)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000cba8`
- `0x180013e70`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18000ccbe`
- `KERNEL32!FreeLibrary` at `0x18000ccbe`
- `KERNEL32!GetProcAddress` at `0x18000ccca`
- `KERNEL32!GetProcAddress` at `0x18000ccca`
- `KERNEL32!GetLastError` at `0x18000cc22`
- `KERNEL32!GetLastError` at `0x18000cc22`
- `KERNEL32!LoadLibraryExW` at `0x18000cc10`
- `KERNEL32!LoadLibraryExW` at `0x18000cc63`
- `KERNEL32!LoadLibraryExW` at `0x18000cc10`
- `KERNEL32!LoadLibraryExW` at `0x18000cc63`

## pseudocode

```c
FARPROC __fastcall try_get_proc_address_from_first_available_module(LPCSTR lpProcName, unsigned int *a2, unsigned int *a3)
{
  unsigned int *v4; // rdi
  __int64 v6; // rsi
  HMODULE Library; // rbx
  const WCHAR *v8; // rbp

  v4 = a2;
  if ( a2 == a3 )
    return 0;
  while ( 1 )
  {
    v6 = *v4;
    Library = (HMODULE)qword_180078480[v6];
    if ( !Library )
      break;
    if ( Library != (HMODULE)-1LL )
      return GetProcAddress(Library, lpProcName);
LABEL_11:
    if ( ++v4 == a3 )
      return 0;
  }
  v8 = off_180063AB0[v6];
  Library = LoadLibraryExW(v8, 0, 0x800u);
  if ( !Library
    && (GetLastError() != 87
     || !wcsncmp(v8, L"api-ms-", 7u)
     || !wcsncmp(v8, L"ext-ms-", 7u)
     || (Library = LoadLibraryExW(v8, 0, 0)) == 0) )
  {
    _InterlockedExchange64(&qword_180078480[v6], -1);
    goto LABEL_11;
  }
  if ( _InterlockedExchange64(&qword_180078480[v6], (__int64)Library) )
    FreeLibrary(Library);
  return GetProcAddress(Library, lpProcName);
}

```

## disassembly

```asm
0x18000cba8  mov     rax, rsp
0x18000cbab  mov     [rax+8], rbx
0x18000cbaf  mov     [rax+10h], rbp
0x18000cbb3  mov     [rax+18h], rsi
0x18000cbb7  mov     [rax+20h], rdi
0x18000cbbb  push    r12
0x18000cbbd  push    r14
0x18000cbbf  push    r15
0x18000cbc1  sub     rsp, 20h
0x18000cbc5  mov     r14, r8
0x18000cbc8  mov     rdi, rdx
0x18000cbcb  mov     r15, rcx
0x18000cbce  cmp     rdx, r8
0x18000cbd1  jz      loc_18000CC8A
0x18000cbd7  lea     r12, cs:180000000h
0x18000cbde  mov     esi, [rdi]
0x18000cbe0  mov     rbx, rva qword_180078480[r12+rsi*8]
0x18000cbe8  nop
0x18000cbe9  test    rbx, rbx
0x18000cbec  jz      short loc_18000CBFD
0x18000cbee  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000cbf2  jnz     loc_18000CCC4
0x18000cbf8  jmp     loc_18000CC7D
0x18000cbfd  mov     rbp, ds:rva off_180063AB0[r12+rsi*8]; "api-ms-win-core-datetime-l1-1-1" ...
0x18000cc05  xor     edx, edx; hFile
0x18000cc07  mov     rcx, rbp; lpLibFileName
0x18000cc0a  mov     r8d, 800h; dwFlags
0x18000cc10  call    cs:__imp_LoadLibraryExW
0x18000cc16  mov     rbx, rax
0x18000cc19  test    rax, rax
0x18000cc1c  jnz     loc_18000CCAB
0x18000cc22  call    cs:__imp_GetLastError
0x18000cc28  cmp     eax, 57h ; 'W'
0x18000cc2b  jnz     short loc_18000CC71
0x18000cc2d  lea     r8d, [rbx+7]; MaxCount
0x18000cc31  mov     rcx, rbp; String1
0x18000cc34  lea     rdx, aApiMs; "api-ms-"
0x18000cc3b  call    wcsncmp
0x18000cc40  test    eax, eax
0x18000cc42  jz      short loc_18000CC71
0x18000cc44  lea     r8d, [rbx+7]; MaxCount
0x18000cc48  mov     rcx, rbp; String1
0x18000cc4b  lea     rdx, aExtMs; "ext-ms-"
0x18000cc52  call    wcsncmp
0x18000cc57  test    eax, eax
0x18000cc59  jz      short loc_18000CC71
0x18000cc5b  xor     r8d, r8d; dwFlags
0x18000cc5e  xor     edx, edx; hFile
0x18000cc60  mov     rcx, rbp; lpLibFileName
0x18000cc63  call    cs:__imp_LoadLibraryExW
0x18000cc69  mov     rbx, rax
0x18000cc6c  test    rax, rax
0x18000cc6f  jnz     short loc_18000CCAB
0x18000cc71  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000cc75  xchg    rax, rva qword_180078480[r12+rsi*8]
0x18000cc7d  add     rdi, 4
0x18000cc81  cmp     rdi, r14
0x18000cc84  jnz     loc_18000CBDE
0x18000cc8a  xor     eax, eax
0x18000cc8c  mov     rbx, [rsp+38h+arg_0]
0x18000cc91  mov     rbp, [rsp+38h+arg_8]
0x18000cc96  mov     rsi, [rsp+38h+arg_10]
0x18000cc9b  mov     rdi, [rsp+38h+arg_18]
0x18000cca0  add     rsp, 20h
0x18000cca4  pop     r15
0x18000cca6  pop     r14
0x18000cca8  pop     r12
0x18000ccaa  retn
0x18000ccab  mov     rax, rbx
0x18000ccae  xchg    rax, rva qword_180078480[r12+rsi*8]
0x18000ccb6  test    rax, rax
0x18000ccb9  jz      short loc_18000CCC4
0x18000ccbb  mov     rcx, rbx; hLibModule
0x18000ccbe  call    cs:__imp_FreeLibrary
0x18000ccc4  mov     rdx, r15; lpProcName
0x18000ccc7  mov     rcx, rbx; hModule
0x18000ccca  call    cs:__imp_GetProcAddress
0x18000ccd0  jmp     short loc_18000CC8C
```
