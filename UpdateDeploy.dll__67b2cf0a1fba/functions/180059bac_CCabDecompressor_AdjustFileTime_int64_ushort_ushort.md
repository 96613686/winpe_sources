# CCabDecompressor::AdjustFileTime(__int64,ushort,ushort)

- ea: `0x180059bac`
- end: `0x180059c92`
- name: `?AdjustFileTime@CCabDecompressor@@CAH_JGG@Z`
- size: `230`
- prototype: `__int64 __fastcall(__int64, WORD, WORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180059ca0`

## callees

- `0x1800110fc`
- `0x180059bac`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059c37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059c37`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x180059bfc`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x180059bfc`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x180059c10`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x180059c10`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180059c2d`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180059c2d`

## string_xrefs

- `0x180059c57`: `AdjustFileTime - SetFileTime`

## pseudocode

```c
__int64 __fastcall CCabDecompressor::AdjustFileTime(__int64 a1, WORD a2, WORD a3)
{
  FILETIME CreationTime; // [rsp+30h] [rbp-28h] BYREF
  struct _FILETIME FileTime; // [rsp+38h] [rbp-20h] BYREF

  FileTime = 0;
  CreationTime = 0;
  if ( !a1
    || *(_DWORD *)(a1 + 16) != 1
    || !DosDateTimeToFileTime(a2, a3, &FileTime)
    || !LocalFileTimeToFileTime(&FileTime, &CreationTime) )
  {
    return 0;
  }
  if ( !SetFileTime(*(HANDLE *)(a1 + 8), &CreationTime, &CreationTime, &CreationTime) )
  {
    GetLastError();
    WUTrace(0, 0, 32, 3);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180059bac  push    rbx
0x180059bae  sub     rsp, 50h
0x180059bb2  mov     rax, cs:__security_cookie
0x180059bb9  xor     rax, rsp
0x180059bbc  mov     [rsp+58h+var_18], rax
0x180059bc1  mov     qword ptr [rsp+58h+FileTime.dwLowDateTime], 0
0x180059bca  movzx   r9d, r8w
0x180059bce  mov     qword ptr [rsp+58h+CreationTime.dwLowDateTime], 0
0x180059bd7  movzx   eax, dx
0x180059bda  mov     rbx, rcx
0x180059bdd  test    rcx, rcx
0x180059be0  jz      loc_180059C76
0x180059be6  cmp     dword ptr [rcx+10h], 1
0x180059bea  jnz     loc_180059C76
0x180059bf0  lea     r8, [rsp+58h+FileTime]; lpFileTime
0x180059bf5  movzx   edx, r9w; wFatTime
0x180059bf9  movzx   ecx, ax; wFatDate
0x180059bfc  call    cs:__imp_DosDateTimeToFileTime
0x180059c02  test    eax, eax
0x180059c04  jz      short loc_180059C76
0x180059c06  lea     rdx, [rsp+58h+CreationTime]; lpFileTime
0x180059c0b  lea     rcx, [rsp+58h+FileTime]; lpLocalFileTime
0x180059c10  call    cs:__imp_LocalFileTimeToFileTime
0x180059c16  test    eax, eax
0x180059c18  jz      short loc_180059C76
0x180059c1a  mov     rcx, [rbx+8]; hFile
0x180059c1e  lea     r9, [rsp+58h+CreationTime]; lpLastWriteTime
0x180059c23  lea     r8, [rsp+58h+CreationTime]; lpLastAccessTime
0x180059c28  lea     rdx, [rsp+58h+CreationTime]; lpCreationTime
0x180059c2d  call    cs:__imp_SetFileTime
0x180059c33  test    eax, eax
0x180059c35  jnz     short loc_180059C8B
0x180059c37  call    cs:__imp_GetLastError
0x180059c3d  movzx   ecx, ax
0x180059c40  or      ecx, 80070000h
0x180059c46  test    eax, eax
0x180059c48  cmovle  ecx, eax
0x180059c4b  mov     eax, 8000FFFFh
0x180059c50  test    ecx, ecx
0x180059c52  cmovns  ecx, eax
0x180059c55  xor     edx, edx
0x180059c57  lea     rax, aAdjustfiletime; "AdjustFileTime - SetFileTime"
0x180059c5e  mov     [rsp+58h+var_30], rax
0x180059c63  mov     [rsp+58h+var_38], ecx
0x180059c67  xor     ecx, ecx
0x180059c69  lea     r9d, [rdx+3]
0x180059c6d  lea     r8d, [rdx+20h]
0x180059c71  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180059c76  xor     eax, eax
0x180059c78  mov     rcx, [rsp+58h+var_18]
0x180059c7d  xor     rcx, rsp; StackCookie
0x180059c80  call    __security_check_cookie
0x180059c85  add     rsp, 50h
0x180059c89  pop     rbx
0x180059c8a  retn
0x180059c8b  mov     eax, 1
0x180059c90  jmp     short loc_180059C78
```
