# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *>>(Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x14001e458`
- end: `0x14001e704`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `684`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HRESULT, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140024bc4`

## callees

- `0x140004314`
- `0x140005ea8`
- `0x140006e08`
- `0x14001e458`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x14001e52c`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x14001e52c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001e53b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001e53b`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x14001e5ef`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x14001e5ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *>>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        HRESULT a2,
        void *a3)
{
  _DWORD *v5; // rbx
  HANDLE Event; // rax
  signed int LastError; // eax
  signed int v8; // esi
  __int64 v9; // rax
  char v10; // bl
  int (__fastcall *v11)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v12; // rax
  int (__fastcall *v13)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v14; // rax
  __int64 v15; // rcx
  unsigned int v16; // ebx
  _DWORD *v18; // [rsp+30h] [rbp-20h]
  HANDLE pHandles[2]; // [rsp+40h] [rbp-10h] BYREF
  DWORD dwindex; // [rsp+80h] [rbp+30h] BYREF
  HRESULT v21; // [rsp+88h] [rbp+38h] BYREF
  __int64 v22; // [rsp+98h] [rbp+48h] BYREF

  v21 = a2;
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[1])(a1);
  v18 = 0;
  v5 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v5 )
  {
    v21 = -2147024882;
    goto LABEL_27;
  }
  *(_QWORD *)v5 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>::`vftable';
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(v5 + 2);
  v5[11] = 1;
  *(_QWORD *)v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>'};
  *((_QWORD *)v5 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *>>'::`2'::FTMEventDelegate::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v5 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v5 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *>>'::`2'::FTMEventDelegate::`vftable';
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
      v21 = v8;
      goto LABEL_27;
    }
  }
  (*(void (__fastcall **)(_DWORD *))(v9 + 8))(v5);
  v18 = v5;
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v5 + 16LL))(v5);
  v21 = 0;
  v21 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), _DWORD *))(*a1)[6])(a1, v5);
  if ( v21 >= 0 )
  {
    pHandles[0] = *((HANDLE *)v5 + 7);
    pHandles[1] = a3;
    v10 = 0;
    dwindex = 0;
    v21 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, (a3 != 0) + 1, pHandles, &dwindex);
    if ( v21 >= 0 && dwindex )
    {
      v21 = -2147023673;
      v10 = 1;
    }
    v22 = 0;
    if ( v10 )
    {
      v11 = **a1;
      v12 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>(&v22);
      if ( v11(a1, &GUID_00000036_0000_0000_c000_000000000046, v12) >= 0 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 72LL))(v22);
    }
    if ( v21 >= 0 && v18[12] != 1 )
    {
      if ( v22
        || (v13 = **a1,
            v14 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>(&v22),
            v13(a1, &GUID_00000036_0000_0000_c000_000000000046, v14) >= 0) )
      {
        (*(void (__fastcall **)(__int64, HRESULT *))(*(_QWORD *)v22 + 64LL))(v22, &v21);
      }
    }
    v15 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
  }
LABEL_27:
  v16 = v21;
  if ( v18 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v18 + 16LL))(v18);
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[2])(a1);
  return v16;
}

