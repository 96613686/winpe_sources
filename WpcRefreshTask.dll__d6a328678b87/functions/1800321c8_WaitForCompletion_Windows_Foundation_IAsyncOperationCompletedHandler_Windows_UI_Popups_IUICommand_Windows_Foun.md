# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *>>(Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x1800321c8`
- end: `0x180032408`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIUICommand@Popups@UI@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `576`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), int, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180033f08`

## callees

- `0x1800065c8`
- `0x180032194`
- `0x1800321c8`
- `0x180032410`
- `0x180033860`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800322ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800322ab`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18003229c`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18003229c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *>>(
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
  *(_QWORD *)v4 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>::`vftable';
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v4 + 2));
  v4[11] = 1;
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v4 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *>>'::`2'::FTMEventDelegate::`vftable';
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
      v11 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(&v19);
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
0x1800321c8  mov     [rsp-20h+arg_10], r8
0x1800321cd  mov     [rsp-20h+arg_8], edx
0x1800321d1  push    rbp
0x1800321d2  push    rbx
0x1800321d3  push    rsi
0x1800321d4  push    rdi
0x1800321d5  mov     rbp, rsp
0x1800321d8  sub     rsp, 48h
0x1800321dc  mov     rdi, rcx
0x1800321df  mov     [rbp+arg_18], rcx
0x1800321e3  test    rcx, rcx
0x1800321e6  jz      short loc_1800321F5
0x1800321e8  mov     rax, [rcx]
0x1800321eb  mov     rax, [rax+8]
0x1800321ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800321f4  nop
0x1800321f5  mov     [rbp+arg_10], 0
0x1800321fd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180032204  mov     ecx, 40h ; '@'; unsigned __int64
0x180032209  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003220e  mov     rbx, rax
0x180032211  test    rax, rax
0x180032214  jnz     short loc_180032222
0x180032216  mov     [rbp+arg_8], 8007000Eh
0x18003221d  jmp     loc_1800323C7
0x180032222  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>::`vftable'
0x180032229  mov     [rbx], rax
0x18003222c  lea     rsi, [rbx+8]
0x180032230  mov     rcx, rsi; this
0x180032233  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180032238  mov     dword ptr [rbx+2Ch], 1
0x18003223f  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>'}
0x180032246  mov     [rbx], rax
0x180032249  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180032250  mov     [rsi], rax
0x180032253  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18003225a  test    rcx, rcx
0x18003225d  jz      short loc_18003226C
0x18003225f  mov     rax, [rcx]
0x180032262  mov     rax, [rax+8]
0x180032266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003226b  nop
0x18003226c  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIUICommand@Popups@UI@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *>>(Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>'}
0x180032273  mov     [rbx], rax
0x180032276  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIUICommand@Popups@UI@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *>>(Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18003227d  mov     [rsi], rax
0x180032280  mov     dword ptr [rbx+30h], 0
0x180032287  mov     qword ptr [rbx+38h], 0
0x18003228f  mov     r9d, 1F0003h; dwDesiredAccess
0x180032295  xor     r8d, r8d; dwFlags
0x180032298  xor     edx, edx; lpName
0x18003229a  xor     ecx, ecx; lpEventAttributes
0x18003229c  call    cs:__imp_CreateEventExW
0x1800322a2  mov     [rbx+38h], rax
0x1800322a6  test    rax, rax
0x1800322a9  jnz     short loc_1800322DC
0x1800322ab  call    cs:__imp_GetLastError
0x1800322b1  mov     esi, eax
0x1800322b3  test    eax, eax
0x1800322b5  jle     short loc_1800322C0
0x1800322b7  movzx   esi, ax
0x1800322ba  or      esi, 80070000h
0x1800322c0  mov     rax, [rbx]
0x1800322c3  test    esi, esi
0x1800322c5  jns     short loc_1800322DF
0x1800322c7  mov     rcx, rbx
0x1800322ca  mov     rax, [rax+10h]
0x1800322ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800322d3  nop
0x1800322d4  mov     [rbp+arg_8], esi
0x1800322d7  jmp     loc_1800323C7
0x1800322dc  mov     rax, [rbx]
0x1800322df  mov     rcx, rbx
0x1800322e2  mov     rax, [rax+8]
0x1800322e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800322eb  nop
0x1800322ec  mov     [rbp+arg_10], rbx
0x1800322f0  mov     rax, [rbx]
0x1800322f3  mov     rcx, rbx
0x1800322f6  mov     rax, [rax+10h]
0x1800322fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800322ff  nop
0x180032300  mov     [rbp+arg_8], 0
0x180032307  mov     rax, [rdi]
0x18003230a  mov     rdx, [rbp+arg_10]
0x18003230e  mov     rcx, rdi
0x180032311  mov     rax, [rax+30h]
0x180032315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003231a  mov     [rbp+arg_8], eax
0x18003231d  test    eax, eax
0x18003231f  js      loc_1800323C7
0x180032325  mov     rax, [rbp+arg_10]
0x180032329  mov     rcx, [rax+38h]; HWND
0x18003232d  mov     [rbp+var_18], rcx
0x180032331  mov     [rbp+var_10], 0
0x180032339  mov     r8d, 1; unsigned int
0x18003233f  lea     rdx, [rbp+var_18]; void **
0x180032343  call    ?SHProcessMessagesUntilEventsEx@@YAKPEAUHWND__@@PEAPEAXKKKK@Z; SHProcessMessagesUntilEventsEx(HWND__ *,void * *,ulong,ulong,ulong,ulong)
0x180032348  cmp     eax, 0FFFFFFFFh
0x18003234b  jnz     short loc_180032354
0x18003234d  mov     [rbp+arg_8], 80004005h
0x180032354  mov     [rbp+arg_0], 0
0x18003235c  cmp     [rbp+arg_8], 0
0x180032360  jl      short loc_1800323A9
0x180032362  mov     rax, [rbp+arg_10]
0x180032366  cmp     dword ptr [rax+30h], 1
0x18003236a  jz      short loc_1800323A9
0x18003236c  mov     rax, [rdi]
0x18003236f  mov     rbx, [rax]
0x180032372  lea     rcx, [rbp+arg_0]
0x180032376  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x18003237b  mov     r8, rax
0x18003237e  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180032385  mov     rcx, rdi
0x180032388  mov     rax, rbx
0x18003238b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032390  test    eax, eax
0x180032392  js      short loc_1800323A9
0x180032394  mov     rcx, [rbp+arg_0]
0x180032398  mov     rax, [rcx]
0x18003239b  lea     rdx, [rbp+arg_8]
0x18003239f  mov     rax, [rax+40h]
0x1800323a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800323a8  nop
0x1800323a9  mov     rcx, [rbp+arg_0]
0x1800323ad  test    rcx, rcx
0x1800323b0  jz      short loc_1800323C7
0x1800323b2  mov     [rbp+arg_0], 0
0x1800323ba  mov     rax, [rcx]
0x1800323bd  mov     rax, [rax+10h]
0x1800323c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800323c6  nop
0x1800323c7  mov     ebx, [rbp+arg_8]
0x1800323ca  mov     rcx, [rbp+arg_10]
0x1800323ce  test    rcx, rcx
0x1800323d1  jz      short loc_1800323E8
0x1800323d3  mov     [rbp+arg_10], 0
0x1800323db  mov     rax, [rcx]
0x1800323de  mov     rax, [rax+10h]
0x1800323e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800323e7  nop
0x1800323e8  test    rdi, rdi
0x1800323eb  jz      short loc_1800323FD
0x1800323ed  mov     rcx, [rdi]
0x1800323f0  mov     rax, [rcx+10h]
0x1800323f4  mov     rcx, rdi
0x1800323f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800323fc  nop
0x1800323fd  mov     eax, ebx
0x1800323ff  add     rsp, 48h
0x180032403  pop     rdi
0x180032404  pop     rsi
0x180032405  pop     rbx
0x180032406  pop     rbp
0x180032407  retn
```
