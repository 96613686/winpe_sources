# RetailDemoUserAgent::CleanupVirtualDesktops(void)

- ea: `0x18003982c`
- end: `0x180039a35`
- name: `?CleanupVirtualDesktops@RetailDemoUserAgent@@AEAAXXZ`
- size: `521`
- prototype: `void __fastcall(RetailDemoUserAgent *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180040500`

## callees

- `0x180008bbc`
- `0x18000e330`
- `0x18001c904`
- `0x180034e64`
- `0x180034f3c`
- `0x180035034`
- `0x18003982c`
- `0x180050010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x18003985f`
- `SHCORE!IUnknown_QueryService` at `0x18003985f`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall RetailDemoUserAgent::CleanupVirtualDesktops(RetailDemoUserAgent *this)
{
  IUnknown **v1; // rax
  HRESULT v2; // ebx
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // rax
  __int64 v6; // rax
  unsigned int i; // ebx
  __int64 v8; // rax
  __int64 v9; // [rsp+30h] [rbp-20h] BYREF
  void *ppvOut; // [rsp+38h] [rbp-18h] BYREF
  _QWORD v11[2]; // [rsp+40h] [rbp-10h] BYREF
  HRESULT v12; // [rsp+68h] [rbp+18h] BYREF
  unsigned int v13; // [rsp+70h] [rbp+20h] BYREF
  __int64 *v14; // [rsp+78h] [rbp+28h] BYREF

  ppvOut = 0;
  v1 = (IUnknown **)CWRLObjectWithGITSite::SiteUnk(this, v11);
  v2 = IUnknown_QueryService(
         *v1,
         (const GUID *const)&SID_VirtualDesktopManager,
         &GUID_4970ba3d_fd4e_4647_bea3_d89076ef4b9c,
         &ppvOut);
  v12 = v2;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v11, v3, v4);
  if ( v2 >= 0 )
  {
    v14 = 0;
    v5 = *(_QWORD *)ppvOut;
    v14 = 0;
    v12 = (*(__int64 (__fastcall **)(void *, __int64 **))(v5 + 56))(ppvOut, &v14);
    if ( v12 < 0
      || (v13 = 0, v12 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v14 + 24))(v14, &v13), v12 < 0) )
    {
      RetailDemoTelemetry::VirtualDesktopsCleanupFailed<long &>(&v12);
    }
    else
    {
      v9 = 0;
      v6 = *v14;
      v9 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, GUID *, __int64 *))(v6 + 32))(
              v14,
              0,
              &GUID_3f07f4be_b107_441a_af0f_39d82529072c,
              &v9);
      if ( v12 >= 0 )
      {
        for ( i = 1; i < v13; ++i )
        {
          v11[0] = 0;
          v8 = *v14;
          v11[0] = 0;
          v12 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, GUID *, _QWORD *))(v8 + 32))(
                  v14,
                  i,
                  &GUID_3f07f4be_b107_441a_af0f_39d82529072c,
                  v11);
          if ( v12 >= 0 )
          {
            v12 = (*(__int64 (__fastcall **)(void *, _QWORD, __int64))(*(_QWORD *)ppvOut + 104LL))(ppvOut, v11[0], v9);
            if ( v12 < 0 )
            {
              RetailDemoTelemetry::RemoveVirtualDesktopFailed<long &>(&v12);
              v12 = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD))(*(_QWORD *)ppvOut + 128LL))(ppvOut, v11[0], 0);
              if ( v12 < 0 )
                RetailDemoTelemetry::ResetVirtualDesktopNameFailed<long &>(&v12);
            }
          }
          else
          {
            RetailDemoTelemetry::VirtualDesktopsCleanupFailed<long &>(&v12);
          }
          wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(v11);
        }
        v12 = (*(__int64 (__fastcall **)(void *, __int64, _QWORD))(*(_QWORD *)ppvOut + 128LL))(ppvOut, v9, 0);
        if ( v12 < 0 )
          RetailDemoTelemetry::ResetVirtualDesktopNameFailed<long &>(&v12);
      }
      else
      {
        RetailDemoTelemetry::VirtualDesktopsCleanupFailed<long &>(&v12);
      }
      wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v9);
    }
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v14);
  }
  else
  {
    RetailDemoTelemetry::VirtualDesktopsCleanupFailed<long &>(&v12);
  }
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&ppvOut);
}

