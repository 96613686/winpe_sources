# Print::Driver::PrinterExtensionRegistrar::RegisterPrinterExtension(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::shared_ptr<Win32Adapters::TransactionManager::Transaction> const &,Print::Driver::PrinterExtensionAssociationInfo const &)

- ea: `0x180084a20`
- end: `0x180084d4c`
- name: `?RegisterPrinterExtension@PrinterExtensionRegistrar@Driver@Print@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$shared_ptr@VTransaction@TransactionManager@Win32Adapters@@@5@AEBVPrinterExtensionAssociationInfo@23@@Z`
- size: `812`
- prototype: `void __fastcall(__int64, __int64, const IID *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800821dc`
- `0x18008c120`

## callees

- `0x180003400`
- `0x18000fa4c`
- `0x180018f00`
- `0x180018f58`
- `0x180081cc0`
- `0x180081d4c`
- `0x1800820a4`
- `0x180082784`
- `0x180083010`
- `0x1800841f0`
- `0x180084a20`
- `0x180084d54`
- `0x180084e98`

## import_xrefs

- `ole32!StringFromCLSID` at `0x180084aba`
- `ole32!StringFromCLSID` at `0x180084af8`
- `ole32!StringFromCLSID` at `0x180084b35`
- `ole32!StringFromCLSID` at `0x180084b92`
- `ole32!StringFromCLSID` at `0x180084aba`
- `ole32!StringFromCLSID` at `0x180084af8`
- `ole32!StringFromCLSID` at `0x180084b35`
- `ole32!StringFromCLSID` at `0x180084b92`
- `ole32!CoTaskMemFree` at `0x180084ad4`
- `ole32!CoTaskMemFree` at `0x180084b12`
- `ole32!CoTaskMemFree` at `0x180084c4a`
- `ole32!CoTaskMemFree` at `0x180084cb1`
- `ole32!CoTaskMemFree` at `0x180084cd6`
- `ole32!CoTaskMemFree` at `0x180084cfb`
- `ole32!CoTaskMemFree` at `0x180084ad4`
- `ole32!CoTaskMemFree` at `0x180084b12`
- `ole32!CoTaskMemFree` at `0x180084c4a`
- `ole32!CoTaskMemFree` at `0x180084cb1`
- `ole32!CoTaskMemFree` at `0x180084cd6`
- `ole32!CoTaskMemFree` at `0x180084cfb`

## string_xrefs

