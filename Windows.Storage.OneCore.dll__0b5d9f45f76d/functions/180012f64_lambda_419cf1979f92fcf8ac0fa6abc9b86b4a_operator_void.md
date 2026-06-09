# _lambda_419cf1979f92fcf8ac0fa6abc9b86b4a_::operator()(void)

- ea: `0x180012f64`
- end: `0x18001327b`
- name: `??R_lambda_419cf1979f92fcf8ac0fa6abc9b86b4a_@@QEBAJXZ`
- size: `791`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180014060`

## callees

- `0x180002be0`
- `0x180003124`
- `0x180007f8c`
- `0x180007fac`
- `0x18000d564`
- `0x1800113ec`
- `0x1800129f4`
- `0x180012e0c`
- `0x180012f64`
- `0x1800137e8`
- `0x1800139b4`
- `0x180014260`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013074`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013074`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800131b9`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800131b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001305b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001305b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180012ff0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180012ff0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180013095`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180013095`

## string_xrefs

- `0x180013054`: `Windows.Internal.CapabilityAccess.CapabilityAccess`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _lambda_419cf1979f92fcf8ac0fa6abc9b86b4a_::operator()(__int64 a1)
{
  int token_information; // eax
  int LastError; // ebx
  void *v4; // rcx
  void *v6; // r14
  const char *v7; // r9
  HSTRING v8; // rbx
  int ActivationFactory; // eax
  __int64 v10; // rdx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, _QWORD, HSTRING); // rbx
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rsi
  __int64 (__fastcall *v16)(__int64, _QWORD, _QWORD, _QWORD); // rdi
  int v17; // ebx
  DWORD ProcessId; // eax
  __int64 *v19; // [rsp+20h] [rbp-99h]
  __int64 v20; // [rsp+40h] [rbp-79h] BYREF
  __int64 v21; // [rsp+48h] [rbp-71h] BYREF
  LPWSTR StringSid; // [rsp+50h] [rbp-69h] BYREF
  HSTRING v23; // [rsp+58h] [rbp-61h] BYREF
  int v24; // [rsp+60h] [rbp-59h] BYREF
  void *Block; // [rsp+68h] [rbp-51h] BYREF
  HSTRING string; // [rsp+70h] [rbp-49h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-41h] BYREF
  _QWORD v28[4]; // [rsp+90h] [rbp-29h] BYREF
  _QWORD v29[4]; // [rsp+B0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  **(_DWORD **)(a1 + 32) = 0;
  Block = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, *(_QWORD *)(a1 + 8));
  LastError = token_information;
  if ( token_information < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDF,
      (unsigned int)"onecore\\base\\windows.storage\\src\\camcheckhelpers.h",
      (const char *)(unsigned int)token_information,
      (int)v19);
    v4 = Block;
    if ( !Block )
      return (unsigned int)LastError;
LABEL_3:
    operator delete(v4);
    return (unsigned int)LastError;
  }
  StringSid = 0;
  v6 = Block;
  if ( !ConvertSidToStringSidW(*(PSID *)Block, &StringSid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xE2,
                  (unsigned int)"onecore\\base\\windows.storage\\src\\camcheckhelpers.h",
                  v7);
LABEL_7:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
    if ( !v6 )
      return (unsigned int)LastError;
    v4 = v6;
    goto LABEL_3;
  }
  Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v29, StringSid);
  Windows::Internal::StringReference::_ConstructorHelper(
    (Windows::Internal::StringReference *)v28,
    *(const unsigned __int16 **)(a1 + 16));
  v21 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Internal.CapabilityAccess.CapabilityAccess",
         0x32u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v8 = string;
  Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(&v21);
  ActivationFactory = RoGetActivationFactory(v8, &GUID_518f3880_4e5c_4524_ab03_cd01336b2178, &v21);
  LastError = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE9,
      (unsigned int)"onecore\\base\\windows.storage\\src\\camcheckhelpers.h",
      (const char *)(unsigned int)ActivationFactory,
      (int)v19);
