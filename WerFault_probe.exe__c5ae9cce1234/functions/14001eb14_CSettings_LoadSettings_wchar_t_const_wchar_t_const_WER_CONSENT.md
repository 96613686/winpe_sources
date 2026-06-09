# CSettings::LoadSettings(wchar_t const *,wchar_t const *,_WER_CONSENT)

- ea: `0x14001eb14`
- end: `0x14001f1f8`
- name: `?LoadSettings@CSettings@@QEAAJPEB_W0W4_WER_CONSENT@@@Z`
- size: `1764`
- prototype: `__int64 __fastcall(CSettings *__hidden this, const wchar_t *, const wchar_t *, enum _WER_CONSENT)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140020fc0`
- `0x140023560`
- `0x140025c30`

## callees

- `0x140005468`
- `0x140008498`
- `0x140008620`
- `0x14001211c`
- `0x14001da94`
- `0x14001eb14`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x14001eefa`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x14001ef31`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x14001eefa`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x14001ef31`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001ed2e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001ed6c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001ed2e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001ed6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001edfc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001f1dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001edfc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001f1dc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001edec`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001edec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001ee2a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001ee97`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001ef85`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001efee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001f0a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001f0f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001ee2a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001ee97`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001ef85`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001efee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001f0a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001f0f5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14001edc2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14001edc2`

## string_xrefs

- `0x14001ebc8`: `BrokerUp`

## pseudocode