- `0x180084bd5`: `Error converting CLSIDs to strings`
- `0x180084c85`: `Error converting CLSIDs to strings`
- `0x180084bc7`: `Print::Driver::PrinterExtensionRegistrar::RegisterPrinterExtension`
- `0x180084bdc`: `Print::Driver::PrinterExtensionRegistrar::RegisterPrinterExtension`
- `0x180084c58`: `Print::Driver::PrinterExtensionRegistrar::RegisterPrinterExtension`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall Print::Driver::PrinterExtensionRegistrar::RegisterPrinterExtension(
        __int64 a1,
        __int64 a2,
        const IID *a3)
{
  HRESULT v4; // eax
  int v5; // ebx
  LPOLESTR v6; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v7; // [rsp+40h] [rbp-C8h]
  __int64 v8; // [rsp+48h] [rbp-C0h]
  LPVOID pv; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v10; // [rsp+58h] [rbp-B0h]
  __int64 v11; // [rsp+60h] [rbp-A8h]
  LPOLESTR lpsz; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v13; // [rsp+70h] [rbp-98h]
  __int64 v14; // [rsp+78h] [rbp-90h]
  LPOLESTR v15; // [rsp+80h] [rbp-88h] BYREF
  __int64 v16; // [rsp+88h] [rbp-80h]
  __int64 v17; // [rsp+90h] [rbp-78h]
  __int64 v18; // [rsp+98h] [rbp-70h]
  IID rclsid; // [rsp+A0h] [rbp-68h] BYREF
  HKEY v20[8]; // [rsp+B8h] [rbp-50h] BYREF
  struct _GUID v21; // [rsp+F8h] [rbp-10h] BYREF
  struct _GUID v22; // [rsp+118h] [rbp+10h] BYREF
  struct _GUID v23; // [rsp+128h] [rbp+20h] BYREF
  char *v24; // [rsp+138h] [rbp+30h] BYREF
  IID v25; // [rsp+158h] [rbp+50h]
  GUID v26[4]; // [rsp+178h] [rbp+70h] BYREF
  char *v27; // [rsp+1B8h] [rbp+B0h] BYREF
  struct _GUID v28; // [rsp+1E8h] [rbp+E0h]

  v18 = -2;
  Print::Driver::PrinterExtensionRegistrar::PrinterExtensionRegistrar(v20, a1, a2);
  Print::Driver::PrinterExtensionAssociationInfo::PrinterExtensionAssociationInfo(&v21);
  Print::Driver::PrinterExtensionRegistrar::CreateAssociation(
    v20,
    (const struct Print::Driver::PrinterExtensionAssociationInfo *)a3,
    (struct Print::Driver::PrinterExtensionAssociationInfo *)&v21);
  lpsz = 0;
  pv = 0;
  v10 = 0;
  v11 = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v13 = -1;
  v14 = -1;
  if ( StringFromCLSID(a3 + 2, &lpsz) < 0
    || (v10 = -1, v11 = -1, StringFromCLSID(a3 + 3, (LPOLESTR *)&pv) < 0)
    || (v7 = -1, v8 = -1, v4 = StringFromCLSID(a3, &v6), v5 = 0, v4 < 0) )
  {
    v5 = -2147467259;
  }
  rclsid = 0;
  if ( Print::Driver::PrinterExtensionRegistrar::GetPrinterDriverAssociation(
         (Print::Driver::PrinterExtensionRegistrar *)v20,
         &v22,
         &v23,
         &rclsid) )
  {
    v15 = 0;
    v16 = 0;
    v17 = 0;
    if ( v5 < 0 || (v16 = -1, v17 = -1, StringFromCLSID(&rclsid, &v15) < 0) )
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
        "Print::Driver::PrinterExtensionRegistrar::RegisterPrinterExtension",
        L"Error converting CLSIDs to strings");
    else
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "Print::Driver::PrinterExtensionRegistrar::RegisterPrinterExtension",
        L"Replacing association. printerDriverId=%ws reasonId=%ws currentAssociationId=%ws newAssociationId=%ws",
        lpsz,
        pv,
        v15,
        v6);
    v25 = rclsid;
    Print::Driver::PrinterExtensionRegistrar::SetLinkAssociation((Print::Driver::PrinterExtensionRegistrar *)v20, &v21);
    Print::Driver::PrinterExtensionAssociationInfo::PrinterExtensionAssociationInfo(v26);
    Print::Driver::PrinterExtensionRegistrar::GetAssociation(
      (Print::Driver::PrinterExtensionRegistrar *)v20,
      &rclsid,
      v26);
    v28 = v21;
    Print::Driver::PrinterExtensionRegistrar::SetLinkAssociation((Print::Driver::PrinterExtensionRegistrar *)v20, v26);
    std::wstring::~wstring(&v27);
    if ( v15 )
      CoTaskMemFree(v15);
  }
  else if ( v5 < 0 )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "Print::Driver::PrinterExtensionRegistrar::RegisterPrinterExtension",
      L"Error converting CLSIDs to strings");
  }
  else
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "Print::Driver::PrinterExtensionRegistrar::RegisterPrinterExtension",
      L"New association. printerDriverId=%ws reasonId=%ws newAssociationId=%ws",
      lpsz,
      pv,
      v6);
  }
  Print::Driver::PrinterExtensionRegistrar::SetPrinterDriverAssociation(
    (Print::Driver::PrinterExtensionRegistrar *)v20,
    &v22,
    &v23,
    &v21);
  if ( v6 )
  {
    CoTaskMemFree(v6);
    v6 = 0;
  }
  v7 = 0;
  v8 = 0;
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  v10 = 0;
  v11 = 0;
  if ( lpsz )
  {
    CoTaskMemFree(lpsz);
    lpsz = 0;
  }
  v13 = 0;
  v14 = 0;
  std::wstring::~wstring(&v24);
  Print::Driver::PrinterExtensionRegistrar::~PrinterExtensionRegistrar((Print::Driver::PrinterExtensionRegistrar *)v20);
}

