# try_get_function_slow

- ea: `0x140015d00`
- end: `0x140015eb2`
- name: `try_get_function_slow`
- size: `434`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140015cc8`
- `0x140015eb4`
- `0x140016008`
- `0x1400160fc`
- `0x140016190`

## callees

- `0x1400113c0`
- `0x140013658`
- `0x140015d00`
- `0x140016848`
- `0x1400168a8`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x140015d6d`
- `KERNEL32!LoadLibraryExW` at `0x140015dc1`
- `KERNEL32!LoadLibraryExW` at `0x140015d6d`
- `KERNEL32!LoadLibraryExW` at `0x140015dc1`
- `KERNEL32!VirtualProtect` at `0x140015e1d`
- `KERNEL32!VirtualProtect` at `0x140015e4e`
- `KERNEL32!VirtualProtect` at `0x140015e1d`
- `KERNEL32!VirtualProtect` at `0x140015e4e`
- `KERNEL32!GetProcAddress` at `0x140015e9e`
- `KERNEL32!GetProcAddress` at `0x140015e9e`
- `KERNEL32!FreeLibrary` at `0x140015e92`
- `KERNEL32!FreeLibrary` at `0x140015e92`
- `KERNEL32!GetLastError` at `0x140015d7f`
- `KERNEL32!GetLastError` at `0x140015d7f`

## pseudocode

```c
FARPROC __fastcall try_get_function_slow(unsigned int a1, const CHAR *a2, unsigned int *a3, unsigned int *a4)
{
  __int64 v4; // r12
  unsigned int *v6; // rsi
  __int64 v8; // rdi
  HMODULE Library; // rbx
  const WCHAR *v10; // rbp
  FARPROC ProcAddress; // rbx
  __int64 v12; // rax
  DWORD flOldProtect; // [rsp+60h] [rbp+18h] BYREF

  v4 = a1;
  v6 = a3;
  if ( a3 == a4 )
  {
LABEL_12:
    ProcAddress = 0;
    goto LABEL_13;
  }
  while ( 1 )
  {
    v8 = *v6;
    Library = (HMODULE)qword_14003CFC0[v8];
    if ( !Library )
      break;
    if ( Library != (HMODULE)-1LL )
      goto LABEL_20;
LABEL_11:
    if ( ++v6 == a4 )
      goto LABEL_12;
  }
  v10 = off_14002B0A0[v8];
  Library = LoadLibraryExW(v10, 0, 0x800u);
  if ( !Library
    && (GetLastError() != 87
     || !wcsncmp(v10, L"api-ms-", 7u)
     || !wcsncmp(v10, L"ext-ms-", 7u)
     || (Library = LoadLibraryExW(v10, 0, 0)) == 0) )
  {
    _InterlockedExchange64(&qword_14003CFC0[v8], -1);
    goto LABEL_11;
  }
  if ( _InterlockedExchange64(&qword_14003CFC0[v8], (__int64)Library) )
    FreeLibrary(Library);
LABEL_20:
  ProcAddress = GetProcAddress(Library, a2);
LABEL_13:
  _acrt_lock(14);
  flOldProtect = 0;
  if ( !VirtualProtect(qword_140041000, 0x100u, 4u, &flOldProtect) )
    goto LABEL_21;
  v12 = (__int64)ProcAddress;
  if ( !ProcAddress )
    v12 = -1;
  _InterlockedExchange64(&qword_140041000[v4], v12);
  if ( !VirtualProtect(qword_140041000, 0x100u, 2u, &flOldProtect) )
LABEL_21:
    abort();
  _acrt_unlock(14);
  return ProcAddress;
}

```

## disassembly

