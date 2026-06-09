# WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *,ulong)

- ea: `0x1800393f8`
- end: `0x180039693`
- name: `??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z`
- size: `667`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), DWORD, __int64, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180043f90`

## callees

- `0x18000d7a0`
- `0x18002de7c`
- `0x1800317f8`
- `0x1800393f8`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800394c1`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800394c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800394d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800394d0`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180039575`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180039575`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        DWORD a2,
        __int64 a3,
        int a4)
{
  char *v5; // rax
  char *v6; // rbx
  _QWORD *v7; // rsi
  HANDLE Event; // rax
  signed int LastError; // eax
  signed int v10; // esi
  __int64 v11; // rax
  HRESULT v12; // ecx
  char v13; // al
  int (__fastcall *v14)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v15; // rax
  int (__fastcall *v16)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v17; // rax
  __int64 v18; // rcx
  unsigned int v19; // ebx
  HANDLE pHandles[3]; // [rsp+38h] [rbp-18h] BYREF
  char *v22; // [rsp+80h] [rbp+30h]
  DWORD dwindex; // [rsp+88h] [rbp+38h] BYREF
  __int64 v24; // [rsp+90h] [rbp+40h] BYREF
  int v25; // [rsp+98h] [rbp+48h] BYREF

  v25 = a4;
  v24 = a3;
  dwindex = a2;
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[1])(a1);
  v22 = 0;
  v5 = (char *)operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  v6 = v5;
  if ( !v5 )
  {
    v25 = -2147024882;
    goto LABEL_30;
  }
  v7 = v5 + 8;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(v5 + 8);
  *((_DWORD *)v6 + 11) = 1;
  *(_QWORD *)v6 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'};
  *v7 = `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v6 = `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
  *v7 = `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
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
      v25 = v10;
      goto LABEL_30;
    }
  }
  (*(void (__fastcall **)(char *))(v11 + 8))(v6);
  v22 = v6;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
  v25 = 0;
  v25 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), char *))(*a1)[6])(a1, v6);
  if ( v25 >= 0 )
  {
    pHandles[0] = *((HANDLE *)v6 + 7);
    pHandles[1] = 0;
    dwindex = 0;
    v12 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, pHandles, &dwindex);
    v25 = v12;
    if ( v12 >= 0 && dwindex )
    {
      v25 = -2147023673;
    }
    else
    {
      v13 = 0;
      if ( v12 != -2147417835 )
        goto LABEL_20;
      v25 = -2147023436;
    }
    v13 = 1;
LABEL_20:
    v24 = 0;
    if ( v13 )
    {
      v14 = **a1;
      v15 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(&v24);
      if ( v14(a1, &GUID_00000036_0000_0000_c000_000000000046, v15) >= 0 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 72LL))(v24);
    }
    if ( v25 >= 0 && *((_DWORD *)v22 + 12) != 1 )
    {
      if ( v24
        || (v16 = **a1,
            v17 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(&v24),
            v16(a1, &GUID_00000036_0000_0000_c000_000000000046, v17) >= 0) )
      {
        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v24 + 64LL))(v24, &v25);
      }
    }
    v18 = v24;
    if ( v24 )
    {
      v24 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
  }
LABEL_30:
  v19 = v25;
  if ( v22 )
    (*(void (__fastcall **)(char *))(*(_QWORD *)v22 + 16LL))(v22);
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[2])(a1);
  return v19;
}

