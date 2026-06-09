# try_get_function_0

- ea: `0x180013a58`
- end: `0x180013c2e`
- name: `try_get_function_0`
- size: `470`
- prototype: `FARPROC __fastcall(unsigned int, const CHAR *, unsigned int *, unsigned int *)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013c30`
- `0x180013c80`
- `0x180013cbc`
- `0x180013d04`
- `0x180013d4c`
- `0x180013d94`
- `0x180013de8`
- `0x180013e4c`
- `0x180013f28`

## callees

- `0x18000fe10`
- `0x180013a58`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180013b84`
- `KERNEL32!FreeLibrary` at `0x180013b84`
- `KERNEL32!LoadLibraryExW` at `0x180013afb`
- `KERNEL32!LoadLibraryExW` at `0x180013b4b`
- `KERNEL32!LoadLibraryExW` at `0x180013afb`
- `KERNEL32!LoadLibraryExW` at `0x180013b4b`
- `KERNEL32!GetLastError` at `0x180013b09`
- `KERNEL32!GetLastError` at `0x180013b09`
- `KERNEL32!GetProcAddress` at `0x180013bb0`
- `KERNEL32!GetProcAddress` at `0x180013bb0`

## pseudocode

```c
FARPROC __fastcall try_get_function_0(unsigned int a1, const CHAR *a2, unsigned int *a3, unsigned int *a4)
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
  v9 = __ROR8__(qword_18003EC00[a1] ^ _security_cookie, _security_cookie & 0x3F);
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
    Library = (HMODULE)qword_18003EB60[v11];
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
  v13 = off_180028750[v11];
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
    _InterlockedExchange64(&qword_18003EB60[v11], -1);
    goto LABEL_19;
  }
  if ( _InterlockedExchange64(&qword_18003EB60[v11], (__int64)Library) )
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
        &qword_18003EC00[v4],
        _security_cookie ^ __ROR8__(result, 64 - ((unsigned __int8)_security_cookie & 0x3Fu)));
      return result;
    }
    v8 = _security_cookie;
  }
  _InterlockedExchange64(&qword_18003EC00[v4], v8 ^ __ROR8__(-1, 64 - ((unsigned __int8)v8 & 0x3Fu)));
  return 0;
}

