# Print::Driver::PrinterExtensionRegistrar::GetPrinterDriverAssociation(_GUID const &,_GUID const &,_GUID &)

- ea: `0x1800841f0`
- end: `0x18008459b`
- name: `?GetPrinterDriverAssociation@PrinterExtensionRegistrar@Driver@Print@@AEAA_NAEBU_GUID@@0AEAU4@@Z`
- size: `939`
- prototype: `char __fastcall(Print::Driver::PrinterExtensionRegistrar *this, const struct _GUID *, const struct _GUID *, struct _GUID *)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180083284`
- `0x180084a20`
- `0x1800855dc`

## callees

- `0x180003400`
- `0x18000fa4c`
- `0x180018f00`
- `0x180018f58`
- `0x180037a08`
- `0x180037c50`
- `0x180038a44`
- `0x1800841f0`
- `0x1800847f0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180084558`
- `ADVAPI32!RegCloseKey` at `0x180084558`
- `ole32!StringFromCLSID` at `0x1800842c2`
- `ole32!StringFromCLSID` at `0x180084386`
- `ole32!StringFromCLSID` at `0x1800843c2`
- `ole32!StringFromCLSID` at `0x18008442a`
- `ole32!StringFromCLSID` at `0x180084466`
- `ole32!StringFromCLSID` at `0x18008449e`
- `ole32!StringFromCLSID` at `0x1800842c2`
- `ole32!StringFromCLSID` at `0x180084386`
- `ole32!StringFromCLSID` at `0x1800843c2`
- `ole32!StringFromCLSID` at `0x18008442a`
- `ole32!StringFromCLSID` at `0x180084466`
- `ole32!StringFromCLSID` at `0x18008449e`
- `ole32!CoTaskMemFree` at `0x180084360`
- `ole32!CoTaskMemFree` at `0x1800843a3`
- `ole32!CoTaskMemFree` at `0x180084404`
- `ole32!CoTaskMemFree` at `0x180084447`
- `ole32!CoTaskMemFree` at `0x18008447f`
- `ole32!CoTaskMemFree` at `0x1800844f2`
- `ole32!CoTaskMemFree` at `0x180084513`
- `ole32!CoTaskMemFree` at `0x180084535`
- `ole32!CoTaskMemFree` at `0x180084360`
- `ole32!CoTaskMemFree` at `0x1800843a3`
- `ole32!CoTaskMemFree` at `0x180084404`
- `ole32!CoTaskMemFree` at `0x180084447`
- `ole32!CoTaskMemFree` at `0x18008447f`
- `ole32!CoTaskMemFree` at `0x1800844f2`
- `ole32!CoTaskMemFree` at `0x180084513`
- `ole32!CoTaskMemFree` at `0x180084535`

## string_xrefs

