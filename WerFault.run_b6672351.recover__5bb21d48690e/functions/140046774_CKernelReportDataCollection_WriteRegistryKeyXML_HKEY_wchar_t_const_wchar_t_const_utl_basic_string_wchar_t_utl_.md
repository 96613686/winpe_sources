# CKernelReportDataCollection::WriteRegistryKeyXML(HKEY__ *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x140046774`
- end: `0x140046bb4`
- name: `?WriteRegistryKeyXML@CKernelReportDataCollection@@AEAAJPEAUHKEY__@@PEB_W1PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `1088`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x140045078`

## callees

- `0x140002748`
- `0x1400041e8`
- `0x1400054e4`
- `0x14000551c`
- `0x14000e658`
- `0x140014a88`
- `0x1400372dc`
- `0x14003b56c`
- `0x140045b18`
- `0x140045b54`
- `0x140046774`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x14004698f`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x14004698f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400468bd`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400468bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140046b30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140046b93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140046b30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140046b93`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004680a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004680a`

## string_xrefs

- `0x1400469af`: `CKernelReportDataCollection::WriteRegistryKeyXML`
- `0x1400469ff`: `CKernelReportDataCollection::WriteRegistryKeyXML`
- `0x140046aa8`: `CKernelReportDataCollection::WriteRegistryKeyXML`
- `0x140046ad2`: `CKernelReportDataCollection::WriteRegistryKeyXML`
- `0x140046b50`: `CKernelReportDataCollection::WriteRegistryKeyXML`
- `0x140046836`: `RegOpenKeyEx failed`
- `0x1400469f3`: `PrintRegKeyXML failed`
- `0x140046a57`: `Sprintf failed while closing the xml node name`

## pseudocode

