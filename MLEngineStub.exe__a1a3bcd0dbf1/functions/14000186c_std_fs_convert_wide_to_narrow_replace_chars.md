# __std_fs_convert_wide_to_narrow_replace_chars

- ea: `0x14000186c`
- end: `0x140001933`
- name: `__std_fs_convert_wide_to_narrow_replace_chars`
- size: `199`
- prototype: `__int64 __fastcall(UINT CodePage, LPCWCH lpWideCharStr, int cchWideChar, LPSTR lpMultiByteStr, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140007260`

## callees

- `0x14000186c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400018c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000190f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400018c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000190f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1400018b8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x140001901`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1400018b8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x140001901`

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
  __int64 v11; // [rsp+40h] [rbp-38h]

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
0x14000186c  mov     rax, rsp
0x14000186f  push    rbx
0x140001870  push    rbp
0x140001871  push    rsi
0x140001872  push    rdi
0x140001873  push    r14
0x140001875  sub     rsp, 50h
0x140001879  mov     r14d, [rsp+78h+arg_20]
0x140001881  mov     rbx, r9
0x140001884  mov     qword ptr [rax-40h], 0
0x14000188c  mov     r9d, r8d; cchWideChar
0x14000188f  mov     qword ptr [rax-48h], 0
0x140001897  mov     edi, r8d
0x14000189a  mov     r8, rdx; lpWideCharStr
0x14000189d  mov     [rax-50h], r14d
0x1400018a1  mov     rsi, rdx
0x1400018a4  mov     [rsp+78h+var_38], 0
0x1400018ad  mov     edx, 400h; dwFlags
0x1400018b2  mov     [rax-58h], rbx
0x1400018b6  mov     ebp, ecx
0x1400018b8  call    cs:__imp_WideCharToMultiByte
0x1400018be  mov     dword ptr [rsp+78h+var_38], eax
0x1400018c2  test    eax, eax
0x1400018c4  jnz     short loc_1400018CE
0x1400018c6  call    cs:__imp_GetLastError
0x1400018cc  jmp     short loc_1400018D0
0x1400018ce  xor     eax, eax
0x1400018d0  mov     dword ptr [rsp+78h+var_38+4], eax
0x1400018d4  cmp     eax, 3ECh
0x1400018d9  jnz     short loc_140001923
0x1400018db  mov     [rsp+78h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1400018e4  mov     r9d, edi; cchWideChar
0x1400018e7  mov     [rsp+78h+lpDefaultChar], 0; lpDefaultChar
0x1400018f0  mov     r8, rsi; lpWideCharStr
0x1400018f3  mov     [rsp+78h+cbMultiByte], r14d; cbMultiByte
0x1400018f8  xor     edx, edx; dwFlags
0x1400018fa  mov     ecx, ebp; CodePage
0x1400018fc  mov     [rsp+78h+lpMultiByteStr], rbx; lpMultiByteStr
0x140001901  call    cs:__imp_WideCharToMultiByte
0x140001907  mov     dword ptr [rsp+78h+var_38], eax
0x14000190b  test    eax, eax
0x14000190d  jnz     short loc_14000191B
0x14000190f  call    cs:__imp_GetLastError
0x140001915  mov     dword ptr [rsp+78h+var_38+4], eax
0x140001919  jmp     short loc_140001923
0x14000191b  mov     dword ptr [rsp+78h+var_38+4], 0
0x140001923  mov     rax, [rsp+78h+var_38]
0x140001928  add     rsp, 50h
0x14000192c  pop     r14
0x14000192e  pop     rdi
0x14000192f  pop     rsi
0x140001930  pop     rbp
0x140001931  pop     rbx
0x140001932  retn
```
