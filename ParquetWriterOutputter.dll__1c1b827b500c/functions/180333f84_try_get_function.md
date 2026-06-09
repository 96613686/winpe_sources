# try_get_function

- ea: `0x180333f84`
- end: `0x18033415a`
- name: `try_get_function`
- size: `470`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18033415c`
- `0x1803341a4`
- `0x1803341ec`
- `0x180334234`
- `0x180334288`

## callees

- `0x180333f84`
- `0x180349020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180334035`
- `KERNEL32!GetLastError` at `0x180334035`
- `KERNEL32!GetProcAddress` at `0x1803340dc`
- `KERNEL32!GetProcAddress` at `0x1803340dc`
- `KERNEL32!FreeLibrary` at `0x1803340b0`
- `KERNEL32!FreeLibrary` at `0x1803340b0`
- `KERNEL32!LoadLibraryExW` at `0x180334027`
- `KERNEL32!LoadLibraryExW` at `0x180334077`
- `KERNEL32!LoadLibraryExW` at `0x180334027`
- `KERNEL32!LoadLibraryExW` at `0x180334077`

## pseudocode

```c
FARPROC __fastcall try_get_function(unsigned int a1, const CHAR *a2, unsigned int *a3, unsigned int *a4)
{
  __int64 v4; // r15
  unsigned int *v6; // rbp
  uintptr_t v8; // r10
  __int64 v9; // rdx
  FARPROC result; // rax
  __int64 v11; // rsi
  HMODULE Library; // rbx
  const WCHAR *v13; // r14

  v4 = a1;
  v6 = a3;
  v8 = _security_cookie;
  v9 = __ROR8__(qword_1804C7200[a1] ^ _security_cookie, _security_cookie & 0x3F);
  if ( v9 == -1 )
    return 0;
  if ( v9 )
    return (FARPROC)v9;
  if ( a3 == a4 )
  {
LABEL_21:
    Library = 0;
    goto LABEL_22;
  }
  while ( 1 )
  {
    v11 = *v6;
    Library = (HMODULE)qword_1804C71E8[v11];
    if ( !Library )
      break;
    if ( Library != (HMODULE)-1LL )
      goto LABEL_25;
LABEL_19:
    if ( ++v6 == a4 )
    {
      v8 = _security_cookie;
      goto LABEL_21;
    }
  }
  v13 = off_1803FB150[v11];
  Library = LoadLibraryExW(v13, 0, 0x800u);
  if ( !Library )
  {
    if ( GetLastError() != 87 || !wcsncmp(v13, L"api-ms-", 7u) || !wcsncmp(v13, L"ext-ms-", 7u) )
      Library = 0;
    else
      Library = LoadLibraryExW(v13, 0, 0);
  }
  if ( !Library )
  {
    _InterlockedExchange64(&qword_1804C71E8[v11], -1);
    goto LABEL_19;
  }
  if ( _InterlockedExchange64(&qword_1804C71E8[v11], (__int64)Library) )
    FreeLibrary(Library);
LABEL_25:
  v8 = _security_cookie;
LABEL_22:
  if ( Library )
  {
    result = GetProcAddress(Library, a2);
    if ( result )
    {
      _InterlockedExchange64(
        &qword_1804C7200[v4],
        _security_cookie ^ __ROR8__(result, 64 - ((unsigned __int8)_security_cookie & 0x3Fu)));
      return result;
    }
    v8 = _security_cookie;
  }
  _InterlockedExchange64(&qword_1804C7200[v4], v8 ^ __ROR8__(-1, 64 - ((unsigned __int8)v8 & 0x3Fu)));
  return 0;
}

