# SdbpGetChmFilePath

- ea: `0x180045bb8`
- end: `0x180045eeb`
- name: `SdbpGetChmFilePath`
- size: `819`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180043730`

## callees

- `0x1800055e0`
- `0x18000f114`
- `0x1800159e0`
- `0x180045bb8`
- `0x1800591b0`

## import_xrefs

- `ntdll!RtlDoesFileExists_U` at `0x180045db2`
- `ntdll!RtlDoesFileExists_U` at `0x180045db2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045e96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045e96`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180045cb0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180045cb0`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180045cc9`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180045cc9`

## string_xrefs

- `0x180045e9c`: `Error trying to retrieve Windows directory [%d]`
- `0x180045d0e`: `SdbpGetChmFilePath`
- `0x180045ea9`: `SdbpGetChmFilePath`
- `0x180045d01`: `Path to the service pack help file is too long`
- `0x180045de4`: `Path to non-service pack help file is too long`
- `0x180045e30`: `Path to help file is too long`
- `0x180045e79`: `Path to language identifier is too long`

## pseudocode

```c
__int64 __fastcall SdbpGetChmFilePath(int a1, __int64 a2, unsigned int *a3, __int64 a4, unsigned int *a5)
{
  unsigned int v9; // r14d
  UINT SystemWindowsDirectoryW; // eax
  unsigned int UserDefaultUILanguage; // ebx
  __int64 v12; // r10
  __int64 v13; // rax
  unsigned int v14; // r11d
  unsigned int v15; // r10d
  DWORD LastError; // eax
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h]
  __int128 v20; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t v21; // [rsp+50h] [rbp-B0h]
  _WORD v22[16]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v23[22]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v24; // [rsp+90h] [rbp-70h] BYREF
  __int128 v25; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v26; // [rsp+B0h] [rbp-50h]
  _OWORD v27[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v28; // [rsp+D8h] [rbp-28h]
  WCHAR FileName[264]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR Buffer[264]; // [rsp+2F0h] [rbp+1F0h] BYREF

  memset(v22, 0, sizeof(v22));
  v21 = aAppsChm[8];
  v26 = *(_QWORD *)L"chm";
  v9 = 0;
  v20 = *(_OWORD *)L"apps.chm";
  LOWORD(v19) = aHtm[4];
  v27[1] = *(_OWORD *)L"MUI\\%04x\\%s";
  v25 = *(_OWORD *)L"apps_sp.chm";
  *(_OWORD *)v23 = *(_OWORD *)L"%s\\Help\\%s";
  v27[0] = *(_OWORD *)L"%s\\Help\\MUI\\%04x\\%s";
  v28 = *(_QWORD *)L"\\%s";
  *(_QWORD *)&v23[14] = *(_QWORD *)L"\\%s";
  v18 = *(_QWORD *)L".htm";
  v24 = *(_OWORD *)L"_%x.htm";
  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(Buffer, 0x104u);
  if ( !SystemWindowsDirectoryW || SystemWindowsDirectoryW >= 0x104 )
  {
    LastError = GetLastError();
    AslLogCallPrintf(1, "SdbpGetChmFilePath", 2830, "Error trying to retrieve Windows directory [%d]", LastError);
    return v9;
  }
  UserDefaultUILanguage = GetUserDefaultUILanguage();
  if ( !a1 )
  {
    if ( (int)RtlStringCchCopyW(v22, 16, &v18) < 0 )
    {
      AslLogCallPrintf(1, "SdbpGetChmFilePath", 2865, "Language identifier is too long");
      return v9;
    }
    if ( (UserDefaultUILanguage == 1033
       || (int)RtlStringCchPrintfW(FileName, 260, v27, Buffer, UserDefaultUILanguage, &v20, v18, v19) < 0
       || !RtlDoesFileExists_U(FileName))
      && (int)RtlStringCchPrintfW(FileName, 260, v23, Buffer, &v20) < 0 )
    {
      AslLogCallPrintf(1, "SdbpGetChmFilePath", 2889, "Path to non-service pack help file is too long");
      return v9;
    }
LABEL_16:
    v12 = -1;
    v13 = -1;
    do
      ++v13;
    while ( FileName[v13] );
    if ( a3 )
    {
      v14 = v13 + 1;
      if ( a2 && *a3 >= v14 && (int)RtlStringCchCopyW(a2, *a3, FileName) < 0 )
      {
        AslLogCallPrintf(1, "SdbpGetChmFilePath", 2903, "Path to help file is too long");
        return v9;
      }
      *a3 = v14;
    }
    do
      ++v12;
    while ( v22[v12] );
    if ( a5 )
    {
      v15 = v12 + 1;
      if ( a4 && *a5 >= v15 && (int)RtlStringCchCopyW(a4, *a5, v22) < 0 )
      {
        AslLogCallPrintf(1, "SdbpGetChmFilePath", 2917, "Path to language identifier is too long");
        return v9;
      }
      *a5 = v15;
    }
    return 1;
  }
  if ( (int)RtlStringCchPrintfW(FileName, 260, v23, Buffer, &v25) < 0 )
  {
    AslLogCallPrintf(1, "SdbpGetChmFilePath", 2848, "Path to the service pack help file is too long");
    return v9;
  }
  if ( (int)RtlStringCchPrintfW(v22, 16, &v24, UserDefaultUILanguage) >= 0 )
    goto LABEL_16;
  AslLogCallPrintf(1, "SdbpGetChmFilePath", 2857, "Language identifier is too long");
  return v9;
}

```

