# VerifyCOMServerByClsid(_GUID const &,ushort *,long,long *)

- ea: `0x180042bb8`
- end: `0x1800431b5`
- name: `?VerifyCOMServerByClsid@@YAJAEBU_GUID@@PEAGJPEAJ@Z`
- size: `1533`
- prototype: `__int64 __fastcall(const struct _GUID *, unsigned __int16 *, __int64, int *)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180056590`

## callees

- `0x180005fa0`
- `0x18000c348`
- `0x18000f518`
- `0x18000f5a0`
- `0x1800133fc`
- `0x18001b414`
- `0x18001bd24`
- `0x18001c854`
- `0x18001c96c`
- `0x180028d5c`
- `0x180028e5c`
- `0x180028eb4`
- `0x18002af88`
- `0x18002d02c`
- `0x18003ccec`
- `0x180042bb8`
- `0x1800431bc`
- `0x180044f30`
- `0x180045900`
- `0x180051a1c`
- `0x180051c38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042f51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004300e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042f51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004300e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042deb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042ea7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042deb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042ea7`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18004308b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18004308b`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x180042d88`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x180042d88`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180042f44`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180043004`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180042f44`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180043004`

## string_xrefs

- `0x180042d20`: `CLSID\{%08lX-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}\InprocServer32`

## pseudocode

```c
__int64 __fastcall VerifyCOMServerByClsid(const struct _GUID *a1, unsigned __int16 *a2, __int64 a3, int *a4)
{
  char v4; // r15
  GuidTrace *v6; // rcx
  const char *String; // rax
  int i; // edx
  __int64 *v9; // rax
  __int64 v10; // rcx
  signed int v11; // esi
  int v12; // eax
  __int64 v13; // rdx
  LSTATUS v14; // eax
  __int64 v15; // rdx
  LSTATUS Value; // eax
  int v17; // ecx
  bool v18; // cc
  __int64 unique; // rax
  BYTE *lpData; // rbx
  LSTATUS v21; // eax
  DWORD v22; // eax
  __int64 v23; // r12
  signed int LastError; // eax
  __int64 v25; // rdx
  __int64 v26; // rax
  WCHAR *v27; // rdi
  signed int v28; // eax
  FileTimeTrace *v29; // rax
  const char *v30; // rax
  int v31; // edx
  int v32; // r8d
  __int64 v33; // rdx
  __int64 cbData; // [rsp+70h] [rbp-90h] BYREF
  LPWSTR lpDst; // [rsp+78h] [rbp-88h] BYREF
  LPBYTE v37; // [rsp+80h] [rbp-80h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp-78h] BYREF
  __int64 FirstFileW; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v40[8]; // [rsp+98h] [rbp-68h] BYREF
  void **v41; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v42[24]; // [rsp+A8h] [rbp-58h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR SubKey[264]; // [rsp+310h] [rbp+210h] BYREF

  v4 = 0;
  phkResult = 0;
  memset_0(SubKey, 0, 0x208u);
  v37 = 0;
  cbData = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = -1;
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    v6 = GuidTrace::GuidTrace((GuidTrace *)&v41, a1);
    String = (const char *)*((_QWORD *)v6 + 3);
    if ( !String )
      String = FSString::GetString(v6);
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 27), 240, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, String);
    v4 = 1;
  }
  if ( (v4 & 1) != 0 )
  {
    v4 &= ~1u;
    FSString::~FSString((FSString *)&v41);
  }
  for ( i = 0; (unsigned __int64)i < 2; ++i )
  {
    v9 = &qword_18007D550[2 * i];
    v10 = *(_QWORD *)&a1->Data1 - *v9;
    if ( *(_QWORD *)&a1->Data1 == *v9 )
      v10 = *(_QWORD *)a1->Data4 - v9[1];
    if ( !v10 )
    {
      v11 = 0;
      goto LABEL_82;
    }
  }
  v12 = StringCchPrintfW(
          SubKey,
          0x103u,
          L"CLSID\\{%08lX-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}\\InprocServer32",
          a1->Data1,
          a1->Data2,
          a1->Data3,
          a1->Data4[0],
          a1->Data4[1],
          a1->Data4[2],
          a1->Data4[3],
          a1->Data4[4],
          a1->Data4[5],
          a1->Data4[6],
          a1->Data4[7],
          cbData);
  v11 = v12;
  if ( v12 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_79;
    v13 = 241;
    goto LABEL_17;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v14 = RegOpenKeyW(HKEY_CLASSES_ROOT, SubKey, &phkResult);
  if ( v14 )
  {
    if ( v14 > 0 )
      v11 = (unsigned __int16)v14 | 0x80070000;
    else
      v11 = v14;
    if ( g_wppLevels >= 8u )
    {
      v15 = 242;
LABEL_78:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, 0, v11);
      goto LABEL_79;
    }
    goto LABEL_79;
  }
  LODWORD(cbData) = 0;
  Value = RegQueryValueExW(phkResult, &cchOriginalDestLength, 0, (LPDWORD)&cbData + 1, 0, (LPDWORD)&cbData);
  v17 = cbData;
  v18 = Value <= 0;
  if ( !Value )
  {
    if ( (unsigned int)cbData >= 2 )
      goto LABEL_33;
    v18 = 1;
  }
  if ( v18 )
    v11 = Value;
  else
    v11 = (unsigned __int16)Value | 0x80070000;
  if ( v11 < 0 )
  {
    if ( g_wppLevels < 8u )
      goto LABEL_79;
    v15 = 243;
    goto LABEL_78;
  }
