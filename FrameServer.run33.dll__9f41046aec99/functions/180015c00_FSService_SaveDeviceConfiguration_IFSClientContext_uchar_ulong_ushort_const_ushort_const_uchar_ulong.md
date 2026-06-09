# FSService::SaveDeviceConfiguration(IFSClientContext *,uchar *,ulong,ushort const *,ushort const *,uchar *,ulong)

- ea: `0x180015c00`
- end: `0x1800163a3`
- name: `?SaveDeviceConfiguration@FSService@@UEAAJPEAUIFSClientContext@@PEAEKPEBG21K@Z`
- size: `1955`
- prototype: `int(FSService *__hidden this, struct IFSClientContext *, unsigned __int8 *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180001408`
- `0x18000162c`
- `0x180005b94`
- `0x180005e78`
- `0x180008cf0`
- `0x180009494`
- `0x180009608`
- `0x180009f50`
- `0x18000a600`
- `0x18000a6cc`
- `0x18000a91c`
- `0x180015c00`
- `0x180017014`
- `0x180017a3c`
- `0x180017a64`
- `0x1800181f0`
- `0x18002ba64`
- `0x180031708`
- `0x1800356a4`
- `0x18003730c`
- `0x1800e9240`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800161ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800161f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800161ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800161f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016180`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016180`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015f33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015f7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015f33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015f7f`
- `RPCRT4!RpcBindingFree` at `0x180015db1`
- `RPCRT4!RpcBindingFree` at `0x180015dee`
- `RPCRT4!RpcBindingFree` at `0x180015db1`
- `RPCRT4!RpcBindingFree` at `0x180015dee`
- `RPCRT4!RpcServerInqBindingHandle` at `0x180015dca`
- `RPCRT4!RpcServerInqBindingHandle` at `0x180015e09`
- `RPCRT4!RpcServerInqBindingHandle` at `0x180015dca`
- `RPCRT4!RpcServerInqBindingHandle` at `0x180015e09`
- `RPCRT4!RpcImpersonateClient` at `0x180015e32`
- `RPCRT4!RpcImpersonateClient` at `0x180015e40`
- `RPCRT4!RpcImpersonateClient` at `0x180015e32`
- `RPCRT4!RpcImpersonateClient` at `0x180015e40`
- `RPCRT4!RpcRevertToSelfEx` at `0x180016170`
- `RPCRT4!RpcRevertToSelfEx` at `0x180016250`
- `RPCRT4!RpcRevertToSelfEx` at `0x180016170`
- `RPCRT4!RpcRevertToSelfEx` at `0x180016250`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180015f75`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180015f75`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015e7c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015f29`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015e7c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015f29`

## pseudocode

```c
__int64 __fastcall FSService::SaveDeviceConfiguration(
        FSService *this,
        struct IFSClientContext *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int8 *a7,
        unsigned int a8)
{
  size_t v9; // r13
  unsigned __int8 *v11; // r14
  const unsigned __int16 *v12; // r15
  unsigned int v13; // edi
  const char *v14; // rcx
  const char *v15; // rax
  signed int v16; // edi
  __int64 v17; // rdx
  __int64 v18; // rdx
  RPC_BINDING_HANDLE v19; // rbx
  signed int LastError; // eax
  __int64 v21; // rdx
  __int64 unique; // rax
  PSID *v23; // rbx
  signed int v24; // eax
  signed int v25; // eax
  int v26; // eax
  unsigned __int64 v27; // r11
  __int64 v28; // rdx
  unsigned __int64 v29; // r11
  const void *v30; // rax
  unsigned int v31; // r15d
  int v32; // eax
  int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // rdx
  int v36; // r8d
  int v37; // r9d
  int v38; // ecx
  wchar_t *v39; // rax
  RPC_BINDING_HANDLE BindingHandle; // [rsp+58h] [rbp-39h] BYREF
  struct IFSConfigurationKey *v42; // [rsp+60h] [rbp-31h] BYREF
  RPC_BINDING_HANDLE v43; // [rsp+68h] [rbp-29h] BYREF
  LPWSTR StringSid; // [rsp+70h] [rbp-21h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+78h] [rbp-19h] BYREF
  unsigned __int64 v46; // [rsp+80h] [rbp-11h] BYREF
  unsigned __int64 v47; // [rsp+88h] [rbp-9h] BYREF
  struct IFSConfiguration *v48; // [rsp+90h] [rbp-1h] BYREF
  unsigned __int64 v49; // [rsp+98h] [rbp+7h] BYREF
  LPVOID TokenInformation; // [rsp+A0h] [rbp+Fh] BYREF
  DWORD TokenInformationLength; // [rsp+E0h] [rbp+4Fh] BYREF
  void *Buf1; // [rsp+E8h] [rbp+57h]

  Buf1 = a3;
  v9 = a4;
  v49 = 0;
  v46 = 0;
  StringSid = 0;
  v47 = 0;
  BindingHandle = 0;
  TokenInformation = 0;
  TokenInformationLength = 0;
  v42 = 0;
  v48 = 0;
  v11 = a7;
  v12 = a6;
  v13 = a8;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v14 = L"<null>";
    v15 = L"<null>";
    if ( a6 )
      v15 = (const char *)a6;
    if ( a5 )
      v14 = (const char *)a5;
    WPP_SF_qqDSSqd(*((_QWORD *)WPP_GLOBAL_Control + 27), (char)a3, a4, (__int64)v14, (__int64)v15, (char)a7, a8);
    a3 = (unsigned __int8 *)Buf1;
  }
  if ( !a2 )
  {
    v16 = -2147024809;
    if ( g_wppLevels )
    {
      v17 = 286;
LABEL_98:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v17,
        &WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids,
        this,
        -2147024809);
      goto LABEL_99;
    }
    goto LABEL_99;
  }
  if ( !a5 )
  {
    v16 = -2147024809;
    if ( g_wppLevels )
    {
      v17 = 287;
      goto LABEL_98;
    }
LABEL_99:
    v31 = a8;
LABEL_100:
    if ( byte_18010EC4D )
    {
      v35 = 307;
      goto LABEL_102;
    }
    goto LABEL_103;
  }
  if ( !v12 )
  {
    v16 = -2147024809;
    if ( g_wppLevels )
    {
      v17 = 288;
      goto LABEL_98;
    }
    goto LABEL_99;
  }
  if ( !a3 || (_DWORD)v9 != 32 )
  {
    v16 = -2147024809;
    if ( g_wppLevels )
    {
      v17 = 289;
      goto LABEL_98;
    }
    goto LABEL_99;
  }
  if ( !v11 )
  {
    if ( !v13 )
      goto LABEL_20;
LABEL_25:
    v16 = -2147024809;
    if ( g_wppLevels )
    {
      v17 = 290;
      goto LABEL_98;
    }
    goto LABEL_99;
  }
  if ( !v13 )
    goto LABEL_25;