LABEL_13:
    Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(&v21);
    goto LABEL_7;
  }
  v20 = 0;
  if ( *(_QWORD *)a1 )
  {
    v15 = v21;
    v16 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v21 + 56LL);
    Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(&v20);
    v17 = *(_DWORD *)(a1 + 24);
    ProcessId = GetProcessId(*(HANDLE *)a1);
    LODWORD(v19) = v17;
    LastError = v16(v15, v29[0], v28[0], ProcessId);
    if ( LastError < 0 )
    {
      v14 = 248;
      goto LABEL_26;
    }
  }
  else
  {
    v23 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      &v23,
      0);
    LastError = GetPackageFamilyNameFromToken(*(void **)(a1 + 8), &v23);
    if ( LastError < 0 )
    {
      v10 = 239;
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\base\\windows.storage\\src\\camcheckhelpers.h",
        (const char *)(unsigned int)LastError,
        (int)v19);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v23);
LABEL_18:
      Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(&v20);
      goto LABEL_13;
    }
    v11 = v21;
    v12 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, HSTRING))(*(_QWORD *)v21 + 48LL);
    Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(&v20);
    v19 = &v20;
    LastError = v12(v11, v29[0], v28[0], v23);
    if ( LastError < 0 )
    {
      v10 = 240;
      goto LABEL_17;
    }
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v23);
  }
  v24 = 0;
  LOBYTE(v13) = 1;
  LastError = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 88LL))(v20, v13);
  if ( LastError < 0 )
  {
    v14 = 252;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\windows.storage\\src\\camcheckhelpers.h",
      (const char *)(unsigned int)LastError,
      (int)v19);
    goto LABEL_18;
  }
  LastError = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v20 + 152LL))(v20, &v24);
  if ( LastError < 0 )
  {
    v14 = 253;
    goto LABEL_26;
  }
  **(_DWORD **)(a1 + 32) = v24;
  Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(&v20);
  Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(&v21);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
  if ( v6 )
    operator delete(v6);
  return 0;
}