```asm
0x140015d00  mov     [rsp+arg_0], rbx
0x140015d05  mov     [rsp+arg_8], rbp
0x140015d0a  mov     [rsp+arg_18], rsi
0x140015d0f  push    rdi
0x140015d10  push    r12
0x140015d12  push    r13
0x140015d14  push    r14
0x140015d16  push    r15
0x140015d18  sub     rsp, 20h
0x140015d1c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140015d20  mov     r12d, ecx
0x140015d23  mov     r14, r9
0x140015d26  mov     rsi, r8
0x140015d29  mov     r15, rdx
0x140015d2c  cmp     r8, r9
0x140015d2f  jz      loc_140015DF0
0x140015d35  lea     r13, cs:140000000h
0x140015d3c  mov     edi, [rsi]
0x140015d3e  mov     rbx, rva qword_14003CFC0[r13+rdi*8]
0x140015d46  nop
0x140015d47  test    rbx, rbx
0x140015d4a  jz      short loc_140015D5A
0x140015d4c  cmp     rbx, rax
0x140015d4f  jnz     loc_140015E98
0x140015d55  jmp     loc_140015DE3
0x140015d5a  mov     rbp, ds:rva off_14002B0A0[r13+rdi*8]; "api-ms-win-core-datetime-l1-1-1" ...
0x140015d62  xor     edx, edx; hFile
0x140015d64  mov     rcx, rbp; lpLibFileName
0x140015d67  mov     r8d, 800h; dwFlags
0x140015d6d  call    cs:__imp_LoadLibraryExW
0x140015d73  mov     rbx, rax
0x140015d76  test    rax, rax
0x140015d79  jnz     loc_140015E7F
0x140015d7f  call    cs:__imp_GetLastError
0x140015d85  cmp     eax, 57h ; 'W'
0x140015d88  jnz     short loc_140015DD3
0x140015d8a  lea     ebx, [rax-50h]
0x140015d8d  mov     rcx, rbp; String1
0x140015d90  mov     r8d, ebx; MaxCount
0x140015d93  lea     rdx, aApiMs; "api-ms-"
0x140015d9a  call    wcsncmp
0x140015d9f  test    eax, eax
0x140015da1  jz      short loc_140015DD3
0x140015da3  mov     r8d, ebx; MaxCount
0x140015da6  lea     rdx, aExtMs; "ext-ms-"
0x140015dad  mov     rcx, rbp; String1
0x140015db0  call    wcsncmp
0x140015db5  test    eax, eax
0x140015db7  jz      short loc_140015DD3
0x140015db9  xor     r8d, r8d; dwFlags
0x140015dbc  xor     edx, edx; hFile
0x140015dbe  mov     rcx, rbp; lpLibFileName
0x140015dc1  call    cs:__imp_LoadLibraryExW
0x140015dc7  mov     rbx, rax
0x140015dca  test    rax, rax
0x140015dcd  jnz     loc_140015E7F
0x140015dd3  or      rax, 0FFFFFFFFFFFFFFFFh
0x140015dd7  xchg    rax, rva qword_14003CFC0[r13+rdi*8]
0x140015ddf  or      rax, 0FFFFFFFFFFFFFFFFh
0x140015de3  add     rsi, 4
0x140015de7  cmp     rsi, r14
0x140015dea  jnz     loc_140015D3C
0x140015df0  xor     ebx, ebx
0x140015df2  mov     edi, 0Eh
0x140015df7  mov     ecx, edi
0x140015df9  call    __acrt_lock
0x140015dfe  and     [rsp+48h+flOldProtect], 0
0x140015e03  lea     rsi, qword_140041000
0x140015e0a  mov     ebp, 100h
0x140015e0f  lea     r9, [rsp+48h+flOldProtect]; lpflOldProtect
0x140015e14  mov     edx, ebp; dwSize
0x140015e16  lea     r8d, [rdi-0Ah]; flNewProtect
0x140015e1a  mov     rcx, rsi; lpAddress
0x140015e1d  call    cs:__imp_VirtualProtect
0x140015e23  test    eax, eax
0x140015e25  jz      loc_140015EAC
0x140015e2b  test    rbx, rbx
0x140015e2e  mov     rax, rbx
0x140015e31  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140015e38  cmovz   rax, rcx
0x140015e3c  xchg    rax, [rsi+r12*8]
0x140015e40  lea     r9, [rsp+48h+flOldProtect]; lpflOldProtect
0x140015e45  mov     edx, ebp; dwSize
0x140015e47  lea     r8d, [rdi-0Ch]; flNewProtect
0x140015e4b  mov     rcx, rsi; lpAddress
0x140015e4e  call    cs:__imp_VirtualProtect
0x140015e54  test    eax, eax
0x140015e56  jz      short loc_140015EAC
0x140015e58  mov     ecx, edi
0x140015e5a  call    __acrt_unlock
0x140015e5f  mov     rbp, [rsp+48h+arg_8]
0x140015e64  mov     rax, rbx
0x140015e67  mov     rbx, [rsp+48h+arg_0]
0x140015e6c  mov     rsi, [rsp+48h+arg_18]
0x140015e71  add     rsp, 20h
0x140015e75  pop     r15
0x140015e77  pop     r14
0x140015e79  pop     r13
0x140015e7b  pop     r12
0x140015e7d  pop     rdi
0x140015e7e  retn
0x140015e7f  mov     rax, rbx
0x140015e82  xchg    rax, rva qword_14003CFC0[r13+rdi*8]
0x140015e8a  test    rax, rax
0x140015e8d  jz      short loc_140015E98
0x140015e8f  mov     rcx, rbx; hLibModule
0x140015e92  call    cs:__imp_FreeLibrary
0x140015e98  mov     rdx, r15; lpProcName
0x140015e9b  mov     rcx, rbx; hModule
0x140015e9e  call    cs:__imp_GetProcAddress
0x140015ea4  mov     rbx, rax
0x140015ea7  jmp     loc_140015DF2
0x140015eac  call    abort
```
