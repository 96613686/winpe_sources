# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x180050cfc`
- end: `0x180050f89`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800525e4`

## callees

- `0x1800065c8`
- `0x180032194`
- `0x180032410`
- `0x180050cfc`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050dd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050dd9`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180050dca`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180050dca`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180050e81`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180050e81`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64),
        HRESULT a2,
        __int64 a3)
{
  _DWORD *v4; // rbx
  HANDLE Event; // rax
  signed int LastError; // eax
  signed int v7; // esi
  __int64 v8; // rax
  char v9; // bl
  int (__fastcall *v10)(_QWORD, GUID *, __int64); // rbx
  __int64 v11; // rax
  int (__fastcall *v12)(_QWORD, GUID *, __int64); // rbx
  __int64 v13; // rax
  __int64 v14; // rcx
  unsigned int v15; // ebx
  HANDLE *v16; // rcx
  HANDLE pHandles[3]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v19; // [rsp+80h] [rbp+30h] BYREF
  HRESULT v20; // [rsp+88h] [rbp+38h] BYREF
  __int64 dwindex; // [rsp+90h] [rbp+40h] BYREF
  HANDLE *v22; // [rsp+98h] [rbp+48h]

  dwindex = a3;
  v20 = a2;
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64)))(*a1)[1])(a1);
  v22 = 0;
  v4 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
  {
    v20 = -2147024882;
    goto LABEL_27;
  }
  *(_QWORD *)v4 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>::`vftable';
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v4 + 2));
  v4[11] = 1;
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v4 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>'::`2'::FTMEventDelegate::`vftable';
  v4[12] = 0;
  *((_QWORD *)v4 + 7) = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  *((_QWORD *)v4 + 7) = Event;
  if ( Event )
  {
    v8 = *(_QWORD *)v4;
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    v8 = *(_QWORD *)v4;
    if ( v7 < 0 )
    {
      (*(void (__fastcall **)(_DWORD *))(v8 + 16))(v4);
      v20 = v7;
      goto LABEL_27;
    }
  }
  (*(void (__fastcall **)(_DWORD *))(v8 + 8))(v4);
  v22 = (HANDLE *)v4;
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v4 + 16LL))(v4);
  v20 = 0;
  v20 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64), HANDLE *))(*a1)[6])(a1, v22);
  if ( v20 >= 0 )
  {
    pHandles[0] = v22[7];
    pHandles[1] = 0;
    v9 = 0;
    LODWORD(dwindex) = 0;
    v20 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, pHandles, (LPDWORD)&dwindex);
    if ( v20 >= 0 && (_DWORD)dwindex )
    {
      v20 = -2147023673;
      v9 = 1;
    }
    v19 = 0;
    if ( v9 )
    {
      v10 = **a1;
      v11 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(&v19);
      if ( v10(a1, &GUID_00000036_0000_0000_c000_000000000046, v11) >= 0 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 72LL))(v19);
    }
    if ( v20 >= 0 && *((_DWORD *)v22 + 12) != 1 )
    {
      if ( v19
        || (v12 = **a1,
            v13 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(&v19),
            v12(a1, &GUID_00000036_0000_0000_c000_000000000046, v13) >= 0) )
      {
        (*(void (__fastcall **)(__int64, HRESULT *))(*(_QWORD *)v19 + 64LL))(v19, &v20);
      }
    }
    v14 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
  }
LABEL_27:
  v15 = v20;
  v16 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*((void (__fastcall **)(HANDLE *))*v16 + 2))(v16);
  }
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64)))(*a1)[2])(a1);
  return v15;
}

