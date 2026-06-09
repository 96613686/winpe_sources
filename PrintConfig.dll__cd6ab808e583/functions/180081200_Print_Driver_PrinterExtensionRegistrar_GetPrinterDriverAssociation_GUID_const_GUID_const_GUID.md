# Print::Driver::PrinterExtensionRegistrar::GetPrinterDriverAssociation(_GUID const &,_GUID const &,_GUID &)

- ea: `0x180081200`
- end: `0x18008154c`
- name: `?GetPrinterDriverAssociation@PrinterExtensionRegistrar@Driver@Print@@AEAA_NAEBU_GUID@@0AEAU4@@Z`
- size: `844`
- prototype: `bool(Print::Driver::PrinterExtensionRegistrar *__hidden this, const struct _GUID *, const struct _GUID *, struct _GUID *)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800802d8`
- `0x1800819cc`
- `0x1800824e0`

## callees

- `0x1800032e0`
- `0x18000f590`
- `0x1800183a0`
- `0x1800183f8`
- `0x18003660c`
- `0x18003683c`
- `0x180037580`
- `0x180081200`
- `0x1800817a0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180081510`
- `ADVAPI32!RegCloseKey` at `0x180081510`
- `ole32!StringFromCLSID` at `0x1800812d2`
- `ole32!StringFromCLSID` at `0x18008138a`
- `ole32!StringFromCLSID` at `0x1800813ba`
- `ole32!StringFromCLSID` at `0x180081416`
- `ole32!StringFromCLSID` at `0x180081442`
- `ole32!StringFromCLSID` at `0x18008146e`
- `ole32!StringFromCLSID` at `0x1800812d2`
- `ole32!StringFromCLSID` at `0x18008138a`
- `ole32!StringFromCLSID` at `0x1800813ba`
- `ole32!StringFromCLSID` at `0x180081416`
- `ole32!StringFromCLSID` at `0x180081442`
- `ole32!StringFromCLSID` at `0x18008146e`
- `ole32!CoTaskMemFree` at `0x18008136a`
- `ole32!CoTaskMemFree` at `0x1800813a1`
- `ole32!CoTaskMemFree` at `0x1800813f6`
- `ole32!CoTaskMemFree` at `0x180081429`
- `ole32!CoTaskMemFree` at `0x180081455`
- `ole32!CoTaskMemFree` at `0x1800814bc`
- `ole32!CoTaskMemFree` at `0x1800814d7`
- `ole32!CoTaskMemFree` at `0x1800814f3`
- `ole32!CoTaskMemFree` at `0x18008136a`
- `ole32!CoTaskMemFree` at `0x1800813a1`
- `ole32!CoTaskMemFree` at `0x1800813f6`
- `ole32!CoTaskMemFree` at `0x180081429`
- `ole32!CoTaskMemFree` at `0x180081455`
- `ole32!CoTaskMemFree` at `0x1800814bc`
- `ole32!CoTaskMemFree` at `0x1800814d7`
- `ole32!CoTaskMemFree` at `0x1800814f3`

## string_xrefs

- `0x1800812f9`: `Error converting CLSID to string`
- `0x1800814a6`: `Error converting CLSIDs to strings`
- `0x1800812d8`: `Print::Driver::PrinterExtensionRegistrar::GetPrinterDriverAssociation`
- `0x1800813d8`: `Print::Driver::PrinterExtensionRegistrar::GetPrinterDriverAssociation`
- `0x180081491`: `Print::Driver::PrinterExtensionRegistrar::GetPrinterDriverAssociation`
- `0x18008149f`: `Print::Driver::PrinterExtensionRegistrar::GetPrinterDriverAssociation`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
char __fastcall Print::Driver::PrinterExtensionRegistrar::GetPrinterDriverAssociation(
        HKEY *this,
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
  Print::Driver::PrinterExtensionRegistrar::GetSubkeyPathForPrinterDriverAssociation(this, a2, SubKey);
  v9 = 0;
  hKey = 0;
  Win32Adapters::Registry::RegOpenKeyTransactedW(*this, SubKey, 0x20019u, &hKey, (__int64)(this + 5));
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
    Win32Adapters::Guid::StringFromGuid(a3, v22);
    Win32Adapters::Registry::RegQueryValueW(&hKey, v22, 0, a4);
    std::wstring::~wstring(v22);
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
  std::wstring::~wstring(SubKey);
  return v9;
}

