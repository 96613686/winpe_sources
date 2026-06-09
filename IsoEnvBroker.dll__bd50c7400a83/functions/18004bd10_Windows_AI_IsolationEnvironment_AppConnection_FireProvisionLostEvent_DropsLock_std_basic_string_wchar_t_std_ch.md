# Windows::AI::IsolationEnvironment::AppConnection::FireProvisionLostEvent_DropsLock(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,Windows::AI::IsolationEnvironment::IsolationProvisionLostReason)

- ea: `0x18004bd10`
- end: `0x18004bf10`
- name: `?FireProvisionLostEvent_DropsLock@AppConnection@IsolationEnvironment@AI@Windows@@QEAAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0W4IsolationProvisionLostReason@234@@Z`
- size: `512`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180037470`

## callees

- `0x180002a30`
- `0x1800075e4`
- `0x18000a464`
- `0x180047b38`
- `0x18004b6b4`
- `0x18004bd10`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004be53`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004be53`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004be86`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004be86`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004be34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004be6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004be34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004be6e`

## string_xrefs

- `0x18004bee9`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`
- `0x18004befb`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`
- `0x18004bec8`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\appconnection.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::AI::IsolationEnvironment::AppConnection::FireProvisionLostEvent_DropsLock(
        __int64 a1,
        const WCHAR *a2,
        const WCHAR *a3,
        int a4)
{
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  int v10; // ebx
  const char *v11; // r9
  int v12; // ebx
  DWORD CurrentThreadId; // ebp
  const char *v14; // r9
  const WCHAR *v16[9]; // [rsp+20h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v8 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( v8 )
  {
    v8[4] = 1;
    *v8 = &Microsoft::WRL::RuntimeClass<Windows::AI::IsolationEnvironment::IIsolationProvisionLostEventArgs,Windows::AI::IsolationEnvironment::IIsolationProvisionLostEventArgs2>::`vftable';
    v8[1] = &Microsoft::WRL::RuntimeClass<Windows::AI::IsolationEnvironment::IIsolationProvisionLostEventArgs,Windows::AI::IsolationEnvironment::IIsolationProvisionLostEventArgs2>::`vftable'{for `IWeakReferenceSource'};
    v8[2] = &Microsoft::WRL::RuntimeClass<Windows::AI::IsolationEnvironment::IIsolationProvisionLostEventArgs,Windows::AI::IsolationEnvironment::IIsolationProvisionLostEventArgs2>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::AI::IsolationEnvironment::IIsolationProvisionLostEventArgs2>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *v9 = &Windows::AI::IsolationEnvironment::ProvisionLostEventArgs::`vftable';
    v9[1] = &Windows::AI::IsolationEnvironment::ProvisionLostEventArgs::`vftable'{for `IWeakReferenceSource'};
    v9[2] = &Windows::AI::IsolationEnvironment::ProvisionLostEventArgs::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::AI::IsolationEnvironment::IIsolationProvisionLostEventArgs2>'};
    v9[6] = 0;
    v9[7] = 0;
    *((_DWORD *)v9 + 10) = a4;
    if ( *((_QWORD *)a2 + 3) > 7u )
      a2 = *(const WCHAR **)a2;
    v16[0] = a2;
    Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>((HSTRING *)v9 + 6, v16);
    if ( *((_QWORD *)a3 + 3) > 7u )
      a3 = *(const WCHAR **)a3;
    v16[0] = a3;
    Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>((HSTRING *)v9 + 7, v16);
    (*(void (__fastcall **)(_QWORD *))(*v9 + 8LL))(v9);
    (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
    if ( a1 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    v10 = dword_1800B9160;
    if ( v10 != GetCurrentThreadId() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x15D,
        (int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
        v11);
    dword_1800B9160 = 0;
    ReleaseSRWLockExclusive(&g_lock);
    Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::AI::IsolationEnvironment::IsolationAppConnection *,Windows::AI::IsolationEnvironment::IsolationProvisionLostEventArgs *>,Microsoft::WRL::InvokeModeOptions<2>>::InvokeAll<Windows::AI::IsolationEnvironment::AppConnection *,Windows::AI::IsolationEnvironment::ProvisionLostEventArgs *>(
      a1 + 40,
      a1,
      v9);
    v12 = dword_1800B9160;
    CurrentThreadId = GetCurrentThreadId();
    if ( v12 == CurrentThreadId )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x2C,
        (int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
        v14);
    AcquireSRWLockExclusive(&g_lock);
    dword_1800B9160 = CurrentThreadId;
    if ( a1 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
    (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\appconnection.cpp",
      (const char *)0x8007000ELL,
      (int)v16[0]);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18004bd10  push    rbx
0x18004bd12  push    rbp
0x18004bd13  push    rsi
0x18004bd14  push    rdi
0x18004bd15  push    r14
0x18004bd17  push    r15
0x18004bd19  sub     rsp, 38h
0x18004bd1d  mov     ebp, r9d
0x18004bd20  mov     r14, r8
0x18004bd23  mov     rbx, rdx
0x18004bd26  mov     rsi, rcx
0x18004bd29  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004bd30  mov     ecx, 40h ; '@'; unsigned __int64
0x18004bd35  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004bd3a  mov     rdi, rax
0x18004bd3d  test    rax, rax
0x18004bd40  jz      loc_18004BEBB
0x18004bd46  mov     qword ptr [rax+20h], 1
0x18004bd4e  lea     rax, ??_7?$RuntimeClass@UIIsolationProvisionLostEventArgs@IsolationEnvironment@AI@Windows@@UIIsolationProvisionLostEventArgs2@234@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Windows::AI::IsolationEnvironment::IIsolationProvisionLostEventArgs,Windows::AI::IsolationEnvironment::IIsolationProvisionLostEventArgs2>::`vftable'
0x18004bd55  mov     [rdi], rax
0x18004bd58  lea     rax, ??_7?$RuntimeClass@UIIsolationProvisionLostEventArgs@IsolationEnvironment@AI@Windows@@UIIsolationProvisionLostEventArgs2@234@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Windows::AI::IsolationEnvironment::IIsolationProvisionLostEventArgs,Windows::AI::IsolationEnvironment::IIsolationProvisionLostEventArgs2>::`vftable'{for `IWeakReferenceSource'}
0x18004bd5f  mov     [rdi+8], rax
0x18004bd63  lea     rax, ??_7?$RuntimeClass@UIIsolationProvisionLostEventArgs@IsolationEnvironment@AI@Windows@@UIIsolationProvisionLostEventArgs2@234@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIIsolationProvisionLostEventArgs2@IsolationEnvironment@AI@Windows@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::AI::IsolationEnvironment::IIsolationProvisionLostEventArgs,Windows::AI::IsolationEnvironment::IIsolationProvisionLostEventArgs2>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::AI::IsolationEnvironment::IIsolationProvisionLostEventArgs2>'}
0x18004bd6a  mov     [rdi+10h], rax
0x18004bd6e  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18004bd75  test    rcx, rcx
0x18004bd78  jz      short loc_18004BD87
0x18004bd7a  mov     rax, [rcx]
0x18004bd7d  mov     rax, [rax+8]
0x18004bd81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bd86  nop
0x18004bd87  lea     rax, ??_7ProvisionLostEventArgs@IsolationEnvironment@AI@Windows@@6B@; const Windows::AI::IsolationEnvironment::ProvisionLostEventArgs::`vftable'
0x18004bd8e  mov     [rdi], rax
0x18004bd91  lea     rax, ??_7ProvisionLostEventArgs@IsolationEnvironment@AI@Windows@@6BIWeakReferenceSource@@@; const Windows::AI::IsolationEnvironment::ProvisionLostEventArgs::`vftable'{for `IWeakReferenceSource'}
0x18004bd98  mov     [rdi+8], rax
0x18004bd9c  lea     rax, ??_7ProvisionLostEventArgs@IsolationEnvironment@AI@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIIsolationProvisionLostEventArgs2@IsolationEnvironment@AI@Windows@@@Details@WRL@Microsoft@@@; const Windows::AI::IsolationEnvironment::ProvisionLostEventArgs::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::AI::IsolationEnvironment::IIsolationProvisionLostEventArgs2>'}
0x18004bda3  mov     [rdi+10h], rax
0x18004bda7  lea     rcx, [rdi+30h]; string
0x18004bdab  mov     qword ptr [rcx], 0
0x18004bdb2  mov     qword ptr [rdi+38h], 0
0x18004bdba  mov     [rdi+28h], ebp
0x18004bdbd  cmp     qword ptr [rbx+18h], 7
0x18004bdc2  jbe     short loc_18004BDC7
0x18004bdc4  mov     rbx, [rbx]
0x18004bdc7  mov     [rsp+68h+var_48], rbx
0x18004bdcc  lea     rdx, [rsp+68h+var_48]
0x18004bdd1  call    ??$Set@PEB_W@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x18004bdd6  cmp     qword ptr [r14+18h], 7
0x18004bddb  jbe     short loc_18004BDE0
0x18004bddd  mov     r14, [r14]
0x18004bde0  mov     [rsp+68h+var_48], r14
0x18004bde5  lea     rdx, [rsp+68h+var_48]
0x18004bdea  lea     rcx, [rdi+38h]; string
0x18004bdee  call    ??$Set@PEB_W@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x18004bdf3  nop
0x18004bdf4  mov     rax, [rdi]
0x18004bdf7  mov     rcx, rdi
0x18004bdfa  mov     rax, [rax+8]
0x18004bdfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be03  nop
0x18004be04  mov     rax, [rdi]
0x18004be07  mov     rcx, rdi
0x18004be0a  mov     rax, [rax+10h]
0x18004be0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be13  nop
0x18004be14  test    rsi, rsi
0x18004be17  jz      short loc_18004BE29
0x18004be19  mov     rax, [rsi]
0x18004be1c  mov     rcx, rsi
0x18004be1f  mov     rax, [rax+8]
0x18004be23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be28  nop
0x18004be29  mov     ebx, cs:dword_1800B9160
0x18004be2f  mov     rbp, [rsp+68h]
0x18004be34  call    cs:__imp_GetCurrentThreadId
0x18004be3a  cmp     ebx, eax
0x18004be3c  jnz     loc_18004BEFB
0x18004be42  mov     cs:dword_1800B9160, 0
0x18004be4c  lea     rcx, ?g_lock@@3Vchecked_srwlock@@A; SRWLock
0x18004be53  call    cs:__imp_ReleaseSRWLockExclusive
0x18004be59  lea     rcx, [rsi+28h]
0x18004be5d  mov     r8, rdi
0x18004be60  mov     rdx, rsi
0x18004be63  call    ??$InvokeAll@PEAVAppConnection@IsolationEnvironment@AI@Windows@@PEAVProvisionLostEventArgs@234@@?$EventSource@U?$ITypedEventHandler@PEAVIsolationAppConnection@IsolationEnvironment@AI@Windows@@PEAVIsolationProvisionLostEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$01@WRL@Microsoft@@@WRL@Microsoft@@QEAAJPEAVAppConnection@IsolationEnvironment@AI@Windows@@PEAVProvisionLostEventArgs@456@@Z; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::AI::IsolationEnvironment::IsolationAppConnection *,Windows::AI::IsolationEnvironment::IsolationProvisionLostEventArgs *>,Microsoft::WRL::InvokeModeOptions<2>>::InvokeAll<Windows::AI::IsolationEnvironment::AppConnection *,Windows::AI::IsolationEnvironment::ProvisionLostEventArgs *>(Windows::AI::IsolationEnvironment::AppConnection *,Windows::AI::IsolationEnvironment::ProvisionLostEventArgs *)
0x18004be68  mov     ebx, cs:dword_1800B9160
0x18004be6e  call    cs:__imp_GetCurrentThreadId
0x18004be74  mov     ebp, eax
0x18004be76  mov     rcx, [rsp+68h]; this
0x18004be7b  cmp     ebx, eax
0x18004be7d  jz      short loc_18004BEE9
0x18004be7f  lea     rcx, ?g_lock@@3Vchecked_srwlock@@A; SRWLock
0x18004be86  call    cs:__imp_AcquireSRWLockExclusive
0x18004be8c  mov     cs:dword_1800B9160, ebp
0x18004be92  test    rsi, rsi
0x18004be95  jz      short loc_18004BEA7
0x18004be97  mov     rax, [rsi]
0x18004be9a  mov     rcx, rsi
0x18004be9d  mov     rax, [rax+10h]
0x18004bea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bea6  nop
0x18004bea7  mov     rax, [rdi]
0x18004beaa  mov     rcx, rdi
0x18004bead  mov     rax, [rax+10h]
0x18004beb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004beb6  nop
0x18004beb7  xor     eax, eax
0x18004beb9  jmp     short loc_18004BEDC
0x18004bebb  mov     rcx, [rsp+68h]; this
0x18004bec0  mov     ebx, 8007000Eh
0x18004bec5  mov     r9d, ebx; char *
0x18004bec8  lea     r8, aOnecoreuapWind_26; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004becf  mov     edx, 2Dh ; '-'; void *
0x18004bed4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bed9  nop
0x18004beda  mov     eax, ebx
0x18004bedc  add     rsp, 38h
0x18004bee0  pop     r15
0x18004bee2  pop     r14
0x18004bee4  pop     rdi
0x18004bee5  pop     rsi
0x18004bee6  pop     rbp
0x18004bee7  pop     rbx
0x18004bee8  retn
0x18004bee9  lea     r8, aOnecoreuapWind_13; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004bef0  mov     edx, 2Ch ; ','; void *
0x18004bef5  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18004befb  lea     r8, aOnecoreuapWind_13; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004bf02  mov     edx, 15Dh; void *
0x18004bf07  mov     rcx, rbp; this
0x18004bf0a  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
