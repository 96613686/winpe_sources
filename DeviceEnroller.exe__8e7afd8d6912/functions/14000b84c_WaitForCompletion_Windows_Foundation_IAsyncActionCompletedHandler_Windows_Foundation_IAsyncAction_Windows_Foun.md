# WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)

- ea: `0x14000b84c`
- end: `0x14000bb0a`
- name: `??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `702`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), DWORD, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140019a6c`
- `0x1400337d8`

## callees

- `0x140004314`
- `0x140005ea8`
- `0x140006e08`
- `0x14000b84c`
- `0x140017e84`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x14000b915`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x14000b915`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b924`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b924`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x14000b9f9`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x14000b9f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        DWORD a2,
        __int64 a3)
{
  char *v5; // rax
  char *v6; // rbx
  _QWORD *v7; // rsi
  HANDLE Event; // rax
  signed int LastError; // eax
  signed int v10; // esi
  __int64 v11; // rax
  unsigned int v12; // r9d
  HWND v13; // rcx
  char v14; // bl
  int (__fastcall *v15)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v16; // rax
  int (__fastcall *v17)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v18; // rax
  __int64 v19; // rcx
  unsigned int v20; // ebx
  unsigned int lpdwindex; // [rsp+20h] [rbp-30h]
  unsigned int v23; // [rsp+28h] [rbp-28h]
  char *v24; // [rsp+30h] [rbp-20h]
  HANDLE pHandles[2]; // [rsp+40h] [rbp-10h] BYREF
  DWORD dwindex; // [rsp+80h] [rbp+30h] BYREF
  __int64 v27; // [rsp+90h] [rbp+40h] BYREF
  __int64 v28; // [rsp+98h] [rbp+48h] BYREF

  v27 = a3;
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[1])(a1);
  v24 = 0;
  v5 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  if ( !v5 )
  {
    LODWORD(v27) = -2147024882;
    goto LABEL_32;
  }
  v7 = v5 + 8;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(v5 + 8);
  *((_DWORD *)v6 + 11) = 1;
  *(_QWORD *)v6 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'};
  *v7 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>'::`2'::CompletionDelegate::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v6 = `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
  *v7 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>'::`2'::CompletionDelegate::`vftable';
  *((_DWORD *)v6 + 12) = 0;
  *((_QWORD *)v6 + 7) = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  *((_QWORD *)v6 + 7) = Event;
  if ( Event )
  {
    v11 = *(_QWORD *)v6;
  }
  else
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    v11 = *(_QWORD *)v6;
    if ( v10 < 0 )
    {
      (*(void (__fastcall **)(char *))(v11 + 16))(v6);
      LODWORD(v27) = v10;
      goto LABEL_32;
    }
  }
  (*(void (__fastcall **)(char *))(v11 + 8))(v6);
  v24 = v6;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
  LODWORD(v27) = 0;
  LODWORD(v27) = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), char *))(*a1)[6])(a1, v6);
  if ( (int)v27 >= 0 )
  {
    v13 = (HWND)*((_QWORD *)v6 + 7);
    pHandles[0] = v13;
    pHandles[1] = 0;
    v14 = 0;
    if ( a2 == -1 && SHProcessMessagesUntilEventsEx(v13, pHandles, 1u, v12, lpdwindex, v23) == -1 )
    {
      LODWORD(v27) = -2147467259;
    }
    else if ( (int)v27 >= 0 && a2 != -1 )
    {
      dwindex = 0;
      LODWORD(v27) = CoWaitForMultipleHandles(a2, 0xFFFFFFFF, 1u, pHandles, &dwindex);
      if ( (int)v27 >= 0 )
      {
        if ( dwindex )
        {
          LODWORD(v27) = -2147023673;
          v14 = 1;
        }
      }
    }
    v28 = 0;
    if ( v14 )
    {
      v15 = **a1;
      v16 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>(&v28);
      if ( v15(a1, &GUID_00000036_0000_0000_c000_000000000046, v16) >= 0 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 72LL))(v28);
    }
    if ( (int)v27 >= 0 && *((_DWORD *)v24 + 12) != 1 )
    {
      if ( v28
        || (v17 = **a1,
            v18 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>(&v28),
            v17(a1, &GUID_00000036_0000_0000_c000_000000000046, v18) >= 0) )
      {
        (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v28 + 64LL))(v28, &v27);
      }
    }
    v19 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
  }
LABEL_32:
  v20 = v27;
  if ( v24 )
    (*(void (__fastcall **)(char *))(*(_QWORD *)v24 + 16LL))(v24);
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[2])(a1);
  return v20;
}

```

## disassembly

