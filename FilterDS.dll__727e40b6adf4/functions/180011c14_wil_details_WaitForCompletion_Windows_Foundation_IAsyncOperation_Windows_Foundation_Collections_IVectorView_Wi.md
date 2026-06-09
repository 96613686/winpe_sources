# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x180011c14`
- end: `0x180011eea`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `726`
- prototype: `__int64(__int64, DWORD, int, ...)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800123b0`

## callees

- `0x180002a70`
- `0x1800049d8`
- `0x180005ca4`
- `0x180006bb4`
- `0x180011c14`
- `0x18001242c`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180011cd4`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180011cd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ce6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011cf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ce6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011cf5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011d16`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011d16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011d01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011d01`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180011e00`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180011e00`

## string_xrefs

- `0x180011d5f`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x180011d95`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x180011dbe`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x180011e13`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *>(
        __int64 a1,
        DWORD a2,
        int a3,
        ...)
{
  char *v4; // rbx
  unsigned int v5; // edi
  wil::details *v6; // rcx
  HANDLE Event; // rsi
  void *v8; // rdi
  DWORD LastError; // r15d
  unsigned int v10; // r8d
  const char *v11; // r9
  int v12; // eax
  int LastErrorFailHr; // eax
  HRESULT v15; // eax
  __int64 v16; // rcx
  int lpdwindex; // [rsp+20h] [rbp-20h]
  int lpdwindexa; // [rsp+20h] [rbp-20h]
  HANDLE pHandles; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  DWORD dwindex; // [rsp+78h] [rbp+38h] BYREF
  int v22; // [rsp+80h] [rbp+40h] BYREF
  __int64 v23; // [rsp+88h] [rbp+48h] BYREF
  va_list va; // [rsp+88h] [rbp+48h]
  va_list va1; // [rsp+90h] [rbp+50h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v23 = va_arg(va1, _QWORD);
  v22 = a3;
  dwindex = a2;
  v4 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
  {
    v5 = -2147024882;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x648,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)v5,
      lpdwindex);
    return v5;
  }
  *(_QWORD *)v4 = &Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>::`vftable';
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(v4 + 8);
  *((_DWORD *)v4 + 11) = 1;
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *>'::`2'::CompletionDelegate::`vftable';
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_DWORD *)v4 + 12) = 0;
  *((_QWORD *)v4 + 7) = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    v8 = (void *)*((_QWORD *)v4 + 7);
    if ( v8 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v8) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v10, v11);
      SetLastError(LastError);
    }
    *((_QWORD *)v4 + 7) = Event;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v6);
    v5 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x62B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
        (const char *)(unsigned int)LastErrorFailHr,
        lpdwindex);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
      goto LABEL_14;
    }
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
  v12 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)a1 + 48LL))(a1, v4);
  v5 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x649,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v12,
      lpdwindex);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
    return v5;
  }
  pHandles = (HANDLE)*((_QWORD *)v4 + 7);
  dwindex = 0;
  v15 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
  v5 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x655,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v15,
      lpdwindexa);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
    return v5;
  }
  if ( *((_DWORD *)v4 + 12) != 1 )
  {
    v23 = 0;
    v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))a1)(
           a1,
           &GUID_00000036_0000_0000_c000_000000000046,
           (__int64 *)va);
    if ( (v5 & 0x80000000) == 0 )
    {
      v22 = -2147418113;
      v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v23 + 64LL))(v23, &v22);
      if ( (v5 & 0x80000000) == 0 )
        v5 = v22;
    }
    v16 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
    return v5;
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
  return 0;
}