```

## disassembly

```asm
0x180050cfc  mov     [rsp-28h+dwindex], r8
0x180050d01  mov     [rsp-28h+arg_8], edx
0x180050d05  push    rbp
0x180050d06  push    rbx
0x180050d07  push    rsi
0x180050d08  push    rdi
0x180050d09  push    r14
0x180050d0b  mov     rbp, rsp
0x180050d0e  sub     rsp, 50h
0x180050d12  mov     rdi, rcx
0x180050d15  mov     [rbp+var_20], rcx
0x180050d19  xor     r14d, r14d
0x180050d1c  test    rcx, rcx
0x180050d1f  jz      short loc_180050D2E
0x180050d21  mov     rax, [rcx]
0x180050d24  mov     rax, [rax+8]
0x180050d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050d2d  nop
0x180050d2e  mov     [rbp+arg_18], r14
0x180050d32  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180050d39  mov     ecx, 40h ; '@'; unsigned __int64
0x180050d3e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180050d43  mov     rbx, rax
0x180050d46  test    rax, rax
0x180050d49  jnz     short loc_180050D57
0x180050d4b  mov     [rbp+arg_8], 8007000Eh
0x180050d52  jmp     loc_180050F4A
0x180050d57  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>::`vftable'
0x180050d5e  mov     [rbx], rax
0x180050d61  lea     rsi, [rbx+8]
0x180050d65  mov     rcx, rsi; this
0x180050d68  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180050d6d  mov     dword ptr [rbx+2Ch], 1
0x180050d74  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>'}
0x180050d7b  mov     [rbx], rax
0x180050d7e  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180050d85  mov     [rsi], rax
0x180050d88  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180050d8f  test    rcx, rcx
0x180050d92  jz      short loc_180050DA1
0x180050d94  mov     rax, [rcx]
0x180050d97  mov     rax, [rax+8]
0x180050d9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050da0  nop
0x180050da1  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>'}
0x180050da8  mov     [rbx], rax
0x180050dab  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180050db2  mov     [rsi], rax
0x180050db5  mov     [rbx+30h], r14d
0x180050db9  mov     [rbx+38h], r14
0x180050dbd  mov     r9d, 1F0003h; dwDesiredAccess
0x180050dc3  xor     r8d, r8d; dwFlags
0x180050dc6  xor     edx, edx; lpName
0x180050dc8  xor     ecx, ecx; lpEventAttributes
0x180050dca  call    cs:__imp_CreateEventExW
0x180050dd0  mov     [rbx+38h], rax
0x180050dd4  test    rax, rax
0x180050dd7  jnz     short loc_180050E0A
0x180050dd9  call    cs:__imp_GetLastError
0x180050ddf  mov     esi, eax
0x180050de1  test    eax, eax
0x180050de3  jle     short loc_180050DEE
0x180050de5  movzx   esi, ax
0x180050de8  or      esi, 80070000h
0x180050dee  mov     rax, [rbx]
0x180050df1  test    esi, esi
0x180050df3  jns     short loc_180050E0D
0x180050df5  mov     rcx, rbx
0x180050df8  mov     rax, [rax+10h]
0x180050dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e01  nop
0x180050e02  mov     [rbp+arg_8], esi
0x180050e05  jmp     loc_180050F4A
0x180050e0a  mov     rax, [rbx]
0x180050e0d  mov     rcx, rbx
0x180050e10  mov     rax, [rax+8]
0x180050e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e19  nop
0x180050e1a  mov     [rbp+arg_18], rbx
0x180050e1e  mov     rax, [rbx]
0x180050e21  mov     rcx, rbx
0x180050e24  mov     rax, [rax+10h]
0x180050e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e2d  nop
0x180050e2e  mov     [rbp+arg_8], r14d
0x180050e32  mov     rax, [rdi]
0x180050e35  mov     rdx, [rbp+arg_18]
0x180050e39  mov     rcx, rdi
0x180050e3c  mov     rax, [rax+30h]
0x180050e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e45  mov     [rbp+arg_8], eax
0x180050e48  test    eax, eax
0x180050e4a  js      loc_180050F4A
0x180050e50  mov     rax, [rbp+arg_18]
0x180050e54  mov     rcx, [rax+38h]
0x180050e58  mov     [rbp+pHandles], rcx
0x180050e5c  mov     [rbp+var_10], r14
0x180050e60  mov     bl, r14b
0x180050e63  mov     dword ptr [rbp+dwindex], r14d
0x180050e67  lea     rax, [rbp+dwindex]
0x180050e6b  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x180050e70  lea     r9, [rbp+pHandles]; pHandles
0x180050e74  mov     r8d, 1; cHandles
0x180050e7a  or      edx, 0FFFFFFFFh; dwTimeout
0x180050e7d  lea     ecx, [r8+7]; dwFlags
0x180050e81  call    cs:__imp_CoWaitForMultipleHandles
0x180050e87  mov     [rbp+arg_8], eax
0x180050e8a  test    eax, eax
0x180050e8c  js      short loc_180050E9D
0x180050e8e  cmp     dword ptr [rbp+dwindex], r14d
0x180050e92  jz      short loc_180050E9D
0x180050e94  mov     [rbp+arg_8], 800704C7h
0x180050e9b  mov     bl, 1
0x180050e9d  mov     [rbp+arg_0], r14
0x180050ea1  test    bl, bl
0x180050ea3  jz      short loc_180050EDD
0x180050ea5  mov     rax, [rdi]
0x180050ea8  mov     rbx, [rax]
0x180050eab  lea     rcx, [rbp+arg_0]
0x180050eaf  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x180050eb4  mov     r8, rax
0x180050eb7  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180050ebe  mov     rcx, rdi
0x180050ec1  mov     rax, rbx
0x180050ec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ec9  test    eax, eax
0x180050ecb  js      short loc_180050EDD
0x180050ecd  mov     rcx, [rbp+arg_0]
0x180050ed1  mov     rax, [rcx]
0x180050ed4  mov     rax, [rax+48h]
0x180050ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050edd  cmp     [rbp+arg_8], r14d
0x180050ee1  jl      short loc_180050F30
0x180050ee3  mov     rax, [rbp+arg_18]
0x180050ee7  cmp     dword ptr [rax+30h], 1
0x180050eeb  jz      short loc_180050F30
0x180050eed  cmp     [rbp+arg_0], r14
0x180050ef1  jnz     short loc_180050F1B
0x180050ef3  mov     rax, [rdi]
0x180050ef6  mov     rbx, [rax]
0x180050ef9  lea     rcx, [rbp+arg_0]
0x180050efd  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x180050f02  mov     r8, rax
0x180050f05  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180050f0c  mov     rcx, rdi
0x180050f0f  mov     rax, rbx
0x180050f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050f17  test    eax, eax
0x180050f19  js      short loc_180050F30
0x180050f1b  mov     rcx, [rbp+arg_0]
0x180050f1f  mov     rax, [rcx]
0x180050f22  lea     rdx, [rbp+arg_8]
0x180050f26  mov     rax, [rax+40h]
0x180050f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050f2f  nop
0x180050f30  mov     rcx, [rbp+arg_0]
0x180050f34  test    rcx, rcx
0x180050f37  jz      short loc_180050F4A
0x180050f39  mov     [rbp+arg_0], r14
0x180050f3d  mov     rax, [rcx]
0x180050f40  mov     rax, [rax+10h]
0x180050f44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050f49  nop
0x180050f4a  mov     ebx, [rbp+arg_8]
0x180050f4d  mov     rcx, [rbp+arg_18]
0x180050f51  test    rcx, rcx
0x180050f54  jz      short loc_180050F67
0x180050f56  mov     [rbp+arg_18], r14
0x180050f5a  mov     rax, [rcx]
0x180050f5d  mov     rax, [rax+10h]
0x180050f61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050f66  nop
0x180050f67  test    rdi, rdi
0x180050f6a  jz      short loc_180050F7C
0x180050f6c  mov     rcx, [rdi]
0x180050f6f  mov     rax, [rcx+10h]
0x180050f73  mov     rcx, rdi
0x180050f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050f7b  nop
0x180050f7c  mov     eax, ebx
0x180050f7e  add     rsp, 50h
0x180050f82  pop     r14
0x180050f84  pop     rdi
0x180050f85  pop     rsi
0x180050f86  pop     rbx
0x180050f87  pop     rbp
0x180050f88  retn
```
