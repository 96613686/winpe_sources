# WebAuthNSyncGetTrustedDeviceList

- ea: `0x180028320`
- end: `0x1800288c0`
- name: `WebAuthNSyncGetTrustedDeviceList`
- size: `1440`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000b040`
- `0x180017a88`
- `0x1800205e4`
- `0x180023c18`
- `0x18002824c`
- `0x180028320`
- `0x1800288c8`
- `0x180028948`
- `0x18002a07c`
- `0x18002a314`
- `0x180036da4`
- `0x180047464`
- `0x180047494`
- `0x1800537a4`
- `0x18006c82c`
- `0x18007d3a4`
- `0x18007da80`
- `0x1800925f4`
- `0x1800926b8`
- `0x180092728`
- `0x18013c090`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028518`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028566`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800285d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028518`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028566`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800285d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002848b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800287fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028860`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002848b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800287fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028860`

## string_xrefs

- `0x18002836c`: `onecore\ds\security\fido\webauthn\dll\webauthnsyncclient.cpp`
- `0x1800283ec`: `onecore\ds\security\fido\webauthn\dll\webauthnsyncclient.cpp`
- `0x18002846a`: `onecore\ds\security\fido\webauthn\dll\webauthnsyncclient.cpp`
- `0x180028738`: `onecore\ds\security\fido\webauthn\dll\webauthnsyncclient.cpp`
- `0x18002879c`: `onecore\ds\security\fido\webauthn\dll\webauthnsyncclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall WebAuthNSyncGetTrustedDeviceList(_QWORD *a1, __int64 a2, int a3)
{
  int v5; // eax
  __int64 v6; // rax
  int v7; // ebx
  void *v8; // rcx
  __int64 *unique; // rax
  __int64 v10; // r14
  HLOCAL v11; // rcx
  __int64 *v12; // rax
  __int64 v13; // rcx
  HLOCAL v14; // rcx
  unsigned __int64 i; // rbx
  __int64 v16; // rsi
  __int64 v17; // rdi
  __int64 *v18; // rax
  __int64 v19; // rcx
  HLOCAL v20; // rcx
  __int64 v21; // r15
  _QWORD *v22; // rdx
  __int64 v23; // rcx
  _QWORD *v24; // rdx
  HLOCAL v25; // rcx
  unsigned __int64 v26; // r12
  int v27; // eax
  __int64 v28; // rcx
  char v29; // al
  __int64 v30; // rdi
  __int64 v31; // rsi
  unsigned int v32; // eax
  unsigned int v33; // eax
  int v34; // eax
  __int64 v35; // r8
  wil::details::in1diag3 *v36; // rcx
  void *v37; // rcx
  void *v38; // rcx
  unsigned int v39; // [rsp+20h] [rbp-178h]
  char v40; // [rsp+30h] [rbp-168h]
  __int64 *v41; // [rsp+38h] [rbp-160h] BYREF
  __int64 v42; // [rsp+40h] [rbp-158h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-150h] BYREF
  int v44; // [rsp+50h] [rbp-148h]
  HLOCAL v45; // [rsp+58h] [rbp-140h] BYREF
  unsigned int v46; // [rsp+60h] [rbp-138h] BYREF
  int v47; // [rsp+64h] [rbp-134h] BYREF
  int v48; // [rsp+68h] [rbp-130h]
  __int64 v49; // [rsp+70h] [rbp-128h] BYREF
  __int64 v50; // [rsp+78h] [rbp-120h] BYREF
  HLOCAL hMem[2]; // [rsp+80h] [rbp-118h] BYREF
  _BYTE v52[32]; // [rsp+90h] [rbp-108h] BYREF
  __int64 v53; // [rsp+B0h] [rbp-E8h]
  __int64 v54; // [rsp+B8h] [rbp-E0h]
  _BYTE v55[24]; // [rsp+E0h] [rbp-B8h] BYREF
  __int128 v56; // [rsp+F8h] [rbp-A0h]
  HLOCAL p_pv; // [rsp+140h] [rbp-58h] BYREF
  __int64 v58; // [rsp+148h] [rbp-50h] BYREF
  char v59; // [rsp+150h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  v48 = 0;
  if ( a1 )
  {
    *a1 = 0;
    winrt::create_instance<IMCloudOpsOffline>(&v41, (const IID *)winrt::impl::guid_v<MCloudOpsOffline>, a3);
    WebAuthNCom::AllowImpersonationCom(v41);
    v42 = 0;
    if ( (*(int (__fastcall **)(__int64 *, __int64 *))(*v41 + 56))(v41, &v42) >= 0 )
    {
      WebAuthNCom::AllowImpersonationCom(v42);
      v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v42 + 24LL))(v42);
      if ( v5 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x101,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnsyncclient.cpp",
          (const char *)(unsigned int)v5,
          v39);
    }
    pv = 0;
    v46 = 0;
    v47 = 0;
    v6 = *v41;
    p_pv = &pv;
    v58 = 0;
    v59 = 1;
    v7 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, unsigned int *, int *))(v6 + 32))(v41, &v58, &v46, &v47);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
    if ( v7 >= 0 )
    {
      p_pv = pv;
      v58 = v46;
      NgcMCloud::RecoveryBlob::FromCbor(v52, &p_pv);
      unique = (__int64 *)wil::make_unique_hlocal<_EXPERIMENTAL_WEBAUTHN_PLUGIN_ADD_AUTHENTICATOR_RESPONSE,>(hMem);
      v10 = *unique;
      *unique = 0;
      v50 = v10;
      v11 = hMem[0];
      hMem[0] = 0;
      if ( v11 )
        LocalFree(v11);
      *(_DWORD *)v10 = 0;
      v12 = (__int64 *)wil::make_unique_hlocal<_WEBAUTHN_TRUSTED_DEVICE * [0]>(
                         &v45,
                         0xCCCCCCCCCCCCCCCDuLL * ((v54 - v53) >> 6));
      v13 = *v12;
      *v12 = 0;
      *(_QWORD *)(v10 + 8) = v13;
      v14 = v45;
      v45 = 0;
      if ( v14 )
        LocalFree(v14);
      v40 = 0;
      for ( i = 0; ; ++i )
      {
        v16 = v53;
        if ( i >= 0xCCCCCCCCCCCCCCCDuLL * ((v54 - v53) >> 6) )
          break;
        v17 = 320 * i;
        v18 = (__int64 *)wil::make_unique_hlocal<_EXPERIMENTAL_WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS,>(&p_pv);
        v19 = *v18;
        *v18 = 0;
        *(_QWORD *)(*(_QWORD *)(v10 + 8) + 8 * i) = v19;
        v20 = p_pv;
        p_pv = 0;
        if ( v20 )
          LocalFree(v20);
        ++*(_DWORD *)v10;
        v21 = *(_QWORD *)(v10 + 8);
        **(_DWORD **)(v21 + 8 * i) = 1;
        v22 = (_QWORD *)(v17 + v16 + 40);
        if ( *(_QWORD *)(v17 + v16 + 64) > 7u )
          v22 = (_QWORD *)*v22;
        wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &v49,
          v22,
          -1);
        v23 = v49;
        v49 = 0;
        *(_QWORD *)(*(_QWORD *)(v21 + 8 * i) + 16LL) = v23;
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v49);
        *(_DWORD *)(*(_QWORD *)(v21 + 8 * i) + 8LL) = *(_DWORD *)(v17 + v16 + 8);
        v24 = (_QWORD *)(v17 + v16 + 80);
        if ( *(_QWORD *)(v17 + v16 + 104) > 7u )
          v24 = (_QWORD *)*v24;
        wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &v45,
          v24,
          -1);
        v25 = v45;
        v45 = 0;
        *(_QWORD *)(*(_QWORD *)(v21 + 8 * i) + 32LL) = v25;
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v45);
        v26 = *(_QWORD *)(v17 + v16 + 72);
        v44 = wil::safe_cast<unsigned long,unsigned __int64,0>((unsigned int)v26);
        v27 = wil::safe_cast<unsigned long,unsigned __int64,0>(HIDWORD(v26));
        v28 = *(_QWORD *)(v21 + 8 * i);
        *(_DWORD *)(v28 + 24) = v44;
        *(_DWORD *)(v28 + 28) = v27;
        v29 = *(_BYTE *)(v17 + v16 + 312);
        if ( v29 == 2 )
        {
          *(_DWORD *)(*(_QWORD *)(v21 + 8 * i) + 4LL) = 0;
          if ( *(_DWORD *)(v17 + v16 + 8) == v47 )
          {
            *(_DWORD *)(*(_QWORD *)(v21 + 8 * i) + 40LL) = 1;
            v40 = 1;
          }
        }
        else
        {
          v30 = v16 + v17 + 112;
          if ( !v30 || v29 != 3 )
            v30 = 0;
          if ( v30 )
          {
            *(_DWORD *)(*(_QWORD *)(v21 + 8 * i) + 4LL) = 2;
            memset_0(v55, 0, 0x58u);
            v31 = *(_QWORD *)(v30 + 176);
            v32 = wil::safe_cast<unsigned long,unsigned __int64,0>(*(_QWORD *)(v30 + 184) - v31);
            v33 = CtapCborUnpackAuthenticatorData(v32, v31, v55);
            if ( v33 )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0x131,
                (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnsyncclient.cpp",
                (const char *)v33,
                v39);
            *(_OWORD *)(*(_QWORD *)(v21 + 8 * i) + 44LL) = v56;
          }
        }
        v48 |= 0x18u;
      }
      if ( v40 )
      {
        v50 = 0;
        *a1 = v10;
        wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_TRUSTED_DEVICE_LIST *,void (*)(_WEBAUTHN_TRUSTED_DEVICE_LIST *),&void WebAuthNSyncFreeTrustedDeviceList(_WEBAUTHN_TRUSTED_DEVICE_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_TRUSTED_DEVICE_LIST *,_WEBAUTHN_TRUSTED_DEVICE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WEBAUTHN_TRUSTED_DEVICE_LIST *,void (*)(_WEBAUTHN_TRUSTED_DEVICE_LIST *),&void WebAuthNSyncFreeTrustedDeviceList(_WEBAUTHN_TRUSTED_DEVICE_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_TRUSTED_DEVICE_LIST *,_WEBAUTHN_TRUSTED_DEVICE_LIST *,0,std::nullptr_t>>(&v50);
        NgcMCloud::RecoveryBlob::~RecoveryBlob((NgcMCloud::RecoveryBlob *)v52);
        v38 = pv;
        pv = 0;
        if ( v38 )
          CoTaskMemFree(v38);
        if ( v42 )
          winrt::com_ptr<ISyncedPasskeyAuthenticatorLowPriv>::unconditional_release_ref(&v42);
        if ( v41 )
          winrt::com_ptr<ISyncedPasskeyAuthenticatorLowPriv>::unconditional_release_ref(&v41);
        return 0;
      }
      else
      {
        v34 = (*(__int64 (__fastcall **)(__int64 *))(*v41 + 40))(v41);
        v36 = retaddr;
        if ( v34 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x139,
            (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnsyncclient.cpp",
            (const char *)(unsigned int)v34,
            v39);
        if ( byte_1801AEA04 < 0 )
          McGenEventWrite_EventWriteTransfer(v36, EVENT_SYNCED_TRUSTEDDEVICENOTFOUND, v35, 1, &p_pv);
        wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_TRUSTED_DEVICE_LIST *,void (*)(_WEBAUTHN_TRUSTED_DEVICE_LIST *),&void WebAuthNSyncFreeTrustedDeviceList(_WEBAUTHN_TRUSTED_DEVICE_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_TRUSTED_DEVICE_LIST *,_WEBAUTHN_TRUSTED_DEVICE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WEBAUTHN_TRUSTED_DEVICE_LIST *,void (*)(_WEBAUTHN_TRUSTED_DEVICE_LIST *),&void WebAuthNSyncFreeTrustedDeviceList(_WEBAUTHN_TRUSTED_DEVICE_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_TRUSTED_DEVICE_LIST *,_WEBAUTHN_TRUSTED_DEVICE_LIST *,0,std::nullptr_t>>(&v50);
        NgcMCloud::RecoveryBlob::~RecoveryBlob((NgcMCloud::RecoveryBlob *)v52);
        v37 = pv;
        pv = 0;
        if ( v37 )
          CoTaskMemFree(v37);
        if ( v42 )
          winrt::com_ptr<ISyncedPasskeyAuthenticatorLowPriv>::unconditional_release_ref(&v42);
        if ( v41 )
          winrt::com_ptr<ISyncedPasskeyAuthenticatorLowPriv>::unconditional_release_ref(&v41);
        return 2147943568LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x107,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnsyncclient.cpp",
        (const char *)(unsigned int)v7,
        v39);
      v8 = pv;
      pv = 0;
      if ( v8 )
        CoTaskMemFree(v8);
      if ( v42 )
        winrt::com_ptr<ISyncedPasskeyAuthenticatorLowPriv>::unconditional_release_ref(&v42);
      if ( v41 )
        winrt::com_ptr<ISyncedPasskeyAuthenticatorLowPriv>::unconditional_release_ref(&v41);
      return (unsigned int)v7;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF5,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnsyncclient.cpp",
      (const char *)0x80090027LL,
      v39);
    return 2148073511LL;
  }
}

```

## disassembly

```asm
0x180028320  mov     [rsp+arg_8], rbx
0x180028325  mov     [rsp+arg_10], rsi
0x18002832a  push    rdi
0x18002832b  push    r12
0x18002832d  push    r13
0x18002832f  push    r14
0x180028331  push    r15
0x180028333  sub     rsp, 170h
0x18002833a  mov     rax, cs:__security_cookie
0x180028341  xor     rax, rsp
0x180028344  mov     [rsp+198h+var_38], rax
0x18002834c  mov     r13, rcx
0x18002834f  xor     r12d, r12d
0x180028352  mov     [rsp+198h+var_130], r12d
0x180028357  test    rcx, rcx
0x18002835a  jnz     short loc_180028384
0x18002835c  mov     rcx, [rsp+198h]; this
0x180028364  mov     ebx, 80090027h
0x180028369  mov     r9d, ebx; char *
0x18002836c  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180028373  mov     edx, 0F5h; void *
0x180028378  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002837d  mov     eax, ebx
0x18002837f  jmp     loc_180028892
0x180028384  mov     [rcx], r12
0x180028387  lea     rdx, ??$guid_v@VMCloudOpsOffline@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<MCloudOpsOffline>
0x18002838e  lea     rcx, [rsp+198h+var_160]
0x180028393  call    ??$create_instance@UIMCloudOpsOffline@@@winrt@@YA?A_PAEBUguid@0@IPEAX@Z
0x180028398  nop
0x180028399  mov     rcx, [rsp+198h+var_160]
0x18002839e  call    WebAuthNCom__AllowImpersonationCom
0x1800283a3  mov     [rsp+198h+var_158], r12
0x1800283a8  mov     rcx, [rsp+198h+var_160]
0x1800283ad  mov     rax, [rcx]
0x1800283b0  lea     rdx, [rsp+198h+var_158]
0x1800283b5  mov     rax, [rax+38h]
0x1800283b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283be  test    eax, eax
0x1800283c0  js      short loc_1800283FD
0x1800283c2  mov     rcx, [rsp+198h+var_158]
0x1800283c7  call    WebAuthNCom__AllowImpersonationCom
0x1800283cc  mov     rcx, [rsp+198h+var_158]
0x1800283d1  mov     rax, [rcx]
0x1800283d4  mov     rax, [rax+18h]
0x1800283d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283dd  mov     rcx, [rsp+198h]; this
0x1800283e5  test    eax, eax
0x1800283e7  jns     short loc_1800283FD
0x1800283e9  mov     r9d, eax; char *
0x1800283ec  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800283f3  mov     edx, 101h; void *
0x1800283f8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800283fd  mov     [rsp+198h+pv], r12
0x180028402  mov     [rsp+198h+var_138], r12d
0x180028407  mov     [rsp+198h+var_134], r12d
0x18002840c  mov     rcx, [rsp+198h+var_160]
0x180028411  mov     rax, [rcx]
0x180028414  lea     rdx, [rsp+198h+pv]
0x180028419  mov     [rsp+198h+var_58], rdx
0x180028421  mov     [rsp+198h+var_50], r12
0x180028429  mov     [rsp+198h+var_48], 1
0x180028431  lea     r9, [rsp+198h+var_134]
0x180028436  lea     r8, [rsp+198h+var_138]
0x18002843b  lea     rdx, [rsp+198h+var_50]
0x180028443  mov     rax, [rax+20h]
0x180028447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002844c  mov     ebx, eax
0x18002844e  lea     rcx, [rsp+198h+var_58]
0x180028456  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18002845b  test    ebx, ebx
0x18002845d  jns     short loc_1800284BC
0x18002845f  mov     rcx, [rsp+198h]; this
0x180028467  mov     r9d, ebx; char *
0x18002846a  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180028471  mov     edx, 107h; void *
0x180028476  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002847b  nop
0x18002847c  mov     rcx, [rsp+198h+pv]; pv
0x180028481  mov     [rsp+198h+pv], r12
0x180028486  test    rcx, rcx
0x180028489  jz      short loc_180028492
0x18002848b  call    cs:__imp_CoTaskMemFree
0x180028491  nop
0x180028492  cmp     [rsp+198h+var_158], r12
0x180028497  jz      short loc_1800284A4
0x180028499  lea     rcx, [rsp+198h+var_158]
0x18002849e  call    ?unconditional_release_ref@?$com_ptr@UISyncedPasskeyAuthenticatorLowPriv@@@winrt@@AEAAXXZ; winrt::com_ptr<ISyncedPasskeyAuthenticatorLowPriv>::unconditional_release_ref(void)
0x1800284a3  nop
0x1800284a4  cmp     [rsp+198h+var_160], r12
0x1800284a9  jz      short loc_1800284B5
0x1800284ab  lea     rcx, [rsp+198h+var_160]
0x1800284b0  call    ?unconditional_release_ref@?$com_ptr@UISyncedPasskeyAuthenticatorLowPriv@@@winrt@@AEAAXXZ; winrt::com_ptr<ISyncedPasskeyAuthenticatorLowPriv>::unconditional_release_ref(void)
0x1800284b5  mov     eax, ebx
0x1800284b7  jmp     loc_180028892
0x1800284bc  mov     rax, [rsp+198h+pv]
0x1800284c1  mov     [rsp+198h+var_58], rax
0x1800284c9  mov     eax, [rsp+198h+var_138]
0x1800284cd  mov     [rsp+198h+var_50], rax
0x1800284d5  lea     rdx, [rsp+198h+var_58]
0x1800284dd  lea     rcx, [rsp+198h+var_108]
0x1800284e5  call    ?FromCbor@RecoveryBlob@NgcMCloud@@SA?AU12@V?$span@$$CBE$0?0@std@@@Z; NgcMCloud::RecoveryBlob::FromCbor(std::span<uchar const,-1>)
0x1800284ea  nop
0x1800284eb  lea     rcx, [rsp+198h+hMem]
0x1800284f3  call    ??$make_unique_hlocal@U_EXPERIMENTAL_WEBAUTHN_PLUGIN_ADD_AUTHENTICATOR_RESPONSE@@$$V@wil@@YA?AV?$unique_ptr@U_EXPERIMENTAL_WEBAUTHN_PLUGIN_ADD_AUTHENTICATOR_RESPONSE@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@XZ; wil::make_unique_hlocal<_EXPERIMENTAL_WEBAUTHN_PLUGIN_ADD_AUTHENTICATOR_RESPONSE,>(void)
0x1800284f8  mov     r14, [rax]
0x1800284fb  mov     [rax], r12
0x1800284fe  mov     [rsp+198h+var_120], r14
0x180028503  mov     rcx, [rsp+198h+hMem]; hMem
0x18002850b  mov     [rsp+198h+hMem], r12
0x180028513  test    rcx, rcx
0x180028516  jz      short loc_18002851E
0x180028518  call    cs:__imp_LocalFree
0x18002851e  mov     [r14], r12d
0x180028521  mov     rdx, [rsp+198h+var_E0]
0x180028529  sub     rdx, [rsp+198h+var_E8]
0x180028531  sar     rdx, 6
0x180028535  mov     rdi, 0CCCCCCCCCCCCCCCDh
0x18002853f  imul    rdx, rdi
0x180028543  lea     rcx, [rsp+198h+var_140]
0x180028548  call    ??$make_unique_hlocal@$$BY0A@PEAU_WEBAUTHN_TRUSTED_DEVICE@@@wil@@YA?AV?$unique_ptr@$$BY0A@PEAU_WEBAUTHN_TRUSTED_DEVICE@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<_WEBAUTHN_TRUSTED_DEVICE * [0]>(unsigned __int64)
0x18002854d  mov     rcx, [rax]
0x180028550  mov     [rax], r12
0x180028553  mov     [r14+8], rcx
0x180028557  mov     rcx, [rsp+198h+var_140]; hMem
0x18002855c  mov     [rsp+198h+var_140], r12
0x180028561  test    rcx, rcx
0x180028564  jz      short loc_18002856C
0x180028566  call    cs:__imp_LocalFree
0x18002856c  mov     [rsp+198h+var_168], r12b
0x180028571  mov     rbx, r12
0x180028574  mov     rax, [rsp+198h+var_E0]
0x18002857c  mov     rsi, [rsp+198h+var_E8]
0x180028584  sub     rax, rsi
0x180028587  sar     rax, 6
0x18002858b  imul    rax, rdi
0x18002858f  cmp     rbx, rax
0x180028592  jnb     loc_180028771
0x180028598  lea     rdi, [rbx+rbx*4]
0x18002859c  shl     rdi, 6
0x1800285a0  lea     rcx, [rsp+198h+var_58]
0x1800285a8  call    ??$make_unique_hlocal@U_EXPERIMENTAL_WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS@@$$V@wil@@YA?AV?$unique_ptr@U_EXPERIMENTAL_WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@XZ; wil::make_unique_hlocal<_EXPERIMENTAL_WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS,>(void)
0x1800285ad  mov     rcx, [rax]
0x1800285b0  mov     [rax], r12
0x1800285b3  mov     rax, [r14+8]
0x1800285b7  mov     [rax+rbx*8], rcx
0x1800285bb  mov     rcx, [rsp+198h+var_58]; hMem
0x1800285c3  mov     [rsp+198h+var_58], r12
0x1800285cb  test    rcx, rcx
0x1800285ce  jz      short loc_1800285D6
0x1800285d0  call    cs:__imp_LocalFree
0x1800285d6  inc     dword ptr [r14]
0x1800285d9  mov     r15, [r14+8]
0x1800285dd  mov     rax, [r15+rbx*8]
0x1800285e1  mov     dword ptr [rax], 1
0x1800285e7  lea     rdx, [rsi+28h]
0x1800285eb  add     rdx, rdi
0x1800285ee  cmp     qword ptr [rdi+rsi+40h], 7
0x1800285f4  jbe     short loc_1800285F9
0x1800285f6  mov     rdx, [rdx]
0x1800285f9  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800285fd  lea     rcx, [rsp+198h+var_128]
0x180028602  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180028607  mov     rcx, [rsp+198h+var_128]
0x18002860c  mov     [rsp+198h+var_128], r12
0x180028611  mov     rax, [r15+rbx*8]
0x180028615  mov     [rax+10h], rcx
0x180028619  lea     rcx, [rsp+198h+var_128]
0x18002861e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180028623  mov     rcx, [r15+rbx*8]
0x180028627  mov     eax, [rdi+rsi+8]
0x18002862b  mov     [rcx+8], eax
0x18002862e  lea     rdx, [rsi+50h]
0x180028632  add     rdx, rdi
0x180028635  cmp     qword ptr [rdi+rsi+68h], 7
0x18002863b  jbe     short loc_180028640
0x18002863d  mov     rdx, [rdx]
0x180028640  or      r8, 0FFFFFFFFFFFFFFFFh
0x180028644  lea     rcx, [rsp+198h+var_140]
0x180028649  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002864e  mov     rcx, [rsp+198h+var_140]
0x180028653  mov     [rsp+198h+var_140], r12
0x180028658  mov     rax, [r15+rbx*8]
0x18002865c  mov     [rax+20h], rcx
0x180028660  lea     rcx, [rsp+198h+var_140]
0x180028665  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18002866a  mov     r12, [rdi+rsi+48h]
0x18002866f  mov     ecx, r12d
0x180028672  call    ??$safe_cast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast<ulong,unsigned __int64,0>(unsigned __int64)
0x180028677  mov     [rsp+198h+var_148], eax
0x18002867b  shr     r12, 20h
0x18002867f  mov     rcx, r12
0x180028682  call    ??$safe_cast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast<ulong,unsigned __int64,0>(unsigned __int64)
0x180028687  mov     rcx, [r15+rbx*8]
0x18002868b  mov     edx, [rsp+198h+var_148]
0x18002868f  mov     [rcx+18h], edx
0x180028692  mov     [rcx+1Ch], eax
0x180028695  mov     al, [rdi+rsi+138h]
0x18002869c  xor     r12d, r12d
0x18002869f  cmp     al, 2
0x1800286a1  jnz     short loc_1800286CE
0x1800286a3  mov     rax, [r15+rbx*8]
0x1800286a7  mov     [rax+4], r12d
0x1800286ab  mov     eax, [rsp+198h+var_134]
0x1800286af  cmp     [rdi+rsi+8], eax
0x1800286b3  jnz     loc_18002875A
0x1800286b9  mov     rax, [r15+rbx*8]
0x1800286bd  mov     dword ptr [rax+28h], 1
0x1800286c4  mov     [rsp+198h+var_168], 1
0x1800286c9  jmp     loc_18002875A
0x1800286ce  add     rdi, 70h ; 'p'
0x1800286d2  add     rdi, rsi
0x1800286d5  jz      short loc_1800286DB
0x1800286d7  cmp     al, 3
0x1800286d9  jz      short loc_1800286DE
0x1800286db  mov     rdi, r12
0x1800286de  test    rdi, rdi
0x1800286e1  jz      short loc_18002875A
0x1800286e3  mov     rax, [r15+rbx*8]
0x1800286e7  mov     dword ptr [rax+4], 2
0x1800286ee  xor     edx, edx; Val
0x1800286f0  lea     r8d, [rdx+58h]; Size
0x1800286f4  lea     rcx, [rsp+198h+var_B8]; void *
0x1800286fc  call    memset_0
0x180028701  mov     rsi, [rdi+0B0h]
0x180028708  mov     rcx, [rdi+0B8h]
0x18002870f  sub     rcx, rsi
0x180028712  call    ??$safe_cast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast<ulong,unsigned __int64,0>(unsigned __int64)
0x180028717  lea     r8, [rsp+198h+var_B8]
0x18002871f  mov     rdx, rsi
0x180028722  mov     ecx, eax
0x180028724  call    CtapCborUnpackAuthenticatorData
0x180028729  mov     rcx, [rsp+198h]; this
0x180028731  test    eax, eax
0x180028733  jz      short loc_180028749
0x180028735  mov     r9d, eax; char *
0x180028738  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18002873f  mov     edx, 131h; void *
0x180028744  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180028749  mov     rax, [r15+rbx*8]
0x18002874d  movups  xmm0, [rsp+198h+var_A0]
0x180028755  movdqu  xmmword ptr [rax+2Ch], xmm0
0x18002875a  or      [rsp+198h+var_130], 18h
0x18002875f  inc     rbx
0x180028762  mov     rdi, 0CCCCCCCCCCCCCCCDh
0x18002876c  jmp     loc_180028574
0x180028771  cmp     [rsp+198h+var_168], 0
0x180028776  jnz     loc_18002882F
0x18002877c  mov     rcx, [rsp+198h+var_160]
0x180028781  mov     rax, [rcx]
0x180028784  mov     rax, [rax+28h]
0x180028788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002878d  mov     rcx, [rsp+198h]; this
0x180028795  test    eax, eax
0x180028797  jns     short loc_1800287AD
0x180028799  mov     r9d, eax; char *
0x18002879c  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800287a3  mov     edx, 139h; void *
0x1800287a8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800287ad  cmp     cs:byte_1801AEA04, r12b
0x1800287b4  jge     short loc_1800287D6
0x1800287b6  lea     rax, [rsp+198h+var_58]
0x1800287be  mov     qword ptr [rsp+198h+var_178], rax
0x1800287c3  mov     r9d, 1
0x1800287c9  lea     rdx, EVENT_SYNCED_TRUSTEDDEVICENOTFOUND
0x1800287d0  call    McGenEventWrite_EventWriteTransfer
0x1800287d5  nop
0x1800287d6  lea     rcx, [rsp+198h+var_120]
0x1800287db  call    ??1?$unique_storage@U?$resource_policy@PEAU_WEBAUTHN_TRUSTED_DEVICE_LIST@@P6AXPEAU1@@Z$1?WebAuthNSyncFreeTrustedDeviceList@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_TRUSTED_DEVICE_LIST *,void (*)(_WEBAUTHN_TRUSTED_DEVICE_LIST *),&WebAuthNSyncFreeTrustedDeviceList(_WEBAUTHN_TRUSTED_DEVICE_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_TRUSTED_DEVICE_LIST *,_WEBAUTHN_TRUSTED_DEVICE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WEBAUTHN_TRUSTED_DEVICE_LIST *,void (*)(_WEBAUTHN_TRUSTED_DEVICE_LIST *),&WebAuthNSyncFreeTrustedDeviceList(_WEBAUTHN_TRUSTED_DEVICE_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_TRUSTED_DEVICE_LIST *,_WEBAUTHN_TRUSTED_DEVICE_LIST *,0,std::nullptr_t>>(void)
0x1800287e0  nop
0x1800287e1  lea     rcx, [rsp+198h+var_108]; this
0x1800287e9  call    ??1RecoveryBlob@NgcMCloud@@QEAA@XZ; NgcMCloud::RecoveryBlob::~RecoveryBlob(void)
0x1800287ee  nop
0x1800287ef  mov     rcx, [rsp+198h+pv]; pv
0x1800287f4  mov     [rsp+198h+pv], r12
0x1800287f9  test    rcx, rcx
0x1800287fc  jz      short loc_180028805
0x1800287fe  call    cs:__imp_CoTaskMemFree
0x180028804  nop
0x180028805  cmp     [rsp+198h+var_158], r12
0x18002880a  jz      short loc_180028817
0x18002880c  lea     rcx, [rsp+198h+var_158]
0x180028811  call    ?unconditional_release_ref@?$com_ptr@UISyncedPasskeyAuthenticatorLowPriv@@@winrt@@AEAAXXZ; winrt::com_ptr<ISyncedPasskeyAuthenticatorLowPriv>::unconditional_release_ref(void)
0x180028816  nop
0x180028817  cmp     [rsp+198h+var_160], r12
0x18002881c  jz      short loc_180028828
0x18002881e  lea     rcx, [rsp+198h+var_160]
0x180028823  call    ?unconditional_release_ref@?$com_ptr@UISyncedPasskeyAuthenticatorLowPriv@@@winrt@@AEAAXXZ; winrt::com_ptr<ISyncedPasskeyAuthenticatorLowPriv>::unconditional_release_ref(void)
0x180028828  mov     eax, 80070490h
0x18002882d  jmp     short loc_180028892
0x18002882f  mov     [rsp+198h+var_120], r12
0x180028834  mov     [r13+0], r14
0x180028838  lea     rcx, [rsp+198h+var_120]
0x18002883d  call    ??1?$unique_storage@U?$resource_policy@PEAU_WEBAUTHN_TRUSTED_DEVICE_LIST@@P6AXPEAU1@@Z$1?WebAuthNSyncFreeTrustedDeviceList@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_TRUSTED_DEVICE_LIST *,void (*)(_WEBAUTHN_TRUSTED_DEVICE_LIST *),&WebAuthNSyncFreeTrustedDeviceList(_WEBAUTHN_TRUSTED_DEVICE_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_TRUSTED_DEVICE_LIST *,_WEBAUTHN_TRUSTED_DEVICE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WEBAUTHN_TRUSTED_DEVICE_LIST *,void (*)(_WEBAUTHN_TRUSTED_DEVICE_LIST *),&WebAuthNSyncFreeTrustedDeviceList(_WEBAUTHN_TRUSTED_DEVICE_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_TRUSTED_DEVICE_LIST *,_WEBAUTHN_TRUSTED_DEVICE_LIST *,0,std::nullptr_t>>(void)
0x180028842  nop
0x180028843  lea     rcx, [rsp+198h+var_108]; this
0x18002884b  call    ??1RecoveryBlob@NgcMCloud@@QEAA@XZ; NgcMCloud::RecoveryBlob::~RecoveryBlob(void)
0x180028850  nop
0x180028851  mov     rcx, [rsp+198h+pv]; pv
0x180028856  mov     [rsp+198h+pv], r12
0x18002885b  test    rcx, rcx
  ... truncated ...
```
