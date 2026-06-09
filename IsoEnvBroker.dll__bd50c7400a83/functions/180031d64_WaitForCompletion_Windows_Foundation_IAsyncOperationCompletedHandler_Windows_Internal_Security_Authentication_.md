# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x180031d64`
- end: `0x180031fdb`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `631`
- prototype: `__int64 __fastcall(__int64, HRESULT, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800337d0`

## callees

- `0x180002a30`
- `0x18001fc7c`
- `0x180031d64`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180031e32`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180031e32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031e41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031e41`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180031ee9`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180031ee9`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(
        __int64 a1,
        HRESULT a2,
        __int64 a3)
{
  _DWORD *v4; // rbx
  HANDLE Event; // rax
  signed int LastError; // eax
  signed int v7; // esi
  __int64 v8; // rax
  char v9; // bl
  __int64 v10; // rcx
  unsigned int v11; // ebx
  HANDLE *v12; // rcx
  HANDLE pHandles[3]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v15; // [rsp+80h] [rbp+30h] BYREF
  HRESULT v16; // [rsp+88h] [rbp+38h] BYREF
  __int64 dwindex; // [rsp+90h] [rbp+40h] BYREF
  HANDLE *v18; // [rsp+98h] [rbp+48h]

  dwindex = a3;
  v16 = a2;
  if ( a1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  v18 = 0;
  v4 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
  {
    v16 = -2147024882;
    goto LABEL_27;
  }
  *(_QWORD *)v4 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>::`vftable';
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v4 + 2));
  v4[11] = 1;
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
      v16 = v7;
      goto LABEL_27;
    }
  }
  (*(void (__fastcall **)(_DWORD *))(v8 + 8))(v4);
  v18 = (HANDLE *)v4;
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v4 + 16LL))(v4);
  v16 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)a1 + 48LL))(a1, v18);
  if ( v16 >= 0 )
  {
    pHandles[0] = v18[7];
    pHandles[1] = 0;
    v9 = 0;
    LODWORD(dwindex) = 0;
    v16 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, pHandles, (LPDWORD)&dwindex);
    if ( v16 >= 0 && (_DWORD)dwindex )
    {
      v16 = -2147023673;
      v9 = 1;
    }
    v15 = 0;
    if ( v9
      && (**(int (__fastcall ***)(__int64, GUID *, __int64 *))a1)(a1, &GUID_00000036_0000_0000_c000_000000000046, &v15) >= 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 72LL))(v15);
    }
    if ( v16 >= 0
      && *((_DWORD *)v18 + 12) != 1
      && (v15
       || (**(int (__fastcall ***)(__int64, GUID *, __int64 *))a1)(a1, &GUID_00000036_0000_0000_c000_000000000046, &v15) >= 0) )
    {
      (*(void (__fastcall **)(__int64, HRESULT *))(*(_QWORD *)v15 + 64LL))(v15, &v16);
    }
    v10 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
  }
LABEL_27:
  v11 = v16;
  v12 = v18;
  if ( v18 )
  {
    v18 = 0;
    (*((void (__fastcall **)(HANDLE *))*v12 + 2))(v12);
  }
  if ( a1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  return v11;
}

```

## disassembly

```asm
0x180031d64  mov     [rsp-28h+dwindex], r8
0x180031d69  mov     [rsp-28h+arg_8], edx
0x180031d6d  push    rbp
0x180031d6e  push    rbx
0x180031d6f  push    rsi
0x180031d70  push    rdi
0x180031d71  push    r14
0x180031d73  mov     rbp, rsp
0x180031d76  sub     rsp, 50h
0x180031d7a  mov     rdi, rcx
0x180031d7d  mov     [rbp+var_20], rcx
0x180031d81  xor     r14d, r14d
0x180031d84  test    rcx, rcx
0x180031d87  jz      short loc_180031D96
0x180031d89  mov     rax, [rcx]
0x180031d8c  mov     rax, [rax+8]
0x180031d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031d95  nop
0x180031d96  mov     [rbp+arg_18], r14
0x180031d9a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180031da1  mov     ecx, 40h ; '@'; unsigned __int64
0x180031da6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180031dab  mov     rbx, rax
0x180031dae  test    rax, rax
0x180031db1  jnz     short loc_180031DBF
0x180031db3  mov     [rbp+arg_8], 8007000Eh
0x180031dba  jmp     loc_180031F9C
0x180031dbf  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>::`vftable'
0x180031dc6  mov     [rbx], rax
0x180031dc9  lea     rsi, [rbx+8]
0x180031dcd  mov     rcx, rsi; this
0x180031dd0  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180031dd5  mov     dword ptr [rbx+2Ch], 1
0x180031ddc  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>'}
0x180031de3  mov     [rbx], rax
0x180031de6  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180031ded  mov     [rsi], rax
0x180031df0  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180031df7  test    rcx, rcx
0x180031dfa  jz      short loc_180031E09
0x180031dfc  mov     rax, [rcx]
0x180031dff  mov     rax, [rax+8]
0x180031e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e08  nop
0x180031e09  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>'}
0x180031e10  mov     [rbx], rax
0x180031e13  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180031e1a  mov     [rsi], rax
0x180031e1d  mov     [rbx+30h], r14d
0x180031e21  mov     [rbx+38h], r14
0x180031e25  mov     r9d, 1F0003h; dwDesiredAccess
0x180031e2b  xor     r8d, r8d; dwFlags
0x180031e2e  xor     edx, edx; lpName
0x180031e30  xor     ecx, ecx; lpEventAttributes
0x180031e32  call    cs:__imp_CreateEventExW
0x180031e38  mov     [rbx+38h], rax
0x180031e3c  test    rax, rax
0x180031e3f  jnz     short loc_180031E72
0x180031e41  call    cs:__imp_GetLastError
0x180031e47  mov     esi, eax
0x180031e49  test    eax, eax
0x180031e4b  jle     short loc_180031E56
0x180031e4d  movzx   esi, ax
0x180031e50  or      esi, 80070000h
0x180031e56  mov     rax, [rbx]
0x180031e59  test    esi, esi
0x180031e5b  jns     short loc_180031E75
0x180031e5d  mov     rcx, rbx
0x180031e60  mov     rax, [rax+10h]
0x180031e64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e69  nop
0x180031e6a  mov     [rbp+arg_8], esi
0x180031e6d  jmp     loc_180031F9C
0x180031e72  mov     rax, [rbx]
0x180031e75  mov     rcx, rbx
0x180031e78  mov     rax, [rax+8]
0x180031e7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e81  nop
0x180031e82  mov     [rbp+arg_18], rbx
0x180031e86  mov     rax, [rbx]
0x180031e89  mov     rcx, rbx
0x180031e8c  mov     rax, [rax+10h]
0x180031e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e95  nop
0x180031e96  mov     [rbp+arg_8], r14d
0x180031e9a  mov     rax, [rdi]
0x180031e9d  mov     rdx, [rbp+arg_18]
0x180031ea1  mov     rcx, rdi
0x180031ea4  mov     rax, [rax+30h]
0x180031ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ead  mov     [rbp+arg_8], eax
0x180031eb0  test    eax, eax
0x180031eb2  js      loc_180031F9C
0x180031eb8  mov     rax, [rbp+arg_18]
0x180031ebc  mov     rcx, [rax+38h]
0x180031ec0  mov     [rbp+pHandles], rcx
0x180031ec4  mov     [rbp+var_10], r14
0x180031ec8  mov     bl, r14b
0x180031ecb  mov     dword ptr [rbp+dwindex], r14d
0x180031ecf  lea     rax, [rbp+dwindex]
0x180031ed3  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x180031ed8  lea     r9, [rbp+pHandles]; pHandles
0x180031edc  mov     r8d, 1; cHandles
0x180031ee2  or      edx, 0FFFFFFFFh; dwTimeout
0x180031ee5  lea     ecx, [r8+7]; dwFlags
0x180031ee9  call    cs:__imp_CoWaitForMultipleHandles
0x180031eef  mov     [rbp+arg_8], eax
0x180031ef2  test    eax, eax
0x180031ef4  js      short loc_180031F05
0x180031ef6  cmp     dword ptr [rbp+dwindex], r14d
0x180031efa  jz      short loc_180031F05
0x180031efc  mov     [rbp+arg_8], 800704C7h
0x180031f03  mov     bl, 1
0x180031f05  mov     [rbp+arg_0], r14
0x180031f09  test    bl, bl
0x180031f0b  jz      short loc_180031F3A
0x180031f0d  mov     rax, [rdi]
0x180031f10  lea     r8, [rbp+arg_0]
0x180031f14  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180031f1b  mov     rcx, rdi
0x180031f1e  mov     rax, [rax]
0x180031f21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f26  test    eax, eax
0x180031f28  js      short loc_180031F3A
0x180031f2a  mov     rcx, [rbp+arg_0]
0x180031f2e  mov     rax, [rcx]
0x180031f31  mov     rax, [rax+48h]
0x180031f35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f3a  cmp     [rbp+arg_8], r14d
0x180031f3e  jl      short loc_180031F82
0x180031f40  mov     rax, [rbp+arg_18]
0x180031f44  cmp     dword ptr [rax+30h], 1
0x180031f48  jz      short loc_180031F82
0x180031f4a  cmp     [rbp+arg_0], r14
0x180031f4e  jnz     short loc_180031F6D
0x180031f50  mov     rax, [rdi]
0x180031f53  lea     r8, [rbp+arg_0]
0x180031f57  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180031f5e  mov     rcx, rdi
0x180031f61  mov     rax, [rax]
0x180031f64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f69  test    eax, eax
0x180031f6b  js      short loc_180031F82
0x180031f6d  mov     rcx, [rbp+arg_0]
0x180031f71  mov     rax, [rcx]
0x180031f74  lea     rdx, [rbp+arg_8]
0x180031f78  mov     rax, [rax+40h]
0x180031f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f81  nop
0x180031f82  mov     rcx, [rbp+arg_0]
0x180031f86  test    rcx, rcx
0x180031f89  jz      short loc_180031F9C
0x180031f8b  mov     [rbp+arg_0], r14
0x180031f8f  mov     rax, [rcx]
0x180031f92  mov     rax, [rax+10h]
0x180031f96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f9b  nop
0x180031f9c  mov     ebx, [rbp+arg_8]
0x180031f9f  mov     rcx, [rbp+arg_18]
0x180031fa3  test    rcx, rcx
0x180031fa6  jz      short loc_180031FB9
0x180031fa8  mov     [rbp+arg_18], r14
0x180031fac  mov     rax, [rcx]
0x180031faf  mov     rax, [rax+10h]
0x180031fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031fb8  nop
0x180031fb9  test    rdi, rdi
0x180031fbc  jz      short loc_180031FCE
0x180031fbe  mov     rcx, [rdi]
0x180031fc1  mov     rax, [rcx+10h]
0x180031fc5  mov     rcx, rdi
0x180031fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031fcd  nop
0x180031fce  mov     eax, ebx
0x180031fd0  add     rsp, 50h
0x180031fd4  pop     r14
0x180031fd6  pop     rdi
0x180031fd7  pop     rsi
0x180031fd8  pop     rbx
0x180031fd9  pop     rbp
0x180031fda  retn
```