```asm
0x14000b84c  mov     [rsp-28h+arg_8], rbx
0x14000b851  mov     [rsp-28h+arg_10], r8
0x14000b856  push    rbp
0x14000b857  push    rsi
0x14000b858  push    rdi
0x14000b859  push    r14
0x14000b85b  push    r15
0x14000b85d  mov     rbp, rsp
0x14000b860  sub     rsp, 50h
0x14000b864  mov     r14d, edx
0x14000b867  mov     rdi, rcx
0x14000b86a  mov     [rbp+var_18], rcx
0x14000b86e  xor     r15d, r15d
0x14000b871  test    rcx, rcx
0x14000b874  jz      short loc_14000B883
0x14000b876  mov     rax, [rcx]
0x14000b879  mov     rax, [rax+8]
0x14000b87d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b882  nop
0x14000b883  mov     [rbp+var_20], r15
0x14000b887  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000b88e  mov     ecx, 40h ; '@'; unsigned __int64
0x14000b893  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000b898  mov     rbx, rax
0x14000b89b  test    rax, rax
0x14000b89e  jnz     short loc_14000B8AC
0x14000b8a0  mov     dword ptr [rbp+arg_10], 8007000Eh
0x14000b8a7  jmp     loc_14000BAC2
0x14000b8ac  lea     rsi, [rax+8]
0x14000b8b0  mov     rcx, rsi
0x14000b8b3  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x14000b8b8  mov     dword ptr [rbx+2Ch], 1
0x14000b8bf  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAsyncActionCompletedHandler@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6BIAsyncActionCompletedHandler@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x14000b8c6  mov     [rbx], rax
0x14000b8c9  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x14000b8d0  mov     [rsi], rax
0x14000b8d3  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14000b8da  test    rcx, rcx
0x14000b8dd  jz      short loc_14000B8EC
0x14000b8df  mov     rax, [rcx]
0x14000b8e2  mov     rax, [rax+8]
0x14000b8e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b8eb  nop
0x14000b8ec  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6BIAsyncActionCompletedHandler@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x14000b8f3  mov     [rbx], rax
0x14000b8f6  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x14000b8fd  mov     [rsi], rax
0x14000b900  mov     [rbx+30h], r15d
0x14000b904  mov     [rbx+38h], r15
0x14000b908  mov     r9d, 1F0003h; dwDesiredAccess
0x14000b90e  xor     r8d, r8d; dwFlags
0x14000b911  xor     edx, edx; lpName
0x14000b913  xor     ecx, ecx; lpEventAttributes
0x14000b915  call    cs:__imp_CreateEventExW
0x14000b91b  mov     [rbx+38h], rax
0x14000b91f  test    rax, rax
0x14000b922  jnz     short loc_14000B955
0x14000b924  call    cs:__imp_GetLastError
0x14000b92a  mov     esi, eax
0x14000b92c  test    eax, eax
0x14000b92e  jle     short loc_14000B939
0x14000b930  movzx   esi, ax
0x14000b933  or      esi, 80070000h
0x14000b939  mov     rax, [rbx]
0x14000b93c  test    esi, esi
0x14000b93e  jns     short loc_14000B958
0x14000b940  mov     rcx, rbx
0x14000b943  mov     rax, [rax+10h]
0x14000b947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b94c  nop
0x14000b94d  mov     dword ptr [rbp+arg_10], esi
0x14000b950  jmp     loc_14000BAC2
0x14000b955  mov     rax, [rbx]
0x14000b958  mov     rcx, rbx
0x14000b95b  mov     rax, [rax+8]
0x14000b95f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b964  nop
0x14000b965  mov     [rbp+var_20], rbx
0x14000b969  mov     rax, [rbx]
0x14000b96c  mov     rcx, rbx
0x14000b96f  mov     rax, [rax+10h]
0x14000b973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b978  nop
0x14000b979  mov     dword ptr [rbp+arg_10], r15d
0x14000b97d  mov     rax, [rdi]
0x14000b980  mov     rdx, [rbp+var_20]
0x14000b984  mov     rcx, rdi
0x14000b987  mov     rax, [rax+30h]
0x14000b98b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b990  mov     dword ptr [rbp+arg_10], eax
0x14000b993  test    eax, eax
0x14000b995  js      loc_14000BAC2
0x14000b99b  mov     rax, [rbp+var_20]
0x14000b99f  mov     rcx, [rax+38h]; HWND
0x14000b9a3  mov     [rbp+pHandles], rcx
0x14000b9a7  mov     [rbp+var_8], r15
0x14000b9ab  mov     bl, r15b
0x14000b9ae  or      esi, 0FFFFFFFFh
0x14000b9b1  cmp     r14d, 0FFFFFFFFh
0x14000b9b5  jnz     short loc_14000B9D1
0x14000b9b7  lea     r8d, [r14+2]; unsigned int
0x14000b9bb  lea     rdx, [rbp+pHandles]; void **
0x14000b9bf  call    ?SHProcessMessagesUntilEventsEx@@YAKPEAUHWND__@@PEAPEAXKKKK@Z; SHProcessMessagesUntilEventsEx(HWND__ *,void * *,ulong,ulong,ulong,ulong)
0x14000b9c4  cmp     eax, esi
0x14000b9c6  jnz     short loc_14000B9D1
0x14000b9c8  mov     dword ptr [rbp+arg_10], 80004005h
0x14000b9cf  jmp     short loc_14000BA15
0x14000b9d1  cmp     dword ptr [rbp+arg_10], r15d
0x14000b9d5  jl      short loc_14000BA15
0x14000b9d7  cmp     r14d, 0FFFFFFFFh
0x14000b9db  jz      short loc_14000BA15
0x14000b9dd  mov     [rbp+dwindex], r15d
0x14000b9e1  lea     rax, [rbp+dwindex]
0x14000b9e5  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x14000b9ea  lea     r9, [rbp+pHandles]; pHandles
0x14000b9ee  mov     r8d, 1; cHandles
0x14000b9f4  mov     edx, esi; dwTimeout
0x14000b9f6  mov     ecx, r14d; dwFlags
0x14000b9f9  call    cs:__imp_CoWaitForMultipleHandles
0x14000b9ff  mov     dword ptr [rbp+arg_10], eax
0x14000ba02  test    eax, eax
0x14000ba04  js      short loc_14000BA15
0x14000ba06  cmp     [rbp+dwindex], r15d
0x14000ba0a  jz      short loc_14000BA15
0x14000ba0c  mov     dword ptr [rbp+arg_10], 800704C7h
0x14000ba13  mov     bl, 1
0x14000ba15  mov     [rbp+arg_18], r15
0x14000ba19  test    bl, bl
0x14000ba1b  jz      short loc_14000BA55
0x14000ba1d  mov     rax, [rdi]
0x14000ba20  mov     rbx, [rax]
0x14000ba23  lea     rcx, [rbp+arg_18]
0x14000ba27  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ITaskService>>)
0x14000ba2c  mov     r8, rax
0x14000ba2f  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x14000ba36  mov     rcx, rdi
0x14000ba39  mov     rax, rbx
0x14000ba3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ba41  test    eax, eax
0x14000ba43  js      short loc_14000BA55
0x14000ba45  mov     rcx, [rbp+arg_18]
0x14000ba49  mov     rax, [rcx]
0x14000ba4c  mov     rax, [rax+48h]
0x14000ba50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ba55  cmp     dword ptr [rbp+arg_10], r15d
0x14000ba59  jl      short loc_14000BAA8
0x14000ba5b  mov     rax, [rbp+var_20]
0x14000ba5f  cmp     dword ptr [rax+30h], 1
0x14000ba63  jz      short loc_14000BAA8
0x14000ba65  cmp     [rbp+arg_18], r15
0x14000ba69  jnz     short loc_14000BA93
0x14000ba6b  mov     rax, [rdi]
0x14000ba6e  mov     rbx, [rax]
0x14000ba71  lea     rcx, [rbp+arg_18]
0x14000ba75  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ITaskService>>)
0x14000ba7a  mov     r8, rax
0x14000ba7d  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x14000ba84  mov     rcx, rdi
0x14000ba87  mov     rax, rbx
0x14000ba8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ba8f  test    eax, eax
0x14000ba91  js      short loc_14000BAA8
0x14000ba93  mov     rcx, [rbp+arg_18]
0x14000ba97  mov     rax, [rcx]
0x14000ba9a  lea     rdx, [rbp+arg_10]
0x14000ba9e  mov     rax, [rax+40h]
0x14000baa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000baa7  nop
0x14000baa8  mov     rcx, [rbp+arg_18]
0x14000baac  test    rcx, rcx
0x14000baaf  jz      short loc_14000BAC2
0x14000bab1  mov     [rbp+arg_18], r15
0x14000bab5  mov     rax, [rcx]
0x14000bab8  mov     rax, [rax+10h]
0x14000babc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bac1  nop
0x14000bac2  mov     ebx, dword ptr [rbp+arg_10]
0x14000bac5  mov     rcx, [rbp+var_20]
0x14000bac9  test    rcx, rcx
0x14000bacc  jz      short loc_14000BADF
0x14000bace  mov     [rbp+var_20], r15
0x14000bad2  mov     rax, [rcx]
0x14000bad5  mov     rax, [rax+10h]
0x14000bad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bade  nop
0x14000badf  test    rdi, rdi
0x14000bae2  jz      short loc_14000BAF4
0x14000bae4  mov     rcx, [rdi]
0x14000bae7  mov     rax, [rcx+10h]
0x14000baeb  mov     rcx, rdi
0x14000baee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000baf3  nop
0x14000baf4  mov     eax, ebx
0x14000baf6  mov     rbx, [rsp+50h+arg_8]
0x14000bafe  add     rsp, 50h
0x14000bb02  pop     r15
0x14000bb04  pop     r14
0x14000bb06  pop     rdi
0x14000bb07  pop     rsi
0x14000bb08  pop     rbp
0x14000bb09  retn
```
