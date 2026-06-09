# Print::Driver::PrinterExtensionRegistrar::RegisterPrinterExtension(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::shared_ptr<Win32Adapters::TransactionManager::Transaction> const &,Print::Driver::PrinterExtensionAssociationInfo const &)

- ea: `0x1800819cc`
- end: `0x180081cbb`
- name: `?RegisterPrinterExtension@PrinterExtensionRegistrar@Driver@Print@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$shared_ptr@VTransaction@TransactionManager@Win32Adapters@@@5@AEBVPrinterExtensionAssociationInfo@23@@Z`
- size: `751`
- prototype: `void __fastcall(__int64, __int64, const IID *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18007f2a8`
- `0x180088d30`

## callees

- `0x1800032e0`
- `0x18000f590`
- `0x1800183a0`
- `0x1800183f8`
- `0x18007edc4`
- `0x18007ee4c`
- `0x18007f194`
- `0x18007f814`
- `0x18008006c`
- `0x180081200`
- `0x1800819cc`
- `0x180081cc4`
- `0x180081e00`

## import_xrefs

- `ole32!StringFromCLSID` at `0x180081a66`
- `ole32!StringFromCLSID` at `0x180081a98`
- `ole32!StringFromCLSID` at `0x180081ac9`
- `ole32!StringFromCLSID` at `0x180081b20`
- `ole32!StringFromCLSID` at `0x180081a66`
- `ole32!StringFromCLSID` at `0x180081a98`
- `ole32!StringFromCLSID` at `0x180081ac9`
- `ole32!StringFromCLSID` at `0x180081b20`
- `ole32!CoTaskMemFree` at `0x180081a7a`
- `ole32!CoTaskMemFree` at `0x180081aac`
- `ole32!CoTaskMemFree` at `0x180081bd2`
- `ole32!CoTaskMemFree` at `0x180081c33`
- `ole32!CoTaskMemFree` at `0x180081c52`
- `ole32!CoTaskMemFree` at `0x180081c71`
- `ole32!CoTaskMemFree` at `0x180081a7a`
- `ole32!CoTaskMemFree` at `0x180081aac`
- `ole32!CoTaskMemFree` at `0x180081bd2`
- `ole32!CoTaskMemFree` at `0x180081c33`
- `ole32!CoTaskMemFree` at `0x180081c52`
- `ole32!CoTaskMemFree` at `0x180081c71`

## string_xrefs

- `0x180081b5d`: `Error converting CLSIDs to strings`
- `0x180081c07`: `Error converting CLSIDs to strings`
- `0x180081b4f`: `Print::Driver::PrinterExtensionRegistrar::RegisterPrinterExtension`
- `0x180081b64`: `Print::Driver::PrinterExtensionRegistrar::RegisterPrinterExtension`
- `0x180081bda`: `Print::Driver::PrinterExtensionRegistrar::RegisterPrinterExtension`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  _BYTE v24[32]; // [rsp+138h] [rbp+30h] BYREF
  IID v25; // [rsp+158h] [rbp+50h]
  _BYTE v26[64]; // [rsp+178h] [rbp+70h] BYREF
  _BYTE v27[48]; // [rsp+1B8h] [rbp+B0h] BYREF
  struct _GUID v28; // [rsp+1E8h] [rbp+E0h]

  v18 = -2;
  Print::Driver::PrinterExtensionRegistrar::PrinterExtensionRegistrar(v20);
  Print::Driver::PrinterExtensionAssociationInfo::PrinterExtensionAssociationInfo((Print::Driver::PrinterExtensionAssociationInfo *)&v21);
  Print::Driver::PrinterExtensionRegistrar::CreateAssociation(
    (Print::Driver::PrinterExtensionRegistrar *)v20,
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
    Print::Driver::PrinterExtensionRegistrar::SetLinkAssociation(
      (Print::Driver::PrinterExtensionRegistrar *)v20,
      (struct Print::Driver::PrinterExtensionAssociationInfo *)&v21);
    Print::Driver::PrinterExtensionAssociationInfo::PrinterExtensionAssociationInfo((Print::Driver::PrinterExtensionAssociationInfo *)v26);
    Print::Driver::PrinterExtensionRegistrar::GetAssociation(
      (Print::Driver::PrinterExtensionRegistrar *)v20,
      &rclsid,
      (struct Print::Driver::PrinterExtensionAssociationInfo *)v26);
    v28 = v21;
    Print::Driver::PrinterExtensionRegistrar::SetLinkAssociation(
      (Print::Driver::PrinterExtensionRegistrar *)v20,
      (struct Print::Driver::PrinterExtensionAssociationInfo *)v26);
    std::wstring::~wstring(v27);
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
  Print::Driver::PrinterExtensionRegistrar::SetPrinterDriverAssociation(v20, &v22, &v23, &v21);
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
  std::wstring::~wstring(v24);
  Print::Driver::PrinterExtensionRegistrar::~PrinterExtensionRegistrar((Print::Driver::PrinterExtensionRegistrar *)v20);
}

