# SuspCountFolderStartupApps(_SYSPREP_OS_OFFLINE *,StartupScanFlags,_SUS_COUNTS *)

- ea: `0x180002c64`
- end: `0x18000315d`
- name: `?SuspCountFolderStartupApps@@YAJPEAU_SYSPREP_OS_OFFLINE@@W4StartupScanFlags@@PEAU_SUS_COUNTS@@@Z`
- size: `1273`
- prototype: `__int64 __fastcall(__int64, int, _DWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003610`

## callees

- `0x180001bc0`
- `0x180002270`
- `0x180002c40`
- `0x180002c64`
- `0x1800039f8`
- `0x180003cfc`
- `0x180003dec`
- `0x1800040f6`
- `0x180004102`
- `0x180004130`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180002f70`
- `msvcrt!_wcsicmp` at `0x180002f70`
- `msvcrt!wcsstr` at `0x180002cec`
- `msvcrt!wcsstr` at `0x180002cec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030e6`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180002e34`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180002e34`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180002f8b`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180002f8b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180002f9d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000312b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180002f9d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000312b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180002f01`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180002f01`

## string_xrefs

- `0x180002d32`: `%PROGRAMDATA%`
- `0x180002d92`: `%PROGRAMDATA%`
- `0x180002d83`: `ProgramData`

## pseudocode