- `0x1800842ef`: `Error converting CLSID to string`
- `0x1800844dc`: `Error converting CLSIDs to strings`
- `0x1800842ce`: `Print::Driver::PrinterExtensionRegistrar::GetPrinterDriverAssociation`
- `0x1800843e6`: `Print::Driver::PrinterExtensionRegistrar::GetPrinterDriverAssociation`
- `0x1800844c7`: `Print::Driver::PrinterExtensionRegistrar::GetPrinterDriverAssociation`
- `0x1800844d5`: `Print::Driver::PrinterExtensionRegistrar::GetPrinterDriverAssociation`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
char __fastcall Print::Driver::PrinterExtensionRegistrar::GetPrinterDriverAssociation(
        Print::Driver::PrinterExtensionRegistrar *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        struct _GUID *a4)
{
  __m128i si128; // xmm6
  char v9; // r15
  LPOLESTR lpsz; // [rsp+38h] [rbp-89h] BYREF
  __int64 v12; // [rsp+40h] [rbp-81h]
  __int64 v13; // [rsp+48h] [rbp-79h]
  LPVOID pv; // [rsp+50h] [rbp-71h] BYREF
  __int64 v15; // [rsp+58h] [rbp-69h]
  __int64 v16; // [rsp+60h] [rbp-61h]
  HKEY hKey; // [rsp+68h] [rbp-59h] BYREF
  LPOLESTR v18; // [rsp+70h] [rbp-51h] BYREF
  __int64 v19; // [rsp+78h] [rbp-49h]
  __int64 v20; // [rsp+80h] [rbp-41h]
  __int64 v21; // [rsp+88h] [rbp-39h]
  _OWORD v22[2]; // [rsp+90h] [rbp-31h] BYREF
  WCHAR SubKey[8]; // [rsp+B0h] [rbp-11h] BYREF
  __m128i v24; // [rsp+C0h] [rbp-1h]

  v21 = -2;
  *(_OWORD *)SubKey = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v24 = si128;
  SubKey[0] = 0;
  Print::Driver::PrinterExtensionRegistrar::GetSubkeyPathForPrinterDriverAssociation((__int64)this, a2, (char **)SubKey);
  v9 = 0;
  hKey = 0;
  Win32Adapters::Registry::RegOpenKeyTransactedW(*(HKEY *)this, SubKey, 0x20019u, 0, &hKey, (__int64 *)this + 5);
  lpsz = 0;
  v12 = 0;
  v13 = 0;
  pv = 0;
  v15 = 0;
  v16 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  if ( hKey )
  {
    v22[0] = 0;
    v22[1] = si128;
    LOWORD(v22[0]) = 0;
    Win32Adapters::Guid::StringFromGuid(a3, (__int64)v22);
    Win32Adapters::Registry::RegQueryValueW((__int64)&hKey, (__int64)v22, 0, a4);
    std::wstring::~wstring((char **)v22);
    if ( *(_QWORD *)&GUID_NULL.Data1 == *(_QWORD *)&a4->Data1 && *(_QWORD *)GUID_NULL.Data4 == *(_QWORD *)a4->Data4 )
    {
      v12 = -1;
      v13 = -1;
      if ( StringFromCLSID(a2, &lpsz) >= 0 )
      {
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        v15 = -1;
        v16 = -1;
        if ( StringFromCLSID(a3, (LPOLESTR *)&pv) >= 0 )
        {
          Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
            "Print::Driver::PrinterExtensionRegistrar::GetPrinterDriverAssociation",
            L"Printer driver has no associations for this reason. printerDriverId=%ws reasonId=%ws",
            lpsz,
            pv);
          goto LABEL_21;
        }
      }
    }
    else
    {
      v9 = 1;
      v12 = -1;
      v13 = -1;
      if ( StringFromCLSID(a2, &lpsz) >= 0 )
      {
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        v15 = -1;
        v16 = -1;
        if ( StringFromCLSID(a3, (LPOLESTR *)&pv) >= 0 )
        {
          if ( v18 )
          {
            CoTaskMemFree(v18);
            v18 = 0;
          }
          v19 = -1;
          v20 = -1;
          if ( StringFromCLSID(a4, &v18) >= 0 )
          {
            Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
              "Print::Driver::PrinterExtensionRegistrar::GetPrinterDriverAssociation",
              L"Printer driver association found. printerDriverId=%ws reasonId=%ws associationId=%ws",
              lpsz,
              pv,
              v18);
            goto LABEL_21;
          }
        }
      }
    }
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "Print::Driver::PrinterExtensionRegistrar::GetPrinterDriverAssociation",
      L"Error converting CLSIDs to strings");
  }
  else
  {
    v12 = -1;
    v13 = -1;
    if ( StringFromCLSID(a2, &lpsz) < 0 )
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
        "Print::Driver::PrinterExtensionRegistrar::GetPrinterDriverAssociation",
        L"Error converting CLSID to string");
    else
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "Print::Driver::PrinterExtensionRegistrar::GetPrinterDriverAssociation",
        L"Printer driver has no associations. printerDriverId=%ws",
        lpsz);
  }
LABEL_21:
  if ( v18 )
  {
    CoTaskMemFree(v18);
    v18 = 0;
  }
  v19 = 0;
  v20 = 0;
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  v15 = 0;
  v16 = 0;
  if ( lpsz )
  {
    CoTaskMemFree(lpsz);
    lpsz = 0;
  }
  v12 = 0;
  v13 = 0;
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  std::wstring::~wstring((char **)SubKey);
  return v9;
}

