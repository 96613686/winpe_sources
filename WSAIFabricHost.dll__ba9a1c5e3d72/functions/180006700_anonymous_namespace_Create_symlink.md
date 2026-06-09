# _anonymous_namespace_::_Create_symlink

- ea: `0x180006700`
- end: `0x18000675e`
- name: `_anonymous_namespace_::_Create_symlink`
- size: `94`
- prototype: `DWORD __fastcall(LPCWSTR lpSymlinkFileName, LPCWSTR lpTargetFileName, DWORD dwFlags)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x180006e3c`
- `0x180006e50`

## callees

- `0x180006700`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006726`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006744`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006726`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006744`
- `api-ms-win-core-file-l2-1-0!CreateSymbolicLinkW` at `0x18000671c`
- `api-ms-win-core-file-l2-1-0!CreateSymbolicLinkW` at `0x18000673a`
- `api-ms-win-core-file-l2-1-0!CreateSymbolicLinkW` at `0x18000671c`
- `api-ms-win-core-file-l2-1-0!CreateSymbolicLinkW` at `0x18000673a`

## pseudocode

```c
DWORD __fastcall anonymous_namespace_::_Create_symlink(
        LPCWSTR lpSymlinkFileName,
        LPCWSTR lpTargetFileName,
        DWORD dwFlags)
{
  DWORD result; // eax

  if ( CreateSymbolicLinkW(lpSymlinkFileName, lpTargetFileName, dwFlags | 2) )
    return 0;
  result = GetLastError();
  if ( result != 87 )
    return result;
  if ( CreateSymbolicLinkW(lpSymlinkFileName, lpTargetFileName, dwFlags) )
    return 0;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x180006700  mov     [rsp+arg_0], rbx
0x180006705  mov     [rsp+arg_8], rsi
0x18000670a  push    rdi
0x18000670b  sub     rsp, 20h
0x18000670f  mov     ebx, r8d
0x180006712  mov     rdi, rdx
0x180006715  or      r8d, 2; dwFlags
0x180006719  mov     rsi, rcx
0x18000671c  call    cs:__imp_CreateSymbolicLinkW
0x180006722  test    al, al
0x180006724  jnz     short loc_18000674C
0x180006726  call    cs:__imp_GetLastError
0x18000672c  cmp     eax, 57h ; 'W'
0x18000672f  jnz     short loc_18000674E
0x180006731  mov     r8d, ebx; dwFlags
0x180006734  mov     rdx, rdi; lpTargetFileName
0x180006737  mov     rcx, rsi; lpSymlinkFileName
0x18000673a  call    cs:__imp_CreateSymbolicLinkW
0x180006740  test    al, al
0x180006742  jnz     short loc_18000674C
0x180006744  call    cs:__imp_GetLastError
0x18000674a  jmp     short loc_18000674E
0x18000674c  xor     eax, eax
0x18000674e  mov     rbx, [rsp+28h+arg_0]
0x180006753  mov     rsi, [rsp+28h+arg_8]
0x180006758  add     rsp, 20h
0x18000675c  pop     rdi
0x18000675d  retn
```
