# Print::Driver::PrinterExtensionRegistrar::UnregisterPrinterExtension(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::shared_ptr<Win32Adapters::TransactionManager::Transaction> const &,Print::Driver::PrinterExtensionAssociationInfo const &)

- ea: `0x1800855dc`
- end: `0x1800858fd`
- name: `?UnregisterPrinterExtension@PrinterExtensionRegistrar@Driver@Print@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$shared_ptr@VTransaction@TransactionManager@Win32Adapters@@@5@AEBVPrinterExtensionAssociationInfo@23@@Z`
- size: `801`
- prototype: `char __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800821dc`
- `0x18008d000`

## callees

- `0x180003400`
- `0x18000fa4c`
- `0x180018f00`
- `0x180018f58`
- `0x180037620`
- `0x180081cc0`
- `0x180081d4c`
- `0x1800820a4`
- `0x180082a98`
- `0x180083010`
- `0x1800841f0`
- `0x180084918`
- `0x180084e98`
- `0x1800853a8`
- `0x1800855dc`
- `0x1801b56b0`

## import_xrefs

- `ole32!StringFromCLSID` at `0x1800857d8`
- `ole32!StringFromCLSID` at `0x180085819`
- `ole32!StringFromCLSID` at `0x1800857d8`
- `ole32!StringFromCLSID` at `0x180085819`
- `ole32!CoTaskMemFree` at `0x1800857f2`
- `ole32!CoTaskMemFree` at `0x180085886`
- `ole32!CoTaskMemFree` at `0x1800858b7`
- `ole32!CoTaskMemFree` at `0x1800857f2`
- `ole32!CoTaskMemFree` at `0x180085886`
- `ole32!CoTaskMemFree` at `0x1800858b7`

## string_xrefs

- `0x180085867`: `Error converting CLSIDs to strings`
- `0x1800856dd`: `Printer extension registration is in current format and was located.`
- `0x1800856e4`: `Print::Driver::PrinterExtensionRegistrar::UnregisterPrinterExtension`
- `0x18008578d`: `Print::Driver::PrinterExtensionRegistrar::UnregisterPrinterExtension`
- `0x180085859`: `Print::Driver::PrinterExtensionRegistrar::UnregisterPrinterExtension`
- `0x18008586e`: `Print::Driver::PrinterExtensionRegistrar::UnregisterPrinterExtension`
- `0x180085786`: `Printer extension registration is in pre-Win8RC format and was removed.`
- `0x180085852`: `Unable to locate printer extension. printerDriverId=%ws reasonId=%ws driverHadAssociation=%ws associationFound=%ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
  GUID v16; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v17; // [rsp+E0h] [rbp-20h]
  __int64 v18; // [rsp+E8h] [rbp-18h]
  struct _GUID v19; // [rsp+F0h] [rbp-10h] BYREF
  struct _GUID v20; // [rsp+100h] [rbp+0h] BYREF
  char *v21; // [rsp+110h] [rbp+10h] BYREF
  struct _GUID v22; // [rsp+130h] [rbp+30h] BYREF

  Print::Driver::PrinterExtensionRegistrar::PrinterExtensionRegistrar(v14, a1, a2);
  Print::Driver::PrinterExtensionAssociationInfo::PrinterExtensionAssociationInfo(&v16);
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
        &v16);
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
          (const struct Print::Driver::PrinterExtensionAssociationInfo *)&v16);
        if ( !memcmp_0(&v16, &Buf2, 0x10u) )
          Print::Driver::PrinterExtensionRegistrar::SetPrinterDriverAssociation(
            (Print::Driver::PrinterExtensionRegistrar *)v14,
            &v19,
            &v20,
            &v22);
        *(_OWORD *)lpsz = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(lpsz[0]) = 0;
        Print::Driver::PrinterExtensionRegistrar::GetSubkeyPathForPrinterExtensionAssociation(v6, &v16, (char **)lpsz);
        Win32Adapters::Registry::RegDeleteKeyTransactedW((__int64)v14[0], lpsz, (__int64)v15);
        std::wstring::~wstring((char **)lpsz);
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
  std::wstring::~wstring(&v21);
  Print::Driver::PrinterExtensionRegistrar::~PrinterExtensionRegistrar((Print::Driver::PrinterExtensionRegistrar *)v14);
  return v5;
}

```

## disassembly