```

## disassembly

```asm
0x180081200  mov     rax, rsp
0x180081203  push    rbp
0x180081204  push    rbx
0x180081205  push    rsi
0x180081206  push    rdi
0x180081207  push    r12
0x180081209  push    r14
0x18008120b  push    r15
0x18008120d  lea     rbp, [rax-5Fh]
0x180081211  sub     rsp, 0E0h
0x180081218  mov     [rbp+57h+var_90], 0FFFFFFFFFFFFFFFEh
0x180081220  movaps  xmmword ptr [rax-48h], xmm6
0x180081224  mov     rax, cs:__security_cookie
0x18008122b  xor     rax, rsp
0x18008122e  mov     qword ptr [rbp+57h+var_48], rax
0x180081232  mov     rsi, r9
0x180081235  mov     r14, r8
0x180081238  mov     rdi, rdx
0x18008123b  mov     rbx, rcx
0x18008123e  xorps   xmm0, xmm0
0x180081241  movups  xmmword ptr [rbp+57h+SubKey], xmm0
0x180081245  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18008124d  movdqu  [rbp+57h+var_58], xmm6
0x180081252  xor     r12d, r12d
0x180081255  mov     [rbp+57h+SubKey], r12w
0x18008125a  lea     r8, [rbp+57h+SubKey]
0x18008125e  call    ?GetSubkeyPathForPrinterDriverAssociation@PrinterExtensionRegistrar@Driver@Print@@AEAAXAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Print::Driver::PrinterExtensionRegistrar::GetSubkeyPathForPrinterDriverAssociation(_GUID const &,std::wstring &)
0x180081263  mov     r15b, r12b
0x180081266  mov     [rbp+57h+hKey], r12
0x18008126a  lea     rax, [rbx+28h]
0x18008126e  mov     [rsp+110h+var_E8], rax; __int64
0x180081273  lea     rax, [rbp+57h+hKey]
0x180081277  mov     [rsp+110h+var_F0], rax; PHKEY
0x18008127c  xor     r9d, r9d
0x18008127f  mov     r8d, 20019h; samDesired
0x180081285  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x180081289  mov     rcx, [rbx]; hKey
0x18008128c  call    ?RegOpenKeyTransactedW@Registry@Win32Adapters@@YAXPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K_NAEAVRegistryHandleRAII@@AEBV?$shared_ptr@VTransaction@TransactionManager@Win32Adapters@@@5@@Z; Win32Adapters::Registry::RegOpenKeyTransactedW(HKEY__ *,std::wstring const &,ulong,bool,RegistryHandleRAII &,std::shared_ptr<Win32Adapters::TransactionManager::Transaction> const &)
0x180081291  mov     [rsp+110h+lpsz], r12
0x180081296  mov     [rsp+110h+var_D8], r12
0x18008129b  mov     [rbp+57h+var_D0], r12
0x18008129f  mov     [rbp+57h+pv], r12
0x1800812a3  mov     [rbp+57h+var_C0], r12
0x1800812a7  mov     [rbp+57h+var_B8], r12
0x1800812ab  mov     [rbp+57h+var_A8], r12
0x1800812af  mov     [rbp+57h+var_A0], r12
0x1800812b3  mov     [rbp+57h+var_98], r12
0x1800812b7  cmp     [rbp+57h+hKey], r12
0x1800812bb  jnz     short loc_180081305
0x1800812bd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800812c1  mov     [rsp+110h+var_D8], rbx
0x1800812c6  mov     [rbp+57h+var_D0], rbx
0x1800812ca  lea     rdx, [rsp+110h+lpsz]; lplpsz
0x1800812cf  mov     rcx, rdi; rclsid
0x1800812d2  call    cs:__imp_StringFromCLSID
0x1800812d8  lea     rcx, aPrintDriverPri_10; "Print::Driver::PrinterExtensionRegistra"...
0x1800812df  test    eax, eax
0x1800812e1  js      short loc_1800812F9
0x1800812e3  mov     r8, [rsp+110h+lpsz]
0x1800812e8  lea     rdx, aPrinterDriverH; "Printer driver has no associations. pri"...
0x1800812ef  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800812f4  jmp     loc_1800814B3
0x1800812f9  lea     rdx, aErrorConvertin_0; "Error converting CLSID to string"
0x180081300  jmp     loc_1800814AD
0x180081305  xorps   xmm0, xmm0
0x180081308  movups  [rbp+57h+var_88], xmm0
0x18008130c  movdqu  [rbp+57h+var_78], xmm6
0x180081311  mov     word ptr [rbp+57h+var_88], r12w
0x180081316  lea     rdx, [rbp+57h+var_88]
0x18008131a  mov     rcx, r14
0x18008131d  call    ?StringFromGuid@Guid@Win32Adapters@@YAXAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Win32Adapters::Guid::StringFromGuid(_GUID const &,std::wstring &)
0x180081322  mov     r9, rsi
0x180081325  xor     r8d, r8d
0x180081328  lea     rdx, [rbp+57h+var_88]
0x18008132c  lea     rcx, [rbp+57h+hKey]
0x180081330  call    ?RegQueryValueW@Registry@Win32Adapters@@YAXAEAVRegistryHandleRAII@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NAEAU_GUID@@@Z; Win32Adapters::Registry::RegQueryValueW(RegistryHandleRAII &,std::wstring const &,bool,_GUID &)
0x180081335  nop
0x180081336  lea     rcx, [rbp+57h+var_88]
0x18008133a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008133f  mov     rax, qword ptr cs:GUID_NULL.Data1
0x180081346  cmp     rax, [rsi]
0x180081349  jnz     loc_1800813E9
0x18008134f  mov     rax, qword ptr cs:GUID_NULL.Data4
0x180081356  cmp     rax, [rsi+8]
0x18008135a  jnz     loc_1800813E9
0x180081360  mov     rcx, [rsp+110h+lpsz]; pv
0x180081365  test    rcx, rcx
0x180081368  jz      short loc_180081375
0x18008136a  call    cs:__imp_CoTaskMemFree
0x180081370  mov     [rsp+110h+lpsz], r12
0x180081375  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180081379  mov     [rsp+110h+var_D8], rbx
0x18008137e  mov     [rbp+57h+var_D0], rbx
0x180081382  lea     rdx, [rsp+110h+lpsz]; lplpsz
0x180081387  mov     rcx, rdi; rclsid
0x18008138a  call    cs:__imp_StringFromCLSID
0x180081390  test    eax, eax
0x180081392  js      loc_18008149F
0x180081398  mov     rcx, [rbp+57h+pv]; pv
0x18008139c  test    rcx, rcx
0x18008139f  jz      short loc_1800813AB
0x1800813a1  call    cs:__imp_CoTaskMemFree
0x1800813a7  mov     [rbp+57h+pv], r12
0x1800813ab  mov     [rbp+57h+var_C0], rbx
0x1800813af  mov     [rbp+57h+var_B8], rbx
0x1800813b3  lea     rdx, [rbp+57h+pv]; lplpsz
0x1800813b7  mov     rcx, r14; rclsid
0x1800813ba  call    cs:__imp_StringFromCLSID
0x1800813c0  test    eax, eax
0x1800813c2  js      loc_18008149F
0x1800813c8  mov     r9, [rbp+57h+pv]
0x1800813cc  mov     r8, [rsp+110h+lpsz]
0x1800813d1  lea     rdx, aPrinterDriverH_0; "Printer driver has no associations for "...
0x1800813d8  lea     rcx, aPrintDriverPri_10; "Print::Driver::PrinterExtensionRegistra"...
0x1800813df  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800813e4  jmp     loc_1800814B3
0x1800813e9  mov     r15b, 1
0x1800813ec  mov     rcx, [rsp+110h+lpsz]; pv
0x1800813f1  test    rcx, rcx
0x1800813f4  jz      short loc_180081401
0x1800813f6  call    cs:__imp_CoTaskMemFree
0x1800813fc  mov     [rsp+110h+lpsz], r12
0x180081401  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180081405  mov     [rsp+110h+var_D8], rbx
0x18008140a  mov     [rbp+57h+var_D0], rbx
0x18008140e  lea     rdx, [rsp+110h+lpsz]; lplpsz
0x180081413  mov     rcx, rdi; rclsid
0x180081416  call    cs:__imp_StringFromCLSID
0x18008141c  test    eax, eax
0x18008141e  js      short loc_18008149F
0x180081420  mov     rcx, [rbp+57h+pv]; pv
0x180081424  test    rcx, rcx
0x180081427  jz      short loc_180081433
0x180081429  call    cs:__imp_CoTaskMemFree
0x18008142f  mov     [rbp+57h+pv], r12
0x180081433  mov     [rbp+57h+var_C0], rbx
0x180081437  mov     [rbp+57h+var_B8], rbx
0x18008143b  lea     rdx, [rbp+57h+pv]; lplpsz
0x18008143f  mov     rcx, r14; rclsid
0x180081442  call    cs:__imp_StringFromCLSID
0x180081448  test    eax, eax
0x18008144a  js      short loc_18008149F
0x18008144c  mov     rcx, [rbp+57h+var_A8]; pv
0x180081450  test    rcx, rcx
0x180081453  jz      short loc_18008145F
0x180081455  call    cs:__imp_CoTaskMemFree
0x18008145b  mov     [rbp+57h+var_A8], r12
0x18008145f  mov     [rbp+57h+var_A0], rbx
0x180081463  mov     [rbp+57h+var_98], rbx
0x180081467  lea     rdx, [rbp+57h+var_A8]; lplpsz
0x18008146b  mov     rcx, rsi; rclsid
0x18008146e  call    cs:__imp_StringFromCLSID
0x180081474  test    eax, eax
0x180081476  js      short loc_18008149F
0x180081478  mov     rax, [rbp+57h+var_A8]
0x18008147c  mov     [rsp+110h+var_F0], rax
0x180081481  mov     r9, [rbp+57h+pv]
0x180081485  mov     r8, [rsp+110h+lpsz]
0x18008148a  lea     rdx, aPrinterDriverA; "Printer driver association found. print"...
0x180081491  lea     rcx, aPrintDriverPri_10; "Print::Driver::PrinterExtensionRegistra"...
0x180081498  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18008149d  jmp     short loc_1800814B3
0x18008149f  lea     rcx, aPrintDriverPri_10; "Print::Driver::PrinterExtensionRegistra"...
0x1800814a6  lea     rdx, aErrorConvertin; "Error converting CLSIDs to strings"
0x1800814ad  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800814b2  nop
0x1800814b3  mov     rcx, [rbp+57h+var_A8]; pv
0x1800814b7  test    rcx, rcx
0x1800814ba  jz      short loc_1800814C6
0x1800814bc  call    cs:__imp_CoTaskMemFree
0x1800814c2  mov     [rbp+57h+var_A8], r12
0x1800814c6  mov     [rbp+57h+var_A0], r12
0x1800814ca  mov     [rbp+57h+var_98], r12
0x1800814ce  mov     rcx, [rbp+57h+pv]; pv
0x1800814d2  test    rcx, rcx
0x1800814d5  jz      short loc_1800814E1
0x1800814d7  call    cs:__imp_CoTaskMemFree
0x1800814dd  mov     [rbp+57h+pv], r12
0x1800814e1  mov     [rbp+57h+var_C0], r12
0x1800814e5  mov     [rbp+57h+var_B8], r12
0x1800814e9  mov     rcx, [rsp+110h+lpsz]; pv
0x1800814ee  test    rcx, rcx
0x1800814f1  jz      short loc_1800814FE
0x1800814f3  call    cs:__imp_CoTaskMemFree
0x1800814f9  mov     [rsp+110h+lpsz], r12
0x1800814fe  mov     [rsp+110h+var_D8], r12
0x180081503  mov     [rbp+57h+var_D0], r12
0x180081507  mov     rcx, [rbp+57h+hKey]; hKey
0x18008150b  test    rcx, rcx
0x18008150e  jz      short loc_18008151A
0x180081510  call    cs:__imp_RegCloseKey
0x180081516  mov     [rbp+57h+hKey], r12
0x18008151a  lea     rcx, [rbp+57h+SubKey]
0x18008151e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180081523  mov     al, r15b
0x180081526  mov     rcx, qword ptr [rbp+57h+var_48]
0x18008152a  xor     rcx, rsp; StackCookie
0x18008152d  call    __security_check_cookie
0x180081532  movaps  xmm6, [rsp+110h+var_48+8]
0x18008153a  add     rsp, 0E0h
0x180081541  pop     r15
0x180081543  pop     r14
0x180081545  pop     r12
0x180081547  pop     rdi
0x180081548  pop     rsi
0x180081549  pop     rbx
0x18008154a  pop     rbp
0x18008154b  retn
```
