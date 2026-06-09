# GetUniBackupName(HKEY__ *,ushort *,ulong,ushort const *,ushort const *)

- ea: `0x18000ced8`
- end: `0x18000d17b`
- name: `?GetUniBackupName@@YAHPEAUHKEY__@@PEAGKPEBG2@Z`
- size: `675`
- prototype: `__int64 __fastcall(HKEY, unsigned __int16 *, __int64, const unsigned __int16 *, unsigned __int16 *pszMore)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18000e060`

## callees

- `0x1800022bc`
- `0x180003180`
- `0x1800035c8`
- `0x18000ced8`
- `0x1800198d0`
- `0x18001a688`
- `0x18001b294`
- `0x18001b980`

## import_xrefs

- `USER32!CharNextW` at `0x18000cf77`
- `USER32!CharNextW` at `0x18000cf77`
- `KERNEL32!CompareStringW` at `0x18000cfc4`
- `KERNEL32!CompareStringW` at `0x18000cfc4`
- `ADVAPI32!RegQueryValueExW` at `0x18000cf4e`
- `ADVAPI32!RegQueryValueExW` at `0x18000cf4e`
- `SHLWAPI!StrRChrW` at `0x18000cf69`
- `SHLWAPI!StrRChrW` at `0x18000cf96`
- `SHLWAPI!StrRChrW` at `0x18000cf69`
- `SHLWAPI!StrRChrW` at `0x18000cf96`
- `SHLWAPI!PathFileExistsW` at `0x18000d055`
- `SHLWAPI!PathFileExistsW` at `0x18000d124`
- `SHLWAPI!PathFileExistsW` at `0x18000d055`
- `SHLWAPI!PathFileExistsW` at `0x18000d124`

## pseudocode

```c
__int64 __fastcall GetUniBackupName(
        HKEY a1,
        unsigned __int16 *a2,
        __int64 a3,
        const unsigned __int16 *a4,
        unsigned __int16 *pszMore)
{
  const unsigned __int16 *v5; // r12
  const WCHAR *v7; // rax
  const unsigned __int16 *v8; // rax
  PWSTR v9; // rdi
  unsigned int v10; // esi
  const unsigned __int16 *v11; // rbx
  const unsigned __int16 *v12; // r8
  signed int i; // r15d
  const WCHAR *v14; // r12
  ULONG lpData; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  const unsigned __int16 *v18; // [rsp+38h] [rbp-C8h]
  WCHAR pszPathOut[264]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE Data[2]; // [rsp+250h] [rbp+150h] BYREF
  __int16 v21; // [rsp+456h] [rbp+356h]

  v21 = 0;
  v5 = a4;
  v18 = a4;
  cbData = 518;
  if ( RegQueryValueExW(a1, L"BackupFileName", 0, 0, Data, &cbData) || (v7 = StrRChrW((PCWSTR)Data, 0, 0x5Cu)) == 0 )
  {
    StringCchCopyW(pszPathOut, 0x104u, v5);
    v11 = pszMore;
    if ( pszMore && !(unsigned int)PathIsUnc2(pszMore) && !IsExtendedLengthDosDevicePath(pszMore) && *pszMore == 92 )
    {
      do
        ++v11;
      while ( *v11 == 92 );
    }
    PathCchCombineEx(pszPathOut, 0x104u, pszPathOut, v11, lpData);
    StringCchCatW(pszPathOut, 0x104u, L".dat");
    if ( PathFileExistsW(pszPathOut) )
    {
      v10 = 0;
      for ( i = 1; i < 999; ++i )
      {
        StringCchPrintfW((unsigned __int16 *)Data, 0x104u, L"%s.%03d", pszMore);
        StringCchCopyW(pszPathOut, 0x104u, v5);
        v14 = (const WCHAR *)Data;
        if ( !(unsigned int)PathIsUnc2((unsigned __int16 *)Data)
          && !IsExtendedLengthDosDevicePath((const unsigned __int16 *)Data)
          && *(_WORD *)Data == 92 )
        {
          do
            ++v14;
          while ( *v14 == 92 );
        }
        PathCchCombineEx(pszPathOut, 0x104u, pszPathOut, v14, i);
        StringCchCatW(pszPathOut, 0x104u, L".dat");
        if ( !PathFileExistsW(pszPathOut) )
        {
          v10 = 1;
          v12 = (const unsigned __int16 *)Data;
          goto LABEL_23;
        }
        v5 = v18;
      }
    }
    else
    {
      v10 = 1;
      v12 = pszMore;
LABEL_23:
      StringCchCopyW(a2, 0x104u, v12);
    }
  }
  else
  {
    v8 = CharNextW(v7);
    StringCchCopyW(a2, 0x104u, v8);
    v9 = StrRChrW(a2, 0, 0x2Eu);
    if ( v9 && CompareStringW(0x7Fu, 1u, v9, -1, L".dat", -1) == 2 )
      *v9 = 0;
    return 1;
  }
  return v10;
}

```