```c
__int64 __fastcall SuspCountFolderStartupApps(__int64 a1, int a2, _DWORD *a3)
{
  __int64 v4; // r15
  int v5; // edi
  __int64 FirstFileW; // r14
  int v7; // esi
  __int64 v8; // rax
  WCHAR *v9; // rbx
  __int64 v10; // r12
  unsigned int v11; // edx
  unsigned int v12; // ebx
  unsigned int v13; // r8d
  __int64 v14; // rdx
  unsigned int v15; // edx
  WCHAR *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  const wchar_t *v19; // rcx
  __int64 v20; // rax
  WCHAR *v21; // r9
  __int64 v22; // rdx
  WCHAR *v23; // rcx
  unsigned __int16 v24; // ax
  const wchar_t *v25; // r15
  WCHAR v26; // cx
  WCHAR *cFileName; // rdx
  const wchar_t *v28; // rbx
  int v29; // edi
  signed int LastError; // eax
  int v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+30h] [rbp-D0h] BYREF
  int v34; // [rsp+34h] [rbp-CCh]
  int v35; // [rsp+38h] [rbp-C8h]
  int v36; // [rsp+3Ch] [rbp-C4h]
  const wchar_t *v37; // [rsp+40h] [rbp-C0h]
  __int64 v38; // [rsp+48h] [rbp-B8h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t v40[12]; // [rsp+2A0h] [rbp+1A0h] BYREF
  wchar_t String2[20]; // [rsp+2B8h] [rbp+1B8h] BYREF
  WCHAR Dst[264]; // [rsp+2E0h] [rbp+1E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+538h] [rbp+438h]

  v36 = a2;
  v4 = a1;
  v38 = a1;
  v5 = 0;
  v34 = 0;
  FirstFileW = -1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v37 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\StartupApproved";
  v7 = 0;
  v8 = 0;
  v35 = 0;
  while ( 1 )
  {
    v9 = off_180006010[v8];
    if ( wcsstr(v9, L"APPDATA") )
    {
      v10 = v4 ? *(_QWORD *)(v4 + 8) : -2147483647LL;
    }
    else if ( v4 )
    {
      v10 = *(_QWORD *)(v4 + 40);
      v37 = L"Microsoft\\Windows\\CurrentVersion\\Explorer\\StartupApproved";
    }
    else
    {
      v10 = -2147483646;
    }
    if ( v4 )
      break;
LABEL_17:
    if ( !ExpandEnvironmentStringsW(v9, Dst, 0x104u) )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16);
LABEL_76:
      if ( FirstFileW != -1 )
        FindClose((HANDLE)FirstFileW);
      return v12;
    }
    v16 = Dst;
    v17 = 260;
    do
    {
      if ( !*v16 )
        break;
      ++v16;
      --v17;
    }
    while ( v17 );
    v12 = v17 == 0 ? 0x80070057 : 0;
    v18 = (260 - v17) & -(__int64)(v17 != 0);
    if ( !v17 )
    {
      v24 = 87;
LABEL_68:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_91e8665fb8f03560ae482285a745ac49_Traceguids, v24);
      goto LABEL_76;
    }
    v19 = L"\\*";
    v20 = 2147483646;
    v21 = &Dst[v18];
    v22 = 260 - v18;
    if ( 260 != v18 )
    {
      do
      {
        if ( !v20 )
          break;
        if ( !*v19 )
          break;
        *v21++ = *v19++;
        --v20;
        --v22;
      }
      while ( v22 );
    }
    v23 = v21 - 1;
    v12 = v22 == 0 ? 0x8007007A : 0;
    v24 = v12;
    if ( v22 )
      v23 = v21;
    *v23 = 0;
    if ( !v22 )
      goto LABEL_68;
    FirstFileW = (__int64)FindFirstFileW(Dst, &FindFileData);
    if ( FirstFileW != -1 )
    {
      v25 = v37;
      while ( 1 )
      {
        v26 = FindFileData.cFileName[0];
        cFileName = FindFileData.cFileName;
        v33 = 0;
        v28 = 0;
        while ( v26 )
        {
          if ( v26 == 32 )
            goto LABEL_35;
          if ( v26 != 46 )
          {
            if ( v26 != 92 )
              goto LABEL_36;
LABEL_35:
            v28 = 0;
            goto LABEL_36;
          }
          v28 = cFileName;
LABEL_36:
          v26 = *++cFileName;
        }
        if ( !v28 )
          v28 = cFileName;
        if ( v28 )
        {
          v29 = 0;
          while ( _wcsicmp(v28, (const wchar_t *)(&g_StartupApp_Extensions)[v29]) )
          {
            if ( (unsigned int)++v29 >= 5 )
              goto LABEL_44;
          }
          ++a3[2];
          v12 = 0;
          if ( (int)SuspUtilsCheckFlags(&v33, FindFileData.cFileName, v10, v25, 1, 0) < 0
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18);
          }
          if ( (v33 & 4) != 0 )
            ++*a3;
          if ( (v33 & 2) == 0 )
          {
            if ( (v36 & 1) != 0 && (int)SuspUtilsMarkAsOEM(FindFileData.cFileName, v10, v25, 1, 0) < 0 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19);
              }
            }
            else
            {
              ++v7;
            }
          }
        }
        else
        {
LABEL_44:
          v12 = 0;
        }
        if ( !FindNextFileW((HANDLE)FirstFileW, &FindFileData) )
        {
          v4 = v38;
          FindClose((HANDLE)FirstFileW);
          v5 = v34;
          goto LABEL_62;
        }
      }
    }
    v12 = 0;
LABEL_62:
    v5 += v7;
    v8 = (unsigned int)(v35 + 1);
    v34 = v5;
    v35 = v8;
    if ( (unsigned int)v8 >= 2 )
    {
      a3[1] = v5;
      return v12;
    }
    v7 = 0;
  }
  wcscpy(String2, L"%PROAMDATA%");
  wcscpy(v40, L"%APPDATA");
  if ( !wcsncmp_0(v9, String2, 0xDu) )
  {
    v12 = ExpandOfflineFolderPath(Dst, v11, v9, L"%PROGRAMDATA%", *(const unsigned __int16 **)v4, L"ProgramData");
    if ( (v12 & 0x80000000) != 0 )
    {
      v14 = 404;
      goto LABEL_13;
    }
    goto LABEL_16;
  }
  if ( wcsncmp_0(v9, v40, 8u) )
    return 2147945410LL;
  v12 = ExpandOfflineFolderPath(
          Dst,
          v15,
          v9,
          L"%APPDATA%",
          *(const unsigned __int16 **)v4,
          L"Users\\Default\\AppData\\Roaming");
  if ( (v12 & 0x80000000) == 0 )
  {
LABEL_16:
    v9 = Dst;
    goto LABEL_17;
  }
  v14 = 408;
LABEL_13:
  wil::details::in1diag3::Return_Hr(retaddr, (void *)v14, v13, (const char *)v12, v32);
  return v12;
}

```

## disassembly

