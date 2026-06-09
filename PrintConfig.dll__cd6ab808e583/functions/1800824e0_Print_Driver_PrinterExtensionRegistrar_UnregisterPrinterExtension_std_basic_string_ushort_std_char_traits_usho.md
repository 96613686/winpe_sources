# Print::Driver::PrinterExtensionRegistrar::UnregisterPrinterExtension(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::shared_ptr<Win32Adapters::TransactionManager::Transaction> const &,Print::Driver::PrinterExtensionAssociationInfo const &)

- ea: `0x1800824e0`
- end: `0x1800827e2`
- name: `?UnregisterPrinterExtension@PrinterExtensionRegistrar@Driver@Print@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$shared_ptr@VTransaction@TransactionManager@Win32Adapters@@@5@AEBVPrinterExtensionAssociationInfo@23@@Z`
- size: `770`
- prototype: `char __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18007f2a8`
- `0x180089b20`

## callees

- `0x1800032e0`
- `0x18000f590`
- `0x1800183a0`
- `0x1800183f8`
- `0x180036244`
- `0x18007edc4`
- `0x18007ee4c`
- `0x18007f194`
- `0x18007fb18`
- `0x18008006c`
- `0x180081200`
- `0x1800818c4`
- `0x180081e00`
- `0x1800822c4`
- `0x1800824e0`
- `0x1801adb40`

## import_xrefs

- `ole32!StringFromCLSID` at `0x1800826dc`
- `ole32!StringFromCLSID` at `0x180082711`
- `ole32!StringFromCLSID` at `0x1800826dc`
- `ole32!StringFromCLSID` at `0x180082711`
- `ole32!CoTaskMemFree` at `0x1800826f0`
- `ole32!CoTaskMemFree` at `0x180082778`
- `ole32!CoTaskMemFree` at `0x1800827a3`
- `ole32!CoTaskMemFree` at `0x1800826f0`
- `ole32!CoTaskMemFree` at `0x180082778`
- `ole32!CoTaskMemFree` at `0x1800827a3`

## string_xrefs

