# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *> *,tagCOWAIT_FLAGS,void *,ulong)

- ea: `0x180038690`
- end: `0x180038936`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z`
- size: `678`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), DWORD, __int64, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003f2fc`

## callees

- `0x18000d7a0`
- `0x18002de7c`
- `0x1800317f8`
- `0x180038690`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180038763`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180038763`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038772`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038772`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180038818`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180038818`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>>(
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
  *(_QWORD *)v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>'};
  *((_QWORD *)v5 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v5 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v5 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
0x180038690  mov     [rsp-28h+arg_18], r9d
0x180038695  mov     [rsp-28h+arg_10], r8
0x18003869a  mov     [rsp-28h+dwindex], edx
0x18003869e  push    rbp
0x18003869f  push    rbx
0x1800386a0  push    rsi
0x1800386a1  push    rdi
0x1800386a2  push    r14
0x1800386a4  mov     rbp, rsp
0x1800386a7  sub     rsp, 50h
0x1800386ab  mov     rdi, rcx
0x1800386ae  mov     [rbp+var_20], rcx
0x1800386b2  xor     r14d, r14d
0x1800386b5  test    rcx, rcx
0x1800386b8  jz      short loc_1800386C7
0x1800386ba  mov     rax, [rcx]
0x1800386bd  mov     rax, [rax+8]
0x1800386c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800386c6  nop
0x1800386c7  mov     [rbp+arg_0], r14
0x1800386cb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800386d2  mov     ecx, 40h ; '@'; unsigned __int64
0x1800386d7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800386dc  mov     rbx, rax
0x1800386df  test    rax, rax
0x1800386e2  jnz     short loc_1800386F0
0x1800386e4  mov     [rbp+arg_18], 8007000Eh
0x1800386eb  jmp     loc_1800388F7
0x1800386f0  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>::`vftable'
0x1800386f7  mov     [rbx], rax
0x1800386fa  lea     rsi, [rbx+8]
0x1800386fe  mov     rcx, rsi
0x180038701  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x180038706  mov     dword ptr [rbx+2Ch], 1
0x18003870d  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>'}
0x180038714  mov     [rbx], rax
0x180038717  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18003871e  mov     [rsi], rax
0x180038721  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180038728  test    rcx, rcx
0x18003872b  jz      short loc_18003873A
0x18003872d  mov     rax, [rcx]
0x180038730  mov     rax, [rax+8]
0x180038734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038739  nop
0x18003873a  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *> *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>'}
0x180038741  mov     [rbx], rax
0x180038744  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18003874b  mov     [rsi], rax
0x18003874e  mov     [rbx+30h], r14d
0x180038752  mov     [rbx+38h], r14
0x180038756  mov     r9d, 1F0003h; dwDesiredAccess
0x18003875c  xor     r8d, r8d; dwFlags
0x18003875f  xor     edx, edx; lpName
0x180038761  xor     ecx, ecx; lpEventAttributes
0x180038763  call    cs:__imp_CreateEventExW
0x180038769  mov     [rbx+38h], rax
0x18003876d  test    rax, rax
0x180038770  jnz     short loc_1800387A3
0x180038772  call    cs:__imp_GetLastError
0x180038778  mov     esi, eax
0x18003877a  test    eax, eax
0x18003877c  jle     short loc_180038787
0x18003877e  movzx   esi, ax
0x180038781  or      esi, 80070000h
0x180038787  mov     rax, [rbx]
0x18003878a  test    esi, esi
0x18003878c  jns     short loc_1800387A6
0x18003878e  mov     rcx, rbx
0x180038791  mov     rax, [rax+10h]
0x180038795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003879a  nop
0x18003879b  mov     [rbp+arg_18], esi
0x18003879e  jmp     loc_1800388F7
0x1800387a3  mov     rax, [rbx]
0x1800387a6  mov     rcx, rbx
0x1800387a9  mov     rax, [rax+8]
0x1800387ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800387b2  nop
0x1800387b3  mov     [rbp+arg_0], rbx
0x1800387b7  mov     rax, [rbx]
0x1800387ba  mov     rcx, rbx
0x1800387bd  mov     rax, [rax+10h]
0x1800387c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800387c6  nop
0x1800387c7  mov     [rbp+arg_18], r14d
0x1800387cb  mov     rax, [rdi]
0x1800387ce  mov     rdx, [rbp+arg_0]
0x1800387d2  mov     rcx, rdi
0x1800387d5  mov     rax, [rax+30h]
0x1800387d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800387de  mov     [rbp+arg_18], eax
0x1800387e1  test    eax, eax
0x1800387e3  js      loc_1800388F7
0x1800387e9  mov     rax, [rbp+arg_0]
0x1800387ed  mov     rcx, [rax+38h]
0x1800387f1  mov     [rbp+pHandles], rcx
0x1800387f5  mov     [rbp+var_10], r14
0x1800387f9  mov     [rbp+dwindex], r14d
0x1800387fd  lea     rax, [rbp+dwindex]
0x180038801  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x180038806  lea     r9, [rbp+pHandles]; pHandles
0x18003880a  mov     edx, 7530h; dwTimeout
0x18003880f  mov     ecx, 8; dwFlags
0x180038814  lea     r8d, [rcx-7]; cHandles
0x180038818  call    cs:__imp_CoWaitForMultipleHandles
0x18003881e  mov     ecx, eax
0x180038820  mov     [rbp+arg_18], eax
0x180038823  test    eax, eax
0x180038825  js      short loc_180038836
0x180038827  cmp     [rbp+dwindex], r14d
0x18003882b  jz      short loc_180038836
0x18003882d  mov     [rbp+arg_18], 800704C7h
0x180038834  jmp     short loc_180038848
0x180038836  mov     al, r14b
0x180038839  cmp     ecx, 80010115h
0x18003883f  jnz     short loc_18003884A
0x180038841  mov     [rbp+arg_18], 800705B4h
0x180038848  mov     al, 1
0x18003884a  mov     [rbp+arg_10], r14
0x18003884e  test    al, al
0x180038850  jz      short loc_18003888A
0x180038852  mov     rax, [rdi]
0x180038855  mov     rbx, [rax]
0x180038858  lea     rcx, [rbp+arg_10]
0x18003885c  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x180038861  mov     r8, rax
0x180038864  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18003886b  mov     rcx, rdi
0x18003886e  mov     rax, rbx
0x180038871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038876  test    eax, eax
0x180038878  js      short loc_18003888A
0x18003887a  mov     rcx, [rbp+arg_10]
0x18003887e  mov     rax, [rcx]
0x180038881  mov     rax, [rax+48h]
0x180038885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003888a  cmp     [rbp+arg_18], r14d
0x18003888e  jl      short loc_1800388DD
0x180038890  mov     rax, [rbp+arg_0]
0x180038894  cmp     dword ptr [rax+30h], 1
0x180038898  jz      short loc_1800388DD
0x18003889a  cmp     [rbp+arg_10], r14
0x18003889e  jnz     short loc_1800388C8
0x1800388a0  mov     rax, [rdi]
0x1800388a3  mov     rbx, [rax]
0x1800388a6  lea     rcx, [rbp+arg_10]
0x1800388aa  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x1800388af  mov     r8, rax
0x1800388b2  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x1800388b9  mov     rcx, rdi
0x1800388bc  mov     rax, rbx
0x1800388bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800388c4  test    eax, eax
0x1800388c6  js      short loc_1800388DD
0x1800388c8  mov     rcx, [rbp+arg_10]
0x1800388cc  mov     rax, [rcx]
0x1800388cf  lea     rdx, [rbp+arg_18]
0x1800388d3  mov     rax, [rax+40h]
0x1800388d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800388dc  nop
0x1800388dd  mov     rcx, [rbp+arg_10]
0x1800388e1  test    rcx, rcx
0x1800388e4  jz      short loc_1800388F7
0x1800388e6  mov     [rbp+arg_10], r14
0x1800388ea  mov     rax, [rcx]
0x1800388ed  mov     rax, [rax+10h]
0x1800388f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800388f6  nop
0x1800388f7  mov     ebx, [rbp+arg_18]
0x1800388fa  mov     rcx, [rbp+arg_0]
0x1800388fe  test    rcx, rcx
0x180038901  jz      short loc_180038914
0x180038903  mov     [rbp+arg_0], r14
0x180038907  mov     rax, [rcx]
0x18003890a  mov     rax, [rax+10h]
0x18003890e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038913  nop
0x180038914  test    rdi, rdi
0x180038917  jz      short loc_180038929
0x180038919  mov     rcx, [rdi]
0x18003891c  mov     rax, [rcx+10h]
0x180038920  mov     rcx, rdi
0x180038923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038928  nop
0x180038929  mov     eax, ebx
0x18003892b  add     rsp, 50h
0x18003892f  pop     r14
0x180038931  pop     rdi
0x180038932  pop     rsi
0x180038933  pop     rbx
0x180038934  pop     rbp
0x180038935  retn
```
