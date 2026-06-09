# MakeAlternateIdUri(AppId *,ushort const *,ushort const *,TraceLoggingCorrelationVector *,Windows::Foundation::IUriRuntimeClass * *)

- ea: `0x180082c10`
- end: `0x180082ec9`
- name: `?MakeAlternateIdUri@@YAJPEAVAppId@@PEBG1PEAVTraceLoggingCorrelationVector@@PEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z`
- size: `697`
- prototype: `int(struct AppId *, const unsigned __int16 *, const unsigned __int16 *, struct TraceLoggingCorrelationVector *, struct Windows::Foundation::IUriRuntimeClass **)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180082258`

## callees

- `0x180009ea0`
- `0x18000ad30`
- `0x1800101f4`
- `0x18001c414`
- `0x180077c44`
- `0x180081834`
- `0x180082af0`
- `0x180082c10`
- `0x1800ffe38`
- `0x180100014`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082d51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082d5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082e94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082e9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082d51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082d5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082e94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082e9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180082ce3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180082d93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180082dc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180082de5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180082e04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180082ce3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180082d93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180082dc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180082de5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180082e04`

## string_xrefs

- `0x180082ca6`: `onecoreuap\enduser\winstore\installservice\lib\storeappinfo.cpp`
- `0x180082e0e`: `fieldsTemplate`
- `0x180082c99`: `MakeAlternateIdUri`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MakeAlternateIdUri(
        HSTRING *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct TraceLoggingCorrelationVector *a4,
        struct Windows::Foundation::IUriRuntimeClass **a5)
{
  __int64 v7; // r13
  unsigned __int64 v8; // rbx
  unsigned __int16 *p_pszDest; // rdi
  PCWSTR StringRawBuffer; // rax
  int ExclusivityIds; // esi
  HSTRING v12; // rbx
  HSTRING v13; // rdi
  struct Windows::Foundation::IUriRuntimeClass *v14; // rax
  HSTRING string; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING v17; // [rsp+58h] [rbp-A8h] BYREF
  struct Windows::Foundation::IUriRuntimeClass *v18; // [rsp+60h] [rbp-A0h] BYREF
  const unsigned __int16 *v19; // [rsp+68h] [rbp-98h]
  struct TraceLoggingCorrelationVector *v20; // [rsp+70h] [rbp-90h]
  _QWORD v21[12]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t pszDest; // [rsp+E0h] [rbp-20h] BYREF
  char v23[2046]; // [rsp+E2h] [rbp-1Eh] BYREF

  v20 = a4;
  v19 = a3;
  *a5 = 0;
  v7 = *((int *)a1 + 14);
  if ( (unsigned int)v7 > 6 )
    LogMessage(
      1u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\storeappinfo.cpp",
      0x304u,
      "MakeAlternateIdUri",
      -1,
      L"Assert (%s): %s",
      0,
      0,
      L"idType >= AppId::Type_ProductId && idType <= AppId::Type_CategoryId",
      L"Failed");
  pszDest = 0;
  memset_0(v23, 0, sizeof(v23));
  v8 = 1024;
  v17 = (HSTRING)1024;
  p_pszDest = &pszDest;
  string = (HSTRING)&pszDest;
  StringRawBuffer = WindowsGetStringRawBuffer(a1[10], 0);
  if ( StringRawBuffer && *StringRawBuffer )
  {
    ExclusivityIds = StringCchPrintfExW(
                       &pszDest,
                       0x400u,
                       (unsigned __int16 **)&string,
                       (unsigned __int64 *)&v17,
                       0,
                       L"&catalogId=%s",
                       StringRawBuffer);
    if ( ExclusivityIds < 0 )
      goto LABEL_8;
    v8 = (unsigned __int64)v17;
    p_pszDest = (unsigned __int16 *)string;
  }
  ExclusivityIds = GetExclusivityIds(p_pszDest, v8, a2);
LABEL_8:
  v12 = 0;
  v13 = 0;
  if ( ExclusivityIds >= 0 )
  {
    WindowsDeleteString(0);
    v17 = 0;
    WindowsDeleteString(0);
    string = 0;
    ExclusivityIds = GetLanguageAndRegion(&string, &v17);
    if ( ExclusivityIds < 0 )
    {
      v12 = string;
      v13 = v17;
    }
    else
    {
      v21[0] = L"productId";
      v21[1] = WindowsGetStringRawBuffer(a1[8], 0);
      v21[2] = L"idType";
      v21[3] = AppId::IdTypeName(*((unsigned int *)a1 + 14));
      v21[4] = L"skuId";
      v21[5] = WindowsGetStringRawBuffer(a1[9], 0);
      v21[6] = L"language";
      v12 = string;
      v21[7] = WindowsGetStringRawBuffer(string, 0);
      v21[8] = L"marketCode";
      v13 = v17;
      v21[9] = WindowsGetStringRawBuffer(v17, 0);
      v21[10] = L"fieldsTemplate";
      v21[11] = v19;
      v18 = 0;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v18);
      ExclusivityIds = GetSLSUri(LODWORD(qword_180227F78[2 * v7]), v21, 6);
      if ( ExclusivityIds >= 0 )
      {
        v14 = v18;
        v18 = 0;
        *a5 = v14;
      }
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v18);
    }
  }
  WindowsDeleteString(v13);
  WindowsDeleteString(v12);
  return (unsigned int)ExclusivityIds;
}

```

