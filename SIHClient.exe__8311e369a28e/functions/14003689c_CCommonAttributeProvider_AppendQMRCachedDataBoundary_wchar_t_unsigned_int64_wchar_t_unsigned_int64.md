# CCommonAttributeProvider::AppendQMRCachedDataBoundary(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *)

- ea: `0x14003689c`
- end: `0x140036c21`
- name: `?AppendQMRCachedDataBoundary@CCommonAttributeProvider@@AEAAJPEA_W_KPEAPEA_WPEA_K@Z`
- size: `901`
- prototype: `__int64 __fastcall(CCommonAttributeProvider *this, wchar_t *, unsigned __int64, wchar_t **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140034ccc`

## callees

- `0x140003de4`
- `0x140008de4`
- `0x14000ce30`
- `0x14000cf80`
- `0x14000d814`
- `0x1400154b4`
- `0x140017bd0`
- `0x14003689c`
- `0x140036c54`
- `0x140036fc0`
- `0x1400374b0`
- `0x14003e34c`
- `0x14003f448`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400369f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140036bf2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400369f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140036bf2`

## string_xrefs

- `0x140036911`: `C:\__w\1\s\src\Client\Engine\lib\SLS\CommonAttributeProvider.cpp`
- `0x140036bd9`: `C:\__w\1\s\src\Client\Engine\lib\SLS\CommonAttributeProvider.cpp`
- `0x14003697d`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x140036ad3`: `Cached DataBoundary found: %ws`
- `0x1400369ca`: `In QMR, attempting to read cached data boundary`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCommonAttributeProvider::AppendQMRCachedDataBoundary(
        CCommonAttributeProvider *this,
        wchar_t *a2,
        unsigned __int64 a3,
        wchar_t **a4,
        unsigned __int64 *a5)
{
  _WORD *v8; // rbx
  _WORD *v9; // rdi
  unsigned __int64 v10; // rdx
  QMRUtil *v11; // rcx
  __int64 v12; // r14
  __int64 v13; // rcx
  signed int v14; // esi
  __int64 v15; // rdx
  int DataBoundaryCacheRegPath; // eax
  __int64 v17; // rcx
  void *v18; // rcx
  void *v19; // rdi
  int StringValue; // eax
  const char *v21; // r9
  __int64 v22; // r9
  __int64 v23; // rdx
  _WORD *v24; // rax
  int v26; // [rsp+20h] [rbp-B1h]
  int v27; // [rsp+20h] [rbp-B1h]
  int v28; // [rsp+20h] [rbp-B1h]
  _WORD *v29; // [rsp+40h] [rbp-91h] BYREF
  void *lpMem; // [rsp+48h] [rbp-89h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+50h] [rbp-81h] BYREF
  unsigned __int64 v32; // [rsp+58h] [rbp-79h] BYREF
  char v33[128]; // [rsp+60h] [rbp-71h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+57h]

  pszDest = a2;
  v32 = a3;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_QMRForAutopatchManaged_56753991>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_QMRForAutopatchManaged_56753991>::GetImpl'::`2'::impl) )
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x3A0,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\SLS\\CommonAttributeProvider.cpp",
      (const char *)0x80240067LL,
      (int)"Feature %hs is not enabled",
      "Feature_Containment_UUS_QMRForAutopatchManaged_56753991");
  v8 = 0;
  v29 = 0;
  *a4 = a2;
  *a5 = a3;
  v9 = 0;
  v12 = 64;
  if ( !(unsigned int)AreTestKeysAllowed() )
    goto LABEL_46;
  v8 = SafeSusComAllocArray((unsigned __int64)v11, v10);
  v29 = v8;
  v14 = v8 == 0 ? 0x8007000E : 0;
  if ( !v8 )
  {
    v15 = 938;
LABEL_39:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\SLS\\CommonAttributeProvider.cpp",
      (const char *)(unsigned int)v14,
      v26);
    goto LABEL_41;
  }
  v9 = v8;
  if ( (int)RegQueryStringValue(
              v13,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
              (__int64)L"QMRDataBoundaryOverride",
              (__int64)v8,
              64) >= 0 )
    WUTrace(0, 0, 4, 4, 0, L"Using QMRDataBoundaryOverride=%ws");
  if ( !*v8 )
  {
LABEL_46:
    if ( QMRUtil::GetInQMR(v11) )
    {
      WUTrace(0, 0, 4, 4, 0, L"In QMR, attempting to read cached data boundary");
      if ( v9 )
        CoTaskMemFree(v8);
      v8 = 0;
      v29 = 0;
      lpMem = 0;
      DataBoundaryCacheRegPath = GetDataBoundaryCacheRegPath((wchar_t **)&lpMem);
      v14 = DataBoundaryCacheRegPath;
      if ( DataBoundaryCacheRegPath < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x92,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\SLS\\slsutil.cpp",
          (const char *)(unsigned int)DataBoundaryCacheRegPath,
          v27);
        v18 = lpMem;
        if ( lpMem )
          goto LABEL_21;
        goto LABEL_22;
      }
      v19 = lpMem;
      StringValue = RegQueryStringValue(v17, (const WCHAR *)lpMem, (__int64)L"DeviceDataBoundary", (__int64)v33, 64);
      v14 = StringValue;
      if ( StringValue < 0 )
      {
        v22 = (unsigned int)StringValue;
        v23 = 153;
        goto LABEL_19;
      }
      v29 = 0;
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
        &v29,
        v33,
        0xFFFFFFFFFFFFFFFFuLL,
        v21);
      if ( !v29 )
      {
        v14 = -2147024882;
        v22 = 2147942414LL;
        v23 = 156;
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v23,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\SLS\\slsutil.cpp",
          (const char *)v22,
          v28);
        if ( v19 )
        {
          v18 = v19;
LABEL_21:
          SusFree(v18);
        }