## disassembly

```asm
0x180045bb8  mov     [rsp-8+arg_0], rbx
0x180045bbd  push    rbp
0x180045bbe  push    rsi
0x180045bbf  push    rdi
0x180045bc0  push    r12
0x180045bc2  push    r13
0x180045bc4  push    r14
0x180045bc6  push    r15
0x180045bc8  lea     rbp, [rsp-410h]
0x180045bd0  sub     rsp, 510h
0x180045bd7  mov     rax, cs:__security_cookie
0x180045bde  xor     rax, rsp
0x180045be1  mov     [rbp+440h+var_40], rax
0x180045be8  movsd   xmm1, qword ptr cs:aAppsSpChm+10h; "chm"
0x180045bf0  xorps   xmm0, xmm0
0x180045bf3  mov     rdi, [rbp+440h+arg_20]
0x180045bfa  xor     eax, eax
0x180045bfc  movups  xmmword ptr [rsp+540h+var_4E6], xmm0
0x180045c01  mov     [rsp+540h+var_4E8], ax
0x180045c06  mov     r15, rdx
0x180045c09  movzx   eax, word ptr cs:aAppsChm+10h; ""
0x180045c10  mov     r13d, ecx
0x180045c13  movups  xmmword ptr [rsp+540h+var_4E6+0Eh], xmm0
0x180045c18  mov     [rsp+540h+var_4F0], ax
0x180045c1d  mov     edx, 104h; uSize
0x180045c22  movups  xmm0, xmmword ptr cs:aAppsChm; "apps.chm"
0x180045c29  movzx   eax, word ptr cs:aHtm+8; ""
0x180045c30  lea     rcx, [rbp+440h+Buffer]; lpBuffer
0x180045c37  movsd   [rbp+440h+var_490], xmm1
0x180045c3c  mov     r12, r9
0x180045c3f  movups  xmm1, xmmword ptr cs:aSHelpMui04xS+10h; "MUI\\%04x\\%s"
0x180045c46  mov     rsi, r8
0x180045c49  xor     r14d, r14d
0x180045c4c  movups  [rsp+540h+var_500], xmm0
0x180045c51  mov     word ptr [rsp+540h+var_508], ax
0x180045c56  movups  xmm0, xmmword ptr cs:aAppsSpChm; "apps_sp.chm"
0x180045c5d  movups  [rbp+440h+var_478], xmm1
0x180045c61  movups  xmm1, xmmword ptr cs:aSHelpS; "%s\\Help\\%s"
0x180045c68  movups  [rbp+440h+var_4A0], xmm0
0x180045c6c  movups  xmm0, xmmword ptr cs:aSHelpMui04xS; "%s\\Help\\MUI\\%04x\\%s"
0x180045c73  movups  [rsp+540h+var_4C8], xmm1
0x180045c78  movsd   xmm1, qword ptr cs:aHtm; ".htm"
0x180045c80  movups  [rbp+440h+var_488], xmm0
0x180045c84  movsd   xmm0, qword ptr cs:aSHelpMui04xS+20h; "\\%s"
0x180045c8c  movsd   [rbp+440h+var_468], xmm0
0x180045c91  movsd   xmm0, qword ptr cs:aSHelpS+0Eh; "\\%s"
0x180045c99  movsd   qword ptr [rbp+440h+var_4C8+0Eh], xmm0
0x180045c9e  movups  xmm0, xmmword ptr cs:aXHtm; "_%x.htm"
0x180045ca5  movsd   [rsp+540h+var_510], xmm1
0x180045cab  movdqu  [rbp+440h+var_4B0], xmm0
0x180045cb0  call    cs:__imp_GetSystemWindowsDirectoryW
0x180045cb6  test    eax, eax
0x180045cb8  jz      loc_180045E96
0x180045cbe  cmp     eax, 104h
0x180045cc3  jnb     loc_180045E96
0x180045cc9  call    cs:__imp_GetUserDefaultUILanguage
0x180045ccf  movzx   ebx, ax
0x180045cd2  test    r13d, r13d
0x180045cd5  jz      short loc_180045D51
0x180045cd7  lea     rax, [rbp+440h+var_4A0]
0x180045cdb  mov     edx, 104h
0x180045ce0  lea     r9, [rbp+440h+Buffer]
0x180045ce7  mov     [rsp+540h+var_520], rax
0x180045cec  lea     r8, [rsp+540h+var_4C8]
0x180045cf1  lea     rcx, [rbp+440h+FileName]
0x180045cf5  call    RtlStringCchPrintfW
0x180045cfa  xor     r13d, r13d
0x180045cfd  test    eax, eax
0x180045cff  jns     short loc_180045D24
0x180045d01  lea     r9, aPathToTheServi; "Path to the service pack help file is t"...
0x180045d08  mov     r8d, 0B20h
0x180045d0e  lea     rdx, aSdbpgetchmfile; "SdbpGetChmFilePath"
0x180045d15  mov     ecx, 1
0x180045d1a  call    AslLogCallPrintf
0x180045d1f  jmp     loc_180045EBE
0x180045d24  mov     r9d, ebx
0x180045d27  lea     r8, [rbp+440h+var_4B0]
0x180045d2b  mov     edx, 10h
0x180045d30  lea     rcx, [rsp+540h+var_4E8]
0x180045d35  call    RtlStringCchPrintfW
0x180045d3a  test    eax, eax
0x180045d3c  jns     loc_180045DF6
0x180045d42  lea     r9, aLanguageIdenti; "Language identifier is too long"
0x180045d49  mov     r8d, 0B29h
0x180045d4f  jmp     short loc_180045D0E
0x180045d51  lea     r8, [rsp+540h+var_510]
0x180045d56  mov     edx, 10h
0x180045d5b  lea     rcx, [rsp+540h+var_4E8]
0x180045d60  call    RtlStringCchCopyW
0x180045d65  xor     r13d, r13d
0x180045d68  test    eax, eax
0x180045d6a  jns     short loc_180045D7B
0x180045d6c  lea     r9, aLanguageIdenti; "Language identifier is too long"
0x180045d73  mov     r8d, 0B31h
0x180045d79  jmp     short loc_180045D0E
0x180045d7b  cmp     ebx, 409h
0x180045d81  jz      short loc_180045DBC
0x180045d83  lea     rax, [rsp+540h+var_500]
0x180045d88  mov     edx, 104h
0x180045d8d  mov     [rsp+540h+var_518], rax
0x180045d92  lea     r9, [rbp+440h+Buffer]
0x180045d99  lea     r8, [rbp+440h+var_488]
0x180045d9d  mov     dword ptr [rsp+540h+var_520], ebx
0x180045da1  lea     rcx, [rbp+440h+FileName]
0x180045da5  call    RtlStringCchPrintfW
0x180045daa  test    eax, eax
0x180045dac  js      short loc_180045DBC
0x180045dae  lea     rcx, [rbp+440h+FileName]; FileName
0x180045db2  call    cs:__imp_RtlDoesFileExists_U
0x180045db8  test    al, al
0x180045dba  jnz     short loc_180045DF6
0x180045dbc  lea     rax, [rsp+540h+var_500]
0x180045dc1  mov     edx, 104h
0x180045dc6  lea     r9, [rbp+440h+Buffer]
0x180045dcd  mov     [rsp+540h+var_520], rax
0x180045dd2  lea     r8, [rsp+540h+var_4C8]
0x180045dd7  lea     rcx, [rbp+440h+FileName]
0x180045ddb  call    RtlStringCchPrintfW
0x180045de0  test    eax, eax
0x180045de2  jns     short loc_180045DF6
0x180045de4  lea     r9, aPathToNonServi; "Path to non-service pack help file is t"...
0x180045deb  mov     r8d, 0B49h
0x180045df1  jmp     loc_180045D0E
0x180045df6  or      r10, 0FFFFFFFFFFFFFFFFh
0x180045dfa  lea     rcx, [rbp+440h+FileName]
0x180045dfe  mov     rax, r10
0x180045e01  inc     rax
0x180045e04  cmp     [rcx+rax*2], r13w
0x180045e09  jnz     short loc_180045E01
0x180045e0b  test    rsi, rsi
0x180045e0e  jz      short loc_180045E45
0x180045e10  lea     r11d, [rax+1]
0x180045e14  test    r15, r15
0x180045e17  jz      short loc_180045E42
0x180045e19  cmp     [rsi], r11d
0x180045e1c  jb      short loc_180045E42
0x180045e1e  mov     edx, [rsi]
0x180045e20  lea     r8, [rbp+440h+FileName]
0x180045e24  mov     rcx, r15
0x180045e27  call    RtlStringCchCopyW
0x180045e2c  test    eax, eax
0x180045e2e  jns     short loc_180045E42
0x180045e30  lea     r9, aPathToHelpFile; "Path to help file is too long"
0x180045e37  mov     r8d, 0B57h
0x180045e3d  jmp     loc_180045D0E
0x180045e42  mov     [rsi], r11d
0x180045e45  lea     rax, [rsp+540h+var_4E8]
0x180045e4a  inc     r10
0x180045e4d  cmp     [rax+r10*2], r13w
0x180045e52  jnz     short loc_180045E4A
0x180045e54  test    rdi, rdi
0x180045e57  jz      short loc_180045E8E
0x180045e59  inc     r10d
0x180045e5c  test    r12, r12
0x180045e5f  jz      short loc_180045E8B
0x180045e61  cmp     [rdi], r10d
0x180045e64  jb      short loc_180045E8B
0x180045e66  mov     edx, [rdi]
0x180045e68  lea     r8, [rsp+540h+var_4E8]
0x180045e6d  mov     rcx, r12
0x180045e70  call    RtlStringCchCopyW
0x180045e75  test    eax, eax
0x180045e77  jns     short loc_180045E8B
0x180045e79  lea     r9, aPathToLanguage; "Path to language identifier is too long"
0x180045e80  mov     r8d, 0B65h
0x180045e86  jmp     loc_180045D0E
0x180045e8b  mov     [rdi], r10d
0x180045e8e  mov     r14d, 1
0x180045e94  jmp     short loc_180045EBE
0x180045e96  call    cs:__imp_GetLastError
0x180045e9c  lea     r9, aErrorTryingToR_0; "Error trying to retrieve Windows direct"...
0x180045ea3  mov     r8d, 0B0Eh
0x180045ea9  lea     rdx, aSdbpgetchmfile; "SdbpGetChmFilePath"
0x180045eb0  mov     dword ptr [rsp+540h+var_520], eax
0x180045eb4  mov     ecx, 1
0x180045eb9  call    AslLogCallPrintf
0x180045ebe  mov     eax, r14d
0x180045ec1  mov     rcx, [rbp+440h+var_40]
0x180045ec8  xor     rcx, rsp; StackCookie
0x180045ecb  call    __security_check_cookie
0x180045ed0  mov     rbx, [rsp+540h+arg_0]
0x180045ed8  add     rsp, 510h
0x180045edf  pop     r15
0x180045ee1  pop     r14
0x180045ee3  pop     r13
0x180045ee5  pop     r12
0x180045ee7  pop     rdi
0x180045ee8  pop     rsi
0x180045ee9  pop     rbp
0x180045eea  retn
```