- `0x180082759`: `Error converting CLSIDs to strings`
- `0x1800825e1`: `Printer extension registration is in current format and was located.`
- `0x1800825e8`: `Print::Driver::PrinterExtensionRegistrar::UnregisterPrinterExtension`
- `0x180082691`: `Print::Driver::PrinterExtensionRegistrar::UnregisterPrinterExtension`
- `0x18008274b`: `Print::Driver::PrinterExtensionRegistrar::UnregisterPrinterExtension`
- `0x180082760`: `Print::Driver::PrinterExtensionRegistrar::UnregisterPrinterExtension`
- `0x18008268a`: `Printer extension registration is in pre-Win8RC format and was removed.`
- `0x180082744`: `Unable to locate printer extension. printerDriverId=%ws reasonId=%ws driverHadAssociation=%ws associationFound=%ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
char __fastcall Print::Driver::PrinterExtensionRegistrar::UnregisterPrinterExtension(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  char v4; // r15
  char v5; // bl
  __int64 v6; // rcx
  const wchar_t *v7; // rax
  struct _GUID Buf1; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v10; // [rsp+50h] [rbp-B0h]
  LPOLESTR lpsz[2]; // [rsp+60h] [rbp-A0h] BYREF
  __m128i si128; // [rsp+70h] [rbp-90h]
  struct _GUID Buf2; // [rsp+80h] [rbp-80h] BYREF
  HKEY v14[5]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v15[24]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v16[16]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v17; // [rsp+E0h] [rbp-20h]
  __int64 v18; // [rsp+E8h] [rbp-18h]
  struct _GUID v19; // [rsp+F0h] [rbp-10h] BYREF
  struct _GUID v20; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v21[32]; // [rsp+110h] [rbp+10h] BYREF
  struct _GUID v22; // [rsp+130h] [rbp+30h] BYREF

  Print::Driver::PrinterExtensionRegistrar::PrinterExtensionRegistrar(v14);
  Print::Driver::PrinterExtensionAssociationInfo::PrinterExtensionAssociationInfo((Print::Driver::PrinterExtensionAssociationInfo *)v16);
  v4 = 0;
  Buf2 = 0;
  v5 = 1;
  if ( Print::Driver::PrinterExtensionRegistrar::GetPrinterDriverAssociation(
         (Print::Driver::PrinterExtensionRegistrar *)v14,
         (const struct _GUID *)(a3 + 32),
         (const struct _GUID *)(a3 + 48),
         &Buf2) )
  {
    v4 = 1;
    for ( Buf1 = Buf2; memcmp_0(&Buf1, &GUID_NULL, 0x10u); Buf1 = v22 )
    {
      Print::Driver::PrinterExtensionRegistrar::GetAssociation(
        (Print::Driver::PrinterExtensionRegistrar *)v14,
        &Buf1,
        (struct Print::Driver::PrinterExtensionAssociationInfo *)v16);
      if ( *(_QWORD *)(a3 + 16) == v17
        && *(_QWORD *)(a3 + 24) == v18
        && *(_QWORD *)(a3 + 32) == *(_QWORD *)&v19.Data1
        && *(_QWORD *)(a3 + 40) == *(_QWORD *)v19.Data4
        && *(_QWORD *)(a3 + 48) == *(_QWORD *)&v20.Data1
        && *(_QWORD *)(a3 + 56) == *(_QWORD *)v20.Data4 )
      {
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
          "Print::Driver::PrinterExtensionRegistrar::UnregisterPrinterExtension",
          L"Printer extension registration is in current format and was located.");
        Print::Driver::PrinterExtensionRegistrar::UnlinkAssociation(
          (Print::Driver::PrinterExtensionRegistrar *)v14,
          (const struct Print::Driver::PrinterExtensionAssociationInfo *)v16);
        if ( !memcmp_0(v16, &Buf2, 0x10u) )
          Print::Driver::PrinterExtensionRegistrar::SetPrinterDriverAssociation(v14, &v19, &v20, &v22);
        *(_OWORD *)lpsz = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(lpsz[0]) = 0;
        Print::Driver::PrinterExtensionRegistrar::GetSubkeyPathForPrinterExtensionAssociation(v6, v16, lpsz);
        Win32Adapters::Registry::RegDeleteKeyTransactedW(v14[0], lpsz, v15);
        std::wstring::~wstring(lpsz);
        goto LABEL_28;
      }
    }
  }
  if ( Print::Driver::PrinterExtensionRegistrar::DeleteOldRegistration(
         (Print::Driver::PrinterExtensionRegistrar *)v14,
         (const struct Print::Driver::PrinterExtensionAssociationInfo *)a3) )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "Print::Driver::PrinterExtensionRegistrar::UnregisterPrinterExtension",
      L"Printer extension registration is in pre-Win8RC format and was removed.");
  }
  else
  {
    lpsz[0] = 0;
    Buf1 = (struct _GUID)0LL;
    v10 = 0;
    lpsz[1] = (LPOLESTR)-1LL;
    si128.m128i_i64[0] = -1;
    if ( StringFromCLSID((const IID *const)(a3 + 32), lpsz) < 0 )
      goto LABEL_23;
    if ( *(_QWORD *)&Buf1.Data1 )
    {
      CoTaskMemFree(*(LPVOID *)&Buf1.Data1);
      *(_QWORD *)&Buf1.Data1 = 0;
    }
    *(_QWORD *)Buf1.Data4 = -1;
    v10 = -1;
    if ( StringFromCLSID((const IID *const)(a3 + 48), (LPOLESTR *)&Buf1) < 0 )
    {
LABEL_23:
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
        "Print::Driver::PrinterExtensionRegistrar::UnregisterPrinterExtension",
        L"Error converting CLSIDs to strings");
    }
    else
    {
      v7 = L"true";
      if ( !v4 )
        v7 = L"false";
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
        "Print::Driver::PrinterExtensionRegistrar::UnregisterPrinterExtension",
        L"Unable to locate printer extension. printerDriverId=%ws reasonId=%ws driverHadAssociation=%ws associationFound=%ws",
        lpsz[0],
        *(_QWORD *)&Buf1.Data1,
        v7,
        L"false",
        -2);
    }
    v5 = 0;
    if ( *(_QWORD *)&Buf1.Data1 )
    {
      CoTaskMemFree(*(LPVOID *)&Buf1.Data1);
      *(_QWORD *)&Buf1.Data1 = 0;
    }
    *(_QWORD *)Buf1.Data4 = 0;
    v10 = 0;
    if ( lpsz[0] )
      CoTaskMemFree(lpsz[0]);
  }
LABEL_28:
  std::wstring::~wstring(v21);
  Print::Driver::PrinterExtensionRegistrar::~PrinterExtensionRegistrar((Print::Driver::PrinterExtensionRegistrar *)v14);
  return v5;
}

```

## disassembly

