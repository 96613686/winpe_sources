# CSettings::LoadSettings(wchar_t const *,wchar_t const *,_WER_CONSENT)

- ea: `0x18000b1f4`
- end: `0x18000b815`
- name: `?LoadSettings@CSettings@@QEAAJPEB_W0W4_WER_CONSENT@@@Z`
- size: `1569`
- prototype: `__int64 __fastcall(CSettings *__hidden this, const wchar_t *, const wchar_t *, enum _WER_CONSENT)`
- caller_count: `12`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009990`
- `0x1800316d0`
- `0x180044230`
- `0x18004ad34`
- `0x18006566c`
- `0x1800663f0`
- `0x180068950`
- `0x180069a50`
- `0x180069ea0`
- `0x18006a180`
- `0x18006ad10`
- `0x180072114`

## callees

- `0x180006e84`
- `0x180009ad4`
- `0x18000b1f4`
- `0x18000b820`
- `0x18000b880`
- `0x18000c390`
- `0x18000d590`
- `0x180021634`
- `0x1800293ac`
- `0x18006200c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b6d8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b78f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b6d8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b78f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b3a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b413`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b487`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b4e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b5d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b625`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b702`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b7b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b7f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b3a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b413`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b487`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b4e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b5d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b625`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b702`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b7b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b7f9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b3cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b432`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b4ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b4ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b602`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b644`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b69c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b75e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b3cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b432`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b4ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b4ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b602`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b644`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b69c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b75e`

## string_xrefs

- `0x18000b253`: `BrokerUp`

## pseudocode

```c
__int64 __fastcall CSettings::LoadSettings(CSettings *this, const wchar_t *a2, const wchar_t *a3, enum _WER_CONSENT a4)
{
  HKEY v4; // r14
  const wchar_t *v7; // rax
  const wchar_t *v8; // r8
  __int64 v9; // rdx
  CSettings *v10; // rcx
  unsigned int i; // esi
  int v12; // edi
  unsigned int j; // esi
  HKEY v14; // rcx
  unsigned int v15; // r8d
  unsigned int *v16; // r9
  HKEY v17; // rcx
  CRegSetting *v18; // rdi
  bool v19; // zf
  _BYTE *v20; // rsi
  unsigned int v21; // r8d
  unsigned int *v22; // r9
  unsigned int DwordData; // eax
  HKEY v24; // rcx
  unsigned int v25; // r8d
  unsigned int *v26; // r9
  HKEY v27; // rcx
  HKEY v28; // rsi
  __int64 k; // rdi
  unsigned int m; // esi
  int v31; // r15d
  __int64 v32; // r12
  __int64 v33; // rdi
  char v34; // al
  HKEY v35; // rcx
  unsigned int v36; // r8d
  unsigned int *v37; // r9
  HKEY v38; // rcx
  __int64 v39; // rdx
  unsigned int v40; // r8d
  unsigned int *v41; // r9
  LSTATUS v42; // eax
  bool v43; // sf
  bool v44; // cc
  LSTATUS ValueW; // eax
  int v46; // edi
  LSTATUS v47; // eax
  bool v48; // sf
  bool v49; // cc
  LSTATUS v50; // eax
  int v51; // edi
  unsigned int phkResult; // [rsp+20h] [rbp-A9h]
  unsigned int phkResulta; // [rsp+20h] [rbp-A9h]
  unsigned int phkResultb; // [rsp+20h] [rbp-A9h]
  unsigned int phkResultc; // [rsp+20h] [rbp-A9h]
  unsigned int phkResultd; // [rsp+20h] [rbp-A9h]
  bool pvData; // [rsp+28h] [rbp-A1h]
  _DWORD v59[2]; // [rsp+40h] [rbp-89h]
  const wchar_t *v60; // [rsp+48h] [rbp-81h]
  const wchar_t *v61; // [rsp+50h] [rbp-79h]
  _DWORD v62[2]; // [rsp+58h] [rbp-71h]
  __int64 v63; // [rsp+60h] [rbp-69h]
  int v64; // [rsp+68h] [rbp-61h]
  const wchar_t *v65; // [rsp+70h] [rbp-59h]
  const wchar_t *v66; // [rsp+78h] [rbp-51h]
  int v67; // [rsp+80h] [rbp-49h]
  __int64 v68; // [rsp+88h] [rbp-41h]
  int v69; // [rsp+90h] [rbp-39h]
  const wchar_t *v70; // [rsp+98h] [rbp-31h]
  const wchar_t *v71; // [rsp+A0h] [rbp-29h]
  int v72; // [rsp+A8h] [rbp-21h]
  __int64 v73; // [rsp+B0h] [rbp-19h]
  int v74; // [rsp+B8h] [rbp-11h]
  const wchar_t *v75; // [rsp+C0h] [rbp-9h]
  const wchar_t *v76; // [rsp+C8h] [rbp-1h]
  int v77; // [rsp+D0h] [rbp+7h]
  __int64 v78; // [rsp+D8h] [rbp+Fh]
  DWORD pcbData; // [rsp+130h] [rbp+67h] BYREF
  HKEY hKey; // [rsp+138h] [rbp+6Fh] BYREF
  HKEY hkey; // [rsp+140h] [rbp+77h] BYREF
  int v82; // [rsp+148h] [rbp+7Fh] BYREF

  v4 = 0;
  hKey = 0;
  v7 = 0;
  if ( a3 )
  {
    v7 = UtilPathTail(a3);
    if ( !v7 )
      v7 = v8;
  }
  v66 = v7;
  v60 = L"Consent";
  v9 = 0;
  v71 = v7;
  v65 = L"ExcludedApplications";
  v59[0] = 0;
  v70 = L"DebugApplications";
  v10 = 0;
  v61 = a2;
  v62[0] = 4;
  v63 = 1;
  v64 = 9;
  v67 = 13;
  v68 = 0;
  v69 = 0;
  v72 = 14;
  v73 = 0;
  v74 = 0;
  v75 = L"BrokerUp";
  v76 = a2;
  v77 = 22;
  v78 = 0;
  *((_DWORD *)this + 1275) = 1;
  *((_DWORD *)this + 1274) = a4;
  do
  {
    ++v9;
    *(_QWORD *)((char *)this + (_QWORD)v10 + 16) = *(_QWORD *)((char *)this + (_QWORD)v10 + 8);
    *(_WORD *)((char *)this + (_QWORD)v10) = 0;
    *(_QWORD *)((char *)this + (_QWORD)v10 + 96) = 0;
    v10 = (CSettings *)((char *)v10 + 104);
  }
  while ( v9 != 49 );
  for ( i = 0; i < 0xF; ++i )
  {
    v12 = CRegSetting::Initialize(
            (char *)this + 104 * (unsigned int)dword_1800AE9D8[10 * i],
            *((unsigned int *)&CSettings::allHiveSettings + 10 * i),
            *((_QWORD *)&off_1800AE9C8 + 5 * i));
    if ( v12 < 0 )
      goto LABEL_71;
  }
  for ( j = 0; j < 4; ++j )
  {
    if ( *(_QWORD *)&v62[10 * j - 2] )
    {
      v12 = CRegSetting::Initialize(
              (char *)this + 104 * (unsigned int)v62[10 * j],
              (unsigned int)v59[10 * j],
              (&v60)[5 * j]);
      if ( v12 < 0 )
        goto LABEL_71;
    }
  }
  CSettings::CreatePerUserDefaultConsent(v10);
  v14 = hKey;
  hKey = 0;
  if ( v14 )
    RegCloseKey(v14);
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Policies\\Microsoft\\Windows\\Windows Error Reporting",
          0,
          0x20119u,
          &hKey) )
    CRegSetting::Load(hKey, this, v15, v16, phkResult);
  v17 = hKey;
  v18 = (CSettings *)((char *)this + 208);
  v19 = *((_BYTE *)this + 208) == 0;
  v20 = (char *)this + 104;
  hKey = 0;
  *((_BYTE *)this + 5108) = v19;
  *((_BYTE *)this + 5109) = *((_BYTE *)this + 104) == 0;
  if ( v17 )
    RegCloseKey(v17);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\Windows Error Reporting", 0, 0x20119u, &hKey) )
    CRegSetting::Load(hKey, this, v21, v22, phkResulta);
  *((_DWORD *)this + 1278) = CRegSetting::GetDwordData(v18);
  DwordData = CRegSetting::GetDwordData((CSettings *)((char *)this + 104));
  v24 = hKey;
  hKey = 0;
  *((_BYTE *)this + 5110) = DwordData == 1;
  *((_BYTE *)this + 5106) = *(_BYTE *)v18;
  *((_BYTE *)this + 5107) = *v20;
  if ( v24 )
    RegCloseKey(v24);
  if ( !RegOpenKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Policies\\Microsoft\\Windows\\Windows Error Reporting",
          0,
          0x20119u,
          &hKey) )
    CRegSetting::Load(hKey, this, v25, v26, phkResultb);
  v27 = hKey;
  *((_BYTE *)this + 5104) = *(_BYTE *)v18;
  *((_BYTE *)this + 5105) = *v20;
  hKey = 0;
  if ( v27 )
    RegCloseKey(v27);
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\Windows Error Reporting", 0, 0x20119u, &hKey) )
  {
    v28 = hKey;
    for ( k = 0; k != 49; ++k )
      CRegSetting::Load((CSettings *)((char *)this + 104 * k), v28, 0x100u);
  }
  for ( m = 0; m < 0x1E; ++m )
  {
    v4 = (HKEY)(&off_1800AEC30)[5 * m];
    if ( v4 )
    {
      v31 = *((_DWORD *)&CSettings::adminSettings + 10 * m);
      v32 = qword_1800AEC40[5 * m];
      v33 = 104LL * (unsigned int)dword_1800AEC38[10 * m];
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               (char *)this + v33 + 32,
                               *((_QWORD *)&off_1800AEC28 + 5 * m))
        || (v34 = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                    (char *)this + v33 + 64,
                    v4),
            v4 = 0,
            !v34) )
      {
        v12 = -2147467259;
        goto LABEL_71;
      }
      *(_QWORD *)((char *)this + v33 + 16) = *(_QWORD *)((char *)this + v33 + 8);
      *(_WORD *)((char *)this + v33) = 256;
      *(_DWORD *)((char *)this + v33 + 4) = v31;
      *(_QWORD *)((char *)this + v33 + 96) = v32;
    }
  }
  v35 = hKey;
  hKey = v4;
  if ( v35 )
    RegCloseKey(v35);
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Policies\\Microsoft\\Windows\\Windows Error Reporting",
          0,
          0x20119u,
          &hKey) )
    CRegSetting::Load(hKey, this, v36, v37, phkResultc);
  v38 = hKey;
  hKey = v4;
  if ( v38 )
    RegCloseKey(v38);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\Windows Error Reporting", 0, 0x20119u, &hKey) )
    CRegSetting::Load(hKey, this, v40, v41, phkResultd);
  LOBYTE(v39) = a2 != 0;
  *((_DWORD *)this + 1275) = CSettings::ComputeConsent(this, v39);
  v82 = (int)v4;
  pcbData = 4;
  hkey = v4;
  v42 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Policies\\Microsoft\\SQMClient", 0, 0x101u, &hkey);
  v43 = v42 < 0;
  v44 = v42 <= 0;
  if ( !v42 )
  {
    ValueW = RegGetValueW(hkey, 0, L"MSFTInternal", 0x10u, (LPDWORD)v4, &v82, &pcbData);
    v43 = ValueW < 0;
    v44 = ValueW <= 0;
    if ( !ValueW )
      goto LABEL_54;
  }
  if ( !v44 )
    v43 = 1;
  if ( v43 )
  {
    v46 = (int)v4;
    v82 = (int)v4;
  }
  else
  {
LABEL_54:
    v46 = v82;
  }
  if ( hkey )
    RegCloseKey(hkey);
  *((_DWORD *)this + 1279) = v46;
  if ( !v46 )
    *((_DWORD *)this + 1279) = UtilRegGetDWORD(
                                 HKEY_LOCAL_MACHINE,
                                 L"SOFTWARE\\Microsoft\\SQMClient",
                                 L"MSFTInternal",
                                 0,
                                 (bool *)v4,
                                 pvData);
  v82 = (int)v4;
  pcbData = 4;
  hkey = v4;
  v47 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Policies\\Microsoft\\SQMClient", 0, 0x101u, &hkey);
  v48 = v47 < 0;
  v49 = v47 <= 0;
  if ( !v47 )
  {
    v50 = RegGetValueW(hkey, 0, L"IsTest", 0x10u, (LPDWORD)v4, &v82, &pcbData);
    v48 = v50 < 0;
    v49 = v50 <= 0;
    if ( !v50 )
      goto LABEL_65;
  }
  if ( !v49 )
    v48 = 1;
  if ( v48 )
  {
    v51 = (int)v4;
    v82 = (int)v4;
  }
  else
  {
LABEL_65:
    v51 = v82;
  }
  if ( hkey )
    RegCloseKey(hkey);
  *((_DWORD *)this + 1280) = v51;
  if ( !v51 )
    *((_DWORD *)this + 1280) = UtilRegGetDWORD(
                                 HKEY_LOCAL_MACHINE,
                                 L"SOFTWARE\\Microsoft\\SQMClient",
                                 L"IsTest",
                                 0,
                                 (bool *)v4,
                                 pvData);
  v12 = (int)v4;