```

## disassembly

```asm
0x180013a58  mov     [rsp+arg_0], rbx
0x180013a5d  mov     [rsp+arg_8], rbp
0x180013a62  mov     [rsp+arg_10], rsi
0x180013a67  push    rdi
0x180013a68  push    r12
0x180013a6a  push    r13
0x180013a6c  push    r14
0x180013a6e  push    r15
0x180013a70  sub     rsp, 20h
0x180013a74  mov     r15d, ecx
0x180013a77  lea     r14, cs:180000000h
0x180013a7e  mov     r12, r9
0x180013a81  mov     rbp, r8
0x180013a84  mov     r13, rdx
0x180013a87  mov     rcx, rva qword_18003EC00[r14+r15*8]
0x180013a8f  mov     r10, cs:__security_cookie
0x180013a96  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180013a9a  mov     eax, r10d
0x180013a9d  mov     rdx, r10
0x180013aa0  xor     rdx, rcx
0x180013aa3  and     eax, 3Fh
0x180013aa6  mov     cl, al
0x180013aa8  ror     rdx, cl
0x180013aab  cmp     rdx, rdi
0x180013aae  jz      loc_180013C0F
0x180013ab4  test    rdx, rdx
0x180013ab7  jz      short loc_180013AC1
0x180013ab9  mov     rax, rdx
0x180013abc  jmp     loc_180013C11
0x180013ac1  cmp     r8, r12
0x180013ac4  jz      loc_180013BA3
0x180013aca  mov     esi, [rbp+0]
0x180013acd  mov     rbx, rva qword_18003EB60[r14+rsi*8]
0x180013ad5  test    rbx, rbx
0x180013ad8  jz      short loc_180013AE8
0x180013ada  cmp     rbx, rdi
0x180013add  jz      loc_180013B8F
0x180013ae3  jmp     loc_180013B8A
0x180013ae8  mov     r14, ds:rva off_180028750[r14+rsi*8]; "api-ms-win-core-datetime-l1-1-1" ...
0x180013af0  xor     edx, edx; hFile
0x180013af2  mov     rcx, r14; lpLibFileName
0x180013af5  mov     r8d, 800h; dwFlags
0x180013afb  call    cs:__imp_LoadLibraryExW
0x180013b01  mov     rbx, rax
0x180013b04  test    rax, rax
0x180013b07  jnz     short loc_180013B58
0x180013b09  call    cs:__imp_GetLastError
0x180013b0f  cmp     eax, 57h ; 'W'
0x180013b12  jnz     short loc_180013B56
0x180013b14  lea     ebx, [rax-50h]
0x180013b17  mov     rcx, r14; String1
0x180013b1a  mov     r8d, ebx; MaxCount
0x180013b1d  lea     rdx, aApiMs; "api-ms-"
0x180013b24  call    wcsncmp
0x180013b29  test    eax, eax
0x180013b2b  jz      short loc_180013B56
0x180013b2d  mov     r8d, ebx; MaxCount
0x180013b30  lea     rdx, aExtMs; "ext-ms-"
0x180013b37  mov     rcx, r14; String1
0x180013b3a  call    wcsncmp
0x180013b3f  test    eax, eax
0x180013b41  jz      short loc_180013B56
0x180013b43  xor     r8d, r8d; dwFlags
0x180013b46  xor     edx, edx; hFile
0x180013b48  mov     rcx, r14; lpLibFileName
0x180013b4b  call    cs:__imp_LoadLibraryExW
0x180013b51  mov     rbx, rax
0x180013b54  jmp     short loc_180013B58
0x180013b56  xor     ebx, ebx
0x180013b58  lea     r14, cs:180000000h
0x180013b5f  test    rbx, rbx
0x180013b62  jnz     short loc_180013B71
0x180013b64  mov     rax, rdi
0x180013b67  xchg    rax, rva qword_18003EB60[r14+rsi*8]
0x180013b6f  jmp     short loc_180013B8F
0x180013b71  mov     rax, rbx
0x180013b74  xchg    rax, rva qword_18003EB60[r14+rsi*8]
0x180013b7c  test    rax, rax
0x180013b7f  jz      short loc_180013B8A
0x180013b81  mov     rcx, rbx; hLibModule
0x180013b84  call    cs:__imp_FreeLibrary
0x180013b8a  test    rbx, rbx
0x180013b8d  jnz     short loc_180013BE4
0x180013b8f  add     rbp, 4
0x180013b93  cmp     rbp, r12
0x180013b96  jnz     loc_180013ACA
0x180013b9c  mov     r10, cs:__security_cookie
0x180013ba3  xor     ebx, ebx
0x180013ba5  test    rbx, rbx
0x180013ba8  jz      short loc_180013BF4
0x180013baa  mov     rdx, r13; lpProcName
0x180013bad  mov     rcx, rbx; hModule
0x180013bb0  call    cs:__imp_GetProcAddress
0x180013bb6  test    rax, rax
0x180013bb9  jz      short loc_180013BED
0x180013bbb  mov     r8, cs:__security_cookie
0x180013bc2  mov     edx, 40h ; '@'
0x180013bc7  mov     ecx, r8d
0x180013bca  and     ecx, 3Fh
0x180013bcd  sub     edx, ecx
0x180013bcf  mov     cl, dl
0x180013bd1  mov     rdx, rax
0x180013bd4  ror     rdx, cl
0x180013bd7  xor     rdx, r8
0x180013bda  xchg    rdx, rva qword_18003EC00[r14+r15*8]
0x180013be2  jmp     short loc_180013C11
0x180013be4  mov     r10, cs:__security_cookie
0x180013beb  jmp     short loc_180013BA5
0x180013bed  mov     r10, cs:__security_cookie
0x180013bf4  mov     eax, r10d
0x180013bf7  mov     ecx, 40h ; '@'
0x180013bfc  and     eax, 3Fh
0x180013bff  sub     ecx, eax
0x180013c01  ror     rdi, cl
0x180013c04  xor     rdi, r10
0x180013c07  xchg    rdi, rva qword_18003EC00[r14+r15*8]
0x180013c0f  xor     eax, eax
0x180013c11  mov     rbx, [rsp+48h+arg_0]
0x180013c16  mov     rbp, [rsp+48h+arg_8]
0x180013c1b  mov     rsi, [rsp+48h+arg_10]
0x180013c20  add     rsp, 20h
0x180013c24  pop     r15
0x180013c26  pop     r14
0x180013c28  pop     r13
0x180013c2a  pop     r12
0x180013c2c  pop     rdi
0x180013c2d  retn
```