```

## disassembly

```asm
0x180011c14  mov     rax, rsp
0x180011c17  mov     [rax+8], rbx
0x180011c1b  mov     [rax+20h], r9
0x180011c1f  mov     [rax+18h], r8d
0x180011c23  mov     [rax+10h], edx
0x180011c26  push    rbp
0x180011c27  push    rsi
0x180011c28  push    rdi
0x180011c29  push    r14
0x180011c2b  push    r15
0x180011c2d  mov     rbp, rsp
0x180011c30  sub     rsp, 40h
0x180011c34  mov     r14, rcx
0x180011c37  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011c3e  mov     ecx, 40h ; '@'; unsigned __int64
0x180011c43  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180011c48  mov     rbx, rax
0x180011c4b  test    rax, rax
0x180011c4e  jnz     short loc_180011C5A
0x180011c50  mov     edi, 8007000Eh
0x180011c55  jmp     loc_180011DB7
0x180011c5a  lea     rax, ??_7?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@Windows@@6B@; const Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>::`vftable'
0x180011c61  mov     [rbx], rax
0x180011c64  lea     rdi, [rbx+8]
0x180011c68  mov     rcx, rdi
0x180011c6b  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x180011c70  mov     dword ptr [rbx+2Ch], 1
0x180011c77  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>'}
0x180011c7e  mov     [rbx], rax
0x180011c81  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180011c88  mov     [rdi], rax
0x180011c8b  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180011c92  test    rcx, rcx
0x180011c95  jz      short loc_180011CA4
0x180011c97  mov     rax, [rcx]
0x180011c9a  mov     rax, [rax+8]
0x180011c9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ca3  nop
0x180011ca4  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>'}
0x180011cab  mov     [rbx], rax
0x180011cae  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180011cb5  mov     [rdi], rax
0x180011cb8  mov     dword ptr [rbx+30h], 0
0x180011cbf  mov     qword ptr [rbx+38h], 0
0x180011cc7  mov     r9d, 1F0003h; dwDesiredAccess
0x180011ccd  xor     r8d, r8d; dwFlags
0x180011cd0  xor     edx, edx; lpName
0x180011cd2  xor     ecx, ecx; lpEventAttributes
0x180011cd4  call    cs:__imp_CreateEventExW
0x180011cda  mov     rsi, rax
0x180011cdd  test    rax, rax
0x180011ce0  jz      loc_180011D83
0x180011ce6  call    cs:__imp_GetLastError
0x180011cec  mov     rdi, [rbx+38h]
0x180011cf0  test    rdi, rdi
0x180011cf3  jz      short loc_180011D1C
0x180011cf5  call    cs:__imp_GetLastError
0x180011cfb  mov     r15d, eax
0x180011cfe  mov     rcx, rdi; hObject
0x180011d01  call    cs:__imp_CloseHandle
0x180011d07  mov     rcx, [rbp+28h]; this
0x180011d0b  test    eax, eax
0x180011d0d  jz      loc_180011EDF
0x180011d13  mov     ecx, r15d; dwErrCode
0x180011d16  call    cs:__imp_SetLastError
0x180011d1c  mov     [rbx+38h], rsi
0x180011d20  mov     rax, [rbx]
0x180011d23  mov     rcx, rbx
0x180011d26  mov     rax, [rax+8]
0x180011d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d2f  nop
0x180011d30  mov     rax, [rbx]
0x180011d33  mov     rcx, rbx
0x180011d36  mov     rax, [rax+10h]
0x180011d3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d3f  nop
0x180011d40  mov     rax, [r14]
0x180011d43  mov     rdx, rbx
0x180011d46  mov     rcx, r14
0x180011d49  mov     rax, [rax+30h]
0x180011d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d52  mov     edi, eax
0x180011d54  test    eax, eax
0x180011d56  jns     short loc_180011DD7
0x180011d58  mov     rcx, [rbp+28h]; this
0x180011d5c  mov     r9d, eax; char *
0x180011d5f  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011d66  mov     edx, 649h; void *
0x180011d6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011d70  nop
0x180011d71  mov     rcx, [rbx]
0x180011d74  mov     rax, [rcx+10h]
0x180011d78  mov     rcx, rbx
0x180011d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d80  nop
0x180011d81  jmp     short loc_180011DD0
0x180011d83  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180011d88  mov     edi, eax
0x180011d8a  test    eax, eax
0x180011d8c  jns     short loc_180011D20
0x180011d8e  mov     rcx, [rbp+28h]; this
0x180011d92  mov     r9d, eax; char *
0x180011d95  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011d9c  mov     edx, 62Bh; void *
0x180011da1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011da6  nop
0x180011da7  mov     rax, [rbx]
0x180011daa  mov     rcx, rbx
0x180011dad  mov     rax, [rax+10h]
0x180011db1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011db6  nop
0x180011db7  mov     rcx, [rbp+28h]; this
0x180011dbb  mov     r9d, edi; char *
0x180011dbe  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011dc5  mov     edx, 648h; void *
0x180011dca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011dcf  nop
0x180011dd0  mov     eax, edi
0x180011dd2  jmp     loc_180011ECE
0x180011dd7  mov     rax, [rbx+38h]
0x180011ddb  mov     [rbp+pHandles], rax
0x180011ddf  mov     [rbp+dwindex], 0
0x180011de6  lea     rax, [rbp+dwindex]
0x180011dea  mov     qword ptr [rsp+40h+lpdwindex], rax; int
0x180011def  lea     r9, [rbp+pHandles]; pHandles
0x180011df3  mov     r8d, 1; cHandles
0x180011df9  or      edx, 0FFFFFFFFh; dwTimeout
0x180011dfc  lea     ecx, [r8+7]; dwFlags
0x180011e00  call    cs:__imp_CoWaitForMultipleHandles
0x180011e06  mov     edi, eax
0x180011e08  test    eax, eax
0x180011e0a  jns     short loc_180011E37
0x180011e0c  mov     rcx, [rbp+28h]; this
0x180011e10  mov     r9d, eax; char *
0x180011e13  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011e1a  mov     edx, 655h; void *
0x180011e1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011e24  nop
0x180011e25  mov     rcx, [rbx]
0x180011e28  mov     rax, [rcx+10h]
0x180011e2c  mov     rcx, rbx
0x180011e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e34  nop
0x180011e35  jmp     short loc_180011DD0
0x180011e37  mov     eax, [rbx+30h]
0x180011e3a  cmp     eax, 1
0x180011e3d  jz      short loc_180011EBC
0x180011e3f  mov     [rbp+arg_18], 0
0x180011e47  mov     rax, [r14]
0x180011e4a  lea     r8, [rbp+arg_18]
0x180011e4e  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180011e55  mov     rcx, r14
0x180011e58  mov     rax, [rax]
0x180011e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e60  mov     edi, eax
0x180011e62  test    eax, eax
0x180011e64  js      short loc_180011E89
0x180011e66  mov     [rbp+arg_10], 8000FFFFh
0x180011e6d  mov     rcx, [rbp+arg_18]
0x180011e71  mov     rax, [rcx]
0x180011e74  lea     rdx, [rbp+arg_10]
0x180011e78  mov     rax, [rax+40h]
0x180011e7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e81  mov     edi, eax
0x180011e83  test    eax, eax
0x180011e85  cmovns  edi, [rbp+arg_10]
0x180011e89  mov     rcx, [rbp+arg_18]
0x180011e8d  test    rcx, rcx
0x180011e90  jz      short loc_180011EA7
0x180011e92  mov     [rbp+arg_18], 0
0x180011e9a  mov     rax, [rcx]
0x180011e9d  mov     rax, [rax+10h]
0x180011ea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ea6  nop
0x180011ea7  mov     rax, [rbx]
0x180011eaa  mov     rcx, rbx
0x180011ead  mov     rax, [rax+10h]
0x180011eb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011eb6  nop
0x180011eb7  jmp     loc_180011DD0
0x180011ebc  mov     rax, [rbx]
0x180011ebf  mov     rcx, rbx
0x180011ec2  mov     rax, [rax+10h]
0x180011ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ecb  nop
0x180011ecc  xor     eax, eax
0x180011ece  mov     rbx, [rsp+40h+arg_0]
0x180011ed3  add     rsp, 40h
0x180011ed7  pop     r15
0x180011ed9  pop     r14
0x180011edb  pop     rdi
0x180011edc  pop     rsi
0x180011edd  pop     rbp
0x180011ede  retn
0x180011edf  mov     edx, 0A0Bh; void *
0x180011ee4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
