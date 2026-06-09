# __std_fs_convert_wide_to_narrow_replace_chars

- ea: `0x18000187c`
- end: `0x180001943`
- name: `__std_fs_convert_wide_to_narrow_replace_chars`
- size: `199`
- prototype: `__int64 __fastcall(UINT CodePage, LPCWCH lpWideCharStr, int cchWideChar, LPSTR lpMultiByteStr, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800079f4`

## callees

- `0x18000187c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800018d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000191f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800018d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000191f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800018c8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180001911`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800018c8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180001911`

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
0x18000187c  mov     rax, rsp
0x18000187f  push    rbx
0x180001880  push    rbp
0x180001881  push    rsi
0x180001882  push    rdi
0x180001883  push    r14
0x180001885  sub     rsp, 50h
0x180001889  mov     r14d, [rsp+78h+arg_20]
0x180001891  mov     rbx, r9
0x180001894  mov     qword ptr [rax-40h], 0
0x18000189c  mov     r9d, r8d; cchWideChar
0x18000189f  mov     qword ptr [rax-48h], 0
0x1800018a7  mov     edi, r8d
0x1800018aa  mov     r8, rdx; lpWideCharStr
0x1800018ad  mov     [rax-50h], r14d
0x1800018b1  mov     rsi, rdx
0x1800018b4  mov     [rsp+78h+var_38], 0
0x1800018bd  mov     edx, 400h; dwFlags
0x1800018c2  mov     [rax-58h], rbx
0x1800018c6  mov     ebp, ecx
0x1800018c8  call    cs:__imp_WideCharToMultiByte
0x1800018ce  mov     dword ptr [rsp+78h+var_38], eax
0x1800018d2  test    eax, eax
0x1800018d4  jnz     short loc_1800018DE
0x1800018d6  call    cs:__imp_GetLastError
0x1800018dc  jmp     short loc_1800018E0
0x1800018de  xor     eax, eax
0x1800018e0  mov     dword ptr [rsp+78h+var_38+4], eax
0x1800018e4  cmp     eax, 3ECh
0x1800018e9  jnz     short loc_180001933
0x1800018eb  mov     [rsp+78h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1800018f4  mov     r9d, edi; cchWideChar
0x1800018f7  mov     [rsp+78h+lpDefaultChar], 0; lpDefaultChar
0x180001900  mov     r8, rsi; lpWideCharStr
0x180001903  mov     [rsp+78h+cbMultiByte], r14d; cbMultiByte
0x180001908  xor     edx, edx; dwFlags
0x18000190a  mov     ecx, ebp; CodePage
0x18000190c  mov     [rsp+78h+lpMultiByteStr], rbx; lpMultiByteStr
0x180001911  call    cs:__imp_WideCharToMultiByte
0x180001917  mov     dword ptr [rsp+78h+var_38], eax
0x18000191b  test    eax, eax
0x18000191d  jnz     short loc_18000192B
0x18000191f  call    cs:__imp_GetLastError
0x180001925  mov     dword ptr [rsp+78h+var_38+4], eax
0x180001929  jmp     short loc_180001933
0x18000192b  mov     dword ptr [rsp+78h+var_38+4], 0
0x180001933  mov     rax, [rsp+78h+var_38]
0x180001938  add     rsp, 50h
0x18000193c  pop     r14
0x18000193e  pop     rdi
0x18000193f  pop     rsi
0x180001940  pop     rbp
0x180001941  pop     rbx
0x180001942  retn
```
