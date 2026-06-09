# __std_fs_convert_wide_to_narrow_replace_chars

- ea: `0x18000dd94`
- end: `0x18000de77`
- name: `__std_fs_convert_wide_to_narrow_replace_chars`
- size: `227`
- prototype: `__int64 __fastcall(UINT CodePage, LPCWCH lpWideCharStr, int cchWideChar, LPSTR lpMultiByteStr, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004168`

## callees

- `0x18000dd94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ddfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ddfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de43`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000ddec`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000de35`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000ddec`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000de35`

## pseudocode

```c
__int64 __fastcall _std_fs_convert_wide_to_narrow_replace_chars(
        UINT CodePage,
        LPCWCH lpWideCharStr,
        int cchWideChar,
        LPSTR lpMultiByteStr,
        int cbMultiByte)
{
  DWORD LastError; // eax
  __int64 v11; // [rsp+40h] [rbp-18h]

  LODWORD(v11) = WideCharToMultiByte(CodePage, 0x400u, lpWideCharStr, cchWideChar, lpMultiByteStr, cbMultiByte, 0, 0);
  if ( (_DWORD)v11 )
    LastError = 0;
  else
    LastError = GetLastError();
  HIDWORD(v11) = LastError;
  if ( LastError == 1004 )
  {
    LODWORD(v11) = WideCharToMultiByte(CodePage, 0, lpWideCharStr, cchWideChar, lpMultiByteStr, cbMultiByte, 0, 0);
    if ( (_DWORD)v11 )
      HIDWORD(v11) = 0;
    else
      HIDWORD(v11) = GetLastError();
  }
  return v11;
}

```

## disassembly

```asm
0x18000dd94  mov     rax, rsp
0x18000dd97  mov     [rax+8], rbx
0x18000dd9b  mov     [rax+10h], rbp
0x18000dd9f  mov     [rax+18h], rsi
0x18000dda3  mov     [rax+20h], rdi
0x18000dda7  push    r14
0x18000dda9  sub     rsp, 50h
0x18000ddad  mov     r14d, [rsp+58h+arg_20]
0x18000ddb5  mov     rbx, r9
0x18000ddb8  mov     qword ptr [rax-20h], 0
0x18000ddc0  mov     r9d, r8d; cchWideChar
0x18000ddc3  mov     qword ptr [rax-28h], 0
0x18000ddcb  mov     edi, r8d
0x18000ddce  mov     r8, rdx; lpWideCharStr
0x18000ddd1  mov     [rax-30h], r14d
0x18000ddd5  mov     rsi, rdx
0x18000ddd8  mov     [rsp+58h+var_18], 0
0x18000dde1  mov     edx, 400h; dwFlags
0x18000dde6  mov     [rax-38h], rbx
0x18000ddea  mov     ebp, ecx
0x18000ddec  call    cs:__imp_WideCharToMultiByte
0x18000ddf2  mov     dword ptr [rsp+58h+var_18], eax
0x18000ddf6  test    eax, eax
0x18000ddf8  jnz     short loc_18000DE02
0x18000ddfa  call    cs:__imp_GetLastError
0x18000de00  jmp     short loc_18000DE04
0x18000de02  xor     eax, eax
0x18000de04  mov     dword ptr [rsp+58h+var_18+4], eax
0x18000de08  cmp     eax, 3ECh
0x18000de0d  jnz     short loc_18000DE57
0x18000de0f  mov     [rsp+58h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000de18  mov     r9d, edi; cchWideChar
0x18000de1b  mov     [rsp+58h+lpDefaultChar], 0; lpDefaultChar
0x18000de24  mov     r8, rsi; lpWideCharStr
0x18000de27  mov     [rsp+58h+cbMultiByte], r14d; cbMultiByte
0x18000de2c  xor     edx, edx; dwFlags
0x18000de2e  mov     ecx, ebp; CodePage
0x18000de30  mov     [rsp+58h+lpMultiByteStr], rbx; lpMultiByteStr
0x18000de35  call    cs:__imp_WideCharToMultiByte
0x18000de3b  mov     dword ptr [rsp+58h+var_18], eax
0x18000de3f  test    eax, eax
0x18000de41  jnz     short loc_18000DE4F
0x18000de43  call    cs:__imp_GetLastError
0x18000de49  mov     dword ptr [rsp+58h+var_18+4], eax
0x18000de4d  jmp     short loc_18000DE57
0x18000de4f  mov     dword ptr [rsp+58h+var_18+4], 0
0x18000de57  mov     rax, [rsp+58h+var_18]
0x18000de5c  mov     rbx, [rsp+58h+arg_0]
0x18000de61  mov     rbp, [rsp+58h+arg_8]
0x18000de66  mov     rsi, [rsp+58h+arg_10]
0x18000de6b  mov     rdi, [rsp+58h+arg_18]
0x18000de70  add     rsp, 50h
0x18000de74  pop     r14
0x18000de76  retn
```
