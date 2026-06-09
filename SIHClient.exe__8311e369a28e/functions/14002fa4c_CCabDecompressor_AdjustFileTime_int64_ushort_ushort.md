# CCabDecompressor::AdjustFileTime(__int64,ushort,ushort)

- ea: `0x14002fa4c`
- end: `0x14002fb32`
- name: `?AdjustFileTime@CCabDecompressor@@CAH_JGG@Z`
- size: `230`
- prototype: `__int64 __fastcall(__int64, WORD, WORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002fb40`

## callees

- `0x1400154b4`
- `0x14002fa4c`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002fad7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002fad7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x14002fa9c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x14002fa9c`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x14002fab0`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x14002fab0`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x14002facd`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x14002facd`

## string_xrefs

- `0x14002faf7`: `AdjustFileTime - SetFileTime`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CCabDecompressor::AdjustFileTime(__int64 a1, WORD a2, WORD a3)
{
  signed int LastError; // eax
  signed int v5; // ecx
  __int64 v7; // [rsp+20h] [rbp-38h]
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
    LastError = GetLastError();
    v5 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v5 = LastError;
    if ( v5 >= 0 )
      v5 = -2147418113;
    LODWORD(v7) = v5;
    WUTrace(0, 0, 32, 3, v7, L"AdjustFileTime - SetFileTime");
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x14002fa4c  push    rbx
0x14002fa4e  sub     rsp, 50h
0x14002fa52  mov     rax, cs:__security_cookie
0x14002fa59  xor     rax, rsp
0x14002fa5c  mov     [rsp+58h+var_18], rax
0x14002fa61  mov     qword ptr [rsp+58h+FileTime.dwLowDateTime], 0
0x14002fa6a  movzx   r9d, r8w
0x14002fa6e  mov     qword ptr [rsp+58h+CreationTime.dwLowDateTime], 0
0x14002fa77  movzx   eax, dx
0x14002fa7a  mov     rbx, rcx
0x14002fa7d  test    rcx, rcx
0x14002fa80  jz      loc_14002FB16
0x14002fa86  cmp     dword ptr [rcx+10h], 1
0x14002fa8a  jnz     loc_14002FB16
0x14002fa90  lea     r8, [rsp+58h+FileTime]; lpFileTime
0x14002fa95  movzx   edx, r9w; wFatTime
0x14002fa99  movzx   ecx, ax; wFatDate
0x14002fa9c  call    cs:__imp_DosDateTimeToFileTime
0x14002faa2  test    eax, eax
0x14002faa4  jz      short loc_14002FB16
0x14002faa6  lea     rdx, [rsp+58h+CreationTime]; lpFileTime
0x14002faab  lea     rcx, [rsp+58h+FileTime]; lpLocalFileTime
0x14002fab0  call    cs:__imp_LocalFileTimeToFileTime
0x14002fab6  test    eax, eax
0x14002fab8  jz      short loc_14002FB16
0x14002faba  mov     rcx, [rbx+8]; hFile
0x14002fabe  lea     r9, [rsp+58h+CreationTime]; lpLastWriteTime
0x14002fac3  lea     r8, [rsp+58h+CreationTime]; lpLastAccessTime
0x14002fac8  lea     rdx, [rsp+58h+CreationTime]; lpCreationTime
0x14002facd  call    cs:__imp_SetFileTime
0x14002fad3  test    eax, eax
0x14002fad5  jnz     short loc_14002FB2B
0x14002fad7  call    cs:__imp_GetLastError
0x14002fadd  movzx   ecx, ax
0x14002fae0  or      ecx, 80070000h
0x14002fae6  test    eax, eax
0x14002fae8  cmovle  ecx, eax
0x14002faeb  mov     eax, 8000FFFFh
0x14002faf0  test    ecx, ecx
0x14002faf2  cmovns  ecx, eax
0x14002faf5  xor     edx, edx
0x14002faf7  lea     rax, aAdjustfiletime; "AdjustFileTime - SetFileTime"
0x14002fafe  mov     [rsp+58h+var_30], rax
0x14002fb03  mov     dword ptr [rsp+58h+var_38], ecx
0x14002fb07  xor     ecx, ecx
0x14002fb09  lea     r9d, [rdx+3]
0x14002fb0d  lea     r8d, [rdx+20h]
0x14002fb11  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14002fb16  xor     eax, eax
0x14002fb18  mov     rcx, [rsp+58h+var_18]
0x14002fb1d  xor     rcx, rsp; StackCookie
0x14002fb20  call    __security_check_cookie
0x14002fb25  add     rsp, 50h
0x14002fb29  pop     rbx
0x14002fb2a  retn
0x14002fb2b  mov     eax, 1
0x14002fb30  jmp     short loc_14002FB18
```
