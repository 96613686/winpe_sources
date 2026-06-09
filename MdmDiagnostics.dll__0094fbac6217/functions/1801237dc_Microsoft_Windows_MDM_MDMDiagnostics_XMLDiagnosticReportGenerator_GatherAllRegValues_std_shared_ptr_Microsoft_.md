# Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GatherAllRegValues(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>,HKEY__ *)

- ea: `0x1801237dc`
- end: `0x180123f37`
- name: `?GatherAllRegValues@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@PEAUHKEY__@@@Z`
- size: `1883`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180124208`

## callees

- `0x180019000`
- `0x18001981c`
- `0x180019fc4`
- `0x1800ece5c`
- `0x1800ed730`
- `0x1800ee898`
- `0x180107e60`
- `0x1801236f4`
- `0x1801237dc`
- `0x180125748`
- `0x1801257d8`
- `0x180125b18`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x180123b79`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x180123b79`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180123c72`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180123c72`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18012398d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180123a86`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180123ba0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180123c99`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180123e28`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18012398d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180123a86`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180123ba0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180123c99`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180123e28`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180123a05`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180123a05`
- `OLEAUT32!__imp_SysFreeString` at `0x180123ac8`
- `OLEAUT32!__imp_SysFreeString` at `0x180123aef`
- `OLEAUT32!__imp_SysFreeString` at `0x180123ac8`
- `OLEAUT32!__imp_SysFreeString` at `0x180123aef`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180123904`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18012396a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180123a56`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180123b45`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180123c3d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180123da1`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180123e05`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180123904`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18012396a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180123a56`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180123b45`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180123c3d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180123da1`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180123e05`

## string_xrefs

- `0x180123870`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticreportgenerator.cpp`
- `0x180123aac`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticreportgenerator.cpp`
- `0x180123e51`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticreportgenerator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GatherAllRegValues(
        Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator *this,
        _QWORD *a2,
        HKEY a3)
{
  HKEY v3; // r14
  signed int DiagValue; // ebx
  __int64 v7; // rdx
  std::_Ref_count_base *v8; // rcx
  DWORD v10; // r13d
  const unsigned __int16 *v11; // r15
  LSTATUS v12; // eax
  int v13; // edi
  bool v14; // zf
  LSTATUS v15; // eax
  __int64 v16; // rbx
  bool v17; // sf
  __int64 v18; // rdx
  LSTATUS v19; // eax
  bool v20; // sf
  LSTATUS v21; // eax
  int v22; // eax
  WCHAR *v23; // r14
  unsigned int v24; // r8d
  LSTATUS v25; // eax
  bool v26; // sf
  BYTE *v27; // rbx
  bool v28; // sf
  __int64 v29; // rdx
  std::_Ref_count_base *v30; // rcx
  int lpReserved; // [rsp+20h] [rbp-E0h]
  int lpReserveda; // [rsp+20h] [rbp-E0h]
  int lpReservedb; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD lpData[2]; // [rsp+48h] [rbp-B8h] BYREF
  DWORD Type; // [rsp+50h] [rbp-B0h] BYREF
  std::_Ref_count_base *v37[2]; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cchValueName; // [rsp+68h] [rbp-98h] BYREF
  DWORD lpcbData; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD v40[2]; // [rsp+70h] [rbp-90h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp-88h] BYREF
  HKEY v42; // [rsp+80h] [rbp-80h]
  BSTR *p_bstrString; // [rsp+88h] [rbp-78h]
  char v44; // [rsp+90h] [rbp-70h]
  _QWORD *v45; // [rsp+98h] [rbp-68h]
  unsigned __int16 v46[40]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName[264]; // [rsp+F0h] [rbp-10h] BYREF
  BYTE Data[2]; // [rsp+300h] [rbp+200h] BYREF
  unsigned __int16 v49[256]; // [rsp+510h] [rbp+410h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+758h] [rbp+658h]

  v3 = a3;
  v42 = a3;
  v45 = a2;
  memset_0(ValueName, 0, 0x208u);
  cchValueName = 260;
  memset_0(Data, 0, 0x208u);
  cbData = 520;
  *(_OWORD *)v37 = 0;
  DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::DiagKey::GetDiagValue(*a2, 0, v37);
  if ( DiagValue < 0 )
  {
    v7 = 644;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\xmldiagnosticreportgenerator.cpp",
      (const char *)(unsigned int)DiagValue,
      lpReserved);
LABEL_4:
    if ( v37[1] )
      std::_Ref_count_base::_Decref(v37[1]);
    v8 = (std::_Ref_count_base *)a2[1];
    if ( v8 )
      std::_Ref_count_base::_Decref(v8);
    return (unsigned int)DiagValue;
  }
  v10 = 0;
  v11 = (const unsigned __int16 *)((char *)v37[0] + 520);
  while ( 1 )
  {
    cbData = 520;
    cchValueName = 260;
    ValueName[0] = 0;
    *(_WORD *)Data = 0;
    Type = 0;
    v12 = RegEnumValueW(v3, v10, ValueName, &cchValueName, 0, &Type, 0, 0);
    v13 = v12;
    if ( v12 > 0 )
      v13 = (unsigned __int16)v12 | 0x80070000;
    v14 = v13 == 0;
    if ( v13 < 0 )
      goto LABEL_76;
    if ( Type == 1 )
    {
      lpData[0] = 260;
      v15 = RegEnumValueW(v3, v10, ValueName, lpData, 0, &Type, Data, &cbData);
      v13 = v15;
      if ( v15 > 0 )
        v13 = (unsigned __int16)v15 | 0x80070000;
      if ( v13 >= 0 )
      {
        if ( (unsigned int)_o__wcsicmp(v11, L"*") )
        {
          DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(
                        this,
                        v11,
                        (const unsigned __int16 *)Data);
          if ( DiagValue < 0 )
          {
            v7 = 698;
            goto LABEL_3;
          }
        }
        else if ( ValueName[0] )
        {
          DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(
                        this,
                        ValueName,
                        (const unsigned __int16 *)Data);
          if ( DiagValue < 0 )
          {
            v7 = 693;
            goto LABEL_3;
          }
        }
        goto LABEL_75;
      }
      if ( v13 != -2147024662 )
        goto LABEL_86;
      v16 = cbData >> 1;
      bstrString = SysAllocStringLen(0, (int)v16 + 1);
      p_bstrString = &bstrString;
      v44 = 1;
      lpData[0] = 260;
      v13 = RegEnumValueW(v3, v10, ValueName, lpData, 0, &Type, (LPBYTE)bstrString, &cbData);
      v17 = v13 < 0;
      if ( v13 > 0 )
      {
        v13 = (unsigned __int16)v13 | 0x80070000;
        v17 = v13 < 0;
      }
      if ( !v17 )
      {
        bstrString[v16] = 0;
        if ( (unsigned int)_o__wcsicmp(v11, L"*") )
        {
          DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(
                        this,
                        v11,
                        bstrString);
          if ( DiagValue < 0 )
          {
            v18 = 737;
            goto LABEL_30;
          }
        }
        else
        {
          DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(
                        this,
                        ValueName,
                        bstrString);
          if ( DiagValue < 0 )
          {
            v18 = 733;
LABEL_30:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v18,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\xmldiagnosticreportgenerator.cpp",
              (const char *)(unsigned int)DiagValue,
              lpReserveda);
            SysFreeString(bstrString);
            goto LABEL_4;
          }
        }
      }
      v44 = 0;
      SysFreeString(bstrString);
      goto LABEL_75;
    }
    if ( Type == 4 )
    {
      v40[0] = 260;
      lpData[0] = 0;
      lpcbData = 4;
      v19 = RegEnumValueW(v3, v10, ValueName, v40, 0, &Type, (LPBYTE)lpData, &lpcbData);
      v13 = v19;
      if ( v19 > 0 )
        v13 = (unsigned __int16)v19 | 0x80070000;
      v14 = v13 == 0;
      if ( v13 >= 0 )
      {
        DiagValue = _o__itow_s(lpData[0], Data, 260, 10);
        v20 = DiagValue < 0;
        if ( DiagValue > 0 )
        {
          DiagValue = (unsigned __int16)DiagValue | 0x80070000;
          v20 = DiagValue < 0;
        }
        if ( v20 )
        {
          v7 = 762;
          goto LABEL_3;
        }
        if ( (unsigned int)_o__wcsicmp(v11, L"*") )
        {
          DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(
                        this,
                        v11,
                        (const unsigned __int16 *)Data);
          if ( DiagValue < 0 )
          {
            v7 = 772;
            goto LABEL_3;
          }
        }
        else
        {
          DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(
                        this,
                        ValueName,
                        (const unsigned __int16 *)Data);
          if ( DiagValue < 0 )
          {
            v7 = 768;
            goto LABEL_3;
          }
        }
        goto LABEL_75;
      }
      goto LABEL_76;
    }
    if ( Type != 11 )
      break;
    lpcbData = 260;
    *(_QWORD *)lpData = 0;
    v40[0] = 8;
    v21 = RegEnumValueW(v3, v10, ValueName, &lpcbData, 0, &Type, (LPBYTE)lpData, v40);
    v13 = v21;
    if ( v21 > 0 )
      v13 = (unsigned __int16)v21 | 0x80070000;
    v14 = v13 == 0;
    if ( v13 >= 0 )
    {
      v22 = _o__ui64tow_s(*(_QWORD *)lpData, Data, 260, 10);
      DiagValue = v22;
      if ( v22 > 0 )
        DiagValue = (unsigned __int16)v22 | 0x80070000;
      if ( DiagValue < 0 )
      {
        v7 = 795;
        goto LABEL_3;
      }
      v23 = ValueName;
      if ( (unsigned int)_o__wcsicmp(v11, L"*") )
        v23 = (WCHAR *)v11;
      if ( !ValueName[0] )
        goto LABEL_61;
      DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(
                    this,
                    v23,
                    (const unsigned __int16 *)Data);
      if ( DiagValue < 0 )
      {
        v7 = 802;
        goto LABEL_3;
      }
      memset_0(v46, 0, sizeof(v46));
      DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::FormatQwordTimestamp(
                    *(unsigned __int64 *)lpData,
                    v46,
                    v24);
      if ( DiagValue < 0 )
      {
        v7 = 805;
        goto LABEL_3;
      }
      if ( v46[0] )
      {
        memset_0(v49, 0, sizeof(v49));
        DiagValue = StringCchPrintfW(v49, 0x100u, L"%sFriendly", v23);
        if ( DiagValue < 0 )
        {
          v7 = 809;
          goto LABEL_3;
        }
        DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(
                      this,
                      v49,
                      v46);
        if ( DiagValue < 0 )
        {
          v7 = 810;
          goto LABEL_3;
        }
        v3 = v42;
      }
      else
      {
LABEL_61:
        v3 = v42;
      }
      goto LABEL_75;
    }
LABEL_76:
    if ( !v14 )
      goto LABEL_86;
    ++v10;
  }
  if ( Type != 3 )
    goto LABEL_75;
  lpData[0] = 260;
  v25 = RegEnumValueW(v3, v10, ValueName, lpData, 0, 0, 0, &cbData);
  v26 = v25 < 0;
  if ( v25 > 0 )
    v26 = 1;
  if ( !v26 )
  {
    v27 = (BYTE *)operator new[](cbData, (const struct std::nothrow_t *)std::nothrow);
    *(_QWORD *)v40 = v27;
    lpData[0] = 260;
    v13 = RegEnumValueW(v3, v10, ValueName, lpData, 0, 0, v27, &cbData);
    v28 = v13 < 0;
    if ( v13 > 0 )
    {
      v13 = (unsigned __int16)v13 | 0x80070000;
      v28 = v13 < 0;
    }
    if ( !v28 )
    {
      if ( (unsigned int)_o__wcsicmp(v11, L"*") )
      {
        DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(
                      this,
                      v11,
                      v27,
                      cbData);
        if ( DiagValue < 0 )
        {
          v29 = 857;
          goto LABEL_72;
        }
      }
      else
      {
        DiagValue = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(
                      this,
                      ValueName,
                      v27,
                      cbData);
        if ( DiagValue < 0 )
        {
          v29 = 853;
LABEL_72:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v29,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\xmldiagnosticreportgenerator.cpp",
            (const char *)(unsigned int)DiagValue,
            lpReservedb);
          std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(v40);
          goto LABEL_4;
        }
      }
    }
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(v40);
LABEL_75:
    v14 = v13 == 0;
    goto LABEL_76;
  }
LABEL_86:
  if ( v37[1] )
    std::_Ref_count_base::_Decref(v37[1]);
  v30 = (std::_Ref_count_base *)a2[1];
  if ( v30 )
    std::_Ref_count_base::_Decref(v30);
  return 0;
}

```

