# CKernelReportDataCollection::WriteRegistryKeyXML(HKEY__ *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x1400437ec`
- end: `0x140043c0d`
- name: `?WriteRegistryKeyXML@CKernelReportDataCollection@@AEAAJPEAUHKEY__@@PEB_W1PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `1057`
- prototype: `__int64 __fastcall(__int64, __int64, const WCHAR *, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x140042250`

## callees

- `0x140002728`
- `0x140004198`
- `0x140005430`
- `0x140005468`
- `0x14000e3c4`
- `0x140013ff0`
- `0x140034d9c`
- `0x14003902c`
- `0x140042c60`
- `0x140042c9c`
- `0x1400437ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1400439fb`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1400439fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14004392f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14004392f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140043b96`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140043bf3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140043b96`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140043bf3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140043882`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140043882`

## string_xrefs

- `0x140043a15`: `CKernelReportDataCollection::WriteRegistryKeyXML`
- `0x140043a65`: `CKernelReportDataCollection::WriteRegistryKeyXML`
- `0x140043b0e`: `CKernelReportDataCollection::WriteRegistryKeyXML`
- `0x140043b38`: `CKernelReportDataCollection::WriteRegistryKeyXML`
- `0x140043bb0`: `CKernelReportDataCollection::WriteRegistryKeyXML`
- `0x1400438a8`: `RegOpenKeyEx failed`
- `0x140043a59`: `PrintRegKeyXML failed`
- `0x140043abd`: `Sprintf failed while closing the xml node name`

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
0x1400437ec  mov     qword ptr [rsp-8+cbMaxValueNameLen], rdx
0x1400437f1  mov     qword ptr [rsp-8+cbMaxValueLen], rcx
0x1400437f6  push    rbp
0x1400437f7  push    rbx
0x1400437f8  push    rsi
0x1400437f9  push    rdi
0x1400437fa  push    r12
0x1400437fc  push    r14
0x1400437fe  push    r15
0x140043800  lea     rbp, [rsp-1Fh]
0x140043805  sub     rsp, 0A0h
0x14004380c  xor     r12d, r12d
0x14004380f  lea     rax, [rbp+4Fh+var_40]
0x140043813  mov     [rbp+4Fh+var_50], rax
0x140043817  lea     rax, [rbp+4Fh+var_40]
0x14004381b  mov     [rbp+4Fh+var_48], rax
0x14004381f  mov     r15, r9
0x140043822  mov     [rbp+4Fh+hKey], r12
0x140043826  mov     rsi, r8
0x140043829  mov     [rbp+4Fh+var_40], r12w
0x14004382e  mov     [rbp+4Fh+cbMaxValueNameLen], r12d
0x140043832  mov     [rbp+4Fh+cbMaxValueLen], r12d
0x140043836  mov     [rbp+4Fh+cchValueName], r12d
0x14004383a  mov     [rbp+4Fh+cbData], r12d
0x14004383e  mov     [rbp+4Fh+cValues], r12d
0x140043842  mov     [rbp+4Fh+Type], r12d
0x140043846  test    r9, r9
0x140043849  jz      loc_140043BA0
0x14004384f  mov     r14, [rbp+4Fh+arg_20]
0x140043853  test    r14, r14
0x140043856  jz      loc_140043BA0
0x14004385c  lea     rcx, [rbp+4Fh+hKey]
0x140043860  mov     edi, r12d
0x140043863  mov     ebx, r12d
0x140043866  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14004386b  lea     r9d, [r12+1]; samDesired
0x140043870  mov     [rsp+0D0h+phkResult], rax; phkResult
0x140043875  xor     r8d, r8d; ulOptions
0x140043878  mov     rdx, rsi; lpSubKey
0x14004387b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140043882  call    cs:__imp_RegOpenKeyExW
0x140043888  mov     esi, eax
0x14004388a  test    eax, eax
0x14004388c  jz      short loc_1400438BD
0x14004388e  jle     short loc_140043899
0x140043890  movzx   esi, ax
0x140043893  or      esi, 80070000h
0x140043899  mov     eax, 80004005h
0x14004389e  test    esi, esi
0x1400438a0  mov     edx, 1CEh
0x1400438a5  cmovns  esi, eax
0x1400438a8  lea     rax, aRegopenkeyexFa_0; "RegOpenKeyEx failed"
0x1400438af  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax
0x1400438b4  mov     dword ptr [rsp+0D0h+phkResult], esi
0x1400438b8  jmp     loc_140043B0A
0x1400438bd  mov     r8, r15
0x1400438c0  lea     rdx, aS_0; "<%s>"
0x1400438c7  mov     rcx, r14
0x1400438ca  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1400438cf  mov     esi, eax
0x1400438d1  test    eax, eax
0x1400438d3  jns     short loc_1400438EF
0x1400438d5  lea     rax, aSprintfFailedW_0; "Sprintf failed while trying to print th"...
0x1400438dc  mov     edx, 1D7h
0x1400438e1  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax
0x1400438e6  mov     dword ptr [rsp+0D0h+phkResult], esi
0x1400438ea  jmp     loc_140043B0A
0x1400438ef  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1400438f3  lea     rax, [rbp+4Fh+cbMaxValueLen]
0x1400438f7  mov     [rsp+0D0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1400438fc  xor     r9d, r9d; lpReserved
0x1400438ff  mov     [rsp+0D0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x140043904  xor     r8d, r8d; lpcchClass
0x140043907  mov     [rsp+0D0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x14004390c  xor     edx, edx; lpClass
0x14004390e  lea     rax, [rbp+4Fh+cbMaxValueNameLen]
0x140043912  mov     [rsp+0D0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x140043917  lea     rax, [rbp+4Fh+cValues]
0x14004391b  mov     [rsp+0D0h+lpcValues], rax; lpcValues
0x140043920  mov     [rsp+0D0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x140043925  mov     [rsp+0D0h+lpcbMaxSubKeyLen], r12; int
0x14004392a  mov     [rsp+0D0h+phkResult], r12; lpcSubKeys
0x14004392f  call    cs:__imp_RegQueryInfoKeyW
0x140043935  mov     esi, eax
0x140043937  test    eax, eax
0x140043939  jz      short loc_14004396A
0x14004393b  jle     short loc_140043946
0x14004393d  movzx   esi, ax
0x140043940  or      esi, 80070000h
0x140043946  mov     eax, 80004005h
0x14004394b  test    esi, esi
0x14004394d  mov     edx, 1ECh
0x140043952  cmovns  esi, eax
0x140043955  lea     rax, aRegqueryinfoke_1; "RegQueryInfoKey failed"
0x14004395c  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax
0x140043961  mov     dword ptr [rsp+0D0h+phkResult], esi
0x140043965  jmp     loc_140043B0A
0x14004396a  mov     eax, [rbp+4Fh+cbMaxValueNameLen]
0x14004396d  lea     rcx, [rbp+4Fh+var_58]
0x140043971  inc     eax
0x140043973  mov     edx, eax
0x140043975  mov     [rbp+4Fh+cbMaxValueNameLen], eax
0x140043978  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x14004397d  mov     rdi, [rax]
0x140043980  mov     [rax], r12
0x140043983  mov     rcx, [rbp+4Fh+var_58]; void *
0x140043987  test    rcx, rcx
0x14004398a  jz      short loc_140043991
0x14004398c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140043991  test    rdi, rdi
0x140043994  jz      loc_140043B2F
0x14004399a  mov     ecx, [rbp+4Fh+cbMaxValueLen]; unsigned __int64
0x14004399d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400439a4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400439a9  mov     rbx, rax
0x1400439ac  test    rax, rax
0x1400439af  jz      loc_140043B28
0x1400439b5  mov     esi, r12d
0x1400439b8  cmp     [rbp+4Fh+cValues], r12d
0x1400439bc  jbe     loc_140043AA4
0x1400439c2  mov     [rdi], r12w
0x1400439c6  lea     r9, [rbp+4Fh+cchValueName]; lpcchValueName
0x1400439ca  mov     eax, [rbp+4Fh+cbMaxValueNameLen]
0x1400439cd  mov     r8, rdi; lpValueName
0x1400439d0  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1400439d4  mov     edx, esi; dwIndex
0x1400439d6  mov     [rbp+4Fh+cchValueName], eax
0x1400439d9  mov     eax, [rbp+4Fh+cbMaxValueLen]
0x1400439dc  mov     [rbp+4Fh+cbData], eax
0x1400439df  lea     rax, [rbp+4Fh+cbData]
0x1400439e3  mov     [rsp+0D0h+lpcValues], rax; lpcbData
0x1400439e8  lea     rax, [rbp+4Fh+Type]
0x1400439ec  mov     [rsp+0D0h+lpcbMaxClassLen], rbx; char *
0x1400439f1  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; lpType
0x1400439f6  mov     [rsp+0D0h+phkResult], r12; lpReserved
0x1400439fb  call    cs:__imp_RegEnumValueW
0x140043a01  test    eax, eax
0x140043a03  jz      short loc_140043A33
0x140043a05  mov     rcx, [rbp+57h]; this
0x140043a09  lea     rdx, aRegenumvalueFa; "RegEnumValue failed"
0x140043a10  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rdx; unsigned int
0x140043a15  lea     r9, aCkernelreportd_3; "CKernelReportDataCollection::WriteRegis"...
0x140043a1c  mov     edx, 21Bh; void *
0x140043a21  mov     dword ptr [rsp+0D0h+phkResult], eax; wil::details *
0x140043a25  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x140043a2c  call    ?Log_Win32Msg@in1diag4@details@wil@@YAKPEAXIPEBD1K1ZZ; wil::details::in1diag4::Log_Win32Msg(void *,uint,char const *,char const *,ulong,char const *,...)
0x140043a31  jmp     short loc_140043A99
0x140043a33  mov     eax, [rbp+4Fh+cbData]
0x140043a36  lea     rcx, [rbp+4Fh+var_50]
0x140043a3a  mov     edx, [rbp+4Fh+Type]
0x140043a3d  mov     r9, rbx
0x140043a40  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rcx
0x140043a45  mov     r8, rdi
0x140043a48  mov     dword ptr [rsp+0D0h+phkResult], eax
0x140043a4c  call    ?PrintRegKeyXML@CKernelReportDataCollection@@AEAAJKPEB_WPEAEKPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CKernelReportDataCollection::PrintRegKeyXML(ulong,wchar_t const *,uchar *,ulong,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x140043a51  test    eax, eax
0x140043a53  jns     short loc_140043A83
0x140043a55  mov     rcx, [rbp+57h]; this
0x140043a59  lea     rdx, aPrintregkeyxml; "PrintRegKeyXML failed"
0x140043a60  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rdx; int
0x140043a65  lea     r9, aCkernelreportd_3; "CKernelReportDataCollection::WriteRegis"...
0x140043a6c  mov     edx, 227h; void *
0x140043a71  mov     dword ptr [rsp+0D0h+phkResult], eax; wil::details *
0x140043a75  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x140043a7c  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140043a81  jmp     short loc_140043A99
0x140043a83  mov     r8, [rbp+4Fh+var_48]
0x140043a87  mov     rcx, r14
0x140043a8a  mov     rdx, [rbp+4Fh+var_50]
0x140043a8e  sub     r8, rdx
0x140043a91  sar     r8, 1
0x140043a94  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x140043a99  inc     esi
0x140043a9b  cmp     esi, [rbp+4Fh+cValues]
0x140043a9e  jb      loc_1400439C2
0x140043aa4  mov     r8, r15
0x140043aa7  lea     rdx, aS_3; "\r\n</%s>\r\n"
0x140043aae  lea     rcx, [rbp+4Fh+var_50]
0x140043ab2  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x140043ab7  mov     esi, eax
0x140043ab9  test    eax, eax
0x140043abb  jns     short loc_140043AD4
0x140043abd  lea     rax, aSprintfFailedW; "Sprintf failed while closing the xml no"...
0x140043ac4  mov     edx, 233h
0x140043ac9  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax
0x140043ace  mov     dword ptr [rsp+0D0h+phkResult], esi
0x140043ad2  jmp     short loc_140043B0A
0x140043ad4  mov     r8, [rbp+4Fh+var_48]
0x140043ad8  mov     rcx, r14
0x140043adb  mov     rdx, [rbp+4Fh+var_50]
0x140043adf  sub     r8, rdx
0x140043ae2  sar     r8, 1
0x140043ae5  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x140043aea  test    al, al
0x140043aec  jnz     short loc_140043B23
0x140043aee  lea     rdx, aFailedToAppend; "Failed to append to buffer"
0x140043af5  mov     eax, 8007000Eh
0x140043afa  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rdx; int
0x140043aff  mov     esi, eax
0x140043b01  mov     dword ptr [rsp+0D0h+phkResult], eax; wil::details *
0x140043b05  mov     edx, 23Bh; void *
0x140043b0a  mov     rcx, [rbp+57h]; this
0x140043b0e  lea     r9, aCkernelreportd_3; "CKernelReportDataCollection::WriteRegis"...
0x140043b15  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x140043b1c  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140043b21  jmp     short loc_140043B4F
0x140043b23  mov     esi, r12d
0x140043b26  jmp     short loc_140043B5F
0x140043b28  mov     edx, 205h
0x140043b2d  jmp     short loc_140043B34
0x140043b2f  mov     edx, 1FBh; void *
0x140043b34  mov     rcx, [rbp+57h]; this
0x140043b38  lea     r9, aCkernelreportd_3; "CKernelReportDataCollection::WriteRegis"...
0x140043b3f  mov     eax, 8007000Eh
0x140043b44  mov     esi, eax
0x140043b46  mov     dword ptr [rsp+0D0h+phkResult], eax; wil::details *
0x140043b4a  call    ?Log_Hr@in1diag4@details@wil@@YAJPEAXIPEBD1J@Z; wil::details::in1diag4::Log_Hr(void *,uint,char const *,char const *,long)
0x140043b4f  mov     rcx, [r14]
0x140043b52  mov     [r14+8], rcx
0x140043b56  mov     [rcx], r12w
0x140043b5a  test    rbx, rbx
0x140043b5d  jz      short loc_140043B67
0x140043b5f  mov     rcx, rbx; void *
0x140043b62  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140043b67  test    rdi, rdi
0x140043b6a  jz      short loc_140043B74
0x140043b6c  mov     rcx, rdi; void *
0x140043b6f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140043b74  mov     rcx, [rbp+4Fh+var_50]; void *
0x140043b78  lea     rax, [rbp+4Fh+var_40]
0x140043b7c  cmp     rcx, rax
0x140043b7f  jz      short loc_140043B8D
0x140043b81  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140043b88  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140043b8d  mov     rcx, [rbp+4Fh+hKey]; hKey
0x140043b91  test    rcx, rcx
0x140043b94  jz      short loc_140043B9C
0x140043b96  call    cs:__imp_RegCloseKey
0x140043b9c  mov     eax, esi
0x140043b9e  jmp     short loc_140043BFB
0x140043ba0  mov     rcx, [rbp+57h]; this
0x140043ba4  lea     rax, aInvalidParams; "Invalid params"
0x140043bab  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; int
0x140043bb0  lea     r9, aCkernelreportd_3; "CKernelReportDataCollection::WriteRegis"...
0x140043bb7  mov     ebx, 80070057h
0x140043bbc  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x140043bc3  mov     edx, 1C1h; void *
0x140043bc8  mov     dword ptr [rsp+0D0h+phkResult], ebx; wil::details *
0x140043bcc  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140043bd1  mov     rcx, [rbp+4Fh+var_50]; void *
0x140043bd5  lea     rax, [rbp+4Fh+var_40]
0x140043bd9  cmp     rcx, rax
0x140043bdc  jz      short loc_140043BEA
0x140043bde  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140043be5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140043bea  mov     rcx, [rbp+4Fh+hKey]; hKey
0x140043bee  test    rcx, rcx
0x140043bf1  jz      short loc_140043BF9
0x140043bf3  call    cs:__imp_RegCloseKey
0x140043bf9  mov     eax, ebx
0x140043bfb  add     rsp, 0A0h
0x140043c02  pop     r15
0x140043c04  pop     r14
0x140043c06  pop     r12
0x140043c08  pop     rdi
0x140043c09  pop     rsi
0x140043c0a  pop     rbx
0x140043c0b  pop     rbp
0x140043c0c  retn
```
