# LoadLibraryFromSystemDirectory

- ea: `0x1800352ac`
- end: `0x180035427`
- name: `LoadLibraryFromSystemDirectory`
- size: `379`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, HMODULE *)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180009f70`
- `0x18001a540`
- `0x180035430`
- `0x1800373fc`

## callees

- `0x180001f20`
- `0x180002938`
- `0x180020acc`
- `0x1800352ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180035308`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180035308`
- `KERNEL32!LoadLibraryW` at `0x1800353bb`
- `KERNEL32!LoadLibraryW` at `0x1800353bb`
- `KERNEL32!GetSystemDirectoryW` at `0x180035374`
- `KERNEL32!GetSystemDirectoryW` at `0x180035374`
- `KERNEL32!GetLastError` at `0x1800353cc`
- `KERNEL32!GetLastError` at `0x1800353cc`

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
0x1800352ac  mov     [rsp+arg_10], rbx
0x1800352b1  push    rbp
0x1800352b2  push    rsi
0x1800352b3  push    rdi
0x1800352b4  push    r14
0x1800352b6  push    r15
0x1800352b8  sub     rsp, 240h
0x1800352bf  mov     rax, cs:__security_cookie
0x1800352c6  xor     rax, rsp
0x1800352c9  mov     [rsp+268h+var_38], rax
0x1800352d1  mov     rdi, rdx
0x1800352d4  mov     rsi, rcx
0x1800352d7  xor     edx, edx; Val
0x1800352d9  lea     rcx, [rsp+268h+Buffer]; void *
0x1800352de  mov     r8d, 208h; Size
0x1800352e4  call    memset_0
0x1800352e9  xor     r14d, r14d
0x1800352ec  test    rsi, rsi
0x1800352ef  jz      loc_1800353F5
0x1800352f5  test    rdi, rdi
0x1800352f8  jz      loc_1800353F5
0x1800352fe  lea     rdx, SubBlock; "\\"
0x180035305  mov     rcx, rsi; Str
0x180035308  call    cs:__imp_wcsstr
0x18003530f  nop     dword ptr [rax+rax+00h]
0x180035314  mov     [rdi], r14
0x180035317  test    rax, rax
0x18003531a  jnz     loc_1800353F8
0x180035320  mov     r15d, 103h
0x180035326  mov     rax, rsi
0x180035329  mov     edx, r15d
0x18003532c  cmp     [rax], r14w
0x180035330  jz      short loc_18003533C
0x180035332  add     rax, 2
0x180035336  sub     rdx, 1
0x18003533a  jnz     short loc_18003532C
0x18003533c  mov     rax, rdx
0x18003533f  mov     ebx, 80070057h
0x180035344  neg     rax
0x180035347  mov     rax, rdx
0x18003534a  sbb     ecx, ecx
0x18003534c  not     ecx
0x18003534e  and     ebx, ecx
0x180035350  mov     rcx, r15
0x180035353  sub     rcx, rdx
0x180035356  neg     rax
0x180035359  sbb     rbp, rbp
0x18003535c  and     rbp, rcx
0x18003535f  test    rdx, rdx
0x180035362  jz      loc_1800353FD
0x180035368  mov     ebx, 104h
0x18003536d  lea     rcx, [rsp+268h+Buffer]; lpBuffer
0x180035372  mov     edx, ebx; uSize
0x180035374  call    cs:__imp_GetSystemDirectoryW
0x18003537b  nop     dword ptr [rax+rax+00h]
0x180035380  mov     ecx, eax
0x180035382  lea     rax, [rcx-1]
0x180035386  cmp     rax, 101h
0x18003538c  ja      short loc_1800353EE
0x18003538e  lea     rax, [rcx+rbp]
0x180035392  cmp     rax, r15
0x180035395  jnb     short loc_1800353EE
0x180035397  mov     eax, 5Ch ; '\'
0x18003539c  mov     r8, rsi; pszSrc
0x18003539f  mov     [rsp+rcx*2+268h+Buffer], ax
0x1800353a4  mov     edx, ebx; cchDest
0x1800353a6  lea     rcx, [rsp+268h+Buffer]; pszDest
0x1800353ab  call    StringCchCatW
0x1800353b0  mov     ebx, eax
0x1800353b2  test    eax, eax
0x1800353b4  js      short loc_1800353FD
0x1800353b6  lea     rcx, [rsp+268h+Buffer]; lpLibFileName
0x1800353bb  call    cs:__imp_LoadLibraryW
0x1800353c2  nop     dword ptr [rax+rax+00h]
0x1800353c7  test    rax, rax
0x1800353ca  jnz     short loc_1800353E9
0x1800353cc  call    cs:__imp_GetLastError
0x1800353d3  nop     dword ptr [rax+rax+00h]
0x1800353d8  mov     ebx, eax
0x1800353da  test    eax, eax
0x1800353dc  jle     short loc_1800353FD
0x1800353de  movzx   ebx, ax
0x1800353e1  or      ebx, 80070000h
0x1800353e7  jmp     short loc_1800353FD
0x1800353e9  mov     [rdi], rax
0x1800353ec  jmp     short loc_1800353FD
0x1800353ee  mov     ebx, 80004005h
0x1800353f3  jmp     short loc_1800353FD
0x1800353f5  mov     [rdi], r14
0x1800353f8  mov     ebx, 80070057h
0x1800353fd  mov     eax, ebx
0x1800353ff  mov     rcx, [rsp+268h+var_38]
0x180035407  xor     rcx, rsp; StackCookie
0x18003540a  call    __security_check_cookie
0x18003540f  mov     rbx, [rsp+268h+arg_10]
0x180035417  add     rsp, 240h
0x18003541e  pop     r15
0x180035420  pop     r14
0x180035422  pop     rdi
0x180035423  pop     rsi
0x180035424  pop     rbp
0x180035425  retn
```
