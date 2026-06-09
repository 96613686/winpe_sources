# PCPStorageProvider::GetRegIntermediateCaEkCertStore(uchar *,ulong,ulong *)

- ea: `0x1800366bc`
- end: `0x180036a51`
- name: `?GetRegIntermediateCaEkCertStore@PCPStorageProvider@@AEAAJPEAEKPEAK@Z`
- size: `917`
- prototype: `int(PCPStorageProvider *__hidden this, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18001bb00`

## callees

- `0x18000f858`
- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x1800366bc`
- `0x180036a58`
- `0x180036ab4`
- `0x1800389c0`
- `0x18005305c`
- `0x18005437c`
- `0x180061bac`
- `0x18006d388`
- `0x1800764d0`
- `0x18007704c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800367a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003687f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800369c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036a1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800367a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003687f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800369c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036a1b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800367fd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800368db`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800367fd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800368db`
- `ntdll!RtlGetPersistedStateLocation` at `0x18003675a`
- `ntdll!RtlGetPersistedStateLocation` at `0x18003675a`
- `CRYPT32!CertOpenStore` at `0x180036822`
- `CRYPT32!CertOpenStore` at `0x180036916`
- `CRYPT32!CertOpenStore` at `0x180036822`
- `CRYPT32!CertOpenStore` at `0x180036916`

## string_xrefs

- `0x180036721`: `System\CurrentControlSet\Services\TPM\WMI\Endorsement\IntermediateCACertStore`

## pseudocode

```c
__int64 __fastcall PCPStorageProvider::GetRegIntermediateCaEkCertStore(
        PCPStorageProvider *this,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned int *a4)
{
  rsize_t v4; // rdi
  int PersistedStateLocation; // eax
  int v8; // eax
  HCERTSTORE v9; // rax
  const char *v10; // r9
  __int64 v11; // rax
  unsigned int LastError; // ebx
  HKEY v13; // rbx
  LSTATUS v14; // eax
  HCERTSTORE v15; // rax
  const char *v16; // r9
  int dwOptions; // [rsp+20h] [rbp-E0h]
  int dwOptionsa; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v21; // [rsp+58h] [rbp-A8h] BYREF
  __int64 Source; // [rsp+60h] [rbp-A0h] BYREF
  int v23; // [rsp+68h] [rbp-98h]
  _BYTE v24[32]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v4 = a3;
  KspFunctionLogger::KspFunctionLogger(
    (KspFunctionLogger *)v24,
    L"PCPStorageProvider::GetRegIntermediateCaEkCertStore",
    1);
  memset_0(SubKey, 0, 0x208u);
  v23 = 520;
  hKey = 0;
  v21 = 0;
  *a4 = 0;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"TPMCoreProvisioningIntermediateCACerts",
                             0,
                             L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement\\IntermediateCACertStore",
                             0);
  if ( PersistedStateLocation < 0 )
  {
    v8 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x3EE,
           (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
           (const char *)(unsigned int)PersistedStateLocation,
           (int)SubKey);
LABEL_8:
    LastError = v8;
    goto LABEL_26;
  }
  if ( hKey )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&Source);
    RegCloseKey(hKey);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&Source);
  }
  hKey = 0;
  if ( RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0) )
  {
    v13 = hKey;
    if ( hKey )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&Source);
      RegCloseKey(v13);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&Source);
    }
    hKey = 0;
    v14 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20019u, 0, &hKey, 0);
    LastError = v14;
    if ( v14 > 0 )
      LastError = (unsigned __int16)v14 | 0x80070000;
    if ( (LastError & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x41B,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)LastError,
        dwOptionsa);
LABEL_26:
      if ( hKey )
        RegCloseKey(hKey);
      goto LABEL_28;
    }
    v15 = CertOpenStore((LPCSTR)4, 0, 0, 0x8000u, hKey);
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &v21,
      v15);
    v11 = v21;
    if ( !v21 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x417,
                    (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                    v16);
LABEL_16:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
LABEL_28:
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v24);
      return LastError;
    }
  }
  else
  {
    v9 = CertOpenStore((LPCSTR)4, 0, 0, 0, hKey);
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &v21,
      v9);
    v11 = v21;
    if ( !v21 )
    {
      v8 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x405,
             (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
             v10);
      goto LABEL_8;
    }
  }
  Source = v11;
  *a4 = 8;
  if ( !(_DWORD)v4 || !a2 )
  {
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    LastError = 0;
    goto LABEL_28;
  }
  if ( (unsigned int)v4 < 8 )
  {
    LastError = -2146893784;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x429,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
      (const char *)0x80090028LL,
      dwOptions);
    goto LABEL_16;
  }
  memcpy_s_1(a2, v4, &Source, 8u);
  if ( hKey )
    RegCloseKey(hKey);
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v24);
  return 0;
}

```

