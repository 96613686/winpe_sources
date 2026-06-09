# Appx::Packaging::Consumption::AppxDataSourceFactory::CreateStreamingDataSource(ushort const *,IAppxStreamingDataSource * *)

- ea: `0x18005ed94`
- end: `0x18005f0f8`
- name: `?CreateStreamingDataSource@AppxDataSourceFactory@Consumption@Packaging@Appx@@SAJPEBGPEAPEAUIAppxStreamingDataSource@@@Z`
- size: `868`
- prototype: `__int64 __fastcall(LPCWSTR pwzURI, struct IAppxStreamingDataSource **)`
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005ed30`
- `0x1800932b0`
- `0x1800cb53c`
- `0x1800f6638`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x180029824`
- `0x1800561fc`
- `0x18005626c`
- `0x18005ed94`
- `0x180071f50`
- `0x1800992a0`
- `0x1800992c4`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005efb2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005efb2`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18005ef49`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18005ef49`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ee87`
- `OLEAUT32!__imp_SysFreeString` at `0x18005f0bc`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ee87`
- `OLEAUT32!__imp_SysFreeString` at `0x18005f0bc`
- `urlmon!CreateUri` at `0x18005ee11`
- `urlmon!CreateUri` at `0x18005ee11`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Appx::Packaging::Consumption::AppxDataSourceFactory::CreateStreamingDataSource(
        LPCWSTR pwzURI,
        struct IAppxStreamingDataSource **a2)
{
  unsigned int v4; // ebx
  HRESULT v6; // eax
  int v7; // eax
  HKEY v8; // rdx
  int v9; // eax
  unsigned __int64 v10; // r8
  int StringValue; // eax
  unsigned __int64 v12; // rdx
  OLECHAR *v13; // rbx
  HRESULT v14; // eax
  unsigned int v15; // edi
  unsigned __int64 v16; // rdx
  HRESULT v17; // eax
  unsigned __int64 v18; // rdx
  LPVOID v19; // rcx
  int v20; // eax
  unsigned __int64 v21; // rdx
  unsigned __int64 v22; // rdx
  LPVOID v23; // rcx
  LPVOID v24; // rcx
  unsigned int *ppv; // [rsp+28h] [rbp-29h]
  int ppva; // [rsp+28h] [rbp-29h]
  int ppvb; // [rsp+28h] [rbp-29h]
  IUri *ppURI; // [rsp+38h] [rbp-19h] BYREF
  LPVOID v29; // [rsp+40h] [rbp-11h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-9h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-1h] BYREF
  LPCOLESTR lpsz[2]; // [rsp+58h] [rbp+7h] BYREF
  int v33; // [rsp+68h] [rbp+17h]
  __int64 v34; // [rsp+70h] [rbp+1Fh]
  GUID pclsid; // [rsp+78h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B0h] [rbp+5Fh]

  v34 = -2;
  if ( !pwzURI )
  {
    v4 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x28,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxdatasourcefactory.cpp",
      (const char *)0x80004003LL,
      (int)ppv);
    return v4;
  }
  ppURI = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&ppURI);
  v6 = CreateUri(pwzURI, 0x100u, 0, &ppURI);
  v4 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxdatasourcefactory.cpp",
      (const char *)(unsigned int)v6,
      (int)ppv);
LABEL_6:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&ppURI);
    return v4;
  }
  bstrString = 0;
  v7 = ((__int64 (__fastcall *)(IUri *, BSTR *))ppURI->lpVtbl->GetSchemeName)(ppURI, &bstrString);
  v4 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxdatasourcefactory.cpp",
      (const char *)(unsigned int)v7,
      (int)ppv);
LABEL_9:
    SysFreeString(bstrString);
    goto LABEL_6;
  }
  phkResult = 0;
  v9 = Common::RegistryKey::Open(
         &phkResult,
         v8,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\AppModel\\PackageStreamingSources",
         0x80000000);
  v4 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x33,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxdatasourcefactory.cpp",
      (const char *)(unsigned int)v9,
      (int)ppv);
    Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
    goto LABEL_9;
  }
  *(_OWORD *)lpsz = 0;
  v33 = 0;
  StringValue = Common::RegistryKey::GetStringValue(
                  (Common::RegistryKey *)&phkResult,
                  bstrString,
                  v10,
                  (struct Common::StringBuffer *)lpsz,
                  ppv);
  v4 = StringValue;
  if ( StringValue < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x39,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxdatasourcefactory.cpp",
      (const char *)(unsigned int)StringValue,
      ppva);
    if ( lpsz[1] )
      operator delete((void *)lpsz[1], v12);
    Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
    goto LABEL_9;
  }
  pclsid = 0;
  v13 = (OLECHAR *)lpsz[1];
  v14 = CLSIDFromString(lpsz[1], &pclsid);
  v15 = v14;
  if ( v14 >= 0 )
  {
    v29 = 0;
    v17 = CoCreateInstance(&pclsid, 0, 5u, &GUID_a575c2d8_ad34_456f_810b_f6c67795014d, &v29);
    v15 = v17;
    if ( v17 >= 0 )
    {
      v20 = (*(__int64 (__fastcall **)(LPVOID, LPCWSTR, struct IAppxStreamingDataSource **))(*(_QWORD *)v29 + 24LL))(
              v29,
              pwzURI,
              a2);
      v15 = v20;
      if ( v20 >= 0 )
      {
        v24 = v29;
        if ( v29 )
        {
          v29 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v24 + 16LL))(v24);
        }
        if ( v13 )
          operator delete(v13, v21);
        Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
        v15 = 0;
        goto LABEL_37;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x48,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxdatasourcefactory.cpp",
        (const char *)(unsigned int)v20,
        ppvb);
      v23 = v29;
      if ( v29 )
      {
        v29 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v23 + 16LL))(v23);
      }
      if ( v13 )
        operator delete(v13, v22);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x46,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxdatasourcefactory.cpp",
        (const char *)(unsigned int)v17,
        ppvb);
      v19 = v29;
      if ( v29 )
      {
        v29 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v19 + 16LL))(v19);
      }
      if ( v13 )
        operator delete(v13, v18);
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3E,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxdatasourcefactory.cpp",
      (const char *)(unsigned int)v14,
      ppva);
    if ( v13 )
      operator delete(v13, v16);
  }
  Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
LABEL_37:
  SysFreeString(bstrString);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&ppURI);
  return v15;
}

```

