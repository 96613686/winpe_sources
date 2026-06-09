# LicenseProxyService::RequestUserRootLicense(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x18005e530`
- end: `0x18005e980`
- name: `?RequestUserRootLicense@LicenseProxyService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `1104`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004738`
- `0x180004878`
- `0x180006a48`
- `0x18000c70c`
- `0x180013b50`
- `0x18003ffe0`
- `0x1800593bc`
- `0x18005e530`
- `0x18005e988`
- `0x18005ef2c`
- `0x18005efac`
- `0x18005efdc`
- `0x1800711b4`
- `0x180099224`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e81b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e81b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005e839`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005e839`

## string_xrefs

- `0x18005e63a`: `LicenseProxyService::RequestUserRootLicense`
- `0x18005e68d`: `LicenseProxyService::RequestUserRootLicense`
- `0x18005e873`: `LicenseProxyService::RequestUserRootLicense`
- `0x18005e934`: `LicenseProxyService::RequestUserRootLicense`
- `0x18005e681`: `Returning existing user root lease and key without a service request for %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall LicenseProxyService::RequestUserRootLicense(
        PTP_CALLBACK_INSTANCE Instance,
        _QWORD *Context,
        PTP_WORK Work)
{
  _QWORD *v3; // rsi
  int v4; // edi
  bool v5; // r14
  __int64 v6; // rcx
  int v7; // eax
  bool v8; // al
  __int64 v9; // rcx
  int v10; // eax
  _QWORD *v11; // rax
  wil *v12; // rcx
  _QWORD *v13; // rax
  int v14; // eax
  unsigned __int64 i; // rdx
  __int64 v16; // rcx
  __int64 v17; // rbx
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rbx
  __int64 v22; // rcx
  int LastError; // eax
  _QWORD *v24; // rbx
  _QWORD *v25; // rdx
  __int64 v26; // rax
  _QWORD *v27; // rbx
  _QWORD *v28; // rax
  const char *v29; // r9
  int Format; // [rsp+20h] [rbp-88h]
  int Formata; // [rsp+20h] [rbp-88h]
  int v32; // [rsp+40h] [rbp-68h] BYREF
  __int64 v33; // [rsp+48h] [rbp-60h] BYREF
  __int64 v34; // [rsp+50h] [rbp-58h] BYREF
  _QWORD *v35; // [rsp+58h] [rbp-50h]
  void **v36; // [rsp+60h] [rbp-48h] BYREF
  __int64 v37; // [rsp+68h] [rbp-40h] BYREF
  _QWORD v38[7]; // [rsp+70h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  wil *v41; // [rsp+C8h] [rbp+20h] BYREF

  if ( Context )
  {
    try
    {
      v3 = Context;
      v4 = 0;
      v5 = 0;
      v32 = 0;
      v35 = Context + 11;
      v6 = Context[11];
      if ( v6 )
      {
        LODWORD(v41) = 0;
        v7 = (*(__int64 (__fastcall **)(__int64, wil **, int *))(*(_QWORD *)v6 + 48LL))(v6, &v41, &v32);
        if ( v7 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x958,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
            (const char *)(unsigned int)v7,
            Format);
        v5 = (int)v41 > 0x10000000;
      }
      v8 = 0;
      v9 = v3[12];
      if ( v9 )
      {
        LODWORD(v41) = 0;
        LODWORD(v33) = 0;
        v10 = (*(__int64 (__fastcall **)(__int64, wil **, __int64 *))(*(_QWORD *)v9 + 48LL))(v9, &v41, &v33);
        if ( v10 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x960,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
            (const char *)(unsigned int)v10,
            Format);
        v8 = (int)v41 > 0x10000000;
      }
      if ( v32 == -2143318010 )
      {
        v11 = v3 + 7;
        if ( v3[10] > 7u )
          v11 = (_QWORD *)*v11;
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
          0x966u,
          "LicenseProxyService::RequestUserRootLicense",
          (wchar_t *)L"Not returning a user root lease because user root key indicates signed out (%s)",
          v11);
      }
      else if ( v5 && v8 )
      {
        v13 = v3 + 7;
        if ( v3[10] > 7u )
          v13 = (_QWORD *)*v13;
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
          0x96Fu,
          "LicenseProxyService::RequestUserRootLicense",
          (wchar_t *)L"Returning existing user root lease and key without a service request for %s",
          v13);
        LODWORD(v41) = 0;
        v36 = &Microsoft::WRL::Wrappers::HandleT<CoTaskMemBufferTraits>::`vftable';
        v37 = 0;
        v14 = (*(__int64 (__fastcall **)(_QWORD, wil **, __int64 *))(*(_QWORD *)v3[12] + 40LL))(v3[12], &v41, &v37);
        if ( v14 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x972,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
            (const char *)(unsigned int)v14,
            Formata);
        std::vector<unsigned char>::vector<unsigned char>(v38, (unsigned int)v41);
        for ( i = 0; i < (unsigned int)v41; ++i )
          *(_BYTE *)(v38[0] + i) = *(_BYTE *)(v37 + i);
        MakeCom<LicenseProxyService::LicenseResponse,>(&v33);
        v17 = v33;
        v18 = *(_QWORD *)(v33 + 56);
        if ( v18 == *(_QWORD *)(v33 + 64) )
        {
          std::vector<std::vector<unsigned char>>::_Emplace_reallocate<std::vector<unsigned char> const &>(
            v33 + 48,
            v18,
            v38);
        }
        else
        {
          std::_Default_allocator_traits<std::allocator<std::vector<unsigned char>>>::construct<std::vector<unsigned char>,std::vector<unsigned char> const &>(
            v16,
            v18,
            v38);
          *(_QWORD *)(v17 + 56) += 24LL;
        }
        v19 = MakeCom<LicenseProxyService::LicenseResponse,>(&v34);
        Microsoft::WRL::ComPtr<ILicenseResponseData>::operator=(v3 + 13, v19);
        v20 = v34;
        if ( v34 )
        {
          v34 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        }
        v21 = v3[13];
        Microsoft::WRL::ComPtr<ILicenseResponseData>::ComPtr<ILicenseResponseData>(&v34, &v33);
        std::vector<Microsoft::WRL::ComPtr<ILicenseResponseData>>::push_back(v21 + 96, &v34);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
        v22 = v33;
        if ( v33 )
        {
          v33 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        }
        std::vector<unsigned char>::_Tidy(v38);
        v36 = &Microsoft::WRL::Wrappers::HandleT<CoTaskMemBufferTraits>::`vftable';
        if ( v37 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<CoTaskMemBufferTraits>::InternalClose(&v36) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          RaiseException(LastError, 1u, 0, 0);
          __debugbreak();
        }
      }
      else
      {
        v24 = v3 + 7;
        if ( v3[10] <= 7u )
          v25 = v3 + 7;
        else
          v25 = (_QWORD *)*v24;
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
          0x96Au,
          "LicenseProxyService::RequestUserRootLicense",
          (wchar_t *)L"Requesting new user root for %s with validKey=%d, validLease=%d",
          v25,
          v5,
          v8);
        if ( v3[10] > 7u )
          v24 = (_QWORD *)*v24;
        v26 = LicenseProxyService::DoRequestUserRootLicense(
                *v3,
                (__int64)&v41,
                (unsigned __int16 **)v3 + 1,
                (TraceLoggingCorrelationVector *)v3[5],
                (__int64)(v3 + 6),
                (__int64)v24);
        Microsoft::WRL::ComPtr<ILicenseResponseData>::operator=(v3 + 13, v26);
        v12 = v41;
        if ( v41 )
        {
          v41 = 0;
          (*(void (__fastcall **)(wil *))(*(_QWORD *)v12 + 16LL))(v12);
        }
      }
    }
    catch ( ... )
    {
      LODWORD(v41) = wil::ResultFromCaughtException(v12);
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x985,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
        v29);
      v4 = (int)v41;
      v3 = Context;
      if ( (_DWORD)v41 == -2015559661 )
      {
        v4 = 0;
        v27 = v35;
        if ( *v35 )
        {
          v28 = Context + 7;
          if ( Context[10] > 7u )
            v28 = (_QWORD *)*v28;
          LogMessage(
            3u,
            "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
            0x98Eu,
            "LicenseProxyService::RequestUserRootLicense",
            (wchar_t *)L"Invalidating user root because authenticator indicates signed out (%s)",
            v28);
          (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v27 + 136LL))(*v27, 2151649286LL);
        }
      }
    }
    *((_DWORD *)v3 + 28) = v4;
  }
}

```

