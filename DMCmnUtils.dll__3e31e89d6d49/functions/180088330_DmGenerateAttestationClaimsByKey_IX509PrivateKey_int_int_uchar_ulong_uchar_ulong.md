# DmGenerateAttestationClaimsByKey(IX509PrivateKey *,int,int,uchar * *,ulong *,uchar * *,ulong *)

- ea: `0x180088330`
- end: `0x1800887bf`
- name: `?DmGenerateAttestationClaimsByKey@@YAJPEAUIX509PrivateKey@@HHPEAPEAEPEAK12@Z`
- size: `1167`
- prototype: `__int64 __fastcall(struct IX509PrivateKey *, int, int, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180053c78`
- `0x18005427c`
- `0x180057c6c`
- `0x180062704`
- `0x180062728`
- `0x18008572c`
- `0x180088330`
- `0x18008b33c`
- `0x1800940b0`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800885af`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800886ae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800885af`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800886ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180088594`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180088699`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180088594`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180088699`
- `OLEAUT32!__imp_SysFreeString` at `0x18008844f`
- `OLEAUT32!__imp_SysFreeString` at `0x18008844f`
- `ncrypt!NCryptCreateClaim` at `0x180088573`
- `ncrypt!NCryptCreateClaim` at `0x180088619`
- `ncrypt!NCryptCreateClaim` at `0x180088573`
- `ncrypt!NCryptCreateClaim` at `0x180088619`
- `ncrypt!NCryptExportKey` at `0x18008866a`
- `ncrypt!NCryptExportKey` at `0x180088712`
- `ncrypt!NCryptExportKey` at `0x18008866a`
- `ncrypt!NCryptExportKey` at `0x180088712`
- `ncrypt!NCryptFreeObject` at `0x1800884a2`
- `ncrypt!NCryptFreeObject` at `0x1800884fc`
- `ncrypt!NCryptFreeObject` at `0x1800884a2`
- `ncrypt!NCryptFreeObject` at `0x1800884fc`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800884c5`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800884c5`
- `ncrypt!NCryptOpenKey` at `0x180088528`
- `ncrypt!NCryptOpenKey` at `0x180088528`

## string_xrefs

