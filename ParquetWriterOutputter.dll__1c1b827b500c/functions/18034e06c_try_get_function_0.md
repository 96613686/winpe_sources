# try_get_function_0

- ea: `0x18034e06c`
- end: `0x18034e20c`
- name: `try_get_function_0`
- size: `416`
- prototype: ``
- caller_count: `23`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18034e20c`
- `0x18034e2fc`
- `0x18034e3a4`
- `0x18034e3fc`
- `0x18034e454`
- `0x18034e4ac`
- `0x18034e514`
- `0x18034e5e0`
- `0x18034e678`
- `0x18034e734`
- `0x18034e7a8`
- `0x18034e820`
- `0x18034e888`
- `0x18034e914`
- `0x18034ea04`
- `0x18034ea6c`
- `0x18034eaf4`
- `0x18034eb40`
- `0x18034eb80`
- `0x18034ebdc`
- `0x18034ec0c`
- `0x18034ecd8`
- `0x18034edac`

## callees

- `0x18034e06c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18034e116`
- `KERNEL32!GetLastError` at `0x18034e116`
- `KERNEL32!GetProcAddress` at `0x18034e18e`
- `KERNEL32!GetProcAddress` at `0x18034e18e`
- `KERNEL32!FreeLibrary` at `0x18034e162`
- `KERNEL32!FreeLibrary` at `0x18034e162`
- `KERNEL32!LoadLibraryExW` at `0x18034e108`
- `KERNEL32!LoadLibraryExW` at `0x18034e129`
- `KERNEL32!LoadLibraryExW` at `0x18034e108`
- `KERNEL32!LoadLibraryExW` at `0x18034e129`

## pseudocode

```c
FARPROC __fastcall try_get_function_0(unsigned int a1, const CHAR *a2, unsigned int *a3, unsigned int *a4)
{
  __int64 v4; // r14
  unsigned int *v6; // rbp
  uintptr_t v8; // r10
  __int64 v9; // rdx
  FARPROC result; // rax
  __int64 v11; // rsi
  HMODULE Library; // rbx
  const WCHAR *v13; // r15

  v4 = a1;
  v6 = a3;
  v8 = _security_cookie;
  v9 = __ROR8__(qword_1804C7AD0[a1] ^ _security_cookie, _security_cookie & 0x3F);
  if ( v9 == -1 )
    return 0;
  if ( v9 )
    return (FARPROC)v9;
  if ( a3 == a4 )
  {
LABEL_19:
    Library = 0;
    goto LABEL_20;
  }
  while ( 1 )
  {
    v11 = *v6;
    Library = (HMODULE)qword_1804C7A30[v11];
    if ( !Library )
      break;
    if ( Library != (HMODULE)-1LL )
      goto LABEL_23;
LABEL_17:
    if ( ++v6 == a4 )
    {
      v8 = _security_cookie;
      goto LABEL_19;
    }
  }
  v13 = off_1804029E0[v11];
  Library = LoadLibraryExW(v13, 0, 0x800u);
  if ( !Library )
  {
    if ( GetLastError() == 87 )
      Library = LoadLibraryExW(v13, 0, 0);
    else
      Library = 0;
  }
  if ( !Library )
  {
    _InterlockedExchange64(&qword_1804C7A30[v11], -1);
    goto LABEL_17;
  }
  if ( _InterlockedExchange64(&qword_1804C7A30[v11], (__int64)Library) )
    FreeLibrary(Library);
LABEL_23:
  v8 = _security_cookie;
LABEL_20:
  if ( Library )
  {
    result = GetProcAddress(Library, a2);
    if ( result )
    {
      _InterlockedExchange64(
        &qword_1804C7AD0[v4],
        _security_cookie ^ __ROR8__(result, 64 - ((unsigned __int8)_security_cookie & 0x3Fu)));
      return result;
    }
    v8 = _security_cookie;
  }
  _InterlockedExchange64(&qword_1804C7AD0[v4], v8 ^ __ROR8__(-1, 64 - ((unsigned __int8)v8 & 0x3Fu)));
  return 0;
}

