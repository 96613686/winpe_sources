# UpdateRefCount(HWND__ *,ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x180016c0c`
- end: `0x180016e35`
- name: `?UpdateRefCount@@YAJPEAUHWND__@@PEBG11K@Z`
- size: `553`
- prototype: `__int64 __fastcall(HWND, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, __int16)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x1800171b0`

## callees

- `0x180003180`
- `0x180015c74`
- `0x180015e48`
- `0x180016c0c`
- `0x180017fdc`
- `0x18001b980`

## import_xrefs

- `msvcrt!_ultow_s` at `0x180016da5`
- `msvcrt!_ultow_s` at `0x180016da5`
- `msvcrt!_wtol` at `0x180016d08`
- `msvcrt!_wtol` at `0x180016d08`
- `USER32!CharNextW` at `0x180016d4f`
- `USER32!CharNextW` at `0x180016d4f`
- `KERNEL32!WritePrivateProfileStringW` at `0x180016dd9`
- `KERNEL32!WritePrivateProfileStringW` at `0x180016dd9`
- `KERNEL32!GetFileAttributesW` at `0x180016c89`
- `KERNEL32!GetFileAttributesW` at `0x180016c89`
- `KERNEL32!GetPrivateProfileStringW` at `0x180016cd1`
- `KERNEL32!GetPrivateProfileStringW` at `0x180016cd1`
- `KERNEL32!SetFileAttributesW` at `0x180016c9c`
- `KERNEL32!SetFileAttributesW` at `0x180016e07`
- `KERNEL32!SetFileAttributesW` at `0x180016c9c`
- `KERNEL32!SetFileAttributesW` at `0x180016e07`
- `SHLWAPI!StrChrW` at `0x180016d41`
- `SHLWAPI!StrChrW` at `0x180016d41`
- `SHLWAPI!PathFileExistsW` at `0x180016c76`
- `SHLWAPI!PathFileExistsW` at `0x180016c76`

## pseudocode