- `0x1800884d7`: `GenerateAttestationClaims: NCryptOpenStorageProvider`
- `0x180088585`: `NCryptCreateClaim(size)`
- `0x18008853a`: `GenerateAttestationClaims: NCryptOpenKey(dmKey)`
- `0x18008862b`: `GenerateAttestationClaims: NCryptCreateClaim`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall DmGenerateAttestationClaimsByKey(
        struct IX509PrivateKey *a1,
        int a2,
        int a3,
        unsigned __int8 **a4,
        unsigned int *a5,
        unsigned __int8 **a6,
        unsigned int *a7)
{
  DWORD dwFlags; // r14d
  SECURITY_STATUS WindowsAIKKeyFromProviderInternal; // ebx
  const wchar_t *v11; // rdx
  HRESULT (__stdcall *get_ContainerName)(IX509PrivateKey *, BSTR *); // rsi
  const WCHAR *v14; // rdi
  NCRYPT_HANDLE v15; // rbx
  NCRYPT_KEY_HANDLE v16; // rbx
  SECURITY_STATUS Claim; // eax
  unsigned int v18; // edi
  const wchar_t *v19; // rdx
  unsigned int v20; // edi
  HANDLE ProcessHeap; // rax
  LPVOID v22; // rax
  unsigned __int8 *v23; // r15
  SECURITY_STATUS v24; // eax
  unsigned int v25; // esi
  DWORD v26; // edi
  HANDLE v27; // rax
  LPVOID v28; // rax
  unsigned __int8 *v29; // r14
  NCRYPT_HANDLE phKey; // [rsp+40h] [rbp-41h] BYREF
  int *v31; // [rsp+48h] [rbp-39h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-31h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+58h] [rbp-29h] BYREF
  unsigned __int8 *v34; // [rsp+60h] [rbp-21h] BYREF
  PBYTE pbOutput; // [rsp+68h] [rbp-19h] BYREF
  LPCWSTR pszProviderName; // [rsp+70h] [rbp-11h] BYREF
  NCRYPT_KEY_HANDLE hKey; // [rsp+78h] [rbp-9h] BYREF
  _BYTE v38[64]; // [rsp+80h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+47h]
  DWORD pcbResult; // [rsp+D0h] [rbp+4Fh] BYREF
  SIZE_T dwBytes; // [rsp+D8h] [rbp+57h]
  int v42; // [rsp+E0h] [rbp+5Fh] BYREF

  v42 = a3;
  hObject = 0;
  phKey = 0;
  hKey = 0;
  bstrString = 0;
  pbOutput = 0;
  v34 = 0;
  pcbResult = 0;
  LODWORD(dwBytes) = 0;
  dwFlags = a2 != 0 ? 96 : 64;
  v31 = &v42;
  pszProviderName = 0;
  WindowsAIKKeyFromProviderInternal = ((__int64 (__fastcall *)(struct IX509PrivateKey *, LPCWSTR *))a1->lpVtbl->get_ProviderName)(
                                        a1,
                                        &pszProviderName);
  if ( WindowsAIKKeyFromProviderInternal < 0 )
  {
    v11 = L"GenerateAttestationClaims: key->get_ProviderName";
LABEL_3:
    lambda_a34be7e6fffcc5ac521306cfbd109a62_::operator()(&v31, v11, (unsigned int)WindowsAIKKeyFromProviderInternal);
    wistd::unique_ptr<unsigned char,wil::process_heap_deleter>::reset(&v34, 0);
    wistd::unique_ptr<unsigned char,wil::process_heap_deleter>::reset(&pbOutput, 0);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszProviderName);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&bstrString);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hKey);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
    return (unsigned int)WindowsAIKKeyFromProviderInternal;
  }
  hKey = 0;
  WindowsAIKKeyFromProviderInternal = DmGetWindowsAIKKeyFromProviderInternal((wchar_t *)pszProviderName, v42, &hKey);
  if ( WindowsAIKKeyFromProviderInternal < 0 )
  {
    v11 = L"GenerateAttestationClaims: DmGetWindowsAIKKeyFromProviderInternal";
    goto LABEL_3;
  }
  get_ContainerName = a1->lpVtbl->get_ContainerName;
  bstrString = 0;
  WindowsAIKKeyFromProviderInternal = ((__int64 (__fastcall *)(struct IX509PrivateKey *, BSTR *))get_ContainerName)(
                                        a1,
                                        &bstrString);
  if ( WindowsAIKKeyFromProviderInternal < 0 )
  {
    v11 = L"GenerateAttestationClaims: key->get_ContainerName";
    goto LABEL_3;
  }
  v14 = pszProviderName;
  v15 = hObject;
  if ( hObject )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v38);
    NCryptFreeObject(v15);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v38);
  }
  hObject = 0;
  WindowsAIKKeyFromProviderInternal = NCryptOpenStorageProvider(&hObject, v14, 0);
  if ( WindowsAIKKeyFromProviderInternal < 0 )
  {
    v11 = L"GenerateAttestationClaims: NCryptOpenStorageProvider";
    goto LABEL_3;
  }
  phKey = 0;
  WindowsAIKKeyFromProviderInternal = NCryptOpenKey(hObject, &phKey, bstrString, 0, dwFlags);
  if ( WindowsAIKKeyFromProviderInternal < 0 )
  {
    v11 = L"GenerateAttestationClaims: NCryptOpenKey(dmKey)";
    goto LABEL_3;
  }
  v16 = hKey;
  Claim = NCryptCreateClaim(phKey, hKey, 2);
  v18 = Claim;
  if ( Claim < 0 )
  {
    v19 = L"NCryptCreateClaim(size)";
LABEL_20:
    lambda_a34be7e6fffcc5ac521306cfbd109a62_::operator()(&v31, v19, (unsigned int)Claim);
    goto LABEL_28;
  }
  v20 = dwBytes;
  ProcessHeap = GetProcessHeap();
  v22 = HeapAlloc(ProcessHeap, 8u, v20);
  wistd::unique_ptr<unsigned char,wil::process_heap_deleter>::reset(&v34, v22);
  v23 = v34;
  if ( v34 )
  {
    Claim = NCryptCreateClaim(phKey, v16, 2);
    v18 = Claim;
    if ( Claim >= 0 )
    {
      v24 = NCryptExportKey(v16, 0, L"RSAPUBLICBLOB", 0, 0, 0, &pcbResult, 0);
      v25 = v24;
      if ( v24 < 0 )
      {
        lambda_a34be7e6fffcc5ac521306cfbd109a62_::operator()(
          &v31,
          L"GenerateAttestationClaims: NCryptExportKey(hAIK size)",
          (unsigned int)v24);
        v18 = v25;
        goto LABEL_28;
      }
      v26 = pcbResult;
      v27 = GetProcessHeap();
      v28 = HeapAlloc(v27, 8u, v26);
      wistd::unique_ptr<unsigned char,wil::process_heap_deleter>::reset(&pbOutput, v28);
      v29 = pbOutput;
      if ( !pbOutput )
      {
        lambda_a34be7e6fffcc5ac521306cfbd109a62_::operator()(&v31, L"NCryptExportKey(hAIK size allocation)", v25);
        v18 = -2147024882;
        goto LABEL_28;
      }
      Claim = NCryptExportKey(v16, 0, L"RSAPUBLICBLOB", 0, pbOutput, pcbResult, &pcbResult, 0);
      v18 = Claim;
      if ( Claim >= 0 )
      {
        v34 = 0;
        *a4 = v23;
        *a5 = dwBytes;
        pbOutput = 0;
        *a6 = v29;
        *a7 = pcbResult;
        v18 = 0;
        goto LABEL_28;
      }
      v19 = L"GenerateAttestationClaims: NCryptExportKey(hAIK)";
    }
    else
    {
      v19 = L"GenerateAttestationClaims: NCryptCreateClaim";
    }
    goto LABEL_20;
  }
  v18 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x303,
    (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\attestationutils\\attestationutils.cpp",
    (const char *)0x8007000ELL,
    0);
