# _anonymous_namespace_::Remover::Delete

- ea: `0x1800471f8`
- end: `0x1800472bf`
- name: `_anonymous_namespace_::Remover::Delete`
- size: `199`
- prototype: `__int64 __fastcall(unsigned int (__fastcall **)(const WCHAR *), const WCHAR *, Common *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180047560`

## callees

- `0x1800471f8`
- `0x180047494`
- `0x1800474c0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047226`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004725c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047288`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047226`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004725c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047288`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18004721c`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18004724e`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18004721c`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18004724e`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180047241`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18004727e`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180047241`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18004727e`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::Remover::Delete(
        unsigned int (__fastcall **a1)(const WCHAR *),
        const WCHAR *a2,
        Common *a3)
{
  unsigned int v4; // ebx
  int v5; // edx
  DWORD LastError; // edi
  const struct _WIN32_FIND_DATAW *v9; // rdx

  v4 = 0;
  v5 = *(_DWORD *)a3;
  if ( (*(_DWORD *)a3 & 0x10) != 0 )
  {
    LastError = 0;
    if ( !RemoveDirectoryW(a2) )
    {
      LastError = GetLastError();
      if ( LastError == 5 )
      {
        v9 = (const struct _WIN32_FIND_DATAW *)*(unsigned int *)a3;
        if ( ((unsigned __int8)v9 & 1) != 0 )
        {
          if ( SetFileAttributesW(a2, (unsigned int)v9 & 0xFFFFFFFE) && RemoveDirectoryW(a2) )
            LastError = 0;
          else
            LastError = GetLastError();
        }
      }
    }
    v4 = Common::IsDirectoryReparsePointOpaque(a3, v9) + 1;
  }
  else if ( ((v5 & 1) == 0 || SetFileAttributesW(a2, v5 & 0xFFFFFFFE)) && (*a1)(a2) )
  {
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
  }
  return anonymous_namespace_::Remover::Report(a1, a2, v4, LastError);
}

```

## disassembly

```asm
0x1800471f8  push    rbx
0x1800471fa  push    rsi
0x1800471fb  push    rdi
0x1800471fc  push    r14
0x1800471fe  push    r15
0x180047200  sub     rsp, 20h
0x180047204  mov     rsi, rdx
0x180047207  xor     ebx, ebx
0x180047209  mov     edx, [r8]
0x18004720c  mov     r14, r8
0x18004720f  mov     r15, rcx
0x180047212  test    dl, 10h
0x180047215  jz      short loc_180047273
0x180047217  mov     rcx, rsi; lpPathName
0x18004721a  mov     edi, ebx
0x18004721c  call    cs:__imp_RemoveDirectoryW
0x180047222  test    eax, eax
0x180047224  jnz     short loc_180047264
0x180047226  call    cs:__imp_GetLastError
0x18004722c  mov     edi, eax
0x18004722e  cmp     eax, 5
0x180047231  jnz     short loc_180047264
0x180047233  mov     edx, [r14]
0x180047236  test    dl, 1
0x180047239  jz      short loc_180047264
0x18004723b  and     edx, 0FFFFFFFEh; dwFileAttributes
0x18004723e  mov     rcx, rsi; lpFileName
0x180047241  call    cs:__imp_SetFileAttributesW
0x180047247  test    eax, eax
0x180047249  jz      short loc_18004725C
0x18004724b  mov     rcx, rsi; lpPathName
0x18004724e  call    cs:__imp_RemoveDirectoryW
0x180047254  test    eax, eax
0x180047256  jz      short loc_18004725C
0x180047258  mov     edi, ebx
0x18004725a  jmp     short loc_180047264
0x18004725c  call    cs:__imp_GetLastError
0x180047262  mov     edi, eax
0x180047264  mov     rcx, r14; this
0x180047267  call    ?IsDirectoryReparsePointOpaque@Common@@YA_NAEBU_WIN32_FIND_DATAW@@@Z; Common::IsDirectoryReparsePointOpaque(_WIN32_FIND_DATAW const &)
0x18004726c  movzx   ebx, al
0x18004726f  inc     ebx
0x180047271  jmp     short loc_1800472A3
0x180047273  test    dl, 1
0x180047276  jz      short loc_180047292
0x180047278  and     edx, 0FFFFFFFEh; dwFileAttributes
0x18004727b  mov     rcx, rsi; lpFileName
0x18004727e  call    cs:__imp_SetFileAttributesW
0x180047284  test    eax, eax
0x180047286  jnz     short loc_180047292
0x180047288  call    cs:__imp_GetLastError
0x18004728e  mov     edi, eax
0x180047290  jmp     short loc_1800472A3
0x180047292  mov     rax, [r15]
0x180047295  mov     rcx, rsi
0x180047298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004729d  test    eax, eax
0x18004729f  jz      short loc_180047288
0x1800472a1  mov     edi, ebx
0x1800472a3  mov     r9d, edi
0x1800472a6  mov     r8d, ebx
0x1800472a9  mov     rdx, rsi
0x1800472ac  mov     rcx, r15
0x1800472af  add     rsp, 20h
0x1800472b3  pop     r15
0x1800472b5  pop     r14
0x1800472b7  pop     rdi
0x1800472b8  pop     rsi
0x1800472b9  pop     rbx
0x1800472ba  jmp     _anonymous_namespace___Remover__Report
```