## disassembly

```asm
0x180082c10  push    rbp
0x180082c12  push    rbx
0x180082c13  push    rsi
0x180082c14  push    rdi
0x180082c15  push    r12
0x180082c17  push    r13
0x180082c19  push    r14
0x180082c1b  push    r15
0x180082c1d  lea     rbp, [rsp-7F8h]
0x180082c25  sub     rsp, 8F8h
0x180082c2c  mov     rax, cs:__security_cookie
0x180082c33  xor     rax, rsp
0x180082c36  mov     [rbp+830h+var_50], rax
0x180082c3d  mov     [rsp+930h+var_8C0], r9
0x180082c42  mov     [rsp+930h+var_8C8], r8
0x180082c47  mov     r12, rdx
0x180082c4a  mov     r14, rcx
0x180082c4d  mov     r15, [rbp+830h+arg_20]
0x180082c54  xor     esi, esi
0x180082c56  mov     [r15], rsi
0x180082c59  movsxd  r13, dword ptr [rcx+38h]
0x180082c5d  cmp     r13d, 6
0x180082c61  jbe     short loc_180082CB5
0x180082c63  lea     rax, aFailed_1; "Failed"
0x180082c6a  mov     [rsp+930h+var_8E8], rax
0x180082c6f  lea     rax, aIdtypeAppidTyp; "idType >= AppId::Type_ProductId && idTy"...
0x180082c76  mov     [rsp+930h+var_8F0], rax
0x180082c7b  mov     [rsp+930h+var_8F8], rsi; unsigned __int16 *
0x180082c80  mov     [rsp+930h+var_900], rsi; char *
0x180082c85  lea     rax, aAssertSS; "Assert (%s): %s"
0x180082c8c  mov     [rsp+930h+var_908], rax; unsigned __int16 *
0x180082c91  mov     [rsp+930h+var_910], 0FFFFFFFFh; int
0x180082c99  lea     r9, aMakealternatei; "MakeAlternateIdUri"
0x180082ca0  mov     r8d, 304h; unsigned int
0x180082ca6  lea     rdx, aOnecoreuapEndu_88; "onecoreuap\\enduser\\winstore\\installs"...
0x180082cad  lea     ecx, [rsi+1]; unsigned int
0x180082cb0  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x180082cb5  mov     [rbp+830h+pszDest], si
0x180082cb9  xor     edx, edx; Val
0x180082cbb  mov     r8d, 7FEh; Size
0x180082cc1  lea     rcx, [rbp+830h+var_84E]; void *
0x180082cc5  call    memset_0
0x180082cca  mov     ebx, 400h
0x180082ccf  mov     [rsp+930h+var_8D8], rbx
0x180082cd4  lea     rdi, [rbp+830h+pszDest]
0x180082cd8  mov     [rsp+930h+string], rdi
0x180082cdd  xor     edx, edx; length
0x180082cdf  mov     rcx, [r14+50h]; string
0x180082ce3  call    cs:__imp_WindowsGetStringRawBuffer
0x180082ce9  test    rax, rax
0x180082cec  jz      short loc_180082D2E
0x180082cee  cmp     [rax], si
0x180082cf1  jz      short loc_180082D2E
0x180082cf3  mov     [rsp+930h+var_900], rax
0x180082cf8  lea     rax, aCatalogidS; "&catalogId=%s"
0x180082cff  mov     [rsp+930h+var_908], rax; unsigned __int16 *
0x180082d04  mov     qword ptr [rsp+930h+var_910], rsi; unsigned int
0x180082d09  lea     r9, [rsp+930h+var_8D8]; unsigned __int64 *
0x180082d0e  lea     r8, [rsp+930h+string]; unsigned __int16 **
0x180082d13  mov     edx, ebx; unsigned __int64
0x180082d15  lea     rcx, [rbp+830h+pszDest]; pszDest
0x180082d19  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180082d1e  mov     esi, eax
0x180082d20  test    eax, eax
0x180082d22  js      short loc_180082D3E
0x180082d24  mov     rbx, [rsp+930h+var_8D8]
0x180082d29  mov     rdi, [rsp+930h+string]
0x180082d2e  mov     r8, r12; unsigned __int16 *
0x180082d31  mov     rdx, rbx; unsigned __int64
0x180082d34  mov     rcx, rdi; unsigned __int16 *
0x180082d37  call    ?GetExclusivityIds@@YAJPEAG_KPEBG@Z; GetExclusivityIds(ushort *,unsigned __int64,ushort const *)
0x180082d3c  mov     esi, eax
0x180082d3e  xor     r12d, r12d
0x180082d41  mov     ebx, r12d
0x180082d44  mov     edi, r12d
0x180082d47  test    esi, esi
0x180082d49  js      loc_180082E91
0x180082d4f  xor     ecx, ecx; string
0x180082d51  call    cs:__imp_WindowsDeleteString
0x180082d57  mov     [rsp+930h+var_8D8], r12
0x180082d5c  xor     ecx, ecx; string
0x180082d5e  call    cs:__imp_WindowsDeleteString
0x180082d64  mov     [rsp+930h+string], r12
0x180082d69  lea     rdx, [rsp+930h+var_8D8]; HSTRING *
0x180082d6e  lea     rcx, [rsp+930h+string]; HSTRING *
0x180082d73  call    ?GetLanguageAndRegion@@YAJPEAPEAUHSTRING__@@0@Z; GetLanguageAndRegion(HSTRING__ * *,HSTRING__ * *)
0x180082d78  mov     esi, eax
0x180082d7a  test    eax, eax
0x180082d7c  js      loc_180082E87
0x180082d82  lea     rax, aProductid_1; "productId"
0x180082d89  mov     [rbp+830h+var_8B0], rax
0x180082d8d  xor     edx, edx; length
0x180082d8f  mov     rcx, [r14+40h]; string
0x180082d93  call    cs:__imp_WindowsGetStringRawBuffer
0x180082d99  mov     [rbp+830h+var_8A8], rax
0x180082d9d  lea     rax, aIdtype; "idType"
0x180082da4  mov     [rbp+830h+var_8A0], rax
0x180082da8  mov     ecx, [r14+38h]
0x180082dac  call    ?IdTypeName@AppId@@SAPEBGW4Type@1@@Z; AppId::IdTypeName(AppId::Type)
0x180082db1  mov     [rbp+830h+var_898], rax
0x180082db5  lea     rax, aSkuid_2; "skuId"
0x180082dbc  mov     [rbp+830h+var_890], rax
0x180082dc0  xor     edx, edx; length
0x180082dc2  mov     rcx, [r14+48h]; string
0x180082dc6  call    cs:__imp_WindowsGetStringRawBuffer
0x180082dcc  mov     [rbp+830h+var_888], rax
0x180082dd0  lea     rax, aLanguage; "language"
0x180082dd7  mov     [rbp+830h+var_880], rax
0x180082ddb  xor     edx, edx; length
0x180082ddd  mov     rbx, [rsp+930h+string]
0x180082de2  mov     rcx, rbx; string
0x180082de5  call    cs:__imp_WindowsGetStringRawBuffer
0x180082deb  mov     [rbp+830h+var_878], rax
0x180082def  lea     rax, aMarketcode; "marketCode"
0x180082df6  mov     [rbp+830h+var_870], rax
0x180082dfa  xor     edx, edx; length
0x180082dfc  mov     rdi, [rsp+930h+var_8D8]
0x180082e01  mov     rcx, rdi; string
0x180082e04  call    cs:__imp_WindowsGetStringRawBuffer
0x180082e0a  mov     [rbp+830h+var_868], rax
0x180082e0e  lea     rax, aFieldstemplate; "fieldsTemplate"
0x180082e15  mov     [rbp+830h+var_860], rax
0x180082e19  mov     rax, [rsp+930h+var_8C8]
0x180082e1e  mov     [rbp+830h+var_858], rax
0x180082e22  mov     [rsp+930h+var_8D0], r12
0x180082e27  lea     rcx, [rsp+930h+var_8D0]
0x180082e2c  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180082e31  mov     rcx, r13
0x180082e34  add     rcx, rcx
0x180082e37  lea     r10, qword_180227F78
0x180082e3e  lea     rax, [rsp+930h+var_8D0]
0x180082e43  mov     [rsp+930h+var_908], rax
0x180082e48  mov     rax, [rsp+930h+var_8C0]
0x180082e4d  mov     qword ptr [rsp+930h+var_910], rax
0x180082e52  lea     r9, [rbp+830h+pszDest]
0x180082e56  lea     r8d, [r12+6]
0x180082e5b  lea     rdx, [rbp+830h+var_8B0]
0x180082e5f  mov     ecx, [r10+rcx*8]
0x180082e63  call    ?GetSLSUri@@YAJW4SLSIndex@@PEBUANNOTATION_VALUE@@_KPEBGPEAVTraceLoggingCorrelationVector@@PEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z; GetSLSUri(SLSIndex,ANNOTATION_VALUE const *,unsigned __int64,ushort const *,TraceLoggingCorrelationVector *,Windows::Foundation::IUriRuntimeClass * *)
0x180082e68  mov     esi, eax
0x180082e6a  test    eax, eax
0x180082e6c  js      short loc_180082E7B
0x180082e6e  mov     rax, [rsp+930h+var_8D0]
0x180082e73  mov     [rsp+930h+var_8D0], r12
0x180082e78  mov     [r15], rax
0x180082e7b  lea     rcx, [rsp+930h+var_8D0]
0x180082e80  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180082e85  jmp     short loc_180082E91
0x180082e87  mov     rbx, [rsp+930h+string]
0x180082e8c  mov     rdi, [rsp+930h+var_8D8]
0x180082e91  mov     rcx, rdi; string
0x180082e94  call    cs:__imp_WindowsDeleteString
0x180082e9a  nop
0x180082e9b  mov     rcx, rbx; string
0x180082e9e  call    cs:__imp_WindowsDeleteString
0x180082ea4  mov     eax, esi
0x180082ea6  mov     rcx, [rbp+830h+var_50]
0x180082ead  xor     rcx, rsp; StackCookie
0x180082eb0  call    __security_check_cookie
0x180082eb5  add     rsp, 8F8h
0x180082ebc  pop     r15
0x180082ebe  pop     r14
0x180082ec0  pop     r13
0x180082ec2  pop     r12
0x180082ec4  pop     rdi
0x180082ec5  pop     rsi
0x180082ec6  pop     rbx
0x180082ec7  pop     rbp
0x180082ec8  retn
```