```asm
0x1800824e0  mov     rax, rsp
0x1800824e3  push    rbp
0x1800824e4  push    rsi
0x1800824e5  push    rdi
0x1800824e6  push    r14
0x1800824e8  push    r15
0x1800824ea  lea     rbp, [rsp-60h]
0x1800824ef  sub     rsp, 160h
0x1800824f6  mov     [rsp+180h+var_150], 0FFFFFFFFFFFFFFFEh
0x1800824ff  mov     [rax+20h], rbx
0x180082503  mov     rax, cs:__security_cookie
0x18008250a  xor     rax, rsp
0x18008250d  mov     [rbp+80h+var_30], rax
0x180082511  mov     rdi, r8
0x180082514  mov     r8, rdx
0x180082517  mov     rdx, rcx
0x18008251a  lea     rcx, [rbp+80h+var_F0]; PHKEY
0x18008251e  call    ??0PrinterExtensionRegistrar@Driver@Print@@AEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$shared_ptr@VTransaction@TransactionManager@Win32Adapters@@@4@@Z; Print::Driver::PrinterExtensionRegistrar::PrinterExtensionRegistrar(std::wstring const &,std::shared_ptr<Win32Adapters::TransactionManager::Transaction> const &)
0x180082523  nop
0x180082524  lea     rcx, [rbp+80h+var_B0]; this
0x180082528  call    ??0PrinterExtensionAssociationInfo@Driver@Print@@QEAA@XZ; Print::Driver::PrinterExtensionAssociationInfo::PrinterExtensionAssociationInfo(void)
0x18008252d  nop
0x18008252e  xor     r15b, r15b
0x180082531  xorps   xmm0, xmm0
0x180082534  movups  [rbp+80h+Buf2], xmm0
0x180082538  lea     r14, [rdi+30h]
0x18008253c  lea     rsi, [rdi+20h]
0x180082540  lea     r9, [rbp+80h+Buf2]; struct _GUID *
0x180082544  mov     r8, r14; struct _GUID *
0x180082547  mov     rdx, rsi; struct _GUID *
0x18008254a  lea     rcx, [rbp+80h+var_F0]; this
0x18008254e  call    ?GetPrinterDriverAssociation@PrinterExtensionRegistrar@Driver@Print@@AEAA_NAEBU_GUID@@0AEAU4@@Z; Print::Driver::PrinterExtensionRegistrar::GetPrinterDriverAssociation(_GUID const &,_GUID const &,_GUID &)
0x180082553  mov     bl, 1
0x180082555  test    al, al
0x180082557  jz      loc_18008267A
0x18008255d  mov     r15b, bl
0x180082560  movaps  xmm0, [rbp+80h+Buf2]
0x180082564  movdqa  [rsp+180h+Buf1], xmm0
0x18008256a  mov     r8d, 10h; Size
0x180082570  lea     rdx, GUID_NULL; Buf2
0x180082577  lea     rcx, [rsp+180h+Buf1]; Buf1
0x18008257c  call    memcmp_0
0x180082581  test    eax, eax
0x180082583  jz      loc_18008267A
0x180082589  lea     r8, [rbp+80h+var_B0]; struct Print::Driver::PrinterExtensionAssociationInfo *
0x18008258d  lea     rdx, [rsp+180h+Buf1]; struct _GUID *
0x180082592  lea     rcx, [rbp+80h+var_F0]; this
0x180082596  call    ?GetAssociation@PrinterExtensionRegistrar@Driver@Print@@AEAAXAEBU_GUID@@AEAVPrinterExtensionAssociationInfo@23@@Z; Print::Driver::PrinterExtensionRegistrar::GetAssociation(_GUID const &,Print::Driver::PrinterExtensionAssociationInfo &)
0x18008259b  mov     rax, [rdi+10h]
0x18008259f  cmp     rax, [rbp+80h+var_A0]
0x1800825a3  jnz     short loc_1800825D5
0x1800825a5  mov     rax, [rdi+18h]
0x1800825a9  cmp     rax, [rbp+80h+var_98]
0x1800825ad  jnz     short loc_1800825D5
0x1800825af  mov     rax, [rsi]
0x1800825b2  cmp     rax, qword ptr [rbp+80h+var_90.Data1]
0x1800825b6  jnz     short loc_1800825D5
0x1800825b8  mov     rax, [rsi+8]
0x1800825bc  cmp     rax, qword ptr [rbp+80h+var_90.Data4]
0x1800825c0  jnz     short loc_1800825D5
0x1800825c2  mov     rax, [r14]
0x1800825c5  cmp     rax, qword ptr [rbp+80h+var_80.Data1]
0x1800825c9  jnz     short loc_1800825D5
0x1800825cb  mov     rax, [r14+8]
0x1800825cf  cmp     rax, qword ptr [rbp+80h+var_80.Data4]
0x1800825d3  jz      short loc_1800825E1
0x1800825d5  movaps  xmm0, xmmword ptr [rbp+80h+var_50.Data1]
0x1800825d9  movdqu  [rsp+180h+Buf1], xmm0
0x1800825df  jmp     short loc_18008256A
0x1800825e1  lea     rdx, aPrinterExtensi; "Printer extension registration is in cu"...
0x1800825e8  lea     rcx, aPrintDriverPri_1; "Print::Driver::PrinterExtensionRegistra"...
0x1800825ef  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800825f4  lea     rdx, [rbp+80h+var_B0]; struct Print::Driver::PrinterExtensionAssociationInfo *
0x1800825f8  lea     rcx, [rbp+80h+var_F0]; this
0x1800825fc  call    ?UnlinkAssociation@PrinterExtensionRegistrar@Driver@Print@@AEAAXAEBVPrinterExtensionAssociationInfo@23@@Z; Print::Driver::PrinterExtensionRegistrar::UnlinkAssociation(Print::Driver::PrinterExtensionAssociationInfo const &)
0x180082601  mov     r8d, 10h; Size
0x180082607  lea     rdx, [rbp+80h+Buf2]; Buf2
0x18008260b  lea     rcx, [rbp+80h+var_B0]; Buf1
0x18008260f  call    memcmp_0
0x180082614  test    eax, eax
0x180082616  jnz     short loc_18008262D
0x180082618  lea     r9, [rbp+80h+var_50]; struct _GUID *
0x18008261c  lea     r8, [rbp+80h+var_80]; struct _GUID *
0x180082620  lea     rdx, [rbp+80h+var_90]; struct _GUID *
0x180082624  lea     rcx, [rbp+80h+var_F0]; this
0x180082628  call    ?SetPrinterDriverAssociation@PrinterExtensionRegistrar@Driver@Print@@AEAAXAEBU_GUID@@00@Z; Print::Driver::PrinterExtensionRegistrar::SetPrinterDriverAssociation(_GUID const &,_GUID const &,_GUID const &)
0x18008262d  xorps   xmm0, xmm0
0x180082630  movups  xmmword ptr [rsp+180h+lpsz], xmm0
0x180082635  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18008263d  movdqu  [rsp+180h+var_110], xmm1
0x180082643  xor     eax, eax
0x180082645  mov     word ptr [rsp+180h+lpsz], ax
0x18008264a  lea     r8, [rsp+180h+lpsz]
0x18008264f  lea     rdx, [rbp+80h+var_B0]
0x180082653  call    ?GetSubkeyPathForPrinterExtensionAssociation@PrinterExtensionRegistrar@Driver@Print@@AEAAXAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Print::Driver::PrinterExtensionRegistrar::GetSubkeyPathForPrinterExtensionAssociation(_GUID const &,std::wstring &)
0x180082658  lea     r8, [rbp+80h+var_C8]
0x18008265c  lea     rdx, [rsp+180h+lpsz]
0x180082661  mov     rcx, [rbp+80h+var_F0]
0x180082665  call    ?RegDeleteKeyTransactedW@Registry@Win32Adapters@@YAXPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$shared_ptr@VTransaction@TransactionManager@Win32Adapters@@@5@@Z; Win32Adapters::Registry::RegDeleteKeyTransactedW(HKEY__ *,std::wstring const &,std::shared_ptr<Win32Adapters::TransactionManager::Transaction> const &)
0x18008266a  nop
0x18008266b  lea     rcx, [rsp+180h+lpsz]
0x180082670  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180082675  jmp     loc_1800827AA
0x18008267a  mov     rdx, rdi; struct Print::Driver::PrinterExtensionAssociationInfo *
0x18008267d  lea     rcx, [rbp+80h+var_F0]; this
0x180082681  call    ?DeleteOldRegistration@PrinterExtensionRegistrar@Driver@Print@@AEAA_NAEBVPrinterExtensionAssociationInfo@23@@Z; Print::Driver::PrinterExtensionRegistrar::DeleteOldRegistration(Print::Driver::PrinterExtensionAssociationInfo const &)
0x180082686  test    al, al
0x180082688  jz      short loc_1800826A2
0x18008268a  lea     rdx, aPrinterExtensi_0; "Printer extension registration is in pr"...
0x180082691  lea     rcx, aPrintDriverPri_1; "Print::Driver::PrinterExtensionRegistra"...
0x180082698  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18008269d  jmp     loc_1800827AA
0x1800826a2  mov     [rsp+180h+lpsz], 0
0x1800826ab  mov     qword ptr [rsp+180h+Buf1], 0
0x1800826b4  mov     qword ptr [rsp+180h+Buf1+8], 0
0x1800826bd  mov     [rsp+180h+var_130], 0
0x1800826c6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800826ca  mov     [rsp+180h+lpsz+8], rbx
0x1800826cf  mov     qword ptr [rsp+180h+var_110], rbx
0x1800826d4  lea     rdx, [rsp+180h+lpsz]; lplpsz
0x1800826d9  mov     rcx, rsi; rclsid
0x1800826dc  call    cs:__imp_StringFromCLSID
0x1800826e2  test    eax, eax
0x1800826e4  js      short loc_180082759
0x1800826e6  mov     rcx, qword ptr [rsp+180h+Buf1]; pv
0x1800826eb  test    rcx, rcx
0x1800826ee  jz      short loc_1800826FF
0x1800826f0  call    cs:__imp_CoTaskMemFree
0x1800826f6  mov     qword ptr [rsp+180h+Buf1], 0
0x1800826ff  mov     qword ptr [rsp+180h+Buf1+8], rbx
0x180082704  mov     [rsp+180h+var_130], rbx
0x180082709  lea     rdx, [rsp+180h+Buf1]; lplpsz
0x18008270e  mov     rcx, r14; rclsid
0x180082711  call    cs:__imp_StringFromCLSID
0x180082717  test    eax, eax
0x180082719  js      short loc_180082759
0x18008271b  lea     rcx, aFalse_0; "false"
0x180082722  lea     rax, aTrue; "true"
0x180082729  test    r15b, r15b
0x18008272c  cmovz   rax, rcx
0x180082730  mov     [rsp+180h+var_158], rcx
0x180082735  mov     [rsp+180h+var_160], rax
0x18008273a  mov     r9, qword ptr [rsp+180h+Buf1]
0x18008273f  mov     r8, [rsp+180h+lpsz]
0x180082744  lea     rdx, aUnableToLocate_1; "Unable to locate printer extension. pri"...
0x18008274b  lea     rcx, aPrintDriverPri_1; "Print::Driver::PrinterExtensionRegistra"...
0x180082752  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180082757  jmp     short loc_18008276C
0x180082759  lea     rdx, aErrorConvertin; "Error converting CLSIDs to strings"
0x180082760  lea     rcx, aPrintDriverPri_1; "Print::Driver::PrinterExtensionRegistra"...
0x180082767  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18008276c  xor     bl, bl
0x18008276e  mov     rcx, qword ptr [rsp+180h+Buf1]; pv
0x180082773  test    rcx, rcx
0x180082776  jz      short loc_180082787
0x180082778  call    cs:__imp_CoTaskMemFree
0x18008277e  mov     qword ptr [rsp+180h+Buf1], 0
0x180082787  mov     qword ptr [rsp+180h+Buf1+8], 0
0x180082790  mov     [rsp+180h+var_130], 0
0x180082799  mov     rcx, [rsp+180h+lpsz]; pv
0x18008279e  test    rcx, rcx
0x1800827a1  jz      short loc_1800827AA
0x1800827a3  call    cs:__imp_CoTaskMemFree
0x1800827a9  nop
0x1800827aa  lea     rcx, [rbp+80h+var_70]
0x1800827ae  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800827b3  nop
0x1800827b4  lea     rcx, [rbp+80h+var_F0]; this
0x1800827b8  call    ??1PrinterExtensionRegistrar@Driver@Print@@QEAA@XZ; Print::Driver::PrinterExtensionRegistrar::~PrinterExtensionRegistrar(void)
0x1800827bd  mov     al, bl
0x1800827bf  mov     rcx, [rbp+80h+var_30]
0x1800827c3  xor     rcx, rsp; StackCookie
0x1800827c6  call    __security_check_cookie
0x1800827cb  mov     rbx, [rsp+180h+arg_18]
0x1800827d3  add     rsp, 160h
0x1800827da  pop     r15
0x1800827dc  pop     r14
0x1800827de  pop     rdi
0x1800827df  pop     rsi
0x1800827e0  pop     rbp
0x1800827e1  retn
```
