# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x1800186ec`
- end: `0x1800189c2`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `726`
- prototype: `__int64(__int64, DWORD, int, ...)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d1bc`

## callees

- `0x180002060`
- `0x1800186ec`
- `0x180018ca4`
- `0x18001a270`
- `0x18001c4c4`
- `0x18001e15c`
- `0x180035010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800187d9`
- `KERNEL32!CloseHandle` at `0x1800187d9`
- `KERNEL32!GetLastError` at `0x1800187be`
- `KERNEL32!GetLastError` at `0x1800187cd`
- `KERNEL32!GetLastError` at `0x1800187be`
- `KERNEL32!GetLastError` at `0x1800187cd`
- `KERNEL32!SetLastError` at `0x1800187ee`
- `KERNEL32!SetLastError` at `0x1800187ee`
- `KERNEL32!CreateEventExW` at `0x1800187ac`
- `KERNEL32!CreateEventExW` at `0x1800187ac`
- `ole32!CoWaitForMultipleHandles` at `0x1800188d8`
- `ole32!CoWaitForMultipleHandles` at `0x1800188d8`

## string_xrefs

- `0x180018837`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18001886d`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x180018896`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x1800188eb`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *> *>(
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
  *(_QWORD *)v4 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>::`vftable';
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(v4 + 8);
  *((_DWORD *)v4 + 11) = 1;
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *> *>'::`2'::CompletionDelegate::`vftable';
  *((_QWORD *)v4 + 1) = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *> *>'::`2'::CompletionDelegate::`vftable';
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
0x1800186ec  mov     rax, rsp
0x1800186ef  mov     [rax+8], rbx
0x1800186f3  mov     [rax+20h], r9
0x1800186f7  mov     [rax+18h], r8d
0x1800186fb  mov     [rax+10h], edx
0x1800186fe  push    rbp
0x1800186ff  push    rsi
0x180018700  push    rdi
0x180018701  push    r14
0x180018703  push    r15
0x180018705  mov     rbp, rsp
0x180018708  sub     rsp, 40h
0x18001870c  mov     r14, rcx
0x18001870f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018716  mov     ecx, 40h ; '@'; unsigned __int64
0x18001871b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180018720  mov     rbx, rax
0x180018723  test    rax, rax
0x180018726  jnz     short loc_180018732
0x180018728  mov     edi, 8007000Eh
0x18001872d  jmp     loc_18001888F
0x180018732  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>::`vftable'
0x180018739  mov     [rbx], rax
0x18001873c  lea     rdi, [rbx+8]
0x180018740  mov     rcx, rdi
0x180018743  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x180018748  mov     dword ptr [rbx+2Ch], 1
0x18001874f  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>'}
0x180018756  mov     [rbx], rax
0x180018759  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180018760  mov     [rdi], rax
0x180018763  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18001876a  test    rcx, rcx
0x18001876d  jz      short loc_18001877C
0x18001876f  mov     rax, [rcx]
0x180018772  mov     rax, [rax+8]
0x180018776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001877b  nop
0x18001877c  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>'}
0x180018783  mov     [rbx], rax
0x180018786  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001878d  mov     [rdi], rax
0x180018790  mov     dword ptr [rbx+30h], 0
0x180018797  mov     qword ptr [rbx+38h], 0
0x18001879f  mov     r9d, 1F0003h; dwDesiredAccess
0x1800187a5  xor     r8d, r8d; dwFlags
0x1800187a8  xor     edx, edx; lpName
0x1800187aa  xor     ecx, ecx; lpEventAttributes
0x1800187ac  call    cs:__imp_CreateEventExW
0x1800187b2  mov     rsi, rax
0x1800187b5  test    rax, rax
0x1800187b8  jz      loc_18001885B
0x1800187be  call    cs:__imp_GetLastError
0x1800187c4  mov     rdi, [rbx+38h]
0x1800187c8  test    rdi, rdi
0x1800187cb  jz      short loc_1800187F4
0x1800187cd  call    cs:__imp_GetLastError
0x1800187d3  mov     r15d, eax
0x1800187d6  mov     rcx, rdi; hObject
0x1800187d9  call    cs:__imp_CloseHandle
0x1800187df  mov     rcx, [rbp+28h]; this
0x1800187e3  test    eax, eax
0x1800187e5  jz      loc_1800189B7
0x1800187eb  mov     ecx, r15d; dwErrCode
0x1800187ee  call    cs:__imp_SetLastError
0x1800187f4  mov     [rbx+38h], rsi
0x1800187f8  mov     rax, [rbx]
0x1800187fb  mov     rcx, rbx
0x1800187fe  mov     rax, [rax+8]
0x180018802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018807  nop
0x180018808  mov     rax, [rbx]
0x18001880b  mov     rcx, rbx
0x18001880e  mov     rax, [rax+10h]
0x180018812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018817  nop
0x180018818  mov     rax, [r14]
0x18001881b  mov     rdx, rbx
0x18001881e  mov     rcx, r14
0x180018821  mov     rax, [rax+30h]
0x180018825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001882a  mov     edi, eax
0x18001882c  test    eax, eax
0x18001882e  jns     short loc_1800188AF
0x180018830  mov     rcx, [rbp+28h]; this
0x180018834  mov     r9d, eax; char *
0x180018837  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001883e  mov     edx, 649h; void *
0x180018843  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018848  nop
0x180018849  mov     rcx, [rbx]
0x18001884c  mov     rax, [rcx+10h]
0x180018850  mov     rcx, rbx
0x180018853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018858  nop
0x180018859  jmp     short loc_1800188A8
0x18001885b  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180018860  mov     edi, eax
0x180018862  test    eax, eax
0x180018864  jns     short loc_1800187F8
0x180018866  mov     rcx, [rbp+28h]; this
0x18001886a  mov     r9d, eax; char *
0x18001886d  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180018874  mov     edx, 62Bh; void *
0x180018879  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001887e  nop
0x18001887f  mov     rax, [rbx]
0x180018882  mov     rcx, rbx
0x180018885  mov     rax, [rax+10h]
0x180018889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001888e  nop
0x18001888f  mov     rcx, [rbp+28h]; this
0x180018893  mov     r9d, edi; char *
0x180018896  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001889d  mov     edx, 648h; void *
0x1800188a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800188a7  nop
0x1800188a8  mov     eax, edi
0x1800188aa  jmp     loc_1800189A6
0x1800188af  mov     rax, [rbx+38h]
0x1800188b3  mov     [rbp+pHandles], rax
0x1800188b7  mov     [rbp+dwindex], 0
0x1800188be  lea     rax, [rbp+dwindex]
0x1800188c2  mov     qword ptr [rsp+40h+lpdwindex], rax; int
0x1800188c7  lea     r9, [rbp+pHandles]; pHandles
0x1800188cb  mov     r8d, 1; cHandles
0x1800188d1  or      edx, 0FFFFFFFFh; dwTimeout
0x1800188d4  lea     ecx, [r8+7]; dwFlags
0x1800188d8  call    cs:__imp_CoWaitForMultipleHandles
0x1800188de  mov     edi, eax
0x1800188e0  test    eax, eax
0x1800188e2  jns     short loc_18001890F
0x1800188e4  mov     rcx, [rbp+28h]; this
0x1800188e8  mov     r9d, eax; char *
0x1800188eb  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800188f2  mov     edx, 655h; void *
0x1800188f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800188fc  nop
0x1800188fd  mov     rcx, [rbx]
0x180018900  mov     rax, [rcx+10h]
0x180018904  mov     rcx, rbx
0x180018907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001890c  nop
0x18001890d  jmp     short loc_1800188A8
0x18001890f  mov     eax, [rbx+30h]
0x180018912  cmp     eax, 1
0x180018915  jz      short loc_180018994
0x180018917  mov     [rbp+arg_18], 0
0x18001891f  mov     rax, [r14]
0x180018922  lea     r8, [rbp+arg_18]
0x180018926  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18001892d  mov     rcx, r14
0x180018930  mov     rax, [rax]
0x180018933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018938  mov     edi, eax
0x18001893a  test    eax, eax
0x18001893c  js      short loc_180018961
0x18001893e  mov     [rbp+arg_10], 8000FFFFh
0x180018945  mov     rcx, [rbp+arg_18]
0x180018949  mov     rax, [rcx]
0x18001894c  lea     rdx, [rbp+arg_10]
0x180018950  mov     rax, [rax+40h]
0x180018954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018959  mov     edi, eax
0x18001895b  test    eax, eax
0x18001895d  cmovns  edi, [rbp+arg_10]
0x180018961  mov     rcx, [rbp+arg_18]
0x180018965  test    rcx, rcx
0x180018968  jz      short loc_18001897F
0x18001896a  mov     [rbp+arg_18], 0
0x180018972  mov     rax, [rcx]
0x180018975  mov     rax, [rax+10h]
0x180018979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001897e  nop
0x18001897f  mov     rax, [rbx]
0x180018982  mov     rcx, rbx
0x180018985  mov     rax, [rax+10h]
0x180018989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001898e  nop
0x18001898f  jmp     loc_1800188A8
0x180018994  mov     rax, [rbx]
0x180018997  mov     rcx, rbx
0x18001899a  mov     rax, [rax+10h]
0x18001899e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189a3  nop
0x1800189a4  xor     eax, eax
0x1800189a6  mov     rbx, [rsp+40h+arg_0]
0x1800189ab  add     rsp, 40h
0x1800189af  pop     r15
0x1800189b1  pop     r14
0x1800189b3  pop     rdi
0x1800189b4  pop     rsi
0x1800189b5  pop     rbp
0x1800189b6  retn
0x1800189b7  mov     edx, 0A0Bh; void *
0x1800189bc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
