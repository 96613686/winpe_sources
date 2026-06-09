# CopyFolder(ushort const *,ushort const *)

- ea: `0x180035fdc`
- end: `0x18003633d`
- name: `?CopyFolder@@YAJPEBG0@Z`
- size: `865`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180035fdc`
- `0x180036ae0`
- `0x180037310`

## callees

- `0x180003f30`
- `0x180017b30`
- `0x18001a280`
- `0x18001ad5c`
- `0x180021d1c`
- `0x180035fdc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003614b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036234`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800362a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003614b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036234`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800362a2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003622a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003622a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003613c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003613c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003630e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003630e`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800362c3`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800362c3`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180036298`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180036298`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800361f9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180036213`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800361f9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180036213`

## string_xrefs

- `0x1800362d6`: `CreateDirectory failed: 0x%x in %s`
- `0x180036066`: `CopyFolder`
- `0x180036110`: `CopyFolder`
- `0x180036164`: `CopyFolder`
- `0x1800362f5`: `CopyFolder`
- `0x18003605f`: `szSrcPath`
- `0x18003608d`: `szDesPath`
- `0x18003626a`: `CopyFolder failed: 0x%x in %s`
- `0x1800362e2`: `CopyFile failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CopyFolder(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  const char *v4; // r8
  signed int v5; // ebx
  __int64 v6; // rdx
  WCHAR *v7; // rcx
  const unsigned __int16 *v8; // rax
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  int v16; // eax
  HANDLE FirstFileW; // rdi
  signed int LastError; // eax
  int v19; // eax
  signed int v20; // eax
  const char *v21; // rdx
  signed int v22; // eax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR PathName[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR FileName[264]; // [rsp+490h] [rbp+390h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+6A0h] [rbp+5A0h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  memset_0(ExistingFileName, 0, 0x208u);
  memset_0(PathName, 0, 0x208u);
  memset_0(FileName, 0, 0x208u);
  if ( !a1 )
  {
    v4 = "szSrcPath";
LABEL_3:
    _DbgPrintMessage(8, "Missing paramter %s in %s", v4, "CopyFolder");
    return (unsigned int)-2147024809;
  }
  if ( !a2 )
  {
    v4 = "szDesPath";
    goto LABEL_3;
  }
  v6 = 2;
  v7 = FileName;
  v8 = a1;
  do
  {
    v9 = *((_OWORD *)v8 + 1);
    *(_OWORD *)v7 = *(_OWORD *)v8;
    v10 = *((_OWORD *)v8 + 2);
    *((_OWORD *)v7 + 1) = v9;
    v11 = *((_OWORD *)v8 + 3);
    *((_OWORD *)v7 + 2) = v10;
    v12 = *((_OWORD *)v8 + 4);
    *((_OWORD *)v7 + 3) = v11;
    v13 = *((_OWORD *)v8 + 5);
    *((_OWORD *)v7 + 4) = v12;
    v14 = *((_OWORD *)v8 + 6);
    *((_OWORD *)v7 + 5) = v13;
    v15 = *((_OWORD *)v8 + 7);
    v8 += 64;
    *((_OWORD *)v7 + 6) = v14;
    *((_OWORD *)v7 + 7) = v15;
    v7 += 64;
    --v6;
  }
  while ( v6 );
  *(_DWORD *)v7 = *(_DWORD *)v8;
  v16 = StringCchCatW(FileName, 0, L"\\*");
  v5 = v16;
  if ( v16 < 0 )
  {
    _DbgPrintMessage(8, "StringCchCat failed: 0x%x in %s", v16, "CopyFolder");
    return (unsigned int)v5;
  }
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 < 0 )
    {
      _DbgPrintMessage(8, "FindFirstFile failed: 0x%x in %s", v5, "CopyFolder");
LABEL_37:
      FindClose(FirstFileW);
      return (unsigned int)v5;
    }
  }
  while ( 1 )
  {
    v19 = StringCchPrintfW(PathName, 0x104u, L"%s\\%s", a2, FindFileData.cFileName);
    v5 = v19;
    if ( v19 < 0 )
      break;
    v19 = StringCchPrintfW(ExistingFileName, 0x104u, L"%s\\%s", a1, FindFileData.cFileName);
    v5 = v19;
    if ( v19 < 0 )
      break;
    if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
    {
      if ( lstrcmpiW(FindFileData.cFileName, L".") && lstrcmpiW(FindFileData.cFileName, L"..") )
      {
        if ( !CreateDirectoryW(PathName, 0) )
        {
          v20 = GetLastError();
          v5 = v20;
          if ( v20 > 0 )
            v5 = (unsigned __int16)v20 | 0x80070000;
          if ( v5 < 0 )
          {
            _DbgPrintMessage(8, "CreateDirectory failed: 0x%x in %s", (unsigned int)v5, "CopyFolder");
            goto LABEL_36;
          }
        }
        v19 = CopyFolder(ExistingFileName, PathName);
        v5 = v19;
        if ( v19 < 0 )
        {
          v21 = "CopyFolder failed: 0x%x in %s";
          goto LABEL_35;
        }
      }
    }
    else if ( !CopyFileExW(ExistingFileName, PathName, 0, 0, 0, 1u) )
    {
      v22 = GetLastError();
      v5 = v22;
      if ( v22 > 0 )
        v5 = (unsigned __int16)v22 | 0x80070000;
      if ( v5 < 0 )
      {
        _DbgPrintMessage(8, "CopyFile failed: 0x%x in %s", (unsigned int)v5, "CopyFolder");
        goto LABEL_36;
      }
    }
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
      goto LABEL_36;
  }
  v21 = "StringCchPrintf failed: 0x%x in %s";
