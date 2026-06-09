# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x140033450`
- end: `0x1400336bd`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `621`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HRESULT, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1400337d8`

## callees

- `0x140004314`
- `0x140005ea8`
- `0x140006e08`
- `0x140008a40`
- `0x140033450`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x14003351b`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x14003351b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003352a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003352a`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1400335cc`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1400335cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        HRESULT a2,
        __int64 a3)
{
  _QWORD *v4; // rbx
  signed int v5; // edi
  struct Microsoft::WRL::Details::ModuleBase *v6; // rcx
  HANDLE Event; // rax
  signed int LastError; // eax
  __int64 v9; // rax
  int (__fastcall **v10)(_QWORD, GUID *, __int64 *); // rax
  int (__fastcall **v11)(_QWORD, GUID *, __int64 *); // rax
  int (__fastcall *v12)(_QWORD, GUID *, __int64 *); // rdi
  __int64 *v13; // rax
  int (__fastcall *v14)(_QWORD, GUID *, __int64 *); // rdi
  __int64 *v15; // rax
  HANDLE pHandles[2]; // [rsp+30h] [rbp-10h] BYREF
  __int64 v18; // [rsp+60h] [rbp+20h] BYREF
  HRESULT v19; // [rsp+68h] [rbp+28h] BYREF
  __int64 dwindex; // [rsp+70h] [rbp+30h] BYREF

  dwindex = a3;
  v19 = a2;
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[1])(a1);
  v4 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
  {
    v5 = -2147024882;
LABEL_5:
    v19 = v5;
    goto LABEL_27;
  }
  *v4 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>::`vftable';
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(v4 + 1);
  v6 = Microsoft::WRL::Details::ModuleBase::module_;
  *v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>'};
  v4[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_DWORD *)v4 + 11) = 1;
  if ( v6 )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v6 + 8LL))(v6);
  *((_DWORD *)v4 + 12) = 0;
  *v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>'::`2'::FTMEventDelegate::`vftable';
  v4[7] = 0;
  v4[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  v4[7] = Event;
  if ( Event )
  {
    v9 = *v4;
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v9 = *v4;
    if ( v5 < 0 )
    {
      (*(void (__fastcall **)(_QWORD *))(v9 + 16))(v4);
      goto LABEL_5;
    }
  }
  (*(void (__fastcall **)(_QWORD *))(v9 + 8))(v4);
  (*(void (__fastcall **)(_QWORD *))(*v4 + 16LL))(v4);
  v10 = *a1;
  v19 = 0;
  v19 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), _QWORD *))v10[6])(a1, v4);
  v5 = v19;
  if ( v19 >= 0 )
  {
    pHandles[0] = *((HANDLE *)v4 + 7);
    pHandles[1] = 0;
    LODWORD(dwindex) = 0;
    v19 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, pHandles, (LPDWORD)&dwindex);
    if ( v19 >= 0 && (_DWORD)dwindex )
    {
      v11 = *a1;
      v19 = -2147023673;
      v18 = 0;
      v12 = *v11;
      v13 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>(&v18);
      if ( v12(a1, &GUID_00000036_0000_0000_c000_000000000046, v13) >= 0 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 72LL))(v18);
    }
    else
    {
      v18 = 0;
    }
    if ( v19 >= 0 && *((_DWORD *)v4 + 12) != 1 )
    {
      if ( v18
        || (v14 = **a1,
            v15 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>(&v18),
            v14(a1, &GUID_00000036_0000_0000_c000_000000000046, v15) >= 0) )
      {
        (*(void (__fastcall **)(__int64, HRESULT *))(*(_QWORD *)v18 + 64LL))(v18, &v19);
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction>::InternalRelease(&v18);
    v5 = v19;
  }
  (*(void (__fastcall **)(_QWORD *))(*v4 + 16LL))(v4);
LABEL_27:
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[2])(a1);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140033450  mov     [rsp-18h+arg_18], rbx
0x140033455  mov     [rsp-18h+dwindex], r8
0x14003345a  mov     [rsp-18h+arg_8], edx
0x14003345e  push    rbp
0x14003345f  push    rsi
0x140033460  push    rdi
0x140033461  mov     rbp, rsp
0x140033464  sub     rsp, 40h
0x140033468  mov     rsi, rcx
0x14003346b  test    rcx, rcx
0x14003346e  jz      short loc_14003347C
0x140033470  mov     rax, [rcx]
0x140033473  mov     rax, [rax+8]
0x140033477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003347c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140033483  mov     ecx, 40h ; '@'; unsigned __int64
0x140033488  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14003348d  mov     rbx, rax
0x140033490  test    rax, rax
0x140033493  jnz     short loc_1400334A2
0x140033495  mov     edi, 8007000Eh
0x14003349a  mov     [rbp+arg_8], edi
0x14003349d  jmp     loc_14003369A
0x1400334a2  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>::`vftable'
0x1400334a9  lea     rdi, [rbx+8]
0x1400334ad  mov     [rbx], rax
0x1400334b0  mov     rcx, rdi
0x1400334b3  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x1400334b8  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1400334bf  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>'}
0x1400334c6  mov     [rbx], rax
0x1400334c9  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1400334d0  mov     [rdi], rax
0x1400334d3  mov     dword ptr [rbx+2Ch], 1
0x1400334da  test    rcx, rcx
0x1400334dd  jz      short loc_1400334EB
0x1400334df  mov     rax, [rcx]
0x1400334e2  mov     rax, [rax+8]
0x1400334e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400334eb  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>'}
0x1400334f2  mov     dword ptr [rbx+30h], 0
0x1400334f9  mov     [rbx], rax
0x1400334fc  mov     r9d, 1F0003h; dwDesiredAccess
0x140033502  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x140033509  mov     qword ptr [rbx+38h], 0
0x140033511  xor     r8d, r8d; dwFlags
0x140033514  mov     [rdi], rax
0x140033517  xor     edx, edx; lpName
0x140033519  xor     ecx, ecx; lpEventAttributes
0x14003351b  call    cs:__imp_CreateEventExW
0x140033521  mov     [rbx+38h], rax
0x140033525  test    rax, rax
0x140033528  jnz     short loc_140033557
0x14003352a  call    cs:__imp_GetLastError
0x140033530  mov     edi, eax
0x140033532  test    eax, eax
0x140033534  jle     short loc_14003353F
0x140033536  movzx   edi, ax
0x140033539  or      edi, 80070000h
0x14003353f  mov     rax, [rbx]
0x140033542  test    edi, edi
0x140033544  jns     short loc_14003355A
0x140033546  mov     rax, [rax+10h]
0x14003354a  mov     rcx, rbx
0x14003354d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033552  jmp     loc_14003349A
0x140033557  mov     rax, [rbx]
0x14003355a  mov     rax, [rax+8]
0x14003355e  mov     rcx, rbx
0x140033561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033566  mov     rax, [rbx]
0x140033569  mov     rcx, rbx
0x14003356c  mov     rax, [rax+10h]
0x140033570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033575  mov     rax, [rsi]
0x140033578  mov     rdx, rbx
0x14003357b  mov     rcx, rsi
0x14003357e  mov     [rbp+arg_8], 0
0x140033585  mov     rax, [rax+30h]
0x140033589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003358e  mov     [rbp+arg_8], eax
0x140033591  mov     edi, eax
0x140033593  test    eax, eax
0x140033595  js      loc_14003368B
0x14003359b  mov     rax, [rbx+38h]
0x14003359f  lea     r9, [rbp+pHandles]; pHandles
0x1400335a3  mov     r8d, 1; cHandles
0x1400335a9  mov     [rbp+pHandles], rax
0x1400335ad  lea     rax, [rbp+dwindex]
0x1400335b1  mov     [rbp+var_8], 0
0x1400335b9  or      edx, 0FFFFFFFFh; dwTimeout
0x1400335bc  mov     dword ptr [rbp+dwindex], 0
0x1400335c3  mov     [rsp+40h+lpdwindex], rax; lpdwindex
0x1400335c8  lea     ecx, [r8+7]; dwFlags
0x1400335cc  call    cs:__imp_CoWaitForMultipleHandles
0x1400335d2  mov     [rbp+arg_8], eax
0x1400335d5  test    eax, eax
0x1400335d7  js      short loc_140033628
0x1400335d9  cmp     dword ptr [rbp+dwindex], 0
0x1400335dd  jz      short loc_140033628
0x1400335df  mov     rax, [rsi]
0x1400335e2  lea     rcx, [rbp+arg_0]
0x1400335e6  mov     [rbp+arg_8], 800704C7h
0x1400335ed  mov     [rbp+arg_0], 0
0x1400335f5  mov     rdi, [rax]
0x1400335f8  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ITaskService>>)
0x1400335fd  mov     r8, rax
0x140033600  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x140033607  mov     rax, rdi
0x14003360a  mov     rcx, rsi
0x14003360d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033612  test    eax, eax
0x140033614  js      short loc_140033630
0x140033616  mov     rcx, [rbp+arg_0]
0x14003361a  mov     rax, [rcx]
0x14003361d  mov     rax, [rax+48h]
0x140033621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033626  jmp     short loc_140033630
0x140033628  mov     [rbp+arg_0], 0
0x140033630  cmp     [rbp+arg_8], 0
0x140033634  jl      short loc_14003367F
0x140033636  cmp     dword ptr [rbx+30h], 1
0x14003363a  jz      short loc_14003367F
0x14003363c  cmp     [rbp+arg_0], 0
0x140033641  jnz     short loc_14003366B
0x140033643  mov     rax, [rsi]
0x140033646  lea     rcx, [rbp+arg_0]
0x14003364a  mov     rdi, [rax]
0x14003364d  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ITaskService>>)
0x140033652  mov     r8, rax
0x140033655  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x14003365c  mov     rax, rdi
0x14003365f  mov     rcx, rsi
0x140033662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033667  test    eax, eax
0x140033669  js      short loc_14003367F
0x14003366b  mov     rcx, [rbp+arg_0]
0x14003366f  lea     rdx, [rbp+arg_8]
0x140033673  mov     rax, [rcx]
0x140033676  mov     rax, [rax+40h]
0x14003367a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003367f  lea     rcx, [rbp+arg_0]
0x140033683  call    ?InternalRelease@?$ComPtr@UIAsyncAction@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction>::InternalRelease(void)
0x140033688  mov     edi, [rbp+arg_8]
0x14003368b  mov     rax, [rbx]
0x14003368e  mov     rcx, rbx
0x140033691  mov     rax, [rax+10h]
0x140033695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003369a  test    rsi, rsi
0x14003369d  jz      short loc_1400336AE
0x14003369f  mov     rcx, [rsi]
0x1400336a2  mov     rax, [rcx+10h]
0x1400336a6  mov     rcx, rsi
0x1400336a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400336ae  mov     rbx, [rsp+40h+arg_18]
0x1400336b3  mov     eax, edi
0x1400336b5  add     rsp, 40h
0x1400336b9  pop     rdi
0x1400336ba  pop     rsi
0x1400336bb  pop     rbp
0x1400336bc  retn
```
