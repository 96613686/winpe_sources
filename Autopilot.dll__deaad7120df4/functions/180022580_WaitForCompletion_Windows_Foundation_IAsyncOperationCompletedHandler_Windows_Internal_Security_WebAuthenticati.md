# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x180022580`
- end: `0x180022820`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `672`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HRESULT, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800238cc`

## callees

- `0x180004638`
- `0x180009c6c`
- `0x18000a944`
- `0x180022580`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180022711`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180022711`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002264e`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002264e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022663`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022663`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        HRESULT a2,
        __int64 a3)
{
  _DWORD *v4; // rbx
  HANDLE Event; // rax
  signed int LastError; // eax
  signed int v7; // esi
  __int64 v8; // rax
  char v9; // bl
  int (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v11; // rax
  int (__fastcall *v12)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v13; // rax
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
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[1])(a1);
  v22 = 0;
  v4 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
  {
    v20 = -2147024882;
    goto LABEL_27;
  }
  *(_QWORD *)v4 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>::`vftable';
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v4 + 2));
  v4[11] = 1;
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
  v20 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HANDLE *))(*a1)[6])(a1, v22);
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
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[2])(a1);
  return v15;
}

```

## disassembly

```asm
0x180022580  mov     [rsp-28h+dwindex], r8
0x180022585  mov     [rsp-28h+arg_8], edx
0x180022589  push    rbp
0x18002258a  push    rbx
0x18002258b  push    rsi
0x18002258c  push    rdi
0x18002258d  push    r14
0x18002258f  mov     rbp, rsp
0x180022592  sub     rsp, 50h
0x180022596  mov     rdi, rcx
0x180022599  mov     [rbp+var_20], rcx
0x18002259d  xor     r14d, r14d
0x1800225a0  test    rcx, rcx
0x1800225a3  jz      short loc_1800225B2
0x1800225a5  mov     rax, [rcx]
0x1800225a8  mov     rax, [rax+8]
0x1800225ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225b1  nop
0x1800225b2  mov     [rbp+arg_18], r14
0x1800225b6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800225bd  mov     ecx, 40h ; '@'; unsigned __int64
0x1800225c2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800225c7  mov     rbx, rax
0x1800225ca  test    rax, rax
0x1800225cd  jnz     short loc_1800225DB
0x1800225cf  mov     [rbp+arg_8], 8007000Eh
0x1800225d6  jmp     loc_1800227E0
0x1800225db  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>::`vftable'
0x1800225e2  mov     [rbx], rax
0x1800225e5  lea     rsi, [rbx+8]
0x1800225e9  mov     rcx, rsi; this
0x1800225ec  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x1800225f1  mov     dword ptr [rbx+2Ch], 1
0x1800225f8  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>'}
0x1800225ff  mov     [rbx], rax
0x180022602  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180022609  mov     [rsi], rax
0x18002260c  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180022613  test    rcx, rcx
0x180022616  jz      short loc_180022625
0x180022618  mov     rax, [rcx]
0x18002261b  mov     rax, [rax+8]
0x18002261f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022624  nop
0x180022625  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>'}
0x18002262c  mov     [rbx], rax
0x18002262f  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180022636  mov     [rsi], rax
0x180022639  mov     [rbx+30h], r14d
0x18002263d  mov     [rbx+38h], r14
0x180022641  mov     r9d, 1F0003h; dwDesiredAccess
0x180022647  xor     r8d, r8d; dwFlags
0x18002264a  xor     edx, edx; lpName
0x18002264c  xor     ecx, ecx; lpEventAttributes
0x18002264e  call    cs:__imp_CreateEventExW
0x180022655  nop     dword ptr [rax+rax+00h]
0x18002265a  mov     [rbx+38h], rax
0x18002265e  test    rax, rax
0x180022661  jnz     short loc_18002269A
0x180022663  call    cs:__imp_GetLastError
0x18002266a  nop     dword ptr [rax+rax+00h]
0x18002266f  mov     esi, eax
0x180022671  test    eax, eax
0x180022673  jle     short loc_18002267E
0x180022675  movzx   esi, ax
0x180022678  or      esi, 80070000h
0x18002267e  mov     rax, [rbx]
0x180022681  test    esi, esi
0x180022683  jns     short loc_18002269D
0x180022685  mov     rcx, rbx
0x180022688  mov     rax, [rax+10h]
0x18002268c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022691  nop
0x180022692  mov     [rbp+arg_8], esi
0x180022695  jmp     loc_1800227E0
0x18002269a  mov     rax, [rbx]
0x18002269d  mov     rcx, rbx
0x1800226a0  mov     rax, [rax+8]
0x1800226a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226a9  nop
0x1800226aa  mov     [rbp+arg_18], rbx
0x1800226ae  mov     rax, [rbx]
0x1800226b1  mov     rcx, rbx
0x1800226b4  mov     rax, [rax+10h]
0x1800226b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226bd  nop
0x1800226be  mov     [rbp+arg_8], r14d
0x1800226c2  mov     rax, [rdi]
0x1800226c5  mov     rdx, [rbp+arg_18]
0x1800226c9  mov     rcx, rdi
0x1800226cc  mov     rax, [rax+30h]
0x1800226d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226d5  mov     [rbp+arg_8], eax
0x1800226d8  test    eax, eax
0x1800226da  js      loc_1800227E0
0x1800226e0  mov     rax, [rbp+arg_18]
0x1800226e4  mov     rcx, [rax+38h]
0x1800226e8  mov     [rbp+pHandles], rcx
0x1800226ec  mov     [rbp+var_10], r14
0x1800226f0  mov     bl, r14b
0x1800226f3  mov     dword ptr [rbp+dwindex], r14d
0x1800226f7  lea     rax, [rbp+dwindex]
0x1800226fb  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x180022700  lea     r9, [rbp+pHandles]; pHandles
0x180022704  mov     r8d, 1; cHandles
0x18002270a  or      edx, 0FFFFFFFFh; dwTimeout
0x18002270d  lea     ecx, [r8+7]; dwFlags
0x180022711  call    cs:__imp_CoWaitForMultipleHandles
0x180022718  nop     dword ptr [rax+rax+00h]
0x18002271d  mov     [rbp+arg_8], eax
0x180022720  test    eax, eax
0x180022722  js      short loc_180022733
0x180022724  cmp     dword ptr [rbp+dwindex], r14d
0x180022728  jz      short loc_180022733
0x18002272a  mov     [rbp+arg_8], 800704C7h
0x180022731  mov     bl, 1
0x180022733  mov     [rbp+arg_0], r14
0x180022737  test    bl, bl
0x180022739  jz      short loc_180022773
0x18002273b  mov     rax, [rdi]
0x18002273e  mov     rbx, [rax]
0x180022741  lea     rcx, [rbp+arg_0]
0x180022745  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x18002274a  mov     r8, rax
0x18002274d  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180022754  mov     rcx, rdi
0x180022757  mov     rax, rbx
0x18002275a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002275f  test    eax, eax
0x180022761  js      short loc_180022773
0x180022763  mov     rcx, [rbp+arg_0]
0x180022767  mov     rax, [rcx]
0x18002276a  mov     rax, [rax+48h]
0x18002276e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022773  cmp     [rbp+arg_8], r14d
0x180022777  jl      short loc_1800227C6
0x180022779  mov     rax, [rbp+arg_18]
0x18002277d  cmp     dword ptr [rax+30h], 1
0x180022781  jz      short loc_1800227C6
0x180022783  cmp     [rbp+arg_0], r14
0x180022787  jnz     short loc_1800227B1
0x180022789  mov     rax, [rdi]
0x18002278c  mov     rbx, [rax]
0x18002278f  lea     rcx, [rbp+arg_0]
0x180022793  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x180022798  mov     r8, rax
0x18002279b  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x1800227a2  mov     rcx, rdi
0x1800227a5  mov     rax, rbx
0x1800227a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227ad  test    eax, eax
0x1800227af  js      short loc_1800227C6
0x1800227b1  mov     rcx, [rbp+arg_0]
0x1800227b5  mov     rax, [rcx]
0x1800227b8  lea     rdx, [rbp+arg_8]
0x1800227bc  mov     rax, [rax+40h]
0x1800227c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227c5  nop
0x1800227c6  mov     rcx, [rbp+arg_0]
0x1800227ca  test    rcx, rcx
0x1800227cd  jz      short loc_1800227E0
0x1800227cf  mov     [rbp+arg_0], r14
0x1800227d3  mov     rax, [rcx]
0x1800227d6  mov     rax, [rax+10h]
0x1800227da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227df  nop
0x1800227e0  mov     ebx, [rbp+arg_8]
0x1800227e3  mov     rcx, [rbp+arg_18]
0x1800227e7  test    rcx, rcx
0x1800227ea  jz      short loc_1800227FD
0x1800227ec  mov     [rbp+arg_18], r14
0x1800227f0  mov     rax, [rcx]
0x1800227f3  mov     rax, [rax+10h]
0x1800227f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227fc  nop
0x1800227fd  test    rdi, rdi
0x180022800  jz      short loc_180022812
0x180022802  mov     rcx, [rdi]
0x180022805  mov     rax, [rcx+10h]
0x180022809  mov     rcx, rdi
0x18002280c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022811  nop
0x180022812  mov     eax, ebx
0x180022814  add     rsp, 50h
0x180022818  pop     r14
0x18002281a  pop     rdi
0x18002281b  pop     rsi
0x18002281c  pop     rbx
0x18002281d  pop     rbp
0x18002281e  retn
```
