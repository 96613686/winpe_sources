# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *> *,tagCOWAIT_FLAGS,void *,ulong)

- ea: `0x18003893c`
- end: `0x180038be2`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z`
- size: `678`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), DWORD, __int64, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800403c4`

## callees

- `0x18000d7a0`
- `0x18002de7c`
- `0x1800317f8`
- `0x18003893c`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180038a0f`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180038a0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038a1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038a1e`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180038ac4`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180038ac4`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        DWORD a2,
        __int64 a3,
        int a4)
{
  _DWORD *v5; // rbx
  HANDLE Event; // rax
  signed int LastError; // eax
  signed int v8; // esi
  __int64 v9; // rax
  HRESULT v10; // ecx
  char v11; // al
  int (__fastcall *v12)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v13; // rax
  int (__fastcall *v14)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v15; // rax
  __int64 v16; // rcx
  unsigned int v17; // ebx
  HANDLE pHandles[3]; // [rsp+38h] [rbp-18h] BYREF
  _DWORD *v20; // [rsp+80h] [rbp+30h]
  DWORD dwindex; // [rsp+88h] [rbp+38h] BYREF
  __int64 v22; // [rsp+90h] [rbp+40h] BYREF
  int v23; // [rsp+98h] [rbp+48h] BYREF

  v23 = a4;
  v22 = a3;
  dwindex = a2;
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[1])(a1);
  v20 = 0;
  v5 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v5 )
  {
    v23 = -2147024882;
    goto LABEL_30;
  }
  *(_QWORD *)v5 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>::`vftable';
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(v5 + 2);
  v5[11] = 1;
  *(_QWORD *)v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>'};
  *((_QWORD *)v5 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v5 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v5 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v5[12] = 0;
  *((_QWORD *)v5 + 7) = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  *((_QWORD *)v5 + 7) = Event;
  if ( Event )
  {
    v9 = *(_QWORD *)v5;
  }
  else
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    v9 = *(_QWORD *)v5;
    if ( v8 < 0 )
    {
      (*(void (__fastcall **)(_DWORD *))(v9 + 16))(v5);
      v23 = v8;
      goto LABEL_30;
    }
  }
  (*(void (__fastcall **)(_DWORD *))(v9 + 8))(v5);
  v20 = v5;
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v5 + 16LL))(v5);
  v23 = 0;
  v23 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), _DWORD *))(*a1)[6])(a1, v5);
  if ( v23 >= 0 )
  {
    pHandles[0] = *((HANDLE *)v5 + 7);
    pHandles[1] = 0;
    dwindex = 0;
    v10 = CoWaitForMultipleHandles(8u, 0x7530u, 1u, pHandles, &dwindex);
    v23 = v10;
    if ( v10 >= 0 && dwindex )
    {
      v23 = -2147023673;
    }
    else
    {
      v11 = 0;
      if ( v10 != -2147417835 )
        goto LABEL_20;
      v23 = -2147023436;
    }
    v11 = 1;
LABEL_20:
    v22 = 0;
    if ( v11 )
    {
      v12 = **a1;
      v13 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(&v22);
      if ( v12(a1, &GUID_00000036_0000_0000_c000_000000000046, v13) >= 0 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 72LL))(v22);
    }
    if ( v23 >= 0 && v20[12] != 1 )
    {
      if ( v22
        || (v14 = **a1,
            v15 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(&v22),
            v14(a1, &GUID_00000036_0000_0000_c000_000000000046, v15) >= 0) )
      {
        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 64LL))(v22, &v23);
      }
    }
    v16 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
  }
LABEL_30:
  v17 = v23;
  if ( v20 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v20 + 16LL))(v20);
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[2])(a1);
  return v17;
}

```

## disassembly