```

## disassembly

```asm
0x180333f84  mov     [rsp+arg_0], rbx
0x180333f89  mov     [rsp+arg_8], rbp
0x180333f8e  mov     [rsp+arg_10], rsi
0x180333f93  push    rdi
0x180333f94  push    r12
0x180333f96  push    r13
0x180333f98  push    r14
0x180333f9a  push    r15
0x180333f9c  sub     rsp, 20h
0x180333fa0  mov     r15d, ecx
0x180333fa3  lea     r14, cs:180000000h
0x180333faa  mov     r12, r9
0x180333fad  mov     rbp, r8
0x180333fb0  mov     r13, rdx
0x180333fb3  mov     rcx, rva qword_1804C7200[r14+r15*8]
0x180333fbb  mov     r10, cs:__security_cookie
0x180333fc2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180333fc6  mov     eax, r10d
0x180333fc9  mov     rdx, r10
0x180333fcc  xor     rdx, rcx
0x180333fcf  and     eax, 3Fh
0x180333fd2  mov     cl, al
0x180333fd4  ror     rdx, cl
0x180333fd7  cmp     rdx, rdi
0x180333fda  jz      loc_18033413B
0x180333fe0  test    rdx, rdx
0x180333fe3  jz      short loc_180333FED
0x180333fe5  mov     rax, rdx
0x180333fe8  jmp     loc_18033413D
0x180333fed  cmp     r8, r12
0x180333ff0  jz      loc_1803340CF
0x180333ff6  mov     esi, [rbp+0]
0x180333ff9  mov     rbx, rva qword_1804C71E8[r14+rsi*8]
0x180334001  test    rbx, rbx
0x180334004  jz      short loc_180334014
0x180334006  cmp     rbx, rdi
0x180334009  jz      loc_1803340BB
0x18033400f  jmp     loc_1803340B6
0x180334014  mov     r14, ds:rva off_1803FB150[r14+rsi*8]
0x18033401c  xor     edx, edx; hFile
0x18033401e  mov     rcx, r14; lpLibFileName
0x180334021  mov     r8d, 800h; dwFlags
0x180334027  call    cs:__imp_LoadLibraryExW
0x18033402d  mov     rbx, rax
0x180334030  test    rax, rax
0x180334033  jnz     short loc_180334084
0x180334035  call    cs:__imp_GetLastError
0x18033403b  cmp     eax, 57h ; 'W'
0x18033403e  jnz     short loc_180334082
0x180334040  lea     ebx, [rax-50h]
0x180334043  mov     rcx, r14; String1
0x180334046  mov     r8d, ebx; MaxCount
0x180334049  lea     rdx, aApiMs
0x180334050  call    wcsncmp
0x180334055  test    eax, eax
0x180334057  jz      short loc_180334082
0x180334059  mov     r8d, ebx; MaxCount
0x18033405c  lea     rdx, aExtMs
0x180334063  mov     rcx, r14; String1
0x180334066  call    wcsncmp
0x18033406b  test    eax, eax
0x18033406d  jz      short loc_180334082
0x18033406f  xor     r8d, r8d; dwFlags
0x180334072  xor     edx, edx; hFile
0x180334074  mov     rcx, r14; lpLibFileName
0x180334077  call    cs:__imp_LoadLibraryExW
0x18033407d  mov     rbx, rax
0x180334080  jmp     short loc_180334084
0x180334082  xor     ebx, ebx
0x180334084  lea     r14, cs:180000000h
0x18033408b  test    rbx, rbx
0x18033408e  jnz     short loc_18033409D
0x180334090  mov     rax, rdi
0x180334093  xchg    rax, rva qword_1804C71E8[r14+rsi*8]
0x18033409b  jmp     short loc_1803340BB
0x18033409d  mov     rax, rbx
0x1803340a0  xchg    rax, rva qword_1804C71E8[r14+rsi*8]
0x1803340a8  test    rax, rax
0x1803340ab  jz      short loc_1803340B6
0x1803340ad  mov     rcx, rbx; hLibModule
0x1803340b0  call    cs:__imp_FreeLibrary
0x1803340b6  test    rbx, rbx
0x1803340b9  jnz     short loc_180334110
0x1803340bb  add     rbp, 4
0x1803340bf  cmp     rbp, r12
0x1803340c2  jnz     loc_180333FF6
0x1803340c8  mov     r10, cs:__security_cookie
0x1803340cf  xor     ebx, ebx
0x1803340d1  test    rbx, rbx
0x1803340d4  jz      short loc_180334120
0x1803340d6  mov     rdx, r13; lpProcName
0x1803340d9  mov     rcx, rbx; hModule
0x1803340dc  call    cs:__imp_GetProcAddress
0x1803340e2  test    rax, rax
0x1803340e5  jz      short loc_180334119
0x1803340e7  mov     r8, cs:__security_cookie
0x1803340ee  mov     edx, 40h ; '@'
0x1803340f3  mov     ecx, r8d
0x1803340f6  and     ecx, 3Fh
0x1803340f9  sub     edx, ecx
0x1803340fb  mov     cl, dl
0x1803340fd  mov     rdx, rax
0x180334100  ror     rdx, cl
0x180334103  xor     rdx, r8
0x180334106  xchg    rdx, rva qword_1804C7200[r14+r15*8]
0x18033410e  jmp     short loc_18033413D
0x180334110  mov     r10, cs:__security_cookie
0x180334117  jmp     short loc_1803340D1
0x180334119  mov     r10, cs:__security_cookie
0x180334120  mov     eax, r10d
0x180334123  mov     ecx, 40h ; '@'
0x180334128  and     eax, 3Fh
0x18033412b  sub     ecx, eax
0x18033412d  ror     rdi, cl
0x180334130  xor     rdi, r10
0x180334133  xchg    rdi, rva qword_1804C7200[r14+r15*8]
0x18033413b  xor     eax, eax
0x18033413d  mov     rbx, [rsp+48h+arg_0]
0x180334142  mov     rbp, [rsp+48h+arg_8]
0x180334147  mov     rsi, [rsp+48h+arg_10]
0x18033414c  add     rsp, 20h
0x180334150  pop     r15
0x180334152  pop     r14
0x180334154  pop     r13
0x180334156  pop     r12
0x180334158  pop     rdi
0x180334159  retn
```