```

## disassembly

```asm
0x1800819cc  mov     rax, rsp
0x1800819cf  push    rbp
0x1800819d0  push    rsi
0x1800819d1  push    rdi
0x1800819d2  lea     rbp, [rax-118h]
0x1800819d9  sub     rsp, 200h
0x1800819e0  mov     [rbp+110h+var_180], 0FFFFFFFFFFFFFFFEh
0x1800819e8  mov     [rax+20h], rbx
0x1800819ec  mov     rax, cs:__security_cookie
0x1800819f3  xor     rax, rsp
0x1800819f6  mov     [rbp+110h+var_20], rax
0x1800819fd  mov     rbx, r8
0x180081a00  mov     r8, rdx
0x180081a03  mov     rdx, rcx
0x180081a06  lea     rcx, [rbp+110h+var_160]; PHKEY
0x180081a0a  call    ??0PrinterExtensionRegistrar@Driver@Print@@AEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$shared_ptr@VTransaction@TransactionManager@Win32Adapters@@@4@@Z; Print::Driver::PrinterExtensionRegistrar::PrinterExtensionRegistrar(std::wstring const &,std::shared_ptr<Win32Adapters::TransactionManager::Transaction> const &)
0x180081a0f  nop
0x180081a10  lea     rcx, [rbp+110h+var_120]; this
0x180081a14  call    ??0PrinterExtensionAssociationInfo@Driver@Print@@QEAA@XZ; Print::Driver::PrinterExtensionAssociationInfo::PrinterExtensionAssociationInfo(void)
0x180081a19  nop
0x180081a1a  lea     r8, [rbp+110h+var_120]; struct Print::Driver::PrinterExtensionAssociationInfo *
0x180081a1e  mov     rdx, rbx; struct Print::Driver::PrinterExtensionAssociationInfo *
0x180081a21  lea     rcx, [rbp+110h+var_160]; this
0x180081a25  call    ?CreateAssociation@PrinterExtensionRegistrar@Driver@Print@@AEAAXAEBVPrinterExtensionAssociationInfo@23@AEAV423@@Z; Print::Driver::PrinterExtensionRegistrar::CreateAssociation(Print::Driver::PrinterExtensionAssociationInfo const &,Print::Driver::PrinterExtensionAssociationInfo &)
0x180081a2a  xor     edi, edi
0x180081a2c  mov     [rsp+210h+lpsz], rdi
0x180081a31  mov     [rsp+210h+pv], rdi
0x180081a36  mov     [rsp+210h+var_1C0], rdi
0x180081a3b  mov     [rsp+210h+var_1B8], rdi
0x180081a40  mov     [rsp+210h+var_1E0], rdi
0x180081a45  mov     [rsp+210h+var_1D8], rdi
0x180081a4a  mov     [rsp+210h+var_1D0], rdi
0x180081a4f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180081a53  mov     [rsp+210h+var_1A8], rsi
0x180081a58  mov     [rsp+210h+var_1A0], rsi
0x180081a5d  lea     rcx, [rbx+20h]; rclsid
0x180081a61  lea     rdx, [rsp+210h+lpsz]; lplpsz
0x180081a66  call    cs:__imp_StringFromCLSID
0x180081a6c  test    eax, eax
0x180081a6e  js      short loc_180081AD5
0x180081a70  mov     rcx, [rsp+210h+pv]; pv
0x180081a75  test    rcx, rcx
0x180081a78  jz      short loc_180081A85
0x180081a7a  call    cs:__imp_CoTaskMemFree
0x180081a80  mov     [rsp+210h+pv], rdi
0x180081a85  mov     [rsp+210h+var_1C0], rsi
0x180081a8a  mov     [rsp+210h+var_1B8], rsi
0x180081a8f  lea     rcx, [rbx+30h]; rclsid
0x180081a93  lea     rdx, [rsp+210h+pv]; lplpsz
0x180081a98  call    cs:__imp_StringFromCLSID
0x180081a9e  test    eax, eax
0x180081aa0  js      short loc_180081AD5
0x180081aa2  mov     rcx, [rsp+210h+var_1E0]; pv
0x180081aa7  test    rcx, rcx
0x180081aaa  jz      short loc_180081AB7
0x180081aac  call    cs:__imp_CoTaskMemFree
0x180081ab2  mov     [rsp+210h+var_1E0], rdi
0x180081ab7  mov     [rsp+210h+var_1D8], rsi
0x180081abc  mov     [rsp+210h+var_1D0], rsi
0x180081ac1  lea     rdx, [rsp+210h+var_1E0]; lplpsz
0x180081ac6  mov     rcx, rbx; rclsid
0x180081ac9  call    cs:__imp_StringFromCLSID
0x180081acf  test    eax, eax
0x180081ad1  mov     ebx, edi
0x180081ad3  jns     short loc_180081ADA
0x180081ad5  mov     ebx, 80004005h
0x180081ada  xorps   xmm0, xmm0
0x180081add  movups  xmmword ptr [rbp+110h+rclsid.Data1], xmm0
0x180081ae1  lea     r9, [rbp+110h+rclsid]; struct _GUID *
0x180081ae5  lea     r8, [rbp+110h+var_F0]; struct _GUID *
0x180081ae9  lea     rdx, [rbp+110h+var_100]; struct _GUID *
0x180081aed  lea     rcx, [rbp+110h+var_160]; this
0x180081af1  call    ?GetPrinterDriverAssociation@PrinterExtensionRegistrar@Driver@Print@@AEAA_NAEBU_GUID@@0AEAU4@@Z; Print::Driver::PrinterExtensionRegistrar::GetPrinterDriverAssociation(_GUID const &,_GUID const &,_GUID &)
0x180081af6  test    al, al
0x180081af8  jz      loc_180081BDA
0x180081afe  mov     [rsp+210h+var_198], rdi
0x180081b03  mov     [rbp+110h+var_190], rdi
0x180081b07  mov     [rbp+110h+var_188], rdi
0x180081b0b  test    ebx, ebx
0x180081b0d  js      short loc_180081B5D
0x180081b0f  mov     [rbp+110h+var_190], rsi
0x180081b13  mov     [rbp+110h+var_188], rsi
0x180081b17  lea     rdx, [rsp+210h+var_198]; lplpsz
0x180081b1c  lea     rcx, [rbp+110h+rclsid]; rclsid
0x180081b20  call    cs:__imp_StringFromCLSID
0x180081b26  test    eax, eax
0x180081b28  js      short loc_180081B5D
0x180081b2a  mov     rax, [rsp+210h+var_1E0]
0x180081b2f  mov     [rsp+210h+var_1E8], rax
0x180081b34  mov     rax, [rsp+210h+var_198]
0x180081b39  mov     [rsp+210h+var_1F0], rax
0x180081b3e  mov     r9, [rsp+210h+pv]
0x180081b43  mov     r8, [rsp+210h+lpsz]
0x180081b48  lea     rdx, aReplacingAssoc; "Replacing association. printerDriverId="...
0x180081b4f  lea     rcx, aPrintDriverPri_0; "Print::Driver::PrinterExtensionRegistra"...
0x180081b56  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180081b5b  jmp     short loc_180081B70
0x180081b5d  lea     rdx, aErrorConvertin; "Error converting CLSIDs to strings"
0x180081b64  lea     rcx, aPrintDriverPri_0; "Print::Driver::PrinterExtensionRegistra"...
0x180081b6b  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180081b70  movups  xmm0, xmmword ptr [rbp+110h+rclsid.Data1]
0x180081b74  movdqu  [rbp+110h+var_C0], xmm0
0x180081b79  lea     rdx, [rbp+110h+var_120]; struct Print::Driver::PrinterExtensionAssociationInfo *
0x180081b7d  lea     rcx, [rbp+110h+var_160]; this
0x180081b81  call    ?SetLinkAssociation@PrinterExtensionRegistrar@Driver@Print@@AEAAXAEAVPrinterExtensionAssociationInfo@23@@Z; Print::Driver::PrinterExtensionRegistrar::SetLinkAssociation(Print::Driver::PrinterExtensionAssociationInfo &)
0x180081b86  lea     rcx, [rbp+110h+var_A0]; this
0x180081b8a  call    ??0PrinterExtensionAssociationInfo@Driver@Print@@QEAA@XZ; Print::Driver::PrinterExtensionAssociationInfo::PrinterExtensionAssociationInfo(void)
0x180081b8f  nop
0x180081b90  lea     r8, [rbp+110h+var_A0]; struct Print::Driver::PrinterExtensionAssociationInfo *
0x180081b94  lea     rdx, [rbp+110h+rclsid]; struct _GUID *
0x180081b98  lea     rcx, [rbp+110h+var_160]; this
0x180081b9c  call    ?GetAssociation@PrinterExtensionRegistrar@Driver@Print@@AEAAXAEBU_GUID@@AEAVPrinterExtensionAssociationInfo@23@@Z; Print::Driver::PrinterExtensionRegistrar::GetAssociation(_GUID const &,Print::Driver::PrinterExtensionAssociationInfo &)
0x180081ba1  movaps  xmm0, xmmword ptr [rbp+110h+var_120.Data1]
0x180081ba5  movdqu  [rbp+110h+var_30], xmm0
0x180081bad  lea     rdx, [rbp+110h+var_A0]; struct Print::Driver::PrinterExtensionAssociationInfo *
0x180081bb1  lea     rcx, [rbp+110h+var_160]; this
0x180081bb5  call    ?SetLinkAssociation@PrinterExtensionRegistrar@Driver@Print@@AEAAXAEAVPrinterExtensionAssociationInfo@23@@Z; Print::Driver::PrinterExtensionRegistrar::SetLinkAssociation(Print::Driver::PrinterExtensionAssociationInfo &)
0x180081bba  nop
0x180081bbb  lea     rcx, [rbp+110h+var_60]
0x180081bc2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180081bc7  nop
0x180081bc8  mov     rcx, [rsp+210h+var_198]; pv
0x180081bcd  test    rcx, rcx
0x180081bd0  jz      short loc_180081C13
0x180081bd2  call    cs:__imp_CoTaskMemFree
0x180081bd8  jmp     short loc_180081C13
0x180081bda  lea     rcx, aPrintDriverPri_0; "Print::Driver::PrinterExtensionRegistra"...
0x180081be1  test    ebx, ebx
0x180081be3  js      short loc_180081C07
0x180081be5  mov     rax, [rsp+210h+var_1E0]
0x180081bea  mov     [rsp+210h+var_1F0], rax
0x180081bef  mov     r9, [rsp+210h+pv]
0x180081bf4  mov     r8, [rsp+210h+lpsz]
0x180081bf9  lea     rdx, aNewAssociation; "New association. printerDriverId=%ws re"...
0x180081c00  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180081c05  jmp     short loc_180081C13
0x180081c07  lea     rdx, aErrorConvertin; "Error converting CLSIDs to strings"
0x180081c0e  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180081c13  lea     r9, [rbp+110h+var_120]; struct _GUID *
0x180081c17  lea     r8, [rbp+110h+var_F0]; struct _GUID *
0x180081c1b  lea     rdx, [rbp+110h+var_100]; struct _GUID *
0x180081c1f  lea     rcx, [rbp+110h+var_160]; this
0x180081c23  call    ?SetPrinterDriverAssociation@PrinterExtensionRegistrar@Driver@Print@@AEAAXAEBU_GUID@@00@Z; Print::Driver::PrinterExtensionRegistrar::SetPrinterDriverAssociation(_GUID const &,_GUID const &,_GUID const &)
0x180081c28  nop
0x180081c29  mov     rcx, [rsp+210h+var_1E0]; pv
0x180081c2e  test    rcx, rcx
0x180081c31  jz      short loc_180081C3E
0x180081c33  call    cs:__imp_CoTaskMemFree
0x180081c39  mov     [rsp+210h+var_1E0], rdi
0x180081c3e  mov     [rsp+210h+var_1D8], rdi
0x180081c43  mov     [rsp+210h+var_1D0], rdi
0x180081c48  mov     rcx, [rsp+210h+pv]; pv
0x180081c4d  test    rcx, rcx
0x180081c50  jz      short loc_180081C5D
0x180081c52  call    cs:__imp_CoTaskMemFree
0x180081c58  mov     [rsp+210h+pv], rdi
0x180081c5d  mov     [rsp+210h+var_1C0], rdi
0x180081c62  mov     [rsp+210h+var_1B8], rdi
0x180081c67  mov     rcx, [rsp+210h+lpsz]; pv
0x180081c6c  test    rcx, rcx
0x180081c6f  jz      short loc_180081C7C
0x180081c71  call    cs:__imp_CoTaskMemFree
0x180081c77  mov     [rsp+210h+lpsz], rdi
0x180081c7c  mov     [rsp+210h+var_1A8], rdi
0x180081c81  mov     [rsp+210h+var_1A0], rdi
0x180081c86  lea     rcx, [rbp+110h+var_E0]
0x180081c8a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180081c8f  nop
0x180081c90  lea     rcx, [rbp+110h+var_160]; this
0x180081c94  call    ??1PrinterExtensionRegistrar@Driver@Print@@QEAA@XZ; Print::Driver::PrinterExtensionRegistrar::~PrinterExtensionRegistrar(void)
0x180081c99  mov     rcx, [rbp+110h+var_20]
0x180081ca0  xor     rcx, rsp; StackCookie
0x180081ca3  call    __security_check_cookie
0x180081ca8  mov     rbx, [rsp+210h+arg_18]
0x180081cb0  add     rsp, 200h
0x180081cb7  pop     rdi
0x180081cb8  pop     rsi
0x180081cb9  pop     rbp
0x180081cba  retn
```
