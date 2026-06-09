# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::IShellActivationResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::IShellActivationResult *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x180021080`
- end: `0x180021356`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAUIShellActivationResult@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUIShellActivationResult@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `726`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800274dc`
- `0x18002cac4`

## callees

- `0x180004e9c`
- `0x18000a0f8`
- `0x18000c964`
- `0x18000e4c8`
- `0x180021080`
- `0x180021ba4`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18002126c`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18002126c`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180021140`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180021140`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021152`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021161`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021152`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021161`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021182`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021182`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002116d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002116d`

## string_xrefs

- `0x1800211cb`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x180021201`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18002122a`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18002127f`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::IShellActivationResult *> *>(
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
  v4 = (char *)operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
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
  *(_QWORD *)v4 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::IShellActivationResult *>::`vftable';
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v4 + 8));
  *((_DWORD *)v4 + 11) = 1;
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::IShellActivationResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::IShellActivationResult *>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::IShellActivationResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::IShellActivationResult *> *>'::`2'::CompletionDelegate::`vftable';
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::IShellActivationResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
0x180021080  mov     rax, rsp
0x180021083  mov     [rax+8], rbx
0x180021087  mov     [rax+20h], r9
0x18002108b  mov     [rax+18h], r8d
0x18002108f  mov     [rax+10h], edx
0x180021092  push    rbp
0x180021093  push    rsi
0x180021094  push    rdi
0x180021095  push    r14
0x180021097  push    r15
0x180021099  mov     rbp, rsp
0x18002109c  sub     rsp, 40h
0x1800210a0  mov     r14, rcx
0x1800210a3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800210aa  mov     ecx, 40h ; '@'; unsigned __int64
0x1800210af  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800210b4  mov     rbx, rax
0x1800210b7  test    rax, rax
0x1800210ba  jnz     short loc_1800210C6
0x1800210bc  mov     edi, 8007000Eh
0x1800210c1  jmp     loc_180021223
0x1800210c6  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAUIShellActivationResult@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::IShellActivationResult *>::`vftable'
0x1800210cd  mov     [rbx], rax
0x1800210d0  lea     rdi, [rbx+8]
0x1800210d4  mov     rcx, rdi; this
0x1800210d7  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x1800210dc  mov     dword ptr [rbx+2Ch], 1
0x1800210e3  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUIShellActivationResult@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAUIShellActivationResult@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::IShellActivationResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::IShellActivationResult *>'}
0x1800210ea  mov     [rbx], rax
0x1800210ed  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUIShellActivationResult@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::IShellActivationResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800210f4  mov     [rdi], rax
0x1800210f7  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800210fe  test    rcx, rcx
0x180021101  jz      short loc_180021110
0x180021103  mov     rax, [rcx]
0x180021106  mov     rax, [rax+8]
0x18002110a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002110f  nop
0x180021110  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAUIShellActivationResult@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUIShellActivationResult@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@PEAUIShellActivationResult@PlatformExtensions@Internal@Windows@@@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::IShellActivationResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::IShellActivationResult *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::IShellActivationResult *>'}
0x180021117  mov     [rbx], rax
0x18002111a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUIShellActivationResult@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::IShellActivationResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180021121  mov     [rdi], rax
0x180021124  mov     dword ptr [rbx+30h], 0
0x18002112b  mov     qword ptr [rbx+38h], 0
0x180021133  mov     r9d, 1F0003h; dwDesiredAccess
0x180021139  xor     r8d, r8d; dwFlags
0x18002113c  xor     edx, edx; lpName
0x18002113e  xor     ecx, ecx; lpEventAttributes
0x180021140  call    cs:__imp_CreateEventExW
0x180021146  mov     rsi, rax
0x180021149  test    rax, rax
0x18002114c  jz      loc_1800211EF
0x180021152  call    cs:__imp_GetLastError
0x180021158  mov     rdi, [rbx+38h]
0x18002115c  test    rdi, rdi
0x18002115f  jz      short loc_180021188
0x180021161  call    cs:__imp_GetLastError
0x180021167  mov     r15d, eax
0x18002116a  mov     rcx, rdi; hObject
0x18002116d  call    cs:__imp_CloseHandle
0x180021173  mov     rcx, [rbp+28h]; this
0x180021177  test    eax, eax
0x180021179  jz      loc_18002134B
0x18002117f  mov     ecx, r15d; dwErrCode
0x180021182  call    cs:__imp_SetLastError
0x180021188  mov     [rbx+38h], rsi
0x18002118c  mov     rax, [rbx]
0x18002118f  mov     rcx, rbx
0x180021192  mov     rax, [rax+8]
0x180021196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002119b  nop
0x18002119c  mov     rax, [rbx]
0x18002119f  mov     rcx, rbx
0x1800211a2  mov     rax, [rax+10h]
0x1800211a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211ab  nop
0x1800211ac  mov     rax, [r14]
0x1800211af  mov     rdx, rbx
0x1800211b2  mov     rcx, r14
0x1800211b5  mov     rax, [rax+30h]
0x1800211b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211be  mov     edi, eax
0x1800211c0  test    eax, eax
0x1800211c2  jns     short loc_180021243
0x1800211c4  mov     rcx, [rbp+28h]; this
0x1800211c8  mov     r9d, eax; char *
0x1800211cb  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800211d2  mov     edx, 649h; void *
0x1800211d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800211dc  nop
0x1800211dd  mov     rcx, [rbx]
0x1800211e0  mov     rax, [rcx+10h]
0x1800211e4  mov     rcx, rbx
0x1800211e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211ec  nop
0x1800211ed  jmp     short loc_18002123C
0x1800211ef  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800211f4  mov     edi, eax
0x1800211f6  test    eax, eax
0x1800211f8  jns     short loc_18002118C
0x1800211fa  mov     rcx, [rbp+28h]; this
0x1800211fe  mov     r9d, eax; char *
0x180021201  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021208  mov     edx, 62Bh; void *
0x18002120d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021212  nop
0x180021213  mov     rax, [rbx]
0x180021216  mov     rcx, rbx
0x180021219  mov     rax, [rax+10h]
0x18002121d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021222  nop
0x180021223  mov     rcx, [rbp+28h]; this
0x180021227  mov     r9d, edi; char *
0x18002122a  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021231  mov     edx, 648h; void *
0x180021236  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002123b  nop
0x18002123c  mov     eax, edi
0x18002123e  jmp     loc_18002133A
0x180021243  mov     rax, [rbx+38h]
0x180021247  mov     [rbp+pHandles], rax
0x18002124b  mov     [rbp+dwindex], 0
0x180021252  lea     rax, [rbp+dwindex]
0x180021256  mov     qword ptr [rsp+40h+lpdwindex], rax; int
0x18002125b  lea     r9, [rbp+pHandles]; pHandles
0x18002125f  mov     r8d, 1; cHandles
0x180021265  or      edx, 0FFFFFFFFh; dwTimeout
0x180021268  lea     ecx, [r8+7]; dwFlags
0x18002126c  call    cs:__imp_CoWaitForMultipleHandles
0x180021272  mov     edi, eax
0x180021274  test    eax, eax
0x180021276  jns     short loc_1800212A3
0x180021278  mov     rcx, [rbp+28h]; this
0x18002127c  mov     r9d, eax; char *
0x18002127f  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021286  mov     edx, 655h; void *
0x18002128b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021290  nop
0x180021291  mov     rcx, [rbx]
0x180021294  mov     rax, [rcx+10h]
0x180021298  mov     rcx, rbx
0x18002129b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212a0  nop
0x1800212a1  jmp     short loc_18002123C
0x1800212a3  mov     eax, [rbx+30h]
0x1800212a6  cmp     eax, 1
0x1800212a9  jz      short loc_180021328
0x1800212ab  mov     [rbp+arg_18], 0
0x1800212b3  mov     rax, [r14]
0x1800212b6  lea     r8, [rbp+arg_18]
0x1800212ba  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x1800212c1  mov     rcx, r14
0x1800212c4  mov     rax, [rax]
0x1800212c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212cc  mov     edi, eax
0x1800212ce  test    eax, eax
0x1800212d0  js      short loc_1800212F5
0x1800212d2  mov     [rbp+arg_10], 8000FFFFh
0x1800212d9  mov     rcx, [rbp+arg_18]
0x1800212dd  mov     rax, [rcx]
0x1800212e0  lea     rdx, [rbp+arg_10]
0x1800212e4  mov     rax, [rax+40h]
0x1800212e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212ed  mov     edi, eax
0x1800212ef  test    eax, eax
0x1800212f1  cmovns  edi, [rbp+arg_10]
0x1800212f5  mov     rcx, [rbp+arg_18]
0x1800212f9  test    rcx, rcx
0x1800212fc  jz      short loc_180021313
0x1800212fe  mov     [rbp+arg_18], 0
0x180021306  mov     rax, [rcx]
0x180021309  mov     rax, [rax+10h]
0x18002130d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021312  nop
0x180021313  mov     rax, [rbx]
0x180021316  mov     rcx, rbx
0x180021319  mov     rax, [rax+10h]
0x18002131d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021322  nop
0x180021323  jmp     loc_18002123C
0x180021328  mov     rax, [rbx]
0x18002132b  mov     rcx, rbx
0x18002132e  mov     rax, [rax+10h]
0x180021332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021337  nop
0x180021338  xor     eax, eax
0x18002133a  mov     rbx, [rsp+40h+arg_0]
0x18002133f  add     rsp, 40h
0x180021343  pop     r15
0x180021345  pop     r14
0x180021347  pop     rdi
0x180021348  pop     rsi
0x180021349  pop     rbp
0x18002134a  retn
0x18002134b  mov     edx, 0A0Bh; void *
0x180021350  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