```

## disassembly

```asm
0x18034e06c  mov     [rsp+arg_0], rbx
0x18034e071  mov     [rsp+arg_8], rbp
0x18034e076  mov     [rsp+arg_10], rsi
0x18034e07b  push    rdi
0x18034e07c  push    r12
0x18034e07e  push    r13
0x18034e080  push    r14
0x18034e082  push    r15
0x18034e084  sub     rsp, 20h
0x18034e088  mov     r14d, ecx
0x18034e08b  lea     r15, cs:180000000h
0x18034e092  mov     r12, r9
0x18034e095  mov     rbp, r8
0x18034e098  mov     r13, rdx
0x18034e09b  mov     rcx, rva qword_1804C7AD0[r15+r14*8]
0x18034e0a3  mov     r10, cs:__security_cookie
0x18034e0aa  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18034e0ae  mov     eax, r10d
0x18034e0b1  mov     rdx, r10
0x18034e0b4  xor     rdx, rcx
0x18034e0b7  and     eax, 3Fh
0x18034e0ba  mov     cl, al
0x18034e0bc  ror     rdx, cl
0x18034e0bf  cmp     rdx, rdi
0x18034e0c2  jz      loc_18034E1ED
0x18034e0c8  test    rdx, rdx
0x18034e0cb  jz      short loc_18034E0D5
0x18034e0cd  mov     rax, rdx
0x18034e0d0  jmp     loc_18034E1EF
0x18034e0d5  cmp     r8, r9
0x18034e0d8  jz      loc_18034E181
0x18034e0de  mov     esi, [rbp+0]
0x18034e0e1  mov     rbx, rva qword_1804C7A30[r15+rsi*8]
0x18034e0e9  test    rbx, rbx
0x18034e0ec  jz      short loc_18034E0F5
0x18034e0ee  cmp     rbx, rdi
0x18034e0f1  jz      short loc_18034E16D
0x18034e0f3  jmp     short loc_18034E168
0x18034e0f5  mov     r15, ds:rva off_1804029E0[r15+rsi*8]
0x18034e0fd  xor     edx, edx; hFile
0x18034e0ff  mov     rcx, r15; lpLibFileName
0x18034e102  mov     r8d, 800h; dwFlags
0x18034e108  call    cs:__imp_LoadLibraryExW
0x18034e10e  mov     rbx, rax
0x18034e111  test    rax, rax
0x18034e114  jnz     short loc_18034E136
0x18034e116  call    cs:__imp_GetLastError
0x18034e11c  cmp     eax, 57h ; 'W'
0x18034e11f  jnz     short loc_18034E134
0x18034e121  xor     r8d, r8d; dwFlags
0x18034e124  xor     edx, edx; hFile
0x18034e126  mov     rcx, r15; lpLibFileName
0x18034e129  call    cs:__imp_LoadLibraryExW
0x18034e12f  mov     rbx, rax
0x18034e132  jmp     short loc_18034E136
0x18034e134  xor     ebx, ebx
0x18034e136  lea     r15, cs:180000000h
0x18034e13d  test    rbx, rbx
0x18034e140  jnz     short loc_18034E14F
0x18034e142  mov     rax, rdi
0x18034e145  xchg    rax, rva qword_1804C7A30[r15+rsi*8]
0x18034e14d  jmp     short loc_18034E16D
0x18034e14f  mov     rax, rbx
0x18034e152  xchg    rax, rva qword_1804C7A30[r15+rsi*8]
0x18034e15a  test    rax, rax
0x18034e15d  jz      short loc_18034E168
0x18034e15f  mov     rcx, rbx; hLibModule
0x18034e162  call    cs:__imp_FreeLibrary
0x18034e168  test    rbx, rbx
0x18034e16b  jnz     short loc_18034E1C2
0x18034e16d  add     rbp, 4
0x18034e171  cmp     rbp, r12
0x18034e174  jnz     loc_18034E0DE
0x18034e17a  mov     r10, cs:__security_cookie
0x18034e181  xor     ebx, ebx
0x18034e183  test    rbx, rbx
0x18034e186  jz      short loc_18034E1D2
0x18034e188  mov     rdx, r13; lpProcName
0x18034e18b  mov     rcx, rbx; hModule
0x18034e18e  call    cs:__imp_GetProcAddress
0x18034e194  test    rax, rax
0x18034e197  jz      short loc_18034E1CB
0x18034e199  mov     r8, cs:__security_cookie
0x18034e1a0  mov     edx, 40h ; '@'
0x18034e1a5  mov     ecx, r8d
0x18034e1a8  and     ecx, 3Fh
0x18034e1ab  sub     edx, ecx
0x18034e1ad  mov     cl, dl
0x18034e1af  mov     rdx, rax
0x18034e1b2  ror     rdx, cl
0x18034e1b5  xor     rdx, r8
0x18034e1b8  xchg    rdx, rva qword_1804C7AD0[r15+r14*8]
0x18034e1c0  jmp     short loc_18034E1EF
0x18034e1c2  mov     r10, cs:__security_cookie
0x18034e1c9  jmp     short loc_18034E183
0x18034e1cb  mov     r10, cs:__security_cookie
0x18034e1d2  mov     eax, r10d
0x18034e1d5  mov     ecx, 40h ; '@'
0x18034e1da  and     eax, 3Fh
0x18034e1dd  sub     ecx, eax
0x18034e1df  ror     rdi, cl
0x18034e1e2  xor     rdi, r10
0x18034e1e5  xchg    rdi, rva qword_1804C7AD0[r15+r14*8]
0x18034e1ed  xor     eax, eax
0x18034e1ef  mov     rbx, [rsp+48h+arg_0]
0x18034e1f4  mov     rbp, [rsp+48h+arg_8]
0x18034e1f9  mov     rsi, [rsp+48h+arg_10]
0x18034e1fe  add     rsp, 20h
0x18034e202  pop     r15
0x18034e204  pop     r14
0x18034e206  pop     r13
0x18034e208  pop     r12
0x18034e20a  pop     rdi
0x18034e20b  retn
```