LABEL_71:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000b1f4  push    rbp
0x18000b1f6  push    rbx
0x18000b1f7  push    rsi
0x18000b1f8  push    rdi
0x18000b1f9  push    r12
0x18000b1fb  push    r13
0x18000b1fd  push    r14
0x18000b1ff  push    r15
0x18000b201  lea     rbp, [rsp-1Fh]
0x18000b206  sub     rsp, 0E8h
0x18000b20d  xor     r14d, r14d
0x18000b210  mov     r13, rdx
0x18000b213  mov     [rbp+57h+hKey], r14
0x18000b217  mov     rbx, rcx
0x18000b21a  mov     eax, r14d
0x18000b21d  test    r8, r8
0x18000b220  jz      short loc_18000B231
0x18000b222  mov     rcx, r8; wchar_t *
0x18000b225  call    ?UtilPathTail@@YAPEB_WPEB_W@Z; UtilPathTail(wchar_t const *)
0x18000b22a  test    rax, rax
0x18000b22d  cmovz   rax, r8
0x18000b231  lea     rcx, aConsent; "Consent"
0x18000b238  mov     [rbp+57h+var_A8], rax
0x18000b23c  mov     [rsp+120h+var_D8], rcx
0x18000b241  mov     rdx, r14
0x18000b244  lea     rcx, aExcludedapplic; "ExcludedApplications"
0x18000b24b  mov     [rbp+57h+var_80], rax
0x18000b24f  mov     [rbp+57h+var_B0], rcx
0x18000b253  lea     rax, aBrokerup; "BrokerUp"
0x18000b25a  lea     rcx, aDebugapplicati; "DebugApplications"
0x18000b261  mov     [rsp+120h+var_E0], r14d
0x18000b266  mov     [rbp+57h+var_88], rcx
0x18000b26a  mov     rcx, r14
0x18000b26d  mov     [rbp+57h+var_D0], r13
0x18000b271  mov     [rbp+57h+var_C8], 4
0x18000b278  mov     [rbp+57h+var_C0], 1
0x18000b280  mov     [rbp+57h+var_B8], 9
0x18000b287  mov     [rbp+57h+var_A0], 0Dh
0x18000b28e  mov     [rbp+57h+var_98], r14
0x18000b292  mov     [rbp+57h+var_90], r14d
0x18000b296  mov     [rbp+57h+var_78], 0Eh
0x18000b29d  mov     [rbp+57h+var_70], r14
0x18000b2a1  mov     [rbp+57h+var_68], r14d
0x18000b2a5  mov     [rbp+57h+var_60], rax
0x18000b2a9  mov     [rbp+57h+var_58], r13
0x18000b2ad  mov     [rbp+57h+var_50], 16h
0x18000b2b4  mov     [rbp+57h+var_48], r14
0x18000b2b8  mov     dword ptr [rbx+13ECh], 1
0x18000b2c2  mov     [rbx+13E8h], r9d
0x18000b2c9  mov     rax, [rcx+rbx+8]
0x18000b2ce  inc     rdx
0x18000b2d1  mov     [rcx+rbx+10h], rax
0x18000b2d6  mov     [rcx+rbx], r14w
0x18000b2db  mov     [rcx+rbx+60h], r14
0x18000b2e0  lea     rcx, [rcx+68h]; this
0x18000b2e4  cmp     rdx, 31h ; '1'
0x18000b2e8  jnz     short loc_18000B2C9
0x18000b2ea  mov     esi, r14d
0x18000b2ed  lea     r10, __ImageBase
0x18000b2f4  cmp     esi, 0Fh
0x18000b2f7  jnb     short loc_18000B346
0x18000b2f9  mov     eax, esi
0x18000b2fb  lea     rdx, [rax+rax*4]
0x18000b2ff  mov     eax, ds:rva dword_1800AE9D8[r10+rdx*8]
0x18000b307  mov     r9, ds:rva off_1800AE9D0[r10+rdx*8]; "DontSendAdditionalData" ...
0x18000b30f  mov     r8, ds:rva off_1800AE9C8[r10+rdx*8]
0x18000b317  imul    rcx, rax, 68h ; 'h'
0x18000b31b  mov     rax, ds:rva qword_1800AE9E0[r10+rdx*8]
0x18000b323  mov     edx, ds:rva ?allHiveSettings@CSettings@@0QBUSETTING@1@B[r10+rdx*8]; CSettings::SETTING const near * const CSettings::allHiveSettings ...
0x18000b32b  add     rcx, rbx
0x18000b32e  mov     [rsp+120h+phkResult], rax
0x18000b333  call    ?Initialize@CRegSetting@@QEAAJW4_DataType@@PEB_W1_K@Z; CRegSetting::Initialize(_DataType,wchar_t const *,wchar_t const *,unsigned __int64)
0x18000b338  mov     edi, eax
0x18000b33a  test    eax, eax
0x18000b33c  js      loc_18000B7F0
0x18000b342  inc     esi
0x18000b344  jmp     short loc_18000B2ED
0x18000b346  mov     esi, r14d
0x18000b349  cmp     esi, 4
0x18000b34c  jnb     short loc_18000B38F
0x18000b34e  mov     eax, esi
0x18000b350  lea     rdx, [rax+rax*4]
0x18000b354  mov     r9, [rbp+rdx*8+57h+var_D0]
0x18000b359  test    r9, r9
0x18000b35c  jz      short loc_18000B38B
0x18000b35e  mov     eax, [rbp+rdx*8+57h+var_C8]
0x18000b362  mov     r8, [rsp+rdx*8+120h+var_D8]
0x18000b367  imul    rcx, rax, 68h ; 'h'
0x18000b36b  mov     rax, [rbp+rdx*8+57h+var_C0]
0x18000b370  mov     edx, [rsp+rdx*8+120h+var_E0]
0x18000b374  add     rcx, rbx
0x18000b377  mov     [rsp+120h+phkResult], rax
0x18000b37c  call    ?Initialize@CRegSetting@@QEAAJW4_DataType@@PEB_W1_K@Z; CRegSetting::Initialize(_DataType,wchar_t const *,wchar_t const *,unsigned __int64)
0x18000b381  mov     edi, eax
0x18000b383  test    eax, eax
0x18000b385  js      loc_18000B7F0
0x18000b38b  inc     esi
0x18000b38d  jmp     short loc_18000B349
0x18000b38f  call    ?CreatePerUserDefaultConsent@CSettings@@AEAAJXZ; CSettings::CreatePerUserDefaultConsent(void)
0x18000b394  mov     rcx, [rbp+57h+hKey]; hKey
0x18000b398  mov     [rbp+57h+hKey], r14
0x18000b39c  test    rcx, rcx
0x18000b39f  jz      short loc_18000B3A7
0x18000b3a1  call    cs:__imp_RegCloseKey
0x18000b3a7  lea     rax, [rbp+57h+hKey]
0x18000b3ab  mov     r12d, 20119h
0x18000b3b1  mov     r15, 0FFFFFFFF80000002h
0x18000b3b8  mov     [rsp+120h+phkResult], rax; unsigned int
0x18000b3bd  mov     r9d, r12d; samDesired
0x18000b3c0  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows"...
0x18000b3c7  mov     rcx, r15; hKey
0x18000b3ca  xor     r8d, r8d; ulOptions
0x18000b3cd  call    cs:__imp_RegOpenKeyExW
0x18000b3d3  test    eax, eax
0x18000b3d5  jnz     short loc_18000B3E3
0x18000b3d7  mov     rcx, [rbp+57h+hKey]; HKEY
0x18000b3db  mov     rdx, rbx; struct CRegSetting *
0x18000b3de  call    ?Load@CRegSetting@@SAJPEAUHKEY__@@QEAV1@KPEAKK@Z; CRegSetting::Load(HKEY__ *,CRegSetting * const,ulong,ulong *,ulong)
0x18000b3e3  mov     rcx, [rbp+57h+hKey]; hKey
0x18000b3e7  lea     rdi, [rbx+0D0h]
0x18000b3ee  cmp     [rdi], r14b
0x18000b3f1  lea     rsi, [rbx+68h]
0x18000b3f5  mov     [rbp+57h+hKey], r14
0x18000b3f9  setz    al
0x18000b3fc  mov     [rbx+13F4h], al
0x18000b402  cmp     [rsi], r14b
0x18000b405  setz    al
0x18000b408  mov     [rbx+13F5h], al
0x18000b40e  test    rcx, rcx
0x18000b411  jz      short loc_18000B419
0x18000b413  call    cs:__imp_RegCloseKey
0x18000b419  lea     rax, [rbp+57h+hKey]
0x18000b41d  mov     r9d, r12d; samDesired
0x18000b420  xor     r8d, r8d; ulOptions
0x18000b423  mov     [rsp+120h+phkResult], rax; unsigned int
0x18000b428  lea     rdx, aSoftwareMicros_24; "Software\\Microsoft\\Windows\\Windows E"...
0x18000b42f  mov     rcx, r15; hKey
0x18000b432  call    cs:__imp_RegOpenKeyExW
0x18000b438  test    eax, eax
0x18000b43a  jnz     short loc_18000B448
0x18000b43c  mov     rcx, [rbp+57h+hKey]; HKEY
0x18000b440  mov     rdx, rbx; struct CRegSetting *
0x18000b443  call    ?Load@CRegSetting@@SAJPEAUHKEY__@@QEAV1@KPEAKK@Z; CRegSetting::Load(HKEY__ *,CRegSetting * const,ulong,ulong *,ulong)
0x18000b448  mov     rcx, rdi; this
0x18000b44b  call    ?GetDwordData@CRegSetting@@QEBAKXZ; CRegSetting::GetDwordData(void)
0x18000b450  mov     rcx, rsi; this
0x18000b453  mov     [rbx+13F8h], eax
0x18000b459  call    ?GetDwordData@CRegSetting@@QEBAKXZ; CRegSetting::GetDwordData(void)
0x18000b45e  mov     rcx, [rbp+57h+hKey]; hKey
0x18000b462  cmp     eax, 1
0x18000b465  mov     [rbp+57h+hKey], r14
0x18000b469  setz    al
0x18000b46c  mov     [rbx+13F6h], al
0x18000b472  mov     al, [rdi]
0x18000b474  mov     [rbx+13F2h], al
0x18000b47a  mov     al, [rsi]
0x18000b47c  mov     [rbx+13F3h], al
0x18000b482  test    rcx, rcx
0x18000b485  jz      short loc_18000B48D
0x18000b487  call    cs:__imp_RegCloseKey
0x18000b48d  lea     rax, [rbp+57h+hKey]
0x18000b491  mov     r15, 0FFFFFFFF80000001h
0x18000b498  mov     rcx, r15; hKey
0x18000b49b  mov     [rsp+120h+phkResult], rax; unsigned int
0x18000b4a0  mov     r9d, r12d; samDesired
0x18000b4a3  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows"...
0x18000b4aa  xor     r8d, r8d; ulOptions
0x18000b4ad  call    cs:__imp_RegOpenKeyExW
0x18000b4b3  test    eax, eax
0x18000b4b5  jnz     short loc_18000B4C3
0x18000b4b7  mov     rcx, [rbp+57h+hKey]; HKEY
0x18000b4bb  mov     rdx, rbx; struct CRegSetting *
0x18000b4be  call    ?Load@CRegSetting@@SAJPEAUHKEY__@@QEAV1@KPEAKK@Z; CRegSetting::Load(HKEY__ *,CRegSetting * const,ulong,ulong *,ulong)
0x18000b4c3  mov     al, [rdi]
0x18000b4c5  mov     rcx, [rbp+57h+hKey]; hKey
0x18000b4c9  mov     [rbx+13F0h], al
0x18000b4cf  mov     al, [rsi]
0x18000b4d1  mov     [rbx+13F1h], al
0x18000b4d7  mov     [rbp+57h+hKey], r14
0x18000b4db  test    rcx, rcx
0x18000b4de  jz      short loc_18000B4E6
0x18000b4e0  call    cs:__imp_RegCloseKey
0x18000b4e6  lea     rax, [rbp+57h+hKey]
0x18000b4ea  mov     r9d, r12d; samDesired
0x18000b4ed  xor     r8d, r8d; ulOptions
0x18000b4f0  mov     [rsp+120h+phkResult], rax; phkResult
0x18000b4f5  lea     rdx, aSoftwareMicros_24; "Software\\Microsoft\\Windows\\Windows E"...
0x18000b4fc  mov     rcx, r15; hKey
0x18000b4ff  call    cs:__imp_RegOpenKeyExW
0x18000b505  test    eax, eax
0x18000b507  jnz     short loc_18000B52E
0x18000b509  mov     rsi, [rbp+57h+hKey]
0x18000b50d  mov     rdi, r14
0x18000b510  imul    rcx, rdi, 68h ; 'h'
0x18000b514  mov     r8d, 100h; unsigned int
0x18000b51a  mov     rdx, rsi; HKEY
0x18000b51d  add     rcx, rbx; this
0x18000b520  call    ?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z; CRegSetting::Load(HKEY__ *,ulong)
0x18000b525  inc     rdi
0x18000b528  cmp     rdi, 31h ; '1'
0x18000b52c  jnz     short loc_18000B510
0x18000b52e  mov     esi, r14d
0x18000b531  cmp     esi, 1Eh
0x18000b534  jnb     loc_18000B5C9
0x18000b53a  mov     eax, esi
0x18000b53c  lea     r8, __ImageBase
0x18000b543  lea     rdx, [rax+rax*4]
0x18000b547  mov     r14, ds:rva off_1800AEC30[r8+rdx*8]; "DisableArchive" ...
0x18000b54f  test    r14, r14
0x18000b552  jz      short loc_18000B5B8
0x18000b554  mov     eax, ds:rva dword_1800AEC38[r8+rdx*8]
0x18000b55c  lea     rcx, [rbx+20h]
0x18000b560  mov     r15d, ds:rva ?adminSettings@CSettings@@0QBUSETTING@1@B[r8+rdx*8]; CSettings::SETTING const near * const CSettings::adminSettings ...
0x18000b568  mov     r12, ds:rva qword_1800AEC40[r8+rdx*8]
0x18000b570  mov     rdx, ds:rva off_1800AEC28[r8+rdx*8]
0x18000b578  imul    rdi, rax, 68h ; 'h'
0x18000b57c  add     rcx, rdi
0x18000b57f  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18000b584  test    al, al
0x18000b586  jz      short loc_18000B5BF
0x18000b588  lea     rcx, [rbx+40h]
0x18000b58c  mov     rdx, r14
0x18000b58f  add     rcx, rdi
0x18000b592  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18000b597  xor     r14d, r14d
0x18000b59a  test    al, al
0x18000b59c  jz      short loc_18000B5BF
0x18000b59e  mov     rax, [rdi+rbx+8]
0x18000b5a3  mov     [rdi+rbx+10h], rax
0x18000b5a8  mov     word ptr [rdi+rbx], 100h
0x18000b5ae  mov     [rdi+rbx+4], r15d
0x18000b5b3  mov     [rdi+rbx+60h], r12
0x18000b5b8  inc     esi
0x18000b5ba  jmp     loc_18000B531
0x18000b5bf  mov     edi, 80004005h
0x18000b5c4  jmp     loc_18000B7F0
0x18000b5c9  mov     rcx, [rbp+57h+hKey]; hKey
0x18000b5cd  mov     [rbp+57h+hKey], r14
0x18000b5d1  test    rcx, rcx
0x18000b5d4  jz      short loc_18000B5DC
0x18000b5d6  call    cs:__imp_RegCloseKey
0x18000b5dc  lea     rax, [rbp+57h+hKey]
0x18000b5e0  mov     r12d, 20119h
0x18000b5e6  mov     r15, 0FFFFFFFF80000002h
0x18000b5ed  mov     [rsp+120h+phkResult], rax; unsigned int
0x18000b5f2  mov     r9d, r12d; samDesired
0x18000b5f5  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows"...
0x18000b5fc  mov     rcx, r15; hKey
0x18000b5ff  xor     r8d, r8d; ulOptions
0x18000b602  call    cs:__imp_RegOpenKeyExW
0x18000b608  test    eax, eax
0x18000b60a  jnz     short loc_18000B618
0x18000b60c  mov     rcx, [rbp+57h+hKey]; HKEY
0x18000b610  mov     rdx, rbx; struct CRegSetting *
0x18000b613  call    ?Load@CRegSetting@@SAJPEAUHKEY__@@QEAV1@KPEAKK@Z; CRegSetting::Load(HKEY__ *,CRegSetting * const,ulong,ulong *,ulong)
0x18000b618  mov     rcx, [rbp+57h+hKey]; hKey
0x18000b61c  mov     [rbp+57h+hKey], r14
0x18000b620  test    rcx, rcx
0x18000b623  jz      short loc_18000B62B
0x18000b625  call    cs:__imp_RegCloseKey
0x18000b62b  lea     rax, [rbp+57h+hKey]
0x18000b62f  mov     r9d, r12d; samDesired
0x18000b632  xor     r8d, r8d; ulOptions
0x18000b635  mov     [rsp+120h+phkResult], rax; unsigned int
0x18000b63a  lea     rdx, aSoftwareMicros_24; "Software\\Microsoft\\Windows\\Windows E"...
0x18000b641  mov     rcx, r15; hKey
0x18000b644  call    cs:__imp_RegOpenKeyExW
0x18000b64a  test    eax, eax
0x18000b64c  jnz     short loc_18000B65A
0x18000b64e  mov     rcx, [rbp+57h+hKey]; HKEY
0x18000b652  mov     rdx, rbx; struct CRegSetting *
0x18000b655  call    ?Load@CRegSetting@@SAJPEAUHKEY__@@QEAV1@KPEAKK@Z; CRegSetting::Load(HKEY__ *,CRegSetting * const,ulong,ulong *,ulong)
0x18000b65a  test    r13, r13
0x18000b65d  mov     rcx, rbx
0x18000b660  setnz   dl
0x18000b663  call    ?ComputeConsent@CSettings@@AEBA?AW4_CONSENT_SETTING@@_N@Z; CSettings::ComputeConsent(bool)
0x18000b668  mov     [rbx+13ECh], eax
0x18000b66e  lea     rdx, aSoftwarePolici_1; "SOFTWARE\\Policies\\Microsoft\\SQMClien"...
0x18000b675  lea     rax, [rbp+57h+hkey]
0x18000b679  mov     [rbp+57h+arg_18], r14d
0x18000b67d  mov     r13d, 101h
0x18000b683  mov     [rsp+120h+phkResult], rax; phkResult
0x18000b688  mov     r9d, r13d; samDesired
0x18000b68b  mov     [rbp+57h+arg_0], 4
0x18000b692  xor     r8d, r8d; ulOptions
0x18000b695  mov     [rbp+57h+hkey], r14
0x18000b699  mov     rcx, r15; hKey
0x18000b69c  call    cs:__imp_RegOpenKeyExW
0x18000b6a2  mov     esi, 80070000h
0x18000b6a7  mov     r12d, 10h
0x18000b6ad  test    eax, eax
0x18000b6af  jnz     short loc_18000B6E2
0x18000b6b1  mov     rcx, [rbp+57h+hkey]; hkey
0x18000b6b5  lea     rax, [rbp+57h+arg_0]
0x18000b6b9  mov     [rsp+120h+pcbData], rax; pcbData
0x18000b6be  lea     r8, aMsftinternal; "MSFTInternal"
0x18000b6c5  lea     rax, [rbp+57h+arg_18]
0x18000b6c9  mov     r9d, r12d; dwFlags
0x18000b6cc  mov     [rsp+120h+pvData], rax; bool
0x18000b6d1  xor     edx, edx; lpSubKey
  ... truncated ...
```