```c
__int64 __fastcall CKernelReportDataCollection::WriteRegistryKeyXML(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v7; // r14
  WCHAR *v8; // rdi
  BYTE *v9; // rbx
  HKEY *v10; // rax
  LSTATUS v11; // eax
  signed int v12; // esi
  const struct std::nothrow_t *v13; // rdx
  LSTATUS v14; // eax
  WCHAR **unique_for; // rax
  const struct std::nothrow_t *v16; // rdx
  unsigned int v17; // r8d
  DWORD i; // esi
  LSTATUS v19; // eax
  int v20; // eax
  __int64 v21; // rdx
  _WORD *v22; // rcx
  wil::details *phkResult; // [rsp+20h] [rbp-61h]
  wil::details *phkResulta; // [rsp+20h] [rbp-61h]
  wil::details *phkResultb; // [rsp+20h] [rbp-61h]
  wil::details *phkResultc; // [rsp+20h] [rbp-61h]
  int lpcbMaxSubKeyLen; // [rsp+28h] [rbp-59h]
  const char *lpcbMaxClassLen; // [rsp+30h] [rbp-51h]
  const char *lpcbMaxClassLena; // [rsp+30h] [rbp-51h]
  DWORD cValues; // [rsp+60h] [rbp-21h] BYREF
  DWORD cchValueName; // [rsp+64h] [rbp-1Dh] BYREF
  DWORD Type; // [rsp+68h] [rbp-19h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-11h] BYREF
  void *v35; // [rsp+78h] [rbp-9h] BYREF
  void *v36; // [rsp+80h] [rbp-1h] BYREF
  char *v37; // [rsp+88h] [rbp+7h]
  _WORD v38[32]; // [rsp+90h] [rbp+Fh] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+D8h] [rbp+57h]
  DWORD cbMaxValueLen; // [rsp+E0h] [rbp+5Fh] BYREF
  int v41; // [rsp+E4h] [rbp+63h]
  DWORD cbMaxValueNameLen; // [rsp+E8h] [rbp+67h] BYREF
  int v43; // [rsp+ECh] [rbp+6Bh]
  DWORD cbData; // [rsp+F8h] [rbp+77h] BYREF

  v43 = HIDWORD(a2);
  v41 = HIDWORD(a1);
  v36 = v38;
  v37 = (char *)v38;
  hKey = 0;
  v38[0] = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  cchValueName = 0;
  cbData = 0;
  cValues = 0;
  Type = 0;
  if ( a4 )
  {
    v7 = a5;
    if ( a5 )
    {
      v8 = 0;
      v9 = 0;
      v10 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
      v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 1u, v10);
      v12 = v11;
      if ( v11 )
      {
        if ( v11 > 0 )
          v12 = (unsigned __int16)v11 | 0x80070000;
        if ( v12 >= 0 )
          v12 = -2147467259;
        LODWORD(phkResulta) = v12;
        wil::details::in1diag4::Log_HrMsg(
          retaddr,
          (void *)0x1CE,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
          "CKernelReportDataCollection::WriteRegistryKeyXML",
          phkResulta,
          (int)"RegOpenKeyEx failed",
          lpcbMaxClassLen);
        goto LABEL_36;
      }
      v12 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v7, L"<%s>", a4);
      if ( v12 < 0 )
      {
        LODWORD(phkResulta) = v12;
        wil::details::in1diag4::Log_HrMsg(
          retaddr,
          (void *)0x1D7,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
          "CKernelReportDataCollection::WriteRegistryKeyXML",
          phkResulta,
          (int)"Sprintf failed while trying to print the node name",
          lpcbMaxClassLen);
        goto LABEL_36;
      }
      v14 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
      v12 = v14;
      if ( v14 )
      {
        if ( v14 > 0 )
          v12 = (unsigned __int16)v14 | 0x80070000;
        if ( v12 >= 0 )
          v12 = -2147467259;
        LODWORD(phkResultb) = v12;
        wil::details::in1diag4::Log_HrMsg(
          retaddr,
          (void *)0x1EC,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
          "CKernelReportDataCollection::WriteRegistryKeyXML",
          phkResultb,
          (int)"RegQueryInfoKey failed",
          lpcbMaxClassLena);
        goto LABEL_36;
      }
      unique_for = (WCHAR **)utl::make_unique_for_overwrite<wchar_t [0],0>(&v35, ++cbMaxValueNameLen);
      v8 = *unique_for;
      *unique_for = 0;
      if ( v35 )
        operator delete(v35, v16);
      if ( v8 )
      {
        v9 = (BYTE *)operator new[](cbMaxValueLen, (const struct std::nothrow_t *)&std::nothrow);
        if ( v9 )
        {
          for ( i = 0; i < cValues; ++i )
          {
            *v8 = 0;
            cchValueName = cbMaxValueNameLen;
            cbData = cbMaxValueLen;
            v19 = RegEnumValueW(hKey, i, v8, &cchValueName, 0, &Type, v9, &cbData);
            if ( v19 )
            {
              LODWORD(phkResultc) = v19;
              wil::details::in1diag4::Log_Win32Msg(
                retaddr,
                (void *)0x21B,
                (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
                "CKernelReportDataCollection::WriteRegistryKeyXML",
                phkResultc,
                (unsigned int)"RegEnumValue failed",
                lpcbMaxClassLena);
            }
            else
            {
              v20 = CKernelReportDataCollection::PrintRegKeyXML(&v36, Type, v8, v9, cbData, &v36);
              if ( v20 >= 0 )
              {
                utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                  v7,
                  v36,
                  (v37 - (_BYTE *)v36) >> 1);
              }
              else
              {
                LODWORD(phkResultb) = v20;
                wil::details::in1diag4::Log_HrMsg(
                  retaddr,
                  (void *)0x227,
                  (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
                  "CKernelReportDataCollection::WriteRegistryKeyXML",
                  phkResultb,
                  (int)"PrintRegKeyXML failed",
                  lpcbMaxClassLena);
              }
            }
          }
          v12 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                  &v36,
                  L"\r\n</%s>\r\n",
                  a4);
          if ( v12 >= 0 )
          {
            if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                                    v7,
                                    v36,
                                    (v37 - (_BYTE *)v36) >> 1) )
            {
              v12 = 0;
              goto LABEL_37;
            }
            v12 = -2147024882;
            LODWORD(phkResultb) = -2147024882;
            wil::details::in1diag4::Log_HrMsg(
              retaddr,
              (void *)0x23B,
              (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
              "CKernelReportDataCollection::WriteRegistryKeyXML",
              phkResultb,
              (int)"Failed to append to buffer",
              lpcbMaxClassLena);
          }
          else
          {
            LODWORD(phkResultb) = v12;
            wil::details::in1diag4::Log_HrMsg(
              retaddr,
              (void *)0x233,
              (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
              "CKernelReportDataCollection::WriteRegistryKeyXML",
              phkResultb,
              (int)"Sprintf failed while closing the xml node name",
              lpcbMaxClassLena);
          }
LABEL_36:
          v22 = *(_WORD **)v7;
          *(_QWORD *)(v7 + 8) = *(_QWORD *)v7;
          *v22 = 0;
          if ( !v9 )
          {
LABEL_38:
            if ( v8 )
              operator delete(v8, v13);
            if ( v36 != v38 )
              operator delete(v36, (const struct std::nothrow_t *)&std::nothrow);
            if ( hKey )
              RegCloseKey(hKey);
            return (unsigned int)v12;
          }
LABEL_37:
          operator delete(v9, v13);
          goto LABEL_38;
        }
        v21 = 517;
      }
      else
      {
        v21 = 507;
      }
      v12 = -2147024882;
      LODWORD(phkResultb) = -2147024882;
      wil::details::in1diag4::Log_Hr(
        retaddr,
        (void *)v21,
        v17,
        "CKernelReportDataCollection::WriteRegistryKeyXML",
        phkResultb,
        lpcbMaxSubKeyLen);
      goto LABEL_36;
    }
  }
  LODWORD(phkResult) = -2147024809;
  wil::details::in1diag4::Log_HrMsg(
    retaddr,
    (void *)0x1C1,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
    "CKernelReportDataCollection::WriteRegistryKeyXML",
    phkResult,
    (int)"Invalid params",
    lpcbMaxClassLen);
  if ( v36 != v38 )
    operator delete(v36, (const struct std::nothrow_t *)&std::nothrow);
  return 2147942487LL;
}

```