## disassembly

```asm
0x18005ed94  mov     rax, rsp
0x18005ed97  push    rbp
0x18005ed98  push    rdi
0x18005ed99  push    r14
0x18005ed9b  lea     rbp, [rax-5Fh]
0x18005ed9f  sub     rsp, 90h
0x18005eda6  mov     [rbp+57h+var_38], 0FFFFFFFFFFFFFFFEh
0x18005edae  mov     [rax+18h], rbx
0x18005edb2  mov     [rax+20h], rsi
0x18005edb6  mov     rax, cs:__security_cookie
0x18005edbd  xor     rax, rsp
0x18005edc0  mov     [rbp+57h+var_20], rax
0x18005edc4  mov     r14, rdx
0x18005edc7  mov     rsi, rcx
0x18005edca  test    rcx, rcx
0x18005edcd  jnz     short loc_18005EDF1
0x18005edcf  mov     rcx, [rbp+5Fh]; this
0x18005edd3  mov     ebx, 80004003h
0x18005edd8  mov     r9d, ebx; char *
0x18005eddb  lea     r8, aOnecorePrintsc_175; "onecore\\printscan\\appxpackaging\\cons"...
0x18005ede2  lea     edx, [rsi+28h]; void *
0x18005ede5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005edea  mov     eax, ebx
0x18005edec  jmp     loc_18005F0D3
0x18005edf1  mov     [rbp+57h+ppURI], 0
0x18005edf9  lea     rcx, [rbp+57h+ppURI]
0x18005edfd  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18005ee02  lea     r9, [rbp+57h+ppURI]; ppURI
0x18005ee06  xor     r8d, r8d; dwReserved
0x18005ee09  mov     edx, 100h; dwFlags
0x18005ee0e  mov     rcx, rsi; pwzURI
0x18005ee11  call    cs:__imp_CreateUri
0x18005ee18  nop     dword ptr [rax+rax+00h]
0x18005ee1d  mov     ebx, eax
0x18005ee1f  mov     rcx, [rbp+5Fh]; this
0x18005ee23  test    eax, eax
0x18005ee25  jns     short loc_18005EE46
0x18005ee27  mov     r9d, eax; char *
0x18005ee2a  lea     r8, aOnecorePrintsc_175; "onecore\\printscan\\appxpackaging\\cons"...
0x18005ee31  mov     edx, 2Bh ; '+'; void *
0x18005ee36  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005ee3b  lea     rcx, [rbp+57h+ppURI]
0x18005ee3f  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18005ee44  jmp     short loc_18005EDEA
0x18005ee46  mov     [rbp+57h+bstrString], 0
0x18005ee4e  mov     rcx, [rbp+57h+ppURI]
0x18005ee52  mov     rax, [rcx]
0x18005ee55  lea     rdx, [rbp+57h+bstrString]
0x18005ee59  mov     rax, [rax+98h]
0x18005ee60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ee65  mov     ebx, eax
0x18005ee67  mov     rcx, [rbp+5Fh]; this
0x18005ee6b  test    eax, eax
0x18005ee6d  jns     short loc_18005EE95
0x18005ee6f  mov     r9d, eax; char *
0x18005ee72  lea     r8, aOnecorePrintsc_175; "onecore\\printscan\\appxpackaging\\cons"...
0x18005ee79  mov     edx, 2Dh ; '-'; void *
0x18005ee7e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005ee83  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18005ee87  call    cs:__imp_SysFreeString
0x18005ee8e  nop     dword ptr [rax+rax+00h]
0x18005ee93  jmp     short loc_18005EE3B
0x18005ee95  mov     [rbp+57h+phkResult], 0
0x18005ee9d  mov     r9d, 80000000h; unsigned int
0x18005eea3  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005eeaa  lea     rcx, [rbp+57h+phkResult]; phkResult
0x18005eeae  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x18005eeb3  mov     ebx, eax
0x18005eeb5  mov     rcx, [rbp+5Fh]; this
0x18005eeb9  test    eax, eax
0x18005eebb  jns     short loc_18005EEDE
0x18005eebd  mov     r9d, eax; char *
0x18005eec0  lea     r8, aOnecorePrintsc_175; "onecore\\printscan\\appxpackaging\\cons"...
0x18005eec7  mov     edx, 33h ; '3'; void *
0x18005eecc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005eed1  nop
0x18005eed2  mov     rcx, [rbp+57h+phkResult]
0x18005eed6  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18005eedb  nop
0x18005eedc  jmp     short loc_18005EE83
0x18005eede  xor     eax, eax
0x18005eee0  xorps   xmm0, xmm0
0x18005eee3  movups  xmmword ptr [rbp+57h+lpsz], xmm0
0x18005eee7  mov     [rbp+57h+var_40], eax
0x18005eeea  lea     r9, [rbp+57h+lpsz]; struct Common::StringBuffer *
0x18005eeee  mov     rdx, [rbp+57h+bstrString]; unsigned __int16 *
0x18005eef2  lea     rcx, [rbp+57h+phkResult]; this
0x18005eef6  call    ?GetStringValue@RegistryKey@Common@@QEAAJPEBG_KAEAVStringBuffer@2@PEAK@Z; Common::RegistryKey::GetStringValue(ushort const *,unsigned __int64,Common::StringBuffer &,ulong *)
0x18005eefb  mov     ebx, eax
0x18005eefd  mov     rcx, [rbp+5Fh]; this
0x18005ef01  test    eax, eax
0x18005ef03  jns     short loc_18005EF37
0x18005ef05  mov     r9d, eax; char *
0x18005ef08  lea     r8, aOnecorePrintsc_175; "onecore\\printscan\\appxpackaging\\cons"...
0x18005ef0f  mov     edx, 39h ; '9'; void *
0x18005ef14  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005ef19  mov     rcx, [rbp+57h+lpsz+8]; void *
0x18005ef1d  test    rcx, rcx
0x18005ef20  jz      short loc_18005EF28
0x18005ef22  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005ef27  nop
0x18005ef28  mov     rcx, [rbp+57h+phkResult]
0x18005ef2c  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18005ef31  nop
0x18005ef32  jmp     loc_18005EE83
0x18005ef37  xorps   xmm0, xmm0
0x18005ef3a  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x18005ef3e  mov     rbx, [rbp+57h+lpsz+8]
0x18005ef42  lea     rdx, [rbp+57h+pclsid]; pclsid
0x18005ef46  mov     rcx, rbx; lpsz
0x18005ef49  call    cs:__imp_CLSIDFromString
0x18005ef50  nop     dword ptr [rax+rax+00h]
0x18005ef55  mov     edi, eax
0x18005ef57  mov     rcx, [rbp+5Fh]; this
0x18005ef5b  test    eax, eax
0x18005ef5d  jns     short loc_18005EF90
0x18005ef5f  mov     r9d, eax; char *
0x18005ef62  lea     r8, aOnecorePrintsc_175; "onecore\\printscan\\appxpackaging\\cons"...
0x18005ef69  mov     edx, 3Eh ; '>'; void *
0x18005ef6e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005ef73  test    rbx, rbx
0x18005ef76  jz      short loc_18005EF81
0x18005ef78  mov     rcx, rbx; void *
0x18005ef7b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005ef80  nop
0x18005ef81  mov     rcx, [rbp+57h+phkResult]
0x18005ef85  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18005ef8a  nop
0x18005ef8b  jmp     loc_18005F0B8
0x18005ef90  mov     [rbp+57h+var_68], 0
0x18005ef98  lea     rax, [rbp+57h+var_68]
0x18005ef9c  mov     [rsp+0A0h+ppv], rax; int
0x18005efa1  lea     r9, _GUID_a575c2d8_ad34_456f_810b_f6c67795014d; riid
0x18005efa8  xor     edx, edx; pUnkOuter
0x18005efaa  lea     r8d, [rdx+5]; dwClsContext
0x18005efae  lea     rcx, [rbp+57h+pclsid]; rclsid
0x18005efb2  call    cs:__imp_CoCreateInstance
0x18005efb9  nop     dword ptr [rax+rax+00h]
0x18005efbe  mov     edi, eax
0x18005efc0  mov     rcx, [rbp+5Fh]; this
0x18005efc4  test    eax, eax
0x18005efc6  jns     short loc_18005F016
0x18005efc8  mov     r9d, eax; char *
0x18005efcb  lea     r8, aOnecorePrintsc_175; "onecore\\printscan\\appxpackaging\\cons"...
0x18005efd2  mov     edx, 46h ; 'F'; void *
0x18005efd7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005efdc  mov     rcx, [rbp+57h+var_68]
0x18005efe0  test    rcx, rcx
0x18005efe3  jz      short loc_18005EFF9
0x18005efe5  mov     [rbp+57h+var_68], 0
0x18005efed  mov     rax, [rcx]
0x18005eff0  mov     rax, [rax+10h]
0x18005eff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eff9  test    rbx, rbx
0x18005effc  jz      short loc_18005F007
0x18005effe  mov     rcx, rbx; void *
0x18005f001  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005f006  nop
0x18005f007  mov     rcx, [rbp+57h+phkResult]
0x18005f00b  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18005f010  nop
0x18005f011  jmp     loc_18005F0B8
0x18005f016  mov     rcx, [rbp+57h+var_68]
0x18005f01a  mov     rax, [rcx]
0x18005f01d  mov     r8, r14
0x18005f020  mov     rdx, rsi
0x18005f023  mov     rax, [rax+18h]
0x18005f027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f02c  mov     edi, eax
0x18005f02e  mov     rcx, [rbp+5Fh]; this
0x18005f032  test    eax, eax
0x18005f034  jns     short loc_18005F081
0x18005f036  mov     r9d, eax; char *
0x18005f039  lea     r8, aOnecorePrintsc_175; "onecore\\printscan\\appxpackaging\\cons"...
0x18005f040  mov     edx, 48h ; 'H'; void *
0x18005f045  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005f04a  mov     rcx, [rbp+57h+var_68]
0x18005f04e  test    rcx, rcx
0x18005f051  jz      short loc_18005F067
0x18005f053  mov     [rbp+57h+var_68], 0
0x18005f05b  mov     rax, [rcx]
0x18005f05e  mov     rax, [rax+10h]
0x18005f062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f067  test    rbx, rbx
0x18005f06a  jz      short loc_18005F075
0x18005f06c  mov     rcx, rbx; void *
0x18005f06f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005f074  nop
0x18005f075  mov     rcx, [rbp+57h+phkResult]
0x18005f079  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18005f07e  nop
0x18005f07f  jmp     short loc_18005F0B8
0x18005f081  mov     rcx, [rbp+57h+var_68]
0x18005f085  test    rcx, rcx
0x18005f088  jz      short loc_18005F09E
0x18005f08a  mov     [rbp+57h+var_68], 0
0x18005f092  mov     rax, [rcx]
0x18005f095  mov     rax, [rax+10h]
0x18005f099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f09e  test    rbx, rbx
0x18005f0a1  jz      short loc_18005F0AC
0x18005f0a3  mov     rcx, rbx; void *
0x18005f0a6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005f0ab  nop
0x18005f0ac  mov     rcx, [rbp+57h+phkResult]
0x18005f0b0  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18005f0b5  nop
0x18005f0b6  xor     edi, edi
0x18005f0b8  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18005f0bc  call    cs:__imp_SysFreeString
0x18005f0c3  nop     dword ptr [rax+rax+00h]
0x18005f0c8  lea     rcx, [rbp+57h+ppURI]
0x18005f0cc  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18005f0d1  mov     eax, edi
0x18005f0d3  mov     rcx, [rbp+57h+var_20]
0x18005f0d7  xor     rcx, rsp; StackCookie
0x18005f0da  call    __security_check_cookie
0x18005f0df  lea     r11, [rsp+0A0h+var_10]
0x18005f0e7  mov     rbx, [r11+30h]
0x18005f0eb  mov     rsi, [r11+38h]
0x18005f0ef  mov     rsp, r11
0x18005f0f2  pop     r14
0x18005f0f4  pop     rdi
0x18005f0f5  pop     rbp
0x18005f0f6  retn
```
