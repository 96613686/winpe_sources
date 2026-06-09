# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *>>(Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x180033e38`
- end: `0x1800340c5`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `653`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HRESULT, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180034270`

## callees

- `0x18000d7a0`
- `0x18002de7c`
- `0x1800317f8`
- `0x180033e38`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180033f06`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180033f06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033f15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033f15`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180033fbd`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180033fbd`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *>>(
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
  v4 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v4 )
  {
    v20 = -2147024882;
    goto LABEL_27;
  }
  *(_QWORD *)v4 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>::`vftable';
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(v4 + 2);
  v4[11] = 1;
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>'};
  *((_QWORD *)v4 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *>>'::`2'::FTMEventDelegate::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v4 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *>>'::`2'::FTMEventDelegate::`vftable';
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
0x180033e38  mov     [rsp-28h+dwindex], r8
0x180033e3d  mov     [rsp-28h+arg_8], edx
0x180033e41  push    rbp
0x180033e42  push    rbx
0x180033e43  push    rsi
0x180033e44  push    rdi
0x180033e45  push    r14
0x180033e47  mov     rbp, rsp
0x180033e4a  sub     rsp, 50h
0x180033e4e  mov     rdi, rcx
0x180033e51  mov     [rbp+var_20], rcx
0x180033e55  xor     r14d, r14d
0x180033e58  test    rcx, rcx
0x180033e5b  jz      short loc_180033E6A
0x180033e5d  mov     rax, [rcx]
0x180033e60  mov     rax, [rax+8]
0x180033e64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e69  nop
0x180033e6a  mov     [rbp+arg_18], r14
0x180033e6e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180033e75  mov     ecx, 40h ; '@'; unsigned __int64
0x180033e7a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180033e7f  mov     rbx, rax
0x180033e82  test    rax, rax
0x180033e85  jnz     short loc_180033E93
0x180033e87  mov     [rbp+arg_8], 8007000Eh
0x180033e8e  jmp     loc_180034086
0x180033e93  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>::`vftable'
0x180033e9a  mov     [rbx], rax
0x180033e9d  lea     rsi, [rbx+8]
0x180033ea1  mov     rcx, rsi
0x180033ea4  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x180033ea9  mov     dword ptr [rbx+2Ch], 1
0x180033eb0  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>'}
0x180033eb7  mov     [rbx], rax
0x180033eba  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *>>(Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180033ec1  mov     [rsi], rax
0x180033ec4  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180033ecb  test    rcx, rcx
0x180033ece  jz      short loc_180033EDD
0x180033ed0  mov     rax, [rcx]
0x180033ed3  mov     rax, [rax+8]
0x180033ed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033edc  nop
0x180033edd  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *>>(Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>'}
0x180033ee4  mov     [rbx], rax
0x180033ee7  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *>>(Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180033eee  mov     [rsi], rax
0x180033ef1  mov     [rbx+30h], r14d
0x180033ef5  mov     [rbx+38h], r14
0x180033ef9  mov     r9d, 1F0003h; dwDesiredAccess
0x180033eff  xor     r8d, r8d; dwFlags
0x180033f02  xor     edx, edx; lpName
0x180033f04  xor     ecx, ecx; lpEventAttributes
0x180033f06  call    cs:__imp_CreateEventExW
0x180033f0c  mov     [rbx+38h], rax
0x180033f10  test    rax, rax
0x180033f13  jnz     short loc_180033F46
0x180033f15  call    cs:__imp_GetLastError
0x180033f1b  mov     esi, eax
0x180033f1d  test    eax, eax
0x180033f1f  jle     short loc_180033F2A
0x180033f21  movzx   esi, ax
0x180033f24  or      esi, 80070000h
0x180033f2a  mov     rax, [rbx]
0x180033f2d  test    esi, esi
0x180033f2f  jns     short loc_180033F49
0x180033f31  mov     rcx, rbx
0x180033f34  mov     rax, [rax+10h]
0x180033f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f3d  nop
0x180033f3e  mov     [rbp+arg_8], esi
0x180033f41  jmp     loc_180034086
0x180033f46  mov     rax, [rbx]
0x180033f49  mov     rcx, rbx
0x180033f4c  mov     rax, [rax+8]
0x180033f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f55  nop
0x180033f56  mov     [rbp+arg_18], rbx
0x180033f5a  mov     rax, [rbx]
0x180033f5d  mov     rcx, rbx
0x180033f60  mov     rax, [rax+10h]
0x180033f64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f69  nop
0x180033f6a  mov     [rbp+arg_8], r14d
0x180033f6e  mov     rax, [rdi]
0x180033f71  mov     rdx, [rbp+arg_18]
0x180033f75  mov     rcx, rdi
0x180033f78  mov     rax, [rax+30h]
0x180033f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f81  mov     [rbp+arg_8], eax
0x180033f84  test    eax, eax
0x180033f86  js      loc_180034086
0x180033f8c  mov     rax, [rbp+arg_18]
0x180033f90  mov     rcx, [rax+38h]
0x180033f94  mov     [rbp+pHandles], rcx
0x180033f98  mov     [rbp+var_10], r14
0x180033f9c  mov     bl, r14b
0x180033f9f  mov     dword ptr [rbp+dwindex], r14d
0x180033fa3  lea     rax, [rbp+dwindex]
0x180033fa7  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x180033fac  lea     r9, [rbp+pHandles]; pHandles
0x180033fb0  mov     r8d, 1; cHandles
0x180033fb6  or      edx, 0FFFFFFFFh; dwTimeout
0x180033fb9  lea     ecx, [r8+7]; dwFlags
0x180033fbd  call    cs:__imp_CoWaitForMultipleHandles
0x180033fc3  mov     [rbp+arg_8], eax
0x180033fc6  test    eax, eax
0x180033fc8  js      short loc_180033FD9
0x180033fca  cmp     dword ptr [rbp+dwindex], r14d
0x180033fce  jz      short loc_180033FD9
0x180033fd0  mov     [rbp+arg_8], 800704C7h
0x180033fd7  mov     bl, 1
0x180033fd9  mov     [rbp+arg_0], r14
0x180033fdd  test    bl, bl
0x180033fdf  jz      short loc_180034019
0x180033fe1  mov     rax, [rdi]
0x180033fe4  mov     rbx, [rax]
0x180033fe7  lea     rcx, [rbp+arg_0]
0x180033feb  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x180033ff0  mov     r8, rax
0x180033ff3  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180033ffa  mov     rcx, rdi
0x180033ffd  mov     rax, rbx
0x180034000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034005  test    eax, eax
0x180034007  js      short loc_180034019
0x180034009  mov     rcx, [rbp+arg_0]
0x18003400d  mov     rax, [rcx]
0x180034010  mov     rax, [rax+48h]
0x180034014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034019  cmp     [rbp+arg_8], r14d
0x18003401d  jl      short loc_18003406C
0x18003401f  mov     rax, [rbp+arg_18]
0x180034023  cmp     dword ptr [rax+30h], 1
0x180034027  jz      short loc_18003406C
0x180034029  cmp     [rbp+arg_0], r14
0x18003402d  jnz     short loc_180034057
0x18003402f  mov     rax, [rdi]
0x180034032  mov     rbx, [rax]
0x180034035  lea     rcx, [rbp+arg_0]
0x180034039  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x18003403e  mov     r8, rax
0x180034041  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180034048  mov     rcx, rdi
0x18003404b  mov     rax, rbx
0x18003404e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034053  test    eax, eax
0x180034055  js      short loc_18003406C
0x180034057  mov     rcx, [rbp+arg_0]
0x18003405b  mov     rax, [rcx]
0x18003405e  lea     rdx, [rbp+arg_8]
0x180034062  mov     rax, [rax+40h]
0x180034066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003406b  nop
0x18003406c  mov     rcx, [rbp+arg_0]
0x180034070  test    rcx, rcx
0x180034073  jz      short loc_180034086
0x180034075  mov     [rbp+arg_0], r14
0x180034079  mov     rax, [rcx]
0x18003407c  mov     rax, [rax+10h]
0x180034080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034085  nop
0x180034086  mov     ebx, [rbp+arg_8]
0x180034089  mov     rcx, [rbp+arg_18]
0x18003408d  test    rcx, rcx
0x180034090  jz      short loc_1800340A3
0x180034092  mov     [rbp+arg_18], r14
0x180034096  mov     rax, [rcx]
0x180034099  mov     rax, [rax+10h]
0x18003409d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800340a2  nop
0x1800340a3  test    rdi, rdi
0x1800340a6  jz      short loc_1800340B8
0x1800340a8  mov     rcx, [rdi]
0x1800340ab  mov     rax, [rcx+10h]
0x1800340af  mov     rcx, rdi
0x1800340b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800340b7  nop
0x1800340b8  mov     eax, ebx
0x1800340ba  add     rsp, 50h
0x1800340be  pop     r14
0x1800340c0  pop     rdi
0x1800340c1  pop     rsi
0x1800340c2  pop     rbx
0x1800340c3  pop     rbp
0x1800340c4  retn
```
