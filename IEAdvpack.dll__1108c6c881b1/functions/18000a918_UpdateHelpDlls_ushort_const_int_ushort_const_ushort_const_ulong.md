# UpdateHelpDlls(ushort const * *,int,ushort const *,ushort const *,ulong)

- ea: `0x18000a918`
- end: `0x18000ae60`
- name: `?UpdateHelpDlls@@YAHPEAPEBGHPEBG1K@Z`
- size: `1352`
- prototype: `__int64 __fastcall(const unsigned __int16 **, int, size_t *, const unsigned __int16 *, char)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800088c4`

## callees

- `0x1800022bc`
- `0x180003fb8`
- `0x18000631c`
- `0x180006c80`
- `0x18000a918`
- `0x18000b710`
- `0x1800198d0`
- `0x18001a688`
- `0x18001b294`
- `0x18001b94e`
- `0x18001b980`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x18000aba6`
- `KERNEL32!DeleteFileW` at `0x18000ad2b`
- `KERNEL32!DeleteFileW` at `0x18000ae14`
- `KERNEL32!DeleteFileW` at `0x18000aba6`
- `KERNEL32!DeleteFileW` at `0x18000ad2b`
- `KERNEL32!DeleteFileW` at `0x18000ae14`
- `KERNEL32!GetFileAttributesW` at `0x18000aa93`
- `KERNEL32!GetFileAttributesW` at `0x18000ab12`
- `KERNEL32!GetFileAttributesW` at `0x18000aa93`
- `KERNEL32!GetFileAttributesW` at `0x18000ab12`
- `KERNEL32!GetSystemDirectoryW` at `0x18000a9df`
- `KERNEL32!GetSystemDirectoryW` at `0x18000a9df`
- `KERNEL32!SetFileAttributesW` at `0x18000ab62`
- `KERNEL32!SetFileAttributesW` at `0x18000ab99`
- `KERNEL32!SetFileAttributesW` at `0x18000ac27`
- `KERNEL32!SetFileAttributesW` at `0x18000ad20`
- `KERNEL32!SetFileAttributesW` at `0x18000ae07`
- `KERNEL32!SetFileAttributesW` at `0x18000ab62`
- `KERNEL32!SetFileAttributesW` at `0x18000ab99`
- `KERNEL32!SetFileAttributesW` at `0x18000ac27`
- `KERNEL32!SetFileAttributesW` at `0x18000ad20`
- `KERNEL32!SetFileAttributesW` at `0x18000ae07`
- `KERNEL32!CopyFileW` at `0x18000abd6`
- `KERNEL32!CopyFileW` at `0x18000ac3e`
- `KERNEL32!CopyFileW` at `0x18000abd6`
- `KERNEL32!CopyFileW` at `0x18000ac3e`
- `KERNEL32!MoveFileW` at `0x18000abb8`
- `KERNEL32!MoveFileW` at `0x18000ad3d`
- `KERNEL32!MoveFileW` at `0x18000abb8`
- `KERNEL32!MoveFileW` at `0x18000ad3d`

## pseudocode

```c
__int64 __fastcall UpdateHelpDlls(const unsigned __int16 **a1, int a2, size_t *a3, const unsigned __int16 *a4, char a5)
{
  int v6; // r12d
  __int64 v7; // r14
  __int64 v8; // r15
  unsigned int v10; // esi
  int v11; // r13d
  int i; // edi
  const unsigned __int16 **v13; // rax
  const unsigned __int16 *v14; // rbx
  const unsigned __int16 *v15; // rbx
  unsigned int v16; // edx
  unsigned int v17; // edx
  const unsigned __int16 **v18; // rsi
  unsigned __int16 *v19; // rbx
  unsigned int v20; // edx
  unsigned int v21; // edi
  const unsigned __int16 **v22; // rsi
  unsigned __int16 *v23; // rbx
  unsigned int v24; // edx
  ULONG v25; // [rsp+20h] [rbp-E0h]
  unsigned int v26; // [rsp+30h] [rbp-D0h]
  DWORD v27; // [rsp+34h] [rbp-CCh] BYREF
  DWORD pdwMSVer; // [rsp+38h] [rbp-C8h] BYREF
  DWORD pdwLSVer; // [rsp+3Ch] [rbp-C4h] BYREF
  DWORD v30; // [rsp+40h] [rbp-C0h] BYREF
  int v31; // [rsp+44h] [rbp-BCh]
  const unsigned __int16 **v32; // [rsp+48h] [rbp-B8h]
  __int64 v33; // [rsp+50h] [rbp-B0h]
  int v34; // [rsp+58h] [rbp-A8h]
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR FileName[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR pszPathOut[264]; // [rsp+480h] [rbp+380h] BYREF

  v31 = a2;
  v32 = a1;
  v6 = a2;
  v27 = 0;
  v30 = 0;
  pdwMSVer = 0;
  pdwLSVer = 0;
  memset_0(pszPathOut, 0, 0x208u);
  memset_0(Buffer, 0, 0x208u);
  v33 = 0;
  v34 = 0;
  if ( a3 )
  {
    StringCchCopyW(pszPathOut, 0x104u, a3);
  }
  else if ( !(unsigned int)GetThisModulePath(pszPathOut) )
  {
    return 0;
  }
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( pszPathOut[v8] );
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    return 0;
  v10 = 1;
  v26 = 1;
  v11 = 0;
  do
    ++v7;
  while ( Buffer[v7] );
  for ( i = 0; i < v6; ++i )
  {
    if ( (unsigned __int64)i >= 3 )
    {
      v6 = v31;
      break;
    }
    v13 = v32;
    pszPathOut[v8] = 0;
    Buffer[v7] = 0;
    v14 = v13[i];
    if ( v14 && !(unsigned int)PathIsUnc2((unsigned __int16 *)v13[i]) && !IsExtendedLengthDosDevicePath(v14) )
    {
      while ( *v14 == 92 )
        ++v14;
    }
    PathCchCombineEx(pszPathOut, 0x104u, pszPathOut, v14, v25);
    if ( GetFileAttributesW(pszPathOut) != -1 )
    {
      GetVersionFromFileW(pszPathOut, &pdwMSVer, &pdwLSVer, 1);
      v15 = v32[i];
      if ( v15 && !(unsigned int)PathIsUnc2((unsigned __int16 *)v32[i]) && !IsExtendedLengthDosDevicePath(v15) )
      {
        while ( *v15 == 92 )
          ++v15;
      }
      PathCchCombineEx(Buffer, 0x104u, Buffer, v15, v25);
      if ( GetFileAttributesW(Buffer) != -1 )
      {
        GetVersionFromFileW(Buffer, &v27, &v30, 1);
        if ( v27 > pdwMSVer || v27 == pdwMSVer && v30 >= pdwLSVer )
          goto LABEL_39;
        SetFileAttributesW(Buffer, 0x80u);
        StringCchCopyW(FileName, 0x104u, (size_t *)Buffer);
        GetBackupName(FileName, v16, 1);
        SetFileAttributesW(FileName, 0x80u);
        DeleteFileW(FileName);
        if ( MoveFileW(Buffer, FileName) )
          *((_DWORD *)&v33 + i) = 1;
      }
      if ( !CopyFileW(pszPathOut, Buffer, 0) )
      {
        if ( (a5 & 1) == 0 )
          goto LABEL_41;
        StringCchCopyW(FileName, 0x104u, (size_t *)Buffer);
        GetBackupName(FileName, v17, 0);
        SetFileAttributesW(FileName, 0x80u);
        if ( !CopyFileW(pszPathOut, FileName, 0) || !(unsigned int)AddWinInit(FileName, Buffer) )
        {
          v26 = 0;
          v10 = 0;
LABEL_41:
          if ( i >= 0 )
          {
            v18 = v32;
            do
            {
              if ( *((_DWORD *)&v33 + (unsigned int)i) )
              {
                v19 = (unsigned __int16 *)v18[i];
                Buffer[v7] = 0;
                if ( v19 && !(unsigned int)PathIsUnc2(v19) && !IsExtendedLengthDosDevicePath(v19) )
                {
                  while ( *v19 == 92 )
                    ++v19;
                }
                PathCchCombineEx(Buffer, 0x104u, Buffer, v19, v25);
                StringCchCopyW(FileName, 0x104u, (size_t *)Buffer);
                GetBackupName(FileName, v20, 1);
                SetFileAttributesW(FileName, 0x80u);
                DeleteFileW(Buffer);
                MoveFileW(FileName, Buffer);
              }
              --i;
            }
            while ( i >= 0 );
            return v26;
          }
          return v10;
        }
        if ( (a5 & 2) != 0 )
          v11 = 1;
      }
    }
LABEL_39:
    v6 = v31;
  }
  v21 = 0;
  if ( v6 > 0 )
  {
    v22 = v32;
    do
    {
      if ( v21 >= 3 )
        break;
      if ( *((_DWORD *)&v33 + v21) )
      {
        v23 = (unsigned __int16 *)v22[v21];
        Buffer[v7] = 0;
        if ( v23 && !(unsigned int)PathIsUnc2(v23) && !IsExtendedLengthDosDevicePath(v23) )
        {
          while ( *v23 == 92 )
            ++v23;
        }
        PathCchCombineEx(Buffer, 0x104u, Buffer, v23, v25);
        StringCchCopyW(FileName, 0x104u, (size_t *)Buffer);
        GetBackupName(FileName, v24, 1);
        SetFileAttributesW(FileName, 0x80u);
        DeleteFileW(FileName);
      }
      ++v21;
    }
    while ( (int)v21 < v6 );
    v10 = 1;
  }
  if ( v11 )
    return 0;
  return v10;
}

```

## disassembly

```asm
0x18000a918  mov     [rsp-8+arg_8], rbx
0x18000a91d  push    rbp
0x18000a91e  push    rsi
0x18000a91f  push    rdi
0x18000a920  push    r12
0x18000a922  push    r13
0x18000a924  push    r14
0x18000a926  push    r15
0x18000a928  lea     rbp, [rsp-5A0h]
0x18000a930  sub     rsp, 6A0h
0x18000a937  mov     rax, cs:__security_cookie
0x18000a93e  xor     rax, rsp
0x18000a941  mov     [rbp+5D0h+var_40], rax
0x18000a948  xor     esi, esi
0x18000a94a  mov     [rsp+6D0h+var_68C], edx
0x18000a94e  mov     rbx, r8
0x18000a951  mov     [rsp+6D0h+var_688], rcx
0x18000a956  mov     r12d, edx
0x18000a959  mov     [rsp+6D0h+var_69C], esi
0x18000a95d  mov     edi, 208h
0x18000a962  mov     [rsp+6D0h+var_690], esi
0x18000a966  mov     r8d, edi; Size
0x18000a969  mov     [rsp+6D0h+pdwMSVer], esi
0x18000a96d  xor     edx, edx; Val
0x18000a96f  mov     [rsp+6D0h+pdwLSVer], esi
0x18000a973  lea     rcx, [rbp+5D0h+pszPathOut]; void *
0x18000a97a  call    memset_0
0x18000a97f  mov     r8d, edi; Size
0x18000a982  lea     rcx, [rsp+6D0h+Buffer]; void *
0x18000a987  xor     edx, edx; Val
0x18000a989  call    memset_0
0x18000a98e  xor     eax, eax
0x18000a990  lea     rcx, [rbp+5D0h+pszPathOut]; unsigned __int16 *
0x18000a997  mov     [rsp+6D0h+var_680], rax
0x18000a99c  mov     [rsp+6D0h+var_678], eax
0x18000a9a0  test    rbx, rbx
0x18000a9a3  jnz     short loc_18000A9B0
0x18000a9a5  call    ?GetThisModulePath@@YAHPEAGH@Z; GetThisModulePath(ushort *,int)
0x18000a9aa  test    eax, eax
0x18000a9ac  jz      short loc_18000A9EB
0x18000a9ae  jmp     short loc_18000A9BD
0x18000a9b0  mov     r8, rbx; unsigned __int16 *
0x18000a9b3  mov     edx, 104h; unsigned __int64
0x18000a9b8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a9bd  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000a9c1  lea     rax, [rbp+5D0h+pszPathOut]
0x18000a9c8  mov     r15, r14
0x18000a9cb  inc     r15
0x18000a9ce  cmp     [rax+r15*2], si
0x18000a9d3  jnz     short loc_18000A9CB
0x18000a9d5  mov     edx, 104h; uSize
0x18000a9da  lea     rcx, [rsp+6D0h+Buffer]; lpBuffer
0x18000a9df  call    cs:__imp_GetSystemDirectoryW
0x18000a9e5  xor     edx, edx
0x18000a9e7  test    eax, eax
0x18000a9e9  jnz     short loc_18000A9F2
0x18000a9eb  xor     eax, eax
0x18000a9ed  jmp     loc_18000AE36
0x18000a9f2  mov     eax, 1
0x18000a9f7  lea     rcx, [rsp+6D0h+Buffer]
0x18000a9fc  mov     esi, eax
0x18000a9fe  mov     [rsp+6D0h+var_6A0], eax
0x18000aa02  mov     r13d, edx
0x18000aa05  inc     r14
0x18000aa08  cmp     [rcx+r14*2], dx
0x18000aa0d  jnz     short loc_18000AA05
0x18000aa0f  mov     edi, edx
0x18000aa11  cmp     edi, r12d
0x18000aa14  jge     loc_18000AD5C
0x18000aa1a  movsxd  r12, edi
0x18000aa1d  cmp     r12, 3
0x18000aa21  jnb     loc_18000AD57
0x18000aa27  mov     rax, [rsp+6D0h+var_688]
0x18000aa2c  mov     [rbp+r15*2+5D0h+pszPathOut], dx
0x18000aa35  mov     [rsp+r14*2+6D0h+Buffer], dx
0x18000aa3b  mov     rbx, [rax+r12*8]
0x18000aa3f  test    rbx, rbx
0x18000aa42  jz      short loc_18000AA71
0x18000aa44  lea     r8, IsBackslash
0x18000aa4b  xor     edx, edx
0x18000aa4d  mov     rcx, rbx; unsigned __int16 *
0x18000aa50  call    PathIsUnc2
0x18000aa55  test    eax, eax
0x18000aa57  jnz     short loc_18000AA71
0x18000aa59  mov     rcx, rbx; unsigned __int16 *
0x18000aa5c  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x18000aa61  test    al, al
0x18000aa63  jnz     short loc_18000AA71
0x18000aa65  jmp     short loc_18000AA6B
0x18000aa67  add     rbx, 2
0x18000aa6b  cmp     word ptr [rbx], 5Ch ; '\'
0x18000aa6f  jz      short loc_18000AA67
0x18000aa71  mov     r9, rbx; pszMore
0x18000aa74  lea     r8, [rbp+5D0h+pszPathOut]; pszPathIn
0x18000aa7b  mov     edx, 104h; cchPathOut
0x18000aa80  lea     rcx, [rbp+5D0h+pszPathOut]; pszPathOut
0x18000aa87  call    PathCchCombineEx
0x18000aa8c  lea     rcx, [rbp+5D0h+pszPathOut]; lpFileName
0x18000aa93  call    cs:__imp_GetFileAttributesW
0x18000aa99  cmp     eax, 0FFFFFFFFh
0x18000aa9c  jz      loc_18000AC6E
0x18000aaa2  mov     r9d, esi; bVersion
0x18000aaa5  lea     r8, [rsp+6D0h+pdwLSVer]; pdwLSVer
0x18000aaaa  lea     rdx, [rsp+6D0h+pdwMSVer]; pdwMSVer
0x18000aaaf  lea     rcx, [rbp+5D0h+pszPathOut]; lpszFilename
0x18000aab6  call    GetVersionFromFileW
0x18000aabb  mov     rax, [rsp+6D0h+var_688]
0x18000aac0  mov     rbx, [rax+r12*8]
0x18000aac4  test    rbx, rbx
0x18000aac7  jz      short loc_18000AAF6
0x18000aac9  lea     r8, IsBackslash
0x18000aad0  xor     edx, edx
0x18000aad2  mov     rcx, rbx; unsigned __int16 *
0x18000aad5  call    PathIsUnc2
0x18000aada  test    eax, eax
0x18000aadc  jnz     short loc_18000AAF6
0x18000aade  mov     rcx, rbx; unsigned __int16 *
0x18000aae1  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x18000aae6  test    al, al
0x18000aae8  jnz     short loc_18000AAF6
0x18000aaea  jmp     short loc_18000AAF0
0x18000aaec  add     rbx, 2
0x18000aaf0  cmp     word ptr [rbx], 5Ch ; '\'
0x18000aaf4  jz      short loc_18000AAEC
0x18000aaf6  mov     r9, rbx; pszMore
0x18000aaf9  lea     r8, [rsp+6D0h+Buffer]; pszPathIn
0x18000aafe  mov     edx, 104h; cchPathOut
0x18000ab03  lea     rcx, [rsp+6D0h+Buffer]; pszPathOut
0x18000ab08  call    PathCchCombineEx
0x18000ab0d  lea     rcx, [rsp+6D0h+Buffer]; lpFileName
0x18000ab12  call    cs:__imp_GetFileAttributesW
0x18000ab18  mov     ebx, esi
0x18000ab1a  cmp     eax, 0FFFFFFFFh
0x18000ab1d  jz      loc_18000ABC7
0x18000ab23  mov     r9d, ebx; bVersion
0x18000ab26  lea     r8, [rsp+6D0h+var_690]; pdwLSVer
0x18000ab2b  lea     rdx, [rsp+6D0h+var_69C]; pdwMSVer
0x18000ab30  lea     rcx, [rsp+6D0h+Buffer]; lpszFilename
0x18000ab35  call    GetVersionFromFileW
0x18000ab3a  mov     eax, [rsp+6D0h+pdwMSVer]
0x18000ab3e  cmp     [rsp+6D0h+var_69C], eax
0x18000ab42  ja      loc_18000AC6E
0x18000ab48  jnz     short loc_18000AB58
0x18000ab4a  mov     eax, [rsp+6D0h+pdwLSVer]
0x18000ab4e  cmp     [rsp+6D0h+var_690], eax
0x18000ab52  jnb     loc_18000AC6E
0x18000ab58  mov     edx, 80h; dwFileAttributes
0x18000ab5d  lea     rcx, [rsp+6D0h+Buffer]; lpFileName
0x18000ab62  call    cs:__imp_SetFileAttributesW
0x18000ab68  lea     r8, [rsp+6D0h+Buffer]; unsigned __int16 *
0x18000ab6d  mov     edx, 104h; unsigned __int64
0x18000ab72  lea     rcx, [rbp+5D0h+FileName]; unsigned __int16 *
0x18000ab79  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ab7e  mov     r8d, ebx; int
0x18000ab81  lea     rcx, [rbp+5D0h+FileName]; unsigned __int16 *
0x18000ab88  call    ?GetBackupName@@YAXPEAGKH@Z; GetBackupName(ushort *,ulong,int)
0x18000ab8d  mov     edx, 80h; dwFileAttributes
0x18000ab92  lea     rcx, [rbp+5D0h+FileName]; lpFileName
0x18000ab99  call    cs:__imp_SetFileAttributesW
0x18000ab9f  lea     rcx, [rbp+5D0h+FileName]; lpFileName
0x18000aba6  call    cs:__imp_DeleteFileW
0x18000abac  lea     rdx, [rbp+5D0h+FileName]; lpNewFileName
0x18000abb3  lea     rcx, [rsp+6D0h+Buffer]; lpExistingFileName
0x18000abb8  call    cs:__imp_MoveFileW
0x18000abbe  test    eax, eax
0x18000abc0  jz      short loc_18000ABC7
0x18000abc2  mov     dword ptr [rsp+r12*4+6D0h+var_680], ebx
0x18000abc7  xor     r8d, r8d; bFailIfExists
0x18000abca  lea     rdx, [rsp+6D0h+Buffer]; lpNewFileName
0x18000abcf  lea     rcx, [rbp+5D0h+pszPathOut]; lpExistingFileName
0x18000abd6  call    cs:__imp_CopyFileW
0x18000abdc  xor     edx, edx
0x18000abde  test    eax, eax
0x18000abe0  jnz     loc_18000AC70
0x18000abe6  mov     r12d, 104h
0x18000abec  test    byte ptr [rbp+5D0h+arg_20], bl
0x18000abf2  jz      loc_18000AC84
0x18000abf8  lea     r8, [rsp+6D0h+Buffer]; unsigned __int16 *
0x18000abfd  mov     edx, r12d; unsigned __int64
0x18000ac00  lea     rcx, [rbp+5D0h+FileName]; unsigned __int16 *
0x18000ac07  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ac0c  xor     r8d, r8d; int
0x18000ac0f  lea     rcx, [rbp+5D0h+FileName]; unsigned __int16 *
0x18000ac16  call    ?GetBackupName@@YAXPEAGKH@Z; GetBackupName(ushort *,ulong,int)
0x18000ac1b  mov     edx, 80h; dwFileAttributes
0x18000ac20  lea     rcx, [rbp+5D0h+FileName]; lpFileName
0x18000ac27  call    cs:__imp_SetFileAttributesW
0x18000ac2d  xor     r8d, r8d; bFailIfExists
0x18000ac30  lea     rdx, [rbp+5D0h+FileName]; lpNewFileName
0x18000ac37  lea     rcx, [rbp+5D0h+pszPathOut]; lpExistingFileName
0x18000ac3e  call    cs:__imp_CopyFileW
0x18000ac44  xor     edx, edx
0x18000ac46  test    eax, eax
0x18000ac48  jz      short loc_18000AC7E
0x18000ac4a  lea     rdx, [rsp+6D0h+Buffer]; lpKeyName
0x18000ac4f  lea     rcx, [rbp+5D0h+FileName]; lpString
0x18000ac56  call    ?AddWinInit@@YAHPEBG0@Z; AddWinInit(ushort const *,ushort const *)
0x18000ac5b  xor     edx, edx
0x18000ac5d  test    eax, eax
0x18000ac5f  jz      short loc_18000AC7E
0x18000ac61  test    byte ptr [rbp+5D0h+arg_20], 2
0x18000ac68  cmovnz  r13d, ebx
0x18000ac6c  jmp     short loc_18000AC70
0x18000ac6e  xor     edx, edx
0x18000ac70  mov     r12d, [rsp+6D0h+var_68C]
0x18000ac75  mov     eax, esi
0x18000ac77  add     edi, eax
0x18000ac79  jmp     loc_18000AA11
0x18000ac7e  mov     [rsp+6D0h+var_6A0], edx
0x18000ac82  mov     esi, edx
0x18000ac84  test    edi, edi
0x18000ac86  js      loc_18000AE34
0x18000ac8c  mov     rsi, [rsp+6D0h+var_688]
0x18000ac91  mov     ebx, edi
0x18000ac93  cmp     dword ptr [rsp+rbx*4+6D0h+var_680], edx
0x18000ac97  jz      loc_18000AD45
0x18000ac9d  mov     rbx, [rsi+rbx*8]
0x18000aca1  mov     [rsp+r14*2+6D0h+Buffer], dx
0x18000aca7  test    rbx, rbx
0x18000acaa  jz      short loc_18000ACD9
0x18000acac  lea     r8, IsBackslash
0x18000acb3  xor     edx, edx
0x18000acb5  mov     rcx, rbx; unsigned __int16 *
0x18000acb8  call    PathIsUnc2
0x18000acbd  test    eax, eax
0x18000acbf  jnz     short loc_18000ACD9
0x18000acc1  mov     rcx, rbx; unsigned __int16 *
0x18000acc4  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x18000acc9  test    al, al
0x18000accb  jnz     short loc_18000ACD9
0x18000accd  jmp     short loc_18000ACD3
0x18000accf  add     rbx, 2
0x18000acd3  cmp     word ptr [rbx], 5Ch ; '\'
0x18000acd7  jz      short loc_18000ACCF
0x18000acd9  mov     r9, rbx; pszMore
0x18000acdc  lea     r8, [rsp+6D0h+Buffer]; pszPathIn
0x18000ace1  mov     rdx, r12; cchPathOut
0x18000ace4  lea     rcx, [rsp+6D0h+Buffer]; pszPathOut
0x18000ace9  call    PathCchCombineEx
0x18000acee  lea     r8, [rsp+6D0h+Buffer]; unsigned __int16 *
0x18000acf3  mov     rdx, r12; unsigned __int64
0x18000acf6  lea     rcx, [rbp+5D0h+FileName]; unsigned __int16 *
0x18000acfd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ad02  mov     r8d, 1; int
0x18000ad08  lea     rcx, [rbp+5D0h+FileName]; unsigned __int16 *
0x18000ad0f  call    ?GetBackupName@@YAXPEAGKH@Z; GetBackupName(ushort *,ulong,int)
0x18000ad14  mov     edx, 80h; dwFileAttributes
0x18000ad19  lea     rcx, [rbp+5D0h+FileName]; lpFileName
0x18000ad20  call    cs:__imp_SetFileAttributesW
0x18000ad26  lea     rcx, [rsp+6D0h+Buffer]; lpFileName
0x18000ad2b  call    cs:__imp_DeleteFileW
0x18000ad31  lea     rdx, [rsp+6D0h+Buffer]; lpNewFileName
0x18000ad36  lea     rcx, [rbp+5D0h+FileName]; lpExistingFileName
0x18000ad3d  call    cs:__imp_MoveFileW
0x18000ad43  xor     edx, edx
0x18000ad45  sub     edi, 1
0x18000ad48  jns     loc_18000AC91
0x18000ad4e  mov     esi, [rsp+6D0h+var_6A0]
0x18000ad52  jmp     loc_18000AE34
0x18000ad57  mov     r12d, [rsp+6D0h+var_68C]
0x18000ad5c  mov     edi, edx
0x18000ad5e  test    r12d, r12d
0x18000ad61  jle     loc_18000AE2E
0x18000ad67  mov     rsi, [rsp+6D0h+var_688]
0x18000ad6c  cmp     edi, 3
0x18000ad6f  jnb     loc_18000AE2A
0x18000ad75  mov     ebx, edi
0x18000ad77  cmp     dword ptr [rsp+rbx*4+6D0h+var_680], edx
0x18000ad7b  jz      loc_18000AE1F
0x18000ad81  mov     rbx, [rsi+rbx*8]
0x18000ad85  mov     [rsp+r14*2+6D0h+Buffer], dx
0x18000ad8b  test    rbx, rbx
0x18000ad8e  jz      short loc_18000ADBD
0x18000ad90  lea     r8, IsBackslash
0x18000ad97  xor     edx, edx
0x18000ad99  mov     rcx, rbx; unsigned __int16 *
0x18000ad9c  call    PathIsUnc2
0x18000ada1  test    eax, eax
0x18000ada3  jnz     short loc_18000ADBD
0x18000ada5  mov     rcx, rbx; unsigned __int16 *
0x18000ada8  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x18000adad  test    al, al
0x18000adaf  jnz     short loc_18000ADBD
0x18000adb1  jmp     short loc_18000ADB7
0x18000adb3  add     rbx, 2
0x18000adb7  cmp     word ptr [rbx], 5Ch ; '\'
0x18000adbb  jz      short loc_18000ADB3
0x18000adbd  mov     r9, rbx; pszMore
0x18000adc0  lea     r8, [rsp+6D0h+Buffer]; pszPathIn
0x18000adc5  mov     ebx, 104h
0x18000adca  lea     rcx, [rsp+6D0h+Buffer]; pszPathOut
0x18000adcf  mov     edx, ebx; cchPathOut
0x18000add1  call    PathCchCombineEx
0x18000add6  lea     r8, [rsp+6D0h+Buffer]; unsigned __int16 *
0x18000addb  mov     edx, ebx; unsigned __int64
0x18000addd  lea     rcx, [rbp+5D0h+FileName]; unsigned __int16 *
0x18000ade4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ade9  mov     r8d, 1; int
0x18000adef  lea     rcx, [rbp+5D0h+FileName]; unsigned __int16 *
0x18000adf6  call    ?GetBackupName@@YAXPEAGKH@Z; GetBackupName(ushort *,ulong,int)
  ... truncated ...
```