LABEL_35:
  _DbgPrintMessage(8, v21, (unsigned int)v19, "CopyFolder");
LABEL_36:
  if ( FirstFileW )
    goto LABEL_37;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180035fdc  mov     [rsp-8+arg_10], rbx
0x180035fe1  mov     [rsp-8+arg_18], rsi
0x180035fe6  push    rbp
0x180035fe7  push    rdi
0x180035fe8  push    r14
0x180035fea  lea     rbp, [rsp-7C0h]
0x180035ff2  sub     rsp, 8C0h
0x180035ff9  mov     rax, cs:__security_cookie
0x180036000  xor     rax, rsp
0x180036003  mov     [rbp+7D0h+var_20], rax
0x18003600a  mov     r14, rdx
0x18003600d  mov     rsi, rcx
0x180036010  xor     edx, edx; Val
0x180036012  lea     rcx, [rsp+8D0h+FindFileData]; void *
0x180036017  mov     r8d, 250h; Size
0x18003601d  call    memset_0
0x180036022  mov     ebx, 208h
0x180036027  lea     rcx, [rbp+7D0h+ExistingFileName]; void *
0x18003602e  mov     r8d, ebx; Size
0x180036031  xor     edx, edx; Val
0x180036033  call    memset_0
0x180036038  mov     r8d, ebx; Size
0x18003603b  lea     rcx, [rbp+7D0h+PathName]; void *
0x180036042  xor     edx, edx; Val
0x180036044  call    memset_0
0x180036049  mov     r8d, ebx; Size
0x18003604c  lea     rcx, [rbp+7D0h+FileName]; void *
0x180036053  xor     edx, edx; Val
0x180036055  call    memset_0
0x18003605a  test    rsi, rsi
0x18003605d  jnz     short loc_180036088
0x18003605f  lea     r8, aSzsrcpath; "szSrcPath"
0x180036066  lea     r9, aCopyfolder; "CopyFolder"
0x18003606d  mov     ecx, 8; int
0x180036072  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180036079  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003607e  mov     ebx, 80070057h
0x180036083  jmp     loc_180036314
0x180036088  test    r14, r14
0x18003608b  jnz     short loc_180036096
0x18003608d  lea     r8, aSzdespath; "szDesPath"
0x180036094  jmp     short loc_180036066
0x180036096  mov     edx, 2
0x18003609b  lea     rcx, [rbp+7D0h+FileName]
0x1800360a2  mov     rax, rsi
0x1800360a5  lea     r8d, [rdx+7Eh]
0x1800360a9  movups  xmm0, xmmword ptr [rax]
0x1800360ac  movups  xmm1, xmmword ptr [rax+10h]
0x1800360b0  movups  xmmword ptr [rcx], xmm0
0x1800360b3  movups  xmm0, xmmword ptr [rax+20h]
0x1800360b7  movups  xmmword ptr [rcx+10h], xmm1
0x1800360bb  movups  xmm1, xmmword ptr [rax+30h]
0x1800360bf  movups  xmmword ptr [rcx+20h], xmm0
0x1800360c3  movups  xmm0, xmmword ptr [rax+40h]
0x1800360c7  movups  xmmword ptr [rcx+30h], xmm1
0x1800360cb  movups  xmm1, xmmword ptr [rax+50h]
0x1800360cf  movups  xmmword ptr [rcx+40h], xmm0
0x1800360d3  movups  xmm0, xmmword ptr [rax+60h]
0x1800360d7  movups  xmmword ptr [rcx+50h], xmm1
0x1800360db  movups  xmm1, xmmword ptr [rax+70h]
0x1800360df  add     rax, r8
0x1800360e2  movups  xmmword ptr [rcx+60h], xmm0
0x1800360e6  movups  xmmword ptr [rcx+70h], xmm1
0x1800360ea  add     rcx, r8
0x1800360ed  sub     rdx, 1; unsigned __int64
0x1800360f1  jnz     short loc_1800360A9
0x1800360f3  mov     eax, [rax]
0x1800360f5  lea     r8, asc_18006D438; "\\*"
0x1800360fc  mov     [rcx], eax
0x1800360fe  lea     rcx, [rbp+7D0h+FileName]; unsigned __int16 *
0x180036105  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003610a  mov     ebx, eax
0x18003610c  test    eax, eax
0x18003610e  jns     short loc_180036130
0x180036110  lea     r9, aCopyfolder; "CopyFolder"
0x180036117  mov     r8d, eax
0x18003611a  lea     rdx, aStringcchcatFa; "StringCchCat failed: 0x%x in %s"
0x180036121  mov     ecx, 8; int
0x180036126  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003612b  jmp     loc_180036314
0x180036130  lea     rdx, [rsp+8D0h+FindFileData]; lpFindFileData
0x180036135  lea     rcx, [rbp+7D0h+FileName]; lpFileName
0x18003613c  call    cs:__imp_FindFirstFileW
0x180036142  mov     rdi, rax
0x180036145  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180036149  jnz     short loc_180036184
0x18003614b  call    cs:__imp_GetLastError
0x180036151  mov     ebx, eax
0x180036153  test    eax, eax
0x180036155  jle     short loc_180036160
0x180036157  movzx   ebx, ax
0x18003615a  or      ebx, 80070000h
0x180036160  test    ebx, ebx
0x180036162  jns     short loc_180036184
0x180036164  lea     r9, aCopyfolder; "CopyFolder"
0x18003616b  mov     r8d, ebx
0x18003616e  lea     rdx, aFindfirstfileF; "FindFirstFile failed: 0x%x in %s"
0x180036175  mov     ecx, 8; int
0x18003617a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003617f  jmp     loc_18003630B
0x180036184  lea     rax, [rsp+8D0h+FindFileData.cFileName]
0x180036189  mov     r9, r14
0x18003618c  lea     r8, aSS_0; "%s\\%s"
0x180036193  mov     [rsp+8D0h+pbCancel], rax
0x180036198  mov     edx, 104h; unsigned __int64
0x18003619d  lea     rcx, [rbp+7D0h+PathName]; unsigned __int16 *
0x1800361a4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800361a9  mov     ebx, eax
0x1800361ab  test    eax, eax
0x1800361ad  js      loc_1800362EB
0x1800361b3  lea     rax, [rsp+8D0h+FindFileData.cFileName]
0x1800361b8  mov     r9, rsi
0x1800361bb  lea     r8, aSS_0; "%s\\%s"
0x1800361c2  mov     [rsp+8D0h+pbCancel], rax
0x1800361c7  mov     edx, 104h; unsigned __int64
0x1800361cc  lea     rcx, [rbp+7D0h+ExistingFileName]; unsigned __int16 *
0x1800361d3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800361d8  mov     ebx, eax
0x1800361da  test    eax, eax
0x1800361dc  js      loc_1800362EB
0x1800361e2  test    byte ptr [rsp+8D0h+FindFileData.dwFileAttributes], 10h
0x1800361e7  jz      loc_180036273
0x1800361ed  lea     rdx, String2; "."
0x1800361f4  lea     rcx, [rsp+8D0h+FindFileData.cFileName]; lpString1
0x1800361f9  call    cs:__imp_lstrcmpiW
0x1800361ff  test    eax, eax
0x180036201  jz      loc_1800362BB
0x180036207  lea     rdx, asc_180069B14; ".."
0x18003620e  lea     rcx, [rsp+8D0h+FindFileData.cFileName]; lpString1
0x180036213  call    cs:__imp_lstrcmpiW
0x180036219  test    eax, eax
0x18003621b  jz      loc_1800362BB
0x180036221  xor     edx, edx; lpSecurityAttributes
0x180036223  lea     rcx, [rbp+7D0h+PathName]; lpPathName
0x18003622a  call    cs:__imp_CreateDirectoryW
0x180036230  test    eax, eax
0x180036232  jnz     short loc_180036251
0x180036234  call    cs:__imp_GetLastError
0x18003623a  mov     ebx, eax
0x18003623c  test    eax, eax
0x18003623e  jle     short loc_180036249
0x180036240  movzx   ebx, ax
0x180036243  or      ebx, 80070000h
0x180036249  test    ebx, ebx
0x18003624b  js      loc_1800362D3
0x180036251  lea     rdx, [rbp+7D0h+PathName]; unsigned __int16 *
0x180036258  lea     rcx, [rbp+7D0h+ExistingFileName]; unsigned __int16 *
0x18003625f  call    ?CopyFolder@@YAJPEBG0@Z; CopyFolder(ushort const *,ushort const *)
0x180036264  mov     ebx, eax
0x180036266  test    eax, eax
0x180036268  jns     short loc_1800362BB
0x18003626a  lea     rdx, aCopyfolderFail; "CopyFolder failed: 0x%x in %s"
0x180036271  jmp     short loc_1800362F2
0x180036273  mov     [rsp+8D0h+dwCopyFlags], 1; dwCopyFlags
0x18003627b  lea     rdx, [rbp+7D0h+PathName]; lpNewFileName
0x180036282  xor     r9d, r9d; lpData
0x180036285  mov     [rsp+8D0h+pbCancel], 0; pbCancel
0x18003628e  xor     r8d, r8d; lpProgressRoutine
0x180036291  lea     rcx, [rbp+7D0h+ExistingFileName]; lpExistingFileName
0x180036298  call    cs:__imp_CopyFileExW
0x18003629e  test    eax, eax
0x1800362a0  jnz     short loc_1800362BB
0x1800362a2  call    cs:__imp_GetLastError
0x1800362a8  mov     ebx, eax
0x1800362aa  test    eax, eax
0x1800362ac  jle     short loc_1800362B7
0x1800362ae  movzx   ebx, ax
0x1800362b1  or      ebx, 80070000h
0x1800362b7  test    ebx, ebx
0x1800362b9  js      short loc_1800362DF
0x1800362bb  lea     rdx, [rsp+8D0h+FindFileData]; lpFindFileData
0x1800362c0  mov     rcx, rdi; hFindFile
0x1800362c3  call    cs:__imp_FindNextFileW
0x1800362c9  test    eax, eax
0x1800362cb  jnz     loc_180036184
0x1800362d1  jmp     short loc_180036306
0x1800362d3  mov     r8d, ebx
0x1800362d6  lea     rdx, aCreatedirector_0; "CreateDirectory failed: 0x%x in %s"
0x1800362dd  jmp     short loc_1800362F5
0x1800362df  mov     r8d, ebx
0x1800362e2  lea     rdx, aCopyfileFailed; "CopyFile failed: 0x%x in %s"
0x1800362e9  jmp     short loc_1800362F5
0x1800362eb  lea     rdx, aStringcchprint; "StringCchPrintf failed: 0x%x in %s"
0x1800362f2  mov     r8d, eax
0x1800362f5  lea     r9, aCopyfolder; "CopyFolder"
0x1800362fc  mov     ecx, 8; int
0x180036301  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180036306  test    rdi, rdi
0x180036309  jz      short loc_180036314
0x18003630b  mov     rcx, rdi; hFindFile
0x18003630e  call    cs:__imp_FindClose
0x180036314  mov     eax, ebx
0x180036316  mov     rcx, [rbp+7D0h+var_20]
0x18003631d  xor     rcx, rsp; StackCookie
0x180036320  call    __security_check_cookie
0x180036325  lea     r11, [rsp+8D0h+var_10]
0x18003632d  mov     rbx, [r11+30h]
0x180036331  mov     rsi, [r11+38h]
0x180036335  mov     rsp, r11
0x180036338  pop     r14
0x18003633a  pop     rdi
0x18003633b  pop     rbp
0x18003633c  retn
```