```asm
0x18003893c  mov     [rsp-28h+arg_18], r9d
0x180038941  mov     [rsp-28h+arg_10], r8
0x180038946  mov     [rsp-28h+dwindex], edx
0x18003894a  push    rbp
0x18003894b  push    rbx
0x18003894c  push    rsi
0x18003894d  push    rdi
0x18003894e  push    r14
0x180038950  mov     rbp, rsp
0x180038953  sub     rsp, 50h
0x180038957  mov     rdi, rcx
0x18003895a  mov     [rbp+var_20], rcx
0x18003895e  xor     r14d, r14d
0x180038961  test    rcx, rcx
0x180038964  jz      short loc_180038973
0x180038966  mov     rax, [rcx]
0x180038969  mov     rax, [rax+8]
0x18003896d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038972  nop
0x180038973  mov     [rbp+arg_0], r14
0x180038977  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003897e  mov     ecx, 40h ; '@'; unsigned __int64
0x180038983  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180038988  mov     rbx, rax
0x18003898b  test    rax, rax
0x18003898e  jnz     short loc_18003899C
0x180038990  mov     [rbp+arg_18], 8007000Eh
0x180038997  jmp     loc_180038BA3
0x18003899c  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>::`vftable'
0x1800389a3  mov     [rbx], rax
0x1800389a6  lea     rsi, [rbx+8]
0x1800389aa  mov     rcx, rsi
0x1800389ad  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x1800389b2  mov     dword ptr [rbx+2Ch], 1
0x1800389b9  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>'}
0x1800389c0  mov     [rbx], rax
0x1800389c3  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800389ca  mov     [rsi], rax
0x1800389cd  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800389d4  test    rcx, rcx
0x1800389d7  jz      short loc_1800389E6
0x1800389d9  mov     rax, [rcx]
0x1800389dc  mov     rax, [rax+8]
0x1800389e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800389e5  nop
0x1800389e6  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z@6B?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *> *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>'}
0x1800389ed  mov     [rbx], rax
0x1800389f0  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800389f7  mov     [rsi], rax
0x1800389fa  mov     [rbx+30h], r14d
0x1800389fe  mov     [rbx+38h], r14
0x180038a02  mov     r9d, 1F0003h; dwDesiredAccess
0x180038a08  xor     r8d, r8d; dwFlags
0x180038a0b  xor     edx, edx; lpName
0x180038a0d  xor     ecx, ecx; lpEventAttributes
0x180038a0f  call    cs:__imp_CreateEventExW
0x180038a15  mov     [rbx+38h], rax
0x180038a19  test    rax, rax
0x180038a1c  jnz     short loc_180038A4F
0x180038a1e  call    cs:__imp_GetLastError
0x180038a24  mov     esi, eax
0x180038a26  test    eax, eax
0x180038a28  jle     short loc_180038A33
0x180038a2a  movzx   esi, ax
0x180038a2d  or      esi, 80070000h
0x180038a33  mov     rax, [rbx]
0x180038a36  test    esi, esi
0x180038a38  jns     short loc_180038A52
0x180038a3a  mov     rcx, rbx
0x180038a3d  mov     rax, [rax+10h]
0x180038a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038a46  nop
0x180038a47  mov     [rbp+arg_18], esi
0x180038a4a  jmp     loc_180038BA3
0x180038a4f  mov     rax, [rbx]
0x180038a52  mov     rcx, rbx
0x180038a55  mov     rax, [rax+8]
0x180038a59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038a5e  nop
0x180038a5f  mov     [rbp+arg_0], rbx
0x180038a63  mov     rax, [rbx]
0x180038a66  mov     rcx, rbx
0x180038a69  mov     rax, [rax+10h]
0x180038a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038a72  nop
0x180038a73  mov     [rbp+arg_18], r14d
0x180038a77  mov     rax, [rdi]
0x180038a7a  mov     rdx, [rbp+arg_0]
0x180038a7e  mov     rcx, rdi
0x180038a81  mov     rax, [rax+30h]
0x180038a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038a8a  mov     [rbp+arg_18], eax
0x180038a8d  test    eax, eax
0x180038a8f  js      loc_180038BA3
0x180038a95  mov     rax, [rbp+arg_0]
0x180038a99  mov     rcx, [rax+38h]
0x180038a9d  mov     [rbp+pHandles], rcx
0x180038aa1  mov     [rbp+var_10], r14
0x180038aa5  mov     [rbp+dwindex], r14d
0x180038aa9  lea     rax, [rbp+dwindex]
0x180038aad  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x180038ab2  lea     r9, [rbp+pHandles]; pHandles
0x180038ab6  mov     edx, 7530h; dwTimeout
0x180038abb  mov     ecx, 8; dwFlags
0x180038ac0  lea     r8d, [rcx-7]; cHandles
0x180038ac4  call    cs:__imp_CoWaitForMultipleHandles
0x180038aca  mov     ecx, eax
0x180038acc  mov     [rbp+arg_18], eax
0x180038acf  test    eax, eax
0x180038ad1  js      short loc_180038AE2
0x180038ad3  cmp     [rbp+dwindex], r14d
0x180038ad7  jz      short loc_180038AE2
0x180038ad9  mov     [rbp+arg_18], 800704C7h
0x180038ae0  jmp     short loc_180038AF4
0x180038ae2  mov     al, r14b
0x180038ae5  cmp     ecx, 80010115h
0x180038aeb  jnz     short loc_180038AF6
0x180038aed  mov     [rbp+arg_18], 800705B4h
0x180038af4  mov     al, 1
0x180038af6  mov     [rbp+arg_10], r14
0x180038afa  test    al, al
0x180038afc  jz      short loc_180038B36
0x180038afe  mov     rax, [rdi]
0x180038b01  mov     rbx, [rax]
0x180038b04  lea     rcx, [rbp+arg_10]
0x180038b08  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x180038b0d  mov     r8, rax
0x180038b10  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180038b17  mov     rcx, rdi
0x180038b1a  mov     rax, rbx
0x180038b1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b22  test    eax, eax
0x180038b24  js      short loc_180038B36
0x180038b26  mov     rcx, [rbp+arg_10]
0x180038b2a  mov     rax, [rcx]
0x180038b2d  mov     rax, [rax+48h]
0x180038b31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b36  cmp     [rbp+arg_18], r14d
0x180038b3a  jl      short loc_180038B89
0x180038b3c  mov     rax, [rbp+arg_0]
0x180038b40  cmp     dword ptr [rax+30h], 1
0x180038b44  jz      short loc_180038B89
0x180038b46  cmp     [rbp+arg_10], r14
0x180038b4a  jnz     short loc_180038B74
0x180038b4c  mov     rax, [rdi]
0x180038b4f  mov     rbx, [rax]
0x180038b52  lea     rcx, [rbp+arg_10]
0x180038b56  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x180038b5b  mov     r8, rax
0x180038b5e  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180038b65  mov     rcx, rdi
0x180038b68  mov     rax, rbx
0x180038b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b70  test    eax, eax
0x180038b72  js      short loc_180038B89
0x180038b74  mov     rcx, [rbp+arg_10]
0x180038b78  mov     rax, [rcx]
0x180038b7b  lea     rdx, [rbp+arg_18]
0x180038b7f  mov     rax, [rax+40h]
0x180038b83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b88  nop
0x180038b89  mov     rcx, [rbp+arg_10]
0x180038b8d  test    rcx, rcx
0x180038b90  jz      short loc_180038BA3
0x180038b92  mov     [rbp+arg_10], r14
0x180038b96  mov     rax, [rcx]
0x180038b99  mov     rax, [rax+10h]
0x180038b9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038ba2  nop
0x180038ba3  mov     ebx, [rbp+arg_18]
0x180038ba6  mov     rcx, [rbp+arg_0]
0x180038baa  test    rcx, rcx
0x180038bad  jz      short loc_180038BC0
0x180038baf  mov     [rbp+arg_0], r14
0x180038bb3  mov     rax, [rcx]
0x180038bb6  mov     rax, [rax+10h]
0x180038bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038bbf  nop
0x180038bc0  test    rdi, rdi
0x180038bc3  jz      short loc_180038BD5
0x180038bc5  mov     rcx, [rdi]
0x180038bc8  mov     rax, [rcx+10h]
0x180038bcc  mov     rcx, rdi
0x180038bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038bd4  nop
0x180038bd5  mov     eax, ebx
0x180038bd7  add     rsp, 50h
0x180038bdb  pop     r14
0x180038bdd  pop     rdi
0x180038bde  pop     rsi
0x180038bdf  pop     rbx
0x180038be0  pop     rbp
0x180038be1  retn
```
