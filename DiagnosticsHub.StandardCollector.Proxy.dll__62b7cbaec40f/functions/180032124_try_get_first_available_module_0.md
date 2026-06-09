# try_get_first_available_module_0

- ea: `0x180032124`
- end: `0x180032219`
- name: `try_get_first_available_module_0`
- size: `245`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800145d0`
- `0x180032124`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180032181`
- `KERNEL32!LoadLibraryExW` at `0x1800321b9`
- `KERNEL32!LoadLibraryExW` at `0x180032181`
- `KERNEL32!LoadLibraryExW` at `0x1800321b9`
- `KERNEL32!FreeLibrary` at `0x18003220e`
- `KERNEL32!FreeLibrary` at `0x18003220e`
- `KERNEL32!GetLastError` at `0x18003218f`
- `KERNEL32!GetLastError` at `0x18003218f`

## pseudocode

```c
HMODULE __fastcall try_get_first_available_module_0(unsigned int *a1, unsigned int *a2)
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
    Library = (HMODULE)qword_18007CBA0[v4];
    if ( !Library )
      break;
    if ( Library != (HMODULE)-1LL )
      return Library;
LABEL_10:
    if ( ++v3 == a2 )
      return 0;
  }
  v6 = off_18006E728[v4];
  Library = LoadLibraryExW(v6, 0, 0x800u);
  if ( !Library && (GetLastError() != 87 || !wcsncmp(v6, L"api-ms-", 7u) || (Library = LoadLibraryExW(v6, 0, 0)) == 0) )
  {
    _InterlockedExchange64(&qword_18007CBA0[v4], -1);
    goto LABEL_10;
  }
  if ( _InterlockedExchange64(&qword_18007CBA0[v4], (__int64)Library) )
    FreeLibrary(Library);
  return Library;
}

```

## disassembly

```asm
0x180032124  mov     [rsp+arg_0], rbx
0x180032129  mov     [rsp+arg_8], rbp
0x18003212e  mov     [rsp+arg_10], rsi
0x180032133  push    rdi
0x180032134  push    r14
0x180032136  push    r15
0x180032138  sub     rsp, 20h
0x18003213c  mov     rbp, rdx
0x18003213f  mov     rdi, rcx
0x180032142  cmp     rcx, rdx
0x180032145  jz      loc_1800321E0
0x18003214b  lea     r15, cs:180000000h
0x180032152  mov     esi, [rdi]
0x180032154  mov     rbx, rva qword_18007CBA0[r15+rsi*8]
0x18003215c  nop
0x18003215d  test    rbx, rbx
0x180032160  jz      short loc_18003216E
0x180032162  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180032166  jnz     loc_180032214
0x18003216c  jmp     short loc_1800321D3
0x18003216e  mov     r14, ds:rva off_18006E728[r15+rsi*8]; "api-ms-win-core-fibers-l1-1-1" ...
0x180032176  xor     edx, edx; hFile
0x180032178  mov     rcx, r14; lpLibFileName
0x18003217b  mov     r8d, 800h; dwFlags
0x180032181  call    cs:__imp_LoadLibraryExW
0x180032187  mov     rbx, rax
0x18003218a  test    rax, rax
0x18003218d  jnz     short loc_1800321FB
0x18003218f  call    cs:__imp_GetLastError
0x180032195  cmp     eax, 57h ; 'W'
0x180032198  jnz     short loc_1800321C7
0x18003219a  lea     r8d, [rbx+7]; MaxCount
0x18003219e  mov     rcx, r14; String1
0x1800321a1  lea     rdx, aApiMs; "api-ms-"
0x1800321a8  call    wcsncmp
0x1800321ad  test    eax, eax
0x1800321af  jz      short loc_1800321C7
0x1800321b1  xor     r8d, r8d; dwFlags
0x1800321b4  xor     edx, edx; hFile
0x1800321b6  mov     rcx, r14; lpLibFileName
0x1800321b9  call    cs:__imp_LoadLibraryExW
0x1800321bf  mov     rbx, rax
0x1800321c2  test    rax, rax
0x1800321c5  jnz     short loc_1800321FB
0x1800321c7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800321cb  xchg    rax, rva qword_18007CBA0[r15+rsi*8]
0x1800321d3  add     rdi, 4
0x1800321d7  cmp     rdi, rbp
0x1800321da  jnz     loc_180032152
0x1800321e0  xor     eax, eax
0x1800321e2  mov     rbx, [rsp+38h+arg_0]
0x1800321e7  mov     rbp, [rsp+38h+arg_8]
0x1800321ec  mov     rsi, [rsp+38h+arg_10]
0x1800321f1  add     rsp, 20h
0x1800321f5  pop     r15
0x1800321f7  pop     r14
0x1800321f9  pop     rdi
0x1800321fa  retn
0x1800321fb  mov     rcx, rbx
0x1800321fe  xchg    rcx, rva qword_18007CBA0[r15+rsi*8]
0x180032206  test    rcx, rcx
0x180032209  jz      short loc_180032214
0x18003220b  mov     rcx, rbx; hLibModule
0x18003220e  call    cs:__imp_FreeLibrary
0x180032214  mov     rax, rbx
0x180032217  jmp     short loc_1800321E2
```