LABEL_20:
  if ( (*(unsigned int (__fastcall **)(struct IFSClientContext *))(*(_QWORD *)a2 + 304LL))(a2) )
  {
    v16 = -2147024891;
    if ( !g_wppLevels )
      goto LABEL_99;
    v18 = 291;
LABEL_23:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids, this, v16);
    goto LABEL_99;
  }
  BindingHandle = 0;
  if ( RpcServerInqBindingHandle(&BindingHandle) )
  {
    v19 = BindingHandle;
    if ( BindingHandle )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&Binding);
      v43 = v19;
      RpcBindingFree(&v43);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&Binding);
    }
    BindingHandle = 0;
    v16 = RpcServerInqBindingHandle(&BindingHandle) | 0x80010000;
    if ( !g_wppLevels )
      goto LABEL_99;
    v18 = 292;
    goto LABEL_23;
  }
  if ( RpcImpersonateClient(BindingHandle) )
  {
    v16 = RpcImpersonateClient(BindingHandle) | 0x80010000;
    if ( !g_wppLevels )
      goto LABEL_99;
    v18 = 293;
    goto LABEL_23;
  }
  if ( !GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFBLL, TokenUser, 0, 0, &TokenInformationLength) )
  {
    LastError = GetLastError();
    v16 = LastError;
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0x80070000;
    if ( (int)(v16 + 0x80000000) >= 0 && v16 != -2147024774 )
    {
      if ( !g_wppLevels )
      {
LABEL_94:
        v31 = a8;
LABEL_95:
        RpcRevertToSelfEx(BindingHandle);
        goto LABEL_100;
      }
      v21 = 294;
LABEL_42:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, &WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids, this, v16);
      goto LABEL_94;
    }
  }
  unique = wil::make_unique_nothrow<unsigned char [0]>(&v43, TokenInformationLength);
  wistd::unique_ptr<unsigned long [0],wistd::default_delete<unsigned long [0]>>::operator=(&TokenInformation, unique);
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v43);
  v23 = (PSID *)TokenInformation;
  if ( !TokenInformation )
  {
    v16 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_94;
    v21 = 295;
    goto LABEL_42;
  }
  if ( !GetTokenInformation(
          (HANDLE)0xFFFFFFFFFFFFFFFBLL,
          TokenUser,
          TokenInformation,
          TokenInformationLength,
          &TokenInformationLength) )
  {
    v24 = GetLastError();
    v16 = v24;
    if ( v24 > 0 )
      v16 = (unsigned __int16)v24 | 0x80070000;
    if ( v16 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_94;
      v21 = 296;
      goto LABEL_42;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &StringSid,
    0);
  if ( !ConvertSidToStringSidW(*v23, &StringSid) )
  {
    v25 = GetLastError();
    v16 = v25;
    if ( v25 > 0 )
      v16 = (unsigned __int16)v25 | 0x80070000;
    if ( v16 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_94;
      v21 = 297;
      goto LABEL_42;
    }
  }
  v26 = StringCchLengthW(a5, 0x7FFFFFFFu, &v49);
  v16 = v26;
  if ( v26 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_94;
    v28 = 298;
LABEL_93:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v28, &WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids, this, v26);
    goto LABEL_94;
  }
  v26 = StringCchLengthW(v12, v27, &v46);
  v16 = v26;
  if ( v26 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_94;
    v28 = 299;
    goto LABEL_93;
  }
  v26 = StringCchLengthW(StringSid, v29, &v47);
  v16 = v26;
  if ( v26 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_94;
    v28 = 300;
    goto LABEL_93;
  }
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v42);
  v26 = FSConfigurationKey::CreateKey(a5, (int)v49 + 1, v12, (int)v46 + 1, StringSid, (int)v47 + 1, &v42);
  v16 = v26;
  if ( v26 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_94;
    v28 = 301;
    goto LABEL_93;
  }
  if ( (*(unsigned int (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)v42 + 40LL))(v42) != 32
    || (v30 = (const void *)(*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)v42 + 32LL))(v42),
        memcmp_0(Buf1, v30, v9)) )
  {
    v26 = -2147024809;
    v16 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_94;
    v28 = 302;
    goto LABEL_93;
  }
  if ( v11 )
  {
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v48);
    v26 = FSConfiguration::CreateConfiguration(v42, &v48);
    v16 = v26;
    if ( v26 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_94;
      v28 = 303;
      goto LABEL_93;
    }
    v31 = a8;
    v32 = (*(__int64 (__fastcall **)(struct IFSConfiguration *, unsigned __int8 *, _QWORD))(*(_QWORD *)v48 + 288LL))(
            v48,
            v11,
            a8);
    v16 = v32;
    if ( v32 < 0 )
    {
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 304, &WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids, this, v32);
      goto LABEL_95;
    }
  }
  else
  {
    v31 = a8;
  }
  RpcRevertToSelfEx(BindingHandle);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1144));
  if ( v11 )
  {
    v33 = FSSaveDeviceConfiguration(v42, v11, v31);
    v16 = v33;
    if ( v33 < 0 )
    {
      if ( g_wppLevels )
      {
        v34 = 306;
        goto LABEL_87;
      }
LABEL_88:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1144));
      goto LABEL_100;
    }
  }
  else
  {
    v33 = FSDeleteDeviceConfiguration(v42);
    v16 = v33;
    if ( v33 < 0 )
    {
      if ( g_wppLevels )
      {
        v34 = 305;
LABEL_87:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v34, &WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids, this, v33);
        goto LABEL_88;
      }
      goto LABEL_88;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1144));
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v35 = 308;
LABEL_102:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v35, &WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids, this, v16);
  }
