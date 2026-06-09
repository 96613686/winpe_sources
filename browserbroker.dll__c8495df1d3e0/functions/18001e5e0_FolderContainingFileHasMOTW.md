# _FolderContainingFileHasMOTW

- ea: `0x18001e5e0`
- end: `0x18001e6b6`
- name: `_FolderContainingFileHasMOTW`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001e194`

## callees

- `0x180002ce0`
- `0x180003160`
- `0x18001df80`
- `0x18001e5e0`
- `0x18001e9a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001e67e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001e67e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001e610`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001e610`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18001e61b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18001e61b`

## pseudocode

```c
char __fastcall FolderContainingFileHasMOTW(__int64 a1)
{
  char v1; // di
  unsigned __int64 v2; // rax
  unsigned __int64 v3; // rbx
  WCHAR pszPath[264]; // [rsp+20h] [rbp-248h] BYREF

  v1 = 0;
  _o_wcscpy_s(pszPath, 260, a1);
  PathRemoveFileSpecW(pszPath);
  v2 = -1;
  do
    ++v2;
  while ( pszPath[v2] );
  if ( v2 > 6 )
  {
    v3 = 2 * v2 - 12;
    if ( !wmemcmp((WCHAR *)((char *)pszPath + v3), L"_files", 6u) )
    {
      if ( v3 >= 0x208 )
        _report_rangecheckfailure();
      *(WCHAR *)((char *)pszPath + v3) = 0;
      _o_wcscat_s(pszPath, 260, L".htm");
      return ExactFileHasMOTW(pszPath);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18001e5e0  push    rbx
0x18001e5e2  push    rbp
0x18001e5e3  push    rsi
0x18001e5e4  push    rdi
0x18001e5e5  sub     rsp, 248h
0x18001e5ec  mov     rax, cs:__security_cookie
0x18001e5f3  xor     rax, rsp
0x18001e5f6  mov     [rsp+268h+var_38], rax
0x18001e5fe  mov     r8, rcx
0x18001e601  xor     ebp, ebp
0x18001e603  lea     rcx, [rsp+268h+pszPath]
0x18001e608  mov     edx, 104h
0x18001e60d  mov     dil, bpl
0x18001e610  call    cs:__imp__o_wcscpy_s
0x18001e616  lea     rcx, [rsp+268h+pszPath]; pszPath
0x18001e61b  call    cs:__imp_PathRemoveFileSpecW
0x18001e621  lea     rcx, [rsp+268h+pszPath]
0x18001e626  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e62a  inc     rax
0x18001e62d  cmp     [rcx+rax*2], bp
0x18001e631  jnz     short loc_18001E62A
0x18001e633  mov     r8d, 6; N
0x18001e639  cmp     rax, r8
0x18001e63c  jbe     short loc_18001E691
0x18001e63e  lea     rbx, ds:0FFFFFFFFFFFFFFF4h[rax*2]
0x18001e646  lea     rsi, [rsp+268h+pszPath]
0x18001e64b  add     rsi, rbx
0x18001e64e  lea     rdx, aFiles; "_files"
0x18001e655  mov     rcx, rsi; S1
0x18001e658  call    wmemcmp
0x18001e65d  test    eax, eax
0x18001e65f  jnz     short loc_18001E691
0x18001e661  cmp     rbx, 208h
0x18001e668  jnb     short loc_18001E6B0
0x18001e66a  lea     r8, aHtm; ".htm"
0x18001e671  mov     [rsi], bp
0x18001e674  mov     edx, 104h
0x18001e679  lea     rcx, [rsp+268h+pszPath]
0x18001e67e  call    cs:__imp__o_wcscat_s
0x18001e684  lea     rcx, [rsp+268h+pszPath]; unsigned __int16 *
0x18001e689  call    _ExactFileHasMOTW
0x18001e68e  mov     dil, al
0x18001e691  mov     al, dil
0x18001e694  mov     rcx, [rsp+268h+var_38]
0x18001e69c  xor     rcx, rsp; StackCookie
0x18001e69f  call    __security_check_cookie
0x18001e6a4  add     rsp, 248h
0x18001e6ab  pop     rdi
0x18001e6ac  pop     rsi
0x18001e6ad  pop     rbp
0x18001e6ae  pop     rbx
0x18001e6af  retn
0x18001e6b0  call    __report_rangecheckfailure
```