LABEL_22:
        v15 = 953;
        goto LABEL_39;
      }
      v8 = v29;
      if ( v19 )
        SusFree(v19);
      WUTrace(0, 0, 4, 5, 0, L"Cached DataBoundary found: %ws");
    }
  }
  if ( v8 && *v8 )
  {
    v24 = v8;
    do
    {
      if ( !*v24 )
        break;
      ++v24;
      --v12;
    }
    while ( v12 );
    v14 = v12 == 0 ? 0x80070057 : 0;
    if ( !v12 )
    {
      v15 = 959;
      goto LABEL_39;
    }
    v14 = StringCchCatExW(a2, a3, L"&", &pszDest, &v32, 0x1800u);
    if ( v14 < 0 )
    {
      v15 = 966;
      goto LABEL_39;
    }
    v14 = StringCchCatExW(pszDest, v32, L"DB=", &pszDest, &v32, 0x1800u);
    if ( v14 < 0 )
    {
      v15 = 973;
      goto LABEL_39;
    }
    v14 = StringCchCatExW(pszDest, v32, v8, &pszDest, &v32, 0x1800u);
    if ( v14 < 0 )
    {
      v15 = 980;
      goto LABEL_39;
    }
  }
  v14 = 0;
LABEL_41:
  if ( v8 )
    CoTaskMemFree(v8);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14003689c  mov     [rsp-8+arg_0], rbx
