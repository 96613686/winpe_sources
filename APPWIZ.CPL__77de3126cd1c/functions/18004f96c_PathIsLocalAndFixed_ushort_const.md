# PathIsLocalAndFixed(ushort const *)

- ea: `0x18004f96c`
- end: `0x18004f9ff`
- name: `?PathIsLocalAndFixed@@YAHPEBG@Z`
- size: `147`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002b2b0`

## callees

- `0x18000791c`
- `0x18004f96c`
- `0x1800582e0`

## import_xrefs

- `SHLWAPI!PathStripToRootW` at `0x18004f9bb`
- `SHLWAPI!PathStripToRootW` at `0x18004f9bb`
- `SHLWAPI!PathIsUNCW` at `0x18004f99a`
- `SHLWAPI!PathIsUNCW` at `0x18004f99a`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18004f9ca`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18004f9ca`

## pseudocode

```c
_BOOL8 __fastcall PathIsLocalAndFixed(const unsigned __int16 *a1)
{
  _BOOL8 result; // rax
  WCHAR pszPath[264]; // [rsp+20h] [rbp-228h] BYREF

  result = 0;
  if ( a1 )
  {
    if ( *a1 )
    {
      if ( !PathIsUNCW(a1) )
      {
        StringCchCopyW(pszPath, 0x104u, a1);
        if ( !PathStripToRootW(pszPath) || GetDriveTypeW(pszPath) == 3 )
          return 1;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004f96c  mov     [rsp+arg_8], rbx
0x18004f971  push    rdi
0x18004f972  sub     rsp, 240h
0x18004f979  mov     rax, cs:__security_cookie
0x18004f980  xor     rax, rsp
0x18004f983  mov     [rsp+248h+var_18], rax
0x18004f98b  xor     edi, edi
0x18004f98d  mov     rbx, rcx
0x18004f990  test    rcx, rcx
0x18004f993  jz      short loc_18004F9DC
0x18004f995  cmp     [rcx], di
0x18004f998  jz      short loc_18004F9DC
0x18004f99a  call    cs:__imp_PathIsUNCW
0x18004f9a0  test    eax, eax
0x18004f9a2  jnz     short loc_18004F9DC
0x18004f9a4  mov     r8, rbx; unsigned __int16 *
0x18004f9a7  lea     rcx, [rsp+248h+pszPath]; unsigned __int16 *
0x18004f9ac  mov     edx, 104h; unsigned __int64
0x18004f9b1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004f9b6  lea     rcx, [rsp+248h+pszPath]; pszPath
0x18004f9bb  call    cs:__imp_PathStripToRootW
0x18004f9c1  test    eax, eax
0x18004f9c3  jz      short loc_18004F9D5
0x18004f9c5  lea     rcx, [rsp+248h+pszPath]; lpRootPathName
0x18004f9ca  call    cs:__imp_GetDriveTypeW
0x18004f9d0  cmp     eax, 3
0x18004f9d3  jnz     short loc_18004F9DC
0x18004f9d5  mov     eax, 1
0x18004f9da  jmp     short loc_18004F9DE
0x18004f9dc  xor     eax, eax
0x18004f9de  mov     rcx, [rsp+248h+var_18]
0x18004f9e6  xor     rcx, rsp; StackCookie
0x18004f9e9  call    __security_check_cookie
0x18004f9ee  mov     rbx, [rsp+248h+arg_8]
0x18004f9f6  add     rsp, 240h
0x18004f9fd  pop     rdi
0x18004f9fe  retn
```