LABEL_103:
  if ( dword_18010C208 && (unsigned __int8)tlgKeywordOn(&dword_18010C208, 0x400000000000LL) )
  {
    v38 = (int)v42;
    LODWORD(v46) = v16;
    LODWORD(v47) = v31;
    if ( v42 )
      v39 = (wchar_t *)(*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)v42 + 72LL))(v42);
    else
      v39 = L"<null_key>";
    v43 = v39;
    Binding = (RPC_BINDING_HANDLE)50331648;
    v49 = (unsigned __int64)this + 44;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v38,
      (unsigned int)&unk_1801027F9,
      v36,
      v37,
      (__int64)&v49,
      (__int64)&Binding,
      (__int64)&v43,
      (__int64)&v47,
      (__int64)&v46);
  }
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v48);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v42);
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&TokenInformation);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&BindingHandle);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180015c00  mov     rax, rsp
0x180015c03  mov     [rax+8], rbx
0x180015c07  mov     [rax+20h], rsi
0x180015c0b  mov     [rax+18h], r8
0x180015c0f  push    rbp
0x180015c10  push    rdi
0x180015c11  push    r13
0x180015c13  push    r14
0x180015c15  push    r15
0x180015c17  lea     rbp, [rax-3Fh]
0x180015c1b  sub     rsp, 0A0h
0x180015c22  mov     rbx, rdx
0x180015c25  mov     r13d, r9d
0x180015c28  xor     edx, edx
0x180015c2a  mov     rsi, rcx
0x180015c2d  mov     [rbp+37h+var_30], rdx
0x180015c31  mov     [rbp+37h+var_48], rdx
0x180015c35  mov     [rbp+37h+StringSid], rdx
0x180015c39  mov     [rbp+37h+var_40], rdx
0x180015c3d  mov     [rbp+37h+BindingHandle], rdx
0x180015c41  mov     [rbp+37h+TokenInformation], rdx
0x180015c45  mov     [rbp+37h+TokenInformationLength], edx
0x180015c48  mov     [rbp+37h+var_68], rdx
0x180015c4c  mov     [rbp+37h+var_38], rdx
0x180015c50  cmp     cs:byte_18010EC4D, 8
0x180015c57  mov     r14, [rbp+37h+arg_30]
0x180015c5b  mov     r15, [rbp+37h+arg_28]
0x180015c5f  mov     edi, dword ptr [rbp+37h+arg_38]
0x180015c62  jb      short loc_180015CB7
0x180015c64  mov     dword ptr [rsp+0C0h+var_78], edi; char
0x180015c68  lea     rcx, aNull_0; "<null>"
0x180015c6f  mov     rax, rcx
0x180015c72  mov     qword ptr [rsp+0C0h+var_80], r14; char
0x180015c77  test    r15, r15
0x180015c7a  mov     r9, rsi
0x180015c7d  cmovnz  rax, r15
0x180015c81  cmp     [rbp+37h+arg_20], rdx
0x180015c85  mov     [rsp+0C0h+var_88], rax; __int64
0x180015c8a  cmovnz  rcx, [rbp+37h+arg_20]
0x180015c8f  mov     [rsp+0C0h+var_90], rcx; __int64
0x180015c94  mov     rcx, cs:WPP_GLOBAL_Control
0x180015c9b  mov     dword ptr [rsp+0C0h+var_98], r13d; char
0x180015ca0  mov     [rsp+0C0h+ReturnLength], r8; char
0x180015ca5  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180015cac  call    WPP_SF_qqDSSqd
0x180015cb1  mov     r8, [rbp+37h+Buf1]
0x180015cb5  xor     edx, edx
0x180015cb7  test    rbx, rbx
0x180015cba  jnz     short loc_180015CDA
0x180015cbc  mov     eax, 80070057h
0x180015cc1  mov     edi, eax
0x180015cc3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180015cca  jb      loc_18001628B
0x180015cd0  mov     edx, 11Eh
0x180015cd5  jmp     loc_18001626D
0x180015cda  cmp     [rbp+37h+arg_20], rdx
0x180015cde  jnz     short loc_180015CFE
0x180015ce0  mov     eax, 80070057h
0x180015ce5  mov     edi, eax
0x180015ce7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180015cee  jb      loc_18001628B
0x180015cf4  mov     edx, 11Fh
0x180015cf9  jmp     loc_18001626D
0x180015cfe  test    r15, r15
0x180015d01  jnz     short loc_180015D21
0x180015d03  mov     eax, 80070057h
0x180015d08  mov     edi, eax
0x180015d0a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180015d11  jb      loc_18001628B
0x180015d17  mov     edx, 120h
0x180015d1c  jmp     loc_18001626D
0x180015d21  test    r8, r8
0x180015d24  jz      loc_180016258
0x180015d2a  cmp     r13d, 20h ; ' '
0x180015d2e  jnz     loc_180016258
0x180015d34  test    r14, r14
0x180015d37  jnz     short loc_180015D75
0x180015d39  test    edi, edi
0x180015d3b  jnz     short loc_180015D79
0x180015d3d  mov     rax, [rbx]
0x180015d40  mov     rcx, rbx
0x180015d43  mov     rax, [rax+130h]
0x180015d4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d4f  xor     edx, edx
0x180015d51  test    eax, eax
0x180015d53  jz      short loc_180015D97
0x180015d55  mov     edi, 80070005h
0x180015d5a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180015d61  jb      loc_18001628B
0x180015d67  mov     edx, 123h
0x180015d6c  mov     dword ptr [rsp+0C0h+ReturnLength], edi
0x180015d70  jmp     loc_180016271
0x180015d75  test    edi, edi
0x180015d77  jnz     short loc_180015D3D
0x180015d79  mov     eax, 80070057h
0x180015d7e  mov     edi, eax
0x180015d80  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180015d87  jb      loc_18001628B
0x180015d8d  mov     edx, 122h
0x180015d92  jmp     loc_18001626D
0x180015d97  mov     rbx, [rbp+37h+BindingHandle]
0x180015d9b  test    rbx, rbx
0x180015d9e  jz      short loc_180015DC2
0x180015da0  lea     rcx, [rbp+37h+var_60]; this
0x180015da4  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180015da9  lea     rcx, [rbp+37h+Binding]; Binding
0x180015dad  mov     [rbp+37h+Binding], rbx
0x180015db1  call    cs:__imp_RpcBindingFree
0x180015db7  lea     rcx, [rbp+37h+var_60]; this
0x180015dbb  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180015dc0  xor     edx, edx
0x180015dc2  lea     rcx, [rbp+37h+BindingHandle]; Binding
0x180015dc6  mov     [rbp+37h+BindingHandle], rdx
0x180015dca  call    cs:__imp_RpcServerInqBindingHandle
0x180015dd0  test    eax, eax
0x180015dd2  jz      short loc_180015E2E
0x180015dd4  mov     rbx, [rbp+37h+BindingHandle]
0x180015dd8  test    rbx, rbx
0x180015ddb  jz      short loc_180015DFD
0x180015ddd  lea     rcx, [rbp+37h+Binding]; this
0x180015de1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180015de6  lea     rcx, [rbp+37h+var_60]; Binding
0x180015dea  mov     [rbp+37h+var_60], rbx
0x180015dee  call    cs:__imp_RpcBindingFree
0x180015df4  lea     rcx, [rbp+37h+Binding]; this
0x180015df8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180015dfd  lea     rcx, [rbp+37h+BindingHandle]; Binding
0x180015e01  mov     [rbp+37h+BindingHandle], 0
0x180015e09  call    cs:__imp_RpcServerInqBindingHandle
0x180015e0f  mov     edi, eax
0x180015e11  or      edi, 80010000h
0x180015e17  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180015e1e  jb      loc_18001628B
0x180015e24  mov     edx, 124h
0x180015e29  jmp     loc_180015D6C
0x180015e2e  mov     rcx, [rbp+37h+BindingHandle]; BindingHandle
0x180015e32  call    cs:__imp_RpcImpersonateClient
0x180015e38  test    eax, eax
0x180015e3a  jz      short loc_180015E65
0x180015e3c  mov     rcx, [rbp+37h+BindingHandle]; BindingHandle
0x180015e40  call    cs:__imp_RpcImpersonateClient
0x180015e46  mov     edi, eax
0x180015e48  or      edi, 80010000h
0x180015e4e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180015e55  jb      loc_18001628B
0x180015e5b  mov     edx, 125h
0x180015e60  jmp     loc_180015D6C
0x180015e65  xor     r9d, r9d; TokenInformationLength
0x180015e68  lea     rax, [rbp+37h+TokenInformationLength]
0x180015e6c  xor     r8d, r8d; TokenInformation
0x180015e6f  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x180015e74  lea     edx, [r9+1]; TokenInformationClass
0x180015e78  lea     rcx, [r9-5]; TokenHandle
0x180015e7c  call    cs:__imp_GetTokenInformation
0x180015e82  test    eax, eax
0x180015e84  jnz     short loc_180015ECA
0x180015e86  call    cs:__imp_GetLastError
0x180015e8c  mov     edi, eax
0x180015e8e  test    eax, eax
0x180015e90  jle     short loc_180015E9B
0x180015e92  movzx   edi, ax
0x180015e95  or      edi, 80070000h
0x180015e9b  mov     ecx, 80000000h
0x180015ea0  lea     eax, [rdi+rcx]
0x180015ea3  test    ecx, eax
0x180015ea5  jnz     short loc_180015ECA
0x180015ea7  cmp     edi, 8007007Ah
0x180015ead  jz      short loc_180015ECA
0x180015eaf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180015eb6  jb      loc_180016248
0x180015ebc  mov     edx, 126h
0x180015ec1  mov     dword ptr [rsp+0C0h+ReturnLength], edi
0x180015ec5  jmp     loc_18001622E
0x180015eca  mov     edx, [rbp+37h+TokenInformationLength]
0x180015ecd  lea     rcx, [rbp+37h+var_60]
0x180015ed1  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x180015ed6  mov     rdx, rax
0x180015ed9  lea     rcx, [rbp+37h+TokenInformation]
0x180015edd  call    ??4?$unique_ptr@$$BY0A@KU?$default_delete@$$BY0A@K@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>>::operator=(wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>> &&)
0x180015ee2  lea     rcx, [rbp+37h+var_60]
0x180015ee6  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x180015eeb  mov     rbx, [rbp+37h+TokenInformation]
0x180015eef  test    rbx, rbx
0x180015ef2  jnz     short loc_180015F0D
0x180015ef4  mov     edi, 8007000Eh
0x180015ef9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180015f00  jb      loc_180016248
0x180015f06  mov     edx, 127h
0x180015f0b  jmp     short loc_180015EC1
0x180015f0d  mov     r9d, [rbp+37h+TokenInformationLength]; TokenInformationLength
0x180015f11  lea     rax, [rbp+37h+TokenInformationLength]
0x180015f15  mov     r8, rbx; TokenInformation
0x180015f18  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x180015f1d  mov     edx, 1; TokenInformationClass
0x180015f22  mov     rcx, 0FFFFFFFFFFFFFFFBh; TokenHandle
0x180015f29  call    cs:__imp_GetTokenInformation
0x180015f2f  test    eax, eax
0x180015f31  jnz     short loc_180015F63
0x180015f33  call    cs:__imp_GetLastError
0x180015f39  mov     edi, eax
0x180015f3b  test    eax, eax
0x180015f3d  jle     short loc_180015F48
0x180015f3f  movzx   edi, ax
0x180015f42  or      edi, 80070000h
0x180015f48  test    edi, edi
0x180015f4a  jns     short loc_180015F63
0x180015f4c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180015f53  jb      loc_180016248
0x180015f59  mov     edx, 128h
0x180015f5e  jmp     loc_180015EC1
0x180015f63  xor     edx, edx
0x180015f65  lea     rcx, [rbp+37h+StringSid]
0x180015f69  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180015f6e  mov     rcx, [rbx]; Sid
0x180015f71  lea     rdx, [rbp+37h+StringSid]; StringSid
0x180015f75  call    cs:__imp_ConvertSidToStringSidW
0x180015f7b  test    eax, eax
0x180015f7d  jnz     short loc_180015FAF
0x180015f7f  call    cs:__imp_GetLastError
0x180015f85  mov     edi, eax
0x180015f87  test    eax, eax
0x180015f89  jle     short loc_180015F94
0x180015f8b  movzx   edi, ax
0x180015f8e  or      edi, 80070000h
0x180015f94  test    edi, edi
0x180015f96  jns     short loc_180015FAF
0x180015f98  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180015f9f  jb      loc_180016248
0x180015fa5  mov     edx, 129h
0x180015faa  jmp     loc_180015EC1
0x180015faf  mov     rcx, [rbp+37h+arg_20]; unsigned __int16 *
0x180015fb3  lea     r8, [rbp+37h+var_30]; unsigned __int64 *
0x180015fb7  mov     r11d, 7FFFFFFFh
0x180015fbd  mov     edx, r11d; unsigned __int64
0x180015fc0  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180015fc5  mov     edi, eax
0x180015fc7  test    eax, eax
0x180015fc9  jns     short loc_180015FE2
0x180015fcb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180015fd2  jb      loc_180016248
0x180015fd8  mov     edx, 12Ah
0x180015fdd  jmp     loc_18001622A
0x180015fe2  lea     r8, [rbp+37h+var_48]; unsigned __int64 *
0x180015fe6  mov     rdx, r11; unsigned __int64
0x180015fe9  mov     rcx, r15; unsigned __int16 *
0x180015fec  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180015ff1  mov     edi, eax
0x180015ff3  test    eax, eax
0x180015ff5  jns     short loc_18001600E
0x180015ff7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180015ffe  jb      loc_180016248
0x180016004  mov     edx, 12Bh
0x180016009  jmp     loc_18001622A
0x18001600e  mov     rcx, [rbp+37h+StringSid]; unsigned __int16 *
0x180016012  lea     r8, [rbp+37h+var_40]; unsigned __int64 *
0x180016016  mov     rdx, r11; unsigned __int64
0x180016019  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001601e  mov     edi, eax
0x180016020  test    eax, eax
0x180016022  jns     short loc_18001603B
0x180016024  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001602b  jb      loc_180016248
0x180016031  mov     edx, 12Ch
0x180016036  jmp     loc_18001622A
0x18001603b  lea     rcx, [rbp+37h+var_68]
0x18001603f  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180016044  mov     eax, dword ptr [rbp+37h+var_40]
0x180016047  lea     rcx, [rbp+37h+var_68]
0x18001604b  mov     r9d, dword ptr [rbp+37h+var_48]
0x18001604f  inc     eax
0x180016051  mov     edx, dword ptr [rbp+37h+var_30]
0x180016054  inc     r9d; unsigned int
0x180016057  mov     r10, [rbp+37h+StringSid]
0x18001605b  inc     edx; unsigned int
0x18001605d  mov     [rsp+0C0h+var_90], rcx; struct IFSConfigurationKey **
0x180016062  mov     r8, r15; unsigned __int16 *
0x180016065  mov     rcx, [rbp+37h+arg_20]; unsigned __int16 *
0x180016069  mov     dword ptr [rsp+0C0h+var_98], eax; unsigned int
0x18001606d  mov     [rsp+0C0h+ReturnLength], r10; unsigned __int16 *
0x180016072  call    ?CreateKey@FSConfigurationKey@@SAJPEBGK0K0KPEAPEAUIFSConfigurationKey@@@Z; FSConfigurationKey::CreateKey(ushort const *,ulong,ushort const *,ulong,ushort const *,ulong,IFSConfigurationKey * *)
0x180016077  mov     edi, eax
0x180016079  test    eax, eax
0x18001607b  jns     short loc_180016094
0x18001607d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180016084  jb      loc_180016248
0x18001608a  mov     edx, 12Dh
0x18001608f  jmp     loc_18001622A
0x180016094  mov     rcx, [rbp+37h+var_68]
0x180016098  mov     rax, [rcx]
0x18001609b  mov     rax, [rax+28h]
0x18001609f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160a4  cmp     r13d, eax
0x1800160a7  jnz     loc_180016215
0x1800160ad  mov     rcx, [rbp+37h+var_68]
0x1800160b1  mov     rax, [rcx]
0x1800160b4  mov     rax, [rax+20h]
0x1800160b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160bd  mov     rcx, [rbp+37h+Buf1]; Buf1
0x1800160c1  mov     rdx, rax; Buf2
0x1800160c4  mov     r8, r13; Size
  ... truncated ...
```
