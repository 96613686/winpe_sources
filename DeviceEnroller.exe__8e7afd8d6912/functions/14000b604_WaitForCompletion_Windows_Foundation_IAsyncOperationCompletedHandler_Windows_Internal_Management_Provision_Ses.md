# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x14000b604`
- end: `0x14000b844`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVSessionResult@Provision@Management@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `576`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), int, void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140012964`
- `0x140012c28`

## callees

- `0x140004314`
- `0x140005ea8`
- `0x140006e08`
- `0x14000b604`
- `0x140017e84`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x14000b6d8`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x14000b6d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b6e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b6e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *>>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        int a2,
        void **a3)
{
  _DWORD *v4; // rbx
  HANDLE Event; // rax
  signed int LastError; // eax
  signed int v7; // esi
  __int64 v8; // rax
  unsigned int v9; // r9d
  int (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v11; // rax
  __int64 v12; // rcx
  unsigned int v13; // ebx
  void **v14; // rcx
  unsigned int v16; // [rsp+20h] [rbp-28h]
  unsigned int v17; // [rsp+28h] [rbp-20h]
  void *v18[3]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v19; // [rsp+70h] [rbp+28h] BYREF
  int v20; // [rsp+78h] [rbp+30h] BYREF
  void **v21; // [rsp+80h] [rbp+38h]
  int (__fastcall ***v22)(_QWORD, _QWORD, _QWORD); // [rsp+88h] [rbp+40h]

  v21 = a3;
  v20 = a2;
  v22 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))a1;
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[1])(a1);
  v21 = 0;
  v4 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
  {
    v20 = -2147024882;
    goto LABEL_22;
  }
  *(_QWORD *)v4 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>::`vftable';
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(v4 + 2);
  v4[11] = 1;
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>'};
  *((_QWORD *)v4 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *>>'::`2'::FTMEventDelegate::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v4 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *>>'::`2'::FTMEventDelegate::`vftable';
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
      goto LABEL_22;
    }
  }
  (*(void (__fastcall **)(_DWORD *))(v8 + 8))(v4);
  v21 = (void **)v4;
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v4 + 16LL))(v4);
  v20 = 0;
  v20 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), void **))(*a1)[6])(a1, v21);
  if ( v20 >= 0 )
  {
    v18[0] = v21[7];
    v18[1] = 0;
    if ( SHProcessMessagesUntilEventsEx((HWND)v18[0], v18, 1u, v9, v16, v17) == -1 )
      v20 = -2147467259;
    v19 = 0;
    if ( v20 >= 0 && *((_DWORD *)v21 + 12) != 1 )
    {
      v10 = **a1;
      v11 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>(&v19);
      if ( v10(a1, &GUID_00000036_0000_0000_c000_000000000046, v11) >= 0 )
        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v19 + 64LL))(v19, &v20);
    }
    v12 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
  }
LABEL_22:
  v13 = v20;
  v14 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*((void (__fastcall **)(void **))*v14 + 2))(v14);
  }
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[2])(a1);
  return v13;
}

