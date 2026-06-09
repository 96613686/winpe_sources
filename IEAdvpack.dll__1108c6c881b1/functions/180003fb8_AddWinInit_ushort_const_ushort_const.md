# AddWinInit(ushort const *,ushort const *)

- ea: `0x180003fb8`
- end: `0x1800040b4`
- name: `?AddWinInit@@YAHPEBG0@Z`
- size: `252`
- prototype: `__int64 __fastcall(LPCWSTR lpString, LPCWSTR lpKeyName)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18000a918`

## callees

- `0x180003fb8`
- `0x180008a6c`
- `0x18001a688`
- `0x18001b294`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180004092`
- `KERNEL32!LocalFree` at `0x180004092`
- `KERNEL32!GetWindowsDirectoryW` at `0x18000401e`
- `KERNEL32!GetWindowsDirectoryW` at `0x18000401e`
- `KERNEL32!WritePrivateProfileStringW` at `0x18000405a`
- `KERNEL32!WritePrivateProfileStringW` at `0x180004070`
- `KERNEL32!WritePrivateProfileStringW` at `0x180004089`
- `KERNEL32!WritePrivateProfileStringW` at `0x18000405a`
- `KERNEL32!WritePrivateProfileStringW` at `0x180004070`
- `KERNEL32!WritePrivateProfileStringW` at `0x180004089`
- `KERNEL32!LocalAlloc` at `0x180003fe2`
- `KERNEL32!LocalAlloc` at `0x180003fe2`
- `KERNEL32!MoveFileExW` at `0x1800040a0`
- `KERNEL32!MoveFileExW` at `0x1800040a0`

## string_xrefs

- `0x180004063`: `Rename`

## pseudocode

```c
__int64 __fastcall AddWinInit(LPCWSTR lpString, LPCWSTR lpKeyName)
{
  WCHAR *v4; // rax
  WCHAR *v5; // rbx
  unsigned int v7; // edi
  ULONG v8; // [rsp+20h] [rbp-38h]

  if ( ctx )
  {
    return MoveFileExW(lpString, lpKeyName, 5u);
  }
  else
  {
    v4 = (WCHAR *)LocalAlloc(0x40u, 0x208u);
    v5 = v4;
    if ( !v4 )
    {
      MsgBox2Param(0, 0x44Eu, 0, 0, 0x10u, 0);
      return 0;
    }
    GetWindowsDirectoryW(v4, 0x104u);
    PathIsUnc2(L"wininit.ini");
    PathCchCombineEx(v5, 0x104u, v5, L"wininit.ini", v8);
    WritePrivateProfileStringW(0, 0, 0, v5);
    v7 = WritePrivateProfileStringW(L"Rename", lpKeyName, lpString, v5);
    WritePrivateProfileStringW(0, 0, 0, v5);
    LocalFree(v5);
  }
  return v7;
}

```

## disassembly

```asm
0x180003fb8  push    rbx
0x180003fba  push    rsi
0x180003fbb  push    rdi
0x180003fbc  push    r14
0x180003fbe  sub     rsp, 38h
0x180003fc2  xor     r14d, r14d
0x180003fc5  mov     rdi, rdx
0x180003fc8  cmp     cs:?ctx@@3UADVCONTEXTW@@A, r14w; ADVCONTEXTW ctx
0x180003fd0  mov     rsi, rcx
0x180003fd3  jnz     loc_18000409A
0x180003fd9  mov     edx, 208h; uBytes
0x180003fde  lea     ecx, [r14+40h]; uFlags
0x180003fe2  call    cs:__imp_LocalAlloc
0x180003fe8  mov     rbx, rax
0x180003feb  test    rax, rax
0x180003fee  jnz     short loc_180004016
0x180003ff0  mov     [rsp+58h+var_30], r14d; unsigned int
0x180003ff5  xor     r9d, r9d; unsigned __int16 *
0x180003ff8  xor     r8d, r8d; unsigned __int16 *
0x180003ffb  mov     [rsp+58h+var_38], 10h; unsigned int
0x180004003  mov     edx, 44Eh; uID
0x180004008  xor     ecx, ecx; hWnd
0x18000400a  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x18000400f  xor     eax, eax
0x180004011  jmp     loc_1800040AA
0x180004016  mov     edx, 104h; uSize
0x18000401b  mov     rcx, rbx; lpBuffer
0x18000401e  call    cs:__imp_GetWindowsDirectoryW
0x180004024  lea     r8, IsBackslash
0x18000402b  xor     edx, edx
0x18000402d  lea     rcx, pszMore; "wininit.ini"
0x180004034  call    PathIsUnc2
0x180004039  lea     r9, pszMore; "wininit.ini"
0x180004040  mov     r8, rbx; pszPathIn
0x180004043  mov     edx, 104h; cchPathOut
0x180004048  mov     rcx, rbx; pszPathOut
0x18000404b  call    PathCchCombineEx
0x180004050  mov     r9, rbx; lpFileName
0x180004053  xor     r8d, r8d; lpString
0x180004056  xor     edx, edx; lpKeyName
0x180004058  xor     ecx, ecx; lpAppName
0x18000405a  call    cs:__imp_WritePrivateProfileStringW
0x180004060  mov     r9, rbx; lpFileName
0x180004063  lea     rcx, aRename; "Rename"
0x18000406a  mov     r8, rsi; lpString
0x18000406d  mov     rdx, rdi; lpKeyName
0x180004070  call    cs:__imp_WritePrivateProfileStringW
0x180004076  mov     edi, r14d
0x180004079  mov     r9, rbx; lpFileName
0x18000407c  test    eax, eax
0x18000407e  setnz   dil
0x180004082  xor     r8d, r8d; lpString
0x180004085  xor     edx, edx; lpKeyName
0x180004087  xor     ecx, ecx; lpAppName
0x180004089  call    cs:__imp_WritePrivateProfileStringW
0x18000408f  mov     rcx, rbx; hMem
0x180004092  call    cs:__imp_LocalFree
0x180004098  jmp     short loc_1800040A8
0x18000409a  mov     r8d, 5; dwFlags
0x1800040a0  call    cs:__imp_MoveFileExW
0x1800040a6  mov     edi, eax
0x1800040a8  mov     eax, edi
0x1800040aa  add     rsp, 38h
0x1800040ae  pop     r14
0x1800040b0  pop     rdi
0x1800040b1  pop     rsi
0x1800040b2  pop     rbx
0x1800040b3  retn
```
