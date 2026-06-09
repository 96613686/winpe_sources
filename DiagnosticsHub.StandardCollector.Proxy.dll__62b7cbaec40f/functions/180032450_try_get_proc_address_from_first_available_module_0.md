# try_get_proc_address_from_first_available_module_0

- ea: `0x180032450`
- end: `0x18003255c`
- name: `try_get_proc_address_from_first_available_module_0`
- size: `268`
- prototype: `__int64 __fastcall(LPCSTR lpProcName)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800145d0`
- `0x180032450`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800324b5`
- `KERNEL32!LoadLibraryExW` at `0x1800324ed`
- `KERNEL32!LoadLibraryExW` at `0x1800324b5`
- `KERNEL32!LoadLibraryExW` at `0x1800324ed`
- `KERNEL32!FreeLibrary` at `0x180032548`
- `KERNEL32!FreeLibrary` at `0x180032548`
- `KERNEL32!GetProcAddress` at `0x180032554`
- `KERNEL32!GetProcAddress` at `0x180032554`
- `KERNEL32!GetLastError` at `0x1800324c3`
- `KERNEL32!GetLastError` at `0x1800324c3`

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
    Library = (HMODULE)qword_18007CBA0[v6];
    if ( !Library )
      break;
    if ( Library != (HMODULE)-1LL )
      return GetProcAddress(Library, lpProcName);
LABEL_10:
    if ( ++v4 == a3 )
      return 0;
  }
  v8 = off_18006E728[v6];
  Library = LoadLibraryExW(v8, 0, 0x800u);
  if ( !Library && (GetLastError() != 87 || !wcsncmp(v8, L"api-ms-", 7u) || (Library = LoadLibraryExW(v8, 0, 0)) == 0) )
  {
    _InterlockedExchange64(&qword_18007CBA0[v6], -1);
    goto LABEL_10;
  }
  if ( _InterlockedExchange64(&qword_18007CBA0[v6], (__int64)Library) )
    FreeLibrary(Library);
  return GetProcAddress(Library, lpProcName);
}

```

## disassembly

```asm
0x180032450  mov     rax, rsp
0x180032453  mov     [rax+8], rbx
0x180032457  mov     [rax+10h], rbp
0x18003245b  mov     [rax+18h], rsi
0x18003245f  mov     [rax+20h], rdi
0x180032463  push    r12
0x180032465  push    r14
0x180032467  push    r15
0x180032469  sub     rsp, 20h
0x18003246d  mov     rbp, r8
0x180032470  mov     rdi, rdx
0x180032473  mov     r15, rcx
0x180032476  cmp     rdx, r8
0x180032479  jz      loc_180032514
0x18003247f  lea     r12, cs:180000000h
0x180032486  mov     esi, [rdi]
0x180032488  mov     rbx, rva qword_18007CBA0[r12+rsi*8]
0x180032490  nop
0x180032491  test    rbx, rbx
0x180032494  jz      short loc_1800324A2
0x180032496  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18003249a  jnz     loc_18003254E
0x1800324a0  jmp     short loc_180032507
0x1800324a2  mov     r14, ds:rva off_18006E728[r12+rsi*8]; "api-ms-win-core-fibers-l1-1-1" ...
0x1800324aa  xor     edx, edx; hFile
0x1800324ac  mov     rcx, r14; lpLibFileName
0x1800324af  mov     r8d, 800h; dwFlags
0x1800324b5  call    cs:__imp_LoadLibraryExW
0x1800324bb  mov     rbx, rax
0x1800324be  test    rax, rax
0x1800324c1  jnz     short loc_180032535
0x1800324c3  call    cs:__imp_GetLastError
0x1800324c9  cmp     eax, 57h ; 'W'
0x1800324cc  jnz     short loc_1800324FB
0x1800324ce  lea     r8d, [rbx+7]; MaxCount
0x1800324d2  mov     rcx, r14; String1
0x1800324d5  lea     rdx, aApiMs; "api-ms-"
0x1800324dc  call    wcsncmp
0x1800324e1  test    eax, eax
0x1800324e3  jz      short loc_1800324FB
0x1800324e5  xor     r8d, r8d; dwFlags
0x1800324e8  xor     edx, edx; hFile
0x1800324ea  mov     rcx, r14; lpLibFileName
0x1800324ed  call    cs:__imp_LoadLibraryExW
0x1800324f3  mov     rbx, rax
0x1800324f6  test    rax, rax
0x1800324f9  jnz     short loc_180032535
0x1800324fb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800324ff  xchg    rax, rva qword_18007CBA0[r12+rsi*8]
0x180032507  add     rdi, 4
0x18003250b  cmp     rdi, rbp
0x18003250e  jnz     loc_180032486
0x180032514  xor     eax, eax
0x180032516  mov     rbx, [rsp+38h+arg_0]
0x18003251b  mov     rbp, [rsp+38h+arg_8]
0x180032520  mov     rsi, [rsp+38h+arg_10]
0x180032525  mov     rdi, [rsp+38h+arg_18]
0x18003252a  add     rsp, 20h
0x18003252e  pop     r15
0x180032530  pop     r14
0x180032532  pop     r12
0x180032534  retn
0x180032535  mov     rax, rbx
0x180032538  xchg    rax, rva qword_18007CBA0[r12+rsi*8]
0x180032540  test    rax, rax
0x180032543  jz      short loc_18003254E
0x180032545  mov     rcx, rbx; hLibModule
0x180032548  call    cs:__imp_FreeLibrary
0x18003254e  mov     rdx, r15; lpProcName
0x180032551  mov     rcx, rbx; hModule
0x180032554  call    cs:__imp_GetProcAddress
0x18003255a  jmp     short loc_180032516
```
