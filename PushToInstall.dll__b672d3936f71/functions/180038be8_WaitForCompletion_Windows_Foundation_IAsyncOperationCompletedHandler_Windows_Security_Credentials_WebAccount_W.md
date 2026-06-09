# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,tagCOWAIT_FLAGS,void *,ulong)

- ea: `0x180038be8`
- end: `0x180038e8d`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z`
- size: `677`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), DWORD, __int64, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800381c4`

## callees

- `0x18000d7a0`
- `0x18002de7c`
- `0x1800317f8`
- `0x180038be8`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180038cbb`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180038cbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038cca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038cca`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180038d6f`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180038d6f`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(
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
  *(_QWORD *)v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>'};
  *((_QWORD *)v5 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v5 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v5 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
    v10 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, pHandles, &dwindex);
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
0x180038be8  mov     [rsp-28h+arg_18], r9d
0x180038bed  mov     [rsp-28h+arg_10], r8
0x180038bf2  mov     [rsp-28h+dwindex], edx
0x180038bf6  push    rbp
0x180038bf7  push    rbx
0x180038bf8  push    rsi
0x180038bf9  push    rdi
0x180038bfa  push    r14
0x180038bfc  mov     rbp, rsp
0x180038bff  sub     rsp, 50h
0x180038c03  mov     rdi, rcx
0x180038c06  mov     [rbp+var_20], rcx
0x180038c0a  xor     r14d, r14d
0x180038c0d  test    rcx, rcx
0x180038c10  jz      short loc_180038C1F
0x180038c12  mov     rax, [rcx]
0x180038c15  mov     rax, [rax+8]
0x180038c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c1e  nop
0x180038c1f  mov     [rbp+arg_0], r14
0x180038c23  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180038c2a  mov     ecx, 40h ; '@'; unsigned __int64
0x180038c2f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180038c34  mov     rbx, rax
0x180038c37  test    rax, rax
0x180038c3a  jnz     short loc_180038C48
0x180038c3c  mov     [rbp+arg_18], 8007000Eh
0x180038c43  jmp     loc_180038E4E
0x180038c48  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>::`vftable'
0x180038c4f  mov     [rbx], rax
0x180038c52  lea     rsi, [rbx+8]
0x180038c56  mov     rcx, rsi
0x180038c59  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x180038c5e  mov     dword ptr [rbx+2Ch], 1
0x180038c65  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>'}
0x180038c6c  mov     [rbx], rax
0x180038c6f  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180038c76  mov     [rsi], rax
0x180038c79  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180038c80  test    rcx, rcx
0x180038c83  jz      short loc_180038C92
0x180038c85  mov     rax, [rcx]
0x180038c88  mov     rax, [rax+8]
0x180038c8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c91  nop
0x180038c92  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z@6B?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>'}
0x180038c99  mov     [rbx], rax
0x180038c9c  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180038ca3  mov     [rsi], rax
0x180038ca6  mov     [rbx+30h], r14d
0x180038caa  mov     [rbx+38h], r14
0x180038cae  mov     r9d, 1F0003h; dwDesiredAccess
0x180038cb4  xor     r8d, r8d; dwFlags
0x180038cb7  xor     edx, edx; lpName
0x180038cb9  xor     ecx, ecx; lpEventAttributes
0x180038cbb  call    cs:__imp_CreateEventExW
0x180038cc1  mov     [rbx+38h], rax
0x180038cc5  test    rax, rax
0x180038cc8  jnz     short loc_180038CFB
0x180038cca  call    cs:__imp_GetLastError
0x180038cd0  mov     esi, eax
0x180038cd2  test    eax, eax
0x180038cd4  jle     short loc_180038CDF
0x180038cd6  movzx   esi, ax
0x180038cd9  or      esi, 80070000h
0x180038cdf  mov     rax, [rbx]
0x180038ce2  test    esi, esi
0x180038ce4  jns     short loc_180038CFE
0x180038ce6  mov     rcx, rbx
0x180038ce9  mov     rax, [rax+10h]
0x180038ced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038cf2  nop
0x180038cf3  mov     [rbp+arg_18], esi
0x180038cf6  jmp     loc_180038E4E
0x180038cfb  mov     rax, [rbx]
0x180038cfe  mov     rcx, rbx
0x180038d01  mov     rax, [rax+8]
0x180038d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d0a  nop
0x180038d0b  mov     [rbp+arg_0], rbx
0x180038d0f  mov     rax, [rbx]
0x180038d12  mov     rcx, rbx
0x180038d15  mov     rax, [rax+10h]
0x180038d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d1e  nop
0x180038d1f  mov     [rbp+arg_18], r14d
0x180038d23  mov     rax, [rdi]
0x180038d26  mov     rdx, [rbp+arg_0]
0x180038d2a  mov     rcx, rdi
0x180038d2d  mov     rax, [rax+30h]
0x180038d31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d36  mov     [rbp+arg_18], eax
0x180038d39  test    eax, eax
0x180038d3b  js      loc_180038E4E
0x180038d41  mov     rax, [rbp+arg_0]
0x180038d45  mov     rcx, [rax+38h]
0x180038d49  mov     [rbp+pHandles], rcx
0x180038d4d  mov     [rbp+var_10], r14
0x180038d51  mov     [rbp+dwindex], r14d
0x180038d55  lea     rax, [rbp+dwindex]
0x180038d59  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x180038d5e  lea     r9, [rbp+pHandles]; pHandles
0x180038d62  mov     r8d, 1; cHandles
0x180038d68  or      edx, 0FFFFFFFFh; dwTimeout
0x180038d6b  lea     ecx, [r8+7]; dwFlags
0x180038d6f  call    cs:__imp_CoWaitForMultipleHandles
0x180038d75  mov     ecx, eax
0x180038d77  mov     [rbp+arg_18], eax
0x180038d7a  test    eax, eax
0x180038d7c  js      short loc_180038D8D
0x180038d7e  cmp     [rbp+dwindex], r14d
0x180038d82  jz      short loc_180038D8D
0x180038d84  mov     [rbp+arg_18], 800704C7h
0x180038d8b  jmp     short loc_180038D9F
0x180038d8d  mov     al, r14b
0x180038d90  cmp     ecx, 80010115h
0x180038d96  jnz     short loc_180038DA1
0x180038d98  mov     [rbp+arg_18], 800705B4h
0x180038d9f  mov     al, 1
0x180038da1  mov     [rbp+arg_10], r14
0x180038da5  test    al, al
0x180038da7  jz      short loc_180038DE1
0x180038da9  mov     rax, [rdi]
0x180038dac  mov     rbx, [rax]
0x180038daf  lea     rcx, [rbp+arg_10]
0x180038db3  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x180038db8  mov     r8, rax
0x180038dbb  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180038dc2  mov     rcx, rdi
0x180038dc5  mov     rax, rbx
0x180038dc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038dcd  test    eax, eax
0x180038dcf  js      short loc_180038DE1
0x180038dd1  mov     rcx, [rbp+arg_10]
0x180038dd5  mov     rax, [rcx]
0x180038dd8  mov     rax, [rax+48h]
0x180038ddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038de1  cmp     [rbp+arg_18], r14d
0x180038de5  jl      short loc_180038E34
0x180038de7  mov     rax, [rbp+arg_0]
0x180038deb  cmp     dword ptr [rax+30h], 1
0x180038def  jz      short loc_180038E34
0x180038df1  cmp     [rbp+arg_10], r14
0x180038df5  jnz     short loc_180038E1F
0x180038df7  mov     rax, [rdi]
0x180038dfa  mov     rbx, [rax]
0x180038dfd  lea     rcx, [rbp+arg_10]
0x180038e01  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x180038e06  mov     r8, rax
0x180038e09  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180038e10  mov     rcx, rdi
0x180038e13  mov     rax, rbx
0x180038e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e1b  test    eax, eax
0x180038e1d  js      short loc_180038E34
0x180038e1f  mov     rcx, [rbp+arg_10]
0x180038e23  mov     rax, [rcx]
0x180038e26  lea     rdx, [rbp+arg_18]
0x180038e2a  mov     rax, [rax+40h]
0x180038e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e33  nop
0x180038e34  mov     rcx, [rbp+arg_10]
0x180038e38  test    rcx, rcx
0x180038e3b  jz      short loc_180038E4E
0x180038e3d  mov     [rbp+arg_10], r14
0x180038e41  mov     rax, [rcx]
0x180038e44  mov     rax, [rax+10h]
0x180038e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e4d  nop
0x180038e4e  mov     ebx, [rbp+arg_18]
0x180038e51  mov     rcx, [rbp+arg_0]
0x180038e55  test    rcx, rcx
0x180038e58  jz      short loc_180038E6B
0x180038e5a  mov     [rbp+arg_0], r14
0x180038e5e  mov     rax, [rcx]
0x180038e61  mov     rax, [rax+10h]
0x180038e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e6a  nop
0x180038e6b  test    rdi, rdi
0x180038e6e  jz      short loc_180038E80
0x180038e70  mov     rcx, [rdi]
0x180038e73  mov     rax, [rcx+10h]
0x180038e77  mov     rcx, rdi
0x180038e7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e7f  nop
0x180038e80  mov     eax, ebx
0x180038e82  add     rsp, 50h
0x180038e86  pop     r14
0x180038e88  pop     rdi
0x180038e89  pop     rsi
0x180038e8a  pop     rbx
0x180038e8b  pop     rbp
0x180038e8c  retn
```
