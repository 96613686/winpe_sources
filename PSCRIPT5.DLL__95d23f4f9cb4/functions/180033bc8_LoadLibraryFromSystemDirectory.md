# LoadLibraryFromSystemDirectory

- ea: `0x180033bc8`
- end: `0x180033d2a`
- name: `LoadLibraryFromSystemDirectory`
- size: `354`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180009c38`
- `0x180019cb0`
- `0x180033d30`
- `0x180035c34`

## callees

- `0x180001ee0`
- `0x1800028d8`
- `0x18001fe90`
- `0x180033bc8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180033c24`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180033c24`
- `KERNEL32!LoadLibraryW` at `0x180033ccb`
- `KERNEL32!LoadLibraryW` at `0x180033ccb`
- `KERNEL32!GetSystemDirectoryW` at `0x180033c8a`
- `KERNEL32!GetSystemDirectoryW` at `0x180033c8a`
- `KERNEL32!GetLastError` at `0x180033cd6`
- `KERNEL32!GetLastError` at `0x180033cd6`

## pseudocode

```c
__int64 __fastcall LoadLibraryFromSystemDirectory(STRSAFE_LPCWSTR pszSrc, HMODULE *a2)
{
  wchar_t *v4; // rax
  STRSAFE_LPCWSTR v5; // rax
  __int64 v6; // rdx
  HRESULT v7; // ebx
  __int64 v8; // rbp
  __int64 SystemDirectoryW; // rcx
  HMODULE LibraryW; // rax
  signed int LastError; // eax
  wchar_t Buffer[264]; // [rsp+20h] [rbp-248h] BYREF

  memset_0(Buffer, 0, 0x208u);
  if ( !pszSrc || !a2 )
  {
    *a2 = 0;
    return (unsigned int)-2147024809;
  }
  v4 = wcsstr(pszSrc, L"\\");
  *a2 = 0;
  if ( v4 )
    return (unsigned int)-2147024809;
  v5 = pszSrc;
  v6 = 259;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v6;
  }
  while ( v6 );
  v7 = v6 == 0 ? 0x80070057 : 0;
  v8 = (259 - v6) & -(__int64)(v6 != 0);
  if ( v6 )
  {
    SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
    if ( (unsigned __int64)(SystemDirectoryW - 1) > 0x101 || (unsigned __int64)(SystemDirectoryW + v8) >= 0x103 )
    {
      return (unsigned int)-2147467259;
    }
    else
    {
      Buffer[SystemDirectoryW] = 92;
      v7 = StringCchCatW(Buffer, 0x104u, pszSrc);
      if ( v7 >= 0 )
      {
        LibraryW = LoadLibraryW(Buffer);
        if ( LibraryW )
        {
          *a2 = LibraryW;
        }
        else
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError > 0 )
            return (unsigned __int16)LastError | 0x80070000;
        }
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180033bc8  mov     [rsp+arg_10], rbx
0x180033bcd  push    rbp
0x180033bce  push    rsi
0x180033bcf  push    rdi
0x180033bd0  push    r14
0x180033bd2  push    r15
0x180033bd4  sub     rsp, 240h
0x180033bdb  mov     rax, cs:__security_cookie
0x180033be2  xor     rax, rsp
0x180033be5  mov     [rsp+268h+var_38], rax
0x180033bed  mov     rdi, rdx
0x180033bf0  mov     rsi, rcx
0x180033bf3  xor     edx, edx; Val
0x180033bf5  lea     rcx, [rsp+268h+Buffer]; void *
0x180033bfa  mov     r8d, 208h; Size
0x180033c00  call    memset_0
0x180033c05  xor     r14d, r14d
0x180033c08  test    rsi, rsi
0x180033c0b  jz      loc_180033CF9
0x180033c11  test    rdi, rdi
0x180033c14  jz      loc_180033CF9
0x180033c1a  lea     rdx, SubBlock; "\\"
0x180033c21  mov     rcx, rsi; Str
0x180033c24  call    cs:__imp_wcsstr
0x180033c2a  mov     [rdi], r14
0x180033c2d  test    rax, rax
0x180033c30  jnz     loc_180033CFC
0x180033c36  mov     r15d, 103h
0x180033c3c  mov     rax, rsi
0x180033c3f  mov     edx, r15d
0x180033c42  cmp     [rax], r14w
0x180033c46  jz      short loc_180033C52
0x180033c48  add     rax, 2
0x180033c4c  sub     rdx, 1
0x180033c50  jnz     short loc_180033C42
0x180033c52  mov     rax, rdx
0x180033c55  mov     ebx, 80070057h
0x180033c5a  neg     rax
0x180033c5d  mov     rax, rdx
0x180033c60  sbb     ecx, ecx
0x180033c62  not     ecx
0x180033c64  and     ebx, ecx
0x180033c66  mov     rcx, r15
0x180033c69  sub     rcx, rdx
0x180033c6c  neg     rax
0x180033c6f  sbb     rbp, rbp
0x180033c72  and     rbp, rcx
0x180033c75  test    rdx, rdx
0x180033c78  jz      loc_180033D01
0x180033c7e  mov     ebx, 104h
0x180033c83  lea     rcx, [rsp+268h+Buffer]; lpBuffer
0x180033c88  mov     edx, ebx; uSize
0x180033c8a  call    cs:__imp_GetSystemDirectoryW
0x180033c90  mov     ecx, eax
0x180033c92  lea     rax, [rcx-1]
0x180033c96  cmp     rax, 101h
0x180033c9c  ja      short loc_180033CF2
0x180033c9e  lea     rax, [rcx+rbp]
0x180033ca2  cmp     rax, r15
0x180033ca5  jnb     short loc_180033CF2
0x180033ca7  mov     eax, 5Ch ; '\'
0x180033cac  mov     r8, rsi; pszSrc
0x180033caf  mov     [rsp+rcx*2+268h+Buffer], ax
0x180033cb4  mov     edx, ebx; cchDest
0x180033cb6  lea     rcx, [rsp+268h+Buffer]; pszDest
0x180033cbb  call    StringCchCatW
0x180033cc0  mov     ebx, eax
0x180033cc2  test    eax, eax
0x180033cc4  js      short loc_180033D01
0x180033cc6  lea     rcx, [rsp+268h+Buffer]; lpLibFileName
0x180033ccb  call    cs:__imp_LoadLibraryW
0x180033cd1  test    rax, rax
0x180033cd4  jnz     short loc_180033CED
0x180033cd6  call    cs:__imp_GetLastError
0x180033cdc  mov     ebx, eax
0x180033cde  test    eax, eax
0x180033ce0  jle     short loc_180033D01
0x180033ce2  movzx   ebx, ax
0x180033ce5  or      ebx, 80070000h
0x180033ceb  jmp     short loc_180033D01
0x180033ced  mov     [rdi], rax
0x180033cf0  jmp     short loc_180033D01
0x180033cf2  mov     ebx, 80004005h
0x180033cf7  jmp     short loc_180033D01
0x180033cf9  mov     [rdi], r14
0x180033cfc  mov     ebx, 80070057h
0x180033d01  mov     eax, ebx
0x180033d03  mov     rcx, [rsp+268h+var_38]
0x180033d0b  xor     rcx, rsp; StackCookie
0x180033d0e  call    __security_check_cookie
0x180033d13  mov     rbx, [rsp+268h+arg_10]
0x180033d1b  add     rsp, 240h
0x180033d22  pop     r15
0x180033d24  pop     r14
0x180033d26  pop     rdi
0x180033d27  pop     rsi
0x180033d28  pop     rbp
0x180033d29  retn
```