## disassembly

```asm
0x18000ced8  mov     [rsp-8+arg_10], rbx
0x18000cedd  push    rbp
0x18000cede  push    rsi
0x18000cedf  push    rdi
0x18000cee0  push    r12
0x18000cee2  push    r13
0x18000cee4  push    r14
0x18000cee6  push    r15
0x18000cee8  lea     rbp, [rsp-370h]
0x18000cef0  sub     rsp, 470h
0x18000cef7  mov     rax, cs:__security_cookie
0x18000cefe  xor     rax, rsp
0x18000cf01  mov     [rbp+3A0h+var_40], rax
0x18000cf08  mov     r14, [rbp+3A0h+pszMore]
0x18000cf0f  xor     eax, eax
0x18000cf11  mov     [rbp+3A0h+var_4A], ax
0x18000cf18  mov     r12, r9
0x18000cf1b  lea     rax, [rsp+4A0h+cbData]
0x18000cf20  mov     [rsp+4A0h+var_468], r9
0x18000cf25  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x18000cf2a  mov     r13, rdx
0x18000cf2d  lea     rax, [rbp+3A0h+Data]
0x18000cf34  mov     [rsp+4A0h+cbData], 206h
0x18000cf3c  xor     r9d, r9d; lpType
0x18000cf3f  mov     [rsp+4A0h+lpData], rax; dwFlags
0x18000cf44  xor     r8d, r8d; lpReserved
0x18000cf47  lea     rdx, aBackupfilename; "BackupFileName"
0x18000cf4e  call    cs:__imp_RegQueryValueExW
0x18000cf54  mov     esi, 5Ch ; '\'
0x18000cf59  test    eax, eax
0x18000cf5b  jnz     short loc_18000CFDB
0x18000cf5d  mov     r8d, esi; wMatch
0x18000cf60  lea     rcx, [rbp+3A0h+Data]; pszStart
0x18000cf67  xor     edx, edx; pszEnd
0x18000cf69  call    cs:__imp_StrRChrW
0x18000cf6f  test    rax, rax
0x18000cf72  jz      short loc_18000CFDB
0x18000cf74  mov     rcx, rax; lpsz
0x18000cf77  call    cs:__imp_CharNextW
0x18000cf7d  mov     edx, 104h; unsigned __int64
0x18000cf82  mov     rcx, r13; unsigned __int16 *
0x18000cf85  mov     r8, rax; unsigned __int16 *
0x18000cf88  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000cf8d  xor     edx, edx; pszEnd
0x18000cf8f  lea     r8d, [rsi-2Eh]; wMatch
0x18000cf93  mov     rcx, r13; pszStart
0x18000cf96  call    cs:__imp_StrRChrW
0x18000cf9c  lea     ebx, [rsi-5Bh]
0x18000cf9f  mov     rdi, rax
0x18000cfa2  test    rax, rax
0x18000cfa5  jz      short loc_18000CFD4
0x18000cfa7  or      r9d, 0FFFFFFFFh; cchCount1
0x18000cfab  lea     rax, aDat_0; ".dat"
0x18000cfb2  mov     dword ptr [rsp+4A0h+lpcbData], r9d; cchCount2
0x18000cfb7  lea     ecx, [rsi+23h]; Locale
0x18000cfba  mov     r8, rdi; lpString1
0x18000cfbd  mov     [rsp+4A0h+lpData], rax; lpString2
0x18000cfc2  mov     edx, ebx; dwCmpFlags
0x18000cfc4  call    cs:__imp_CompareStringW
0x18000cfca  cmp     eax, 2
0x18000cfcd  jnz     short loc_18000CFD4
0x18000cfcf  xor     eax, eax
0x18000cfd1  mov     [rdi], ax
0x18000cfd4  mov     esi, ebx
0x18000cfd6  jmp     loc_18000D14F
0x18000cfdb  mov     edi, 104h
0x18000cfe0  lea     rcx, [rsp+4A0h+pszPathOut]; unsigned __int16 *
0x18000cfe5  mov     edx, edi; unsigned __int64
0x18000cfe7  mov     r8, r12; unsigned __int16 *
0x18000cfea  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000cfef  mov     rbx, r14
0x18000cff2  test    r14, r14
0x18000cff5  jz      short loc_18000D027
0x18000cff7  lea     r8, IsBackslash
0x18000cffe  xor     edx, edx
0x18000d000  mov     rcx, r14; unsigned __int16 *
0x18000d003  call    PathIsUnc2
0x18000d008  test    eax, eax
0x18000d00a  jnz     short loc_18000D027
0x18000d00c  mov     rcx, r14; unsigned __int16 *
0x18000d00f  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x18000d014  test    al, al
0x18000d016  jnz     short loc_18000D027
0x18000d018  cmp     [r14], si
0x18000d01c  jnz     short loc_18000D027
0x18000d01e  add     rbx, 2
0x18000d022  cmp     [rbx], si
0x18000d025  jz      short loc_18000D01E
0x18000d027  mov     r9, rbx; pszMore
0x18000d02a  lea     r8, [rsp+4A0h+pszPathOut]; pszPathIn
0x18000d02f  mov     rdx, rdi; cchPathOut
0x18000d032  lea     rcx, [rsp+4A0h+pszPathOut]; pszPathOut
0x18000d037  call    PathCchCombineEx
0x18000d03c  lea     r8, aDat_0; ".dat"
0x18000d043  mov     rdx, rdi; unsigned __int64
0x18000d046  lea     rcx, [rsp+4A0h+pszPathOut]; unsigned __int16 *
0x18000d04b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d050  lea     rcx, [rsp+4A0h+pszPathOut]; pszPath
0x18000d055  call    cs:__imp_PathFileExistsW
0x18000d05b  test    eax, eax
0x18000d05d  jnz     short loc_18000D06A
0x18000d05f  lea     esi, [rax+1]
0x18000d062  mov     r8, r14
0x18000d065  jmp     loc_18000D144
0x18000d06a  xor     esi, esi
0x18000d06c  lea     ebx, [rsi+1]
0x18000d06f  mov     r15d, ebx
0x18000d072  cmp     r15d, 3E7h
0x18000d079  jge     loc_18000D14F
0x18000d07f  mov     r9, r14
0x18000d082  mov     dword ptr [rsp+4A0h+lpData], r15d; dwFlags
0x18000d087  lea     r8, aS03d; "%s.%03d"
0x18000d08e  mov     rdx, rdi; unsigned __int64
0x18000d091  lea     rcx, [rbp+3A0h+Data]; unsigned __int16 *
0x18000d098  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d09d  mov     r8, r12; unsigned __int16 *
0x18000d0a0  lea     rcx, [rsp+4A0h+pszPathOut]; unsigned __int16 *
0x18000d0a5  mov     rdx, rdi; unsigned __int64
0x18000d0a8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d0ad  lea     r8, IsBackslash
0x18000d0b4  xor     edx, edx
0x18000d0b6  lea     rcx, [rbp+3A0h+Data]; unsigned __int16 *
0x18000d0bd  lea     r12, [rbp+3A0h+Data]
0x18000d0c4  call    PathIsUnc2
0x18000d0c9  test    eax, eax
0x18000d0cb  jnz     short loc_18000D0F6
0x18000d0cd  lea     rcx, [rbp+3A0h+Data]; unsigned __int16 *
0x18000d0d4  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x18000d0d9  test    al, al
0x18000d0db  jnz     short loc_18000D0F6
0x18000d0dd  mov     eax, 5Ch ; '\'
0x18000d0e2  cmp     word ptr [rbp+3A0h+Data], ax
0x18000d0e9  jnz     short loc_18000D0F6
0x18000d0eb  add     r12, 2
0x18000d0ef  cmp     [r12], ax
0x18000d0f4  jz      short loc_18000D0EB
0x18000d0f6  mov     r9, r12; pszMore
0x18000d0f9  lea     r8, [rsp+4A0h+pszPathOut]; pszPathIn
0x18000d0fe  mov     rdx, rdi; cchPathOut
0x18000d101  lea     rcx, [rsp+4A0h+pszPathOut]; pszPathOut
0x18000d106  call    PathCchCombineEx
0x18000d10b  lea     r8, aDat_0; ".dat"
0x18000d112  mov     rdx, rdi; unsigned __int64
0x18000d115  lea     rcx, [rsp+4A0h+pszPathOut]; unsigned __int16 *
0x18000d11a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d11f  lea     rcx, [rsp+4A0h+pszPathOut]; pszPath
0x18000d124  call    cs:__imp_PathFileExistsW
0x18000d12a  test    eax, eax
0x18000d12c  jz      short loc_18000D13B
0x18000d12e  mov     r12, [rsp+4A0h+var_468]
0x18000d133  add     r15d, ebx
0x18000d136  jmp     loc_18000D072
0x18000d13b  mov     esi, ebx
0x18000d13d  lea     r8, [rbp+3A0h+Data]; unsigned __int16 *
0x18000d144  mov     rdx, rdi; unsigned __int64
0x18000d147  mov     rcx, r13; unsigned __int16 *
0x18000d14a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d14f  mov     eax, esi
0x18000d151  mov     rcx, [rbp+3A0h+var_40]
0x18000d158  xor     rcx, rsp; StackCookie
0x18000d15b  call    __security_check_cookie
0x18000d160  mov     rbx, [rsp+4A0h+arg_10]
0x18000d168  add     rsp, 470h
0x18000d16f  pop     r15
0x18000d171  pop     r14
0x18000d173  pop     r13
0x18000d175  pop     r12
0x18000d177  pop     rdi
0x18000d178  pop     rsi
0x18000d179  pop     rbp
0x18000d17a  retn
```