```asm
0x1800855dc  mov     rax, rsp
0x1800855df  push    rbp
0x1800855e0  push    rsi
0x1800855e1  push    rdi
0x1800855e2  push    r14
0x1800855e4  push    r15
0x1800855e6  lea     rbp, [rsp-60h]
0x1800855eb  sub     rsp, 160h
0x1800855f2  mov     [rsp+180h+var_150], 0FFFFFFFFFFFFFFFEh
0x1800855fb  mov     [rax+20h], rbx
0x1800855ff  mov     rax, cs:__security_cookie
0x180085606  xor     rax, rsp
0x180085609  mov     [rbp+80h+var_30], rax
0x18008560d  mov     rdi, r8
0x180085610  mov     r8, rdx
0x180085613  mov     rdx, rcx
0x180085616  lea     rcx, [rbp+80h+var_F0]; PHKEY
0x18008561a  call    ??0PrinterExtensionRegistrar@Driver@Print@@AEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$shared_ptr@VTransaction@TransactionManager@Win32Adapters@@@4@@Z; Print::Driver::PrinterExtensionRegistrar::PrinterExtensionRegistrar(std::wstring const &,std::shared_ptr<Win32Adapters::TransactionManager::Transaction> const &)
0x18008561f  nop
0x180085620  lea     rcx, [rbp+80h+var_B0]; this
0x180085624  call    ??0PrinterExtensionAssociationInfo@Driver@Print@@QEAA@XZ; Print::Driver::PrinterExtensionAssociationInfo::PrinterExtensionAssociationInfo(void)
0x180085629  nop
0x18008562a  xor     r15b, r15b
0x18008562d  xorps   xmm0, xmm0
0x180085630  movups  [rbp+80h+Buf2], xmm0
0x180085634  lea     r14, [rdi+30h]
0x180085638  lea     rsi, [rdi+20h]
0x18008563c  lea     r9, [rbp+80h+Buf2]; struct _GUID *
0x180085640  mov     r8, r14; struct _GUID *
0x180085643  mov     rdx, rsi; struct _GUID *
0x180085646  lea     rcx, [rbp+80h+var_F0]; this
0x18008564a  call    ?GetPrinterDriverAssociation@PrinterExtensionRegistrar@Driver@Print@@AEAA_NAEBU_GUID@@0AEAU4@@Z; Print::Driver::PrinterExtensionRegistrar::GetPrinterDriverAssociation(_GUID const &,_GUID const &,_GUID &)
0x18008564f  mov     bl, 1
0x180085651  test    al, al
0x180085653  jz      loc_180085776
0x180085659  mov     r15b, bl
0x18008565c  movaps  xmm0, [rbp+80h+Buf2]
0x180085660  movdqa  [rsp+180h+Buf1], xmm0
0x180085666  mov     r8d, 10h; Size
0x18008566c  lea     rdx, GUID_NULL; Buf2
0x180085673  lea     rcx, [rsp+180h+Buf1]; Buf1
0x180085678  call    memcmp_0
0x18008567d  test    eax, eax
0x18008567f  jz      loc_180085776
0x180085685  lea     r8, [rbp+80h+var_B0]; struct Print::Driver::PrinterExtensionAssociationInfo *
0x180085689  lea     rdx, [rsp+180h+Buf1]; struct _GUID *
0x18008568e  lea     rcx, [rbp+80h+var_F0]; this
0x180085692  call    ?GetAssociation@PrinterExtensionRegistrar@Driver@Print@@AEAAXAEBU_GUID@@AEAVPrinterExtensionAssociationInfo@23@@Z; Print::Driver::PrinterExtensionRegistrar::GetAssociation(_GUID const &,Print::Driver::PrinterExtensionAssociationInfo &)
0x180085697  mov     rax, [rdi+10h]
0x18008569b  cmp     rax, [rbp+80h+var_A0]
0x18008569f  jnz     short loc_1800856D1
0x1800856a1  mov     rax, [rdi+18h]
0x1800856a5  cmp     rax, [rbp+80h+var_98]
0x1800856a9  jnz     short loc_1800856D1
0x1800856ab  mov     rax, [rsi]
0x1800856ae  cmp     rax, qword ptr [rbp+80h+var_90.Data1]
0x1800856b2  jnz     short loc_1800856D1
0x1800856b4  mov     rax, [rsi+8]
0x1800856b8  cmp     rax, qword ptr [rbp+80h+var_90.Data4]
0x1800856bc  jnz     short loc_1800856D1
0x1800856be  mov     rax, [r14]
0x1800856c1  cmp     rax, qword ptr [rbp+80h+var_80.Data1]
0x1800856c5  jnz     short loc_1800856D1
0x1800856c7  mov     rax, [r14+8]
0x1800856cb  cmp     rax, qword ptr [rbp+80h+var_80.Data4]
0x1800856cf  jz      short loc_1800856DD
0x1800856d1  movaps  xmm0, xmmword ptr [rbp+80h+var_50.Data1]
0x1800856d5  movdqu  [rsp+180h+Buf1], xmm0
0x1800856db  jmp     short loc_180085666
0x1800856dd  lea     rdx, aPrinterExtensi; "Printer extension registration is in cu"...
0x1800856e4  lea     rcx, aPrintDriverPri_1; "Print::Driver::PrinterExtensionRegistra"...
0x1800856eb  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800856f0  lea     rdx, [rbp+80h+var_B0]; struct Print::Driver::PrinterExtensionAssociationInfo *
0x1800856f4  lea     rcx, [rbp+80h+var_F0]; this
0x1800856f8  call    ?UnlinkAssociation@PrinterExtensionRegistrar@Driver@Print@@AEAAXAEBVPrinterExtensionAssociationInfo@23@@Z; Print::Driver::PrinterExtensionRegistrar::UnlinkAssociation(Print::Driver::PrinterExtensionAssociationInfo const &)
0x1800856fd  mov     r8d, 10h; Size
0x180085703  lea     rdx, [rbp+80h+Buf2]; Buf2
0x180085707  lea     rcx, [rbp+80h+var_B0]; Buf1
0x18008570b  call    memcmp_0
0x180085710  test    eax, eax
0x180085712  jnz     short loc_180085729
0x180085714  lea     r9, [rbp+80h+var_50]; struct _GUID *
0x180085718  lea     r8, [rbp+80h+var_80]; struct _GUID *
0x18008571c  lea     rdx, [rbp+80h+var_90]; struct _GUID *
0x180085720  lea     rcx, [rbp+80h+var_F0]; this
0x180085724  call    ?SetPrinterDriverAssociation@PrinterExtensionRegistrar@Driver@Print@@AEAAXAEBU_GUID@@00@Z; Print::Driver::PrinterExtensionRegistrar::SetPrinterDriverAssociation(_GUID const &,_GUID const &,_GUID const &)
0x180085729  xorps   xmm0, xmm0
0x18008572c  movups  xmmword ptr [rsp+180h+lpsz], xmm0
0x180085731  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180085739  movdqu  [rsp+180h+var_110], xmm1
0x18008573f  xor     eax, eax
0x180085741  mov     word ptr [rsp+180h+lpsz], ax
0x180085746  lea     r8, [rsp+180h+lpsz]
0x18008574b  lea     rdx, [rbp+80h+var_B0]
0x18008574f  call    ?GetSubkeyPathForPrinterExtensionAssociation@PrinterExtensionRegistrar@Driver@Print@@AEAAXAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Print::Driver::PrinterExtensionRegistrar::GetSubkeyPathForPrinterExtensionAssociation(_GUID const &,std::wstring &)
0x180085754  lea     r8, [rbp+80h+var_C8]
0x180085758  lea     rdx, [rsp+180h+lpsz]
0x18008575d  mov     rcx, [rbp+80h+var_F0]
0x180085761  call    ?RegDeleteKeyTransactedW@Registry@Win32Adapters@@YAXPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$shared_ptr@VTransaction@TransactionManager@Win32Adapters@@@5@@Z; Win32Adapters::Registry::RegDeleteKeyTransactedW(HKEY__ *,std::wstring const &,std::shared_ptr<Win32Adapters::TransactionManager::Transaction> const &)
0x180085766  nop
0x180085767  lea     rcx, [rsp+180h+lpsz]
0x18008576c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180085771  jmp     loc_1800858C4
0x180085776  mov     rdx, rdi; struct Print::Driver::PrinterExtensionAssociationInfo *
0x180085779  lea     rcx, [rbp+80h+var_F0]; this
0x18008577d  call    ?DeleteOldRegistration@PrinterExtensionRegistrar@Driver@Print@@AEAA_NAEBVPrinterExtensionAssociationInfo@23@@Z; Print::Driver::PrinterExtensionRegistrar::DeleteOldRegistration(Print::Driver::PrinterExtensionAssociationInfo const &)
0x180085782  test    al, al
0x180085784  jz      short loc_18008579E
0x180085786  lea     rdx, aPrinterExtensi_0; "Printer extension registration is in pr"...
0x18008578d  lea     rcx, aPrintDriverPri_1; "Print::Driver::PrinterExtensionRegistra"...
0x180085794  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180085799  jmp     loc_1800858C4
0x18008579e  mov     [rsp+180h+lpsz], 0
0x1800857a7  mov     qword ptr [rsp+180h+Buf1], 0
0x1800857b0  mov     qword ptr [rsp+180h+Buf1+8], 0
0x1800857b9  mov     [rsp+180h+var_130], 0
0x1800857c2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800857c6  mov     [rsp+180h+lpsz+8], rbx
0x1800857cb  mov     qword ptr [rsp+180h+var_110], rbx
0x1800857d0  lea     rdx, [rsp+180h+lpsz]; lplpsz
0x1800857d5  mov     rcx, rsi; rclsid
0x1800857d8  call    cs:__imp_StringFromCLSID
0x1800857df  nop     dword ptr [rax+rax+00h]
0x1800857e4  test    eax, eax
0x1800857e6  js      short loc_180085867
0x1800857e8  mov     rcx, qword ptr [rsp+180h+Buf1]; pv
0x1800857ed  test    rcx, rcx
0x1800857f0  jz      short loc_180085807
0x1800857f2  call    cs:__imp_CoTaskMemFree
0x1800857f9  nop     dword ptr [rax+rax+00h]
0x1800857fe  mov     qword ptr [rsp+180h+Buf1], 0
0x180085807  mov     qword ptr [rsp+180h+Buf1+8], rbx
0x18008580c  mov     [rsp+180h+var_130], rbx
0x180085811  lea     rdx, [rsp+180h+Buf1]; lplpsz
0x180085816  mov     rcx, r14; rclsid
0x180085819  call    cs:__imp_StringFromCLSID
0x180085820  nop     dword ptr [rax+rax+00h]
0x180085825  test    eax, eax
0x180085827  js      short loc_180085867
0x180085829  lea     rcx, aFalse_0; "false"
0x180085830  lea     rax, aTrue; "true"
0x180085837  test    r15b, r15b
0x18008583a  cmovz   rax, rcx
0x18008583e  mov     [rsp+180h+var_158], rcx
0x180085843  mov     [rsp+180h+var_160], rax
0x180085848  mov     r9, qword ptr [rsp+180h+Buf1]
0x18008584d  mov     r8, [rsp+180h+lpsz]
0x180085852  lea     rdx, aUnableToLocate_1; "Unable to locate printer extension. pri"...
0x180085859  lea     rcx, aPrintDriverPri_1; "Print::Driver::PrinterExtensionRegistra"...
0x180085860  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180085865  jmp     short loc_18008587A
0x180085867  lea     rdx, aErrorConvertin; "Error converting CLSIDs to strings"
0x18008586e  lea     rcx, aPrintDriverPri_1; "Print::Driver::PrinterExtensionRegistra"...
0x180085875  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18008587a  xor     bl, bl
0x18008587c  mov     rcx, qword ptr [rsp+180h+Buf1]; pv
0x180085881  test    rcx, rcx
0x180085884  jz      short loc_18008589B
0x180085886  call    cs:__imp_CoTaskMemFree
0x18008588d  nop     dword ptr [rax+rax+00h]
0x180085892  mov     qword ptr [rsp+180h+Buf1], 0
0x18008589b  mov     qword ptr [rsp+180h+Buf1+8], 0
0x1800858a4  mov     [rsp+180h+var_130], 0
0x1800858ad  mov     rcx, [rsp+180h+lpsz]; pv
0x1800858b2  test    rcx, rcx
0x1800858b5  jz      short loc_1800858C4
0x1800858b7  call    cs:__imp_CoTaskMemFree
0x1800858be  nop     dword ptr [rax+rax+00h]
0x1800858c3  nop
0x1800858c4  lea     rcx, [rbp+80h+var_70]
0x1800858c8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800858cd  nop
0x1800858ce  lea     rcx, [rbp+80h+var_F0]; this
0x1800858d2  call    ??1PrinterExtensionRegistrar@Driver@Print@@QEAA@XZ; Print::Driver::PrinterExtensionRegistrar::~PrinterExtensionRegistrar(void)
0x1800858d7  mov     al, bl
0x1800858d9  mov     rcx, [rbp+80h+var_30]
0x1800858dd  xor     rcx, rsp; StackCookie
0x1800858e0  call    __security_check_cookie
0x1800858e5  mov     rbx, [rsp+180h+arg_18]
0x1800858ed  add     rsp, 160h
0x1800858f4  pop     r15
0x1800858f6  pop     r14
0x1800858f8  pop     rdi
0x1800858f9  pop     rsi
0x1800858fa  pop     rbp
0x1800858fb  retn
```