LABEL_33:
  LODWORD(cbData) = cbData + 2;
  unique = wil::make_unique_nothrow<unsigned char [0]>(&lpDst, (unsigned int)(v17 + 2));
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::operator=(&v37, unique);
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&lpDst);
  lpData = v37;
  if ( !v37 )
  {
    v12 = -2147024882;
    v11 = -2147024882;
    if ( g_wppLevels )
    {
      v13 = 244;
LABEL_17:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, 0, v12);
      goto LABEL_79;
    }
    goto LABEL_79;
  }
  memset_0(v37, 0, (unsigned int)cbData);
  v21 = RegQueryValueExW(phkResult, &cchOriginalDestLength, 0, (LPDWORD)&cbData + 1, lpData, (LPDWORD)&cbData);
  if ( v21 )
  {
    if ( v21 > 0 )
      v11 = (unsigned __int16)v21 | 0x80070000;
    else
      v11 = v21;
    if ( g_wppLevels >= 8u )
    {
      v15 = 245;
      goto LABEL_78;
    }
LABEL_79:
    if ( byte_18008D62D )
    {
      v33 = 255;
      goto LABEL_81;
    }
    goto LABEL_82;
  }
  if ( (unsigned __int8)byte_18008D62D >= 8u )
    WPP_SF_dS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      246,
      (unsigned int)&WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids,
      HIDWORD(cbData),
      (__int64)lpData);
  if ( HIDWORD(cbData) == 2 )
  {
    lpDst = 0;
    v22 = ExpandEnvironmentStringsW((LPCWSTR)lpData, 0, 0);
    v23 = v22;
    if ( v22 )
      goto LABEL_55;
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( v11 >= 0 )
    {
LABEL_55:
      v26 = wil::make_unique_nothrow<unsigned char [0]>(v40, 2 * v23);
      wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::operator=(&lpDst, v26);
      wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(v40);
      v27 = lpDst;
      if ( !lpDst )
      {
        v11 = -2147024882;
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            249,
            &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids,
            0,
            -2147024882);
        goto LABEL_58;
      }
      memset_0(lpDst, 0, 2 * v23);
      if ( ExpandEnvironmentStringsW((LPCWSTR)lpData, v27, v23) )
        goto LABEL_65;
      v28 = GetLastError();
      v11 = v28;
      if ( v28 > 0 )
        v11 = (unsigned __int16)v28 | 0x80070000;
      if ( v11 >= 0 )
      {
LABEL_65:
        if ( (unsigned __int8)byte_18008D62D >= 8u )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 27), 251, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, v27);
        wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::swap(&v37, &lpDst);
        wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&lpDst);
        lpData = v37;
        goto LABEL_68;
      }
      if ( g_wppLevels )
      {
        v25 = 250;
        goto LABEL_54;
      }
    }
    else if ( g_wppLevels )
    {
      v25 = 248;
LABEL_54:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v25, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, 0, v11);
    }
