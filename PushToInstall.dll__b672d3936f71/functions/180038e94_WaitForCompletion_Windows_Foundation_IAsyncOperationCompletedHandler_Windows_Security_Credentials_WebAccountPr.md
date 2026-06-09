# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *,ulong)

- ea: `0x180038e94`
- end: `0x18003913a`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z`
- size: `678`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), DWORD, __int64, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180038220`

## callees

- `0x18000d7a0`
- `0x18002de7c`
- `0x1800317f8`
- `0x180038e94`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180038f67`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180038f67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038f76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038f76`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18003901c`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18003901c`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(
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
  *(_QWORD *)v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>'};
  *((_QWORD *)v5 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v5 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v5 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
0x180038e94  mov     [rsp-28h+arg_18], r9d
0x180038e99  mov     [rsp-28h+arg_10], r8
0x180038e9e  mov     [rsp-28h+dwindex], edx
0x180038ea2  push    rbp
0x180038ea3  push    rbx
0x180038ea4  push    rsi
0x180038ea5  push    rdi
0x180038ea6  push    r14
0x180038ea8  mov     rbp, rsp
0x180038eab  sub     rsp, 50h
0x180038eaf  mov     rdi, rcx
0x180038eb2  mov     [rbp+var_20], rcx
0x180038eb6  xor     r14d, r14d
0x180038eb9  test    rcx, rcx
0x180038ebc  jz      short loc_180038ECB
0x180038ebe  mov     rax, [rcx]
0x180038ec1  mov     rax, [rax+8]
0x180038ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038eca  nop
0x180038ecb  mov     [rbp+arg_0], r14
0x180038ecf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180038ed6  mov     ecx, 40h ; '@'; unsigned __int64
0x180038edb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180038ee0  mov     rbx, rax
0x180038ee3  test    rax, rax
0x180038ee6  jnz     short loc_180038EF4
0x180038ee8  mov     [rbp+arg_18], 8007000Eh
0x180038eef  jmp     loc_1800390FB
0x180038ef4  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>::`vftable'
0x180038efb  mov     [rbx], rax
0x180038efe  lea     rsi, [rbx+8]
0x180038f02  mov     rcx, rsi
0x180038f05  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x180038f0a  mov     dword ptr [rbx+2Ch], 1
0x180038f11  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>'}
0x180038f18  mov     [rbx], rax
0x180038f1b  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180038f22  mov     [rsi], rax
0x180038f25  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180038f2c  test    rcx, rcx
0x180038f2f  jz      short loc_180038F3E
0x180038f31  mov     rax, [rcx]
0x180038f34  mov     rax, [rax+8]
0x180038f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038f3d  nop
0x180038f3e  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z@6B?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>'}
0x180038f45  mov     [rbx], rax
0x180038f48  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180038f4f  mov     [rsi], rax
0x180038f52  mov     [rbx+30h], r14d
0x180038f56  mov     [rbx+38h], r14
0x180038f5a  mov     r9d, 1F0003h; dwDesiredAccess
0x180038f60  xor     r8d, r8d; dwFlags
0x180038f63  xor     edx, edx; lpName
0x180038f65  xor     ecx, ecx; lpEventAttributes
0x180038f67  call    cs:__imp_CreateEventExW
0x180038f6d  mov     [rbx+38h], rax
0x180038f71  test    rax, rax
0x180038f74  jnz     short loc_180038FA7
0x180038f76  call    cs:__imp_GetLastError
0x180038f7c  mov     esi, eax
0x180038f7e  test    eax, eax
0x180038f80  jle     short loc_180038F8B
0x180038f82  movzx   esi, ax
0x180038f85  or      esi, 80070000h
0x180038f8b  mov     rax, [rbx]
0x180038f8e  test    esi, esi
0x180038f90  jns     short loc_180038FAA
0x180038f92  mov     rcx, rbx
0x180038f95  mov     rax, [rax+10h]
0x180038f99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038f9e  nop
0x180038f9f  mov     [rbp+arg_18], esi
0x180038fa2  jmp     loc_1800390FB
0x180038fa7  mov     rax, [rbx]
0x180038faa  mov     rcx, rbx
0x180038fad  mov     rax, [rax+8]
0x180038fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038fb6  nop
0x180038fb7  mov     [rbp+arg_0], rbx
0x180038fbb  mov     rax, [rbx]
0x180038fbe  mov     rcx, rbx
0x180038fc1  mov     rax, [rax+10h]
0x180038fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038fca  nop
0x180038fcb  mov     [rbp+arg_18], r14d
0x180038fcf  mov     rax, [rdi]
0x180038fd2  mov     rdx, [rbp+arg_0]
0x180038fd6  mov     rcx, rdi
0x180038fd9  mov     rax, [rax+30h]
0x180038fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038fe2  mov     [rbp+arg_18], eax
0x180038fe5  test    eax, eax
0x180038fe7  js      loc_1800390FB
0x180038fed  mov     rax, [rbp+arg_0]
0x180038ff1  mov     rcx, [rax+38h]
0x180038ff5  mov     [rbp+pHandles], rcx
0x180038ff9  mov     [rbp+var_10], r14
0x180038ffd  mov     [rbp+dwindex], r14d
0x180039001  lea     rax, [rbp+dwindex]
0x180039005  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x18003900a  lea     r9, [rbp+pHandles]; pHandles
0x18003900e  mov     edx, 7530h; dwTimeout
0x180039013  mov     ecx, 8; dwFlags
0x180039018  lea     r8d, [rcx-7]; cHandles
0x18003901c  call    cs:__imp_CoWaitForMultipleHandles
0x180039022  mov     ecx, eax
0x180039024  mov     [rbp+arg_18], eax
0x180039027  test    eax, eax
0x180039029  js      short loc_18003903A
0x18003902b  cmp     [rbp+dwindex], r14d
0x18003902f  jz      short loc_18003903A
0x180039031  mov     [rbp+arg_18], 800704C7h
0x180039038  jmp     short loc_18003904C
0x18003903a  mov     al, r14b
0x18003903d  cmp     ecx, 80010115h
0x180039043  jnz     short loc_18003904E
0x180039045  mov     [rbp+arg_18], 800705B4h
0x18003904c  mov     al, 1
0x18003904e  mov     [rbp+arg_10], r14
0x180039052  test    al, al
0x180039054  jz      short loc_18003908E
0x180039056  mov     rax, [rdi]
0x180039059  mov     rbx, [rax]
0x18003905c  lea     rcx, [rbp+arg_10]
0x180039060  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x180039065  mov     r8, rax
0x180039068  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18003906f  mov     rcx, rdi
0x180039072  mov     rax, rbx
0x180039075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003907a  test    eax, eax
0x18003907c  js      short loc_18003908E
0x18003907e  mov     rcx, [rbp+arg_10]
0x180039082  mov     rax, [rcx]
0x180039085  mov     rax, [rax+48h]
0x180039089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003908e  cmp     [rbp+arg_18], r14d
0x180039092  jl      short loc_1800390E1
0x180039094  mov     rax, [rbp+arg_0]
0x180039098  cmp     dword ptr [rax+30h], 1
0x18003909c  jz      short loc_1800390E1
0x18003909e  cmp     [rbp+arg_10], r14
0x1800390a2  jnz     short loc_1800390CC
0x1800390a4  mov     rax, [rdi]
0x1800390a7  mov     rbx, [rax]
0x1800390aa  lea     rcx, [rbp+arg_10]
0x1800390ae  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x1800390b3  mov     r8, rax
0x1800390b6  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x1800390bd  mov     rcx, rdi
0x1800390c0  mov     rax, rbx
0x1800390c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800390c8  test    eax, eax
0x1800390ca  js      short loc_1800390E1
0x1800390cc  mov     rcx, [rbp+arg_10]
0x1800390d0  mov     rax, [rcx]
0x1800390d3  lea     rdx, [rbp+arg_18]
0x1800390d7  mov     rax, [rax+40h]
0x1800390db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800390e0  nop
0x1800390e1  mov     rcx, [rbp+arg_10]
0x1800390e5  test    rcx, rcx
0x1800390e8  jz      short loc_1800390FB
0x1800390ea  mov     [rbp+arg_10], r14
0x1800390ee  mov     rax, [rcx]
0x1800390f1  mov     rax, [rax+10h]
0x1800390f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800390fa  nop
0x1800390fb  mov     ebx, [rbp+arg_18]
0x1800390fe  mov     rcx, [rbp+arg_0]
0x180039102  test    rcx, rcx
0x180039105  jz      short loc_180039118
0x180039107  mov     [rbp+arg_0], r14
0x18003910b  mov     rax, [rcx]
0x18003910e  mov     rax, [rax+10h]
0x180039112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039117  nop
0x180039118  test    rdi, rdi
0x18003911b  jz      short loc_18003912D
0x18003911d  mov     rcx, [rdi]
0x180039120  mov     rax, [rcx+10h]
0x180039124  mov     rcx, rdi
0x180039127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003912c  nop
0x18003912d  mov     eax, ebx
0x18003912f  add     rsp, 50h
0x180039133  pop     r14
0x180039135  pop     rdi
0x180039136  pop     rsi
0x180039137  pop     rbx
0x180039138  pop     rbp
0x180039139  retn
```
