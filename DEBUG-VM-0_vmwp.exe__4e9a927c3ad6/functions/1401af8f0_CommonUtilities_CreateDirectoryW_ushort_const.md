# CommonUtilities::CreateDirectoryW(ushort const *)

- ea: `0x1401af8f0`
- end: `0x1401afa60`
- name: `?CreateDirectoryW@CommonUtilities@@YAKPEBG@Z`
- size: `368`
- prototype: `unsigned int __fastcall(CommonUtilities *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x14008209c`

## callees

- `0x1400d69d8`
- `0x140132940`
- `0x1401af8f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401af946`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401af9ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401af946`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401af9ed`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1401af932`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1401af9dd`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1401af932`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1401af9dd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1401afa05`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1401afa05`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1401af917`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1401af917`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x1401af99a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x1401af99a`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1401af981`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1401af981`

## pseudocode

```c
DWORD __fastcall CommonUtilities::CreateDirectoryW(const WCHAR *this, const unsigned __int16 *a2)
{
  DWORD result; // eax
  unsigned int v4; // r11d
  LPWSTR v5; // rbx
  WCHAR v6; // ax
  DWORD FileAttributesW; // eax
  WCHAR pszPath[264]; // [rsp+20h] [rbp-228h] BYREF

  if ( !PathIsRelativeW(this) )
  {
    if ( CreateDirectoryW(this, 0) )
      return 0;
    result = GetLastError();
    if ( result != 3 )
      return result;
    if ( StringCchCopyW(pszPath, 0x104u, this) < 0 || PathCchAddBackslash(pszPath, v4) < 0 )
      return 206;
    v5 = PathSkipRootW(pszPath);
    if ( v5 )
    {
      while ( 1 )
      {
        v6 = *v5;
        if ( !*v5 )
          break;
        do
        {
          if ( v6 == 92 )
            break;
          v6 = *++v5;
        }
        while ( *v5 );
        if ( *v5 )
        {
          *v5 = 0;
          if ( !CreateDirectoryW(pszPath, 0) )
          {
            result = GetLastError();
            if ( result != 183 )
              return result;
            FileAttributesW = GetFileAttributesW(pszPath);
            if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
              return 183;
          }
        }
        *v5++ = 92;
      }
      return 0;
    }
  }
  return 161;
}

```

## disassembly

```asm
0x1401af8f0  mov     [rsp+arg_8], rbx
0x1401af8f5  mov     [rsp+arg_10], rbp
0x1401af8fa  push    rdi
0x1401af8fb  sub     rsp, 240h
0x1401af902  mov     rax, cs:__security_cookie
0x1401af909  xor     rax, rsp
0x1401af90c  mov     [rsp+248h+var_18], rax
0x1401af914  mov     rbx, rcx
0x1401af917  call    cs:__imp_PathIsRelativeW
0x1401af91e  nop     dword ptr [rax+rax+00h]
0x1401af923  xor     edi, edi
0x1401af925  test    eax, eax
0x1401af927  jnz     loc_1401AFA35
0x1401af92d  xor     edx, edx; lpSecurityAttributes
0x1401af92f  mov     rcx, rbx; lpPathName
0x1401af932  call    cs:__imp_CreateDirectoryW
0x1401af939  nop     dword ptr [rax+rax+00h]
0x1401af93e  test    eax, eax
0x1401af940  jnz     loc_1401AFA31
0x1401af946  call    cs:__imp_GetLastError
0x1401af94d  nop     dword ptr [rax+rax+00h]
0x1401af952  cmp     eax, 3
0x1401af955  jnz     loc_1401AFA3A
0x1401af95b  mov     r11d, 104h
0x1401af961  lea     rcx, [rsp+248h+pszPath]; unsigned __int16 *
0x1401af966  mov     edx, r11d; unsigned __int64
0x1401af969  mov     r8, rbx; unsigned __int16 *
0x1401af96c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1401af971  test    eax, eax
0x1401af973  js      loc_1401AFA2A
0x1401af979  mov     edx, r11d; cchPath
0x1401af97c  lea     rcx, [rsp+248h+pszPath]; pszPath
0x1401af981  call    cs:__imp_PathCchAddBackslash
0x1401af988  nop     dword ptr [rax+rax+00h]
0x1401af98d  test    eax, eax
0x1401af98f  js      loc_1401AFA2A
0x1401af995  lea     rcx, [rsp+248h+pszPath]; pszPath
0x1401af99a  call    cs:__imp_PathSkipRootW
0x1401af9a1  nop     dword ptr [rax+rax+00h]
0x1401af9a6  mov     rbx, rax
0x1401af9a9  test    rax, rax
0x1401af9ac  jz      loc_1401AFA35
0x1401af9b2  lea     ebp, [rdi+5Ch]
0x1401af9b5  movzx   eax, word ptr [rbx]
0x1401af9b8  test    ax, ax
0x1401af9bb  jz      short loc_1401AFA31
0x1401af9bd  cmp     ax, bp
0x1401af9c0  jz      short loc_1401AF9CE
0x1401af9c2  add     rbx, 2
0x1401af9c6  movzx   eax, word ptr [rbx]
0x1401af9c9  test    ax, ax
0x1401af9cc  jnz     short loc_1401AF9BD
0x1401af9ce  cmp     [rbx], di
0x1401af9d1  jz      short loc_1401AFA1A
0x1401af9d3  xor     edx, edx; lpSecurityAttributes
0x1401af9d5  mov     [rbx], di
0x1401af9d8  lea     rcx, [rsp+248h+pszPath]; lpPathName
0x1401af9dd  call    cs:__imp_CreateDirectoryW
0x1401af9e4  nop     dword ptr [rax+rax+00h]
0x1401af9e9  test    eax, eax
0x1401af9eb  jnz     short loc_1401AFA1A
0x1401af9ed  call    cs:__imp_GetLastError
0x1401af9f4  nop     dword ptr [rax+rax+00h]
0x1401af9f9  cmp     eax, 0B7h
0x1401af9fe  jnz     short loc_1401AFA3A
0x1401afa00  lea     rcx, [rsp+248h+pszPath]; lpFileName
0x1401afa05  call    cs:__imp_GetFileAttributesW
0x1401afa0c  nop     dword ptr [rax+rax+00h]
0x1401afa11  cmp     eax, 0FFFFFFFFh
0x1401afa14  jz      short loc_1401AFA23
0x1401afa16  test    al, 10h
0x1401afa18  jz      short loc_1401AFA23
0x1401afa1a  mov     [rbx], bp
0x1401afa1d  add     rbx, 2
0x1401afa21  jmp     short loc_1401AF9B5
0x1401afa23  mov     eax, 0B7h
0x1401afa28  jmp     short loc_1401AFA3A
0x1401afa2a  mov     eax, 0CEh
0x1401afa2f  jmp     short loc_1401AFA3A
0x1401afa31  xor     eax, eax
0x1401afa33  jmp     short loc_1401AFA3A
0x1401afa35  mov     eax, 0A1h
0x1401afa3a  mov     rcx, [rsp+248h+var_18]
0x1401afa42  xor     rcx, rsp; StackCookie
0x1401afa45  call    __security_check_cookie
0x1401afa4a  lea     r11, [rsp+248h+var_8]
0x1401afa52  mov     rbx, [r11+18h]
0x1401afa56  mov     rbp, [r11+20h]
0x1401afa5a  mov     rsp, r11
0x1401afa5d  pop     rdi
0x1401afa5e  retn
```