```c
__int64 __fastcall CSettings::LoadSettings(CSettings *this, const wchar_t *a2, const wchar_t *a3, DWORD a4)
{
  const wchar_t *v6; // r9
  __int64 v7; // rax
  const wchar_t *v8; // rcx
  unsigned __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rcx
  unsigned int v13; // edi
  int v14; // esi
  unsigned int i; // edi
  __int64 v16; // r9
  HKEY *phkResult; // rax
  HKEY *v18; // rax
  HKEY v19; // rsi
  __int64 j; // rdi
  HKEY *v21; // rax
  HKEY v22; // rsi
  __int64 k; // rdi
  int v24; // eax
  int v25; // eax
  int v26; // eax
  HKEY *v27; // rax
  HKEY v28; // rsi
  __int64 m; // rdi
  HKEY *v30; // rax
  HKEY v31; // rsi
  __int64 n; // rdi
  unsigned int v33; // edi
  wchar_t *v34; // r9
  HKEY *v35; // rax
  HKEY v36; // rsi
  __int64 ii; // rdi
  HKEY *v38; // rax
  __int64 v39; // rdx
  HKEY v40; // rsi
  __int64 jj; // rdi
  unsigned int DWORD; // eax
  unsigned int v43; // eax
  bool pvData; // [rsp+28h] [rbp-D8h]
  bool pvDataa; // [rsp+28h] [rbp-D8h]
  bool pvDatab; // [rsp+28h] [rbp-D8h]
  HKEY hKey[2]; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v49[2]; // [rsp+60h] [rbp-A0h]
  const wchar_t *v50; // [rsp+68h] [rbp-98h]
  const wchar_t *v51; // [rsp+70h] [rbp-90h]
  _DWORD v52[2]; // [rsp+78h] [rbp-88h]
  __int64 v53; // [rsp+80h] [rbp-80h]
  int v54; // [rsp+88h] [rbp-78h]
  const wchar_t *v55; // [rsp+90h] [rbp-70h]
  const wchar_t *v56; // [rsp+98h] [rbp-68h]
  int v57; // [rsp+A0h] [rbp-60h]
  __int64 v58; // [rsp+A8h] [rbp-58h]
  int v59; // [rsp+B0h] [rbp-50h]
  const wchar_t *v60; // [rsp+B8h] [rbp-48h]
  const wchar_t *v61; // [rsp+C0h] [rbp-40h]
  int v62; // [rsp+C8h] [rbp-38h]
  __int64 v63; // [rsp+D0h] [rbp-30h]
  int v64; // [rsp+D8h] [rbp-28h]
  const wchar_t *v65; // [rsp+E0h] [rbp-20h]
  const wchar_t *v66; // [rsp+E8h] [rbp-18h]
  int v67; // [rsp+F0h] [rbp-10h]
  __int64 v68; // [rsp+F8h] [rbp-8h]
  int v69; // [rsp+150h] [rbp+50h] BYREF
  int Data; // [rsp+158h] [rbp+58h] BYREF
  HKEY v71; // [rsp+160h] [rbp+60h] BYREF
  DWORD pcbData; // [rsp+168h] [rbp+68h] BYREF

  pcbData = a4;
  v71 = 0;
  v6 = 0;
  if ( a3 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a3[v7] );
    v8 = &a3[v7];
    while ( 1 )
    {
      v6 = v8;
      if ( v8 <= a3 )
        break;
      v9 = *--v8;
      LOWORD(v9) = v9 - 47;
      if ( (unsigned __int16)v9 <= 0x2Du )
      {
        v10 = 0x200000000801LL;
        if ( _bittest64(&v10, v9) )
          break;
      }
    }
    if ( !v6 )
      v6 = a3;
  }
  v49[0] = 0;
  v50 = L"Consent";
  v51 = a2;
  v55 = L"ExcludedApplications";
  v11 = 0;
  v52[0] = 4;
  v60 = L"DebugApplications";
  v53 = 1;
  v65 = L"BrokerUp";
  v12 = 0;
  v54 = 9;
  v56 = v6;
  v57 = 13;
  v58 = 0;
  v59 = 0;
  v61 = v6;
  v62 = 14;
  v63 = 0;
  v64 = 0;
  v66 = a2;
  v67 = 22;
  v68 = 0;
  *((_DWORD *)this + 1275) = 1;
  *((_DWORD *)this + 1274) = 1;
  do
  {
    *(_WORD *)((char *)this + v12) = 0;
    ++v11;
    *(_QWORD *)((char *)this + v12 + 96) = 0;
    *(_QWORD *)((char *)this + v12 + 16) = *(_QWORD *)((char *)this + v12 + 8);
    v12 += 104;
  }
  while ( v11 != 49 );
  v13 = 0;
  while ( 1 )
  {
    v14 = CRegSetting::Initialize(
            (char *)this + 104 * (unsigned int)dword_14005FF08[10 * v13],
            *((unsigned int *)&CSettings::allHiveSettings + 10 * v13),
            *((_QWORD *)&off_14005FEF8 + 5 * v13),
            (&off_14005FF00)[5 * v13],
            qword_14005FF10[5 * v13]);
    if ( v14 < 0 )
      break;
    if ( ++v13 >= 0xF )
    {
      for ( i = 0; i < 4; ++i )
      {
        v16 = *(_QWORD *)&v52[10 * i - 2];
        if ( v16 )
        {
          v14 = CRegSetting::Initialize(
                  (char *)this + 104 * (unsigned int)v52[10 * i],
                  (unsigned int)v49[10 * i],
                  (&v50)[5 * i],
                  v16,
                  *(&v53 + 5 * i));
          if ( v14 < 0 )
            goto LABEL_65;
        }
      }
      v69 = 0;
      pcbData = 4;
      if ( RegGetValueW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Consent",
             L"DefaultConsent",
             0x10u,
             0,
             &v69,
             &pcbData) == 2 )
      {
        pcbData = 4;
        if ( !RegGetValueW(
                HKEY_LOCAL_MACHINE,
                L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Consent",
                L"NewUserDefaultConsent",
                0x10u,
                0,
                &v69,
                &pcbData) )
        {
          Data = v69;
          hKey[0] = 0;
          if ( (unsigned int)(v69 - 1) <= 3 )
          {
            phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(hKey);
            if ( !RegCreateKeyExW(
                    HKEY_CURRENT_USER,
                    L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Consent",
                    0,
                    0,
                    0,
                    0x20106u,
                    0,
                    phkResult,
                    0) )
              RegSetValueExW(hKey[0], L"DefaultConsent", 0, 4u, (const BYTE *)&Data, 4u);
            if ( hKey[0] )
              RegCloseKey(hKey[0]);
          }
        }
      }
      v18 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v71);
      if ( !RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Policies\\Microsoft\\Windows\\Windows Error Reporting",
              0,
              0x20119u,
              v18) )
      {
        v19 = v71;
        for ( j = 0; j != 49; ++j )
          CRegSetting::Load((CSettings *)((char *)this + 104 * j), v19, 0x100u);
      }
      *((_BYTE *)this + 5108) = *((_BYTE *)this + 208) == 0;
      *((_BYTE *)this + 5109) = *((_BYTE *)this + 104) == 0;
      v21 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v71);
      if ( !RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\Windows Error Reporting",
              0,
              0x20119u,
              v21) )
      {
        v22 = v71;
        for ( k = 0; k != 49; ++k )
          CRegSetting::Load((CSettings *)((char *)this + 104 * k), v22, 0x100u);
      }
      if ( !*((_BYTE *)this + 208) )
        goto LABEL_37;
      v24 = *((_DWORD *)this + 53);
      if ( !v24 )
      {
        v25 = **((_DWORD **)this + 27);
        goto LABEL_38;
      }
      if ( v24 == 1 )
        v25 = wcstol(*((const wchar_t **)this + 27), 0, 10);
      else
LABEL_37:
        v25 = *((_DWORD *)this + 76);
LABEL_38:
      *((_DWORD *)this + 1278) = v25;
      if ( !*((_BYTE *)this + 104) )
        goto LABEL_43;
      if ( !*((_DWORD *)this + 27) )
      {
        v26 = **((_DWORD **)this + 14);
        goto LABEL_44;
      }
      if ( *((_DWORD *)this + 27) == 1 )
        v26 = wcstol(*((const wchar_t **)this + 14), 0, 10);
      else
LABEL_43:
        v26 = *((_DWORD *)this + 50);
LABEL_44:
      *((_BYTE *)this + 5110) = v26 == 1;
      *((_BYTE *)this + 5106) = *((_BYTE *)this + 208);
      *((_BYTE *)this + 5107) = *((_BYTE *)this + 104);
      v27 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v71);
      if ( !RegOpenKeyExW(
              HKEY_CURRENT_USER,
              L"Software\\Policies\\Microsoft\\Windows\\Windows Error Reporting",
              0,
              0x20119u,
              v27) )
      {
        v28 = v71;
        for ( m = 0; m != 49; ++m )
          CRegSetting::Load((CSettings *)((char *)this + 104 * m), v28, 0x100u);
      }
      *((_BYTE *)this + 5104) = *((_BYTE *)this + 208);
      *((_BYTE *)this + 5105) = *((_BYTE *)this + 104);
      v30 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v71);
      if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\Windows Error Reporting", 0, 0x20119u, v30) )
      {
        v31 = v71;
        for ( n = 0; n != 49; ++n )
          CRegSetting::Load((CSettings *)((char *)this + 104 * n), v31, 0x100u);
      }
      v33 = 0;
      while ( 1 )
      {
        v34 = (&off_14005FA50)[5 * v33];
        if ( v34 )
        {
          v14 = CRegSetting::Initialize(
                  (char *)this + 104 * (unsigned int)dword_14005FA58[10 * v33],
                  *((unsigned int *)&CSettings::adminSettings + 10 * v33),
                  *((_QWORD *)&off_14005FA48 + 5 * v33),
                  v34,
                  qword_14005FA60[5 * v33]);
          if ( v14 < 0 )
            goto LABEL_65;
        }
        if ( ++v33 >= 0x1E )
        {
          v35 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v71);
          if ( !RegOpenKeyExW(
                  HKEY_LOCAL_MACHINE,
                  L"Software\\Policies\\Microsoft\\Windows\\Windows Error Reporting",
                  0,
                  0x20119u,
                  v35) )
          {
            v36 = v71;
            for ( ii = 0; ii != 49; ++ii )
              CRegSetting::Load((CSettings *)((char *)this + 104 * ii), v36, 0x100u);
          }
          v38 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v71);
          if ( !RegOpenKeyExW(
                  HKEY_LOCAL_MACHINE,
                  L"Software\\Microsoft\\Windows\\Windows Error Reporting",
                  0,
                  0x20119u,
                  v38) )
          {
            v40 = v71;
            for ( jj = 0; jj != 49; ++jj )
              CRegSetting::Load((CSettings *)((char *)this + 104 * jj), v40, 0x100u);
          }
          LOBYTE(v39) = a2 != 0;
          *((_DWORD *)this + 1275) = CSettings::ComputeConsent(this, v39);
          DWORD = UtilRegGetDWORD(
                    HKEY_LOCAL_MACHINE,
                    L"SOFTWARE\\Policies\\Microsoft\\SQMClient",
                    L"MSFTInternal",
                    0,
                    0,
                    pvData);
          *((_DWORD *)this + 1279) = DWORD;
          if ( !DWORD )
            *((_DWORD *)this + 1279) = UtilRegGetDWORD(
                                         HKEY_LOCAL_MACHINE,
                                         L"SOFTWARE\\Microsoft\\SQMClient",
                                         L"MSFTInternal",
                                         0,
                                         0,
                                         pvDataa);
          v43 = UtilRegGetDWORD(
                  HKEY_LOCAL_MACHINE,
                  L"SOFTWARE\\Policies\\Microsoft\\SQMClient",
                  L"IsTest",
                  0,
                  0,
                  pvDataa);
          *((_DWORD *)this + 1280) = v43;
          if ( !v43 )
            *((_DWORD *)this + 1280) = UtilRegGetDWORD(
                                         HKEY_LOCAL_MACHINE,
                                         L"SOFTWARE\\Microsoft\\SQMClient",
                                         L"IsTest",
                                         0,
                                         0,
                                         pvDatab);
          v14 = 0;
          goto LABEL_65;
        }
      }
    }
  }
LABEL_65:
  if ( v71 )
    RegCloseKey(v71);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14001eb14  mov     [rsp-8+arg_18], r9d
0x14001eb19  push    rbp
0x14001eb1a  push    rbx
0x14001eb1b  push    rsi
0x14001eb1c  push    rdi
0x14001eb1d  push    r12
0x14001eb1f  push    r13
0x14001eb21  push    r14
0x14001eb23  push    r15
0x14001eb25  lea     rbp, [rsp-8]
0x14001eb2a  sub     rsp, 108h
0x14001eb31  xor     r15d, r15d
0x14001eb34  mov     r14, rdx
0x14001eb37  mov     [rbp+40h+arg_10], r15
0x14001eb3b  mov     rbx, rcx
0x14001eb3e  mov     r9d, r15d
0x14001eb41  test    r8, r8
0x14001eb44  jz      short loc_14001EB8A
0x14001eb46  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001eb4a  inc     rax
0x14001eb4d  cmp     [r8+rax*2], r15w
0x14001eb52  jnz     short loc_14001EB4A
0x14001eb54  lea     rcx, [r8+rax*2]
0x14001eb58  jmp     short loc_14001EB7B
0x14001eb5a  sub     rcx, 2
0x14001eb5e  movzx   eax, word ptr [rcx]
0x14001eb61  sub     ax, 2Fh ; '/'
0x14001eb65  cmp     ax, 2Dh ; '-'
0x14001eb69  ja      short loc_14001EB7B
0x14001eb6b  mov     rdx, 200000000801h
0x14001eb75  bt      rdx, rax
0x14001eb79  jb      short loc_14001EB83
0x14001eb7b  mov     r9, rcx
0x14001eb7e  cmp     rcx, r8
0x14001eb81  ja      short loc_14001EB5A
0x14001eb83  test    r9, r9
0x14001eb86  cmovz   r9, r8
0x14001eb8a  lea     rax, aConsent; "Consent"
0x14001eb91  mov     [rsp+140h+var_E0], r15d
0x14001eb96  mov     [rsp+140h+var_D8], rax
0x14001eb9b  mov     r13d, 4
0x14001eba1  lea     rax, aExcludedapplic; "ExcludedApplications"
0x14001eba8  mov     [rsp+140h+var_D0], r14
0x14001ebad  mov     [rbp+40h+var_B0], rax
0x14001ebb1  mov     rdx, r15
0x14001ebb4  lea     rax, aDebugapplicati; "DebugApplications"
0x14001ebbb  mov     [rsp+140h+var_C8], r13d
0x14001ebc0  lea     r12d, [r13-3]
0x14001ebc4  mov     [rbp+40h+var_88], rax
0x14001ebc8  lea     rax, aBrokerup; "BrokerUp"
0x14001ebcf  mov     [rbp+40h+var_C0], r12
0x14001ebd3  mov     [rbp+40h+var_60], rax
0x14001ebd7  mov     rcx, r15
0x14001ebda  mov     [rbp+40h+var_B8], 9
0x14001ebe1  mov     [rbp+40h+var_A8], r9
0x14001ebe5  mov     [rbp+40h+var_A0], 0Dh
0x14001ebec  mov     [rbp+40h+var_98], r15
0x14001ebf0  mov     [rbp+40h+var_90], r15d
0x14001ebf4  mov     [rbp+40h+var_80], r9
0x14001ebf8  mov     [rbp+40h+var_78], 0Eh
0x14001ebff  mov     [rbp+40h+var_70], r15
0x14001ec03  mov     [rbp+40h+var_68], r15d
0x14001ec07  mov     [rbp+40h+var_58], r14
0x14001ec0b  mov     [rbp+40h+var_50], 16h
0x14001ec12  mov     [rbp+40h+var_48], r15
0x14001ec16  mov     [rbx+13ECh], r12d
0x14001ec1d  mov     [rbx+13E8h], r12d
0x14001ec24  mov     [rbx+rcx], r15w
0x14001ec29  add     rdx, r12
0x14001ec2c  mov     [rbx+rcx+60h], r15
0x14001ec31  mov     rax, [rbx+rcx+8]
0x14001ec36  mov     [rbx+rcx+10h], rax
0x14001ec3b  lea     rcx, [rcx+68h]
0x14001ec3f  cmp     rdx, 31h ; '1'
0x14001ec43  jnz     short loc_14001EC24
0x14001ec45  mov     edi, r15d
0x14001ec48  lea     r10, __ImageBase
0x14001ec4f  mov     eax, edi
0x14001ec51  lea     rdx, [rax+rax*4]
0x14001ec55  mov     eax, ds:rva dword_14005FF08[r10+rdx*8]
0x14001ec5d  mov     r9, ds:rva off_14005FF00[r10+rdx*8]; "DontSendAdditionalData" ...
0x14001ec65  mov     r8, ds:rva off_14005FEF8[r10+rdx*8]
0x14001ec6d  imul    rcx, rax, 68h ; 'h'
0x14001ec71  mov     rax, ds:rva qword_14005FF10[r10+rdx*8]
0x14001ec79  mov     edx, ds:rva ?allHiveSettings@CSettings@@0QBUSETTING@1@B[r10+rdx*8]; CSettings::SETTING const near * const CSettings::allHiveSettings ...
0x14001ec81  add     rcx, rbx
0x14001ec84  mov     [rsp+140h+pdwType], rax
0x14001ec89  call    ?Initialize@CRegSetting@@QEAAJW4_DataType@@PEB_W1_K@Z; CRegSetting::Initialize(_DataType,wchar_t const *,wchar_t const *,unsigned __int64)
0x14001ec8e  mov     esi, eax
0x14001ec90  test    eax, eax
0x14001ec92  js      loc_14001F1D3
0x14001ec98  add     edi, r12d
0x14001ec9b  lea     r10, __ImageBase
0x14001eca2  cmp     edi, 0Fh
0x14001eca5  jb      short loc_14001EC4F
0x14001eca7  mov     edi, r15d
0x14001ecaa  mov     eax, edi
0x14001ecac  lea     rdx, [rax+rax*4]
0x14001ecb0  mov     r9, [rsp+rdx*8+140h+var_D0]
0x14001ecb5  test    r9, r9
0x14001ecb8  jz      short loc_14001ECE7
0x14001ecba  mov     eax, [rsp+rdx*8+140h+var_C8]
0x14001ecbe  mov     r8, [rsp+rdx*8+140h+var_D8]
0x14001ecc3  imul    rcx, rax, 68h ; 'h'
0x14001ecc7  mov     rax, [rbp+rdx*8+40h+var_C0]
0x14001eccc  mov     edx, [rsp+rdx*8+140h+var_E0]
0x14001ecd0  add     rcx, rbx
0x14001ecd3  mov     [rsp+140h+pdwType], rax
0x14001ecd8  call    ?Initialize@CRegSetting@@QEAAJW4_DataType@@PEB_W1_K@Z; CRegSetting::Initialize(_DataType,wchar_t const *,wchar_t const *,unsigned __int64)
0x14001ecdd  mov     esi, eax
0x14001ecdf  test    eax, eax
0x14001ece1  js      loc_14001F1D3
0x14001ece7  add     edi, r12d
0x14001ecea  cmp     edi, r13d
0x14001eced  jb      short loc_14001ECAA
0x14001ecef  lea     rax, [rbp+40h+arg_18]
0x14001ecf3  mov     [rbp+40h+arg_0], r15d
0x14001ecf7  mov     [rsp+140h+pcbData], rax; pcbData
0x14001ecfc  lea     rdi, aSoftwareMicros_12; "Software\\Microsoft\\Windows\\Windows E"...
0x14001ed03  lea     rax, [rbp+40h+arg_0]
0x14001ed07  mov     [rbp+40h+arg_18], r13d
0x14001ed0b  mov     [rsp+140h+pvData], rax; pvData
0x14001ed10  lea     r8, ValueName; "DefaultConsent"
0x14001ed17  mov     esi, 10h
0x14001ed1c  mov     [rsp+140h+pdwType], r15; pdwType
0x14001ed21  mov     r9d, esi; dwFlags
0x14001ed24  mov     rdx, rdi; lpSubKey
0x14001ed27  mov     rcx, 0FFFFFFFF80000001h; hkey
0x14001ed2e  call    cs:__imp_RegGetValueW
0x14001ed34  cmp     eax, 2
0x14001ed37  jnz     loc_14001EE02
0x14001ed3d  lea     rax, [rbp+40h+arg_18]
0x14001ed41  mov     [rbp+40h+arg_18], r13d
0x14001ed45  mov     [rsp+140h+pcbData], rax; pcbData
0x14001ed4a  lea     r8, aNewuserdefault; "NewUserDefaultConsent"
0x14001ed51  lea     rax, [rbp+40h+arg_0]
0x14001ed55  mov     r9d, esi; dwFlags
0x14001ed58  mov     [rsp+140h+pvData], rax; pvData
0x14001ed5d  mov     rdx, rdi; lpSubKey
0x14001ed60  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14001ed67  mov     [rsp+140h+pdwType], r15; pdwType
0x14001ed6c  call    cs:__imp_RegGetValueW
0x14001ed72  test    eax, eax
0x14001ed74  jnz     loc_14001EE02
0x14001ed7a  mov     eax, [rbp+40h+arg_0]
0x14001ed7d  mov     [rbp+40h+Data], eax
0x14001ed80  dec     eax
0x14001ed82  mov     [rsp+140h+hKey], r15
0x14001ed87  cmp     eax, 3
0x14001ed8a  ja      short loc_14001EE02
0x14001ed8c  lea     rcx, [rsp+140h+hKey]
0x14001ed91  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14001ed96  mov     [rsp+140h+lpdwDisposition], r15; lpdwDisposition
0x14001ed9b  xor     r9d, r9d; lpClass
0x14001ed9e  mov     [rsp+140h+phkResult], rax; phkResult
0x14001eda3  xor     r8d, r8d; Reserved
0x14001eda6  mov     [rsp+140h+pcbData], r15; lpSecurityAttributes
0x14001edab  mov     rdx, rdi; lpSubKey
0x14001edae  mov     dword ptr [rsp+140h+pvData], 20106h; samDesired
0x14001edb6  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14001edbd  mov     dword ptr [rsp+140h+pdwType], r15d; dwOptions
0x14001edc2  call    cs:__imp_RegCreateKeyExW
0x14001edc8  test    eax, eax
0x14001edca  jnz     short loc_14001EDF2
0x14001edcc  mov     rcx, [rsp+140h+hKey]; hKey
0x14001edd1  lea     rax, [rbp+40h+Data]
0x14001edd5  mov     dword ptr [rsp+140h+pvData], r13d; bool
0x14001edda  lea     rdx, ValueName; "DefaultConsent"
0x14001ede1  mov     r9d, r13d; dwType
0x14001ede4  mov     [rsp+140h+pdwType], rax; lpData
0x14001ede9  xor     r8d, r8d; Reserved
0x14001edec  call    cs:__imp_RegSetValueExW
0x14001edf2  mov     rcx, [rsp+140h+hKey]; hKey
0x14001edf7  test    rcx, rcx
0x14001edfa  jz      short loc_14001EE02
0x14001edfc  call    cs:__imp_RegCloseKey
0x14001ee02  lea     rcx, [rbp+40h+arg_10]
0x14001ee06  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14001ee0b  mov     r13, 0FFFFFFFF80000002h
0x14001ee12  mov     [rsp+140h+pdwType], rax; phkResult
0x14001ee17  mov     rcx, r13; hKey
0x14001ee1a  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x14001ee21  mov     r9d, 20119h; samDesired
0x14001ee27  xor     r8d, r8d; ulOptions
0x14001ee2a  call    cs:__imp_RegOpenKeyExW
0x14001ee30  test    eax, eax
0x14001ee32  jnz     short loc_14001EE59
0x14001ee34  mov     rsi, [rbp+40h+arg_10]
0x14001ee38  mov     rdi, r15
0x14001ee3b  imul    rcx, rdi, 68h ; 'h'
0x14001ee3f  mov     r8d, 100h; unsigned int
0x14001ee45  mov     rdx, rsi; HKEY
0x14001ee48  add     rcx, rbx; this
0x14001ee4b  call    ?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z; CRegSetting::Load(HKEY__ *,ulong)
0x14001ee50  add     rdi, r12
0x14001ee53  cmp     rdi, 31h ; '1'
0x14001ee57  jnz     short loc_14001EE3B
0x14001ee59  cmp     [rbx+0D0h], r15b
0x14001ee60  lea     rcx, [rbp+40h+arg_10]
0x14001ee64  setz    al
0x14001ee67  mov     [rbx+13F4h], al
0x14001ee6d  cmp     [rbx+68h], r15b
0x14001ee71  setz    al
0x14001ee74  mov     [rbx+13F5h], al
0x14001ee7a  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14001ee7f  mov     r9d, 20119h; samDesired
0x14001ee85  mov     [rsp+140h+pdwType], rax; phkResult
0x14001ee8a  xor     r8d, r8d; ulOptions
0x14001ee8d  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Windows\\Windows E"...
0x14001ee94  mov     rcx, r13; hKey
0x14001ee97  call    cs:__imp_RegOpenKeyExW
0x14001ee9d  test    eax, eax
0x14001ee9f  jnz     short loc_14001EEC6
0x14001eea1  mov     rsi, [rbp+40h+arg_10]
0x14001eea5  mov     rdi, r15
0x14001eea8  imul    rcx, rdi, 68h ; 'h'
0x14001eeac  mov     r8d, 100h; unsigned int
0x14001eeb2  mov     rdx, rsi; HKEY
0x14001eeb5  add     rcx, rbx; this
0x14001eeb8  call    ?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z; CRegSetting::Load(HKEY__ *,ulong)
0x14001eebd  add     rdi, r12
0x14001eec0  cmp     rdi, 31h ; '1'
0x14001eec4  jnz     short loc_14001EEA8
0x14001eec6  mov     edi, 0Ah
0x14001eecb  cmp     [rbx+0D0h], r15b
0x14001eed2  jz      short loc_14001EF02
0x14001eed4  mov     eax, [rbx+0D4h]
0x14001eeda  test    eax, eax
0x14001eedc  jnz     short loc_14001EEE9
0x14001eede  mov     rax, [rbx+0D8h]
0x14001eee5  mov     eax, [rax]
0x14001eee7  jmp     short loc_14001EF08
0x14001eee9  cmp     eax, r12d
0x14001eeec  jnz     short loc_14001EF02
0x14001eeee  mov     rcx, [rbx+0D8h]; String
0x14001eef5  mov     r8d, edi; Radix
0x14001eef8  xor     edx, edx; EndPtr
0x14001eefa  call    cs:__imp_wcstol
0x14001ef00  jmp     short loc_14001EF08
0x14001ef02  mov     eax, [rbx+130h]
0x14001ef08  mov     [rbx+13F8h], eax
0x14001ef0e  cmp     [rbx+68h], r15b
0x14001ef12  jz      short loc_14001EF39
0x14001ef14  cmp     [rbx+6Ch], r15d
0x14001ef18  jnz     short loc_14001EF22
0x14001ef1a  mov     rax, [rbx+70h]
0x14001ef1e  mov     eax, [rax]
0x14001ef20  jmp     short loc_14001EF3F
0x14001ef22  cmp     [rbx+6Ch], r12d
0x14001ef26  jnz     short loc_14001EF39
0x14001ef28  mov     rcx, [rbx+70h]; String
0x14001ef2c  mov     r8d, edi; Radix
0x14001ef2f  xor     edx, edx; EndPtr
0x14001ef31  call    cs:__imp_wcstol
0x14001ef37  jmp     short loc_14001EF3F
0x14001ef39  mov     eax, [rbx+0C8h]
0x14001ef3f  cmp     eax, r12d
0x14001ef42  lea     rcx, [rbp+40h+arg_10]
0x14001ef46  setz    al
0x14001ef49  mov     [rbx+13F6h], al
0x14001ef4f  mov     al, [rbx+0D0h]
0x14001ef55  mov     [rbx+13F2h], al
0x14001ef5b  mov     al, [rbx+68h]
0x14001ef5e  mov     [rbx+13F3h], al
0x14001ef64  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14001ef69  mov     r9d, 20119h; samDesired
0x14001ef6f  mov     [rsp+140h+pdwType], rax; phkResult
0x14001ef74  xor     r8d, r8d; ulOptions
0x14001ef77  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x14001ef7e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14001ef85  call    cs:__imp_RegOpenKeyExW
0x14001ef8b  test    eax, eax
0x14001ef8d  jnz     short loc_14001EFB4
0x14001ef8f  mov     rsi, [rbp+40h+arg_10]
0x14001ef93  mov     rdi, r15
0x14001ef96  imul    rcx, rdi, 68h ; 'h'
0x14001ef9a  mov     r8d, 100h; unsigned int
0x14001efa0  mov     rdx, rsi; HKEY
0x14001efa3  add     rcx, rbx; this
0x14001efa6  call    ?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z; CRegSetting::Load(HKEY__ *,ulong)
0x14001efab  add     rdi, r12
0x14001efae  cmp     rdi, 31h ; '1'
0x14001efb2  jnz     short loc_14001EF96
0x14001efb4  mov     al, [rbx+0D0h]
0x14001efba  lea     rcx, [rbp+40h+arg_10]
0x14001efbe  mov     [rbx+13F0h], al
0x14001efc4  mov     al, [rbx+68h]
0x14001efc7  mov     [rbx+13F1h], al
0x14001efcd  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14001efd2  mov     r9d, 20119h; samDesired
0x14001efd8  mov     [rsp+140h+pdwType], rax; phkResult
0x14001efdd  xor     r8d, r8d; ulOptions
0x14001efe0  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Windows\\Windows E"...
0x14001efe7  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14001efee  call    cs:__imp_RegOpenKeyExW
0x14001eff4  test    eax, eax
0x14001eff6  jnz     short loc_14001F01D
0x14001eff8  mov     rsi, [rbp+40h+arg_10]
0x14001effc  mov     rdi, r15
0x14001efff  imul    rcx, rdi, 68h ; 'h'
  ... truncated ...
```