```

## disassembly

```asm
0x180012f64  push    rbp
0x180012f66  push    rbx
0x180012f67  push    rsi
0x180012f68  push    rdi
0x180012f69  push    r14
0x180012f6b  push    r15
0x180012f6d  lea     rbp, [rsp-2Fh]
0x180012f72  sub     rsp, 0E8h
0x180012f79  mov     rax, cs:__security_cookie
0x180012f80  xor     rax, rsp
0x180012f83  mov     [rbp+57h+var_40], rax
0x180012f87  mov     r15, rcx
0x180012f8a  mov     rax, [rcx+20h]
0x180012f8e  mov     dword ptr [rax], 0
0x180012f94  mov     [rbp+57h+Block], 0
0x180012f9c  mov     rdx, [rcx+8]
0x180012fa0  lea     rcx, [rbp+57h+Block]
0x180012fa4  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x180012fa9  mov     ebx, eax
0x180012fab  test    eax, eax
0x180012fad  jns     short loc_180012FDD
0x180012faf  mov     rcx, [rbp+5Fh]; this
0x180012fb3  mov     r9d, eax; char *
0x180012fb6  lea     r8, aOnecoreBaseWin_0; "onecore\\base\\windows.storage\\src\\ca"...
0x180012fbd  mov     edx, 0DFh; void *
0x180012fc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012fc7  nop
0x180012fc8  mov     rcx, [rbp+57h+Block]; Block
0x180012fcc  test    rcx, rcx
0x180012fcf  jz      short loc_180012FD6
0x180012fd1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012fd6  mov     eax, ebx
0x180012fd8  jmp     loc_18001325F
0x180012fdd  mov     [rbp+57h+StringSid], 0
0x180012fe5  lea     rdx, [rbp+57h+StringSid]; StringSid
0x180012fe9  mov     r14, [rbp+57h+Block]
0x180012fed  mov     rcx, [r14]; Sid
0x180012ff0  call    cs:__imp_ConvertSidToStringSidW
0x180012ff6  test    eax, eax
0x180012ff8  jnz     short loc_180013025
0x180012ffa  mov     rcx, [rbp+5Fh]; this
0x180012ffe  lea     r8, aOnecoreBaseWin_0; "onecore\\base\\windows.storage\\src\\ca"...
0x180013005  mov     edx, 0E2h; void *
0x18001300a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001300f  mov     ebx, eax
0x180013011  lea     rcx, [rbp+57h+StringSid]
0x180013015  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001301a  nop
0x18001301b  test    r14, r14
0x18001301e  jz      short loc_180012FD6
0x180013020  mov     rcx, r14
0x180013023  jmp     short loc_180012FD1
0x180013025  mov     rdx, [rbp+57h+StringSid]; unsigned __int16 *
0x180013029  lea     rcx, [rbp+57h+var_60]; this
0x18001302d  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180013032  mov     rdx, [r15+10h]; unsigned __int16 *
0x180013036  lea     rcx, [rbp+57h+var_80]; this
0x18001303a  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18001303f  mov     [rbp+57h+var_C8], 0
0x180013047  lea     r9, [rbp+57h+string]; string
0x18001304b  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18001304f  mov     edx, 32h ; '2'; length
0x180013054  lea     rcx, ?RuntimeClass_Windows_Internal_CapabilityAccess_CapabilityAccess@@3QBGB; "Windows.Internal.CapabilityAccess.Capab"...
0x18001305b  call    cs:__imp_WindowsCreateStringReference
0x180013061  test    eax, eax
0x180013063  jns     short loc_18001307A
0x180013065  xor     r9d, r9d; lpArguments
0x180013068  xor     r8d, r8d; nNumberOfArguments
0x18001306b  lea     edx, [r9+1]; dwExceptionFlags
0x18001306f  mov     ecx, 0C000000Dh; dwExceptionCode
0x180013074  call    cs:__imp_RaiseException
0x18001307a  mov     rbx, [rbp+57h+string]
0x18001307e  lea     rcx, [rbp+57h+var_C8]
0x180013082  call    ?InternalRelease@?$ComPtr@UIPersistFile@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(void)
0x180013087  lea     r8, [rbp+57h+var_C8]
0x18001308b  lea     rdx, _GUID_518f3880_4e5c_4524_ab03_cd01336b2178
0x180013092  mov     rcx, rbx
0x180013095  call    cs:__imp_RoGetActivationFactory
0x18001309b  mov     ebx, eax
0x18001309d  test    eax, eax
0x18001309f  jns     short loc_1800130C8
0x1800130a1  mov     rcx, [rbp+5Fh]; this
0x1800130a5  mov     r9d, eax; char *
0x1800130a8  lea     r8, aOnecoreBaseWin_0; "onecore\\base\\windows.storage\\src\\ca"...
0x1800130af  mov     edx, 0E9h; void *
0x1800130b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800130b9  nop
0x1800130ba  lea     rcx, [rbp+57h+var_C8]
0x1800130be  call    ?InternalRelease@?$ComPtr@UIPersistFile@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(void)
0x1800130c3  jmp     loc_180013011
0x1800130c8  mov     [rbp+57h+var_D0], 0
0x1800130d0  cmp     qword ptr [r15], 0
0x1800130d4  jnz     loc_18001319E
0x1800130da  mov     [rbp+57h+var_B8], 0
0x1800130e2  xor     edx, edx
0x1800130e4  lea     rcx, [rbp+57h+var_B8]
0x1800130e8  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800130ed  lea     rdx, [rbp+57h+var_B8]; HSTRING *
0x1800130f1  mov     rcx, [r15+8]; void *
0x1800130f5  call    ?GetPackageFamilyNameFromToken@@YAJPEAXPEAPEAUHSTRING__@@@Z; GetPackageFamilyNameFromToken(void *,HSTRING__ * *)
0x1800130fa  mov     ebx, eax
0x1800130fc  test    eax, eax
0x1800130fe  jns     short loc_18001312E
0x180013100  mov     edx, 0EFh; void *
0x180013105  lea     r8, aOnecoreBaseWin_0; "onecore\\base\\windows.storage\\src\\ca"...
0x18001310c  mov     r9d, ebx; char *
0x18001310f  mov     rcx, [rbp+5Fh]; this
0x180013113  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013118  nop
0x180013119  lea     rcx, [rbp+57h+var_B8]
0x18001311d  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180013122  nop
0x180013123  lea     rcx, [rbp+57h+var_D0]
0x180013127  call    ?InternalRelease@?$ComPtr@UIPersistFile@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(void)
0x18001312c  jmp     short loc_1800130BA
0x18001312e  mov     rdi, [rbp+57h+var_C8]
0x180013132  mov     rax, [rdi]
0x180013135  mov     rbx, [rax+30h]
0x180013139  lea     rcx, [rbp+57h+var_D0]
0x18001313d  call    ?InternalRelease@?$ComPtr@UIPersistFile@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(void)
0x180013142  lea     rax, [rbp+57h+var_D0]
0x180013146  mov     qword ptr [rsp+110h+var_F0], rax
0x18001314b  mov     r9, [rbp+57h+var_B8]
0x18001314f  mov     r8, [rbp+57h+var_80]
0x180013153  mov     rdx, [rbp+57h+var_60]
0x180013157  mov     rcx, rdi
0x18001315a  mov     rax, rbx
0x18001315d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013162  mov     ebx, eax
0x180013164  test    eax, eax
0x180013166  jns     short loc_18001316F
0x180013168  mov     edx, 0F0h
0x18001316d  jmp     short loc_180013105
0x18001316f  lea     rcx, [rbp+57h+var_B8]
0x180013173  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180013178  mov     [rbp+57h+var_B0], 0
0x18001317f  mov     rcx, [rbp+57h+var_D0]
0x180013183  mov     rax, [rcx]
0x180013186  mov     dl, 1
0x180013188  mov     rax, [rax+58h]
0x18001318c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013191  mov     ebx, eax
0x180013193  test    eax, eax
0x180013195  jns     short loc_180013205
0x180013197  mov     edx, 0FCh
0x18001319c  jmp     short loc_1800131ED
0x18001319e  mov     rsi, [rbp+57h+var_C8]
0x1800131a2  mov     rax, [rsi]
0x1800131a5  mov     rdi, [rax+38h]
0x1800131a9  lea     rcx, [rbp+57h+var_D0]
0x1800131ad  call    ?InternalRelease@?$ComPtr@UIPersistFile@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(void)
0x1800131b2  mov     ebx, [r15+18h]
0x1800131b6  mov     rcx, [r15]; Process
0x1800131b9  call    cs:__imp_GetProcessId
0x1800131bf  lea     rcx, [rbp+57h+var_D0]
0x1800131c3  mov     [rsp+110h+var_E8], rcx
0x1800131c8  mov     [rsp+110h+var_F0], ebx; int
0x1800131cc  mov     r9d, eax
0x1800131cf  mov     r8, [rbp+57h+var_80]
0x1800131d3  mov     rdx, [rbp+57h+var_60]
0x1800131d7  mov     rcx, rsi
0x1800131da  mov     rax, rdi
0x1800131dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131e2  mov     ebx, eax
0x1800131e4  test    eax, eax
0x1800131e6  jns     short loc_180013178
0x1800131e8  mov     edx, 0F8h; void *
0x1800131ed  mov     rcx, [rbp+5Fh]; this
0x1800131f1  mov     r9d, ebx; char *
0x1800131f4  lea     r8, aOnecoreBaseWin_0; "onecore\\base\\windows.storage\\src\\ca"...
0x1800131fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013200  jmp     loc_180013123
0x180013205  mov     rcx, [rbp+57h+var_D0]
0x180013209  mov     rax, [rcx]
0x18001320c  lea     rdx, [rbp+57h+var_B0]
0x180013210  mov     rax, [rax+98h]
0x180013217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001321c  mov     ebx, eax
0x18001321e  test    eax, eax
0x180013220  jns     short loc_180013229
0x180013222  mov     edx, 0FDh
0x180013227  jmp     short loc_1800131ED
0x180013229  mov     rcx, [r15+20h]
0x18001322d  mov     eax, [rbp+57h+var_B0]
0x180013230  mov     [rcx], eax
0x180013232  lea     rcx, [rbp+57h+var_D0]
0x180013236  call    ?InternalRelease@?$ComPtr@UIPersistFile@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(void)
0x18001323b  nop
0x18001323c  lea     rcx, [rbp+57h+var_C8]
0x180013240  call    ?InternalRelease@?$ComPtr@UIPersistFile@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(void)
0x180013245  nop
0x180013246  lea     rcx, [rbp+57h+StringSid]
0x18001324a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001324f  nop
0x180013250  test    r14, r14
0x180013253  jz      short loc_18001325D
0x180013255  mov     rcx, r14; Block
0x180013258  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001325d  xor     eax, eax
0x18001325f  mov     rcx, [rbp+57h+var_40]
0x180013263  xor     rcx, rsp; StackCookie
0x180013266  call    __security_check_cookie
0x18001326b  add     rsp, 0E8h
0x180013272  pop     r15
0x180013274  pop     r14
0x180013276  pop     rdi
0x180013277  pop     rsi
0x180013278  pop     rbx
0x180013279  pop     rbp
0x18001327a  retn
```
