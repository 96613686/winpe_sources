# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x180050540`
- end: `0x1800507cd`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180051ed8`

## callees

- `0x1800065c8`
- `0x180032194`
- `0x180032410`
- `0x180050540`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005061d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005061d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18005060e`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18005060e`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800506c5`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800506c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(
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
  *(_QWORD *)v4 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>::`vftable';
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v4 + 2));
  v4[11] = 1;
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v4 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>'::`2'::FTMEventDelegate::`vftable';
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
0x180050540  mov     [rsp-28h+dwindex], r8
0x180050545  mov     [rsp-28h+arg_8], edx
0x180050549  push    rbp
0x18005054a  push    rbx
0x18005054b  push    rsi
0x18005054c  push    rdi
0x18005054d  push    r14
0x18005054f  mov     rbp, rsp
0x180050552  sub     rsp, 50h
0x180050556  mov     rdi, rcx
0x180050559  mov     [rbp+var_20], rcx
0x18005055d  xor     r14d, r14d
0x180050560  test    rcx, rcx
0x180050563  jz      short loc_180050572
0x180050565  mov     rax, [rcx]
0x180050568  mov     rax, [rax+8]
0x18005056c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050571  nop
0x180050572  mov     [rbp+arg_18], r14
0x180050576  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005057d  mov     ecx, 40h ; '@'; unsigned __int64
0x180050582  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180050587  mov     rbx, rax
0x18005058a  test    rax, rax
0x18005058d  jnz     short loc_18005059B
0x18005058f  mov     [rbp+arg_8], 8007000Eh
0x180050596  jmp     loc_18005078E
0x18005059b  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>::`vftable'
0x1800505a2  mov     [rbx], rax
0x1800505a5  lea     rsi, [rbx+8]
0x1800505a9  mov     rcx, rsi; this
0x1800505ac  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x1800505b1  mov     dword ptr [rbx+2Ch], 1
0x1800505b8  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>'}
0x1800505bf  mov     [rbx], rax
0x1800505c2  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800505c9  mov     [rsi], rax
0x1800505cc  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800505d3  test    rcx, rcx
0x1800505d6  jz      short loc_1800505E5
0x1800505d8  mov     rax, [rcx]
0x1800505db  mov     rax, [rax+8]
0x1800505df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800505e4  nop
0x1800505e5  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>'}
0x1800505ec  mov     [rbx], rax
0x1800505ef  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800505f6  mov     [rsi], rax
0x1800505f9  mov     [rbx+30h], r14d
0x1800505fd  mov     [rbx+38h], r14
0x180050601  mov     r9d, 1F0003h; dwDesiredAccess
0x180050607  xor     r8d, r8d; dwFlags
0x18005060a  xor     edx, edx; lpName
0x18005060c  xor     ecx, ecx; lpEventAttributes
0x18005060e  call    cs:__imp_CreateEventExW
0x180050614  mov     [rbx+38h], rax
0x180050618  test    rax, rax
0x18005061b  jnz     short loc_18005064E
0x18005061d  call    cs:__imp_GetLastError
0x180050623  mov     esi, eax
0x180050625  test    eax, eax
0x180050627  jle     short loc_180050632
0x180050629  movzx   esi, ax
0x18005062c  or      esi, 80070000h
0x180050632  mov     rax, [rbx]
0x180050635  test    esi, esi
0x180050637  jns     short loc_180050651
0x180050639  mov     rcx, rbx
0x18005063c  mov     rax, [rax+10h]
0x180050640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050645  nop
0x180050646  mov     [rbp+arg_8], esi
0x180050649  jmp     loc_18005078E
0x18005064e  mov     rax, [rbx]
0x180050651  mov     rcx, rbx
0x180050654  mov     rax, [rax+8]
0x180050658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005065d  nop
0x18005065e  mov     [rbp+arg_18], rbx
0x180050662  mov     rax, [rbx]
0x180050665  mov     rcx, rbx
0x180050668  mov     rax, [rax+10h]
0x18005066c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050671  nop
0x180050672  mov     [rbp+arg_8], r14d
0x180050676  mov     rax, [rdi]
0x180050679  mov     rdx, [rbp+arg_18]
0x18005067d  mov     rcx, rdi
0x180050680  mov     rax, [rax+30h]
0x180050684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050689  mov     [rbp+arg_8], eax
0x18005068c  test    eax, eax
0x18005068e  js      loc_18005078E
0x180050694  mov     rax, [rbp+arg_18]
0x180050698  mov     rcx, [rax+38h]
0x18005069c  mov     [rbp+pHandles], rcx
0x1800506a0  mov     [rbp+var_10], r14
0x1800506a4  mov     bl, r14b
0x1800506a7  mov     dword ptr [rbp+dwindex], r14d
0x1800506ab  lea     rax, [rbp+dwindex]
0x1800506af  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x1800506b4  lea     r9, [rbp+pHandles]; pHandles
0x1800506b8  mov     r8d, 1; cHandles
0x1800506be  or      edx, 0FFFFFFFFh; dwTimeout
0x1800506c1  lea     ecx, [r8+7]; dwFlags
0x1800506c5  call    cs:__imp_CoWaitForMultipleHandles
0x1800506cb  mov     [rbp+arg_8], eax
0x1800506ce  test    eax, eax
0x1800506d0  js      short loc_1800506E1
0x1800506d2  cmp     dword ptr [rbp+dwindex], r14d
0x1800506d6  jz      short loc_1800506E1
0x1800506d8  mov     [rbp+arg_8], 800704C7h
0x1800506df  mov     bl, 1
0x1800506e1  mov     [rbp+arg_0], r14
0x1800506e5  test    bl, bl
0x1800506e7  jz      short loc_180050721
0x1800506e9  mov     rax, [rdi]
0x1800506ec  mov     rbx, [rax]
0x1800506ef  lea     rcx, [rbp+arg_0]
0x1800506f3  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x1800506f8  mov     r8, rax
0x1800506fb  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180050702  mov     rcx, rdi
0x180050705  mov     rax, rbx
0x180050708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005070d  test    eax, eax
0x18005070f  js      short loc_180050721
0x180050711  mov     rcx, [rbp+arg_0]
0x180050715  mov     rax, [rcx]
0x180050718  mov     rax, [rax+48h]
0x18005071c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050721  cmp     [rbp+arg_8], r14d
0x180050725  jl      short loc_180050774
0x180050727  mov     rax, [rbp+arg_18]
0x18005072b  cmp     dword ptr [rax+30h], 1
0x18005072f  jz      short loc_180050774
0x180050731  cmp     [rbp+arg_0], r14
0x180050735  jnz     short loc_18005075F
0x180050737  mov     rax, [rdi]
0x18005073a  mov     rbx, [rax]
0x18005073d  lea     rcx, [rbp+arg_0]
0x180050741  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x180050746  mov     r8, rax
0x180050749  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180050750  mov     rcx, rdi
0x180050753  mov     rax, rbx
0x180050756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005075b  test    eax, eax
0x18005075d  js      short loc_180050774
0x18005075f  mov     rcx, [rbp+arg_0]
0x180050763  mov     rax, [rcx]
0x180050766  lea     rdx, [rbp+arg_8]
0x18005076a  mov     rax, [rax+40h]
0x18005076e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050773  nop
0x180050774  mov     rcx, [rbp+arg_0]
0x180050778  test    rcx, rcx
0x18005077b  jz      short loc_18005078E
0x18005077d  mov     [rbp+arg_0], r14
0x180050781  mov     rax, [rcx]
0x180050784  mov     rax, [rax+10h]
0x180050788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005078d  nop
0x18005078e  mov     ebx, [rbp+arg_8]
0x180050791  mov     rcx, [rbp+arg_18]
0x180050795  test    rcx, rcx
0x180050798  jz      short loc_1800507AB
0x18005079a  mov     [rbp+arg_18], r14
0x18005079e  mov     rax, [rcx]
0x1800507a1  mov     rax, [rax+10h]
0x1800507a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800507aa  nop
0x1800507ab  test    rdi, rdi
0x1800507ae  jz      short loc_1800507C0
0x1800507b0  mov     rcx, [rdi]
0x1800507b3  mov     rax, [rcx+10h]
0x1800507b7  mov     rcx, rdi
0x1800507ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800507bf  nop
0x1800507c0  mov     eax, ebx
0x1800507c2  add     rsp, 50h
0x1800507c6  pop     r14
0x1800507c8  pop     rdi
0x1800507c9  pop     rsi
0x1800507ca  pop     rbx
0x1800507cb  pop     rbp
0x1800507cc  retn
```
