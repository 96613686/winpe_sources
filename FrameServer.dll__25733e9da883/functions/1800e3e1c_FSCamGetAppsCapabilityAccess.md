# FSCamGetAppsCapabilityAccess

- ea: `0x1800e3e1c`
- end: `0x1800e428a`
- name: `FSCamGetAppsCapabilityAccess`
- size: `1134`
- prototype: `__int64 __fastcall(PCNZWCH sourceString)`
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18007d914`
- `0x18007f710`
- `0x18007fde0`

## callees

- `0x180003e20`
- `0x18000478c`
- `0x180008cf0`
- `0x180009608`
- `0x180017bb4`
- `0x180036698`
- `0x180036730`
- `0x1800e3a3c`
- `0x1800e3a94`
- `0x1800e3ab4`
- `0x1800e3e1c`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e3fd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4126`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e3fd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4126`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800e4038`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800e4038`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800e3fcf`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800e3fcf`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e410a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e410a`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800e414f`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800e414f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800e3f79`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800e3f79`

## string_xrefs

- `0x1800e3efe`: `Windows.Internal.CapabilityAccess.CapabilityAccess`

## pseudocode

```c
__int64 __fastcall FSCamGetAppsCapabilityAccess(PCNZWCH sourceString, unsigned int a2, void *a3)
{
  signed int v6; // ebx
  __int64 v7; // rdx
  HSTRING *v8; // rax
  HSTRING v9; // rdi
  int ActivationFactory; // eax
  __int64 v11; // rdx
  HSTRING *v12; // rax
  char v13; // r15
  signed int LastError; // eax
  HRESULT v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  IUnknown *v18; // rbx
  struct IUnknownVtbl *lpVtbl; // rax
  ULONG (__stdcall *Release)(IUnknown *); // r14
  int v21; // eax
  unsigned int v22; // edi
  const wchar_t *v23; // rax
  const wchar_t *v24; // rax
  const wchar_t *v25; // rax
  IUnknown *pProxy; // [rsp+40h] [rbp-C0h] BYREF
  int v28; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v29; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING v30; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING v31; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING string; // [rsp+68h] [rbp-98h] BYREF
  struct _EXCEPTION_RECORD pExceptionRecord; // [rsp+70h] [rbp-90h] BYREF

  pProxy = 0;
  v29 = 0;
  v28 = 0;
  v31 = 0;
  v30 = 0;
  if ( !sourceString )
  {
    if ( !g_wppLevels )
    {
LABEL_43:
      v22 = -2147024891;
      goto LABEL_51;
    }
    v6 = -2147024809;
    v7 = 10;
    goto LABEL_4;
  }
  v8 = wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
         &string,
         sourceString);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::operator=(
    &v30,
    v8);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
  v9 = v30;
  if ( !v30 )
  {
    ActivationFactory = -2147024882;
    v6 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_42;
    v11 = (unsigned int)((_DWORD)v30 + 11);
    goto LABEL_8;
  }
  v12 = wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
          &string,
          L"Windows.Internal.CapabilityAccess.CapabilityAccess");
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::operator=(
    &v31,
    v12);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
  if ( !v31 )
  {
    ActivationFactory = -2147024882;
    v6 = -2147024882;
    if ( g_wppLevels )
    {
      v11 = 12;
LABEL_8:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        &WPP_b3b5bd672325328eaa75912f82e6dc75_Traceguids,
        0,
        ActivationFactory);
      goto LABEL_42;
    }
    goto LABEL_42;
  }
  pProxy = 0;
  ActivationFactory = RoGetActivationFactory(v31, &GUID_518f3880_4e5c_4524_ab03_cd01336b2178, &pProxy);
  v6 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v13 = 0;
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 14, &WPP_b3b5bd672325328eaa75912f82e6dc75_Traceguids);
    if ( a3 )
    {
      if ( !ImpersonateLoggedOnUser(a3) )
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        if ( v6 < 0 )
        {
          if ( g_wppLevels )
          {
            v7 = 15;
LABEL_4:
            WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_b3b5bd672325328eaa75912f82e6dc75_Traceguids, 0, v6);
            goto LABEL_42;
          }
          goto LABEL_42;
        }
      }
      v13 = 1;
    }
    v15 = CoSetProxyBlanket(
            pProxy,
            0xFFFFFFFF,
            0xFFFFFFFF,
            (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
            0,
            3u,
            (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
            0x40u);
    v6 = v15;
    if ( v15 >= 0 )
    {
      v17 = v29;
      v18 = pProxy;
      lpVtbl = pProxy->lpVtbl;
      v29 = 0;
      Release = lpVtbl[2].Release;
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      v15 = ((__int64 (__fastcall *)(IUnknown *, HSTRING, _QWORD, _QWORD, __int64 *))Release)(v18, v9, a2, 0, &v29);
      v6 = v15;
      if ( v15 >= 0 )
      {
        v15 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v29 + 152LL))(v29, &v28);
        v6 = v15;
        if ( v15 < 0 && g_wppLevels )
        {
          v16 = 18;
          goto LABEL_36;
        }
      }
      else if ( g_wppLevels )
      {
        v16 = 17;
        goto LABEL_36;
      }
    }
    else if ( g_wppLevels )
    {
      v16 = 16;
LABEL_36:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_b3b5bd672325328eaa75912f82e6dc75_Traceguids, 0, v15);
    }
    if ( v13 && !RevertToSelf() )
    {
      memset_0(&pExceptionRecord, 0, sizeof(pExceptionRecord));
      v21 = GetLastError();
      if ( v21 > 0 )
        v21 = (unsigned __int16)v21 | 0x80070000;
      pExceptionRecord.ExceptionCode = v21;
      pExceptionRecord.ExceptionFlags = 1;
      RaiseFailFastException(&pExceptionRecord, 0, 1u);
    }
    goto LABEL_42;
  }
  if ( g_wppLevels )
  {
    v11 = 13;
    goto LABEL_8;
  }
