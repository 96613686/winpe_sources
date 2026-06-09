# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *,ulong)

- ea: `0x180039140`
- end: `0x1800393f2`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z`
- size: `690`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), int, __int64, DWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003827c`

## callees

- `0x18000d7a0`
- `0x18002de7c`
- `0x1800317f8`
- `0x180039140`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180039217`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180039217`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039226`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039226`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800392cb`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800392cb`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        int a2,
        __int64 a3,
        DWORD a4)
{
  _DWORD *v6; // rbx
  HANDLE Event; // rax
  signed int LastError; // eax
  signed int v9; // esi
  __int64 v10; // rax
  HRESULT v11; // ecx
  char v12; // al
  int (__fastcall *v13)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v14; // rax
  int (__fastcall *v15)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v16; // rax
  __int64 v17; // rcx
  unsigned int v18; // ebx
  _DWORD *v20; // [rsp+30h] [rbp-20h]
  HANDLE pHandles[2]; // [rsp+40h] [rbp-10h] BYREF
  __int64 v22; // [rsp+80h] [rbp+30h] BYREF
  int v23; // [rsp+88h] [rbp+38h] BYREF
  __int64 dwindex; // [rsp+90h] [rbp+40h] BYREF

  dwindex = a3;
  v23 = a2;
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[1])(a1);
  v20 = 0;
  v6 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v6 )
  {
    v23 = -2147024882;
    goto LABEL_30;
  }
  *(_QWORD *)v6 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>::`vftable';
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(v6 + 2);
  v6[11] = 1;
  *(_QWORD *)v6 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>'};
  *((_QWORD *)v6 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>'::`2'::FTMEventDelegate::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v6 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v6 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>'::`2'::FTMEventDelegate::`vftable';
  v6[12] = 0;
  *((_QWORD *)v6 + 7) = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  *((_QWORD *)v6 + 7) = Event;
  if ( Event )
  {
    v10 = *(_QWORD *)v6;
  }
  else
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    v10 = *(_QWORD *)v6;
    if ( v9 < 0 )
    {
      (*(void (__fastcall **)(_DWORD *))(v10 + 16))(v6);
      v23 = v9;
      goto LABEL_30;
    }
  }
  (*(void (__fastcall **)(_DWORD *))(v10 + 8))(v6);
  v20 = v6;
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
  v23 = 0;
  v23 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), _DWORD *))(*a1)[6])(a1, v6);
  if ( v23 >= 0 )
  {
    pHandles[0] = *((HANDLE *)v6 + 7);
    pHandles[1] = 0;
    LODWORD(dwindex) = 0;
    v11 = CoWaitForMultipleHandles(8u, a4, 1u, pHandles, (LPDWORD)&dwindex);
    v23 = v11;
    if ( v11 >= 0 && (_DWORD)dwindex )
    {
      v23 = -2147023673;
    }
    else
    {
      v12 = 0;
      if ( v11 != -2147417835 )
        goto LABEL_20;
      v23 = -2147023436;
    }
    v12 = 1;
LABEL_20:
    v22 = 0;
    if ( v12 )
    {
      v13 = **a1;
      v14 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(&v22);
      if ( v13(a1, &GUID_00000036_0000_0000_c000_000000000046, v14) >= 0 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 72LL))(v22);
    }
    if ( v23 >= 0 && v20[12] != 1 )
    {
      if ( v22
        || (v15 = **a1,
            v16 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(&v22),
            v15(a1, &GUID_00000036_0000_0000_c000_000000000046, v16) >= 0) )
      {
        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 64LL))(v22, &v23);
      }
    }
    v17 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
  }
LABEL_30:
  v18 = v23;
  if ( v20 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v20 + 16LL))(v20);
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[2])(a1);
  return v18;
}

