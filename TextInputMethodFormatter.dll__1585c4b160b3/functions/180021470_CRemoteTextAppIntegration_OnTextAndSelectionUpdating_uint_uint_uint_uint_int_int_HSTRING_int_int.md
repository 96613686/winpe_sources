# CRemoteTextAppIntegration::OnTextAndSelectionUpdating(uint,uint,uint,uint,int,int,HSTRING__ *,int,int)

- ea: `0x180021470`
- end: `0x1800216b9`
- name: `?OnTextAndSelectionUpdating@CRemoteTextAppIntegration@@UEAAJIIIIHHPEAUHSTRING__@@HH@Z`
- size: `585`
- prototype: `__int64 __fastcall(CRemoteTextAppIntegration *__hidden this, unsigned int, unsigned int, unsigned int, unsigned int, int, int, HSTRING string, int, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002270`
- `0x180003e44`
- `0x180006a14`
- `0x180018cd0`
- `0x180021470`
- `0x180024b70`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800214cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002165b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800214cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002165b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800214a5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180021628`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800214a5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180021628`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800215c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800215c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800215d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800215d8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRemoteTextAppIntegration::OnTextAndSelectionUpdating(
        RTL_SRWLOCK *this,
        int a2,
        int a3,
        int a4,
        unsigned int a5,
        int a6,
        int a7,
        HSTRING string,
        int a9,
        int a10)
{
  RTL_SRWLOCK *v14; // r14
  __int64 v15; // rbx
  char *v16; // rax
  char *v17; // rdi
  _QWORD *v19; // rbx
  PVOID v20; // rbx
  _DWORD *Ptr; // rdx
  signed __int32 v22; // eax
  char *v23; // [rsp+20h] [rbp-68h] BYREF
  _QWORD v24[11]; // [rsp+30h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  RTL_SRWLOCK *v26; // [rsp+90h] [rbp+8h] BYREF

  v14 = this + 75;
  if ( this[75].Ptr )
  {
    AcquireSRWLockExclusive(this + 76);
    if ( v14->Ptr )
      v15 = (__int64)(*((_QWORD *)v14->Ptr + 3) - *((_QWORD *)v14->Ptr + 2)) >> 3;
    else
      v15 = 0;
    if ( v14 != (RTL_SRWLOCK *)-8LL )
      ReleaseSRWLockExclusive(v14 + 1);
    if ( v15 )
    {
      v16 = (char *)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
      v17 = v16;
      if ( !v16 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x616,
          (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextappintegration\\lib\\remotetextappintegration.cpp",
          (const char *)0x8007000ELL,
          (int)v23);
        return 2147942414LL;
      }
      v19 = v16 + 16;
      Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v16 + 16));
      *((_QWORD *)v17 + 7) = 1;
      *(_QWORD *)v17 = &Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextTextAndSelectionUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable';
      *((_QWORD *)v17 + 1) = &CRemoteTextTextAndSelectionUpdatingEventArgs::`vftable'{for `IWeakReferenceSource'};
      *v19 = &Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextTextAndSelectionUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      *(_QWORD *)v17 = &CRemoteTextTextAndSelectionUpdatingEventArgs::`vftable';
      *((_QWORD *)v17 + 1) = &CRemoteTextTextAndSelectionUpdatingEventArgs::`vftable'{for `IWeakReferenceSource'};
      *v19 = &Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextTextAndSelectionUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
      *((_QWORD *)v17 + 11) = 0;
      *((_QWORD *)v17 + 12) = 0;
      *((_DWORD *)v17 + 16) = a2;
      *((_DWORD *)v17 + 17) = a3;
      *((_DWORD *)v17 + 18) = a4;
      *((_DWORD *)v17 + 19) = a5;
      *((_DWORD *)v17 + 20) = a6;
      *((_DWORD *)v17 + 21) = a7;
      WindowsDeleteString(0);
      *((_QWORD *)v17 + 11) = 0;
      WindowsDuplicateString(string, (HSTRING *)v17 + 11);
      *((_DWORD *)v17 + 24) = a9;
      *((_DWORD *)v17 + 25) = a10;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v17 + 8LL))(v17);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v17 + 16LL))(v17);
      v23 = v17;
      v26 = this - 2;
      v20 = 0;
      AcquireSRWLockExclusive(v14 + 1);
      Ptr = v14->Ptr;
      if ( v14->Ptr )
      {
        v20 = v14->Ptr;
        do
          v22 = Ptr[3];
        while ( v22 != 0x7FFFFFFF && v22 != _InterlockedCompareExchange(Ptr + 3, v22 + 1, v22) );
      }
      if ( v14 != (RTL_SRWLOCK *)-8LL )
        ReleaseSRWLockExclusive(v14 + 1);
      if ( v20 )
      {
        v24[0] = &v26;
        v24[1] = &v23;
        Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_63f70fd3a6236e7362d86e89a2498b35_,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextNonComponentUIHostDetectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(
          v24,
          v20,
          v14);
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v20);
      }
      (*(void (__fastcall **)(char *))(*(_QWORD *)v17 + 16LL))(v17);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180021470  push    rbx