## disassembly

```asm
0x1800366bc  push    rbp
0x1800366be  push    rbx
0x1800366bf  push    rsi
0x1800366c0  push    rdi
0x1800366c1  push    r14
0x1800366c3  lea     rbp, [rsp-1B0h]
0x1800366cb  sub     rsp, 2B0h
0x1800366d2  mov     rax, cs:__security_cookie
0x1800366d9  xor     rax, rsp
0x1800366dc  mov     [rbp+1D0h+var_30], rax
0x1800366e3  mov     edi, r8d
0x1800366e6  lea     rcx, [rsp+2D0h+var_260]; this
0x1800366eb  mov     rsi, rdx
0x1800366ee  mov     r8b, 1; bool
0x1800366f1  lea     rdx, aPcpstorageprov_18; "PCPStorageProvider::GetRegIntermediateC"...
0x1800366f8  mov     r14, r9
0x1800366fb  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x180036700  mov     ebx, 208h
0x180036705  lea     rcx, [rbp+1D0h+SubKey]; void *
0x180036709  mov     r8d, ebx; Size
0x18003670c  xor     edx, edx; Val
0x18003670e  call    memset_0
0x180036713  lea     rax, [rsp+2D0h+var_268]
0x180036718  mov     [rsp+2D0h+var_268], ebx
0x18003671c  mov     [rsp+2D0h+lpSecurityAttributes], rax
0x180036721  lea     r8, aSystemCurrentc_9; "System\\CurrentControlSet\\Services\\TP"...
0x180036728  lea     rax, [rbp+1D0h+SubKey]
0x18003672c  mov     [rsp+2D0h+samDesired], ebx
0x180036730  xor     r9d, r9d
0x180036733  mov     qword ptr [rsp+2D0h+dwOptions], rax; int
0x180036738  xor     edx, edx
0x18003673a  mov     [rsp+2D0h+hKey], 0
0x180036743  lea     rcx, aTpmcoreprovisi_0; "TPMCoreProvisioningIntermediateCACerts"
0x18003674a  mov     [rsp+2D0h+var_278], 0
0x180036753  mov     dword ptr [r14], 0
0x18003675a  call    cs:__imp_RtlGetPersistedStateLocation
0x180036761  nop     dword ptr [rax+rax+00h]
0x180036766  test    eax, eax
0x180036768  jns     short loc_18003678A
0x18003676a  mov     rcx, [rbp+1D8h]; this
0x180036771  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180036778  mov     r9d, eax; char *
0x18003677b  mov     edx, 3EEh; void *
0x180036780  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180036785  jmp     loc_180036861
0x18003678a  mov     rbx, [rsp+2D0h+hKey]
0x18003678f  test    rbx, rbx
0x180036792  jz      short loc_1800367B7
0x180036794  lea     rcx, [rsp+2D0h+Source]; this
0x180036799  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003679e  mov     rcx, rbx; hKey
0x1800367a1  call    cs:__imp_RegCloseKey
0x1800367a8  nop     dword ptr [rax+rax+00h]
0x1800367ad  lea     rcx, [rsp+2D0h+Source]; this
0x1800367b2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800367b7  mov     [rsp+2D0h+lpdwDisposition], 0; lpdwDisposition
0x1800367c0  lea     rax, [rsp+2D0h+hKey]
0x1800367c5  mov     [rsp+2D0h+phkResult], rax; phkResult
0x1800367ca  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x1800367ce  mov     [rsp+2D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800367d7  xor     r9d, r9d; lpClass
0x1800367da  mov     [rsp+2D0h+samDesired], 0F003Fh; samDesired
0x1800367e2  xor     r8d, r8d; Reserved
0x1800367e5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800367ec  mov     [rsp+2D0h+dwOptions], 0; dwOptions
0x1800367f4  mov     [rsp+2D0h+hKey], 0
0x1800367fd  call    cs:__imp_RegCreateKeyExW
0x180036804  nop     dword ptr [rax+rax+00h]
0x180036809  test    eax, eax
0x18003680b  jnz     short loc_180036868
0x18003680d  mov     rax, [rsp+2D0h+hKey]
0x180036812  xor     edx, edx; dwEncodingType
0x180036814  xor     r9d, r9d; dwFlags
0x180036817  mov     qword ptr [rsp+2D0h+dwOptions], rax; int
0x18003681c  xor     r8d, r8d; hCryptProv
0x18003681f  lea     ecx, [rdx+4]; lpszStoreProvider
0x180036822  call    cs:__imp_CertOpenStore
0x180036829  nop     dword ptr [rax+rax+00h]
0x18003682e  mov     rdx, rax
0x180036831  lea     rcx, [rsp+2D0h+var_278]
0x180036836  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18003683b  mov     rax, [rsp+2D0h+var_278]
0x180036840  test    rax, rax
0x180036843  jnz     loc_18003696C
0x180036849  mov     rcx, [rbp+1D8h]; this
0x180036850  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180036857  mov     edx, 405h; void *
0x18003685c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180036861  mov     ebx, eax
0x180036863  jmp     loc_180036A11
0x180036868  mov     rbx, [rsp+2D0h+hKey]
0x18003686d  test    rbx, rbx
0x180036870  jz      short loc_180036895
0x180036872  lea     rcx, [rsp+2D0h+Source]; this
0x180036877  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003687c  mov     rcx, rbx; hKey
0x18003687f  call    cs:__imp_RegCloseKey
0x180036886  nop     dword ptr [rax+rax+00h]
0x18003688b  lea     rcx, [rsp+2D0h+Source]; this
0x180036890  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180036895  mov     [rsp+2D0h+lpdwDisposition], 0; lpdwDisposition
0x18003689e  lea     rax, [rsp+2D0h+hKey]
0x1800368a3  mov     [rsp+2D0h+phkResult], rax; phkResult
0x1800368a8  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x1800368ac  mov     [rsp+2D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800368b5  xor     r9d, r9d; lpClass
0x1800368b8  mov     [rsp+2D0h+samDesired], 20019h; samDesired
0x1800368c0  xor     r8d, r8d; Reserved
0x1800368c3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800368ca  mov     [rsp+2D0h+dwOptions], 0; int
0x1800368d2  mov     [rsp+2D0h+hKey], 0
0x1800368db  call    cs:__imp_RegCreateKeyExW
0x1800368e2  nop     dword ptr [rax+rax+00h]
0x1800368e7  mov     ebx, eax
0x1800368e9  test    eax, eax
0x1800368eb  jle     short loc_1800368F6
0x1800368ed  movzx   ebx, ax
0x1800368f0  or      ebx, 80070000h
0x1800368f6  test    ebx, ebx
0x1800368f8  js      loc_1800369F6
0x1800368fe  mov     rax, [rsp+2D0h+hKey]
0x180036903  xor     edx, edx; dwEncodingType
0x180036905  mov     r9d, 8000h; dwFlags
0x18003690b  mov     qword ptr [rsp+2D0h+dwOptions], rax; pvPara
0x180036910  xor     r8d, r8d; hCryptProv
0x180036913  lea     ecx, [rdx+4]; lpszStoreProvider
0x180036916  call    cs:__imp_CertOpenStore
0x18003691d  nop     dword ptr [rax+rax+00h]
0x180036922  mov     rdx, rax
0x180036925  lea     rcx, [rsp+2D0h+var_278]
0x18003692a  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18003692f  mov     rax, [rsp+2D0h+var_278]
0x180036934  test    rax, rax
0x180036937  jnz     short loc_18003696C
0x180036939  mov     rcx, [rbp+1D8h]; this
0x180036940  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180036947  mov     edx, 417h; void *
0x18003694c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180036951  mov     ebx, eax
0x180036953  lea     rcx, [rsp+2D0h+var_278]
0x180036958  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003695d  lea     rcx, [rsp+2D0h+hKey]
0x180036962  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180036967  jmp     loc_180036A27
0x18003696c  mov     [rsp+2D0h+Source], rax
0x180036971  mov     r9d, 8; SourceSize
0x180036977  mov     [r14], r9d
0x18003697a  test    edi, edi
0x18003697c  jz      short loc_1800369DE
0x18003697e  test    rsi, rsi
0x180036981  jz      short loc_1800369DE
0x180036983  cmp     edi, r9d
0x180036986  jnb     short loc_1800369AA
0x180036988  mov     rcx, [rbp+1D8h]; this
0x18003698f  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180036996  mov     ebx, 80090028h
0x18003699b  mov     edx, 429h; void *
0x1800369a0  mov     r9d, ebx; char *
0x1800369a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800369a8  jmp     short loc_180036953
0x1800369aa  mov     rdx, rdi; DestinationSize
0x1800369ad  lea     r8, [rsp+2D0h+Source]; Source
0x1800369b2  mov     rcx, rsi; Destination
0x1800369b5  call    memcpy_s_1
0x1800369ba  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800369bf  test    rcx, rcx
0x1800369c2  jz      short loc_1800369D0
0x1800369c4  call    cs:__imp_RegCloseKey
0x1800369cb  nop     dword ptr [rax+rax+00h]
0x1800369d0  lea     rcx, [rsp+2D0h+var_260]; this
0x1800369d5  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x1800369da  xor     eax, eax
0x1800369dc  jmp     short loc_180036A33
0x1800369de  lea     rcx, [rsp+2D0h+var_278]
0x1800369e3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800369e8  lea     rcx, [rsp+2D0h+hKey]
0x1800369ed  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800369f2  xor     ebx, ebx
0x1800369f4  jmp     short loc_180036A27
0x1800369f6  mov     rcx, [rbp+1D8h]; this
0x1800369fd  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180036a04  mov     r9d, ebx; char *
0x180036a07  mov     edx, 41Bh; void *
0x180036a0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036a11  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180036a16  test    rcx, rcx
0x180036a19  jz      short loc_180036A27
0x180036a1b  call    cs:__imp_RegCloseKey
0x180036a22  nop     dword ptr [rax+rax+00h]
0x180036a27  lea     rcx, [rsp+2D0h+var_260]; this
0x180036a2c  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180036a31  mov     eax, ebx
0x180036a33  mov     rcx, [rbp+1D0h+var_30]
0x180036a3a  xor     rcx, rsp; StackCookie
0x180036a3d  call    __security_check_cookie
0x180036a42  add     rsp, 2B0h
0x180036a49  pop     r14
0x180036a4b  pop     rdi
0x180036a4c  pop     rsi
0x180036a4d  pop     rbx
0x180036a4e  pop     rbp
0x180036a4f  retn
```