```

## disassembly

```asm
0x180039140  mov     [rsp-28h+arg_18], rbx
0x180039145  mov     [rsp-28h+dwindex], r8
0x18003914a  mov     [rsp-28h+arg_8], edx
0x18003914e  push    rbp
0x18003914f  push    rsi
0x180039150  push    rdi
0x180039151  push    r14
0x180039153  push    r15
0x180039155  mov     rbp, rsp
0x180039158  sub     rsp, 50h
0x18003915c  mov     r14d, r9d
0x18003915f  mov     rdi, rcx
0x180039162  mov     [rbp+var_18], rcx
0x180039166  xor     r15d, r15d
0x180039169  test    rcx, rcx
0x18003916c  jz      short loc_18003917B
0x18003916e  mov     rax, [rcx]
0x180039171  mov     rax, [rax+8]
0x180039175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003917a  nop
0x18003917b  mov     [rbp+var_20], r15
0x18003917f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180039186  mov     ecx, 40h ; '@'; unsigned __int64
0x18003918b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180039190  mov     rbx, rax
0x180039193  test    rax, rax
0x180039196  jnz     short loc_1800391A4
0x180039198  mov     [rbp+arg_8], 8007000Eh
0x18003919f  jmp     loc_1800393AA
0x1800391a4  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>::`vftable'
0x1800391ab  mov     [rbx], rax
0x1800391ae  lea     rsi, [rbx+8]
0x1800391b2  mov     rcx, rsi
0x1800391b5  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x1800391ba  mov     dword ptr [rbx+2Ch], 1
0x1800391c1  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>'}
0x1800391c8  mov     [rbx], rax
0x1800391cb  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800391d2  mov     [rsi], rax
0x1800391d5  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800391dc  test    rcx, rcx
0x1800391df  jz      short loc_1800391EE
0x1800391e1  mov     rax, [rcx]
0x1800391e4  mov     rax, [rax+8]
0x1800391e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800391ed  nop
0x1800391ee  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z@6B?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>'}
0x1800391f5  mov     [rbx], rax
0x1800391f8  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800391ff  mov     [rsi], rax
0x180039202  mov     [rbx+30h], r15d
0x180039206  mov     [rbx+38h], r15
0x18003920a  mov     r9d, 1F0003h; dwDesiredAccess
0x180039210  xor     r8d, r8d; dwFlags
0x180039213  xor     edx, edx; lpName
0x180039215  xor     ecx, ecx; lpEventAttributes
0x180039217  call    cs:__imp_CreateEventExW
0x18003921d  mov     [rbx+38h], rax
0x180039221  test    rax, rax
0x180039224  jnz     short loc_180039257
0x180039226  call    cs:__imp_GetLastError
0x18003922c  mov     esi, eax
0x18003922e  test    eax, eax
0x180039230  jle     short loc_18003923B
0x180039232  movzx   esi, ax
0x180039235  or      esi, 80070000h
0x18003923b  mov     rax, [rbx]
0x18003923e  test    esi, esi
0x180039240  jns     short loc_18003925A
0x180039242  mov     rcx, rbx
0x180039245  mov     rax, [rax+10h]
0x180039249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003924e  nop
0x18003924f  mov     [rbp+arg_8], esi
0x180039252  jmp     loc_1800393AA
0x180039257  mov     rax, [rbx]
0x18003925a  mov     rcx, rbx
0x18003925d  mov     rax, [rax+8]
0x180039261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039266  nop
0x180039267  mov     [rbp+var_20], rbx
0x18003926b  mov     rax, [rbx]
0x18003926e  mov     rcx, rbx
0x180039271  mov     rax, [rax+10h]
0x180039275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003927a  nop
0x18003927b  mov     [rbp+arg_8], r15d
0x18003927f  mov     rax, [rdi]
0x180039282  mov     rdx, [rbp+var_20]
0x180039286  mov     rcx, rdi
0x180039289  mov     rax, [rax+30h]
0x18003928d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039292  mov     [rbp+arg_8], eax
0x180039295  test    eax, eax
0x180039297  js      loc_1800393AA
0x18003929d  mov     rax, [rbp+var_20]
0x1800392a1  mov     rcx, [rax+38h]
0x1800392a5  mov     [rbp+pHandles], rcx
0x1800392a9  mov     [rbp+var_8], r15
0x1800392ad  mov     dword ptr [rbp+dwindex], r15d
0x1800392b1  lea     rax, [rbp+dwindex]
0x1800392b5  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x1800392ba  lea     r9, [rbp+pHandles]; pHandles
0x1800392be  mov     r8d, 1; cHandles
0x1800392c4  mov     edx, r14d; dwTimeout
0x1800392c7  lea     ecx, [r8+7]; dwFlags
0x1800392cb  call    cs:__imp_CoWaitForMultipleHandles
0x1800392d1  mov     ecx, eax
0x1800392d3  mov     [rbp+arg_8], eax
0x1800392d6  test    eax, eax
0x1800392d8  js      short loc_1800392E9
0x1800392da  cmp     dword ptr [rbp+dwindex], r15d
0x1800392de  jz      short loc_1800392E9
0x1800392e0  mov     [rbp+arg_8], 800704C7h
0x1800392e7  jmp     short loc_1800392FB
0x1800392e9  mov     al, r15b
0x1800392ec  cmp     ecx, 80010115h
0x1800392f2  jnz     short loc_1800392FD
0x1800392f4  mov     [rbp+arg_8], 800705B4h
0x1800392fb  mov     al, 1
0x1800392fd  mov     [rbp+arg_0], r15
0x180039301  test    al, al
0x180039303  jz      short loc_18003933D
0x180039305  mov     rax, [rdi]
0x180039308  mov     rbx, [rax]
0x18003930b  lea     rcx, [rbp+arg_0]
0x18003930f  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x180039314  mov     r8, rax
0x180039317  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18003931e  mov     rcx, rdi
0x180039321  mov     rax, rbx
0x180039324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039329  test    eax, eax
0x18003932b  js      short loc_18003933D
0x18003932d  mov     rcx, [rbp+arg_0]
0x180039331  mov     rax, [rcx]
0x180039334  mov     rax, [rax+48h]
0x180039338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003933d  cmp     [rbp+arg_8], r15d
0x180039341  jl      short loc_180039390
0x180039343  mov     rax, [rbp+var_20]
0x180039347  cmp     dword ptr [rax+30h], 1
0x18003934b  jz      short loc_180039390
0x18003934d  cmp     [rbp+arg_0], r15
0x180039351  jnz     short loc_18003937B
0x180039353  mov     rax, [rdi]
0x180039356  mov     rbx, [rax]
0x180039359  lea     rcx, [rbp+arg_0]
0x18003935d  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x180039362  mov     r8, rax
0x180039365  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18003936c  mov     rcx, rdi
0x18003936f  mov     rax, rbx
0x180039372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039377  test    eax, eax
0x180039379  js      short loc_180039390
0x18003937b  mov     rcx, [rbp+arg_0]
0x18003937f  mov     rax, [rcx]
0x180039382  lea     rdx, [rbp+arg_8]
0x180039386  mov     rax, [rax+40h]
0x18003938a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003938f  nop
0x180039390  mov     rcx, [rbp+arg_0]
0x180039394  test    rcx, rcx
0x180039397  jz      short loc_1800393AA
0x180039399  mov     [rbp+arg_0], r15
0x18003939d  mov     rax, [rcx]
0x1800393a0  mov     rax, [rax+10h]
0x1800393a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800393a9  nop
0x1800393aa  mov     ebx, [rbp+arg_8]
0x1800393ad  mov     rcx, [rbp+var_20]
0x1800393b1  test    rcx, rcx
0x1800393b4  jz      short loc_1800393C7
0x1800393b6  mov     [rbp+var_20], r15
0x1800393ba  mov     rax, [rcx]
0x1800393bd  mov     rax, [rax+10h]
0x1800393c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800393c6  nop
0x1800393c7  test    rdi, rdi
0x1800393ca  jz      short loc_1800393DC
0x1800393cc  mov     rcx, [rdi]
0x1800393cf  mov     rax, [rcx+10h]
0x1800393d3  mov     rcx, rdi
0x1800393d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800393db  nop
0x1800393dc  mov     eax, ebx
0x1800393de  mov     rbx, [rsp+50h+arg_18]
0x1800393e6  add     rsp, 50h
0x1800393ea  pop     r15
0x1800393ec  pop     r14
0x1800393ee  pop     rdi
0x1800393ef  pop     rsi
0x1800393f0  pop     rbp
0x1800393f1  retn
```