## disassembly

```asm
0x140046774  mov     qword ptr [rsp-8+cbMaxValueNameLen], rdx
0x140046779  mov     qword ptr [rsp-8+cbMaxValueLen], rcx
0x14004677e  push    rbp
0x14004677f  push    rbx
0x140046780  push    rsi
0x140046781  push    rdi
0x140046782  push    r12
0x140046784  push    r14
0x140046786  push    r15
0x140046788  lea     rbp, [rsp-1Fh]
0x14004678d  sub     rsp, 0A0h
0x140046794  xor     r12d, r12d
0x140046797  lea     rax, [rbp+4Fh+var_40]
0x14004679b  mov     [rbp+4Fh+var_50], rax
0x14004679f  lea     rax, [rbp+4Fh+var_40]
0x1400467a3  mov     [rbp+4Fh+var_48], rax
0x1400467a7  mov     r15, r9
0x1400467aa  mov     [rbp+4Fh+hKey], r12
0x1400467ae  mov     rsi, r8
0x1400467b1  mov     [rbp+4Fh+var_40], r12w
0x1400467b6  mov     [rbp+4Fh+cbMaxValueNameLen], r12d
0x1400467ba  mov     [rbp+4Fh+cbMaxValueLen], r12d
0x1400467be  mov     [rbp+4Fh+cchValueName], r12d
0x1400467c2  mov     [rbp+4Fh+cbData], r12d
0x1400467c6  mov     [rbp+4Fh+cValues], r12d
0x1400467ca  mov     [rbp+4Fh+Type], r12d
0x1400467ce  test    r9, r9
0x1400467d1  jz      loc_140046B40
0x1400467d7  mov     r14, [rbp+4Fh+arg_20]
0x1400467db  test    r14, r14
0x1400467de  jz      loc_140046B40
0x1400467e4  lea     rcx, [rbp+4Fh+hKey]
0x1400467e8  mov     edi, r12d
0x1400467eb  mov     ebx, r12d
0x1400467ee  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1400467f3  lea     r9d, [r12+1]; samDesired
0x1400467f8  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1400467fd  xor     r8d, r8d; ulOptions
0x140046800  mov     rdx, rsi; lpSubKey
0x140046803  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14004680a  call    cs:__imp_RegOpenKeyExW
0x140046811  nop     dword ptr [rax+rax+00h]
0x140046816  mov     esi, eax
0x140046818  test    eax, eax
0x14004681a  jz      short loc_14004684B
0x14004681c  jle     short loc_140046827
0x14004681e  movzx   esi, ax
0x140046821  or      esi, 80070000h
0x140046827  mov     eax, 80004005h
0x14004682c  test    esi, esi
0x14004682e  mov     edx, 1CEh
0x140046833  cmovns  esi, eax
0x140046836  lea     rax, aRegopenkeyexFa_0; "RegOpenKeyEx failed"
0x14004683d  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax
0x140046842  mov     dword ptr [rsp+0D0h+phkResult], esi
0x140046846  jmp     loc_140046AA4
0x14004684b  mov     r8, r15
0x14004684e  lea     rdx, aS_0; "<%s>"
0x140046855  mov     rcx, r14
0x140046858  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x14004685d  mov     esi, eax
0x14004685f  test    eax, eax
0x140046861  jns     short loc_14004687D
0x140046863  lea     rax, aSprintfFailedW_0; "Sprintf failed while trying to print th"...
0x14004686a  mov     edx, 1D7h
0x14004686f  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax
0x140046874  mov     dword ptr [rsp+0D0h+phkResult], esi
0x140046878  jmp     loc_140046AA4
0x14004687d  mov     rcx, [rbp+4Fh+hKey]; hKey
0x140046881  lea     rax, [rbp+4Fh+cbMaxValueLen]
0x140046885  mov     [rsp+0D0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x14004688a  xor     r9d, r9d; lpReserved
0x14004688d  mov     [rsp+0D0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x140046892  xor     r8d, r8d; lpcchClass
0x140046895  mov     [rsp+0D0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x14004689a  xor     edx, edx; lpClass
0x14004689c  lea     rax, [rbp+4Fh+cbMaxValueNameLen]
0x1400468a0  mov     [rsp+0D0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1400468a5  lea     rax, [rbp+4Fh+cValues]
0x1400468a9  mov     [rsp+0D0h+lpcValues], rax; lpcValues
0x1400468ae  mov     [rsp+0D0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1400468b3  mov     [rsp+0D0h+lpcbMaxSubKeyLen], r12; int
0x1400468b8  mov     [rsp+0D0h+phkResult], r12; lpcSubKeys
0x1400468bd  call    cs:__imp_RegQueryInfoKeyW
0x1400468c4  nop     dword ptr [rax+rax+00h]
0x1400468c9  mov     esi, eax
0x1400468cb  test    eax, eax
0x1400468cd  jz      short loc_1400468FE
0x1400468cf  jle     short loc_1400468DA
0x1400468d1  movzx   esi, ax
0x1400468d4  or      esi, 80070000h
0x1400468da  mov     eax, 80004005h
0x1400468df  test    esi, esi
0x1400468e1  mov     edx, 1ECh
0x1400468e6  cmovns  esi, eax
0x1400468e9  lea     rax, aRegqueryinfoke_1; "RegQueryInfoKey failed"
0x1400468f0  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax
0x1400468f5  mov     dword ptr [rsp+0D0h+phkResult], esi
0x1400468f9  jmp     loc_140046AA4
0x1400468fe  mov     eax, [rbp+4Fh+cbMaxValueNameLen]
0x140046901  lea     rcx, [rbp+4Fh+var_58]
0x140046905  inc     eax
0x140046907  mov     edx, eax
0x140046909  mov     [rbp+4Fh+cbMaxValueNameLen], eax
0x14004690c  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x140046911  mov     rdi, [rax]
0x140046914  mov     [rax], r12
0x140046917  mov     rcx, [rbp+4Fh+var_58]; void *
0x14004691b  test    rcx, rcx
0x14004691e  jz      short loc_140046925
0x140046920  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140046925  test    rdi, rdi
0x140046928  jz      loc_140046AC9
0x14004692e  mov     ecx, [rbp+4Fh+cbMaxValueLen]; unsigned __int64
0x140046931  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140046938  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14004693d  mov     rbx, rax
0x140046940  test    rax, rax
0x140046943  jz      loc_140046AC2
0x140046949  mov     esi, r12d
0x14004694c  cmp     [rbp+4Fh+cValues], r12d
0x140046950  jbe     loc_140046A3E
0x140046956  mov     [rdi], r12w
0x14004695a  lea     r9, [rbp+4Fh+cchValueName]; lpcchValueName
0x14004695e  mov     eax, [rbp+4Fh+cbMaxValueNameLen]
0x140046961  mov     r8, rdi; lpValueName
0x140046964  mov     rcx, [rbp+4Fh+hKey]; hKey
0x140046968  mov     edx, esi; dwIndex
0x14004696a  mov     [rbp+4Fh+cchValueName], eax
0x14004696d  mov     eax, [rbp+4Fh+cbMaxValueLen]
0x140046970  mov     [rbp+4Fh+cbData], eax
0x140046973  lea     rax, [rbp+4Fh+cbData]
0x140046977  mov     [rsp+0D0h+lpcValues], rax; lpcbData
0x14004697c  lea     rax, [rbp+4Fh+Type]
0x140046980  mov     [rsp+0D0h+lpcbMaxClassLen], rbx; char *
0x140046985  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; lpType
0x14004698a  mov     [rsp+0D0h+phkResult], r12; lpReserved
0x14004698f  call    cs:__imp_RegEnumValueW
0x140046996  nop     dword ptr [rax+rax+00h]
0x14004699b  test    eax, eax
0x14004699d  jz      short loc_1400469CD
0x14004699f  mov     rcx, [rbp+57h]; this
0x1400469a3  lea     rdx, aRegenumvalueFa; "RegEnumValue failed"
0x1400469aa  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rdx; unsigned int
0x1400469af  lea     r9, aCkernelreportd_3; "CKernelReportDataCollection::WriteRegis"...
0x1400469b6  mov     edx, 21Bh; void *
0x1400469bb  mov     dword ptr [rsp+0D0h+phkResult], eax; wil::details *
0x1400469bf  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x1400469c6  call    ?Log_Win32Msg@in1diag4@details@wil@@YAKPEAXIPEBD1K1ZZ; wil::details::in1diag4::Log_Win32Msg(void *,uint,char const *,char const *,ulong,char const *,...)
0x1400469cb  jmp     short loc_140046A33
0x1400469cd  mov     eax, [rbp+4Fh+cbData]
0x1400469d0  lea     rcx, [rbp+4Fh+var_50]
0x1400469d4  mov     edx, [rbp+4Fh+Type]
0x1400469d7  mov     r9, rbx
0x1400469da  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rcx
0x1400469df  mov     r8, rdi
0x1400469e2  mov     dword ptr [rsp+0D0h+phkResult], eax
0x1400469e6  call    ?PrintRegKeyXML@CKernelReportDataCollection@@AEAAJKPEB_WPEAEKPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CKernelReportDataCollection::PrintRegKeyXML(ulong,wchar_t const *,uchar *,ulong,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1400469eb  test    eax, eax
0x1400469ed  jns     short loc_140046A1D
0x1400469ef  mov     rcx, [rbp+57h]; this
0x1400469f3  lea     rdx, aPrintregkeyxml; "PrintRegKeyXML failed"
0x1400469fa  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rdx; int
0x1400469ff  lea     r9, aCkernelreportd_3; "CKernelReportDataCollection::WriteRegis"...
0x140046a06  mov     edx, 227h; void *
0x140046a0b  mov     dword ptr [rsp+0D0h+phkResult], eax; wil::details *
0x140046a0f  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x140046a16  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140046a1b  jmp     short loc_140046A33
0x140046a1d  mov     r8, [rbp+4Fh+var_48]
0x140046a21  mov     rcx, r14
0x140046a24  mov     rdx, [rbp+4Fh+var_50]
0x140046a28  sub     r8, rdx
0x140046a2b  sar     r8, 1
0x140046a2e  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x140046a33  inc     esi
0x140046a35  cmp     esi, [rbp+4Fh+cValues]
0x140046a38  jb      loc_140046956
0x140046a3e  mov     r8, r15
0x140046a41  lea     rdx, aS_3; "\r\n</%s>\r\n"
0x140046a48  lea     rcx, [rbp+4Fh+var_50]
0x140046a4c  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x140046a51  mov     esi, eax
0x140046a53  test    eax, eax
0x140046a55  jns     short loc_140046A6E
0x140046a57  lea     rax, aSprintfFailedW; "Sprintf failed while closing the xml no"...
0x140046a5e  mov     edx, 233h
0x140046a63  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax
0x140046a68  mov     dword ptr [rsp+0D0h+phkResult], esi
0x140046a6c  jmp     short loc_140046AA4
0x140046a6e  mov     r8, [rbp+4Fh+var_48]
0x140046a72  mov     rcx, r14
0x140046a75  mov     rdx, [rbp+4Fh+var_50]
0x140046a79  sub     r8, rdx
0x140046a7c  sar     r8, 1
0x140046a7f  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x140046a84  test    al, al
0x140046a86  jnz     short loc_140046ABD
0x140046a88  lea     rdx, aFailedToAppend; "Failed to append to buffer"
0x140046a8f  mov     eax, 8007000Eh
0x140046a94  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rdx; int
0x140046a99  mov     esi, eax
0x140046a9b  mov     dword ptr [rsp+0D0h+phkResult], eax; wil::details *
0x140046a9f  mov     edx, 23Bh; void *
0x140046aa4  mov     rcx, [rbp+57h]; this
0x140046aa8  lea     r9, aCkernelreportd_3; "CKernelReportDataCollection::WriteRegis"...
0x140046aaf  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x140046ab6  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140046abb  jmp     short loc_140046AE9
0x140046abd  mov     esi, r12d
0x140046ac0  jmp     short loc_140046AF9
0x140046ac2  mov     edx, 205h
0x140046ac7  jmp     short loc_140046ACE
0x140046ac9  mov     edx, 1FBh; void *
0x140046ace  mov     rcx, [rbp+57h]; this
0x140046ad2  lea     r9, aCkernelreportd_3; "CKernelReportDataCollection::WriteRegis"...
0x140046ad9  mov     eax, 8007000Eh
0x140046ade  mov     esi, eax
0x140046ae0  mov     dword ptr [rsp+0D0h+phkResult], eax; wil::details *
0x140046ae4  call    ?Log_Hr@in1diag4@details@wil@@YAJPEAXIPEBD1J@Z; wil::details::in1diag4::Log_Hr(void *,uint,char const *,char const *,long)
0x140046ae9  mov     rcx, [r14]
0x140046aec  mov     [r14+8], rcx
0x140046af0  mov     [rcx], r12w
0x140046af4  test    rbx, rbx
0x140046af7  jz      short loc_140046B01
0x140046af9  mov     rcx, rbx; void *
0x140046afc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140046b01  test    rdi, rdi
0x140046b04  jz      short loc_140046B0E
0x140046b06  mov     rcx, rdi; void *
0x140046b09  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140046b0e  mov     rcx, [rbp+4Fh+var_50]; void *
0x140046b12  lea     rax, [rbp+4Fh+var_40]
0x140046b16  cmp     rcx, rax
0x140046b19  jz      short loc_140046B27
0x140046b1b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140046b22  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140046b27  mov     rcx, [rbp+4Fh+hKey]; hKey
0x140046b2b  test    rcx, rcx
0x140046b2e  jz      short loc_140046B3C
0x140046b30  call    cs:__imp_RegCloseKey
0x140046b37  nop     dword ptr [rax+rax+00h]
0x140046b3c  mov     eax, esi
0x140046b3e  jmp     short loc_140046BA1
0x140046b40  mov     rcx, [rbp+57h]; this
0x140046b44  lea     rax, aInvalidParams; "Invalid params"
0x140046b4b  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; int
0x140046b50  lea     r9, aCkernelreportd_3; "CKernelReportDataCollection::WriteRegis"...
0x140046b57  mov     ebx, 80070057h
0x140046b5c  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x140046b63  mov     edx, 1C1h; void *
0x140046b68  mov     dword ptr [rsp+0D0h+phkResult], ebx; wil::details *
0x140046b6c  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140046b71  mov     rcx, [rbp+4Fh+var_50]; void *
0x140046b75  lea     rax, [rbp+4Fh+var_40]
0x140046b79  cmp     rcx, rax
0x140046b7c  jz      short loc_140046B8A
0x140046b7e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140046b85  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140046b8a  mov     rcx, [rbp+4Fh+hKey]; hKey
0x140046b8e  test    rcx, rcx
0x140046b91  jz      short loc_140046B9F
0x140046b93  call    cs:__imp_RegCloseKey
0x140046b9a  nop     dword ptr [rax+rax+00h]
0x140046b9f  mov     eax, ebx
0x140046ba1  add     rsp, 0A0h
0x140046ba8  pop     r15
0x140046baa  pop     r14
0x140046bac  pop     r12
0x140046bae  pop     rdi
0x140046baf  pop     rsi
0x140046bb0  pop     rbx
0x140046bb1  pop     rbp
0x140046bb2  retn
```