```

## disassembly

```asm
0x14001e458  mov     [rsp-28h+arg_8], edx
0x14001e45c  push    rbp
0x14001e45d  push    rbx
0x14001e45e  push    rsi
0x14001e45f  push    rdi
0x14001e460  push    r14
0x14001e462  mov     rbp, rsp
0x14001e465  sub     rsp, 50h
0x14001e469  mov     r14, r8
0x14001e46c  mov     rdi, rcx
0x14001e46f  mov     [rbp+var_18], rcx
0x14001e473  test    rcx, rcx
0x14001e476  jz      short loc_14001E485
0x14001e478  mov     rax, [rcx]
0x14001e47b  mov     rax, [rax+8]
0x14001e47f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e484  nop
0x14001e485  mov     [rbp+var_20], 0
0x14001e48d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001e494  mov     ecx, 40h ; '@'; unsigned __int64
0x14001e499  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14001e49e  mov     rbx, rax
0x14001e4a1  test    rax, rax
0x14001e4a4  jnz     short loc_14001E4B2
0x14001e4a6  mov     [rbp+arg_8], 8007000Eh
0x14001e4ad  jmp     loc_14001E6C1
0x14001e4b2  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>::`vftable'
0x14001e4b9  mov     [rbx], rax
0x14001e4bc  lea     rsi, [rbx+8]
0x14001e4c0  mov     rcx, rsi
0x14001e4c3  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x14001e4c8  mov     dword ptr [rbx+2Ch], 1
0x14001e4cf  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>'}
0x14001e4d6  mov     [rbx], rax
0x14001e4d9  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *>>(Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x14001e4e0  mov     [rsi], rax
0x14001e4e3  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14001e4ea  test    rcx, rcx
0x14001e4ed  jz      short loc_14001E4FC
0x14001e4ef  mov     rax, [rcx]
0x14001e4f2  mov     rax, [rax+8]
0x14001e4f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e4fb  nop
0x14001e4fc  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *>>(Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>'}
0x14001e503  mov     [rbx], rax
0x14001e506  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *>>(Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x14001e50d  mov     [rsi], rax
0x14001e510  mov     dword ptr [rbx+30h], 0
0x14001e517  mov     qword ptr [rbx+38h], 0
0x14001e51f  mov     r9d, 1F0003h; dwDesiredAccess
0x14001e525  xor     r8d, r8d; dwFlags
0x14001e528  xor     edx, edx; lpName
0x14001e52a  xor     ecx, ecx; lpEventAttributes
0x14001e52c  call    cs:__imp_CreateEventExW
0x14001e532  mov     [rbx+38h], rax
0x14001e536  test    rax, rax
0x14001e539  jnz     short loc_14001E56C
0x14001e53b  call    cs:__imp_GetLastError
0x14001e541  mov     esi, eax
0x14001e543  test    eax, eax
0x14001e545  jle     short loc_14001E550
0x14001e547  movzx   esi, ax
0x14001e54a  or      esi, 80070000h
0x14001e550  mov     rax, [rbx]
0x14001e553  test    esi, esi
0x14001e555  jns     short loc_14001E56F
0x14001e557  mov     rcx, rbx
0x14001e55a  mov     rax, [rax+10h]
0x14001e55e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e563  nop
0x14001e564  mov     [rbp+arg_8], esi
0x14001e567  jmp     loc_14001E6C1
0x14001e56c  mov     rax, [rbx]
0x14001e56f  mov     rcx, rbx
0x14001e572  mov     rax, [rax+8]
0x14001e576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e57b  nop
0x14001e57c  mov     [rbp+var_20], rbx
0x14001e580  mov     rax, [rbx]
0x14001e583  mov     rcx, rbx
0x14001e586  mov     rax, [rax+10h]
0x14001e58a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e58f  nop
0x14001e590  mov     [rbp+arg_8], 0
0x14001e597  mov     rax, [rdi]
0x14001e59a  mov     rdx, [rbp+var_20]
0x14001e59e  mov     rcx, rdi
0x14001e5a1  mov     rax, [rax+30h]
0x14001e5a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e5aa  mov     [rbp+arg_8], eax
0x14001e5ad  test    eax, eax
0x14001e5af  js      loc_14001E6C1
0x14001e5b5  mov     rax, [rbp+var_20]
0x14001e5b9  mov     rcx, [rax+38h]
0x14001e5bd  mov     [rbp+pHandles], rcx
0x14001e5c1  mov     [rbp+var_8], r14
0x14001e5c5  xor     bl, bl
0x14001e5c7  mov     [rbp+dwindex], 0
0x14001e5ce  neg     r14
0x14001e5d1  sbb     r8d, r8d
0x14001e5d4  neg     r8d
0x14001e5d7  inc     r8d; cHandles
0x14001e5da  lea     rax, [rbp+dwindex]
0x14001e5de  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x14001e5e3  lea     r9, [rbp+pHandles]; pHandles
0x14001e5e7  or      edx, 0FFFFFFFFh; dwTimeout
0x14001e5ea  mov     ecx, 8; dwFlags
0x14001e5ef  call    cs:__imp_CoWaitForMultipleHandles
0x14001e5f5  mov     [rbp+arg_8], eax
0x14001e5f8  test    eax, eax
0x14001e5fa  js      short loc_14001E60B
0x14001e5fc  cmp     [rbp+dwindex], 0
0x14001e600  jz      short loc_14001E60B
0x14001e602  mov     [rbp+arg_8], 800704C7h
0x14001e609  mov     bl, 1
0x14001e60b  mov     [rbp+arg_18], 0
0x14001e613  test    bl, bl
0x14001e615  jz      short loc_14001E64F
0x14001e617  mov     rax, [rdi]
0x14001e61a  mov     rbx, [rax]
0x14001e61d  lea     rcx, [rbp+arg_18]
0x14001e621  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ITaskService>>)
0x14001e626  mov     r8, rax
0x14001e629  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x14001e630  mov     rcx, rdi
0x14001e633  mov     rax, rbx
0x14001e636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e63b  test    eax, eax
0x14001e63d  js      short loc_14001E64F
0x14001e63f  mov     rcx, [rbp+arg_18]
0x14001e643  mov     rax, [rcx]
0x14001e646  mov     rax, [rax+48h]
0x14001e64a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e64f  cmp     [rbp+arg_8], 0
0x14001e653  jl      short loc_14001E6A3
0x14001e655  mov     rax, [rbp+var_20]
0x14001e659  cmp     dword ptr [rax+30h], 1
0x14001e65d  jz      short loc_14001E6A3
0x14001e65f  cmp     [rbp+arg_18], 0
0x14001e664  jnz     short loc_14001E68E
0x14001e666  mov     rax, [rdi]
0x14001e669  mov     rbx, [rax]
0x14001e66c  lea     rcx, [rbp+arg_18]
0x14001e670  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ITaskService>>)
0x14001e675  mov     r8, rax
0x14001e678  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x14001e67f  mov     rcx, rdi
0x14001e682  mov     rax, rbx
0x14001e685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e68a  test    eax, eax
0x14001e68c  js      short loc_14001E6A3
0x14001e68e  mov     rcx, [rbp+arg_18]
0x14001e692  mov     rax, [rcx]
0x14001e695  lea     rdx, [rbp+arg_8]
0x14001e699  mov     rax, [rax+40h]
0x14001e69d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e6a2  nop
0x14001e6a3  mov     rcx, [rbp+arg_18]
0x14001e6a7  test    rcx, rcx
0x14001e6aa  jz      short loc_14001E6C1
0x14001e6ac  mov     [rbp+arg_18], 0
0x14001e6b4  mov     rax, [rcx]
0x14001e6b7  mov     rax, [rax+10h]
0x14001e6bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e6c0  nop
0x14001e6c1  mov     ebx, [rbp+arg_8]
0x14001e6c4  mov     rcx, [rbp+var_20]
0x14001e6c8  test    rcx, rcx
0x14001e6cb  jz      short loc_14001E6E2
0x14001e6cd  mov     [rbp+var_20], 0
0x14001e6d5  mov     rax, [rcx]
0x14001e6d8  mov     rax, [rax+10h]
0x14001e6dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e6e1  nop
0x14001e6e2  test    rdi, rdi
0x14001e6e5  jz      short loc_14001E6F7
0x14001e6e7  mov     rcx, [rdi]
0x14001e6ea  mov     rax, [rcx+10h]
0x14001e6ee  mov     rcx, rdi
0x14001e6f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e6f6  nop
0x14001e6f7  mov     eax, ebx
0x14001e6f9  add     rsp, 50h
0x14001e6fd  pop     r14
0x14001e6ff  pop     rdi
0x14001e700  pop     rsi
0x14001e701  pop     rbx
0x14001e702  pop     rbp
0x14001e703  retn
```
