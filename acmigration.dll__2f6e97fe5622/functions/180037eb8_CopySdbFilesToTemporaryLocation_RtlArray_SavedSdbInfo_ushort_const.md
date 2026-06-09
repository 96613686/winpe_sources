# CopySdbFilesToTemporaryLocation(RtlArray<_SavedSdbInfo> &,ushort const *)

- ea: `0x180037eb8`
- end: `0x1800381f7`
- name: `?CopySdbFilesToTemporaryLocation@@YAJAEAV?$RtlArray@U_SavedSdbInfo@@@@PEBG@Z`
- size: `831`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x1800384a0`

## callees

- `0x180001cf0`
- `0x180037eb8`
- `0x1800385d8`
- `0x18004fec8`
- `0x1800543c0`
- `0x180054934`
- `0x180059f10`
- `0x180060a28`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800380df`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180038119`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800380df`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180038119`
- `KERNEL32!CopyFileW` at `0x18003808f`
- `KERNEL32!CopyFileW` at `0x18003808f`
- `KERNEL32!GetLastError` at `0x18003809d`
- `KERNEL32!GetLastError` at `0x1800381ab`
- `KERNEL32!GetLastError` at `0x18003809d`
- `KERNEL32!GetLastError` at `0x1800381ab`
- `SHLWAPI!PathFindFileNameW` at `0x180038056`
- `SHLWAPI!PathFindFileNameW` at `0x180038056`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180037f24`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180037f69`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180037f24`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180037f69`

## string_xrefs

- `0x180037fb4`: `Failed to ensure temporary directory exists: 0x%x`
- `0x180037fc0`: `CopySdbFilesToTemporaryLocation`
- `0x180038159`: `CopySdbFilesToTemporaryLocation`
- `0x180038148`: `Failed to copy sdb file to temporary location: 0x%x`

## pseudocode

```c
__int64 __fastcall CopySdbFilesToTemporaryLocation(unsigned __int64 *a1, const WCHAR *a2)
{
  __int64 v4; // rdx
  size_t v5; // rdx
  int v6; // ebx
  unsigned __int128 v7; // rax
  int v8; // ebx
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rsi
  __int64 v11; // rbx
  unsigned __int64 v12; // rcx
  const unsigned __int16 *v13; // r8
  const WCHAR *FileNameW; // r14
  size_t v15; // rdx
  size_t v16; // rdx
  signed int LastError; // eax
  bool v18; // sf
  __int64 v19; // r8
  int v20; // eax
  __int64 v21; // r8
  int v22; // eax
  signed int v23; // eax
  ULONG v25; // [rsp+20h] [rbp-E0h]
  __int64 v26; // [rsp+20h] [rbp-E0h]
  __int16 v27; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v28; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszPath[264]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR v31[264]; // [rsp+470h] [rbp+370h] BYREF
  WCHAR NewFileName[264]; // [rsp+680h] [rbp+580h] BYREF
  WCHAR pszPathOut[264]; // [rsp+890h] [rbp+790h] BYREF

  v27 = 0;
  v28 = 0;
  if ( (unsigned int)SdbGetPathCustomSdbPreRS3(pszPath, a2, &v28, 0) )
  {
    if ( PathRemoveFileSpecW(pszPath) )
    {
      v27 = 332;
      v28 = 0;
      if ( (unsigned int)SdbGetPathCustomSdbPreRS3(v31, v4, &v28, &v27) )
      {
        if ( PathRemoveFileSpecW(v31) )
        {
          v6 = PathCchCombineEx(pszPathOut, v5, a2, L"Migrating\\", v25);
          if ( v6 < 0 )
            return (unsigned int)v6;
          v8 = AslPathEnsureDirectory(pszPathOut);
          if ( v8 )
          {
            v6 = v8 | 0x10000000;
            if ( v6 >= 0 )
              v6 = -2147467259;
            LODWORD(v26) = v6;
            AslLogCallPrintf(
              1,
              "CopySdbFilesToTemporaryLocation",
              393,
              "Failed to ensure temporary directory exists: 0x%x",
              v26);
            return (unsigned int)v6;
          }
          v9 = a1[2];
          if ( !v9 )
            return 0;
          v10 = 0;
          while ( 1 )
          {
            v11 = 0;
            if ( v10 < v9 )
            {
              v7 = a1[1] * (unsigned __int128)v10;
              if ( !is_mul_ok(a1[1], v10) || (v12 = a1[5], v11 = v12 + v7, v12 + (unsigned __int64)v7 < v12) )
                v11 = 0;
            }
            if ( !*(_QWORD *)v11 )
              goto LABEL_38;
            v13 = *(const unsigned __int16 **)(v11 + 16);
            if ( !v13 || (int)ExpandDirectory(ExistingFileName, DWORD2(v7), v13) < 0 )
              goto LABEL_38;
            if ( *(_DWORD *)(v11 + 8) )
            {
              *(_DWORD *)(v11 + 24) = 1;
            }
            else
            {
              v19 = -1;
              do
                ++v19;
              while ( pszPath[v19] );
              v20 = _o__wcsnicmp(ExistingFileName, pszPath);
              *(_DWORD *)(v11 + 24) = v20 == 0;
              if ( v20 )
              {
                v21 = -1;
                do
                  ++v21;
                while ( v31[v21] );
                v22 = _o__wcsnicmp(ExistingFileName, v31);
                *(_DWORD *)(v11 + 24) = v22 == 0;
                if ( v22 )
                {
                  AslStringDuplicate(v11 + 32, *(_QWORD *)(v11 + 16));
                  goto LABEL_38;
                }
              }
            }
            FileNameW = PathFindFileNameW(ExistingFileName);
            if ( PathCchCombineEx(NewFileName, v15, pszPathOut, FileNameW, v26) >= 0 )
            {
              if ( CopyFileW(ExistingFileName, NewFileName, 1) )
                goto LABEL_36;
              LastError = GetLastError();
              v18 = LastError < 0;
              if ( LastError > 0 )
              {
                LastError = (unsigned __int16)LastError | 0x80070000;
                v18 = LastError < 0;
              }
              if ( v18 )
              {
                if ( LastError == -2147024816 )
                {
LABEL_36:
                  if ( PathCchCombineEx(NewFileName, v16, L"Migrating\\", FileNameW, v26) >= 0 )
                    AslStringDuplicate(v11 + 32, NewFileName);
                  goto LABEL_38;
                }
              }
              else
              {
                LastError = -2147467259;
              }
              AslLogCallPrintf(
                1,
                "CopySdbFilesToTemporaryLocation",
                458,
                "Failed to copy sdb file to temporary location: 0x%x",
                LastError);
            }
LABEL_38:
            v9 = a1[2];
            if ( ++v10 >= v9 )
              return 0;
          }
        }
      }
    }
  }
  v23 = GetLastError();
  v6 = v23;
  if ( v23 > 0 )
    v6 = (unsigned __int16)v23 | 0x80070000;
  if ( v6 >= 0 )
    return (unsigned int)-2147467259;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180037eb8  mov     [rsp-8+arg_10], rbx
0x180037ebd  mov     [rsp-8+arg_18], rsi
0x180037ec2  push    rbp
0x180037ec3  push    rdi
0x180037ec4  push    r12
0x180037ec6  push    r14
0x180037ec8  push    r15
0x180037eca  lea     rbp, [rsp-9B0h]
0x180037ed2  sub     rsp, 0AB0h
0x180037ed9  mov     rax, cs:__security_cookie
0x180037ee0  xor     rax, rsp
0x180037ee3  mov     [rbp+9D0h+var_30], rax
0x180037eea  mov     r15, rcx
0x180037eed  lea     r8, [rsp+0AD0h+var_A98]
0x180037ef2  xorps   xmm0, xmm0
0x180037ef5  lea     rcx, [rbp+9D0h+pszPath]
0x180037efc  xor     r12d, r12d
0x180037eff  xor     r9d, r9d
0x180037f02  mov     [rsp+0AD0h+var_AA0], r12w
0x180037f08  mov     rbx, rdx
0x180037f0b  movups  [rsp+0AD0h+var_A98], xmm0
0x180037f10  call    SdbGetPathCustomSdbPreRS3
0x180037f15  test    eax, eax
0x180037f17  jz      loc_1800381AB
0x180037f1d  lea     rcx, [rbp+9D0h+pszPath]; pszPath
0x180037f24  call    cs:__imp_PathRemoveFileSpecW
0x180037f2a  test    eax, eax
0x180037f2c  jz      loc_1800381AB
0x180037f32  mov     eax, 14Ch
0x180037f37  lea     r9, [rsp+0AD0h+var_AA0]
0x180037f3c  xorps   xmm0, xmm0
0x180037f3f  mov     [rsp+0AD0h+var_AA0], ax
0x180037f44  lea     r8, [rsp+0AD0h+var_A98]
0x180037f49  lea     rcx, [rbp+9D0h+var_660]
0x180037f50  movups  [rsp+0AD0h+var_A98], xmm0
0x180037f55  call    SdbGetPathCustomSdbPreRS3
0x180037f5a  test    eax, eax
0x180037f5c  jz      loc_1800381AB
0x180037f62  lea     rcx, [rbp+9D0h+var_660]; pszPath
0x180037f69  call    cs:__imp_PathRemoveFileSpecW
0x180037f6f  test    eax, eax
0x180037f71  jz      loc_1800381AB
0x180037f77  lea     r9, pszPathIn; "Migrating\\"
0x180037f7e  mov     r8, rbx; pszPathIn
0x180037f81  lea     rcx, [rbp+9D0h+pszPathOut]; pszPathOut
0x180037f88  call    PathCchCombineEx
0x180037f8d  mov     ebx, eax
0x180037f8f  test    eax, eax
0x180037f91  js      loc_1800381CA
0x180037f97  lea     edx, [r12+1]
0x180037f9c  lea     rcx, [rbp+9D0h+pszPathOut]; lpPathName
0x180037fa3  call    AslPathEnsureDirectory
0x180037fa8  mov     ebx, eax
0x180037faa  test    eax, eax
0x180037fac  jz      short loc_180037FE3
0x180037fae  or      ebx, 10000000h
0x180037fb4  lea     r9, aFailedToEnsure; "Failed to ensure temporary directory ex"...
0x180037fbb  mov     edi, 80004005h
0x180037fc0  lea     rdx, aCopysdbfilesto; "CopySdbFilesToTemporaryLocation"
0x180037fc7  cmovge  ebx, edi
0x180037fca  lea     ecx, [r12+1]
0x180037fcf  mov     r8d, 189h
0x180037fd5  mov     [rsp+0AD0h+var_AB0], ebx
0x180037fd9  call    AslLogCallPrintf
0x180037fde  jmp     loc_1800381CA
0x180037fe3  mov     rax, [r15+10h]
0x180037fe7  test    rax, rax
0x180037fea  jz      loc_1800381A6
0x180037ff0  mov     rsi, r12
0x180037ff3  mov     edi, 80004005h
0x180037ff8  mov     rbx, r12
0x180037ffb  cmp     rsi, rax
0x180037ffe  jnb     short loc_18003801C
0x180038000  mov     rax, rsi
0x180038003  mul     qword ptr [r15+8]
0x180038007  test    rdx, rdx
0x18003800a  jnz     short loc_180038019
0x18003800c  mov     rcx, [r15+28h]
0x180038010  lea     rbx, [rcx+rax]
0x180038014  cmp     rbx, rcx
0x180038017  jnb     short loc_18003801C
0x180038019  mov     rbx, r12
0x18003801c  cmp     [rbx], r12
0x18003801f  jz      loc_180038196
0x180038025  mov     r8, [rbx+10h]; unsigned __int16 *
0x180038029  test    r8, r8
0x18003802c  jz      loc_180038196
0x180038032  lea     rcx, [rsp+0AD0h+ExistingFileName]; lpDst
0x180038037  call    ?ExpandDirectory@@YAJPEAGKPEBG@Z; ExpandDirectory(ushort *,ulong,ushort const *)
0x18003803c  test    eax, eax
0x18003803e  js      loc_180038196
0x180038044  cmp     [rbx+8], r12d
0x180038048  jz      short loc_1800380BE
0x18003804a  mov     dword ptr [rbx+18h], 1
0x180038051  lea     rcx, [rsp+0AD0h+ExistingFileName]; pszPath
0x180038056  call    cs:__imp_PathFindFileNameW
0x18003805c  mov     r9, rax; pszMore
0x18003805f  lea     r8, [rbp+9D0h+pszPathOut]; pszPathIn
0x180038066  lea     rcx, [rbp+9D0h+NewFileName]; pszPathOut
0x18003806d  mov     r14, rax
0x180038070  call    PathCchCombineEx
0x180038075  test    eax, eax
0x180038077  js      loc_180038196
0x18003807d  mov     r8d, 1; bFailIfExists
0x180038083  lea     rdx, [rbp+9D0h+NewFileName]; lpNewFileName
0x18003808a  lea     rcx, [rsp+0AD0h+ExistingFileName]; lpExistingFileName
0x18003808f  call    cs:__imp_CopyFileW
0x180038095  test    eax, eax
0x180038097  jnz     loc_18003816C
0x18003809d  call    cs:__imp_GetLastError
0x1800380a3  test    eax, eax
0x1800380a5  jle     short loc_1800380B1
0x1800380a7  movzx   eax, ax
0x1800380aa  or      eax, 80070000h
0x1800380af  test    eax, eax
0x1800380b1  js      loc_180038141
0x1800380b7  mov     eax, edi
0x1800380b9  jmp     loc_180038148
0x1800380be  lea     rax, [rbp+9D0h+pszPath]
0x1800380c5  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800380c9  inc     r8
0x1800380cc  cmp     [rax+r8*2], r12w
0x1800380d1  jnz     short loc_1800380C9
0x1800380d3  lea     rdx, [rbp+9D0h+pszPath]
0x1800380da  lea     rcx, [rsp+0AD0h+ExistingFileName]
0x1800380df  call    cs:__imp__o__wcsnicmp
0x1800380e5  test    eax, eax
0x1800380e7  mov     ecx, r12d
0x1800380ea  setz    cl
0x1800380ed  mov     [rbx+18h], ecx
0x1800380f0  test    eax, eax
0x1800380f2  jz      loc_180038051
0x1800380f8  lea     rax, [rbp+9D0h+var_660]
0x1800380ff  or      r8, 0FFFFFFFFFFFFFFFFh
0x180038103  inc     r8
0x180038106  cmp     [rax+r8*2], r12w
0x18003810b  jnz     short loc_180038103
0x18003810d  lea     rdx, [rbp+9D0h+var_660]
0x180038114  lea     rcx, [rsp+0AD0h+ExistingFileName]
0x180038119  call    cs:__imp__o__wcsnicmp
0x18003811f  test    eax, eax
0x180038121  mov     ecx, r12d
0x180038124  setz    cl
0x180038127  mov     [rbx+18h], ecx
0x18003812a  test    eax, eax
0x18003812c  jz      loc_180038051
0x180038132  mov     rdx, [rbx+10h]
0x180038136  lea     rcx, [rbx+20h]
0x18003813a  call    AslStringDuplicate
0x18003813f  jmp     short loc_180038196
0x180038141  cmp     eax, 80070050h
0x180038146  jz      short loc_18003816C
0x180038148  lea     r9, aFailedToCopySd_1; "Failed to copy sdb file to temporary lo"...
0x18003814f  mov     [rsp+0AD0h+var_AB0], eax
0x180038153  mov     r8d, 1CAh
0x180038159  lea     rdx, aCopysdbfilesto; "CopySdbFilesToTemporaryLocation"
0x180038160  mov     ecx, 1
0x180038165  call    AslLogCallPrintf
0x18003816a  jmp     short loc_180038196
0x18003816c  mov     r9, r14; pszMore
0x18003816f  lea     r8, pszPathIn; "Migrating\\"
0x180038176  lea     rcx, [rbp+9D0h+NewFileName]; pszPathOut
0x18003817d  call    PathCchCombineEx
0x180038182  test    eax, eax
0x180038184  js      short loc_180038196
0x180038186  lea     rcx, [rbx+20h]
0x18003818a  lea     rdx, [rbp+9D0h+NewFileName]
0x180038191  call    AslStringDuplicate
0x180038196  mov     rax, [r15+10h]
0x18003819a  inc     rsi
0x18003819d  cmp     rsi, rax
0x1800381a0  jb      loc_180037FF8
0x1800381a6  mov     ebx, r12d
0x1800381a9  jmp     short loc_1800381CA
0x1800381ab  call    cs:__imp_GetLastError
0x1800381b1  mov     ebx, eax
0x1800381b3  test    eax, eax
0x1800381b5  jle     short loc_1800381C0
0x1800381b7  movzx   ebx, ax
0x1800381ba  or      ebx, 80070000h
0x1800381c0  test    ebx, ebx
0x1800381c2  mov     edi, 80004005h
0x1800381c7  cmovns  ebx, edi
0x1800381ca  mov     eax, ebx
0x1800381cc  mov     rcx, [rbp+9D0h+var_30]
0x1800381d3  xor     rcx, rsp; StackCookie
0x1800381d6  call    __security_check_cookie
0x1800381db  lea     r11, [rsp+0AD0h+var_20]
0x1800381e3  mov     rbx, [r11+40h]
0x1800381e7  mov     rsi, [r11+48h]
0x1800381eb  mov     rsp, r11
0x1800381ee  pop     r15
0x1800381f0  pop     r14
0x1800381f2  pop     r12
0x1800381f4  pop     rdi
0x1800381f5  pop     rbp
0x1800381f6  retn
```