```

## disassembly

```asm
0x1800393f8  mov     [rsp-28h+arg_18], r9d
0x1800393fd  mov     [rsp-28h+arg_10], r8
0x180039402  mov     [rsp-28h+dwindex], edx
0x180039406  push    rbp
0x180039407  push    rbx
0x180039408  push    rsi
0x180039409  push    rdi
0x18003940a  push    r14
0x18003940c  mov     rbp, rsp
0x18003940f  sub     rsp, 50h
0x180039413  mov     rdi, rcx
0x180039416  mov     [rbp+var_20], rcx
0x18003941a  xor     r14d, r14d
0x18003941d  test    rcx, rcx
0x180039420  jz      short loc_18003942F
0x180039422  mov     rax, [rcx]
0x180039425  mov     rax, [rax+8]
0x180039429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003942e  nop
0x18003942f  mov     [rbp+arg_0], r14
0x180039433  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003943a  mov     ecx, 40h ; '@'; unsigned __int64
0x18003943f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180039444  mov     rbx, rax
0x180039447  test    rax, rax
0x18003944a  jnz     short loc_180039458
0x18003944c  mov     [rbp+arg_18], 8007000Eh
0x180039453  jmp     loc_180039654
0x180039458  lea     rsi, [rax+8]
0x18003945c  mov     rcx, rsi
0x18003945f  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x180039464  mov     dword ptr [rbx+2Ch], 1
0x18003946b  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAsyncActionCompletedHandler@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6BIAsyncActionCompletedHandler@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x180039472  mov     [rbx], rax
0x180039475  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18003947c  mov     [rsi], rax
0x18003947f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180039486  test    rcx, rcx
0x180039489  jz      short loc_180039498
0x18003948b  mov     rax, [rcx]
0x18003948e  mov     rax, [rax+8]
0x180039492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039497  nop
0x180039498  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6BIAsyncActionCompletedHandler@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x18003949f  mov     [rbx], rax
0x1800394a2  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800394a9  mov     [rsi], rax
0x1800394ac  mov     [rbx+30h], r14d
0x1800394b0  mov     [rbx+38h], r14
0x1800394b4  mov     r9d, 1F0003h; dwDesiredAccess
0x1800394ba  xor     r8d, r8d; dwFlags
0x1800394bd  xor     edx, edx; lpName
0x1800394bf  xor     ecx, ecx; lpEventAttributes
0x1800394c1  call    cs:__imp_CreateEventExW
0x1800394c7  mov     [rbx+38h], rax
0x1800394cb  test    rax, rax
0x1800394ce  jnz     short loc_180039501
0x1800394d0  call    cs:__imp_GetLastError
0x1800394d6  mov     esi, eax
0x1800394d8  test    eax, eax
0x1800394da  jle     short loc_1800394E5
0x1800394dc  movzx   esi, ax
0x1800394df  or      esi, 80070000h
0x1800394e5  mov     rax, [rbx]
0x1800394e8  test    esi, esi
0x1800394ea  jns     short loc_180039504
0x1800394ec  mov     rcx, rbx
0x1800394ef  mov     rax, [rax+10h]
0x1800394f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800394f8  nop
0x1800394f9  mov     [rbp+arg_18], esi
0x1800394fc  jmp     loc_180039654
0x180039501  mov     rax, [rbx]
0x180039504  mov     rcx, rbx
0x180039507  mov     rax, [rax+8]
0x18003950b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039510  nop
0x180039511  mov     [rbp+arg_0], rbx
0x180039515  mov     rax, [rbx]
0x180039518  mov     rcx, rbx
0x18003951b  mov     rax, [rax+10h]
0x18003951f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039524  nop
0x180039525  mov     [rbp+arg_18], r14d
0x180039529  mov     rax, [rdi]
0x18003952c  mov     rdx, [rbp+arg_0]
0x180039530  mov     rcx, rdi
0x180039533  mov     rax, [rax+30h]
0x180039537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003953c  mov     [rbp+arg_18], eax
0x18003953f  test    eax, eax
0x180039541  js      loc_180039654
0x180039547  mov     rax, [rbp+arg_0]
0x18003954b  mov     rcx, [rax+38h]
0x18003954f  mov     [rbp+pHandles], rcx
0x180039553  mov     [rbp+var_10], r14
0x180039557  mov     [rbp+dwindex], r14d
0x18003955b  lea     rax, [rbp+dwindex]
0x18003955f  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x180039564  lea     r9, [rbp+pHandles]; pHandles
0x180039568  mov     r8d, 1; cHandles
0x18003956e  or      edx, 0FFFFFFFFh; dwTimeout
0x180039571  lea     ecx, [r8+7]; dwFlags
0x180039575  call    cs:__imp_CoWaitForMultipleHandles
0x18003957b  mov     ecx, eax
0x18003957d  mov     [rbp+arg_18], eax
0x180039580  test    eax, eax
0x180039582  js      short loc_180039593
0x180039584  cmp     [rbp+dwindex], r14d
0x180039588  jz      short loc_180039593
0x18003958a  mov     [rbp+arg_18], 800704C7h
0x180039591  jmp     short loc_1800395A5
0x180039593  mov     al, r14b
0x180039596  cmp     ecx, 80010115h
0x18003959c  jnz     short loc_1800395A7
0x18003959e  mov     [rbp+arg_18], 800705B4h
0x1800395a5  mov     al, 1
0x1800395a7  mov     [rbp+arg_10], r14
0x1800395ab  test    al, al
0x1800395ad  jz      short loc_1800395E7
0x1800395af  mov     rax, [rdi]
0x1800395b2  mov     rbx, [rax]
0x1800395b5  lea     rcx, [rbp+arg_10]
0x1800395b9  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x1800395be  mov     r8, rax
0x1800395c1  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x1800395c8  mov     rcx, rdi
0x1800395cb  mov     rax, rbx
0x1800395ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800395d3  test    eax, eax
0x1800395d5  js      short loc_1800395E7
0x1800395d7  mov     rcx, [rbp+arg_10]
0x1800395db  mov     rax, [rcx]
0x1800395de  mov     rax, [rax+48h]
0x1800395e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800395e7  cmp     [rbp+arg_18], r14d
0x1800395eb  jl      short loc_18003963A
0x1800395ed  mov     rax, [rbp+arg_0]
0x1800395f1  cmp     dword ptr [rax+30h], 1
0x1800395f5  jz      short loc_18003963A
0x1800395f7  cmp     [rbp+arg_10], r14
0x1800395fb  jnz     short loc_180039625
0x1800395fd  mov     rax, [rdi]
0x180039600  mov     rbx, [rax]
0x180039603  lea     rcx, [rbp+arg_10]
0x180039607  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x18003960c  mov     r8, rax
0x18003960f  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180039616  mov     rcx, rdi
0x180039619  mov     rax, rbx
0x18003961c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039621  test    eax, eax
0x180039623  js      short loc_18003963A
0x180039625  mov     rcx, [rbp+arg_10]
0x180039629  mov     rax, [rcx]
0x18003962c  lea     rdx, [rbp+arg_18]
0x180039630  mov     rax, [rax+40h]
0x180039634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039639  nop
0x18003963a  mov     rcx, [rbp+arg_10]
0x18003963e  test    rcx, rcx
0x180039641  jz      short loc_180039654
0x180039643  mov     [rbp+arg_10], r14
0x180039647  mov     rax, [rcx]
0x18003964a  mov     rax, [rax+10h]
0x18003964e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039653  nop
0x180039654  mov     ebx, [rbp+arg_18]
0x180039657  mov     rcx, [rbp+arg_0]
0x18003965b  test    rcx, rcx
0x18003965e  jz      short loc_180039671
0x180039660  mov     [rbp+arg_0], r14
0x180039664  mov     rax, [rcx]
0x180039667  mov     rax, [rax+10h]
0x18003966b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039670  nop
0x180039671  test    rdi, rdi
0x180039674  jz      short loc_180039686
0x180039676  mov     rcx, [rdi]
0x180039679  mov     rax, [rcx+10h]
0x18003967d  mov     rcx, rdi
0x180039680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039685  nop
0x180039686  mov     eax, ebx
0x180039688  add     rsp, 50h
0x18003968c  pop     r14
0x18003968e  pop     rdi
0x18003968f  pop     rsi
0x180039690  pop     rbx
0x180039691  pop     rbp
0x180039692  retn
```