LABEL_58:
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&lpDst);
    goto LABEL_79;
  }
  if ( HIDWORD(cbData) != 1 )
  {
    v11 = -2147024883;
    if ( !g_wppLevels )
      goto LABEL_79;
    v15 = 247;
    goto LABEL_78;
  }
LABEL_68:
  FirstFileW = (__int64)FindFirstFileW((LPCWSTR)lpData, &FindFileData);
  if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v11 = -1072875819;
    if ( g_wppLevels < 8u )
      goto LABEL_79;
    v15 = 252;
    goto LABEL_78;
  }
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    v4 |= 2u;
    v29 = FileTimeTrace::FileTimeTrace(
            (FileTimeTrace *)&v41,
            (const union _ULARGE_INTEGER *)&FindFileData.ftCreationTime);
    v30 = FSString::GetString((FileTimeTrace *)((char *)v29 + 8));
    WPP_SF_Ssd(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      v31,
      v32,
      (unsigned int)FindFileData.cFileName,
      (__int64)v30,
      FindFileData.nFileSizeLow);
  }
  if ( (v4 & 2) != 0 )
  {
    v41 = &BlobTrace::`vftable';
    FSString::~FSString((FSString *)v42);
  }
  if ( v11 < 0 )
    goto LABEL_79;
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    v33 = 256;
LABEL_81:
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      v33,
      &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids,
      (unsigned int)v11);
  }
LABEL_82:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&FirstFileW);
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v37);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180042bb8  mov     [rsp-8+arg_8], rbx
0x180042bbd  mov     [rsp-8+arg_10], rsi
0x180042bc2  push    rbp
0x180042bc3  push    rdi
0x180042bc4  push    r12
0x180042bc6  push    r14
0x180042bc8  push    r15
0x180042bca  lea     rbp, [rsp-430h]
0x180042bd2  sub     rsp, 530h
0x180042bd9  mov     rax, cs:__security_cookie
0x180042be0  xor     rax, rsp
0x180042be3  mov     [rbp+450h+var_30], rax
0x180042bea  xor     r15d, r15d
0x180042bed  mov     r14, rcx
0x180042bf0  mov     [rsp+550h+Type], r15d
0x180042bf5  lea     rcx, [rbp+450h+SubKey]; void *
0x180042bfc  xor     edx, edx; Val
0x180042bfe  mov     [rbp+450h+phkResult], r15
0x180042c02  mov     r8d, 208h; Size
0x180042c08  call    memset_0
0x180042c0d  xor     edx, edx; Val
0x180042c0f  mov     [rbp+450h+var_4D0], r15
0x180042c13  mov     r8d, 250h; Size
0x180042c19  mov     [rsp+550h+cbData], r15d
0x180042c1e  lea     rcx, [rbp+450h+FindFileData]; void *
0x180042c22  mov     [rsp+550h+Type], r15d
0x180042c27  call    memset_0
0x180042c2c  mov     [rbp+450h+var_4C0], 0FFFFFFFFFFFFFFFFh
0x180042c34  cmp     cs:byte_18008D62D, 8
0x180042c3b  lea     r12, WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids
0x180042c42  jb      short loc_180042C85
0x180042c44  mov     rdx, r14; struct _GUID *
0x180042c47  lea     rcx, [rbp+450h+var_4B0]; this
0x180042c4b  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x180042c50  mov     rcx, rax; this
0x180042c53  mov     rax, [rax+18h]
0x180042c57  test    rax, rax
0x180042c5a  jnz     short loc_180042C61
0x180042c5c  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x180042c61  mov     rcx, cs:WPP_GLOBAL_Control
0x180042c68  mov     edx, 0F0h
0x180042c6d  mov     r9, rax
0x180042c70  mov     r8, r12
0x180042c73  mov     rcx, [rcx+0D8h]
0x180042c7a  call    WPP_SF_s
0x180042c7f  mov     r15d, 1
0x180042c85  test    r15b, 1
0x180042c89  jz      short loc_180042C98
0x180042c8b  and     r15d, 0FFFFFFFEh
0x180042c8f  lea     rcx, [rbp+450h+var_4B0]; this
0x180042c93  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180042c98  xor     edx, edx
0x180042c9a  movsxd  rax, edx
0x180042c9d  cmp     rax, 2
0x180042ca1  jnb     short loc_180042CD1
0x180042ca3  shl     rax, 4
0x180042ca7  lea     rcx, qword_18007D550
0x180042cae  add     rax, rcx
0x180042cb1  mov     rcx, [r14]
0x180042cb4  sub     rcx, [rax]
0x180042cb7  jnz     short loc_180042CC1
0x180042cb9  mov     rcx, [r14+8]
0x180042cbd  sub     rcx, [rax+8]
0x180042cc1  test    rcx, rcx
0x180042cc4  jz      short loc_180042CCA
0x180042cc6  inc     edx
0x180042cc8  jmp     short loc_180042C9A
0x180042cca  xor     esi, esi
0x180042ccc  jmp     loc_18004316D
0x180042cd1  movzx   ecx, byte ptr [r14+0Eh]
0x180042cd6  movzx   edx, byte ptr [r14+0Dh]
0x180042cdb  movzx   r8d, byte ptr [r14+0Ch]
0x180042ce0  movzx   r9d, byte ptr [r14+0Bh]
0x180042ce5  movzx   eax, byte ptr [r14+0Fh]
0x180042cea  movzx   r10d, byte ptr [r14+0Ah]
0x180042cef  movzx   r11d, byte ptr [r14+9]
0x180042cf4  movzx   ebx, byte ptr [r14+8]
0x180042cf9  movzx   edi, word ptr [r14+6]
0x180042cfe  movzx   esi, word ptr [r14+4]
0x180042d03  mov     [rsp+550h+var_4E8], eax
0x180042d07  mov     [rsp+550h+var_4F0], ecx
0x180042d0b  lea     rcx, [rbp+450h+SubKey]; unsigned __int16 *
0x180042d12  mov     [rsp+550h+var_4F8], edx
0x180042d16  mov     edx, 103h; unsigned __int64
0x180042d1b  mov     [rsp+550h+var_500], r8d
0x180042d20  lea     r8, aClsid08lx04x04; "CLSID\\{%08lX-%04X-%04X-%02X%02X-%02X%0"...
0x180042d27  mov     [rsp+550h+var_508], r9d
0x180042d2c  mov     r9d, [r14]
0x180042d2f  mov     [rsp+550h+var_510], r10d
0x180042d34  mov     [rsp+550h+var_518], r11d
0x180042d39  mov     [rsp+550h+var_520], ebx
0x180042d3d  mov     dword ptr [rsp+550h+lpcbData], edi
0x180042d41  mov     dword ptr [rsp+550h+lpData], esi
0x180042d45  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180042d4a  mov     esi, eax
0x180042d4c  test    eax, eax
0x180042d4e  jns     short loc_180042D6B
0x180042d50  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180042d57  jb      loc_180043142
0x180042d5d  mov     edx, 0F1h
0x180042d62  mov     dword ptr [rsp+550h+lpData], eax
0x180042d66  jmp     loc_18004312C
0x180042d6b  xor     edx, edx
0x180042d6d  lea     rcx, [rbp+450h+phkResult]
0x180042d71  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180042d76  lea     r8, [rbp+450h+phkResult]; phkResult
0x180042d7a  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180042d81  lea     rdx, [rbp+450h+SubKey]; lpSubKey
0x180042d88  call    cs:__imp_RegOpenKeyW
0x180042d8e  mov     edi, 80070000h
0x180042d93  test    eax, eax
0x180042d95  jz      short loc_180042DBD
0x180042d97  jg      short loc_180042D9D
0x180042d99  mov     esi, eax
0x180042d9b  jmp     short loc_180042DA2
0x180042d9d  movzx   esi, ax
0x180042da0  or      esi, edi
0x180042da2  test    esi, esi
0x180042da4  jns     short loc_180042DBD
0x180042da6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x180042dad  jb      loc_180043142
0x180042db3  mov     edx, 0F2h
0x180042db8  jmp     loc_180043128
0x180042dbd  mov     rcx, [rbp+450h+phkResult]; hKey
0x180042dc1  lea     rax, [rsp+550h+cbData]
0x180042dc6  mov     [rsp+550h+lpcbData], rax; lpcbData
0x180042dcb  lea     r9, [rsp+550h+Type]; lpType
0x180042dd0  xor     r8d, r8d; lpReserved
0x180042dd3  mov     [rsp+550h+lpData], 0; lpData
0x180042ddc  lea     rdx, cchOriginalDestLength; lpValueName
0x180042de3  mov     [rsp+550h+cbData], 0
0x180042deb  call    cs:__imp_RegQueryValueExW
0x180042df1  mov     ecx, [rsp+550h+cbData]
0x180042df5  test    eax, eax
0x180042df7  jnz     short loc_180042E00
0x180042df9  cmp     ecx, 2
0x180042dfc  jnb     short loc_180042E26
0x180042dfe  test    eax, eax
0x180042e00  jg      short loc_180042E06
0x180042e02  mov     esi, eax
0x180042e04  jmp     short loc_180042E0B
0x180042e06  movzx   esi, ax
0x180042e09  or      esi, edi
0x180042e0b  test    esi, esi
0x180042e0d  jns     short loc_180042E26
0x180042e0f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x180042e16  jb      loc_180043142
0x180042e1c  mov     edx, 0F3h
0x180042e21  jmp     loc_180043128
0x180042e26  add     ecx, 2
0x180042e29  mov     [rsp+550h+cbData], ecx
0x180042e2d  mov     edx, ecx
0x180042e2f  lea     rcx, [rsp+550h+lpDst]
0x180042e34  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x180042e39  mov     rdx, rax
0x180042e3c  lea     rcx, [rbp+450h+var_4D0]
0x180042e40  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::operator=(wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &&)
0x180042e45  lea     rcx, [rsp+550h+lpDst]
0x180042e4a  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x180042e4f  mov     rbx, [rbp+450h+var_4D0]
0x180042e53  test    rbx, rbx
0x180042e56  jnz     short loc_180042E76
0x180042e58  mov     eax, 8007000Eh
0x180042e5d  mov     esi, eax
0x180042e5f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180042e66  jb      loc_180043142
0x180042e6c  mov     edx, 0F4h
0x180042e71  jmp     loc_180042D62
0x180042e76  mov     r8d, [rsp+550h+cbData]; Size
0x180042e7b  xor     edx, edx; Val
0x180042e7d  mov     rcx, rbx; void *
0x180042e80  call    memset_0
0x180042e85  mov     rcx, [rbp+450h+phkResult]; hKey
0x180042e89  lea     rax, [rsp+550h+cbData]
0x180042e8e  mov     [rsp+550h+lpcbData], rax; lpcbData
0x180042e93  lea     r9, [rsp+550h+Type]; lpType
0x180042e98  xor     r8d, r8d; lpReserved
0x180042e9b  mov     [rsp+550h+lpData], rbx; lpData
0x180042ea0  lea     rdx, cchOriginalDestLength; lpValueName
0x180042ea7  call    cs:__imp_RegQueryValueExW
0x180042ead  test    eax, eax
0x180042eaf  jz      short loc_180042ED7
0x180042eb1  jg      short loc_180042EB7
0x180042eb3  mov     esi, eax
0x180042eb5  jmp     short loc_180042EBC
0x180042eb7  movzx   esi, ax
0x180042eba  or      esi, edi
0x180042ebc  test    esi, esi
0x180042ebe  jns     short loc_180042ED7
0x180042ec0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x180042ec7  jb      loc_180043142
0x180042ecd  mov     edx, 0F5h
0x180042ed2  jmp     loc_180043128
0x180042ed7  cmp     cs:byte_18008D62D, 8
0x180042ede  jb      short loc_180042F05
0x180042ee0  mov     rcx, cs:WPP_GLOBAL_Control
0x180042ee7  mov     edx, 0F6h
0x180042eec  mov     r9d, [rsp+550h+Type]
0x180042ef1  mov     r8, r12
0x180042ef4  mov     [rsp+550h+lpData], rbx
0x180042ef9  mov     rcx, [rcx+0D8h]
0x180042f00  call    WPP_SF_dS
0x180042f05  cmp     [rsp+550h+Type], 2
0x180042f0a  jz      short loc_180042F33
0x180042f0c  cmp     [rsp+550h+Type], 1
0x180042f11  jz      loc_180043084
0x180042f17  mov     esi, 8007000Dh
0x180042f1c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180042f23  jb      loc_180043142
0x180042f29  mov     edx, 0F7h
0x180042f2e  jmp     loc_180043128
0x180042f33  xor     r8d, r8d; nSize
0x180042f36  mov     [rsp+550h+lpDst], 0
0x180042f3f  xor     edx, edx; lpDst
0x180042f41  mov     rcx, rbx; lpSrc
0x180042f44  call    cs:__imp_ExpandEnvironmentStringsW
0x180042f4a  mov     r12d, eax
0x180042f4d  test    eax, eax
0x180042f4f  jnz     short loc_180042F7A
0x180042f51  call    cs:__imp_GetLastError
0x180042f57  mov     esi, eax
0x180042f59  test    eax, eax
0x180042f5b  jle     short loc_180042F62
0x180042f5d  movzx   esi, ax
0x180042f60  or      esi, edi
0x180042f62  test    esi, esi
0x180042f64  jns     short loc_180042F7A
0x180042f66  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180042f6d  jb      short loc_180042FDF
0x180042f6f  mov     edx, 0F8h
0x180042f74  mov     dword ptr [rsp+550h+lpData], esi
0x180042f78  jmp     short loc_180042FC5
0x180042f7a  mov     r14, r12
0x180042f7d  lea     rcx, [rbp+450h+var_4B8]
0x180042f81  add     r14, r14
0x180042f84  mov     rdx, r14
0x180042f87  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x180042f8c  mov     rdx, rax
0x180042f8f  lea     rcx, [rsp+550h+lpDst]
0x180042f94  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::operator=(wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &&)
0x180042f99  lea     rcx, [rbp+450h+var_4B8]
0x180042f9d  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x180042fa2  mov     rdi, [rsp+550h+lpDst]
0x180042fa7  test    rdi, rdi
0x180042faa  jnz     short loc_180042FEE
0x180042fac  mov     eax, 8007000Eh
0x180042fb1  mov     esi, eax
0x180042fb3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180042fba  jb      short loc_180042FDF
0x180042fbc  mov     edx, 0F9h
0x180042fc1  mov     dword ptr [rsp+550h+lpData], eax
0x180042fc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180042fcc  lea     r8, WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids
0x180042fd3  xor     r9d, r9d
0x180042fd6  mov     rcx, [rcx+10h]
0x180042fda  call    WPP_SF_qD
0x180042fdf  lea     rcx, [rsp+550h+lpDst]
0x180042fe4  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x180042fe9  jmp     loc_180043142
0x180042fee  mov     r8, r14; Size
0x180042ff1  xor     edx, edx; Val
0x180042ff3  mov     rcx, rdi; void *
0x180042ff6  call    memset_0
0x180042ffb  mov     r8d, r12d; nSize
0x180042ffe  mov     rdx, rdi; lpDst
0x180043001  mov     rcx, rbx; lpSrc
0x180043004  call    cs:__imp_ExpandEnvironmentStringsW
0x18004300a  test    eax, eax
0x18004300c  jnz     short loc_18004303A
0x18004300e  call    cs:__imp_GetLastError
0x180043014  mov     esi, eax
0x180043016  test    eax, eax
0x180043018  jle     short loc_180043023
0x18004301a  movzx   esi, ax
0x18004301d  or      esi, 80070000h
0x180043023  test    esi, esi
0x180043025  jns     short loc_18004303A
0x180043027  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004302e  jb      short loc_180042FDF
0x180043030  mov     edx, 0FAh
0x180043035  jmp     loc_180042F74
0x18004303a  cmp     cs:byte_18008D62D, 8
0x180043041  lea     r12, WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids
0x180043048  jb      short loc_180043068
0x18004304a  mov     rcx, cs:WPP_GLOBAL_Control
0x180043051  mov     edx, 0FBh
0x180043056  mov     r9, rdi
0x180043059  mov     r8, r12
0x18004305c  mov     rcx, [rcx+0D8h]
0x180043063  call    WPP_SF_S
0x180043068  lea     rdx, [rsp+550h+lpDst]
0x18004306d  lea     rcx, [rbp+450h+var_4D0]
0x180043071  call    ?swap@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAXAEAV12@@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::swap(wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &)
0x180043076  lea     rcx, [rsp+550h+lpDst]
0x18004307b  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x180043080  mov     rbx, [rbp+450h+var_4D0]
0x180043084  lea     rdx, [rbp+450h+FindFileData]; lpFindFileData
0x180043088  mov     rcx, rbx; lpFileName
0x18004308b  call    cs:__imp_FindFirstFileW
0x180043091  mov     [rbp+450h+var_4C0], rax
  ... truncated ...
```