0x1400368a1  push    rbp
0x1400368a2  push    rsi
0x1400368a3  push    rdi
0x1400368a4  push    r12
0x1400368a6  push    r13
0x1400368a8  push    r14
0x1400368aa  push    r15
0x1400368ac  lea     rbp, [rsp-1Fh]
0x1400368b1  sub     rsp, 0F0h
0x1400368b8  mov     rax, cs:__security_cookie
0x1400368bf  xor     rax, rsp
0x1400368c2  mov     [rbp+4Fh+var_40], rax
0x1400368c6  mov     rdi, r9
0x1400368c9  mov     r12, r8
0x1400368cc  mov     r15, rdx
0x1400368cf  mov     [rsp+120h+pszDest], rdx
0x1400368d4  mov     [rbp+4Fh+var_C8], r8
0x1400368d8  mov     rsi, [rbp+4Fh+arg_20]
0x1400368dc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_QMRForAutopatchManaged_56753991@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_QMRForAutopatchManaged_56753991@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_QMRForAutopatchManaged_56753991> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_QMRForAutopatchManaged_56753991>::GetImpl(void)'::`2'::impl
0x1400368e3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_QMRForAutopatchManaged_56753991@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_QMRForAutopatchManaged_56753991>::__private_IsEnabled(void)
0x1400368e8  xor     r13d, r13d
0x1400368eb  test    al, al
0x1400368ed  jnz     short loc_140036922
0x1400368ef  mov     rcx, [rbp+57h]; this
0x1400368f3  lea     rax, aFeatureContain; "Feature_Containment_UUS_QMRForAutopatch"...
0x1400368fa  mov     [rsp+120h+var_F8], rax; char *
0x1400368ff  lea     rax, aFeatureHsIsNot; "Feature %hs is not enabled"
0x140036906  mov     [rsp+120h+var_100], rax; int
0x14003690b  mov     r9d, 80240067h; char *
0x140036911  lea     r8, aCW1SSrcClientE_0; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x140036918  mov     edx, 3A0h; void *
0x14003691d  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x140036922  mov     rbx, r13
0x140036925  mov     [rsp+120h+var_E0], rbx
0x14003692a  mov     [rdi], r15
0x14003692d  mov     [rsi], r12
0x140036930  mov     rdi, r13
0x140036933  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x140036938  mov     r14d, 40h ; '@'
0x14003693e  test    eax, eax
0x140036940  jz      short loc_1400369BD
0x140036942  call    ?SafeSusComAllocArray@@YAPEAX_K0@Z; SafeSusComAllocArray(unsigned __int64,unsigned __int64)
0x140036947  mov     rbx, rax
0x14003694a  mov     [rsp+120h+var_E0], rax
0x14003694f  neg     rax
0x140036952  sbb     esi, esi
0x140036954  not     esi
0x140036956  and     esi, 8007000Eh
0x14003695c  test    rbx, rbx
0x14003695f  jnz     short loc_14003696B
0x140036961  mov     edx, 3AAh
0x140036966  jmp     loc_140036BD2
0x14003696b  mov     rdi, rbx
0x14003696e  mov     dword ptr [rsp+120h+var_100], r14d
0x140036973  mov     r9, rbx
0x140036976  lea     r8, aQmrdataboundar; "QMRDataBoundaryOverride"
0x14003697d  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140036984  call    ?RegQueryStringValue@@YAJPEAUHKEY__@@PEB_W1PEA_WKW4RegistryHiveType@@@Z; RegQueryStringValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t *,ulong,RegistryHiveType)
0x140036989  test    eax, eax
0x14003698b  js      short loc_1400369B3
0x14003698d  mov     [rsp+120h+var_F0], rbx
0x140036992  lea     rax, aUsingQmrdatabo; "Using QMRDataBoundaryOverride=%ws"
0x140036999  mov     [rsp+120h+var_F8], rax
0x14003699e  mov     [rsp+120h+var_100], r13
0x1400369a3  xor     edx, edx
0x1400369a5  xor     ecx, ecx
0x1400369a7  lea     r9d, [rdx+4]
0x1400369ab  mov     r8d, r9d
0x1400369ae  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1400369b3  cmp     [rbx], r13w
0x1400369b7  jnz     loc_140036AF5
0x1400369bd  call    ?GetInQMR@QMRUtil@@YA_NXZ; QMRUtil::GetInQMR(void)
0x1400369c2  test    al, al
0x1400369c4  jz      loc_140036AF5
0x1400369ca  lea     rax, aInQmrAttemptin; "In QMR, attempting to read cached data "...
0x1400369d1  mov     [rsp+120h+var_F8], rax
0x1400369d6  mov     [rsp+120h+var_100], r13; int
0x1400369db  xor     edx, edx
0x1400369dd  xor     ecx, ecx
0x1400369df  lea     r9d, [rdx+4]
0x1400369e3  mov     r8d, r9d
0x1400369e6  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1400369eb  test    rdi, rdi
0x1400369ee  jz      short loc_1400369F9
0x1400369f0  mov     rcx, rbx; pv
0x1400369f3  call    cs:__imp_CoTaskMemFree
0x1400369f9  mov     rbx, r13
0x1400369fc  mov     [rsp+120h+var_E0], rbx
0x140036a01  mov     [rsp+120h+lpMem], r13
0x140036a06  lea     rcx, [rsp+120h+lpMem]; wchar_t **
0x140036a0b  call    ?GetDataBoundaryCacheRegPath@@YAJPEAPEA_W@Z; GetDataBoundaryCacheRegPath(wchar_t * *)
0x140036a10  mov     esi, eax
0x140036a12  test    eax, eax
0x140036a14  jns     short loc_140036A3B
0x140036a16  mov     rcx, [rbp+57h]; this
0x140036a1a  mov     r9d, eax; char *
0x140036a1d  lea     r8, aCW1SSrcClientE_4; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x140036a24  mov     edx, 92h; void *
0x140036a29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140036a2e  nop
0x140036a2f  mov     rcx, [rsp+120h+lpMem]
0x140036a34  test    rcx, rcx
0x140036a37  jz      short loc_140036AB4
0x140036a39  jmp     short loc_140036AAF
0x140036a3b  mov     dword ptr [rsp+120h+var_100], r14d; int
0x140036a40  lea     r9, [rbp+4Fh+var_C0]
0x140036a44  lea     r8, ?c_szRegSLSDataBoundaryCacheDataBoundary@@3QB_WB; "DeviceDataBoundary"
0x140036a4b  mov     rdi, [rsp+120h+lpMem]
0x140036a50  mov     rdx, rdi
0x140036a53  call    ?RegQueryStringValue@@YAJPEAUHKEY__@@PEB_W1PEA_WKW4RegistryHiveType@@@Z; RegQueryStringValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t *,ulong,RegistryHiveType)
0x140036a58  mov     esi, eax
0x140036a5a  test    eax, eax
0x140036a5c  jns     short loc_140036A68
0x140036a5e  mov     r9d, eax
0x140036a61  mov     edx, 99h
0x140036a66  jmp     short loc_140036A96
0x140036a68  mov     [rsp+120h+var_E0], r13
0x140036a6d  or      r8, 0FFFFFFFFFFFFFFFFh
0x140036a71  lea     rdx, [rbp+4Fh+var_C0]
0x140036a75  lea     rcx, [rsp+120h+var_E0]
0x140036a7a  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x140036a7f  mov     rax, [rsp+120h+var_E0]
0x140036a84  test    rax, rax
0x140036a87  jnz     short loc_140036ABE
0x140036a89  mov     esi, 8007000Eh
0x140036a8e  mov     r9d, esi; char *
0x140036a91  mov     edx, 9Ch; void *
0x140036a96  lea     r8, aCW1SSrcClientE_4; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x140036a9d  mov     rcx, [rbp+57h]; this
0x140036aa1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140036aa6  nop
0x140036aa7  test    rdi, rdi
0x140036aaa  jz      short loc_140036AB4
0x140036aac  mov     rcx, rdi; lpMem
0x140036aaf  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140036ab4  mov     edx, 3B9h
0x140036ab9  jmp     loc_140036BD2
0x140036abe  mov     rbx, rax
0x140036ac1  test    rdi, rdi
0x140036ac4  jz      short loc_140036ACE
0x140036ac6  mov     rcx, rdi; lpMem
0x140036ac9  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140036ace  mov     [rsp+120h+var_F0], rbx
0x140036ad3  lea     rax, aCachedDataboun; "Cached DataBoundary found: %ws"
0x140036ada  mov     [rsp+120h+var_F8], rax
0x140036adf  mov     [rsp+120h+var_100], r13
0x140036ae4  xor     edx, edx
0x140036ae6  xor     ecx, ecx
0x140036ae8  lea     r9d, [rdx+5]
0x140036aec  lea     r8d, [rdx+4]
0x140036af0  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140036af5  test    rbx, rbx
0x140036af8  jz      loc_140036BE7
0x140036afe  cmp     [rbx], r13w
0x140036b02  jz      loc_140036BE7
0x140036b08  mov     rax, rbx
0x140036b0b  cmp     [rax], r13w
0x140036b0f  jz      short loc_140036B1B
0x140036b11  add     rax, 2
0x140036b15  sub     r14, 1
0x140036b19  jnz     short loc_140036B0B
0x140036b1b  mov     rax, r14
0x140036b1e  neg     rax
0x140036b21  sbb     esi, esi
0x140036b23  not     esi
0x140036b25  and     esi, 80070057h
0x140036b2b  test    r14, r14
0x140036b2e  jnz     short loc_140036B3A
0x140036b30  mov     edx, 3BFh
0x140036b35  jmp     loc_140036BD2
0x140036b3a  mov     edi, 1800h
0x140036b3f  mov     dword ptr [rsp+120h+var_F8], edi; unsigned int
0x140036b43  lea     rax, [rbp+4Fh+var_C8]
0x140036b47  mov     [rsp+120h+var_100], rax; unsigned __int64 *
0x140036b4c  lea     r9, [rsp+120h+pszDest]; wchar_t **
0x140036b51  lea     r8, asc_14006C8E0; "&"
0x140036b58  mov     rdx, r12; unsigned __int64
0x140036b5b  mov     rcx, r15; pszDest
0x140036b5e  call    ?StringCchCatExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCatExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x140036b63  mov     esi, eax
0x140036b65  test    eax, eax
0x140036b67  jns     short loc_140036B70
0x140036b69  mov     edx, 3C6h
0x140036b6e  jmp     short loc_140036BD2
0x140036b70  mov     dword ptr [rsp+120h+var_F8], edi; unsigned int
0x140036b74  lea     rax, [rbp+4Fh+var_C8]
0x140036b78  mov     [rsp+120h+var_100], rax; unsigned __int64 *
0x140036b7d  lea     r9, [rsp+120h+pszDest]; wchar_t **
0x140036b82  lea     r8, aDb; "DB="
0x140036b89  mov     rdx, [rbp+4Fh+var_C8]; unsigned __int64
0x140036b8d  mov     rcx, [rsp+120h+pszDest]; pszDest
0x140036b92  call    ?StringCchCatExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCatExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x140036b97  mov     esi, eax
0x140036b99  test    eax, eax
0x140036b9b  jns     short loc_140036BA4
0x140036b9d  mov     edx, 3CDh
0x140036ba2  jmp     short loc_140036BD2
0x140036ba4  mov     dword ptr [rsp+120h+var_F8], edi; unsigned int
0x140036ba8  lea     rax, [rbp+4Fh+var_C8]
0x140036bac  mov     [rsp+120h+var_100], rax; int
0x140036bb1  lea     r9, [rsp+120h+pszDest]; wchar_t **
0x140036bb6  mov     r8, rbx; wchar_t *
0x140036bb9  mov     rdx, [rbp+4Fh+var_C8]; unsigned __int64
0x140036bbd  mov     rcx, [rsp+120h+pszDest]; pszDest
0x140036bc2  call    ?StringCchCatExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCatExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x140036bc7  mov     esi, eax
0x140036bc9  test    eax, eax
0x140036bcb  jns     short loc_140036BE7
0x140036bcd  mov     edx, 3D4h; void *
0x140036bd2  mov     rcx, [rbp+57h]; this
0x140036bd6  mov     r9d, esi; char *
0x140036bd9  lea     r8, aCW1SSrcClientE_0; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x140036be0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140036be5  jmp     short loc_140036BEA
0x140036be7  mov     esi, r13d
0x140036bea  test    rbx, rbx
0x140036bed  jz      short loc_140036BF8
0x140036bef  mov     rcx, rbx; pv
0x140036bf2  call    cs:__imp_CoTaskMemFree
0x140036bf8  mov     eax, esi
0x140036bfa  mov     rcx, [rbp+4Fh+var_40]
0x140036bfe  xor     rcx, rsp; StackCookie
0x140036c01  call    __security_check_cookie
0x140036c06  mov     rbx, [rsp+120h+arg_0]
0x140036c0e  add     rsp, 0F0h
0x140036c15  pop     r15
0x140036c17  pop     r14
0x140036c19  pop     r13
0x140036c1b  pop     r12
0x140036c1d  pop     rdi
0x140036c1e  pop     rsi
0x140036c1f  pop     rbp
0x140036c20  retn
```