```

## disassembly

```asm
0x18003982c  mov     [rsp-8+arg_0], rbx
0x180039831  push    rbp
0x180039832  mov     rbp, rsp
0x180039835  sub     rsp, 50h
0x180039839  mov     [rbp+ppvOut], 0
0x180039841  lea     rdx, [rbp+var_10]
0x180039845  call    ?SiteUnk@CWRLObjectWithGITSite@@IEAA?AV?$ComPtr@UIUnknown@@@WRL@Microsoft@@XZ; CWRLObjectWithGITSite::SiteUnk(void)
0x18003984a  lea     r9, [rbp+ppvOut]; ppvOut
0x18003984e  lea     r8, _GUID_4970ba3d_fd4e_4647_bea3_d89076ef4b9c; riid
0x180039855  lea     rdx, SID_VirtualDesktopManager; guidService
0x18003985c  mov     rcx, [rax]; punk
0x18003985f  call    cs:__imp_IUnknown_QueryService
0x180039865  mov     ebx, eax
0x180039867  mov     [rbp+arg_8], eax
0x18003986a  lea     rcx, [rbp+var_10]
0x18003986e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180039873  test    ebx, ebx
0x180039875  jns     short loc_180039885
0x180039877  lea     rcx, [rbp+arg_8]
0x18003987b  call    ??$VirtualDesktopsCleanupFailed@AEAJ@RetailDemoTelemetry@@SAXAEAJ@Z; RetailDemoTelemetry::VirtualDesktopsCleanupFailed<long &>(long &)
0x180039880  jmp     loc_180039A21
0x180039885  mov     [rbp+arg_18], 0
0x18003988d  mov     rcx, [rbp+ppvOut]
0x180039891  mov     rax, [rcx]
0x180039894  mov     [rbp+arg_18], 0
0x18003989c  lea     rdx, [rbp+arg_18]
0x1800398a0  mov     rax, [rax+38h]
0x1800398a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800398a9  mov     [rbp+arg_8], eax
0x1800398ac  test    eax, eax
0x1800398ae  js      loc_180039A0D
0x1800398b4  mov     [rbp+arg_10], 0
0x1800398bb  mov     rcx, [rbp+arg_18]
0x1800398bf  mov     rax, [rcx]
0x1800398c2  lea     rdx, [rbp+arg_10]
0x1800398c6  mov     rax, [rax+18h]
0x1800398ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800398cf  mov     [rbp+arg_8], eax
0x1800398d2  test    eax, eax
0x1800398d4  js      loc_180039A0D
0x1800398da  mov     [rbp+var_20], 0
0x1800398e2  mov     rcx, [rbp+arg_18]
0x1800398e6  mov     rax, [rcx]
0x1800398e9  mov     [rbp+var_20], 0
0x1800398f1  lea     r9, [rbp+var_20]
0x1800398f5  lea     r8, _GUID_3f07f4be_b107_441a_af0f_39d82529072c
0x1800398fc  xor     edx, edx
0x1800398fe  mov     rax, [rax+20h]
0x180039902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039907  mov     [rbp+arg_8], eax
0x18003990a  test    eax, eax
0x18003990c  jns     short loc_180039926
0x18003990e  lea     rcx, [rbp+arg_8]
0x180039912  call    ??$VirtualDesktopsCleanupFailed@AEAJ@RetailDemoTelemetry@@SAXAEAJ@Z; RetailDemoTelemetry::VirtualDesktopsCleanupFailed<long &>(long &)
0x180039917  nop
0x180039918  lea     rcx, [rbp+var_20]
0x18003991c  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x180039921  jmp     loc_180039A17
0x180039926  mov     ebx, 1
0x18003992b  cmp     [rbp+arg_10], ebx
0x18003992e  jbe     loc_1800399DA
0x180039934  mov     [rbp+var_10], 0
0x18003993c  mov     rcx, [rbp+arg_18]
0x180039940  mov     rax, [rcx]
0x180039943  mov     [rbp+var_10], 0
0x18003994b  lea     r9, [rbp+var_10]
0x18003994f  lea     r8, _GUID_3f07f4be_b107_441a_af0f_39d82529072c
0x180039956  mov     edx, ebx
0x180039958  mov     rax, [rax+20h]
0x18003995c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039961  mov     [rbp+arg_8], eax
0x180039964  test    eax, eax
0x180039966  jns     short loc_180039973
0x180039968  lea     rcx, [rbp+arg_8]
0x18003996c  call    ??$VirtualDesktopsCleanupFailed@AEAJ@RetailDemoTelemetry@@SAXAEAJ@Z; RetailDemoTelemetry::VirtualDesktopsCleanupFailed<long &>(long &)
0x180039971  jmp     short loc_1800399C6
0x180039973  mov     rcx, [rbp+ppvOut]
0x180039977  mov     rax, [rcx]
0x18003997a  mov     r8, [rbp+var_20]
0x18003997e  mov     rdx, [rbp+var_10]
0x180039982  mov     rax, [rax+68h]
0x180039986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003998b  mov     [rbp+arg_8], eax
0x18003998e  test    eax, eax
0x180039990  jns     short loc_1800399C6
0x180039992  lea     rcx, [rbp+arg_8]
0x180039996  call    ??$RemoveVirtualDesktopFailed@AEAJ@RetailDemoTelemetry@@SAXAEAJ@Z; RetailDemoTelemetry::RemoveVirtualDesktopFailed<long &>(long &)
0x18003999b  mov     rcx, [rbp+ppvOut]
0x18003999f  mov     rax, [rcx]
0x1800399a2  xor     r8d, r8d
0x1800399a5  mov     rdx, [rbp+var_10]
0x1800399a9  mov     rax, [rax+80h]
0x1800399b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800399b5  mov     [rbp+arg_8], eax
0x1800399b8  test    eax, eax
0x1800399ba  jns     short loc_1800399C6
0x1800399bc  lea     rcx, [rbp+arg_8]
0x1800399c0  call    ??$ResetVirtualDesktopNameFailed@AEAJ@RetailDemoTelemetry@@SAXAEAJ@Z; RetailDemoTelemetry::ResetVirtualDesktopNameFailed<long &>(long &)
0x1800399c5  nop
0x1800399c6  lea     rcx, [rbp+var_10]
0x1800399ca  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x1800399cf  inc     ebx
0x1800399d1  cmp     ebx, [rbp+arg_10]
0x1800399d4  jb      loc_180039934
0x1800399da  mov     rcx, [rbp+ppvOut]
0x1800399de  mov     rax, [rcx]
0x1800399e1  xor     r8d, r8d
0x1800399e4  mov     rdx, [rbp+var_20]
0x1800399e8  mov     rax, [rax+80h]
0x1800399ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800399f4  mov     [rbp+arg_8], eax
0x1800399f7  test    eax, eax
0x1800399f9  jns     loc_180039918
0x1800399ff  lea     rcx, [rbp+arg_8]
0x180039a03  call    ??$ResetVirtualDesktopNameFailed@AEAJ@RetailDemoTelemetry@@SAXAEAJ@Z; RetailDemoTelemetry::ResetVirtualDesktopNameFailed<long &>(long &)
0x180039a08  jmp     loc_180039918
0x180039a0d  lea     rcx, [rbp+arg_8]
0x180039a11  call    ??$VirtualDesktopsCleanupFailed@AEAJ@RetailDemoTelemetry@@SAXAEAJ@Z; RetailDemoTelemetry::VirtualDesktopsCleanupFailed<long &>(long &)
0x180039a16  nop
0x180039a17  lea     rcx, [rbp+arg_18]
0x180039a1b  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x180039a20  nop
0x180039a21  lea     rcx, [rbp+ppvOut]
0x180039a25  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x180039a2a  mov     rbx, [rsp+50h+arg_0]
0x180039a2f  add     rsp, 50h
0x180039a33  pop     rbp
0x180039a34  retn
```
