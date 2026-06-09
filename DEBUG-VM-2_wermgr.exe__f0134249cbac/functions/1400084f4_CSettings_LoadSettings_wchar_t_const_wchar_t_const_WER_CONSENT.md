# CSettings::LoadSettings(wchar_t const *,wchar_t const *,_WER_CONSENT)

- ea: `0x1400084f4`
- end: `0x140008b82`
- name: `?LoadSettings@CSettings@@QEAAJPEB_W0W4_WER_CONSENT@@@Z`
- size: `1678`
- prototype: `__int64 __fastcall(CSettings *__hidden this, const wchar_t *, const wchar_t *, enum _WER_CONSENT)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000e49c`

## callees

- `0x14000470c`
- `0x14000560c`
- `0x140007c50`
- `0x140008220`
- `0x1400084f4`
- `0x14000c394`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x140008888`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1400088cc`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x140008888`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1400088cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008792`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008b66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008792`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008b66`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400087b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140008828`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140008921`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000898a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140008a3d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140008a8a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400087b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140008828`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140008921`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000898a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140008a3d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140008a8a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140008758`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140008758`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140008782`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140008782`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400086c5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140008706`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400086c5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140008706`

## string_xrefs

- `0x140008565`: `BrokerUp`

## pseudocode

```c
__int64 __fastcall CSettings::LoadSettings(CSettings *this, const wchar_t *a2, const wchar_t *a3, DWORD a4)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  unsigned int v6; // ebx
  int v7; // edi
  unsigned int i; // ebx
  __int64 v9; // r9
  HKEY *phkResult; // rax
  HKEY *v11; // rax
  HKEY v12; // rdi
  __int64 j; // rbx
  HKEY *v14; // rax
  HKEY v15; // rdi
  __int64 k; // rbx
  int v17; // eax
  char v18; // cl
  int v19; // eax
  HKEY *v20; // rax
  HKEY v21; // rdi
  __int64 m; // rbx
  HKEY *v23; // rax
  HKEY v24; // rdi
  __int64 n; // rbx
  unsigned int v26; // ebx
  wchar_t *v27; // r9
  HKEY *v28; // rax
  HKEY v29; // rdi
  __int64 ii; // rbx
  HKEY *v31; // rax
  __int64 v32; // rcx
  HKEY v33; // rdi
  __int64 jj; // rbx
  bool pvData; // [rsp+30h] [rbp-D8h]
  bool pvDataa; // [rsp+30h] [rbp-D8h]
  bool pvDatab; // [rsp+30h] [rbp-D8h]
  HKEY v39; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v40; // [rsp+68h] [rbp-A0h]
  const wchar_t *v41; // [rsp+70h] [rbp-98h]
  __int64 v42; // [rsp+78h] [rbp-90h]
  _DWORD v43[2]; // [rsp+80h] [rbp-88h]
  __int64 v44; // [rsp+88h] [rbp-80h]
  int v45; // [rsp+90h] [rbp-78h]
  const wchar_t *v46; // [rsp+98h] [rbp-70h]
  __int64 v47; // [rsp+A0h] [rbp-68h]
  int v48; // [rsp+A8h] [rbp-60h]
  __int64 v49; // [rsp+B0h] [rbp-58h]
  int v50; // [rsp+B8h] [rbp-50h]
  const wchar_t *v51; // [rsp+C0h] [rbp-48h]
  __int64 v52; // [rsp+C8h] [rbp-40h]
  int v53; // [rsp+D0h] [rbp-38h]
  __int64 v54; // [rsp+D8h] [rbp-30h]
  int v55; // [rsp+E0h] [rbp-28h]
  const wchar_t *v56; // [rsp+E8h] [rbp-20h]
  __int64 v57; // [rsp+F0h] [rbp-18h]
  int v58; // [rsp+F8h] [rbp-10h]
  __int64 v59; // [rsp+100h] [rbp-8h]
  HKEY hKey; // [rsp+158h] [rbp+50h] BYREF
  const wchar_t *Data; // [rsp+160h] [rbp+58h] BYREF
  const wchar_t *v62; // [rsp+168h] [rbp+60h] BYREF
  DWORD pcbData; // [rsp+170h] [rbp+68h] BYREF

  pcbData = a4;
  v62 = a3;
  Data = a2;
  v45 = 9;
  hKey = 0;
  v41 = L"Consent";
  LODWORD(v40) = 0;
  v46 = L"ExcludedApplications";
  v42 = 0;
  v51 = L"DebugApplications";
  v43[0] = 4;
  v56 = L"BrokerUp";
  v4 = 0;
  v44 = 1;
  v5 = 0;
  v47 = 0;
  v48 = 13;
  v49 = 0;
  v50 = 0;
  v52 = 0;
  v53 = 14;
  v54 = 0;
  v55 = 0;
  v57 = 0;
  v58 = 22;
  v59 = 0;
  LODWORD(qword_14002DB7C) = 1;
  dword_14002DB78 = 1;
  do
  {
    LOWORD(g_Policy[v5]) = 0;
    ++v4;
    g_Policy[v5 + 12] = 0;
    g_Policy[v5 + 2] = g_Policy[v5 + 1];
    v5 += 13;
  }
  while ( v4 != 49 );
  v6 = 0;
  while ( 1 )
  {
    v7 = CRegSetting::Initialize(
           &g_Policy[13 * (unsigned int)dword_140020298[10 * v6]],
           *((unsigned int *)&CSettings::allHiveSettings + 10 * v6),
           *((_QWORD *)&off_140020288 + 5 * v6),
           (&off_140020290)[5 * v6],
           qword_1400202A0[5 * v6]);
    if ( v7 < 0 )
      break;
    if ( ++v6 >= 0xF )
    {
      for ( i = 0; i < 4; ++i )
      {
        v9 = *(_QWORD *)&v43[10 * i - 2];
        if ( v9 )
        {
          v7 = CRegSetting::Initialize(
                 &g_Policy[13 * (unsigned int)v43[10 * i]],
                 *((unsigned int *)&v40 + 10 * i),
                 (&v41)[5 * i],
                 v9,
                 *(&v44 + 5 * i));
          if ( v7 < 0 )
            goto LABEL_56;
        }
      }
      LODWORD(v62) = 0;
      pcbData = 4;
      if ( RegGetValueW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Consent",
             L"DefaultConsent",
             0x10u,
             0,
             &v62,
             &pcbData) == 2 )
      {
        pcbData = 4;
        if ( !RegGetValueW(
                HKEY_LOCAL_MACHINE,
                L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Consent",
                L"NewUserDefaultConsent",
                0x10u,
                0,
                &v62,
                &pcbData) )
        {
          LODWORD(Data) = (_DWORD)v62;
          v39 = 0;
          if ( (unsigned int)((_DWORD)v62 - 1) <= 3 )
          {
            phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v39);
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
              RegSetValueExW(v39, L"DefaultConsent", 0, 4u, (const BYTE *)&Data, 4u);
            if ( v39 )
              RegCloseKey(v39);
          }
        }
      }
      v11 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
      if ( !RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Policies\\Microsoft\\Windows\\Windows Error Reporting",
              0,
              0x20119u,
              v11) )
      {
        v12 = hKey;
        for ( j = 0; j != 49; ++j )
          CRegSetting::Load((CRegSetting *)&g_Policy[13 * j], v12, 0x100u);
      }
      LOBYTE(word_14002DB84) = byte_14002C860 == 0;
      HIBYTE(word_14002DB84) = byte_14002C7F8 == 0;
      v14 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
      if ( !RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\Windows Error Reporting",
              0,
              0x20119u,
              v14) )
      {
        v15 = hKey;
        for ( k = 0; k != 49; ++k )
          CRegSetting::Load((CRegSetting *)&g_Policy[13 * k], v15, 0x100u);
      }
      if ( !byte_14002C860 )
        goto LABEL_28;
      if ( !dword_14002C864 )
      {
        v17 = *(_DWORD *)qword_14002C868;
        goto LABEL_29;
      }
      if ( dword_14002C864 == 1 )
        v17 = wcstol(qword_14002C868, 0, 10);
      else
LABEL_28:
        v17 = dword_14002C8C0;
LABEL_29:
      v18 = byte_14002C7F8;
      LODWORD(qword_14002DB88) = v17;
      if ( !byte_14002C7F8 )
        goto LABEL_34;
      if ( !dword_14002C7FC )
      {
        v19 = *(_DWORD *)qword_14002C800;
        goto LABEL_35;
      }
      if ( dword_14002C7FC == 1 )
      {
        v19 = wcstol(qword_14002C800, 0, 10);
        v18 = byte_14002C7F8;
      }
      else
      {
LABEL_34:
        v19 = dword_14002C858;
      }
LABEL_35:
      HIBYTE(qword_14002DB7C) = v18;
      byte_14002DB86 = v19 == 1;
      BYTE6(qword_14002DB7C) = byte_14002C860;
      v20 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
      if ( !RegOpenKeyExW(
              HKEY_CURRENT_USER,
              L"Software\\Policies\\Microsoft\\Windows\\Windows Error Reporting",
              0,
              0x20119u,
              v20) )
      {
        v21 = hKey;
        for ( m = 0; m != 49; ++m )
          CRegSetting::Load((CRegSetting *)&g_Policy[13 * m], v21, 0x100u);
      }
      BYTE4(qword_14002DB7C) = byte_14002C860;
      BYTE5(qword_14002DB7C) = byte_14002C7F8;
      v23 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
      if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\Windows Error Reporting", 0, 0x20119u, v23) )
      {
        v24 = hKey;
        for ( n = 0; n != 49; ++n )
          CRegSetting::Load((CRegSetting *)&g_Policy[13 * n], v24, 0x100u);
      }
      v26 = 0;
      while ( 1 )
      {
        v27 = (&off_1400204F0)[5 * v26];
        if ( v27 )
        {
          v7 = CRegSetting::Initialize(
                 &g_Policy[13 * (unsigned int)dword_1400204F8[10 * v26]],
                 *((unsigned int *)&CSettings::adminSettings + 10 * v26),
                 *((_QWORD *)&off_1400204E8 + 5 * v26),
                 v27,
                 qword_140020500[5 * v26]);
          if ( v7 < 0 )
            goto LABEL_56;
        }
        if ( ++v26 >= 0x1E )
        {
          v28 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
          if ( !RegOpenKeyExW(
                  HKEY_LOCAL_MACHINE,
                  L"Software\\Policies\\Microsoft\\Windows\\Windows Error Reporting",
                  0,
                  0x20119u,
                  v28) )
          {
            v29 = hKey;
            for ( ii = 0; ii != 49; ++ii )
              CRegSetting::Load((CRegSetting *)&g_Policy[13 * ii], v29, 0x100u);
          }
          v31 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
          if ( !RegOpenKeyExW(
                  HKEY_LOCAL_MACHINE,
                  L"Software\\Microsoft\\Windows\\Windows Error Reporting",
                  0,
                  0x20119u,
                  v31) )
          {
            v33 = hKey;
            for ( jj = 0; jj != 49; ++jj )
              CRegSetting::Load((CRegSetting *)&g_Policy[13 * jj], v33, 0x100u);
          }
          LODWORD(qword_14002DB7C) = CSettings::ComputeConsent(v32, 0);
          HIDWORD(qword_14002DB88) = UtilRegGetDWORD(
                                       HKEY_LOCAL_MACHINE,
                                       L"SOFTWARE\\Policies\\Microsoft\\SQMClient",
                                       L"MSFTInternal",
                                       0,
                                       0,
                                       pvData);
          if ( !HIDWORD(qword_14002DB88) )
            HIDWORD(qword_14002DB88) = UtilRegGetDWORD(
                                         HKEY_LOCAL_MACHINE,
                                         L"SOFTWARE\\Microsoft\\SQMClient",
                                         L"MSFTInternal",
                                         0,
                                         0,
                                         pvDataa);
          dword_14002DB90 = UtilRegGetDWORD(
                              HKEY_LOCAL_MACHINE,
                              L"SOFTWARE\\Policies\\Microsoft\\SQMClient",
                              L"IsTest",
                              0,
                              0,
                              pvDataa);
          if ( !dword_14002DB90 )
            dword_14002DB90 = UtilRegGetDWORD(
                                HKEY_LOCAL_MACHINE,
                                L"SOFTWARE\\Microsoft\\SQMClient",
                                L"IsTest",
                                0,
                                0,
                                pvDatab);
          v7 = 0;
          goto LABEL_56;
        }
      }
    }
  }
LABEL_56:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400084f4  mov     rax, rsp
0x1400084f7  mov     [rax+20h], r9d
0x1400084fb  mov     [rax+18h], r8
0x1400084ff  mov     [rax+10h], rdx
0x140008503  mov     [rax+8], rcx
0x140008507  push    rbp
0x140008508  push    rbx
0x140008509  push    rsi
0x14000850a  push    rdi
0x14000850b  push    r12
0x14000850d  push    r13
0x14000850f  push    r14
0x140008511  push    r15
0x140008513  lea     rbp, [rax-48h]
0x140008517  sub     rsp, 108h
0x14000851e  xor     esi, esi
0x140008520  mov     [rbp+40h+var_B8], 9
0x140008527  lea     rax, aConsent; "Consent"
0x14000852e  mov     [rbp+40h+hKey], rsi
0x140008532  mov     [rsp+140h+var_D8], rax
0x140008537  lea     r15, ?g_Policy@@3VCSettings@@A; CSettings g_Policy
0x14000853e  lea     rax, aExcludedapplic; "ExcludedApplications"
0x140008545  mov     dword ptr [rsp+140h+var_E0], esi
0x140008549  lea     r14d, [rsi+1]
0x14000854d  mov     [rbp+40h+var_B0], rax
0x140008551  lea     rax, aDebugapplicati; "DebugApplications"
0x140008558  mov     [rsp+140h+var_D0], rsi
0x14000855d  mov     [rbp+40h+var_88], rax
0x140008561  lea     r12d, [rsi+4]
0x140008565  lea     rax, aBrokerup; "BrokerUp"
0x14000856c  mov     [rsp+140h+var_C8], r12d
0x140008571  mov     [rbp+40h+var_60], rax
0x140008575  mov     edx, esi
0x140008577  mov     [rbp+40h+var_C0], r14
0x14000857b  mov     ecx, esi
0x14000857d  mov     [rbp+40h+var_A8], rsi
0x140008581  mov     [rbp+40h+var_A0], 0Dh
0x140008588  mov     [rbp+40h+var_98], rsi
0x14000858c  mov     [rbp+40h+var_90], esi
0x14000858f  mov     [rbp+40h+var_80], rsi
0x140008593  mov     [rbp+40h+var_78], 0Eh
0x14000859a  mov     [rbp+40h+var_70], rsi
0x14000859e  mov     [rbp+40h+var_68], esi
0x1400085a1  mov     [rbp+40h+var_58], rsi
0x1400085a5  mov     [rbp+40h+var_50], 16h
0x1400085ac  mov     [rbp+40h+var_48], rsi
0x1400085b0  mov     dword ptr cs:qword_14002DB7C, r14d
0x1400085b7  mov     cs:dword_14002DB78, r14d
0x1400085be  mov     [rcx+r15], si
0x1400085c3  add     rdx, r14
0x1400085c6  mov     [rcx+r15+60h], rsi
0x1400085cb  mov     rax, [rcx+r15+8]
0x1400085d0  mov     [rcx+r15+10h], rax
0x1400085d5  lea     rcx, [rcx+68h]
0x1400085d9  cmp     rdx, 31h ; '1'
0x1400085dd  jnz     short loc_1400085BE
0x1400085df  mov     ebx, esi
0x1400085e1  lea     r10, __ImageBase
0x1400085e8  mov     eax, ebx
0x1400085ea  lea     rdx, [rax+rax*4]
0x1400085ee  mov     eax, ds:rva dword_140020298[r10+rdx*8]
0x1400085f6  mov     r9, ds:rva off_140020290[r10+rdx*8]; "DontSendAdditionalData" ...
0x1400085fe  mov     r8, ds:rva off_140020288[r10+rdx*8]
0x140008606  imul    rcx, rax, 68h ; 'h'
0x14000860a  mov     rax, ds:rva qword_1400202A0[r10+rdx*8]
0x140008612  mov     edx, ds:rva ?allHiveSettings@CSettings@@0QBUSETTING@1@B[r10+rdx*8]; CSettings::SETTING const near * const CSettings::allHiveSettings ...
0x14000861a  add     rcx, r15
0x14000861d  mov     [rsp+140h+pdwType], rax
0x140008622  call    ?Initialize@CRegSetting@@QEAAJW4_DataType@@PEB_W1_K@Z; CRegSetting::Initialize(_DataType,wchar_t const *,wchar_t const *,unsigned __int64)
0x140008627  mov     edi, eax
0x140008629  test    eax, eax
0x14000862b  js      loc_140008B5D
0x140008631  add     ebx, r14d
0x140008634  lea     r10, __ImageBase
0x14000863b  cmp     ebx, 0Fh
0x14000863e  jb      short loc_1400085E8
0x140008640  mov     ebx, esi
0x140008642  mov     eax, ebx
0x140008644  lea     rdx, [rax+rax*4]
0x140008648  mov     r9, [rsp+rdx*8+140h+var_D0]
0x14000864d  test    r9, r9
0x140008650  jz      short loc_14000867F
0x140008652  mov     eax, [rsp+rdx*8+140h+var_C8]
0x140008656  mov     r8, [rsp+rdx*8+140h+var_D8]
0x14000865b  imul    rcx, rax, 68h ; 'h'
0x14000865f  mov     rax, [rbp+rdx*8+40h+var_C0]
0x140008664  mov     edx, dword ptr [rsp+rdx*8+140h+var_E0]
0x140008668  add     rcx, r15
0x14000866b  mov     [rsp+140h+pdwType], rax
0x140008670  call    ?Initialize@CRegSetting@@QEAAJW4_DataType@@PEB_W1_K@Z; CRegSetting::Initialize(_DataType,wchar_t const *,wchar_t const *,unsigned __int64)
0x140008675  mov     edi, eax
0x140008677  test    eax, eax
0x140008679  js      loc_140008B5D
0x14000867f  add     ebx, r14d
0x140008682  cmp     ebx, r12d
0x140008685  jb      short loc_140008642
0x140008687  lea     rax, [rbp+40h+arg_18]
0x14000868b  mov     dword ptr [rbp+40h+arg_10], esi
0x14000868e  mov     [rsp+140h+pcbData], rax; pcbData
0x140008693  lea     rbx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\Windows E"...
0x14000869a  lea     rax, [rbp+40h+arg_10]
0x14000869e  mov     [rbp+40h+arg_18], r12d
0x1400086a2  mov     [rsp+140h+pvData], rax; pvData
0x1400086a7  lea     r8, aDefaultconsent; "DefaultConsent"
0x1400086ae  mov     edi, 10h
0x1400086b3  mov     [rsp+140h+pdwType], rsi; pdwType
0x1400086b8  mov     r9d, edi; dwFlags
0x1400086bb  mov     rdx, rbx; lpSubKey
0x1400086be  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1400086c5  call    cs:__imp_RegGetValueW
0x1400086cb  mov     r13, 0FFFFFFFF80000002h
0x1400086d2  cmp     eax, 2
0x1400086d5  jnz     loc_140008798
0x1400086db  lea     rax, [rbp+40h+arg_18]
0x1400086df  mov     [rbp+40h+arg_18], r12d
0x1400086e3  mov     [rsp+140h+pcbData], rax; pcbData
0x1400086e8  lea     r8, aNewuserdefault; "NewUserDefaultConsent"
0x1400086ef  lea     rax, [rbp+40h+arg_10]
0x1400086f3  mov     r9d, edi; dwFlags
0x1400086f6  mov     [rsp+140h+pvData], rax; pvData
0x1400086fb  mov     rdx, rbx; lpSubKey
0x1400086fe  mov     rcx, r13; hkey
0x140008701  mov     [rsp+140h+pdwType], rsi; pdwType
0x140008706  call    cs:__imp_RegGetValueW
0x14000870c  test    eax, eax
0x14000870e  jnz     loc_140008798
0x140008714  mov     eax, dword ptr [rbp+40h+arg_10]
0x140008717  mov     dword ptr [rbp+40h+Data], eax
0x14000871a  dec     eax
0x14000871c  mov     [rsp+140h+var_F0], rsi
0x140008721  cmp     eax, 3
0x140008724  ja      short loc_140008798
0x140008726  lea     rcx, [rsp+140h+var_F0]
0x14000872b  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140008730  mov     [rsp+40h], rsi; lpdwDisposition
0x140008735  lea     rcx, [r13-1]; hKey
0x140008739  mov     [rsp+140h+phkResult], rax; phkResult
0x14000873e  xor     r9d, r9d; lpClass
0x140008741  mov     [rsp+140h+pcbData], rsi; lpSecurityAttributes
0x140008746  xor     r8d, r8d; Reserved
0x140008749  mov     dword ptr [rsp+140h+pvData], 20106h; samDesired
0x140008751  mov     rdx, rbx; lpSubKey
0x140008754  mov     dword ptr [rsp+140h+pdwType], esi; dwOptions
0x140008758  call    cs:__imp_RegCreateKeyExW
0x14000875e  test    eax, eax
0x140008760  jnz     short loc_140008788
0x140008762  mov     rcx, [rsp+140h+var_F0]; hKey
0x140008767  lea     rax, [rbp+40h+Data]
0x14000876b  mov     dword ptr [rsp+140h+pvData], r12d; bool
0x140008770  lea     rdx, aDefaultconsent; "DefaultConsent"
0x140008777  mov     r9d, r12d; dwType
0x14000877a  mov     [rsp+140h+pdwType], rax; lpData
0x14000877f  xor     r8d, r8d; Reserved
0x140008782  call    cs:__imp_RegSetValueExW
0x140008788  mov     rcx, [rsp+140h+var_F0]; hKey
0x14000878d  test    rcx, rcx
0x140008790  jz      short loc_140008798
0x140008792  call    cs:__imp_RegCloseKey
0x140008798  lea     rcx, [rbp+40h+hKey]
0x14000879c  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1400087a1  mov     r9d, 20119h; samDesired
0x1400087a7  mov     [rsp+140h+pdwType], rax; phkResult
0x1400087ac  xor     r8d, r8d; ulOptions
0x1400087af  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x1400087b6  mov     rcx, r13; hKey
0x1400087b9  call    cs:__imp_RegOpenKeyExW
0x1400087bf  mov     r12d, 100h
0x1400087c5  test    eax, eax
0x1400087c7  jnz     short loc_1400087EB
0x1400087c9  mov     rdi, [rbp+40h+hKey]
0x1400087cd  mov     rbx, rsi
0x1400087d0  imul    rcx, rbx, 68h ; 'h'
0x1400087d4  mov     r8d, r12d; unsigned int
0x1400087d7  mov     rdx, rdi; HKEY
0x1400087da  add     rcx, r15; this
0x1400087dd  call    ?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z; CRegSetting::Load(HKEY__ *,ulong)
0x1400087e2  add     rbx, r14
0x1400087e5  cmp     rbx, 31h ; '1'
0x1400087e9  jnz     short loc_1400087D0
0x1400087eb  cmp     cs:byte_14002C860, sil
0x1400087f2  lea     rcx, [rbp+40h+hKey]
0x1400087f6  setz    byte ptr cs:word_14002DB84
0x1400087fd  cmp     cs:byte_14002C7F8, sil
0x140008804  setz    byte ptr cs:word_14002DB84+1
0x14000880b  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140008810  mov     r9d, 20119h; samDesired
0x140008816  mov     [rsp+140h+pdwType], rax; phkResult
0x14000881b  xor     r8d, r8d; ulOptions
0x14000881e  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\Windows E"...
0x140008825  mov     rcx, r13; hKey
0x140008828  call    cs:__imp_RegOpenKeyExW
0x14000882e  test    eax, eax
0x140008830  jnz     short loc_140008854
0x140008832  mov     rdi, [rbp+40h+hKey]
0x140008836  mov     rbx, rsi
0x140008839  imul    rcx, rbx, 68h ; 'h'
0x14000883d  mov     r8d, r12d; unsigned int
0x140008840  mov     rdx, rdi; HKEY
0x140008843  add     rcx, r15; this
0x140008846  call    ?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z; CRegSetting::Load(HKEY__ *,ulong)
0x14000884b  add     rbx, r14
0x14000884e  cmp     rbx, 31h ; '1'
0x140008852  jnz     short loc_140008839
0x140008854  cmp     cs:byte_14002C860, sil
0x14000885b  mov     ebx, 0Ah
0x140008860  jz      short loc_140008890
0x140008862  mov     eax, cs:dword_14002C864
0x140008868  test    eax, eax
0x14000886a  jnz     short loc_140008877
0x14000886c  mov     rax, cs:qword_14002C868
0x140008873  mov     eax, [rax]
0x140008875  jmp     short loc_140008896
0x140008877  cmp     eax, r14d
0x14000887a  jnz     short loc_140008890
0x14000887c  mov     rcx, cs:qword_14002C868; String
0x140008883  mov     r8d, ebx; Radix
0x140008886  xor     edx, edx; EndPtr
0x140008888  call    cs:__imp_wcstol
0x14000888e  jmp     short loc_140008896
0x140008890  mov     eax, cs:dword_14002C8C0
0x140008896  mov     cl, cs:byte_14002C7F8
0x14000889c  mov     dword ptr cs:qword_14002DB88, eax
0x1400088a2  test    cl, cl
0x1400088a4  jz      short loc_1400088DA
0x1400088a6  mov     eax, cs:dword_14002C7FC
0x1400088ac  test    eax, eax
0x1400088ae  jnz     short loc_1400088BB
0x1400088b0  mov     rax, cs:qword_14002C800
0x1400088b7  mov     eax, [rax]
0x1400088b9  jmp     short loc_1400088E0
0x1400088bb  cmp     eax, r14d
0x1400088be  jnz     short loc_1400088DA
0x1400088c0  mov     rcx, cs:qword_14002C800; String
0x1400088c7  mov     r8d, ebx; Radix
0x1400088ca  xor     edx, edx; EndPtr
0x1400088cc  call    cs:__imp_wcstol
0x1400088d2  mov     cl, cs:byte_14002C7F8
0x1400088d8  jmp     short loc_1400088E0
0x1400088da  mov     eax, cs:dword_14002C858
0x1400088e0  cmp     eax, r14d
0x1400088e3  mov     byte ptr cs:qword_14002DB7C+7, cl
0x1400088e9  mov     al, cs:byte_14002C860
0x1400088ef  lea     rcx, [rbp+40h+hKey]
0x1400088f3  setz    cs:byte_14002DB86
0x1400088fa  mov     byte ptr cs:qword_14002DB7C+6, al
0x140008900  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140008905  mov     r9d, 20119h; samDesired
0x14000890b  mov     [rsp+140h+pdwType], rax; phkResult
0x140008910  xor     r8d, r8d; ulOptions
0x140008913  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x14000891a  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140008921  call    cs:__imp_RegOpenKeyExW
0x140008927  test    eax, eax
0x140008929  jnz     short loc_14000894D
0x14000892b  mov     rdi, [rbp+40h+hKey]
0x14000892f  mov     rbx, rsi
0x140008932  imul    rcx, rbx, 68h ; 'h'
0x140008936  mov     r8d, r12d; unsigned int
0x140008939  mov     rdx, rdi; HKEY
0x14000893c  add     rcx, r15; this
0x14000893f  call    ?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z; CRegSetting::Load(HKEY__ *,ulong)
0x140008944  add     rbx, r14
0x140008947  cmp     rbx, 31h ; '1'
0x14000894b  jnz     short loc_140008932
0x14000894d  mov     al, cs:byte_14002C860
0x140008953  lea     rcx, [rbp+40h+hKey]
0x140008957  mov     byte ptr cs:qword_14002DB7C+4, al
0x14000895d  mov     al, cs:byte_14002C7F8
0x140008963  mov     byte ptr cs:qword_14002DB7C+5, al
0x140008969  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14000896e  mov     r9d, 20119h; samDesired
0x140008974  mov     [rsp+140h+pdwType], rax; phkResult
0x140008979  xor     r8d, r8d; ulOptions
0x14000897c  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\Windows E"...
0x140008983  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14000898a  call    cs:__imp_RegOpenKeyExW
0x140008990  test    eax, eax
0x140008992  jnz     short loc_1400089B6
0x140008994  mov     rdi, [rbp+40h+hKey]
0x140008998  mov     rbx, rsi
0x14000899b  imul    rcx, rbx, 68h ; 'h'
0x14000899f  mov     r8d, r12d; unsigned int
0x1400089a2  mov     rdx, rdi; HKEY
0x1400089a5  add     rcx, r15; this
0x1400089a8  call    ?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z; CRegSetting::Load(HKEY__ *,ulong)
0x1400089ad  add     rbx, r14
0x1400089b0  cmp     rbx, 31h ; '1'
0x1400089b4  jnz     short loc_14000899B
0x1400089b6  mov     ebx, esi
0x1400089b8  lea     r10, __ImageBase
0x1400089bf  mov     eax, ebx
0x1400089c1  lea     rdx, [rax+rax*4]
0x1400089c5  mov     r9, ds:rva off_1400204F0[r10+rdx*8]; "DisableArchive" ...
0x1400089cd  test    r9, r9
0x1400089d0  jz      short loc_140008A14
0x1400089d2  mov     eax, ds:rva dword_1400204F8[r10+rdx*8]
0x1400089da  mov     r8, ds:rva off_1400204E8[r10+rdx*8]
0x1400089e2  imul    rcx, rax, 68h ; 'h'
0x1400089e6  mov     rax, ds:rva qword_140020500[r10+rdx*8]
0x1400089ee  mov     edx, ds:rva ?adminSettings@CSettings@@0QBUSETTING@1@B[r10+rdx*8]; CSettings::SETTING const near * const CSettings::adminSettings ...
  ... truncated ...
```