0x180021472  push    rbp
0x180021473  push    rsi
0x180021474  push    rdi
0x180021475  push    r12
0x180021477  push    r13
0x180021479  push    r14
0x18002147b  push    r15
0x18002147d  sub     rsp, 48h
0x180021481  mov     r15d, r9d
0x180021484  mov     r12d, r8d
0x180021487  mov     r13d, edx
0x18002148a  mov     rbp, rcx
0x18002148d  lea     r14, [rcx+258h]
0x180021494  cmp     qword ptr [r14], 0
0x180021498  jz      loc_1800216A6
0x18002149e  lea     rsi, [r14+8]
0x1800214a2  mov     rcx, rsi; SRWLock
0x1800214a5  call    cs:__imp_AcquireSRWLockExclusive
0x1800214ab  mov     rax, [r14]
0x1800214ae  test    rax, rax
0x1800214b1  jnz     short loc_1800214B7
0x1800214b3  xor     ebx, ebx
0x1800214b5  jmp     short loc_1800214C3
0x1800214b7  mov     rbx, [rax+18h]
0x1800214bb  sub     rbx, [rax+10h]
0x1800214bf  sar     rbx, 3
0x1800214c3  test    rsi, rsi
0x1800214c6  jz      short loc_1800214D1
0x1800214c8  mov     rcx, rsi; SRWLock
0x1800214cb  call    cs:__imp_ReleaseSRWLockExclusive
0x1800214d1  test    rbx, rbx
0x1800214d4  jz      loc_1800216A6
0x1800214da  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800214e1  mov     ecx, 68h ; 'h'; unsigned __int64
0x1800214e6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800214eb  mov     rdi, rax
0x1800214ee  test    rax, rax
0x1800214f1  jnz     short loc_18002151C
0x1800214f3  mov     rcx, [rsp+88h]; this
0x1800214fb  mov     ebx, 8007000Eh
0x180021500  mov     r9d, ebx; char *
0x180021503  lea     r8, aMincoreTextinp_14; "mincore\\textinput\\dev\\virtualization"...
0x18002150a  mov     edx, 616h; void *
0x18002150f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021514  nop
0x180021515  mov     eax, ebx
0x180021517  jmp     loc_1800216A8
0x18002151c  lea     rbx, [rax+10h]
0x180021520  mov     rcx, rbx; this
0x180021523  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180021528  mov     qword ptr [rdi+38h], 1
0x180021530  lea     rax, ??_7?$RuntimeClass@UIRemoteTextTextAndSelectionUpdatingEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextTextAndSelectionUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable'
0x180021537  mov     [rdi], rax
0x18002153a  lea     rax, ??_7CRemoteTextTextAndSelectionUpdatingEventArgs@@6BIWeakReferenceSource@@@; const CRemoteTextTextAndSelectionUpdatingEventArgs::`vftable'{for `IWeakReferenceSource'}
0x180021541  mov     [rdi+8], rax
0x180021545  lea     rax, ??_7?$RuntimeClass@UIRemoteTextTextAndSelectionUpdatingEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextTextAndSelectionUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18002154c  mov     [rbx], rax
0x18002154f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180021556  test    rcx, rcx
0x180021559  jz      short loc_180021568
0x18002155b  mov     rax, [rcx]
0x18002155e  mov     rax, [rax+8]
0x180021562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021567  nop
0x180021568  lea     rax, ??_7CRemoteTextTextAndSelectionUpdatingEventArgs@@6B@; const CRemoteTextTextAndSelectionUpdatingEventArgs::`vftable'
0x18002156f  mov     [rdi], rax
0x180021572  lea     rax, ??_7CRemoteTextTextAndSelectionUpdatingEventArgs@@6BIWeakReferenceSource@@@; const CRemoteTextTextAndSelectionUpdatingEventArgs::`vftable'{for `IWeakReferenceSource'}
0x180021579  mov     [rdi+8], rax
0x18002157d  lea     rax, ??_7?$RuntimeClass@UIRemoteTextTextAndSelectionUpdatingEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextTextAndSelectionUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180021584  mov     [rbx], rax
0x180021587  lea     rbx, [rdi+58h]
0x18002158b  xor     eax, eax
0x18002158d  mov     [rbx], rax
0x180021590  mov     [rdi+60h], rax
0x180021594  mov     [rdi+40h], r13d
0x180021598  mov     [rdi+44h], r12d
0x18002159c  mov     [rdi+48h], r15d
0x1800215a0  mov     eax, [rsp+88h+arg_20]
0x1800215a7  mov     [rdi+4Ch], eax
0x1800215aa  mov     eax, [rsp+88h+arg_28]
0x1800215b1  mov     [rdi+50h], eax
0x1800215b4  mov     eax, [rsp+88h+arg_30]
0x1800215bb  mov     [rdi+54h], eax
0x1800215be  xor     ecx, ecx; string
0x1800215c0  call    cs:__imp_WindowsDeleteString
0x1800215c6  mov     qword ptr [rbx], 0
0x1800215cd  mov     rdx, rbx; newString
0x1800215d0  mov     rcx, [rsp+88h+string]; string
0x1800215d8  call    cs:__imp_WindowsDuplicateString
0x1800215de  mov     eax, [rsp+88h+arg_40]
0x1800215e5  mov     [rdi+60h], eax
0x1800215e8  mov     eax, [rsp+88h+arg_48]
0x1800215ef  mov     [rdi+64h], eax
0x1800215f2  mov     rax, [rdi]
0x1800215f5  mov     rcx, rdi
0x1800215f8  mov     rax, [rax+8]
0x1800215fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021601  nop
0x180021602  mov     rax, [rdi]
0x180021605  mov     rcx, rdi
0x180021608  mov     rax, [rax+10h]
0x18002160c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021611  nop
0x180021612  mov     [rsp+88h+var_68], rdi
0x180021617  lea     rax, [rbp-10h]
0x18002161b  mov     [rsp+88h+arg_0], rax
0x180021623  xor     ebx, ebx
0x180021625  mov     rcx, rsi; SRWLock
0x180021628  call    cs:__imp_AcquireSRWLockExclusive
0x18002162e  mov     rdx, [r14]
0x180021631  test    rdx, rdx
0x180021634  jz      short loc_180021653
0x180021636  mov     rbx, rdx
0x180021639  mov     r8d, 7FFFFFFFh
0x18002163f  jmp     short loc_18002164B
0x180021641  lea     ecx, [rax+1]
0x180021644  lock cmpxchg [rdx+0Ch], ecx
0x180021649  jz      short loc_180021653
0x18002164b  mov     eax, [rdx+0Ch]
0x18002164e  cmp     eax, r8d
0x180021651  jnz     short loc_180021641
0x180021653  test    rsi, rsi
0x180021656  jz      short loc_180021661
0x180021658  mov     rcx, rsi; SRWLock
0x18002165b  call    cs:__imp_ReleaseSRWLockExclusive
0x180021661  test    rbx, rbx
0x180021664  jz      short loc_180021696
0x180021666  lea     rax, [rsp+88h+arg_0]
0x18002166e  mov     [rsp+88h+var_58], rax
0x180021673  lea     rax, [rsp+88h+var_68]
0x180021678  mov     [rsp+88h+var_50], rax
0x18002167d  mov     r8, r14
0x180021680  mov     rdx, rbx
0x180021683  lea     rcx, [rsp+88h+var_58]
0x180021688  call    ??$InvokeDelegates@V_lambda_63f70fd3a6236e7362d86e89a2498b35_@@U?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextNonComponentUIHostDetectedEventArgs@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@?$InvokeTraits@$0?1@WRL@Microsoft@@SAJV_lambda_63f70fd3a6236e7362d86e89a2498b35_@@PEAVEventTargetArray@Details@12@PEAV?$EventSource@U?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextNonComponentUIHostDetectedEventArgs@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@12@@Z; Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_63f70fd3a6236e7362d86e89a2498b35_,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextNonComponentUIHostDetectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(_lambda_63f70fd3a6236e7362d86e89a2498b35_,Microsoft::WRL::Details::EventTargetArray *,Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextNonComponentUIHostDetectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> *)
0x18002168d  mov     rcx, rbx
0x180021690  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180021695  nop
0x180021696  mov     rax, [rdi]
0x180021699  mov     rcx, rdi
0x18002169c  mov     rax, [rax+10h]
0x1800216a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216a5  nop
0x1800216a6  xor     eax, eax
0x1800216a8  add     rsp, 48h
0x1800216ac  pop     r15
0x1800216ae  pop     r14
0x1800216b0  pop     r13
0x1800216b2  pop     r12
0x1800216b4  pop     rdi
0x1800216b5  pop     rsi
0x1800216b6  pop     rbp
0x1800216b7  pop     rbx
0x1800216b8  retn
```