## disassembly

```asm
0x18005e530  test    rdx, rdx
0x18005e533  jz      locret_18005E97F
0x18005e539  mov     r11, rsp
0x18005e53c  mov     [r11+8], rbx
0x18005e540  mov     [r11+10h], rdx
0x18005e544  push    rsi
0x18005e545  push    rdi
0x18005e546  push    r14
0x18005e548  sub     rsp, 90h
0x18005e54f  mov     rsi, rdx
0x18005e552  xor     edi, edi
0x18005e554  mov     r14b, dil
0x18005e557  mov     [rsp+0A8h+var_68], edi
0x18005e55b  lea     rax, [rdx+58h]
0x18005e55f  mov     [rsp+0A8h+var_50], rax
0x18005e564  mov     rcx, [rax]
0x18005e567  test    rcx, rcx
0x18005e56a  jz      short loc_18005E5B3
0x18005e56c  mov     [r11+20h], edi
0x18005e570  mov     rax, [rcx]
0x18005e573  lea     r8, [r11-68h]
0x18005e577  lea     rdx, [r11+20h]
0x18005e57b  mov     rax, [rax+30h]
0x18005e57f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e584  mov     rcx, [rsp+0A8h]; this
0x18005e58c  test    eax, eax
0x18005e58e  jns     short loc_18005E5A4
0x18005e590  mov     r9d, eax; char *
0x18005e593  lea     r8, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x18005e59a  mov     edx, 958h; void *
0x18005e59f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005e5a4  cmp     dword ptr [rsp+0A8h+arg_18], 10000000h
0x18005e5af  setnle  r14b
0x18005e5b3  mov     al, dil
0x18005e5b6  mov     rcx, [rsi+60h]
0x18005e5ba  test    rcx, rcx
0x18005e5bd  jz      short loc_18005E611
0x18005e5bf  mov     dword ptr [rsp+0A8h+arg_18], edi
0x18005e5c6  mov     dword ptr [rsp+0A8h+var_60], edi
0x18005e5ca  mov     rax, [rcx]
0x18005e5cd  lea     r8, [rsp+0A8h+var_60]
0x18005e5d2  lea     rdx, [rsp+0A8h+arg_18]
0x18005e5da  mov     rax, [rax+30h]
0x18005e5de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e5e3  mov     rcx, [rsp+0A8h]; this
0x18005e5eb  test    eax, eax
0x18005e5ed  jns     short loc_18005E603
0x18005e5ef  mov     r9d, eax; char *
0x18005e5f2  lea     r8, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x18005e5f9  mov     edx, 960h; void *
0x18005e5fe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005e603  cmp     dword ptr [rsp+0A8h+arg_18], 10000000h
0x18005e60e  setnle  al
0x18005e611  cmp     [rsp+0A8h+var_68], 803F9006h
0x18005e619  jnz     short loc_18005E65D
0x18005e61b  lea     rax, [rsi+38h]
0x18005e61f  cmp     qword ptr [rax+18h], 7
0x18005e624  jbe     short loc_18005E629
0x18005e626  mov     rax, [rax]
0x18005e629  mov     [rsp+0A8h+var_80], rax
0x18005e62e  lea     rax, aNotReturningAU; "Not returning a user root lease because"...
0x18005e635  mov     [rsp+0A8h+Format], rax; Format
0x18005e63a  lea     r9, aLicenseproxyse_7; "LicenseProxyService::RequestUserRootLic"...
0x18005e641  mov     r8d, 966h; unsigned int
0x18005e647  lea     rdx, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x18005e64e  mov     ecx, 3; unsigned int
0x18005e653  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18005e658  jmp     loc_18005E8F0
0x18005e65d  test    r14b, r14b
0x18005e660  jz      loc_18005E840
0x18005e666  test    al, al
0x18005e668  jz      loc_18005E840
0x18005e66e  lea     rax, [rsi+38h]
0x18005e672  cmp     qword ptr [rax+18h], 7
0x18005e677  jbe     short loc_18005E67C
0x18005e679  mov     rax, [rax]
0x18005e67c  mov     [rsp+0A8h+var_80], rax
0x18005e681  lea     rax, aReturningExist_0; "Returning existing user root lease and "...
0x18005e688  mov     [rsp+0A8h+Format], rax; int
0x18005e68d  lea     r9, aLicenseproxyse_7; "LicenseProxyService::RequestUserRootLic"...
0x18005e694  mov     r8d, 96Fh; unsigned int
0x18005e69a  lea     rdx, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x18005e6a1  mov     ecx, 3; unsigned int
0x18005e6a6  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18005e6ab  mov     dword ptr [rsp+0A8h+arg_18], edi
0x18005e6b2  lea     r14, ??_7?$HandleT@UCoTaskMemBufferTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CoTaskMemBufferTraits>::`vftable'
0x18005e6b9  mov     [rsp+0A8h+var_48], r14
0x18005e6be  mov     [rsp+0A8h+var_40], rdi
0x18005e6c3  mov     rcx, [rsi+60h]
0x18005e6c7  mov     rax, [rcx]
0x18005e6ca  lea     r8, [rsp+0A8h+var_40]
0x18005e6cf  lea     rdx, [rsp+0A8h+arg_18]
0x18005e6d7  mov     rax, [rax+28h]
0x18005e6db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e6e0  mov     rcx, [rsp+0A8h]; this
0x18005e6e8  test    eax, eax
0x18005e6ea  jns     short loc_18005E700
0x18005e6ec  mov     r9d, eax; char *
0x18005e6ef  lea     r8, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x18005e6f6  mov     edx, 972h; void *
0x18005e6fb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005e700  mov     edx, dword ptr [rsp+0A8h+arg_18]
0x18005e707  lea     rcx, [rsp+0A8h+var_38]
0x18005e70c  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18005e711  nop
0x18005e712  mov     rdx, rdi
0x18005e715  cmp     dword ptr [rsp+0A8h+arg_18], edi
0x18005e71c  jbe     short loc_18005E73D
0x18005e71e  mov     rax, [rsp+0A8h+var_40]
0x18005e723  mov     cl, [rax+rdx]
0x18005e726  mov     rax, [rsp+0A8h+var_38]
0x18005e72b  mov     [rax+rdx], cl
0x18005e72e  inc     rdx
0x18005e731  mov     eax, dword ptr [rsp+0A8h+arg_18]
0x18005e738  cmp     rdx, rax
0x18005e73b  jb      short loc_18005E71E
0x18005e73d  lea     rcx, [rsp+0A8h+var_60]
0x18005e742  call    ??$MakeCom@VLicenseResponse@LicenseProxyService@@$$V@@YA?AV?$ComPtr@VLicenseResponse@LicenseProxyService@@@WRL@Microsoft@@XZ; MakeCom<LicenseProxyService::LicenseResponse,>(void)
0x18005e747  nop
0x18005e748  mov     rbx, [rsp+0A8h+var_60]
0x18005e74d  mov     rdx, [rbx+38h]
0x18005e751  lea     r8, [rsp+0A8h+var_38]
0x18005e756  cmp     rdx, [rbx+40h]
0x18005e75a  jz      short loc_18005E768
0x18005e75c  call    ??$construct@V?$vector@EV?$allocator@E@std@@@std@@AEBV12@@?$_Default_allocator_traits@V?$allocator@V?$vector@EV?$allocator@E@std@@@std@@@std@@@std@@SAXAEAV?$allocator@V?$vector@EV?$allocator@E@std@@@std@@@1@QEAV?$vector@EV?$allocator@E@std@@@1@AEBV31@@Z; std::_Default_allocator_traits<std::allocator<std::vector<uchar>>>::construct<std::vector<uchar>,std::vector<uchar> const &>(std::allocator<std::vector<uchar>> &,std::vector<uchar> * const,std::vector<uchar> const &)
0x18005e761  add     qword ptr [rbx+38h], 18h
0x18005e766  jmp     short loc_18005E771
0x18005e768  lea     rcx, [rbx+30h]
0x18005e76c  call    ??$_Emplace_reallocate@AEBV?$vector@EV?$allocator@E@std@@@std@@@?$vector@V?$vector@EV?$allocator@E@std@@@std@@V?$allocator@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@AEAAPEAV?$vector@EV?$allocator@E@std@@@1@QEAV21@AEBV21@@Z; std::vector<std::vector<uchar>>::_Emplace_reallocate<std::vector<uchar> const &>(std::vector<uchar> * const,std::vector<uchar> const &)
0x18005e771  lea     rcx, [rsp+0A8h+var_58]
0x18005e776  call    ??$MakeCom@VLicenseResponse@LicenseProxyService@@$$V@@YA?AV?$ComPtr@VLicenseResponse@LicenseProxyService@@@WRL@Microsoft@@XZ; MakeCom<LicenseProxyService::LicenseResponse,>(void)
0x18005e77b  mov     rdx, rax
0x18005e77e  lea     rcx, [rsi+68h]
0x18005e782  call    ??4?$ComPtr@UILicenseResponseData@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<ILicenseResponseData>::operator=(Microsoft::WRL::ComPtr<ILicenseResponseData> &&)
0x18005e787  nop
0x18005e788  mov     rcx, [rsp+0A8h+var_58]
0x18005e78d  test    rcx, rcx
0x18005e790  jz      short loc_18005E7A4
0x18005e792  mov     [rsp+0A8h+var_58], rdi
0x18005e797  mov     rax, [rcx]
0x18005e79a  mov     rax, [rax+10h]
0x18005e79e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e7a3  nop
0x18005e7a4  mov     rbx, [rsi+68h]
0x18005e7a8  lea     rdx, [rsp+0A8h+var_60]
0x18005e7ad  lea     rcx, [rsp+0A8h+var_58]
0x18005e7b2  call    ??$?0VLicenseResponse@LicenseProxyService@@@?$ComPtr@UILicenseResponseData@@@WRL@Microsoft@@QEAA@AEBV?$ComPtr@VLicenseResponse@LicenseProxyService@@@12@PEAPEAX@Z; Microsoft::WRL::ComPtr<ILicenseResponseData>::ComPtr<ILicenseResponseData>(Microsoft::WRL::ComPtr<LicenseProxyService::LicenseResponse> const &,void * *)
0x18005e7b7  nop
0x18005e7b8  lea     rdx, [rsp+0A8h+var_58]
0x18005e7bd  lea     rcx, [rbx+60h]
0x18005e7c1  call    ?push_back@?$vector@V?$ComPtr@UILicenseResponseData@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UILicenseResponseData@@@WRL@Microsoft@@@std@@@std@@QEAAX$$QEAV?$ComPtr@UILicenseResponseData@@@WRL@Microsoft@@@Z; std::vector<Microsoft::WRL::ComPtr<ILicenseResponseData>>::push_back(Microsoft::WRL::ComPtr<ILicenseResponseData> &&)
0x18005e7c6  nop
0x18005e7c7  lea     rcx, [rsp+0A8h+var_58]
0x18005e7cc  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18005e7d1  nop
0x18005e7d2  mov     rcx, [rsp+0A8h+var_60]
0x18005e7d7  test    rcx, rcx
0x18005e7da  jz      short loc_18005E7EE
0x18005e7dc  mov     [rsp+0A8h+var_60], rdi
0x18005e7e1  mov     rax, [rcx]
0x18005e7e4  mov     rax, [rax+10h]
0x18005e7e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e7ed  nop
0x18005e7ee  lea     rcx, [rsp+0A8h+var_38]
0x18005e7f3  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18005e7f8  nop
0x18005e7f9  mov     [rsp+0A8h+var_48], r14
0x18005e7fe  cmp     [rsp+0A8h+var_40], rdi
0x18005e803  jz      loc_18005E8F0
0x18005e809  lea     rcx, [rsp+0A8h+var_48]
0x18005e80e  call    ?InternalClose@?$HandleT@UCoTaskMemBufferTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<CoTaskMemBufferTraits>::InternalClose(void)
0x18005e813  test    al, al
0x18005e815  jnz     loc_18005E8F0
0x18005e81b  call    cs:__imp_GetLastError
0x18005e821  test    eax, eax
0x18005e823  jle     short loc_18005E82D
0x18005e825  movzx   eax, ax
0x18005e828  or      eax, 80070000h
0x18005e82d  xor     r9d, r9d; lpArguments
0x18005e830  xor     r8d, r8d; nNumberOfArguments
0x18005e833  lea     edx, [r9+1]; dwExceptionFlags
0x18005e837  mov     ecx, eax; dwExceptionCode
0x18005e839  call    cs:__imp_RaiseException
0x18005e83f  int     3; Trap to Debugger
0x18005e840  lea     rbx, [rsi+38h]
0x18005e844  cmp     qword ptr [rbx+18h], 7
0x18005e849  jbe     short loc_18005E850
0x18005e84b  mov     rdx, [rbx]
0x18005e84e  jmp     short loc_18005E853
0x18005e850  mov     rdx, rbx
0x18005e853  movzx   eax, al
0x18005e856  movzx   ecx, r14b
0x18005e85a  mov     [rsp+0A8h+var_70], eax
0x18005e85e  mov     [rsp+0A8h+var_78], ecx
0x18005e862  mov     [rsp+0A8h+var_80], rdx
0x18005e867  lea     rax, aRequestingNewU; "Requesting new user root for %s with va"...
0x18005e86e  mov     [rsp+0A8h+Format], rax; Format
0x18005e873  lea     r9, aLicenseproxyse_7; "LicenseProxyService::RequestUserRootLic"...
0x18005e87a  mov     r8d, 96Ah; unsigned int
0x18005e880  lea     rdx, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x18005e887  mov     ecx, 3; unsigned int
0x18005e88c  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18005e891  cmp     qword ptr [rbx+18h], 7
0x18005e896  jbe     short loc_18005E89B
0x18005e898  mov     rbx, [rbx]
0x18005e89b  lea     rax, [rsi+30h]
0x18005e89f  lea     r8, [rsi+8]
0x18005e8a3  mov     [rsp+0A8h+var_80], rbx
0x18005e8a8  mov     [rsp+0A8h+Format], rax
0x18005e8ad  mov     r9, [rsi+28h]
0x18005e8b1  lea     rdx, [rsp+0A8h+arg_18]
0x18005e8b9  mov     rcx, [rsi]
0x18005e8bc  call    ?DoRequestUserRootLicense@LicenseProxyService@@AEAA?AV?$ComPtr@VLicenseResponse@LicenseProxyService@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVTraceLoggingCorrelationVector@@AEBV?$ComPtr@UILicenseIdentityContext@@@34@PEBG@Z; LicenseProxyService::DoRequestUserRootLicense(std::wstring const &,TraceLoggingCorrelationVector *,Microsoft::WRL::ComPtr<ILicenseIdentityContext> const &,ushort const *)
0x18005e8c1  lea     rcx, [rsi+68h]
0x18005e8c5  mov     rdx, rax
0x18005e8c8  call    ??4?$ComPtr@UILicenseResponseData@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<ILicenseResponseData>::operator=(Microsoft::WRL::ComPtr<ILicenseResponseData> &&)
0x18005e8cd  nop
0x18005e8ce  mov     rcx, [rsp+0A8h+arg_18]
0x18005e8d6  test    rcx, rcx
0x18005e8d9  jz      short loc_18005E8F0
0x18005e8db  mov     [rsp+0A8h+arg_18], rdi
0x18005e8e3  mov     rax, [rcx]
0x18005e8e6  mov     rax, [rax+10h]
0x18005e8ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e8ef  nop
0x18005e8f0  jmp     short loc_18005E969
0x18005e8f2  mov     edi, dword ptr [rsp+0A8h+arg_18]
0x18005e8f9  mov     rsi, [rsp+0A8h+arg_8]
0x18005e901  cmp     edi, 87DD0013h
0x18005e907  jnz     short loc_18005E969
0x18005e909  xor     edi, edi
0x18005e90b  mov     rbx, [rsp+0A8h+var_50]
0x18005e910  cmp     [rbx], rdi
0x18005e913  jz      short loc_18005E969
0x18005e915  lea     rax, [rsi+38h]
0x18005e919  cmp     qword ptr [rax+18h], 7
0x18005e91e  jbe     short loc_18005E923
0x18005e920  mov     rax, [rax]
0x18005e923  mov     [rsp+0A8h+var_80], rax
0x18005e928  lea     rax, aInvalidatingUs; "Invalidating user root because authenti"...
0x18005e92f  mov     [rsp+0A8h+Format], rax; Format
0x18005e934  lea     r9, aLicenseproxyse_7; "LicenseProxyService::RequestUserRootLic"...
0x18005e93b  mov     r8d, 98Eh; unsigned int
0x18005e941  lea     rdx, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x18005e948  mov     ecx, 3; unsigned int
0x18005e94d  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18005e952  mov     rcx, [rbx]
0x18005e955  mov     rax, [rcx]
0x18005e958  mov     edx, 803F9006h
0x18005e95d  mov     rax, [rax+88h]
0x18005e964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e969  mov     [rsi+70h], edi
0x18005e96c  mov     rbx, [rsp+0A8h+arg_0]
0x18005e974  add     rsp, 90h
0x18005e97b  pop     r14
0x18005e97d  pop     rdi
0x18005e97e  pop     rsi
0x18005e97f  retn
```