LABEL_42:
  if ( v28 != 3 )
    goto LABEL_43;
  if ( v6 >= 0 )
  {
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
    {
      v25 = L"null";
      if ( sourceString )
        v25 = sourceString;
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        21,
        (unsigned int)&WPP_b3b5bd672325328eaa75912f82e6dc75_Traceguids,
        a2,
        (__int64)v25);
    }
    goto LABEL_59;
  }
  if ( v6 != -2147024891 )
  {
    if ( byte_18010EC4D )
    {
      v23 = L"null";
      if ( sourceString )
        v23 = sourceString;
      WPP_SF_DDS(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        19,
        (unsigned int)&WPP_b3b5bd672325328eaa75912f82e6dc75_Traceguids,
        v6,
        a2,
        (__int64)v23);
    }
LABEL_59:
    v22 = v6;
    goto LABEL_60;
  }
  v22 = -2147024891;
LABEL_51:
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v24 = L"null";
    if ( sourceString )
      v24 = sourceString;
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      20,
      (unsigned int)&WPP_b3b5bd672325328eaa75912f82e6dc75_Traceguids,
      a2,
      (__int64)v24);
  }
LABEL_60:
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v30);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v31);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v29);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&pProxy);
  return v22;
}

```

## disassembly

```asm
0x1800e3e1c  push    rbp
0x1800e3e1e  push    rbx
0x1800e3e1f  push    rsi
0x1800e3e20  push    rdi
0x1800e3e21  push    r12
0x1800e3e23  push    r14
0x1800e3e25  push    r15
0x1800e3e27  lea     rbp, [rsp-20h]
0x1800e3e2c  sub     rsp, 120h
0x1800e3e33  mov     rax, cs:__security_cookie
0x1800e3e3a  xor     rax, rsp
0x1800e3e3d  mov     [rbp+50h+var_40], rax
0x1800e3e41  mov     [rsp+150h+pProxy], 0
0x1800e3e4a  mov     r14, r8
0x1800e3e4d  mov     [rsp+150h+var_100], 0
0x1800e3e56  mov     r12d, edx
0x1800e3e59  mov     [rsp+150h+var_108], 0
0x1800e3e61  mov     rsi, rcx
0x1800e3e64  mov     [rsp+150h+var_F0], 0
0x1800e3e6d  mov     [rsp+150h+var_F8], 0
0x1800e3e76  test    rcx, rcx
0x1800e3e79  jnz     short loc_1800E3EB3
0x1800e3e7b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e3e82  jb      loc_1800E415C
0x1800e3e88  mov     ebx, 80070057h
0x1800e3e8d  lea     edx, [rcx+0Ah]
0x1800e3e90  mov     [rsp+150h+dwAuthnLevel], ebx
0x1800e3e94  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e3e9b  lea     r8, WPP_b3b5bd672325328eaa75912f82e6dc75_Traceguids
0x1800e3ea2  xor     r9d, r9d
0x1800e3ea5  mov     rcx, [rcx+10h]
0x1800e3ea9  call    WPP_SF_qD
0x1800e3eae  jmp     loc_1800E4155
0x1800e3eb3  mov     rdx, rsi; sourceString
0x1800e3eb6  lea     rcx, [rsp+150h+string]; string
0x1800e3ebb  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800e3ec0  mov     rdx, rax
0x1800e3ec3  lea     rcx, [rsp+150h+var_F8]
0x1800e3ec8  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &&)
0x1800e3ecd  lea     rcx, [rsp+150h+string]
0x1800e3ed2  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800e3ed7  mov     rdi, [rsp+150h+var_F8]
0x1800e3edc  test    rdi, rdi
0x1800e3edf  jnz     short loc_1800E3EFE
0x1800e3ee1  mov     eax, 8007000Eh
0x1800e3ee6  mov     ebx, eax
0x1800e3ee8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e3eef  jb      loc_1800E4155
0x1800e3ef5  lea     edx, [rdi+0Bh]
0x1800e3ef8  mov     [rsp+150h+dwAuthnLevel], eax
0x1800e3efc  jmp     short loc_1800E3E94
0x1800e3efe  lea     rdx, ?RuntimeClass_Windows_Internal_CapabilityAccess_CapabilityAccess@@3QBGB; "Windows.Internal.CapabilityAccess.Capab"...
0x1800e3f05  lea     rcx, [rsp+150h+string]; string
0x1800e3f0a  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800e3f0f  mov     rdx, rax
0x1800e3f12  lea     rcx, [rsp+150h+var_F0]
0x1800e3f17  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &&)
0x1800e3f1c  lea     rcx, [rsp+150h+string]
0x1800e3f21  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800e3f26  mov     rbx, [rsp+150h+var_F0]
0x1800e3f2b  test    rbx, rbx
0x1800e3f2e  jnz     short loc_1800E3F4B
0x1800e3f30  mov     eax, 8007000Eh
0x1800e3f35  mov     ebx, eax
0x1800e3f37  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e3f3e  jb      loc_1800E4155
0x1800e3f44  mov     edx, 0Ch
0x1800e3f49  jmp     short loc_1800E3EF8
0x1800e3f4b  mov     rcx, [rsp+150h+pProxy]
0x1800e3f50  mov     [rsp+150h+pProxy], 0
0x1800e3f59  test    rcx, rcx
0x1800e3f5c  jz      short loc_1800E3F6A
0x1800e3f5e  mov     rax, [rcx]
0x1800e3f61  mov     rax, [rax+10h]
0x1800e3f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3f6a  lea     r8, [rsp+150h+pProxy]
0x1800e3f6f  mov     rcx, rbx
0x1800e3f72  lea     rdx, _GUID_518f3880_4e5c_4524_ab03_cd01336b2178
0x1800e3f79  call    cs:__imp_RoGetActivationFactory
0x1800e3f7f  mov     ebx, eax
0x1800e3f81  test    eax, eax
0x1800e3f83  jns     short loc_1800E3F9C
0x1800e3f85  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e3f8c  jb      loc_1800E4155
0x1800e3f92  mov     edx, 0Dh
0x1800e3f97  jmp     loc_1800E3EF8
0x1800e3f9c  xor     r15b, r15b
0x1800e3f9f  cmp     cs:byte_18010EC4D, 8
0x1800e3fa6  jb      short loc_1800E3FC7
0x1800e3fa8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e3faf  lea     r8, WPP_b3b5bd672325328eaa75912f82e6dc75_Traceguids
0x1800e3fb6  mov     edx, 0Eh
0x1800e3fbb  mov     rcx, [rcx+0D8h]
0x1800e3fc2  call    WPP_SF_
0x1800e3fc7  test    r14, r14
0x1800e3fca  jz      short loc_1800E400C
0x1800e3fcc  mov     rcx, r14; hToken
0x1800e3fcf  call    cs:__imp_ImpersonateLoggedOnUser
0x1800e3fd5  test    eax, eax
0x1800e3fd7  jnz     short loc_1800E4009
0x1800e3fd9  call    cs:__imp_GetLastError
0x1800e3fdf  mov     ebx, eax
0x1800e3fe1  test    eax, eax
0x1800e3fe3  jle     short loc_1800E3FEE
0x1800e3fe5  movzx   ebx, ax
0x1800e3fe8  or      ebx, 80070000h
0x1800e3fee  test    ebx, ebx
0x1800e3ff0  jns     short loc_1800E4009
0x1800e3ff2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e3ff9  jb      loc_1800E4155
0x1800e3fff  mov     edx, 0Fh
0x1800e4004  jmp     loc_1800E3E90
0x1800e4009  mov     r15b, 1
0x1800e400c  mov     rcx, [rsp+150h+pProxy]; pProxy
0x1800e4011  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x1800e4015  mov     [rsp+150h+dwCapabilities], 40h ; '@'; dwCapabilities
0x1800e401d  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x1800e4020  mov     [rsp+150h+pAuthInfo], r9; pAuthInfo
0x1800e4025  mov     r8d, edx; dwAuthzSvc
0x1800e4028  mov     [rsp+150h+dwImpLevel], 3; dwImpLevel
0x1800e4030  mov     [rsp+150h+dwAuthnLevel], 0; dwAuthnLevel
0x1800e4038  call    cs:__imp_CoSetProxyBlanket
0x1800e403e  mov     ebx, eax
0x1800e4040  test    eax, eax
0x1800e4042  jns     short loc_1800E405B
0x1800e4044  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e404b  jb      loc_1800E4105
0x1800e4051  mov     edx, 10h
0x1800e4056  jmp     loc_1800E40E7
0x1800e405b  mov     rcx, [rsp+150h+var_100]
0x1800e4060  mov     rbx, [rsp+150h+pProxy]
0x1800e4065  mov     rax, [rbx]
0x1800e4068  mov     [rsp+150h+var_100], 0
0x1800e4071  mov     r14, [rax+40h]
0x1800e4075  test    rcx, rcx
0x1800e4078  jz      short loc_1800E4086
0x1800e407a  mov     rax, [rcx]
0x1800e407d  mov     rax, [rax+10h]
0x1800e4081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4086  lea     rax, [rsp+150h+var_100]
0x1800e408b  xor     r9d, r9d
0x1800e408e  mov     qword ptr [rsp+150h+dwAuthnLevel], rax
0x1800e4093  mov     r8d, r12d
0x1800e4096  mov     rax, r14
0x1800e4099  mov     rdx, rdi
0x1800e409c  mov     rcx, rbx
0x1800e409f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e40a4  mov     ebx, eax
0x1800e40a6  test    eax, eax
0x1800e40a8  jns     short loc_1800E40BA
0x1800e40aa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e40b1  jb      short loc_1800E4105
0x1800e40b3  mov     edx, 11h
0x1800e40b8  jmp     short loc_1800E40E7
0x1800e40ba  mov     rcx, [rsp+150h+var_100]
0x1800e40bf  lea     rdx, [rsp+150h+var_108]
0x1800e40c4  mov     rax, [rcx]
0x1800e40c7  mov     rax, [rax+98h]
0x1800e40ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e40d3  mov     ebx, eax
0x1800e40d5  test    eax, eax
0x1800e40d7  jns     short loc_1800E4105
0x1800e40d9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e40e0  jb      short loc_1800E4105
0x1800e40e2  mov     edx, 12h
0x1800e40e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e40ee  lea     r8, WPP_b3b5bd672325328eaa75912f82e6dc75_Traceguids
0x1800e40f5  xor     r9d, r9d
0x1800e40f8  mov     [rsp+150h+dwAuthnLevel], eax
0x1800e40fc  mov     rcx, [rcx+10h]
0x1800e4100  call    WPP_SF_qD
0x1800e4105  test    r15b, r15b
0x1800e4108  jz      short loc_1800E4155
0x1800e410a  call    cs:__imp_RevertToSelf
0x1800e4110  test    eax, eax
0x1800e4112  jnz     short loc_1800E4155
0x1800e4114  xor     edx, edx; Val
0x1800e4116  lea     rcx, [rsp+150h+pExceptionRecord]; void *
0x1800e411b  mov     r8d, 98h; Size
0x1800e4121  call    memset_0
0x1800e4126  call    cs:__imp_GetLastError
0x1800e412c  test    eax, eax
0x1800e412e  jle     short loc_1800E4138
0x1800e4130  movzx   eax, ax
0x1800e4133  or      eax, 80070000h
0x1800e4138  xor     edx, edx; pContextRecord
0x1800e413a  mov     [rsp+150h+pExceptionRecord.ExceptionCode], eax
0x1800e413e  lea     rcx, [rsp+150h+pExceptionRecord]; pExceptionRecord
0x1800e4143  mov     [rsp+150h+pExceptionRecord.ExceptionFlags], 1
0x1800e414b  lea     r8d, [rdx+1]; dwFlags
0x1800e414f  call    cs:__imp_RaiseFailFastException
0x1800e4155  cmp     [rsp+150h+var_108], 3
0x1800e415a  jz      short loc_1800E4163
0x1800e415c  mov     edi, 80070005h
0x1800e4161  jmp     short loc_1800E41C2
0x1800e4163  test    ebx, ebx
0x1800e4165  jns     loc_1800E4202
0x1800e416b  mov     edi, 80070005h
0x1800e4170  cmp     ebx, edi
0x1800e4172  jz      short loc_1800E41C0
0x1800e4174  cmp     cs:byte_18010EC4D, 1
0x1800e417b  jb      loc_1800E4240
0x1800e4181  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e4188  lea     rax, aNull; "null"
0x1800e418f  test    rsi, rsi
0x1800e4192  lea     r8, WPP_b3b5bd672325328eaa75912f82e6dc75_Traceguids
0x1800e4199  mov     edx, 13h
0x1800e419e  mov     r9d, ebx
0x1800e41a1  cmovnz  rax, rsi
0x1800e41a5  mov     rcx, [rcx+0D8h]
0x1800e41ac  mov     qword ptr [rsp+150h+dwImpLevel], rax
0x1800e41b1  mov     [rsp+150h+dwAuthnLevel], r12d
0x1800e41b6  call    WPP_SF_DDS
0x1800e41bb  jmp     loc_1800E4240
0x1800e41c0  mov     edi, ebx
0x1800e41c2  cmp     cs:byte_18010EC4D, 8
0x1800e41c9  jb      short loc_1800E4242
0x1800e41cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e41d2  lea     rax, aNull; "null"
0x1800e41d9  test    rsi, rsi
0x1800e41dc  lea     r8, WPP_b3b5bd672325328eaa75912f82e6dc75_Traceguids
0x1800e41e3  mov     edx, 14h
0x1800e41e8  mov     r9d, r12d
0x1800e41eb  cmovnz  rax, rsi
0x1800e41ef  mov     rcx, [rcx+0D8h]
0x1800e41f6  mov     qword ptr [rsp+150h+dwAuthnLevel], rax
0x1800e41fb  call    WPP_SF_DS
0x1800e4200  jmp     short loc_1800E4242
0x1800e4202  cmp     cs:byte_18010EC4D, 8
0x1800e4209  jb      short loc_1800E4240
0x1800e420b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e4212  lea     rax, aNull; "null"
0x1800e4219  test    rsi, rsi
0x1800e421c  lea     r8, WPP_b3b5bd672325328eaa75912f82e6dc75_Traceguids
0x1800e4223  mov     edx, 15h
0x1800e4228  mov     r9d, r12d
0x1800e422b  cmovnz  rax, rsi
0x1800e422f  mov     rcx, [rcx+0D8h]
0x1800e4236  mov     qword ptr [rsp+150h+dwAuthnLevel], rax
0x1800e423b  call    WPP_SF_DS
0x1800e4240  mov     edi, ebx
0x1800e4242  lea     rcx, [rsp+150h+var_F8]
0x1800e4247  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800e424c  lea     rcx, [rsp+150h+var_F0]
0x1800e4251  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800e4256  lea     rcx, [rsp+150h+var_100]; void *
0x1800e425b  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800e4260  lea     rcx, [rsp+150h+pProxy]; void *
0x1800e4265  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800e426a  mov     eax, edi
0x1800e426c  mov     rcx, [rbp+50h+var_40]
0x1800e4270  xor     rcx, rsp; StackCookie
0x1800e4273  call    __security_check_cookie
0x1800e4278  add     rsp, 120h
0x1800e427f  pop     r15
0x1800e4281  pop     r14
0x1800e4283  pop     r12
0x1800e4285  pop     rdi
0x1800e4286  pop     rsi
0x1800e4287  pop     rbx
0x1800e4288  pop     rbp
0x1800e4289  retn
```
