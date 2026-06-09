# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> *>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x1800189c8`
- end: `0x180018c9e`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `726`
- prototype: `__int64(__int64, DWORD, int, ...)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001a874`

## callees

- `0x180002060`
- `0x1800189c8`
- `0x180018ca4`
- `0x18001a270`
- `0x18001c4c4`
- `0x18001e15c`
- `0x180035010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180018ab5`
- `KERNEL32!CloseHandle` at `0x180018ab5`
- `KERNEL32!GetLastError` at `0x180018a9a`
- `KERNEL32!GetLastError` at `0x180018aa9`
- `KERNEL32!GetLastError` at `0x180018a9a`
- `KERNEL32!GetLastError` at `0x180018aa9`
- `KERNEL32!SetLastError` at `0x180018aca`
- `KERNEL32!SetLastError` at `0x180018aca`
- `KERNEL32!CreateEventExW` at `0x180018a88`
- `KERNEL32!CreateEventExW` at `0x180018a88`
- `ole32!CoWaitForMultipleHandles` at `0x180018bb4`
- `ole32!CoWaitForMultipleHandles` at `0x180018bb4`

## string_xrefs

- `0x180018b13`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x180018b49`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x180018b72`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x180018bc7`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> *>(
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
  *(_QWORD *)v4 = &Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>::`vftable';
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(v4 + 8);
  *((_DWORD *)v4 + 11) = 1;
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> *>'::`2'::CompletionDelegate::`vftable';
  *((_QWORD *)v4 + 1) = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> *>'::`2'::CompletionDelegate::`vftable';
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
  v12 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)a1 + 64LL))(a1, v4);
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
0x1800189c8  mov     rax, rsp
0x1800189cb  mov     [rax+8], rbx
0x1800189cf  mov     [rax+20h], r9
0x1800189d3  mov     [rax+18h], r8d
0x1800189d7  mov     [rax+10h], edx
0x1800189da  push    rbp
0x1800189db  push    rsi
0x1800189dc  push    rdi
0x1800189dd  push    r14
0x1800189df  push    r15
0x1800189e1  mov     rbp, rsp
0x1800189e4  sub     rsp, 40h
0x1800189e8  mov     r14, rcx
0x1800189eb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800189f2  mov     ecx, 40h ; '@'; unsigned __int64
0x1800189f7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800189fc  mov     rbx, rax
0x1800189ff  test    rax, rax
0x180018a02  jnz     short loc_180018A0E
0x180018a04  mov     edi, 8007000Eh
0x180018a09  jmp     loc_180018B6B
0x180018a0e  lea     rax, ??_7?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>::`vftable'
0x180018a15  mov     [rbx], rax
0x180018a18  lea     rdi, [rbx+8]
0x180018a1c  mov     rcx, rdi
0x180018a1f  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x180018a24  mov     dword ptr [rbx+2Ch], 1
0x180018a2b  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>'}
0x180018a32  mov     [rbx], rax
0x180018a35  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180018a3c  mov     [rdi], rax
0x180018a3f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180018a46  test    rcx, rcx
0x180018a49  jz      short loc_180018A58
0x180018a4b  mov     rax, [rcx]
0x180018a4e  mov     rax, [rax+8]
0x180018a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a57  nop
0x180018a58  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> *>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>'}
0x180018a5f  mov     [rbx], rax
0x180018a62  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> *>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180018a69  mov     [rdi], rax
0x180018a6c  mov     dword ptr [rbx+30h], 0
0x180018a73  mov     qword ptr [rbx+38h], 0
0x180018a7b  mov     r9d, 1F0003h; dwDesiredAccess
0x180018a81  xor     r8d, r8d; dwFlags
0x180018a84  xor     edx, edx; lpName
0x180018a86  xor     ecx, ecx; lpEventAttributes
0x180018a88  call    cs:__imp_CreateEventExW
0x180018a8e  mov     rsi, rax
0x180018a91  test    rax, rax
0x180018a94  jz      loc_180018B37
0x180018a9a  call    cs:__imp_GetLastError
0x180018aa0  mov     rdi, [rbx+38h]
0x180018aa4  test    rdi, rdi
0x180018aa7  jz      short loc_180018AD0
0x180018aa9  call    cs:__imp_GetLastError
0x180018aaf  mov     r15d, eax
0x180018ab2  mov     rcx, rdi; hObject
0x180018ab5  call    cs:__imp_CloseHandle
0x180018abb  mov     rcx, [rbp+28h]; this
0x180018abf  test    eax, eax
0x180018ac1  jz      loc_180018C93
0x180018ac7  mov     ecx, r15d; dwErrCode
0x180018aca  call    cs:__imp_SetLastError
0x180018ad0  mov     [rbx+38h], rsi
0x180018ad4  mov     rax, [rbx]
0x180018ad7  mov     rcx, rbx
0x180018ada  mov     rax, [rax+8]
0x180018ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ae3  nop
0x180018ae4  mov     rax, [rbx]
0x180018ae7  mov     rcx, rbx
0x180018aea  mov     rax, [rax+10h]
0x180018aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018af3  nop
0x180018af4  mov     rax, [r14]
0x180018af7  mov     rdx, rbx
0x180018afa  mov     rcx, r14
0x180018afd  mov     rax, [rax+40h]
0x180018b01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b06  mov     edi, eax
0x180018b08  test    eax, eax
0x180018b0a  jns     short loc_180018B8B
0x180018b0c  mov     rcx, [rbp+28h]; this
0x180018b10  mov     r9d, eax; char *
0x180018b13  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180018b1a  mov     edx, 649h; void *
0x180018b1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018b24  nop
0x180018b25  mov     rcx, [rbx]
0x180018b28  mov     rax, [rcx+10h]
0x180018b2c  mov     rcx, rbx
0x180018b2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b34  nop
0x180018b35  jmp     short loc_180018B84
0x180018b37  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180018b3c  mov     edi, eax
0x180018b3e  test    eax, eax
0x180018b40  jns     short loc_180018AD4
0x180018b42  mov     rcx, [rbp+28h]; this
0x180018b46  mov     r9d, eax; char *
0x180018b49  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180018b50  mov     edx, 62Bh; void *
0x180018b55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018b5a  nop
0x180018b5b  mov     rax, [rbx]
0x180018b5e  mov     rcx, rbx
0x180018b61  mov     rax, [rax+10h]
0x180018b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b6a  nop
0x180018b6b  mov     rcx, [rbp+28h]; this
0x180018b6f  mov     r9d, edi; char *
0x180018b72  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180018b79  mov     edx, 648h; void *
0x180018b7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018b83  nop
0x180018b84  mov     eax, edi
0x180018b86  jmp     loc_180018C82
0x180018b8b  mov     rax, [rbx+38h]
0x180018b8f  mov     [rbp+pHandles], rax
0x180018b93  mov     [rbp+dwindex], 0
0x180018b9a  lea     rax, [rbp+dwindex]
0x180018b9e  mov     qword ptr [rsp+40h+lpdwindex], rax; int
0x180018ba3  lea     r9, [rbp+pHandles]; pHandles
0x180018ba7  mov     r8d, 1; cHandles
0x180018bad  or      edx, 0FFFFFFFFh; dwTimeout
0x180018bb0  lea     ecx, [r8+7]; dwFlags
0x180018bb4  call    cs:__imp_CoWaitForMultipleHandles
0x180018bba  mov     edi, eax
0x180018bbc  test    eax, eax
0x180018bbe  jns     short loc_180018BEB
0x180018bc0  mov     rcx, [rbp+28h]; this
0x180018bc4  mov     r9d, eax; char *
0x180018bc7  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180018bce  mov     edx, 655h; void *
0x180018bd3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018bd8  nop
0x180018bd9  mov     rcx, [rbx]
0x180018bdc  mov     rax, [rcx+10h]
0x180018be0  mov     rcx, rbx
0x180018be3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018be8  nop
0x180018be9  jmp     short loc_180018B84
0x180018beb  mov     eax, [rbx+30h]
0x180018bee  cmp     eax, 1
0x180018bf1  jz      short loc_180018C70
0x180018bf3  mov     [rbp+arg_18], 0
0x180018bfb  mov     rax, [r14]
0x180018bfe  lea     r8, [rbp+arg_18]
0x180018c02  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180018c09  mov     rcx, r14
0x180018c0c  mov     rax, [rax]
0x180018c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c14  mov     edi, eax
0x180018c16  test    eax, eax
0x180018c18  js      short loc_180018C3D
0x180018c1a  mov     [rbp+arg_10], 8000FFFFh
0x180018c21  mov     rcx, [rbp+arg_18]
0x180018c25  mov     rax, [rcx]
0x180018c28  lea     rdx, [rbp+arg_10]
0x180018c2c  mov     rax, [rax+40h]
0x180018c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c35  mov     edi, eax
0x180018c37  test    eax, eax
0x180018c39  cmovns  edi, [rbp+arg_10]
0x180018c3d  mov     rcx, [rbp+arg_18]
0x180018c41  test    rcx, rcx
0x180018c44  jz      short loc_180018C5B
0x180018c46  mov     [rbp+arg_18], 0
0x180018c4e  mov     rax, [rcx]
0x180018c51  mov     rax, [rax+10h]
0x180018c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c5a  nop
0x180018c5b  mov     rax, [rbx]
0x180018c5e  mov     rcx, rbx
0x180018c61  mov     rax, [rax+10h]
0x180018c65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c6a  nop
0x180018c6b  jmp     loc_180018B84
0x180018c70  mov     rax, [rbx]
0x180018c73  mov     rcx, rbx
0x180018c76  mov     rax, [rax+10h]
0x180018c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c7f  nop
0x180018c80  xor     eax, eax
0x180018c82  mov     rbx, [rsp+40h+arg_0]
0x180018c87  add     rsp, 40h
0x180018c8b  pop     r15
0x180018c8d  pop     r14
0x180018c8f  pop     rdi
0x180018c90  pop     rsi
0x180018c91  pop     rbp
0x180018c92  retn
0x180018c93  mov     edx, 0A0Bh; void *
0x180018c98  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