```

## disassembly

```asm
0x180084a20  mov     rax, rsp
0x180084a23  push    rbp
0x180084a24  push    rsi
0x180084a25  push    rdi
0x180084a26  lea     rbp, [rax-118h]
0x180084a2d  sub     rsp, 200h
0x180084a34  mov     [rbp+110h+var_180], 0FFFFFFFFFFFFFFFEh
0x180084a3c  mov     [rax+20h], rbx
0x180084a40  mov     rax, cs:__security_cookie
0x180084a47  xor     rax, rsp
0x180084a4a  mov     [rbp+110h+var_20], rax
0x180084a51  mov     rbx, r8
0x180084a54  mov     r8, rdx
0x180084a57  mov     rdx, rcx
0x180084a5a  lea     rcx, [rbp+110h+var_160]; PHKEY
0x180084a5e  call    ??0PrinterExtensionRegistrar@Driver@Print@@AEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$shared_ptr@VTransaction@TransactionManager@Win32Adapters@@@4@@Z; Print::Driver::PrinterExtensionRegistrar::PrinterExtensionRegistrar(std::wstring const &,std::shared_ptr<Win32Adapters::TransactionManager::Transaction> const &)
0x180084a63  nop
0x180084a64  lea     rcx, [rbp+110h+var_120]; this
0x180084a68  call    ??0PrinterExtensionAssociationInfo@Driver@Print@@QEAA@XZ; Print::Driver::PrinterExtensionAssociationInfo::PrinterExtensionAssociationInfo(void)
0x180084a6d  nop
0x180084a6e  lea     r8, [rbp+110h+var_120]; struct Print::Driver::PrinterExtensionAssociationInfo *
0x180084a72  mov     rdx, rbx; struct Print::Driver::PrinterExtensionAssociationInfo *
0x180084a75  lea     rcx, [rbp+110h+var_160]; this
0x180084a79  call    ?CreateAssociation@PrinterExtensionRegistrar@Driver@Print@@AEAAXAEBVPrinterExtensionAssociationInfo@23@AEAV423@@Z; Print::Driver::PrinterExtensionRegistrar::CreateAssociation(Print::Driver::PrinterExtensionAssociationInfo const &,Print::Driver::PrinterExtensionAssociationInfo &)
0x180084a7e  xor     edi, edi
0x180084a80  mov     [rsp+210h+lpsz], rdi
0x180084a85  mov     [rsp+210h+pv], rdi
0x180084a8a  mov     [rsp+210h+var_1C0], rdi
0x180084a8f  mov     [rsp+210h+var_1B8], rdi
0x180084a94  mov     [rsp+210h+var_1E0], rdi
0x180084a99  mov     [rsp+210h+var_1D8], rdi
0x180084a9e  mov     [rsp+210h+var_1D0], rdi
0x180084aa3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180084aa7  mov     [rsp+210h+var_1A8], rsi
0x180084aac  mov     [rsp+210h+var_1A0], rsi
0x180084ab1  lea     rcx, [rbx+20h]; rclsid
0x180084ab5  lea     rdx, [rsp+210h+lpsz]; lplpsz
0x180084aba  call    cs:__imp_StringFromCLSID
0x180084ac1  nop     dword ptr [rax+rax+00h]
0x180084ac6  test    eax, eax
0x180084ac8  js      short loc_180084B47
0x180084aca  mov     rcx, [rsp+210h+pv]; pv
0x180084acf  test    rcx, rcx
0x180084ad2  jz      short loc_180084AE5
0x180084ad4  call    cs:__imp_CoTaskMemFree
0x180084adb  nop     dword ptr [rax+rax+00h]
0x180084ae0  mov     [rsp+210h+pv], rdi
0x180084ae5  mov     [rsp+210h+var_1C0], rsi
0x180084aea  mov     [rsp+210h+var_1B8], rsi
0x180084aef  lea     rcx, [rbx+30h]; rclsid
0x180084af3  lea     rdx, [rsp+210h+pv]; lplpsz
0x180084af8  call    cs:__imp_StringFromCLSID
0x180084aff  nop     dword ptr [rax+rax+00h]
0x180084b04  test    eax, eax
0x180084b06  js      short loc_180084B47
0x180084b08  mov     rcx, [rsp+210h+var_1E0]; pv
0x180084b0d  test    rcx, rcx
0x180084b10  jz      short loc_180084B23
0x180084b12  call    cs:__imp_CoTaskMemFree
0x180084b19  nop     dword ptr [rax+rax+00h]
0x180084b1e  mov     [rsp+210h+var_1E0], rdi
0x180084b23  mov     [rsp+210h+var_1D8], rsi
0x180084b28  mov     [rsp+210h+var_1D0], rsi
0x180084b2d  lea     rdx, [rsp+210h+var_1E0]; lplpsz
0x180084b32  mov     rcx, rbx; rclsid
0x180084b35  call    cs:__imp_StringFromCLSID
0x180084b3c  nop     dword ptr [rax+rax+00h]
0x180084b41  test    eax, eax
0x180084b43  mov     ebx, edi
0x180084b45  jns     short loc_180084B4C
0x180084b47  mov     ebx, 80004005h
0x180084b4c  xorps   xmm0, xmm0
0x180084b4f  movups  xmmword ptr [rbp+110h+rclsid.Data1], xmm0
0x180084b53  lea     r9, [rbp+110h+rclsid]; struct _GUID *
0x180084b57  lea     r8, [rbp+110h+var_F0]; struct _GUID *
0x180084b5b  lea     rdx, [rbp+110h+var_100]; struct _GUID *
0x180084b5f  lea     rcx, [rbp+110h+var_160]; this
0x180084b63  call    ?GetPrinterDriverAssociation@PrinterExtensionRegistrar@Driver@Print@@AEAA_NAEBU_GUID@@0AEAU4@@Z; Print::Driver::PrinterExtensionRegistrar::GetPrinterDriverAssociation(_GUID const &,_GUID const &,_GUID &)
0x180084b68  test    al, al
0x180084b6a  jz      loc_180084C58
0x180084b70  mov     [rsp+210h+var_198], rdi
0x180084b75  mov     [rbp+110h+var_190], rdi
0x180084b79  mov     [rbp+110h+var_188], rdi
0x180084b7d  test    ebx, ebx
0x180084b7f  js      short loc_180084BD5
0x180084b81  mov     [rbp+110h+var_190], rsi
0x180084b85  mov     [rbp+110h+var_188], rsi
0x180084b89  lea     rdx, [rsp+210h+var_198]; lplpsz
0x180084b8e  lea     rcx, [rbp+110h+rclsid]; rclsid
0x180084b92  call    cs:__imp_StringFromCLSID
0x180084b99  nop     dword ptr [rax+rax+00h]
0x180084b9e  test    eax, eax
0x180084ba0  js      short loc_180084BD5
0x180084ba2  mov     rax, [rsp+210h+var_1E0]
0x180084ba7  mov     [rsp+210h+var_1E8], rax
0x180084bac  mov     rax, [rsp+210h+var_198]
0x180084bb1  mov     [rsp+210h+var_1F0], rax
0x180084bb6  mov     r9, [rsp+210h+pv]
0x180084bbb  mov     r8, [rsp+210h+lpsz]
0x180084bc0  lea     rdx, aReplacingAssoc; "Replacing association. printerDriverId="...
0x180084bc7  lea     rcx, aPrintDriverPri_0; "Print::Driver::PrinterExtensionRegistra"...
0x180084bce  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180084bd3  jmp     short loc_180084BE8
0x180084bd5  lea     rdx, aErrorConvertin; "Error converting CLSIDs to strings"
0x180084bdc  lea     rcx, aPrintDriverPri_0; "Print::Driver::PrinterExtensionRegistra"...
0x180084be3  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180084be8  movups  xmm0, xmmword ptr [rbp+110h+rclsid.Data1]
0x180084bec  movdqu  [rbp+110h+var_C0], xmm0
0x180084bf1  lea     rdx, [rbp+110h+var_120]; struct Print::Driver::PrinterExtensionAssociationInfo *
0x180084bf5  lea     rcx, [rbp+110h+var_160]; this
0x180084bf9  call    ?SetLinkAssociation@PrinterExtensionRegistrar@Driver@Print@@AEAAXAEAVPrinterExtensionAssociationInfo@23@@Z; Print::Driver::PrinterExtensionRegistrar::SetLinkAssociation(Print::Driver::PrinterExtensionAssociationInfo &)
0x180084bfe  lea     rcx, [rbp+110h+var_A0]; this
0x180084c02  call    ??0PrinterExtensionAssociationInfo@Driver@Print@@QEAA@XZ; Print::Driver::PrinterExtensionAssociationInfo::PrinterExtensionAssociationInfo(void)
0x180084c07  nop
0x180084c08  lea     r8, [rbp+110h+var_A0]; struct Print::Driver::PrinterExtensionAssociationInfo *
0x180084c0c  lea     rdx, [rbp+110h+rclsid]; struct _GUID *
0x180084c10  lea     rcx, [rbp+110h+var_160]; this
0x180084c14  call    ?GetAssociation@PrinterExtensionRegistrar@Driver@Print@@AEAAXAEBU_GUID@@AEAVPrinterExtensionAssociationInfo@23@@Z; Print::Driver::PrinterExtensionRegistrar::GetAssociation(_GUID const &,Print::Driver::PrinterExtensionAssociationInfo &)
0x180084c19  movaps  xmm0, xmmword ptr [rbp+110h+var_120.Data1]
0x180084c1d  movdqu  [rbp+110h+var_30], xmm0
0x180084c25  lea     rdx, [rbp+110h+var_A0]; struct Print::Driver::PrinterExtensionAssociationInfo *
0x180084c29  lea     rcx, [rbp+110h+var_160]; this
0x180084c2d  call    ?SetLinkAssociation@PrinterExtensionRegistrar@Driver@Print@@AEAAXAEAVPrinterExtensionAssociationInfo@23@@Z; Print::Driver::PrinterExtensionRegistrar::SetLinkAssociation(Print::Driver::PrinterExtensionAssociationInfo &)
0x180084c32  nop
0x180084c33  lea     rcx, [rbp+110h+var_60]
0x180084c3a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180084c3f  nop
0x180084c40  mov     rcx, [rsp+210h+var_198]; pv
0x180084c45  test    rcx, rcx
0x180084c48  jz      short loc_180084C91
0x180084c4a  call    cs:__imp_CoTaskMemFree
0x180084c51  nop     dword ptr [rax+rax+00h]
0x180084c56  jmp     short loc_180084C91
0x180084c58  lea     rcx, aPrintDriverPri_0; "Print::Driver::PrinterExtensionRegistra"...
0x180084c5f  test    ebx, ebx
0x180084c61  js      short loc_180084C85
0x180084c63  mov     rax, [rsp+210h+var_1E0]
0x180084c68  mov     [rsp+210h+var_1F0], rax
0x180084c6d  mov     r9, [rsp+210h+pv]
0x180084c72  mov     r8, [rsp+210h+lpsz]
0x180084c77  lea     rdx, aNewAssociation; "New association. printerDriverId=%ws re"...
0x180084c7e  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180084c83  jmp     short loc_180084C91
0x180084c85  lea     rdx, aErrorConvertin; "Error converting CLSIDs to strings"
0x180084c8c  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180084c91  lea     r9, [rbp+110h+var_120]; struct _GUID *
0x180084c95  lea     r8, [rbp+110h+var_F0]; struct _GUID *
0x180084c99  lea     rdx, [rbp+110h+var_100]; struct _GUID *
0x180084c9d  lea     rcx, [rbp+110h+var_160]; this
0x180084ca1  call    ?SetPrinterDriverAssociation@PrinterExtensionRegistrar@Driver@Print@@AEAAXAEBU_GUID@@00@Z; Print::Driver::PrinterExtensionRegistrar::SetPrinterDriverAssociation(_GUID const &,_GUID const &,_GUID const &)
0x180084ca6  nop
0x180084ca7  mov     rcx, [rsp+210h+var_1E0]; pv
0x180084cac  test    rcx, rcx
0x180084caf  jz      short loc_180084CC2
0x180084cb1  call    cs:__imp_CoTaskMemFree
0x180084cb8  nop     dword ptr [rax+rax+00h]
0x180084cbd  mov     [rsp+210h+var_1E0], rdi
0x180084cc2  mov     [rsp+210h+var_1D8], rdi
0x180084cc7  mov     [rsp+210h+var_1D0], rdi
0x180084ccc  mov     rcx, [rsp+210h+pv]; pv
0x180084cd1  test    rcx, rcx
0x180084cd4  jz      short loc_180084CE7
0x180084cd6  call    cs:__imp_CoTaskMemFree
0x180084cdd  nop     dword ptr [rax+rax+00h]
0x180084ce2  mov     [rsp+210h+pv], rdi
0x180084ce7  mov     [rsp+210h+var_1C0], rdi
0x180084cec  mov     [rsp+210h+var_1B8], rdi
0x180084cf1  mov     rcx, [rsp+210h+lpsz]; pv
0x180084cf6  test    rcx, rcx
0x180084cf9  jz      short loc_180084D0C
0x180084cfb  call    cs:__imp_CoTaskMemFree
0x180084d02  nop     dword ptr [rax+rax+00h]
0x180084d07  mov     [rsp+210h+lpsz], rdi
0x180084d0c  mov     [rsp+210h+var_1A8], rdi
0x180084d11  mov     [rsp+210h+var_1A0], rdi
0x180084d16  lea     rcx, [rbp+110h+var_E0]
0x180084d1a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180084d1f  nop
0x180084d20  lea     rcx, [rbp+110h+var_160]; this
0x180084d24  call    ??1PrinterExtensionRegistrar@Driver@Print@@QEAA@XZ; Print::Driver::PrinterExtensionRegistrar::~PrinterExtensionRegistrar(void)
0x180084d29  mov     rcx, [rbp+110h+var_20]
0x180084d30  xor     rcx, rsp; StackCookie
0x180084d33  call    __security_check_cookie
0x180084d38  mov     rbx, [rsp+210h+arg_18]
0x180084d40  add     rsp, 200h
0x180084d47  pop     rdi
0x180084d48  pop     rsi
0x180084d49  pop     rbp
0x180084d4a  retn
```