```c
__int64 __fastcall UpdateRefCount(
        HWND a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        __int16 a5)
{
  const WCHAR *v5; // rbx
  DWORD FileAttributesW; // r14d
  unsigned int RefCountFrReg; // esi
  WCHAR *v8; // rax
  int v9; // edi
  const WCHAR *v10; // rax
  __int64 v11; // rax
  WCHAR pszPath[264]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t String[264]; // [rsp+240h] [rbp+140h] BYREF
  WCHAR ReturnedString[1024]; // [rsp+450h] [rbp+350h] BYREF

  v5 = a2;
  if ( a2 )
  {
    if ( *a2 )
    {
      BuildPath(pszPath, a2, a3, a4);
      StringCchCatW(pszPath, 260, L".INI");
      if ( PathFileExistsW(pszPath) )
      {
        FileAttributesW = GetFileAttributesW(pszPath);
        SetFileAttributesW(pszPath, 0x80u);
        while ( *v5 )
        {
          if ( GetPrivateProfileStringW(L"backup", v5, &word_18001DE6C, ReturnedString, 0x400u, pszPath) )
          {
            if ( !(unsigned int)GetFieldString(ReturnedString, 6, String, 260)
              || (RefCountFrReg = _wtol(String), RefCountFrReg == -1) )
            {
              RefCountFrReg = GetRefCountFrReg(v5);
            }
            else if ( (a5 & 0x800) != 0 )
            {
              ++RefCountFrReg;
            }
            v8 = ReturnedString;
            v9 = 0;
            while ( 1 )
            {
              v10 = StrChrW(v8, 0x2Cu);
              if ( !v10 )
                break;
              v8 = CharNextW(v10);
              if ( ++v9 >= 6 )
              {
                if ( v8 )
                {
                  v8[1] = 48;
                  goto LABEL_18;
                }
                break;
              }
            }
            if ( (unsigned int)v9 < 6 )
            {
              do
              {
                StringCchCatW(ReturnedString, 1024, L",");
                ++v9;
              }
              while ( v9 < 6 );
            }
LABEL_18:
            _ultow_s(RefCountFrReg, String, 0x104u, 10);
            StringCchCatW(ReturnedString, 1024, String);
            WritePrivateProfileStringW(L"backup", v5, ReturnedString, pszPath);
          }
          v11 = -1;
          do
            ++v11;
          while ( v5[v11] );
          v5 += v11 + 1;
        }
        SetFileAttributesW(pszPath, FileAttributesW);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180016c0c  mov     [rsp-8+arg_0], rbx
0x180016c11  push    rbp
0x180016c12  push    rsi
0x180016c13  push    rdi
0x180016c14  push    r14
0x180016c16  push    r15
0x180016c18  lea     rbp, [rsp-0B60h]
0x180016c20  sub     rsp, 0C60h
0x180016c27  mov     rax, cs:__security_cookie
0x180016c2e  xor     rax, rsp
0x180016c31  mov     [rbp+0B80h+var_30], rax
0x180016c38  xor     r15d, r15d
0x180016c3b  mov     rbx, rdx
0x180016c3e  test    rdx, rdx
0x180016c41  jz      loc_180016E0D
0x180016c47  cmp     [rdx], r15w
0x180016c4b  jz      loc_180016E0D
0x180016c51  lea     rcx, [rsp+0C80h+pszPath]
0x180016c56  call    BuildPath
0x180016c5b  lea     r8, aIni_0; ".INI"
0x180016c62  mov     edx, 104h; unsigned __int64
0x180016c67  lea     rcx, [rsp+0C80h+pszPath]; unsigned __int16 *
0x180016c6c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180016c71  lea     rcx, [rsp+0C80h+pszPath]; pszPath
0x180016c76  call    cs:__imp_PathFileExistsW
0x180016c7c  test    eax, eax
0x180016c7e  jz      loc_180016E0D
0x180016c84  lea     rcx, [rsp+0C80h+pszPath]; lpFileName
0x180016c89  call    cs:__imp_GetFileAttributesW
0x180016c8f  mov     edx, 80h; dwFileAttributes
0x180016c94  lea     rcx, [rsp+0C80h+pszPath]; lpFileName
0x180016c99  mov     r14d, eax
0x180016c9c  call    cs:__imp_SetFileAttributesW
0x180016ca2  jmp     loc_180016DF5
0x180016ca7  lea     rax, [rsp+0C80h+pszPath]
0x180016cac  mov     rdx, rbx; lpKeyName
0x180016caf  mov     [rsp+0C80h+lpFileName], rax; lpFileName
0x180016cb4  lea     r9, [rbp+0B80h+ReturnedString]; lpReturnedString
0x180016cbb  lea     r8, word_18001DE6C; lpDefault
0x180016cc2  mov     [rsp+0C80h+nSize], 400h; nSize
0x180016cca  lea     rcx, c_szIE4SECTIONNAME; "backup"
0x180016cd1  call    cs:__imp_GetPrivateProfileStringW
0x180016cd7  test    eax, eax
0x180016cd9  jz      loc_180016DDF
0x180016cdf  mov     r9d, 104h; int
0x180016ce5  lea     r8, [rbp+0B80h+String]; unsigned __int16 *
0x180016cec  mov     edx, 6; int
0x180016cf1  lea     rcx, [rbp+0B80h+ReturnedString]; unsigned __int16 *
0x180016cf8  call    ?GetFieldString@@YAHPEBGHPEAGH@Z; GetFieldString(ushort const *,int,ushort *,int)
0x180016cfd  test    eax, eax
0x180016cff  jz      short loc_180016D25
0x180016d01  lea     rcx, [rbp+0B80h+String]; String
0x180016d08  call    cs:__imp__wtol
0x180016d0e  mov     esi, eax
0x180016d10  cmp     eax, 0FFFFFFFFh
0x180016d13  jz      short loc_180016D25
0x180016d15  test    [rbp+0B80h+arg_20], 800h
0x180016d1f  jz      short loc_180016D2F
0x180016d21  inc     esi
0x180016d23  jmp     short loc_180016D2F
0x180016d25  mov     rcx, rbx; lpValueName
0x180016d28  call    ?GetRefCountFrReg@@YAKPEBG@Z; GetRefCountFrReg(ushort const *)
0x180016d2d  mov     esi, eax
0x180016d2f  lea     rax, [rbp+0B80h+ReturnedString]
0x180016d36  mov     edi, r15d
0x180016d39  mov     edx, 2Ch ; ','; wMatch
0x180016d3e  mov     rcx, rax; pszStart
0x180016d41  call    cs:__imp_StrChrW
0x180016d47  test    rax, rax
0x180016d4a  jz      short loc_180016D6C
0x180016d4c  mov     rcx, rax; lpsz
0x180016d4f  call    cs:__imp_CharNextW
0x180016d55  inc     edi
0x180016d57  cmp     edi, 6
0x180016d5a  jl      short loc_180016D39
0x180016d5c  test    rax, rax
0x180016d5f  jz      short loc_180016D6C
0x180016d61  mov     ecx, 30h ; '0'
0x180016d66  mov     [rax+2], cx
0x180016d6a  jmp     short loc_180016D90
0x180016d6c  cmp     edi, 6
0x180016d6f  jnb     short loc_180016D90
0x180016d71  lea     r8, asc_18001E134; ","
0x180016d78  mov     edx, 400h; unsigned __int64
0x180016d7d  lea     rcx, [rbp+0B80h+ReturnedString]; unsigned __int16 *
0x180016d84  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180016d89  inc     edi
0x180016d8b  cmp     edi, 6
0x180016d8e  jl      short loc_180016D71
0x180016d90  mov     r9d, 0Ah; Radix
0x180016d96  lea     rdx, [rbp+0B80h+String]; Buffer
0x180016d9d  mov     r8d, 104h; BufferCount
0x180016da3  mov     ecx, esi; Value
0x180016da5  call    cs:__imp__ultow_s
0x180016dab  lea     r8, [rbp+0B80h+String]; unsigned __int16 *
0x180016db2  mov     edx, 400h; unsigned __int64
0x180016db7  lea     rcx, [rbp+0B80h+ReturnedString]; unsigned __int16 *
0x180016dbe  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180016dc3  lea     r9, [rsp+0C80h+pszPath]; lpFileName
0x180016dc8  mov     rdx, rbx; lpKeyName
0x180016dcb  lea     r8, [rbp+0B80h+ReturnedString]; lpString
0x180016dd2  lea     rcx, c_szIE4SECTIONNAME; "backup"
0x180016dd9  call    cs:__imp_WritePrivateProfileStringW
0x180016ddf  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016de3  inc     rax
0x180016de6  cmp     [rbx+rax*2], r15w
0x180016deb  jnz     short loc_180016DE3
0x180016ded  lea     rbx, [rbx+rax*2]
0x180016df1  add     rbx, 2
0x180016df5  cmp     [rbx], r15w
0x180016df9  jnz     loc_180016CA7
0x180016dff  mov     edx, r14d; dwFileAttributes
0x180016e02  lea     rcx, [rsp+0C80h+pszPath]; lpFileName
0x180016e07  call    cs:__imp_SetFileAttributesW
0x180016e0d  xor     eax, eax
0x180016e0f  mov     rcx, [rbp+0B80h+var_30]
0x180016e16  xor     rcx, rsp; StackCookie
0x180016e19  call    __security_check_cookie
0x180016e1e  mov     rbx, [rsp+0C80h+arg_0]
0x180016e26  add     rsp, 0C60h
0x180016e2d  pop     r15
0x180016e2f  pop     r14
0x180016e31  pop     rdi
0x180016e32  pop     rsi
0x180016e33  pop     rbp
0x180016e34  retn
```