```

## disassembly

```asm
0x14000b604  mov     [rsp-20h+arg_10], r8
0x14000b609  mov     [rsp-20h+arg_8], edx
0x14000b60d  push    rbp
0x14000b60e  push    rbx
0x14000b60f  push    rsi
0x14000b610  push    rdi
0x14000b611  mov     rbp, rsp
0x14000b614  sub     rsp, 48h
0x14000b618  mov     rdi, rcx
0x14000b61b  mov     [rbp+arg_18], rcx
0x14000b61f  test    rcx, rcx
0x14000b622  jz      short loc_14000B631
0x14000b624  mov     rax, [rcx]
0x14000b627  mov     rax, [rax+8]
0x14000b62b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b630  nop
0x14000b631  mov     [rbp+arg_10], 0
0x14000b639  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000b640  mov     ecx, 40h ; '@'; unsigned __int64
0x14000b645  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000b64a  mov     rbx, rax
0x14000b64d  test    rax, rax
0x14000b650  jnz     short loc_14000B65E
0x14000b652  mov     [rbp+arg_8], 8007000Eh
0x14000b659  jmp     loc_14000B803
0x14000b65e  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>::`vftable'
0x14000b665  mov     [rbx], rax
0x14000b668  lea     rsi, [rbx+8]
0x14000b66c  mov     rcx, rsi
0x14000b66f  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x14000b674  mov     dword ptr [rbx+2Ch], 1
0x14000b67b  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>'}
0x14000b682  mov     [rbx], rax
0x14000b685  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVSessionResult@Provision@Management@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x14000b68c  mov     [rsi], rax
0x14000b68f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14000b696  test    rcx, rcx
0x14000b699  jz      short loc_14000B6A8
0x14000b69b  mov     rax, [rcx]
0x14000b69e  mov     rax, [rax+8]
0x14000b6a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b6a7  nop
0x14000b6a8  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVSessionResult@Provision@Management@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVSessionResult@Provision@Management@Internal@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>'}
0x14000b6af  mov     [rbx], rax
0x14000b6b2  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVSessionResult@Provision@Management@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x14000b6b9  mov     [rsi], rax
0x14000b6bc  mov     dword ptr [rbx+30h], 0
0x14000b6c3  mov     qword ptr [rbx+38h], 0
0x14000b6cb  mov     r9d, 1F0003h; dwDesiredAccess
0x14000b6d1  xor     r8d, r8d; dwFlags
0x14000b6d4  xor     edx, edx; lpName
0x14000b6d6  xor     ecx, ecx; lpEventAttributes
0x14000b6d8  call    cs:__imp_CreateEventExW
0x14000b6de  mov     [rbx+38h], rax
0x14000b6e2  test    rax, rax
0x14000b6e5  jnz     short loc_14000B718
0x14000b6e7  call    cs:__imp_GetLastError
0x14000b6ed  mov     esi, eax
0x14000b6ef  test    eax, eax
0x14000b6f1  jle     short loc_14000B6FC
0x14000b6f3  movzx   esi, ax
0x14000b6f6  or      esi, 80070000h
0x14000b6fc  mov     rax, [rbx]
0x14000b6ff  test    esi, esi
0x14000b701  jns     short loc_14000B71B
0x14000b703  mov     rcx, rbx
0x14000b706  mov     rax, [rax+10h]
0x14000b70a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b70f  nop
0x14000b710  mov     [rbp+arg_8], esi
0x14000b713  jmp     loc_14000B803
0x14000b718  mov     rax, [rbx]
0x14000b71b  mov     rcx, rbx
0x14000b71e  mov     rax, [rax+8]
0x14000b722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b727  nop
0x14000b728  mov     [rbp+arg_10], rbx
0x14000b72c  mov     rax, [rbx]
0x14000b72f  mov     rcx, rbx
0x14000b732  mov     rax, [rax+10h]
0x14000b736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b73b  nop
0x14000b73c  mov     [rbp+arg_8], 0
0x14000b743  mov     rax, [rdi]
0x14000b746  mov     rdx, [rbp+arg_10]
0x14000b74a  mov     rcx, rdi
0x14000b74d  mov     rax, [rax+30h]
0x14000b751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b756  mov     [rbp+arg_8], eax
0x14000b759  test    eax, eax
0x14000b75b  js      loc_14000B803
0x14000b761  mov     rax, [rbp+arg_10]
0x14000b765  mov     rcx, [rax+38h]; HWND
0x14000b769  mov     [rbp+var_18], rcx
0x14000b76d  mov     [rbp+var_10], 0
0x14000b775  mov     r8d, 1; unsigned int
0x14000b77b  lea     rdx, [rbp+var_18]; void **
0x14000b77f  call    ?SHProcessMessagesUntilEventsEx@@YAKPEAUHWND__@@PEAPEAXKKKK@Z; SHProcessMessagesUntilEventsEx(HWND__ *,void * *,ulong,ulong,ulong,ulong)
0x14000b784  cmp     eax, 0FFFFFFFFh
0x14000b787  jnz     short loc_14000B790
0x14000b789  mov     [rbp+arg_8], 80004005h
0x14000b790  mov     [rbp+arg_0], 0
0x14000b798  cmp     [rbp+arg_8], 0
0x14000b79c  jl      short loc_14000B7E5
0x14000b79e  mov     rax, [rbp+arg_10]
0x14000b7a2  cmp     dword ptr [rax+30h], 1
0x14000b7a6  jz      short loc_14000B7E5
0x14000b7a8  mov     rax, [rdi]
0x14000b7ab  mov     rbx, [rax]
0x14000b7ae  lea     rcx, [rbp+arg_0]
0x14000b7b2  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ITaskService>>)
0x14000b7b7  mov     r8, rax
0x14000b7ba  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x14000b7c1  mov     rcx, rdi
0x14000b7c4  mov     rax, rbx
0x14000b7c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b7cc  test    eax, eax
0x14000b7ce  js      short loc_14000B7E5
0x14000b7d0  mov     rcx, [rbp+arg_0]
0x14000b7d4  mov     rax, [rcx]
0x14000b7d7  lea     rdx, [rbp+arg_8]
0x14000b7db  mov     rax, [rax+40h]
0x14000b7df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b7e4  nop
0x14000b7e5  mov     rcx, [rbp+arg_0]
0x14000b7e9  test    rcx, rcx
0x14000b7ec  jz      short loc_14000B803
0x14000b7ee  mov     [rbp+arg_0], 0
0x14000b7f6  mov     rax, [rcx]
0x14000b7f9  mov     rax, [rax+10h]
0x14000b7fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b802  nop
0x14000b803  mov     ebx, [rbp+arg_8]
0x14000b806  mov     rcx, [rbp+arg_10]
0x14000b80a  test    rcx, rcx
0x14000b80d  jz      short loc_14000B824
0x14000b80f  mov     [rbp+arg_10], 0
0x14000b817  mov     rax, [rcx]
0x14000b81a  mov     rax, [rax+10h]
0x14000b81e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b823  nop
0x14000b824  test    rdi, rdi
0x14000b827  jz      short loc_14000B839
0x14000b829  mov     rcx, [rdi]
0x14000b82c  mov     rax, [rcx+10h]
0x14000b830  mov     rcx, rdi
0x14000b833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b838  nop
0x14000b839  mov     eax, ebx
0x14000b83b  add     rsp, 48h
0x14000b83f  pop     rdi
0x14000b840  pop     rsi
0x14000b841  pop     rbx
0x14000b842  pop     rbp
0x14000b843  retn
```