```

## disassembly

```asm
0x1800841f0  mov     rax, rsp
0x1800841f3  push    rbp
0x1800841f4  push    rbx
0x1800841f5  push    rsi
0x1800841f6  push    rdi
0x1800841f7  push    r12
0x1800841f9  push    r14
0x1800841fb  push    r15
0x1800841fd  lea     rbp, [rax-5Fh]
0x180084201  sub     rsp, 0E0h
0x180084208  mov     [rbp+57h+var_90], 0FFFFFFFFFFFFFFFEh
0x180084210  movaps  xmmword ptr [rax-48h], xmm6
0x180084214  mov     rax, cs:__security_cookie
0x18008421b  xor     rax, rsp
0x18008421e  mov     qword ptr [rbp+57h+var_48], rax
0x180084222  mov     rsi, r9
0x180084225  mov     r14, r8
0x180084228  mov     rdi, rdx
0x18008422b  mov     rbx, rcx
0x18008422e  xorps   xmm0, xmm0
0x180084231  movups  xmmword ptr [rbp+57h+SubKey], xmm0
0x180084235  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18008423d  movdqu  [rbp+57h+var_58], xmm6
0x180084242  xor     r12d, r12d
0x180084245  mov     [rbp+57h+SubKey], r12w
0x18008424a  lea     r8, [rbp+57h+SubKey]
0x18008424e  call    ?GetSubkeyPathForPrinterDriverAssociation@PrinterExtensionRegistrar@Driver@Print@@AEAAXAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Print::Driver::PrinterExtensionRegistrar::GetSubkeyPathForPrinterDriverAssociation(_GUID const &,std::wstring &)
0x180084253  mov     r15b, r12b
0x180084256  mov     [rbp+57h+hKey], r12
0x18008425a  lea     rax, [rbx+28h]
0x18008425e  mov     [rsp+110h+var_E8], rax; __int64
0x180084263  lea     rax, [rbp+57h+hKey]
0x180084267  mov     [rsp+110h+var_F0], rax; PHKEY
0x18008426c  xor     r9d, r9d
0x18008426f  mov     r8d, 20019h; samDesired
0x180084275  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x180084279  mov     rcx, [rbx]; hKey
0x18008427c  call    ?RegOpenKeyTransactedW@Registry@Win32Adapters@@YAXPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K_NAEAVRegistryHandleRAII@@AEBV?$shared_ptr@VTransaction@TransactionManager@Win32Adapters@@@5@@Z; Win32Adapters::Registry::RegOpenKeyTransactedW(HKEY__ *,std::wstring const &,ulong,bool,RegistryHandleRAII &,std::shared_ptr<Win32Adapters::TransactionManager::Transaction> const &)
0x180084281  mov     [rsp+110h+lpsz], r12
0x180084286  mov     [rsp+110h+var_D8], r12
0x18008428b  mov     [rbp+57h+var_D0], r12
0x18008428f  mov     [rbp+57h+pv], r12
0x180084293  mov     [rbp+57h+var_C0], r12
0x180084297  mov     [rbp+57h+var_B8], r12
0x18008429b  mov     [rbp+57h+var_A8], r12
0x18008429f  mov     [rbp+57h+var_A0], r12
0x1800842a3  mov     [rbp+57h+var_98], r12
0x1800842a7  cmp     [rbp+57h+hKey], r12
0x1800842ab  jnz     short loc_1800842FB
0x1800842ad  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800842b1  mov     [rsp+110h+var_D8], rbx
0x1800842b6  mov     [rbp+57h+var_D0], rbx
0x1800842ba  lea     rdx, [rsp+110h+lpsz]; lplpsz
0x1800842bf  mov     rcx, rdi; rclsid
0x1800842c2  call    cs:__imp_StringFromCLSID
0x1800842c9  nop     dword ptr [rax+rax+00h]
0x1800842ce  lea     rcx, aPrintDriverPri_10; "Print::Driver::PrinterExtensionRegistra"...
0x1800842d5  test    eax, eax
0x1800842d7  js      short loc_1800842EF
0x1800842d9  mov     r8, [rsp+110h+lpsz]
0x1800842de  lea     rdx, aPrinterDriverH; "Printer driver has no associations. pri"...
0x1800842e5  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800842ea  jmp     loc_1800844E9
0x1800842ef  lea     rdx, aErrorConvertin_0; "Error converting CLSID to string"
0x1800842f6  jmp     loc_1800844E3
0x1800842fb  xorps   xmm0, xmm0
0x1800842fe  movups  [rbp+57h+var_88], xmm0
0x180084302  movdqu  [rbp+57h+var_78], xmm6
0x180084307  mov     word ptr [rbp+57h+var_88], r12w
0x18008430c  lea     rdx, [rbp+57h+var_88]
0x180084310  mov     rcx, r14
0x180084313  call    ?StringFromGuid@Guid@Win32Adapters@@YAXAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Win32Adapters::Guid::StringFromGuid(_GUID const &,std::wstring &)
0x180084318  mov     r9, rsi
0x18008431b  xor     r8d, r8d
0x18008431e  lea     rdx, [rbp+57h+var_88]
0x180084322  lea     rcx, [rbp+57h+hKey]
0x180084326  call    ?RegQueryValueW@Registry@Win32Adapters@@YAXAEAVRegistryHandleRAII@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NAEAU_GUID@@@Z; Win32Adapters::Registry::RegQueryValueW(RegistryHandleRAII &,std::wstring const &,bool,_GUID &)
0x18008432b  nop
0x18008432c  lea     rcx, [rbp+57h+var_88]
0x180084330  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180084335  mov     rax, qword ptr cs:GUID_NULL.Data1
0x18008433c  cmp     rax, [rsi]
0x18008433f  jnz     loc_1800843F7
0x180084345  mov     rax, qword ptr cs:GUID_NULL.Data4
0x18008434c  cmp     rax, [rsi+8]
0x180084350  jnz     loc_1800843F7
0x180084356  mov     rcx, [rsp+110h+lpsz]; pv
0x18008435b  test    rcx, rcx
0x18008435e  jz      short loc_180084371
0x180084360  call    cs:__imp_CoTaskMemFree
0x180084367  nop     dword ptr [rax+rax+00h]
0x18008436c  mov     [rsp+110h+lpsz], r12
0x180084371  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180084375  mov     [rsp+110h+var_D8], rbx
0x18008437a  mov     [rbp+57h+var_D0], rbx
0x18008437e  lea     rdx, [rsp+110h+lpsz]; lplpsz
0x180084383  mov     rcx, rdi; rclsid
0x180084386  call    cs:__imp_StringFromCLSID
0x18008438d  nop     dword ptr [rax+rax+00h]
0x180084392  test    eax, eax
0x180084394  js      loc_1800844D5
0x18008439a  mov     rcx, [rbp+57h+pv]; pv
0x18008439e  test    rcx, rcx
0x1800843a1  jz      short loc_1800843B3
0x1800843a3  call    cs:__imp_CoTaskMemFree
0x1800843aa  nop     dword ptr [rax+rax+00h]
0x1800843af  mov     [rbp+57h+pv], r12
0x1800843b3  mov     [rbp+57h+var_C0], rbx
0x1800843b7  mov     [rbp+57h+var_B8], rbx
0x1800843bb  lea     rdx, [rbp+57h+pv]; lplpsz
0x1800843bf  mov     rcx, r14; rclsid
0x1800843c2  call    cs:__imp_StringFromCLSID
0x1800843c9  nop     dword ptr [rax+rax+00h]
0x1800843ce  test    eax, eax
0x1800843d0  js      loc_1800844D5
0x1800843d6  mov     r9, [rbp+57h+pv]
0x1800843da  mov     r8, [rsp+110h+lpsz]
0x1800843df  lea     rdx, aPrinterDriverH_0; "Printer driver has no associations for "...
0x1800843e6  lea     rcx, aPrintDriverPri_10; "Print::Driver::PrinterExtensionRegistra"...
0x1800843ed  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800843f2  jmp     loc_1800844E9
0x1800843f7  mov     r15b, 1
0x1800843fa  mov     rcx, [rsp+110h+lpsz]; pv
0x1800843ff  test    rcx, rcx
0x180084402  jz      short loc_180084415
0x180084404  call    cs:__imp_CoTaskMemFree
0x18008440b  nop     dword ptr [rax+rax+00h]
0x180084410  mov     [rsp+110h+lpsz], r12
0x180084415  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180084419  mov     [rsp+110h+var_D8], rbx
0x18008441e  mov     [rbp+57h+var_D0], rbx
0x180084422  lea     rdx, [rsp+110h+lpsz]; lplpsz
0x180084427  mov     rcx, rdi; rclsid
0x18008442a  call    cs:__imp_StringFromCLSID
0x180084431  nop     dword ptr [rax+rax+00h]
0x180084436  test    eax, eax
0x180084438  js      loc_1800844D5
0x18008443e  mov     rcx, [rbp+57h+pv]; pv
0x180084442  test    rcx, rcx
0x180084445  jz      short loc_180084457
0x180084447  call    cs:__imp_CoTaskMemFree
0x18008444e  nop     dword ptr [rax+rax+00h]
0x180084453  mov     [rbp+57h+pv], r12
0x180084457  mov     [rbp+57h+var_C0], rbx
0x18008445b  mov     [rbp+57h+var_B8], rbx
0x18008445f  lea     rdx, [rbp+57h+pv]; lplpsz
0x180084463  mov     rcx, r14; rclsid
0x180084466  call    cs:__imp_StringFromCLSID
0x18008446d  nop     dword ptr [rax+rax+00h]
0x180084472  test    eax, eax
0x180084474  js      short loc_1800844D5
0x180084476  mov     rcx, [rbp+57h+var_A8]; pv
0x18008447a  test    rcx, rcx
0x18008447d  jz      short loc_18008448F
0x18008447f  call    cs:__imp_CoTaskMemFree
0x180084486  nop     dword ptr [rax+rax+00h]
0x18008448b  mov     [rbp+57h+var_A8], r12
0x18008448f  mov     [rbp+57h+var_A0], rbx
0x180084493  mov     [rbp+57h+var_98], rbx
0x180084497  lea     rdx, [rbp+57h+var_A8]; lplpsz
0x18008449b  mov     rcx, rsi; rclsid
0x18008449e  call    cs:__imp_StringFromCLSID
0x1800844a5  nop     dword ptr [rax+rax+00h]
0x1800844aa  test    eax, eax
0x1800844ac  js      short loc_1800844D5
0x1800844ae  mov     rax, [rbp+57h+var_A8]
0x1800844b2  mov     [rsp+110h+var_F0], rax
0x1800844b7  mov     r9, [rbp+57h+pv]
0x1800844bb  mov     r8, [rsp+110h+lpsz]
0x1800844c0  lea     rdx, aPrinterDriverA; "Printer driver association found. print"...
0x1800844c7  lea     rcx, aPrintDriverPri_10; "Print::Driver::PrinterExtensionRegistra"...
0x1800844ce  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800844d3  jmp     short loc_1800844E9
0x1800844d5  lea     rcx, aPrintDriverPri_10; "Print::Driver::PrinterExtensionRegistra"...
0x1800844dc  lea     rdx, aErrorConvertin; "Error converting CLSIDs to strings"
0x1800844e3  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800844e8  nop
0x1800844e9  mov     rcx, [rbp+57h+var_A8]; pv
0x1800844ed  test    rcx, rcx
0x1800844f0  jz      short loc_180084502
0x1800844f2  call    cs:__imp_CoTaskMemFree
0x1800844f9  nop     dword ptr [rax+rax+00h]
0x1800844fe  mov     [rbp+57h+var_A8], r12
0x180084502  mov     [rbp+57h+var_A0], r12
0x180084506  mov     [rbp+57h+var_98], r12
0x18008450a  mov     rcx, [rbp+57h+pv]; pv
0x18008450e  test    rcx, rcx
0x180084511  jz      short loc_180084523
0x180084513  call    cs:__imp_CoTaskMemFree
0x18008451a  nop     dword ptr [rax+rax+00h]
0x18008451f  mov     [rbp+57h+pv], r12
0x180084523  mov     [rbp+57h+var_C0], r12
0x180084527  mov     [rbp+57h+var_B8], r12
0x18008452b  mov     rcx, [rsp+110h+lpsz]; pv
0x180084530  test    rcx, rcx
0x180084533  jz      short loc_180084546
0x180084535  call    cs:__imp_CoTaskMemFree
0x18008453c  nop     dword ptr [rax+rax+00h]
0x180084541  mov     [rsp+110h+lpsz], r12
0x180084546  mov     [rsp+110h+var_D8], r12
0x18008454b  mov     [rbp+57h+var_D0], r12
0x18008454f  mov     rcx, [rbp+57h+hKey]; hKey
0x180084553  test    rcx, rcx
0x180084556  jz      short loc_180084568
0x180084558  call    cs:__imp_RegCloseKey
0x18008455f  nop     dword ptr [rax+rax+00h]
0x180084564  mov     [rbp+57h+hKey], r12
0x180084568  lea     rcx, [rbp+57h+SubKey]
0x18008456c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180084571  mov     al, r15b
0x180084574  mov     rcx, qword ptr [rbp+57h+var_48]
0x180084578  xor     rcx, rsp; StackCookie
0x18008457b  call    __security_check_cookie
0x180084580  movaps  xmm6, [rsp+110h+var_48+8]
0x180084588  add     rsp, 0E0h
0x18008458f  pop     r15
0x180084591  pop     r14
0x180084593  pop     r12
0x180084595  pop     rdi
0x180084596  pop     rsi
0x180084597  pop     rbx
0x180084598  pop     rbp
0x180084599  retn
```