## disassembly

```asm
0x1801237dc  mov     [rsp-8+arg_18], rbx
0x1801237e1  push    rbp
0x1801237e2  push    rsi
0x1801237e3  push    rdi
0x1801237e4  push    r12
0x1801237e6  push    r13
0x1801237e8  push    r14
0x1801237ea  push    r15
0x1801237ec  lea     rbp, [rsp-620h]
0x1801237f4  sub     rsp, 720h
0x1801237fb  mov     rax, cs:__security_cookie
0x180123802  xor     rax, rsp
0x180123805  mov     [rbp+650h+var_40], rax
0x18012380c  mov     r14, r8
0x18012380f  mov     [rbp+650h+var_6D0], r8
0x180123813  mov     rsi, rdx
0x180123816  mov     r12, rcx
0x180123819  mov     [rbp+650h+var_6B8], rdx
0x18012381d  mov     ebx, 208h
0x180123822  mov     r8d, ebx; Size
0x180123825  xor     edx, edx; Val
0x180123827  lea     rcx, [rbp+650h+ValueName]; void *
0x18012382b  call    memset_0
0x180123830  mov     [rsp+750h+cchValueName], 104h
0x180123838  mov     r8d, ebx; Size
0x18012383b  xor     edx, edx; Val
0x18012383d  lea     rcx, [rbp+650h+Data]; void *
0x180123844  call    memset_0
0x180123849  mov     [rsp+750h+cbData], ebx
0x18012384d  xorps   xmm0, xmm0
0x180123850  movdqu  xmmword ptr [rsp+750h+var_6F8], xmm0
0x180123856  lea     r8, [rsp+750h+var_6F8]
0x18012385b  xor     edx, edx
0x18012385d  mov     rcx, [rsi]
0x180123860  call    ?GetDiagValue@DiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@QEAAJ_KPEAV?$shared_ptr@VDiagValue@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@@Z; Microsoft::Windows::MDM::MDMDiagnostics::DiagKey::GetDiagValue(unsigned __int64,std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagValue> *)
0x180123865  mov     ebx, eax
0x180123867  test    eax, eax
0x180123869  jns     short loc_1801238AC
0x18012386b  mov     edx, 284h; void *
0x180123870  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180123877  mov     r9d, ebx; char *
0x18012387a  mov     rcx, [rbp+658h]; this
0x180123881  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180123886  nop
0x180123887  mov     rcx, [rsp+750h+var_6F8+8]; this
0x18012388c  test    rcx, rcx
0x18012388f  jz      short loc_180123897
0x180123891  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180123896  nop
0x180123897  mov     rcx, [rsi+8]; this
0x18012389b  test    rcx, rcx
0x18012389e  jz      short loc_1801238A5
0x1801238a0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801238a5  mov     eax, ebx
0x1801238a7  jmp     loc_180123F0D
0x1801238ac  xor     ebx, ebx
0x1801238ae  mov     r13d, ebx
0x1801238b1  mov     r15, [rsp+750h+var_6F8]
0x1801238b6  add     r15, 208h
0x1801238bd  mov     [rsp+750h+cbData], 208h
0x1801238c5  mov     [rsp+750h+cchValueName], 104h
0x1801238cd  mov     [rbp+650h+ValueName], bx
0x1801238d1  mov     word ptr [rbp+650h+Data], bx
0x1801238d8  mov     [rsp+750h+Type], ebx
0x1801238dc  mov     [rsp+750h+lpcbData], rbx; lpcbData
0x1801238e1  mov     [rsp+750h+lpData], rbx; lpData
0x1801238e6  lea     rax, [rsp+750h+Type]
0x1801238eb  mov     [rsp+750h+lpType], rax; lpType
0x1801238f0  mov     [rsp+750h+lpReserved], rbx; lpReserved
0x1801238f5  lea     r9, [rsp+750h+cchValueName]; lpcchValueName
0x1801238fa  lea     r8, [rbp+650h+ValueName]; lpValueName
0x1801238fe  mov     edx, r13d; dwIndex
0x180123901  mov     rcx, r14; hKey
0x180123904  call    cs:__imp_RegEnumValueW
0x18012390a  mov     edi, eax
0x18012390c  test    eax, eax
0x18012390e  jle     short loc_180123919
0x180123910  movzx   edi, ax
0x180123913  or      edi, 80070000h
0x180123919  test    edi, edi
0x18012391b  js      loc_180123E93
0x180123921  mov     eax, [rsp+750h+Type]
0x180123925  cmp     eax, 1
0x180123928  jnz     loc_180123AFA
0x18012392e  mov     [rsp+750h+var_708], 104h
0x180123936  lea     rax, [rsp+750h+cbData]
0x18012393b  mov     [rsp+750h+lpcbData], rax; lpcbData
0x180123940  lea     rax, [rbp+650h+Data]
0x180123947  mov     [rsp+750h+lpData], rax; lpData
0x18012394c  lea     rax, [rsp+750h+Type]
0x180123951  mov     [rsp+750h+lpType], rax; lpType
0x180123956  mov     [rsp+750h+lpReserved], rbx; lpReserved
0x18012395b  lea     r9, [rsp+750h+var_708]; lpcchValueName
0x180123960  lea     r8, [rbp+650h+ValueName]; lpValueName
0x180123964  mov     edx, r13d; dwIndex
0x180123967  mov     rcx, r14; hKey
0x18012396a  call    cs:__imp_RegEnumValueW
0x180123970  mov     edi, eax
0x180123972  test    eax, eax
0x180123974  jle     short loc_18012397F
0x180123976  movzx   edi, ax
0x180123979  or      edi, 80070000h
0x18012397f  test    edi, edi
0x180123981  js      short loc_1801239EE
0x180123983  lea     rdx, Delimiter; "*"
0x18012398a  mov     rcx, r15
0x18012398d  call    cs:__imp__o__wcsicmp
0x180123993  test    eax, eax
0x180123995  jnz     short loc_1801239C8
0x180123997  cmp     [rbp+650h+ValueName], bx
0x18012399b  jz      loc_180123E91
0x1801239a1  lea     r8, [rbp+650h+Data]; unsigned __int16 *
0x1801239a8  lea     rdx, [rbp+650h+ValueName]; unsigned __int16 *
0x1801239ac  mov     rcx, r12; this
0x1801239af  call    ?WriteSingleLineData@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(ushort const *,ushort const *)
0x1801239b4  mov     ebx, eax
0x1801239b6  test    eax, eax
0x1801239b8  jns     loc_180123E8F
0x1801239be  mov     edx, 2B5h
0x1801239c3  jmp     loc_180123870
0x1801239c8  lea     r8, [rbp+650h+Data]; unsigned __int16 *
0x1801239cf  mov     rdx, r15; unsigned __int16 *
0x1801239d2  mov     rcx, r12; this
0x1801239d5  call    ?WriteSingleLineData@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(ushort const *,ushort const *)
0x1801239da  mov     ebx, eax
0x1801239dc  test    eax, eax
0x1801239de  jns     loc_180123E8F
0x1801239e4  mov     edx, 2BAh
0x1801239e9  jmp     loc_180123870
0x1801239ee  cmp     edi, 800700EAh
0x1801239f4  jnz     loc_180123EED
0x1801239fa  mov     ebx, [rsp+750h+cbData]
0x1801239fe  shr     ebx, 1
0x180123a00  lea     edx, [rbx+1]; ui
0x180123a03  xor     ecx, ecx; strIn
0x180123a05  call    cs:__imp_SysAllocStringLen
0x180123a0b  mov     [rsp+750h+bstrString], rax
0x180123a10  lea     rcx, [rsp+750h+bstrString]
0x180123a15  mov     [rbp+650h+var_6C8], rcx
0x180123a19  mov     [rbp+650h+var_6C0], 1
0x180123a1d  mov     [rsp+750h+var_708], 104h
0x180123a25  lea     rcx, [rsp+750h+cbData]
0x180123a2a  mov     [rsp+750h+lpcbData], rcx; lpcbData
0x180123a2f  mov     [rsp+750h+lpData], rax; lpData
0x180123a34  lea     rax, [rsp+750h+Type]
0x180123a39  mov     [rsp+750h+lpType], rax; lpType
0x180123a3e  mov     [rsp+750h+lpReserved], 0; int
0x180123a47  lea     r9, [rsp+750h+var_708]; lpcchValueName
0x180123a4c  lea     r8, [rbp+650h+ValueName]; lpValueName
0x180123a50  mov     edx, r13d; dwIndex
0x180123a53  mov     rcx, r14; hKey
0x180123a56  call    cs:__imp_RegEnumValueW
0x180123a5c  mov     edi, eax
0x180123a5e  xor     eax, eax
0x180123a60  test    edi, edi
0x180123a62  jle     short loc_180123A6F
0x180123a64  movzx   edi, di
0x180123a67  or      edi, 80070000h
0x180123a6d  test    edi, edi
0x180123a6f  js      short loc_180123AE5
0x180123a71  mov     ecx, eax
0x180123a73  mov     rax, [rsp+750h+bstrString]
0x180123a78  mov     [rax+rbx*2], cx
0x180123a7c  lea     rdx, Delimiter; "*"
0x180123a83  mov     rcx, r15
0x180123a86  call    cs:__imp__o__wcsicmp
0x180123a8c  mov     r8, [rsp+750h+bstrString]; unsigned __int16 *
0x180123a91  mov     rcx, r12; this
0x180123a94  test    eax, eax
0x180123a96  jnz     short loc_180123AD3
0x180123a98  lea     rdx, [rbp+650h+ValueName]; unsigned __int16 *
0x180123a9c  call    ?WriteSingleLineData@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(ushort const *,ushort const *)
0x180123aa1  mov     ebx, eax
0x180123aa3  test    eax, eax
0x180123aa5  jns     short loc_180123AE5
0x180123aa7  mov     edx, 2DDh; void *
0x180123aac  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180123ab3  mov     r9d, ebx; char *
0x180123ab6  mov     rcx, [rbp+658h]; this
0x180123abd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180123ac2  nop
0x180123ac3  mov     rcx, [rsp+750h+bstrString]; bstrString
0x180123ac8  call    cs:__imp_SysFreeString
0x180123ace  jmp     loc_180123887
0x180123ad3  mov     rdx, r15; unsigned __int16 *
0x180123ad6  call    ?WriteSingleLineData@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(ushort const *,ushort const *)
0x180123adb  mov     ebx, eax
0x180123add  test    eax, eax
0x180123adf  js      loc_180123E9D
0x180123ae5  xor     ebx, ebx
0x180123ae7  mov     [rbp+650h+var_6C0], bl
0x180123aea  mov     rcx, [rsp+750h+bstrString]; bstrString
0x180123aef  call    cs:__imp_SysFreeString
0x180123af5  jmp     loc_180123E91
0x180123afa  cmp     eax, 4
0x180123afd  jnz     loc_180123BED
0x180123b03  mov     [rsp+750h+var_6E0], 104h
0x180123b0b  mov     [rsp+750h+var_708], ebx
0x180123b0f  mov     [rsp+750h+var_6E4], eax
0x180123b13  lea     rax, [rsp+750h+var_6E4]
0x180123b18  mov     [rsp+750h+lpcbData], rax; lpcbData
0x180123b1d  lea     rax, [rsp+750h+var_708]
0x180123b22  mov     [rsp+750h+lpData], rax; lpData
0x180123b27  lea     rax, [rsp+750h+Type]
0x180123b2c  mov     [rsp+750h+lpType], rax; lpType
0x180123b31  mov     [rsp+750h+lpReserved], rbx; lpReserved
0x180123b36  lea     r9, [rsp+750h+var_6E0]; lpcchValueName
0x180123b3b  lea     r8, [rbp+650h+ValueName]; lpValueName
0x180123b3f  mov     edx, r13d; dwIndex
0x180123b42  mov     rcx, r14; hKey
0x180123b45  call    cs:__imp_RegEnumValueW
0x180123b4b  mov     edi, eax
0x180123b4d  test    eax, eax
0x180123b4f  jle     short loc_180123B5A
0x180123b51  movzx   edi, ax
0x180123b54  or      edi, 80070000h
0x180123b5a  test    edi, edi
0x180123b5c  js      loc_180123E93
0x180123b62  mov     r9d, 0Ah
0x180123b68  mov     r8d, 104h
0x180123b6e  lea     rdx, [rbp+650h+Data]
0x180123b75  mov     ecx, [rsp+750h+var_708]
0x180123b79  call    cs:__imp__o__itow_s
0x180123b7f  mov     ebx, eax
0x180123b81  test    eax, eax
0x180123b83  jle     short loc_180123B90
0x180123b85  movzx   ebx, bx
0x180123b88  or      ebx, 80070000h
0x180123b8e  test    ebx, ebx
0x180123b90  js      loc_180123EA7
0x180123b96  lea     rdx, Delimiter; "*"
0x180123b9d  mov     rcx, r15
0x180123ba0  call    cs:__imp__o__wcsicmp
0x180123ba6  lea     r8, [rbp+650h+Data]; unsigned __int16 *
0x180123bad  mov     rcx, r12; this
0x180123bb0  test    eax, eax
0x180123bb2  jnz     short loc_180123BD1
0x180123bb4  lea     rdx, [rbp+650h+ValueName]; unsigned __int16 *
0x180123bb8  call    ?WriteSingleLineData@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(ushort const *,ushort const *)
0x180123bbd  mov     ebx, eax
0x180123bbf  test    eax, eax
0x180123bc1  jns     loc_180123E8F
0x180123bc7  mov     edx, 300h
0x180123bcc  jmp     loc_180123870
0x180123bd1  mov     rdx, r15; unsigned __int16 *
0x180123bd4  call    ?WriteSingleLineData@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(ushort const *,ushort const *)
0x180123bd9  mov     ebx, eax
0x180123bdb  test    eax, eax
0x180123bdd  jns     loc_180123E8F
0x180123be3  mov     edx, 304h
0x180123be8  jmp     loc_180123870
0x180123bed  cmp     eax, 0Bh
0x180123bf0  jnz     loc_180123D68
0x180123bf6  mov     [rsp+750h+var_6E4], 104h
0x180123bfe  mov     qword ptr [rsp+750h+var_708], rbx
0x180123c03  mov     [rsp+750h+var_6E0], 8
0x180123c0b  lea     rax, [rsp+750h+var_6E0]
0x180123c10  mov     [rsp+750h+lpcbData], rax; lpcbData
0x180123c15  lea     rax, [rsp+750h+var_708]
0x180123c1a  mov     [rsp+750h+lpData], rax; lpData
0x180123c1f  lea     rax, [rsp+750h+Type]
0x180123c24  mov     [rsp+750h+lpType], rax; lpType
0x180123c29  mov     [rsp+750h+lpReserved], rbx; lpReserved
0x180123c2e  lea     r9, [rsp+750h+var_6E4]; lpcchValueName
0x180123c33  lea     r8, [rbp+650h+ValueName]; lpValueName
0x180123c37  mov     edx, r13d; dwIndex
0x180123c3a  mov     rcx, r14; hKey
0x180123c3d  call    cs:__imp_RegEnumValueW
0x180123c43  mov     edi, eax
0x180123c45  test    eax, eax
0x180123c47  jle     short loc_180123C52
0x180123c49  movzx   edi, ax
0x180123c4c  or      edi, 80070000h
0x180123c52  test    edi, edi
0x180123c54  js      loc_180123E93
0x180123c5a  mov     r9d, 0Ah
0x180123c60  mov     r8d, 104h
0x180123c66  lea     rdx, [rbp+650h+Data]
0x180123c6d  mov     rcx, qword ptr [rsp+750h+var_708]
0x180123c72  call    cs:__imp__o__ui64tow_s
0x180123c78  mov     ebx, eax
0x180123c7a  test    eax, eax
0x180123c7c  jle     short loc_180123C87
0x180123c7e  movzx   ebx, ax
0x180123c81  or      ebx, 80070000h
0x180123c87  test    ebx, ebx
0x180123c89  js      loc_180123ED9
0x180123c8f  lea     rdx, Delimiter; "*"
0x180123c96  mov     rcx, r15
0x180123c99  call    cs:__imp__o__wcsicmp
0x180123c9f  lea     r14, [rbp+650h+ValueName]
0x180123ca3  xor     ebx, ebx
0x180123ca5  test    eax, eax
0x180123ca7  cmovnz  r14, r15
0x180123cab  cmp     [rbp+650h+ValueName], bx
0x180123caf  jz      loc_180123D5F
0x180123cb5  lea     r8, [rbp+650h+Data]; unsigned __int16 *
0x180123cbc  mov     rdx, r14; unsigned __int16 *
0x180123cbf  mov     rcx, r12; this
0x180123cc2  call    ?WriteSingleLineData@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteSingleLineData(ushort const *,ushort const *)
  ... truncated ...
```