```asm
0x180002c64  mov     [rsp-8+arg_8], rbx
0x180002c69  push    rbp
0x180002c6a  push    rsi
0x180002c6b  push    rdi
0x180002c6c  push    r12
0x180002c6e  push    r13
0x180002c70  push    r14
0x180002c72  push    r15
0x180002c74  lea     rbp, [rsp-400h]
0x180002c7c  sub     rsp, 500h
0x180002c83  mov     rax, cs:__security_cookie
0x180002c8a  xor     rax, rsp
0x180002c8d  mov     [rbp+430h+var_40], rax
0x180002c94  mov     r13, r8
0x180002c97  mov     [rsp+530h+var_4F4], edx
0x180002c9b  mov     r15, rcx
0x180002c9e  mov     [rsp+530h+var_4E8], rcx
0x180002ca3  xor     edi, edi
0x180002ca5  lea     rcx, [rsp+530h+FindFileData]; void *
0x180002caa  xor     edx, edx; Val
0x180002cac  mov     [rsp+530h+var_4FC], edi
0x180002cb0  mov     r8d, 250h; Size
0x180002cb6  or      r14, 0FFFFFFFFFFFFFFFFh
0x180002cba  call    memset_0
0x180002cbf  lea     rsi, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180002cc6  mov     [rsp+530h+var_4F0], rsi
0x180002ccb  xor     esi, esi
0x180002ccd  mov     eax, esi
0x180002ccf  mov     [rsp+530h+var_4F8], eax
0x180002cd3  lea     rcx, cs:180000000h
0x180002cda  mov     rbx, ds:rva off_180006010[rcx+rax*8]; "%PROGRAMDATA%\\Microsoft\\Windows\\Star"... ...
0x180002ce2  lea     rdx, aAppdata; "APPDATA"
0x180002ce9  mov     rcx, rbx; Str
0x180002cec  call    cs:__imp_wcsstr
0x180002cf2  test    rax, rax
0x180002cf5  jz      short loc_180002D0B
0x180002cf7  test    r15, r15
0x180002cfa  jz      short loc_180002D02
0x180002cfc  mov     r12, [r15+8]
0x180002d00  jmp     short loc_180002D29
0x180002d02  mov     r12, 0FFFFFFFF80000001h
0x180002d09  jmp     short loc_180002D29
0x180002d0b  test    r15, r15
0x180002d0e  jz      short loc_180002D22
0x180002d10  mov     r12, [r15+28h]
0x180002d14  lea     rax, aMicrosoftWindo; "Microsoft\\Windows\\CurrentVersion\\Exp"...
0x180002d1b  mov     [rsp+530h+var_4F0], rax
0x180002d20  jmp     short loc_180002D29
0x180002d22  mov     r12, 0FFFFFFFF80000002h
0x180002d29  test    r15, r15
0x180002d2c  jz      loc_180002E24
0x180002d32  movups  xmm0, xmmword ptr cs:aProgramdata_0; "%PROGRAMDATA%"
0x180002d39  movzx   eax, word ptr cs:aAppdata_0+10h; ""
0x180002d40  mov     r8d, 0Dh; MaxCount
0x180002d46  movups  xmm1, xmmword ptr cs:aProgramdata_0+0Ch; "AMDATA%"
0x180002d4d  lea     rdx, [rbp+430h+String2]; String2
0x180002d54  mov     rcx, rbx; String1
0x180002d57  movups  xmmword ptr [rbp+430h+String2], xmm0
0x180002d5e  mov     [rbp+430h+var_280], ax
0x180002d65  movups  xmm0, xmmword ptr cs:aAppdata_0; "%APPDATA"
0x180002d6c  movups  xmmword ptr [rbp+430h+String2+0Ch], xmm1
0x180002d73  movups  xmmword ptr [rbp+430h+var_290], xmm0
0x180002d7a  call    wcsncmp_0
0x180002d7f  test    eax, eax
0x180002d81  jnz     short loc_180002DCC
0x180002d83  lea     rax, aProgramdata; "ProgramData"
0x180002d8a  mov     r8, rbx; unsigned __int16 *
0x180002d8d  mov     [rsp+530h+var_508], rax; unsigned __int16 *
0x180002d92  lea     r9, aProgramdata_0; "%PROGRAMDATA%"
0x180002d99  mov     rax, [r15]
0x180002d9c  lea     rcx, [rbp+430h+Dst]; pszPath
0x180002da3  mov     [rsp+530h+var_510], rax; int
0x180002da8  call    ?ExpandOfflineFolderPath@@YAJPEAGK00PEBG0@Z; ExpandOfflineFolderPath(ushort *,ulong,ushort *,ushort *,ushort const *,ushort *)
0x180002dad  mov     ebx, eax
0x180002daf  test    eax, eax
0x180002db1  jns     short loc_180002E1D
0x180002db3  mov     edx, 194h; void *
0x180002db8  mov     rcx, [rbp+438h]; this
0x180002dbf  mov     r9d, ebx; char *
0x180002dc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002dc7  jmp     loc_180003131
0x180002dcc  mov     r8d, 8; MaxCount
0x180002dd2  lea     rdx, [rbp+430h+var_290]; String2
0x180002dd9  mov     rcx, rbx; String1
0x180002ddc  call    wcsncmp_0
0x180002de1  test    eax, eax
0x180002de3  jnz     loc_18000309D
0x180002de9  lea     rax, aUsersDefaultAp; "Users\\Default\\AppData\\Roaming"
0x180002df0  mov     r8, rbx; unsigned __int16 *
0x180002df3  mov     [rsp+530h+var_508], rax; unsigned __int16 *
0x180002df8  lea     r9, aAppdata_1; "%APPDATA%"
0x180002dff  mov     rax, [r15]
0x180002e02  lea     rcx, [rbp+430h+Dst]; pszPath
0x180002e09  mov     [rsp+530h+var_510], rax; unsigned __int16 *
0x180002e0e  call    ?ExpandOfflineFolderPath@@YAJPEAGK00PEBG0@Z; ExpandOfflineFolderPath(ushort *,ulong,ushort *,ushort *,ushort const *,ushort *)
0x180002e13  mov     ebx, eax
0x180002e15  test    eax, eax
0x180002e17  js      loc_180003093
0x180002e1d  lea     rbx, [rbp+430h+Dst]
0x180002e24  mov     r8d, 104h; nSize
0x180002e2a  lea     rdx, [rbp+430h+Dst]; lpDst
0x180002e31  mov     rcx, rbx; lpSrc
0x180002e34  call    cs:__imp_ExpandEnvironmentStringsW
0x180002e3a  test    eax, eax
0x180002e3c  jz      loc_1800030E6
0x180002e42  mov     r9d, 104h
0x180002e48  lea     rax, [rbp+430h+Dst]
0x180002e4f  mov     edx, r9d
0x180002e52  cmp     [rax], si
0x180002e55  jz      short loc_180002E61
0x180002e57  add     rax, 2
0x180002e5b  sub     rdx, 1
0x180002e5f  jnz     short loc_180002E52
0x180002e61  mov     rax, rdx
0x180002e64  mov     rcx, r9
0x180002e67  neg     rax
0x180002e6a  mov     rax, rdx
0x180002e6d  sbb     ebx, ebx
0x180002e6f  sub     rcx, rdx
0x180002e72  not     ebx
0x180002e74  and     ebx, 80070057h
0x180002e7a  neg     rax
0x180002e7d  sbb     r8, r8
0x180002e80  and     r8, rcx
0x180002e83  test    rdx, rdx
0x180002e86  jz      loc_1800030B0
0x180002e8c  mov     rdx, r9
0x180002e8f  lea     rcx, asc_180006B24; "\\*"
0x180002e96  lea     r9, [rbp+430h+Dst]
0x180002e9d  mov     eax, 7FFFFFFEh
0x180002ea2  lea     r9, [r9+r8*2]
0x180002ea6  sub     rdx, r8
0x180002ea9  jz      short loc_180002ECF
0x180002eab  test    rax, rax
0x180002eae  jz      short loc_180002ECF
0x180002eb0  movzx   r8d, word ptr [rcx]
0x180002eb4  test    r8w, r8w
0x180002eb8  jz      short loc_180002ECF
0x180002eba  mov     [r9], r8w
0x180002ebe  add     rcx, 2
0x180002ec2  add     r9, 2
0x180002ec6  dec     rax
0x180002ec9  sub     rdx, 1
0x180002ecd  jnz     short loc_180002EAB
0x180002ecf  mov     rax, rdx
0x180002ed2  lea     rcx, [r9-2]
0x180002ed6  neg     rax
0x180002ed9  sbb     ebx, ebx
0x180002edb  not     ebx
0x180002edd  and     ebx, 8007007Ah
0x180002ee3  test    rdx, rdx
0x180002ee6  mov     eax, ebx
0x180002ee8  cmovnz  rcx, r9
0x180002eec  mov     [rcx], si
0x180002eef  jz      loc_1800030B2
0x180002ef5  lea     rdx, [rsp+530h+FindFileData]; lpFindFileData
0x180002efa  lea     rcx, [rbp+430h+Dst]; lpFileName
0x180002f01  call    cs:__imp_FindFirstFileW
0x180002f07  mov     r14, rax
0x180002f0a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180002f0e  jz      loc_180003075
0x180002f14  mov     r15, [rsp+530h+var_4F0]
0x180002f19  movzx   ecx, [rsp+530h+FindFileData.cFileName]
0x180002f1e  lea     rdx, [rsp+530h+FindFileData.cFileName]
0x180002f23  xor     eax, eax
0x180002f25  mov     [rsp+530h+var_500], eax
0x180002f29  mov     ebx, eax
0x180002f2b  jmp     short loc_180002F49
0x180002f2d  cmp     cx, 20h ; ' '
0x180002f31  jz      short loc_180002F3F
0x180002f33  cmp     cx, 2Eh ; '.'
0x180002f37  jz      short loc_180002FAC
0x180002f39  cmp     cx, 5Ch ; '\'
0x180002f3d  jnz     short loc_180002F42
0x180002f3f  mov     rbx, rax
0x180002f42  add     rdx, 2
0x180002f46  movzx   ecx, word ptr [rdx]
0x180002f49  test    cx, cx
0x180002f4c  jnz     short loc_180002F2D
0x180002f4e  test    rbx, rbx
0x180002f51  cmovz   rbx, rdx
0x180002f55  test    rbx, rbx
0x180002f58  jz      short loc_180002F81
0x180002f5a  mov     edi, eax
0x180002f5c  lea     rax, cs:180000000h
0x180002f63  mov     edx, edi
0x180002f65  mov     rcx, rbx; String1
0x180002f68  mov     rdx, ds:rva ?g_StartupApp_Extensions@@3PAPEBGA[rax+rdx*8]; String2
0x180002f70  call    cs:__imp__wcsicmp
0x180002f76  test    eax, eax
0x180002f78  jz      short loc_180002FB1
0x180002f7a  inc     edi
0x180002f7c  cmp     edi, 5
0x180002f7f  jb      short loc_180002F5C
0x180002f81  xor     ebx, ebx
0x180002f83  lea     rdx, [rsp+530h+FindFileData]; lpFindFileData
0x180002f88  mov     rcx, r14; hFindFile
0x180002f8b  call    cs:__imp_FindNextFileW
0x180002f91  test    eax, eax
0x180002f93  jnz     short loc_180002F19
0x180002f95  mov     r15, [rsp+530h+var_4E8]
0x180002f9a  mov     rcx, r14; hFindFile
0x180002f9d  call    cs:__imp_FindClose
0x180002fa3  mov     edi, [rsp+530h+var_4FC]
0x180002fa7  jmp     loc_180003077
0x180002fac  mov     rbx, rdx
0x180002faf  jmp     short loc_180002F42
0x180002fb1  mov     edi, 1
0x180002fb6  lea     rdx, [rsp+530h+FindFileData.cFileName]
0x180002fbb  add     [r13+8], edi
0x180002fbf  lea     rcx, [rsp+530h+var_500]
0x180002fc4  xor     ebx, ebx
0x180002fc6  mov     r9, r15
0x180002fc9  mov     dword ptr [rsp+530h+var_508], ebx
0x180002fcd  mov     r8, r12
0x180002fd0  mov     dword ptr [rsp+530h+var_510], edi
0x180002fd4  call    ?SuspUtilsCheckFlags@@YAJPEAKPEAGPEAUHKEY__@@PEBGW4_SUS_STARTUP_TYPE@@H@Z; SuspUtilsCheckFlags(ulong *,ushort *,HKEY__ *,ushort const *,_SUS_STARTUP_TYPE,int)
0x180002fd9  test    eax, eax
0x180002fdb  jns     short loc_180003002
0x180002fdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180002fe4  lea     rax, WPP_GLOBAL_Control
0x180002feb  cmp     rcx, rax
0x180002fee  jz      short loc_180003002
0x180002ff0  test    byte ptr [rcx+1Ch], 4
0x180002ff4  jz      short loc_180003002
0x180002ff6  mov     rcx, [rcx+10h]
0x180002ffa  lea     edx, [rdi+11h]
0x180002ffd  call    WPP_SF_
0x180003002  test    byte ptr [rsp+530h+var_500], 4
0x180003007  jz      short loc_18000300D
0x180003009  add     [r13+0], edi
0x18000300d  test    byte ptr [rsp+530h+var_500], 2
0x180003012  jnz     loc_180002F83
0x180003018  test    byte ptr [rsp+530h+var_4F4], dil
0x18000301d  jz      short loc_18000306E
0x18000301f  mov     r9d, edi
0x180003022  mov     dword ptr [rsp+530h+var_510], ebx
0x180003026  mov     r8, r15
0x180003029  lea     rcx, [rsp+530h+FindFileData.cFileName]
0x18000302e  mov     rdx, r12
0x180003031  call    ?SuspUtilsMarkAsOEM@@YAJPEAGPEAUHKEY__@@PEBGW4_SUS_STARTUP_TYPE@@H@Z; SuspUtilsMarkAsOEM(ushort *,HKEY__ *,ushort const *,_SUS_STARTUP_TYPE,int)
0x180003036  test    eax, eax
0x180003038  jns     short loc_18000306E
0x18000303a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003041  lea     rax, WPP_GLOBAL_Control
0x180003048  cmp     rcx, rax
0x18000304b  jz      loc_180002F83
0x180003051  test    [rcx+1Ch], dil
0x180003055  jz      loc_180002F83
0x18000305b  mov     rcx, [rcx+10h]
0x18000305f  mov     edx, 13h
0x180003064  call    WPP_SF_
0x180003069  jmp     loc_180002F83
0x18000306e  add     esi, edi
0x180003070  jmp     loc_180002F83
0x180003075  xor     ebx, ebx
0x180003077  mov     eax, [rsp+530h+var_4F8]
0x18000307b  add     edi, esi
0x18000307d  inc     eax
0x18000307f  mov     [rsp+530h+var_4FC], edi
0x180003083  mov     [rsp+530h+var_4F8], eax
0x180003087  cmp     eax, 2
0x18000308a  jnb     short loc_1800030A7
0x18000308c  xor     esi, esi
0x18000308e  jmp     loc_180002CD3
0x180003093  mov     edx, 198h
0x180003098  jmp     loc_180002DB8
0x18000309d  mov     eax, 80070BC2h
0x1800030a2  jmp     loc_180003133
0x1800030a7  mov     [r13+4], edi
0x1800030ab  jmp     loc_180003131
0x1800030b0  mov     eax, ebx
0x1800030b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800030b9  lea     rdx, WPP_GLOBAL_Control
0x1800030c0  cmp     rcx, rdx
0x1800030c3  jz      short loc_180003122
0x1800030c5  test    byte ptr [rcx+1Ch], 1
0x1800030c9  jz      short loc_180003122
0x1800030cb  mov     rcx, [rcx+10h]
0x1800030cf  lea     r8, WPP_91e8665fb8f03560ae482285a745ac49_Traceguids
0x1800030d6  movzx   r9d, ax
0x1800030da  mov     edx, 11h
0x1800030df  call    WPP_SF_D
0x1800030e4  jmp     short loc_180003122
0x1800030e6  call    cs:__imp_GetLastError
0x1800030ec  mov     ebx, eax
0x1800030ee  test    eax, eax
0x1800030f0  jle     short loc_1800030FB
0x1800030f2  movzx   ebx, ax
0x1800030f5  or      ebx, 80070000h
0x1800030fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180003102  lea     rax, WPP_GLOBAL_Control
0x180003109  cmp     rcx, rax
0x18000310c  jz      short loc_180003122
0x18000310e  test    byte ptr [rcx+1Ch], 1
0x180003112  jz      short loc_180003122
0x180003114  mov     rcx, [rcx+10h]
0x180003118  mov     edx, 10h
0x18000311d  call    WPP_SF_
0x180003122  cmp     r14, 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```