LABEL_28:
  wistd::unique_ptr<unsigned char,wil::process_heap_deleter>::reset(&v34, 0);
  wistd::unique_ptr<unsigned char,wil::process_heap_deleter>::reset(&pbOutput, 0);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszProviderName);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&bstrString);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
  return v18;
}

```

## disassembly

```asm
0x180088330  mov     [rsp-8+arg_18], rbx
0x180088335  mov     [rsp-8+arg_10], r8d
0x18008833a  push    rbp
0x18008833b  push    rsi
0x18008833c  push    rdi
0x18008833d  push    r12
0x18008833f  push    r13
0x180088341  push    r14
0x180088343  push    r15
0x180088345  lea     rbp, [rsp-0Fh]
0x18008834a  sub     rsp, 90h
0x180088351  mov     r12, r9
0x180088354  mov     rdi, rcx
0x180088357  xor     r13d, r13d
0x18008835a  mov     [rbp+3Fh+hObject], r13
0x18008835e  mov     [rbp+3Fh+phKey], r13
0x180088362  mov     [rbp+3Fh+hKey], r13
0x180088366  mov     [rbp+3Fh+bstrString], r13
0x18008836a  mov     [rbp+3Fh+pbOutput], r13
0x18008836e  mov     [rbp+3Fh+var_60], r13
0x180088372  mov     [rbp+3Fh+arg_0], r13d
0x180088376  mov     dword ptr [rbp+3Fh+dwBytes], r13d
0x18008837a  neg     edx
0x18008837c  sbb     r14d, r14d
0x18008837f  and     r14d, 20h
0x180088383  add     r14d, 40h ; '@'
0x180088387  lea     rax, [rbp+3Fh+arg_10]
0x18008838b  mov     [rbp+3Fh+var_78], rax
0x18008838f  mov     [rbp+3Fh+pszProviderName], r13
0x180088393  mov     rax, [rcx]
0x180088396  lea     rdx, [rbp+3Fh+pszProviderName]
0x18008839a  mov     rax, [rax+0C8h]
0x1800883a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800883a6  mov     ebx, eax
0x1800883a8  test    eax, eax
0x1800883aa  jns     short loc_180088410
0x1800883ac  lea     rdx, aGenerateattest_2; "GenerateAttestationClaims: key->get_Pro"...
0x1800883b3  mov     r8d, ebx
0x1800883b6  lea     rcx, [rbp+3Fh+var_78]
0x1800883ba  call    _lambda_a34be7e6fffcc5ac521306cfbd109a62___operator__
0x1800883bf  nop
0x1800883c0  xor     edx, edx
0x1800883c2  lea     rcx, [rbp+3Fh+var_60]
0x1800883c6  call    ?reset@?$unique_ptr@EUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::process_heap_deleter>::reset(uchar *)
0x1800883cb  nop
0x1800883cc  xor     edx, edx
0x1800883ce  lea     rcx, [rbp+3Fh+pbOutput]
0x1800883d2  call    ?reset@?$unique_ptr@EUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::process_heap_deleter>::reset(uchar *)
0x1800883d7  nop
0x1800883d8  lea     rcx, [rbp+3Fh+pszProviderName]
0x1800883dc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800883e1  nop
0x1800883e2  lea     rcx, [rbp+3Fh+bstrString]
0x1800883e6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800883eb  nop
0x1800883ec  lea     rcx, [rbp+3Fh+hKey]
0x1800883f0  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800883f5  nop
0x1800883f6  lea     rcx, [rbp+3Fh+phKey]
0x1800883fa  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800883ff  nop
0x180088400  lea     rcx, [rbp+3Fh+hObject]
0x180088404  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180088409  mov     eax, ebx
0x18008840b  jmp     loc_1800887A3
0x180088410  mov     [rbp+3Fh+hKey], r13
0x180088414  lea     r8, [rbp+3Fh+hKey]; unsigned __int64 *
0x180088418  mov     edx, [rbp+3Fh+arg_10]; int
0x18008841b  mov     rcx, [rbp+3Fh+pszProviderName]; String1
0x18008841f  call    ?DmGetWindowsAIKKeyFromProviderInternal@@YAJPEBGHPEA_K@Z; DmGetWindowsAIKKeyFromProviderInternal(ushort const *,int,unsigned __int64 *)
0x180088424  mov     ebx, eax
0x180088426  test    eax, eax
0x180088428  jns     short loc_180088433
0x18008842a  lea     rdx, aGenerateattest_0; "GenerateAttestationClaims: DmGetWindows"...
0x180088431  jmp     short loc_1800883B3
0x180088433  mov     rax, [rdi]
0x180088436  mov     rsi, [rax+78h]
0x18008843a  mov     rbx, [rbp+3Fh+bstrString]
0x18008843e  test    rbx, rbx
0x180088441  jz      short loc_180088464
0x180088443  lea     rcx, [rbp+3Fh+var_40]; this
0x180088447  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18008844c  mov     rcx, rbx; bstrString
0x18008844f  call    cs:__imp_SysFreeString
0x180088456  nop     dword ptr [rax+rax+00h]
0x18008845b  lea     rcx, [rbp+3Fh+var_40]; this
0x18008845f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180088464  mov     [rbp+3Fh+bstrString], r13
0x180088468  lea     rdx, [rbp+3Fh+bstrString]
0x18008846c  mov     rcx, rdi
0x18008846f  mov     rax, rsi
0x180088472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088477  mov     ebx, eax
0x180088479  test    eax, eax
0x18008847b  jns     short loc_180088489
0x18008847d  lea     rdx, aGenerateattest_1; "GenerateAttestationClaims: key->get_Con"...
0x180088484  jmp     loc_1800883B3
0x180088489  mov     rdi, [rbp+3Fh+pszProviderName]
0x18008848d  mov     rbx, [rbp+3Fh+hObject]
0x180088491  test    rbx, rbx
0x180088494  jz      short loc_1800884B7
0x180088496  lea     rcx, [rbp+3Fh+var_40]; this
0x18008849a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18008849f  mov     rcx, rbx; hObject
0x1800884a2  call    cs:__imp_NCryptFreeObject
0x1800884a9  nop     dword ptr [rax+rax+00h]
0x1800884ae  lea     rcx, [rbp+3Fh+var_40]; this
0x1800884b2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800884b7  mov     [rbp+3Fh+hObject], r13
0x1800884bb  xor     r8d, r8d; dwFlags
0x1800884be  mov     rdx, rdi; pszProviderName
0x1800884c1  lea     rcx, [rbp+3Fh+hObject]; phProvider
0x1800884c5  call    cs:__imp_NCryptOpenStorageProvider
0x1800884cc  nop     dword ptr [rax+rax+00h]
0x1800884d1  mov     ebx, eax
0x1800884d3  test    eax, eax
0x1800884d5  jns     short loc_1800884E3
0x1800884d7  lea     rdx, aGenerateattest_6; "GenerateAttestationClaims: NCryptOpenSt"...
0x1800884de  jmp     loc_1800883B3
0x1800884e3  mov     rdi, [rbp+3Fh+bstrString]
0x1800884e7  mov     rbx, [rbp+3Fh+phKey]
0x1800884eb  test    rbx, rbx
0x1800884ee  jz      short loc_180088511
0x1800884f0  lea     rcx, [rbp+3Fh+var_40]; this
0x1800884f4  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800884f9  mov     rcx, rbx; hObject
0x1800884fc  call    cs:__imp_NCryptFreeObject
0x180088503  nop     dword ptr [rax+rax+00h]
0x180088508  lea     rcx, [rbp+3Fh+var_40]; this
0x18008850c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180088511  mov     [rbp+3Fh+phKey], r13
0x180088515  mov     [rsp+0C0h+dwFlags], r14d; dwFlags
0x18008851a  xor     r9d, r9d; dwLegacyKeySpec
0x18008851d  mov     r8, rdi; pszKeyName
0x180088520  lea     rdx, [rbp+3Fh+phKey]; phKey
0x180088524  mov     rcx, [rbp+3Fh+hObject]; hProvider
0x180088528  call    cs:__imp_NCryptOpenKey
0x18008852f  nop     dword ptr [rax+rax+00h]
0x180088534  mov     ebx, eax
0x180088536  test    eax, eax
0x180088538  jns     short loc_180088546
0x18008853a  lea     rdx, aGenerateattest; "GenerateAttestationClaims: NCryptOpenKe"...
0x180088541  jmp     loc_1800883B3
0x180088546  mov     [rsp+0C0h+var_88], r13d
0x18008854b  lea     rax, [rbp+3Fh+dwBytes]
0x18008854f  mov     [rsp+0C0h+pcbResult], rax
0x180088554  mov     [rsp+0C0h+cbOutput], r13d
0x180088559  mov     qword ptr [rsp+0C0h+dwFlags], r13; int
0x18008855e  xor     r9d, r9d
0x180088561  lea     esi, [r9+2]
0x180088565  mov     r8d, esi
0x180088568  mov     rbx, [rbp+3Fh+hKey]
0x18008856c  mov     rdx, rbx
0x18008856f  mov     rcx, [rbp+3Fh+phKey]
0x180088573  call    cs:__imp_NCryptCreateClaim
0x18008857a  nop     dword ptr [rax+rax+00h]
0x18008857f  mov     edi, eax
0x180088581  test    eax, eax
0x180088583  jns     short loc_180088591
0x180088585  lea     rdx, aNcryptcreatecl_0; "NCryptCreateClaim(size)"
0x18008858c  jmp     loc_180088632
0x180088591  mov     edi, dword ptr [rbp+3Fh+dwBytes]
0x180088594  call    cs:__imp_GetProcessHeap
0x18008859b  nop     dword ptr [rax+rax+00h]
0x1800885a0  mov     r8d, edi; dwBytes
0x1800885a3  mov     r14d, 8
0x1800885a9  mov     edx, r14d; dwFlags
0x1800885ac  mov     rcx, rax; hHeap
0x1800885af  call    cs:__imp_HeapAlloc
0x1800885b6  nop     dword ptr [rax+rax+00h]
0x1800885bb  mov     rdx, rax
0x1800885be  lea     rcx, [rbp+3Fh+var_60]
0x1800885c2  call    ?reset@?$unique_ptr@EUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::process_heap_deleter>::reset(uchar *)
0x1800885c7  mov     r15, [rbp+3Fh+var_60]
0x1800885cb  test    r15, r15
0x1800885ce  jnz     short loc_1800885F2
0x1800885d0  mov     rcx, [rbp+47h]; this
0x1800885d4  mov     edi, 8007000Eh
0x1800885d9  mov     r9d, edi; char *
0x1800885dc  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\dm\\dmcmnutils\\atte"...
0x1800885e3  mov     edx, 303h; void *
0x1800885e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800885ed  jmp     loc_180088758
0x1800885f2  mov     eax, dword ptr [rbp+3Fh+dwBytes]
0x1800885f5  mov     [rsp+0C0h+var_88], r13d
0x1800885fa  lea     rcx, [rbp+3Fh+dwBytes]
0x1800885fe  mov     [rsp+0C0h+pcbResult], rcx
0x180088603  mov     [rsp+0C0h+cbOutput], eax
0x180088607  mov     qword ptr [rsp+0C0h+dwFlags], r15
0x18008860c  xor     r9d, r9d
0x18008860f  mov     r8d, esi
0x180088612  mov     rdx, rbx
0x180088615  mov     rcx, [rbp+3Fh+phKey]
0x180088619  call    cs:__imp_NCryptCreateClaim
0x180088620  nop     dword ptr [rax+rax+00h]
0x180088625  mov     edi, eax
0x180088627  test    eax, eax
0x180088629  jns     short loc_180088643
0x18008862b  lea     rdx, aGenerateattest_3; "GenerateAttestationClaims: NCryptCreate"...
0x180088632  mov     r8d, eax
0x180088635  lea     rcx, [rbp+3Fh+var_78]
0x180088639  call    _lambda_a34be7e6fffcc5ac521306cfbd109a62___operator__
0x18008863e  jmp     loc_180088758
0x180088643  mov     [rsp+0C0h+var_88], r13d; dwFlags
0x180088648  lea     rax, [rbp+3Fh+arg_0]
0x18008864c  mov     [rsp+0C0h+pcbResult], rax; pcbResult
0x180088651  mov     [rsp+0C0h+cbOutput], r13d; cbOutput
0x180088656  mov     qword ptr [rsp+0C0h+dwFlags], r13; pbOutput
0x18008865b  xor     r9d, r9d; pParameterList
0x18008865e  lea     r8, pszBlobType; "RSAPUBLICBLOB"
0x180088665  xor     edx, edx; hExportKey
0x180088667  mov     rcx, rbx; hKey
0x18008866a  call    cs:__imp_NCryptExportKey
0x180088671  nop     dword ptr [rax+rax+00h]
0x180088676  mov     esi, eax
0x180088678  test    eax, eax
0x18008867a  jns     short loc_180088696
0x18008867c  mov     r8d, eax
0x18008867f  lea     rdx, aGenerateattest_4; "GenerateAttestationClaims: NCryptExport"...
0x180088686  lea     rcx, [rbp+3Fh+var_78]
0x18008868a  call    _lambda_a34be7e6fffcc5ac521306cfbd109a62___operator__
0x18008868f  mov     edi, esi
0x180088691  jmp     loc_180088758
0x180088696  mov     edi, [rbp+3Fh+arg_0]
0x180088699  call    cs:__imp_GetProcessHeap
0x1800886a0  nop     dword ptr [rax+rax+00h]
0x1800886a5  mov     r8d, edi; dwBytes
0x1800886a8  mov     edx, r14d; dwFlags
0x1800886ab  mov     rcx, rax; hHeap
0x1800886ae  call    cs:__imp_HeapAlloc
0x1800886b5  nop     dword ptr [rax+rax+00h]
0x1800886ba  mov     rdx, rax
0x1800886bd  lea     rcx, [rbp+3Fh+pbOutput]
0x1800886c1  call    ?reset@?$unique_ptr@EUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::process_heap_deleter>::reset(uchar *)
0x1800886c6  mov     r14, [rbp+3Fh+pbOutput]
0x1800886ca  test    r14, r14
0x1800886cd  jnz     short loc_1800886E9
0x1800886cf  mov     r8d, esi
0x1800886d2  lea     rdx, aNcryptexportke_0; "NCryptExportKey(hAIK size allocation)"
0x1800886d9  lea     rcx, [rbp+3Fh+var_78]
0x1800886dd  call    _lambda_a34be7e6fffcc5ac521306cfbd109a62___operator__
0x1800886e2  mov     edi, 8007000Eh
0x1800886e7  jmp     short loc_180088758
0x1800886e9  mov     eax, [rbp+3Fh+arg_0]
0x1800886ec  mov     [rsp+0C0h+var_88], r13d; dwFlags
0x1800886f1  lea     rcx, [rbp+3Fh+arg_0]
0x1800886f5  mov     [rsp+0C0h+pcbResult], rcx; pcbResult
0x1800886fa  mov     [rsp+0C0h+cbOutput], eax; cbOutput
0x1800886fe  mov     qword ptr [rsp+0C0h+dwFlags], r14; pbOutput
0x180088703  xor     r9d, r9d; pParameterList
0x180088706  lea     r8, pszBlobType; "RSAPUBLICBLOB"
0x18008870d  xor     edx, edx; hExportKey
0x18008870f  mov     rcx, rbx; hKey
0x180088712  call    cs:__imp_NCryptExportKey
0x180088719  nop     dword ptr [rax+rax+00h]
0x18008871e  mov     edi, eax
0x180088720  test    eax, eax
0x180088722  jns     short loc_180088730
0x180088724  lea     rdx, aGenerateattest_5; "GenerateAttestationClaims: NCryptExport"...
0x18008872b  jmp     loc_180088632
0x180088730  mov     [rbp+3Fh+var_60], r13
0x180088734  mov     [r12], r15
0x180088738  mov     rcx, [rbp+3Fh+arg_20]
0x18008873c  mov     eax, dword ptr [rbp+3Fh+dwBytes]
0x18008873f  mov     [rcx], eax
0x180088741  mov     [rbp+3Fh+pbOutput], r13
0x180088745  mov     rax, [rbp+3Fh+arg_28]
0x180088749  mov     [rax], r14
0x18008874c  mov     rcx, [rbp+3Fh+arg_30]
0x180088750  mov     eax, [rbp+3Fh+arg_0]
0x180088753  mov     [rcx], eax
0x180088755  mov     edi, r13d
0x180088758  xor     edx, edx
0x18008875a  lea     rcx, [rbp+3Fh+var_60]
0x18008875e  call    ?reset@?$unique_ptr@EUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::process_heap_deleter>::reset(uchar *)
0x180088763  nop
0x180088764  xor     edx, edx
0x180088766  lea     rcx, [rbp+3Fh+pbOutput]
0x18008876a  call    ?reset@?$unique_ptr@EUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::process_heap_deleter>::reset(uchar *)
0x18008876f  nop
0x180088770  lea     rcx, [rbp+3Fh+pszProviderName]
0x180088774  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180088779  nop
0x18008877a  lea     rcx, [rbp+3Fh+bstrString]
0x18008877e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180088783  nop
0x180088784  lea     rcx, [rbp+3Fh+hKey]
0x180088788  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18008878d  nop
0x18008878e  lea     rcx, [rbp+3Fh+phKey]
0x180088792  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180088797  nop
0x180088798  lea     rcx, [rbp+3Fh+hObject]
0x18008879c  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800887a1  mov     eax, edi
0x1800887a3  mov     rbx, [rsp+0C0h+arg_18]
0x1800887ab  add     rsp, 90h
0x1800887b2  pop     r15
0x1800887b4  pop     r14
0x1800887b6  pop     r13
  ... truncated ...
```
