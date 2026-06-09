# CSettings::LoadSettings(wchar_t const *,wchar_t const *,_WER_CONSENT)

- ea: `0x140020118`
- end: `0x1400207be`
- name: `?LoadSettings@CSettings@@QEAAJPEB_W0W4_WER_CONSENT@@@Z`
- size: `1702`
- prototype: `__int64 __fastcall(CSettings *__hidden this, const wchar_t *, const wchar_t *, enum _WER_CONSENT)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400225cc`
- `0x140024c90`
- `0x140027570`

## callees

- `0x14000551c`
- `0x1400083f0`
- `0x14000857c`
- `0x140012994`
- `0x14001efd0`
- `0x140020118`
- `0x140020e64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x14002048e`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1400204cb`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x14002048e`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1400204cb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14002032f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140020379`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14002032f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140020379`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140020794`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140020794`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400203b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140020425`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140020525`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140020594`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140020651`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400206a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400203b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140020425`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140020525`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140020594`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140020651`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400206a7`

## string_xrefs

- `0x1400201cc`: `BrokerUp`

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
  HKEY *v17; // rax
  HKEY v18; // rsi
  __int64 j; // rdi
  HKEY *v20; // rax
  HKEY v21; // rsi
  __int64 k; // rdi
  int v23; // eax
  int v24; // eax
  int v25; // eax
  HKEY *v26; // rax
  HKEY v27; // rsi
  __int64 m; // rdi
  HKEY *v29; // rax
  HKEY v30; // rsi
  __int64 n; // rdi
  unsigned int v32; // edi
  wchar_t *v33; // r9
  HKEY *v34; // rax
  HKEY v35; // rsi
  __int64 ii; // rdi
  HKEY *v37; // rax
  __int64 v38; // rdx
  HKEY v39; // rsi
  __int64 jj; // rdi
  unsigned int DWORD; // eax
  unsigned int v42; // eax
  bool pvData; // [rsp+28h] [rbp-91h]
  bool pvDataa; // [rsp+28h] [rbp-91h]
  bool pvDatab; // [rsp+28h] [rbp-91h]
  _DWORD v47[2]; // [rsp+40h] [rbp-79h]
  const wchar_t *v48; // [rsp+48h] [rbp-71h]
  const wchar_t *v49; // [rsp+50h] [rbp-69h]
  _DWORD v50[2]; // [rsp+58h] [rbp-61h]
  __int64 v51; // [rsp+60h] [rbp-59h]
  int v52; // [rsp+68h] [rbp-51h]
  const wchar_t *v53; // [rsp+70h] [rbp-49h]
  const wchar_t *v54; // [rsp+78h] [rbp-41h]
  int v55; // [rsp+80h] [rbp-39h]
  __int64 v56; // [rsp+88h] [rbp-31h]
  int v57; // [rsp+90h] [rbp-29h]
  const wchar_t *v58; // [rsp+98h] [rbp-21h]
  const wchar_t *v59; // [rsp+A0h] [rbp-19h]
  int v60; // [rsp+A8h] [rbp-11h]
  __int64 v61; // [rsp+B0h] [rbp-9h]
  int v62; // [rsp+B8h] [rbp-1h]
  const wchar_t *v63; // [rsp+C0h] [rbp+7h]
  const wchar_t *v64; // [rsp+C8h] [rbp+Fh]
  int v65; // [rsp+D0h] [rbp+17h]
  __int64 v66; // [rsp+D8h] [rbp+1Fh]
  unsigned int v67; // [rsp+120h] [rbp+67h] BYREF
  HKEY hKey; // [rsp+128h] [rbp+6Fh] BYREF
  DWORD pcbData; // [rsp+138h] [rbp+7Fh] BYREF

  pcbData = a4;
  hKey = 0;
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
  v47[0] = 0;
  v48 = L"Consent";
  v49 = a2;
  v53 = L"ExcludedApplications";
  v11 = 0;
  v50[0] = 4;
  v58 = L"DebugApplications";
  v51 = 1;
  v63 = L"BrokerUp";
  v12 = 0;
  v52 = 9;
  v54 = v6;
  v55 = 13;
  v56 = 0;
  v57 = 0;
  v59 = v6;
  v60 = 14;
  v61 = 0;
  v62 = 0;
  v64 = a2;
  v65 = 22;
  v66 = 0;
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
            (char *)this + 104 * (unsigned int)dword_140063F08[10 * v13],
            *((unsigned int *)&CSettings::allHiveSettings + 10 * v13),
            *((_QWORD *)&off_140063EF8 + 5 * v13),
            (&off_140063F00)[5 * v13],
            qword_140063F10[5 * v13]);
    if ( v14 < 0 )
      break;
    if ( ++v13 >= 0xF )
    {
      for ( i = 0; i < 4; ++i )
      {
        v16 = *(_QWORD *)&v50[10 * i - 2];
        if ( v16 )
        {
          v14 = CRegSetting::Initialize(
                  (char *)this + 104 * (unsigned int)v50[10 * i],
                  (unsigned int)v47[10 * i],
                  (&v48)[5 * i],
                  v16,
                  *(&v51 + 5 * i));
          if ( v14 < 0 )
            goto LABEL_61;
        }
      }
      v67 = 0;
      pcbData = 4;
      if ( RegGetValueW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Consent",
             L"DefaultConsent",
             0x10u,
             0,
             &v67,
             &pcbData) == 2 )
      {
        pcbData = 4;
        if ( !RegGetValueW(
                HKEY_LOCAL_MACHINE,
                L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Consent",
                L"NewUserDefaultConsent",
                0x10u,
                0,
                &v67,
                &pcbData) )
          CSettings::SetUserDefaultConsent(v67);
      }
      v17 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
      if ( !RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Policies\\Microsoft\\Windows\\Windows Error Reporting",
              0,
              0x20119u,
              v17) )
      {
        v18 = hKey;
        for ( j = 0; j != 49; ++j )
          CRegSetting::Load((CSettings *)((char *)this + 104 * j), v18, 0x100u);
      }
      *((_BYTE *)this + 5108) = *((_BYTE *)this + 208) == 0;
      *((_BYTE *)this + 5109) = *((_BYTE *)this + 104) == 0;
      v20 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
      if ( !RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\Windows Error Reporting",
              0,
              0x20119u,
              v20) )
      {
        v21 = hKey;
        for ( k = 0; k != 49; ++k )
          CRegSetting::Load((CSettings *)((char *)this + 104 * k), v21, 0x100u);
      }
      if ( !*((_BYTE *)this + 208) )
        goto LABEL_33;
      v23 = *((_DWORD *)this + 53);
      if ( !v23 )
      {
        v24 = **((_DWORD **)this + 27);
        goto LABEL_34;
      }
      if ( v23 == 1 )
        v24 = wcstol(*((const wchar_t **)this + 27), 0, 10);
      else
LABEL_33:
        v24 = *((_DWORD *)this + 76);
LABEL_34:
      *((_DWORD *)this + 1278) = v24;
      if ( !*((_BYTE *)this + 104) )
        goto LABEL_39;
      if ( !*((_DWORD *)this + 27) )
      {
        v25 = **((_DWORD **)this + 14);
        goto LABEL_40;
      }
      if ( *((_DWORD *)this + 27) == 1 )
        v25 = wcstol(*((const wchar_t **)this + 14), 0, 10);
      else
LABEL_39:
        v25 = *((_DWORD *)this + 50);
LABEL_40:
      *((_BYTE *)this + 5110) = v25 == 1;
      *((_BYTE *)this + 5106) = *((_BYTE *)this + 208);
      *((_BYTE *)this + 5107) = *((_BYTE *)this + 104);
      v26 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
      if ( !RegOpenKeyExW(
              HKEY_CURRENT_USER,
              L"Software\\Policies\\Microsoft\\Windows\\Windows Error Reporting",
              0,
              0x20119u,
              v26) )
      {
        v27 = hKey;
        for ( m = 0; m != 49; ++m )
          CRegSetting::Load((CSettings *)((char *)this + 104 * m), v27, 0x100u);
      }
      *((_BYTE *)this + 5104) = *((_BYTE *)this + 208);
      *((_BYTE *)this + 5105) = *((_BYTE *)this + 104);
      v29 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
      if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\Windows Error Reporting", 0, 0x20119u, v29) )
      {
        v30 = hKey;
        for ( n = 0; n != 49; ++n )
          CRegSetting::Load((CSettings *)((char *)this + 104 * n), v30, 0x100u);
      }
      v32 = 0;
      while ( 1 )
      {
        v33 = (&off_140063A50)[5 * v32];
        if ( v33 )
        {
          v14 = CRegSetting::Initialize(
                  (char *)this + 104 * (unsigned int)dword_140063A58[10 * v32],
                  *((unsigned int *)&CSettings::adminSettings + 10 * v32),
                  *((_QWORD *)&off_140063A48 + 5 * v32),
                  v33,
                  qword_140063A60[5 * v32]);
          if ( v14 < 0 )
            goto LABEL_61;
        }
        if ( ++v32 >= 0x1E )
        {
          v34 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
          if ( !RegOpenKeyExW(
                  HKEY_LOCAL_MACHINE,
                  L"Software\\Policies\\Microsoft\\Windows\\Windows Error Reporting",
                  0,
                  0x20119u,
                  v34) )
          {
            v35 = hKey;
            for ( ii = 0; ii != 49; ++ii )
              CRegSetting::Load((CSettings *)((char *)this + 104 * ii), v35, 0x100u);
          }
          v37 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
          if ( !RegOpenKeyExW(
                  HKEY_LOCAL_MACHINE,
                  L"Software\\Microsoft\\Windows\\Windows Error Reporting",
                  0,
                  0x20119u,
                  v37) )
          {
            v39 = hKey;
            for ( jj = 0; jj != 49; ++jj )
              CRegSetting::Load((CSettings *)((char *)this + 104 * jj), v39, 0x100u);
          }
          LOBYTE(v38) = a2 != 0;
          *((_DWORD *)this + 1275) = CSettings::ComputeConsent(this, v38);
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
          v42 = UtilRegGetDWORD(
                  HKEY_LOCAL_MACHINE,
                  L"SOFTWARE\\Policies\\Microsoft\\SQMClient",
                  L"IsTest",
                  0,
                  0,
                  pvDataa);
          *((_DWORD *)this + 1280) = v42;
          if ( !v42 )
            *((_DWORD *)this + 1280) = UtilRegGetDWORD(
                                         HKEY_LOCAL_MACHINE,
                                         L"SOFTWARE\\Microsoft\\SQMClient",
                                         L"IsTest",
                                         0,
                                         0,
                                         pvDatab);
          v14 = 0;
          goto LABEL_61;
        }
      }
    }
  }
LABEL_61:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140020118  mov     [rsp-8+arg_10], rbx
0x14002011d  mov     [rsp-8+arg_18], r9d
0x140020122  push    rbp
0x140020123  push    rsi
0x140020124  push    rdi
0x140020125  push    r12
0x140020127  push    r13
0x140020129  push    r14
0x14002012b  push    r15
0x14002012d  lea     rbp, [rsp-27h]
0x140020132  sub     rsp, 0E0h
0x140020139  xor     r15d, r15d
0x14002013c  mov     r14, rdx
0x14002013f  mov     [rbp+57h+hKey], r15
0x140020143  mov     rbx, rcx
0x140020146  mov     r9d, r15d
0x140020149  test    r8, r8
0x14002014c  jz      short loc_140020192
0x14002014e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140020152  inc     rax
0x140020155  cmp     [r8+rax*2], r15w
0x14002015a  jnz     short loc_140020152
0x14002015c  lea     rcx, [r8+rax*2]
0x140020160  jmp     short loc_140020183
0x140020162  sub     rcx, 2
0x140020166  movzx   eax, word ptr [rcx]
0x140020169  sub     ax, 2Fh ; '/'
0x14002016d  cmp     ax, 2Dh ; '-'
0x140020171  ja      short loc_140020183
0x140020173  mov     rdx, 200000000801h
0x14002017d  bt      rdx, rax
0x140020181  jb      short loc_14002018B
0x140020183  mov     r9, rcx
0x140020186  cmp     rcx, r8
0x140020189  ja      short loc_140020162
0x14002018b  test    r9, r9
0x14002018e  cmovz   r9, r8
0x140020192  lea     rax, aConsent; "Consent"
0x140020199  mov     [rbp+57h+var_D0], r15d
0x14002019d  mov     [rbp+57h+var_C8], rax
0x1400201a1  mov     r13d, 4
0x1400201a7  lea     rax, aExcludedapplic; "ExcludedApplications"
0x1400201ae  mov     [rbp+57h+var_C0], r14
0x1400201b2  mov     [rbp+57h+var_A0], rax
0x1400201b6  mov     rdx, r15
0x1400201b9  lea     rax, aDebugapplicati; "DebugApplications"
0x1400201c0  mov     [rbp+57h+var_B8], r13d
0x1400201c4  lea     r12d, [r13-3]
0x1400201c8  mov     [rbp+57h+var_78], rax
0x1400201cc  lea     rax, aBrokerup; "BrokerUp"
0x1400201d3  mov     [rbp+57h+var_B0], r12
0x1400201d7  mov     [rbp+57h+var_50], rax
0x1400201db  mov     rcx, r15
0x1400201de  mov     [rbp+57h+var_A8], 9
0x1400201e5  mov     [rbp+57h+var_98], r9
0x1400201e9  mov     [rbp+57h+var_90], 0Dh
0x1400201f0  mov     [rbp+57h+var_88], r15
0x1400201f4  mov     [rbp+57h+var_80], r15d
0x1400201f8  mov     [rbp+57h+var_70], r9
0x1400201fc  mov     [rbp+57h+var_68], 0Eh
0x140020203  mov     [rbp+57h+var_60], r15
0x140020207  mov     [rbp+57h+var_58], r15d
0x14002020b  mov     [rbp+57h+var_48], r14
0x14002020f  mov     [rbp+57h+var_40], 16h
0x140020216  mov     [rbp+57h+var_38], r15
0x14002021a  mov     [rbx+13ECh], r12d
0x140020221  mov     [rbx+13E8h], r12d
0x140020228  mov     [rbx+rcx], r15w
0x14002022d  add     rdx, r12
0x140020230  mov     [rbx+rcx+60h], r15
0x140020235  mov     rax, [rbx+rcx+8]
0x14002023a  mov     [rbx+rcx+10h], rax
0x14002023f  lea     rcx, [rcx+68h]
0x140020243  cmp     rdx, 31h ; '1'
0x140020247  jnz     short loc_140020228
0x140020249  mov     edi, r15d
0x14002024c  lea     r10, __ImageBase
0x140020253  mov     eax, edi
0x140020255  lea     rdx, [rax+rax*4]
0x140020259  mov     eax, ds:rva dword_140063F08[r10+rdx*8]
0x140020261  mov     r9, ds:rva off_140063F00[r10+rdx*8]; "DontSendAdditionalData" ...
0x140020269  mov     r8, ds:rva off_140063EF8[r10+rdx*8]
0x140020271  imul    rcx, rax, 68h ; 'h'
0x140020275  mov     rax, ds:rva qword_140063F10[r10+rdx*8]
0x14002027d  mov     edx, ds:rva ?allHiveSettings@CSettings@@0QBUSETTING@1@B[r10+rdx*8]; CSettings::SETTING const near * const CSettings::allHiveSettings ...
0x140020285  add     rcx, rbx
0x140020288  mov     [rsp+110h+pdwType], rax
0x14002028d  call    ?Initialize@CRegSetting@@QEAAJW4_DataType@@PEB_W1_K@Z; CRegSetting::Initialize(_DataType,wchar_t const *,wchar_t const *,unsigned __int64)
0x140020292  mov     esi, eax
0x140020294  test    eax, eax
0x140020296  js      loc_14002078B
0x14002029c  add     edi, r12d
0x14002029f  lea     r10, __ImageBase
0x1400202a6  cmp     edi, 0Fh
0x1400202a9  jb      short loc_140020253
0x1400202ab  mov     edi, r15d
0x1400202ae  mov     eax, edi
0x1400202b0  lea     rdx, [rax+rax*4]
0x1400202b4  mov     r9, [rbp+rdx*8+57h+var_C0]
0x1400202b9  test    r9, r9
0x1400202bc  jz      short loc_1400202EB
0x1400202be  mov     eax, [rbp+rdx*8+57h+var_B8]
0x1400202c2  mov     r8, [rbp+rdx*8+57h+var_C8]
0x1400202c7  imul    rcx, rax, 68h ; 'h'
0x1400202cb  mov     rax, [rbp+rdx*8+57h+var_B0]
0x1400202d0  mov     edx, [rbp+rdx*8+57h+var_D0]
0x1400202d4  add     rcx, rbx
0x1400202d7  mov     [rsp+110h+pdwType], rax
0x1400202dc  call    ?Initialize@CRegSetting@@QEAAJW4_DataType@@PEB_W1_K@Z; CRegSetting::Initialize(_DataType,wchar_t const *,wchar_t const *,unsigned __int64)
0x1400202e1  mov     esi, eax
0x1400202e3  test    eax, eax
0x1400202e5  js      loc_14002078B
0x1400202eb  add     edi, r12d
0x1400202ee  cmp     edi, r13d
0x1400202f1  jb      short loc_1400202AE
0x1400202f3  lea     rax, [rbp+57h+arg_18]
0x1400202f7  mov     [rbp+57h+arg_0], r15d
0x1400202fb  mov     [rsp+110h+pcbData], rax; pcbData
0x140020300  lea     r8, ValueName; "DefaultConsent"
0x140020307  lea     rax, [rbp+57h+arg_0]
0x14002030b  mov     [rbp+57h+arg_18], r13d
0x14002030f  mov     [rsp+110h+pvData], rax; pvData
0x140020314  lea     rdx, aSoftwareMicros_12; "Software\\Microsoft\\Windows\\Windows E"...
0x14002031b  mov     edi, 10h
0x140020320  mov     [rsp+110h+pdwType], r15; pdwType
0x140020325  mov     r9d, edi; dwFlags
0x140020328  mov     rcx, 0FFFFFFFF80000001h; hkey
0x14002032f  call    cs:__imp_RegGetValueW
0x140020336  nop     dword ptr [rax+rax+00h]
0x14002033b  mov     r13, 0FFFFFFFF80000002h
0x140020342  cmp     eax, 2
0x140020345  jnz     short loc_140020391
0x140020347  lea     rax, [rbp+57h+arg_18]
0x14002034b  mov     [rbp+57h+arg_18], 4
0x140020352  mov     [rsp+110h+pcbData], rax; pcbData
0x140020357  lea     r8, aNewuserdefault; "NewUserDefaultConsent"
0x14002035e  lea     rax, [rbp+57h+arg_0]
0x140020362  mov     r9d, edi; dwFlags
0x140020365  mov     [rsp+110h+pvData], rax; bool
0x14002036a  lea     rdx, aSoftwareMicros_12; "Software\\Microsoft\\Windows\\Windows E"...
0x140020371  mov     rcx, r13; hkey
0x140020374  mov     [rsp+110h+pdwType], r15; pdwType
0x140020379  call    cs:__imp_RegGetValueW
0x140020380  nop     dword ptr [rax+rax+00h]
0x140020385  test    eax, eax
0x140020387  jnz     short loc_140020391
0x140020389  mov     ecx, [rbp+57h+arg_0]
0x14002038c  call    ?SetUserDefaultConsent@CSettings@@SAJW4_CONSENT_SETTING@@@Z; CSettings::SetUserDefaultConsent(_CONSENT_SETTING)
0x140020391  lea     rcx, [rbp+57h+hKey]
0x140020395  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14002039a  mov     r9d, 20119h; samDesired
0x1400203a0  mov     [rsp+110h+pdwType], rax; phkResult
0x1400203a5  xor     r8d, r8d; ulOptions
0x1400203a8  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x1400203af  mov     rcx, r13; hKey
0x1400203b2  call    cs:__imp_RegOpenKeyExW
0x1400203b9  nop     dword ptr [rax+rax+00h]
0x1400203be  test    eax, eax
0x1400203c0  jnz     short loc_1400203E7
0x1400203c2  mov     rsi, [rbp+57h+hKey]
0x1400203c6  mov     rdi, r15
0x1400203c9  imul    rcx, rdi, 68h ; 'h'
0x1400203cd  mov     r8d, 100h; unsigned int
0x1400203d3  mov     rdx, rsi; HKEY
0x1400203d6  add     rcx, rbx; this
0x1400203d9  call    ?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z; CRegSetting::Load(HKEY__ *,ulong)
0x1400203de  add     rdi, r12
0x1400203e1  cmp     rdi, 31h ; '1'
0x1400203e5  jnz     short loc_1400203C9
0x1400203e7  cmp     [rbx+0D0h], r15b
0x1400203ee  lea     rcx, [rbp+57h+hKey]
0x1400203f2  setz    al
0x1400203f5  mov     [rbx+13F4h], al
0x1400203fb  cmp     [rbx+68h], r15b
0x1400203ff  setz    al
0x140020402  mov     [rbx+13F5h], al
0x140020408  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14002040d  mov     r9d, 20119h; samDesired
0x140020413  mov     [rsp+110h+pdwType], rax; phkResult
0x140020418  xor     r8d, r8d; ulOptions
0x14002041b  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Windows\\Windows E"...
0x140020422  mov     rcx, r13; hKey
0x140020425  call    cs:__imp_RegOpenKeyExW
0x14002042c  nop     dword ptr [rax+rax+00h]
0x140020431  test    eax, eax
0x140020433  jnz     short loc_14002045A
0x140020435  mov     rsi, [rbp+57h+hKey]
0x140020439  mov     rdi, r15
0x14002043c  imul    rcx, rdi, 68h ; 'h'
0x140020440  mov     r8d, 100h; unsigned int
0x140020446  mov     rdx, rsi; HKEY
0x140020449  add     rcx, rbx; this
0x14002044c  call    ?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z; CRegSetting::Load(HKEY__ *,ulong)
0x140020451  add     rdi, r12
0x140020454  cmp     rdi, 31h ; '1'
0x140020458  jnz     short loc_14002043C
0x14002045a  mov     edi, 0Ah
0x14002045f  cmp     [rbx+0D0h], r15b
0x140020466  jz      short loc_14002049C
0x140020468  mov     eax, [rbx+0D4h]
0x14002046e  test    eax, eax
0x140020470  jnz     short loc_14002047D
0x140020472  mov     rax, [rbx+0D8h]
0x140020479  mov     eax, [rax]
0x14002047b  jmp     short loc_1400204A2
0x14002047d  cmp     eax, r12d
0x140020480  jnz     short loc_14002049C
0x140020482  mov     rcx, [rbx+0D8h]; String
0x140020489  mov     r8d, edi; Radix
0x14002048c  xor     edx, edx; EndPtr
0x14002048e  call    cs:__imp_wcstol
0x140020495  nop     dword ptr [rax+rax+00h]
0x14002049a  jmp     short loc_1400204A2
0x14002049c  mov     eax, [rbx+130h]
0x1400204a2  mov     [rbx+13F8h], eax
0x1400204a8  cmp     [rbx+68h], r15b
0x1400204ac  jz      short loc_1400204D9
0x1400204ae  cmp     [rbx+6Ch], r15d
0x1400204b2  jnz     short loc_1400204BC
0x1400204b4  mov     rax, [rbx+70h]
0x1400204b8  mov     eax, [rax]
0x1400204ba  jmp     short loc_1400204DF
0x1400204bc  cmp     [rbx+6Ch], r12d
0x1400204c0  jnz     short loc_1400204D9
0x1400204c2  mov     rcx, [rbx+70h]; String
0x1400204c6  mov     r8d, edi; Radix
0x1400204c9  xor     edx, edx; EndPtr
0x1400204cb  call    cs:__imp_wcstol
0x1400204d2  nop     dword ptr [rax+rax+00h]
0x1400204d7  jmp     short loc_1400204DF
0x1400204d9  mov     eax, [rbx+0C8h]
0x1400204df  cmp     eax, r12d
0x1400204e2  lea     rcx, [rbp+57h+hKey]
0x1400204e6  setz    al
0x1400204e9  mov     [rbx+13F6h], al
0x1400204ef  mov     al, [rbx+0D0h]
0x1400204f5  mov     [rbx+13F2h], al
0x1400204fb  mov     al, [rbx+68h]
0x1400204fe  mov     [rbx+13F3h], al
0x140020504  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140020509  mov     r9d, 20119h; samDesired
0x14002050f  mov     [rsp+110h+pdwType], rax; phkResult
0x140020514  xor     r8d, r8d; ulOptions
0x140020517  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x14002051e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140020525  call    cs:__imp_RegOpenKeyExW
0x14002052c  nop     dword ptr [rax+rax+00h]
0x140020531  test    eax, eax
0x140020533  jnz     short loc_14002055A
0x140020535  mov     rsi, [rbp+57h+hKey]
0x140020539  mov     rdi, r15
0x14002053c  imul    rcx, rdi, 68h ; 'h'
0x140020540  mov     r8d, 100h; unsigned int
0x140020546  mov     rdx, rsi; HKEY
0x140020549  add     rcx, rbx; this
0x14002054c  call    ?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z; CRegSetting::Load(HKEY__ *,ulong)
0x140020551  add     rdi, r12
0x140020554  cmp     rdi, 31h ; '1'
0x140020558  jnz     short loc_14002053C
0x14002055a  mov     al, [rbx+0D0h]
0x140020560  lea     rcx, [rbp+57h+hKey]
0x140020564  mov     [rbx+13F0h], al
0x14002056a  mov     al, [rbx+68h]
0x14002056d  mov     [rbx+13F1h], al
0x140020573  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140020578  mov     r9d, 20119h; samDesired
0x14002057e  mov     [rsp+110h+pdwType], rax; phkResult
0x140020583  xor     r8d, r8d; ulOptions
0x140020586  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Windows\\Windows E"...
0x14002058d  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140020594  call    cs:__imp_RegOpenKeyExW
0x14002059b  nop     dword ptr [rax+rax+00h]
0x1400205a0  test    eax, eax
0x1400205a2  jnz     short loc_1400205C9
0x1400205a4  mov     rsi, [rbp+57h+hKey]
0x1400205a8  mov     rdi, r15
0x1400205ab  imul    rcx, rdi, 68h ; 'h'
0x1400205af  mov     r8d, 100h; unsigned int
0x1400205b5  mov     rdx, rsi; HKEY
0x1400205b8  add     rcx, rbx; this
0x1400205bb  call    ?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z; CRegSetting::Load(HKEY__ *,ulong)
0x1400205c0  add     rdi, r12
0x1400205c3  cmp     rdi, 31h ; '1'
0x1400205c7  jnz     short loc_1400205AB
0x1400205c9  mov     edi, r15d
0x1400205cc  lea     r10, __ImageBase
0x1400205d3  mov     eax, edi
0x1400205d5  lea     rdx, [rax+rax*4]
0x1400205d9  mov     r9, ds:rva off_140063A50[r10+rdx*8]; "DisableArchive" ...
0x1400205e1  test    r9, r9
0x1400205e4  jz      short loc_140020628
0x1400205e6  mov     eax, ds:rva dword_140063A58[r10+rdx*8]
0x1400205ee  mov     r8, ds:rva off_140063A48[r10+rdx*8]
0x1400205f6  imul    rcx, rax, 68h ; 'h'
0x1400205fa  mov     rax, ds:rva qword_140063A60[r10+rdx*8]
0x140020602  mov     edx, ds:rva ?adminSettings@CSettings@@0QBUSETTING@1@B[r10+rdx*8]; CSettings::SETTING const near * const CSettings::adminSettings ...
0x14002060a  add     rcx, rbx
0x14002060d  mov     [rsp+110h+pdwType], rax
0x140020612  call    ?Initialize@CRegSetting@@QEAAJW4_DataType@@PEB_W1_K@Z; CRegSetting::Initialize(_DataType,wchar_t const *,wchar_t const *,unsigned __int64)
0x140020617  mov     esi, eax
  ... truncated ...
```
