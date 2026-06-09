# CRemoteTextAppIntegration::OnTextUpdating(uint,uint,uint,uint,int,int,HSTRING__ *)

- ea: `0x1800216c0`
- end: `0x1800218f4`
- name: `?OnTextUpdating@CRemoteTextAppIntegration@@UEAAJIIIIHHPEAUHSTRING__@@@Z`
- size: `564`
- prototype: `__int64 __fastcall(CRemoteTextAppIntegration *__hidden this, unsigned int, unsigned int, unsigned int, unsigned int, int, int, HSTRING string)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002270`
- `0x180003e44`
- `0x180006a14`
- `0x180018cd0`
- `0x1800216c0`
- `0x180024b70`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002171b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021896`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002171b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021896`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800216f5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180021863`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800216f5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180021863`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002180e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002180e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180021826`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180021826`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRemoteTextAppIntegration::OnTextUpdating(
        RTL_SRWLOCK *this,
        int a2,
        int a3,
        int a4,
        unsigned int a5,
        int a6,
        int a7,
        HSTRING string)
{
  RTL_SRWLOCK *v12; // r14
  __int64 v13; // rbx
  char *v14; // rax
  char *v15; // rdi
  _QWORD *v17; // rbx
  PVOID v18; // rbx
  _DWORD *Ptr; // rdx
  signed __int32 v20; // eax
  char *v21; // [rsp+20h] [rbp-68h] BYREF
  _QWORD v22[11]; // [rsp+30h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  RTL_SRWLOCK *v24; // [rsp+90h] [rbp+8h] BYREF

  v12 = this + 18;
  if ( this[18].Ptr )
  {
    AcquireSRWLockExclusive(this + 19);
    if ( v12->Ptr )
      v13 = (__int64)(*((_QWORD *)v12->Ptr + 3) - *((_QWORD *)v12->Ptr + 2)) >> 3;
    else
      v13 = 0;
    if ( v12 != (RTL_SRWLOCK *)-8LL )
      ReleaseSRWLockExclusive(v12 + 1);
    if ( v13 )
    {
      v14 = (char *)operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
      v15 = v14;
      if ( !v14 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x50C,
          (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextappintegration\\lib\\remotetextappintegration.cpp",
          (const char *)0x8007000ELL,
          (int)v21);
        return 2147942414LL;
      }
      v17 = v14 + 16;
      Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v14 + 16));
      *((_QWORD *)v15 + 7) = 1;
      *(_QWORD *)v15 = &Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextTextUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable';
      *((_QWORD *)v15 + 1) = &CRemoteTextTextUpdatingEventArgs::`vftable'{for `IWeakReferenceSource'};
      *v17 = &Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextTextUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      *(_QWORD *)v15 = &CRemoteTextTextUpdatingEventArgs::`vftable';
      *((_QWORD *)v15 + 1) = &CRemoteTextTextUpdatingEventArgs::`vftable'{for `IWeakReferenceSource'};
      *v17 = &Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextTextUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
      *((_QWORD *)v15 + 11) = 0;
      *((_DWORD *)v15 + 16) = a2;
      *((_DWORD *)v15 + 17) = a3;
      *((_DWORD *)v15 + 18) = a4;
      *((_DWORD *)v15 + 19) = a5;
      *((_DWORD *)v15 + 20) = a6;
      *((_DWORD *)v15 + 21) = a7;
      WindowsDeleteString(0);
      *((_QWORD *)v15 + 11) = 0;
      WindowsDuplicateString(string, (HSTRING *)v15 + 11);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v15 + 8LL))(v15);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))(v15);
      v21 = v15;
      v24 = this - 2;
      v18 = 0;
      AcquireSRWLockExclusive(v12 + 1);
      Ptr = v12->Ptr;
      if ( v12->Ptr )
      {
        v18 = v12->Ptr;
        do
          v20 = Ptr[3];
        while ( v20 != 0x7FFFFFFF && v20 != _InterlockedCompareExchange(Ptr + 3, v20 + 1, v20) );
      }
      if ( v12 != (RTL_SRWLOCK *)-8LL )
        ReleaseSRWLockExclusive(v12 + 1);
      if ( v18 )
      {
        v22[0] = &v24;
        v22[1] = &v21;
        Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_63f70fd3a6236e7362d86e89a2498b35_,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextNonComponentUIHostDetectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(
          v22,
          v18,
          v12);
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v18);
      }
      (*(void (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))(v15);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800216c0  push    rbx
0x1800216c2  push    rbp
0x1800216c3  push    rsi
0x1800216c4  push    rdi
0x1800216c5  push    r12
0x1800216c7  push    r13
0x1800216c9  push    r14
0x1800216cb  push    r15
0x1800216cd  sub     rsp, 48h
0x1800216d1  mov     r15d, r9d
0x1800216d4  mov     r12d, r8d
0x1800216d7  mov     r13d, edx
0x1800216da  mov     rbp, rcx
0x1800216dd  lea     r14, [rcx+90h]
0x1800216e4  cmp     qword ptr [r14], 0
0x1800216e8  jz      loc_1800218E1
0x1800216ee  lea     rsi, [r14+8]
0x1800216f2  mov     rcx, rsi; SRWLock
0x1800216f5  call    cs:__imp_AcquireSRWLockExclusive
0x1800216fb  mov     rax, [r14]
0x1800216fe  test    rax, rax
0x180021701  jnz     short loc_180021707
0x180021703  xor     ebx, ebx
0x180021705  jmp     short loc_180021713
0x180021707  mov     rbx, [rax+18h]
0x18002170b  sub     rbx, [rax+10h]
0x18002170f  sar     rbx, 3
0x180021713  test    rsi, rsi
0x180021716  jz      short loc_180021721
0x180021718  mov     rcx, rsi; SRWLock
0x18002171b  call    cs:__imp_ReleaseSRWLockExclusive
0x180021721  test    rbx, rbx
0x180021724  jz      loc_1800218E1
0x18002172a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180021731  mov     ecx, 60h ; '`'; unsigned __int64
0x180021736  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002173b  mov     rdi, rax
0x18002173e  test    rax, rax
0x180021741  jnz     short loc_18002176C
0x180021743  mov     rcx, [rsp+88h]; this
0x18002174b  mov     ebx, 8007000Eh
0x180021750  mov     r9d, ebx; char *
0x180021753  lea     r8, aMincoreTextinp_14; "mincore\\textinput\\dev\\virtualization"...
0x18002175a  mov     edx, 50Ch; void *
0x18002175f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021764  nop
0x180021765  mov     eax, ebx
0x180021767  jmp     loc_1800218E3
0x18002176c  lea     rbx, [rax+10h]
0x180021770  mov     rcx, rbx; this
0x180021773  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180021778  mov     qword ptr [rdi+38h], 1
0x180021780  lea     rax, ??_7?$RuntimeClass@UIRemoteTextTextUpdatingEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextTextUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable'
0x180021787  mov     [rdi], rax
0x18002178a  lea     rax, ??_7CRemoteTextTextUpdatingEventArgs@@6BIWeakReferenceSource@@@; const CRemoteTextTextUpdatingEventArgs::`vftable'{for `IWeakReferenceSource'}
0x180021791  mov     [rdi+8], rax
0x180021795  lea     rax, ??_7?$RuntimeClass@UIRemoteTextTextUpdatingEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextTextUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18002179c  mov     [rbx], rax
0x18002179f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800217a6  test    rcx, rcx
0x1800217a9  jz      short loc_1800217B8
0x1800217ab  mov     rax, [rcx]
0x1800217ae  mov     rax, [rax+8]
0x1800217b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800217b7  nop
0x1800217b8  lea     rax, ??_7CRemoteTextTextUpdatingEventArgs@@6B@; const CRemoteTextTextUpdatingEventArgs::`vftable'
0x1800217bf  mov     [rdi], rax
0x1800217c2  lea     rax, ??_7CRemoteTextTextUpdatingEventArgs@@6BIWeakReferenceSource@@@; const CRemoteTextTextUpdatingEventArgs::`vftable'{for `IWeakReferenceSource'}
0x1800217c9  mov     [rdi+8], rax
0x1800217cd  lea     rax, ??_7?$RuntimeClass@UIRemoteTextTextUpdatingEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextTextUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800217d4  mov     [rbx], rax
0x1800217d7  lea     rbx, [rdi+58h]
0x1800217db  mov     qword ptr [rbx], 0
0x1800217e2  mov     [rdi+40h], r13d
0x1800217e6  mov     [rdi+44h], r12d
0x1800217ea  mov     [rdi+48h], r15d
0x1800217ee  mov     eax, [rsp+88h+arg_20]
0x1800217f5  mov     [rdi+4Ch], eax
0x1800217f8  mov     eax, [rsp+88h+arg_28]
0x1800217ff  mov     [rdi+50h], eax
0x180021802  mov     eax, [rsp+88h+arg_30]
0x180021809  mov     [rdi+54h], eax
0x18002180c  xor     ecx, ecx; string
0x18002180e  call    cs:__imp_WindowsDeleteString
0x180021814  mov     qword ptr [rbx], 0
0x18002181b  mov     rdx, rbx; newString
0x18002181e  mov     rcx, [rsp+88h+string]; string
0x180021826  call    cs:__imp_WindowsDuplicateString
0x18002182c  nop
0x18002182d  mov     rax, [rdi]
0x180021830  mov     rcx, rdi
0x180021833  mov     rax, [rax+8]
0x180021837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002183c  nop
0x18002183d  mov     rax, [rdi]
0x180021840  mov     rcx, rdi
0x180021843  mov     rax, [rax+10h]
0x180021847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002184c  nop
0x18002184d  mov     [rsp+88h+var_68], rdi
0x180021852  lea     rax, [rbp-10h]
0x180021856  mov     [rsp+88h+arg_0], rax
0x18002185e  xor     ebx, ebx
0x180021860  mov     rcx, rsi; SRWLock
0x180021863  call    cs:__imp_AcquireSRWLockExclusive
0x180021869  mov     rdx, [r14]
0x18002186c  test    rdx, rdx
0x18002186f  jz      short loc_18002188E
0x180021871  mov     rbx, rdx
0x180021874  mov     r8d, 7FFFFFFFh
0x18002187a  jmp     short loc_180021886
0x18002187c  lea     ecx, [rax+1]
0x18002187f  lock cmpxchg [rdx+0Ch], ecx
0x180021884  jz      short loc_18002188E
0x180021886  mov     eax, [rdx+0Ch]
0x180021889  cmp     eax, r8d
0x18002188c  jnz     short loc_18002187C
0x18002188e  test    rsi, rsi
0x180021891  jz      short loc_18002189C
0x180021893  mov     rcx, rsi; SRWLock
0x180021896  call    cs:__imp_ReleaseSRWLockExclusive
0x18002189c  test    rbx, rbx
0x18002189f  jz      short loc_1800218D1
0x1800218a1  lea     rax, [rsp+88h+arg_0]
0x1800218a9  mov     [rsp+88h+var_58], rax
0x1800218ae  lea     rax, [rsp+88h+var_68]
0x1800218b3  mov     [rsp+88h+var_50], rax
0x1800218b8  mov     r8, r14
0x1800218bb  mov     rdx, rbx
0x1800218be  lea     rcx, [rsp+88h+var_58]
0x1800218c3  call    ??$InvokeDelegates@V_lambda_63f70fd3a6236e7362d86e89a2498b35_@@U?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextNonComponentUIHostDetectedEventArgs@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@?$InvokeTraits@$0?1@WRL@Microsoft@@SAJV_lambda_63f70fd3a6236e7362d86e89a2498b35_@@PEAVEventTargetArray@Details@12@PEAV?$EventSource@U?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextNonComponentUIHostDetectedEventArgs@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@12@@Z; Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_63f70fd3a6236e7362d86e89a2498b35_,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextNonComponentUIHostDetectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(_lambda_63f70fd3a6236e7362d86e89a2498b35_,Microsoft::WRL::Details::EventTargetArray *,Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextNonComponentUIHostDetectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> *)
0x1800218c8  mov     rcx, rbx
0x1800218cb  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x1800218d0  nop
0x1800218d1  mov     rax, [rdi]
0x1800218d4  mov     rcx, rdi
0x1800218d7  mov     rax, [rax+10h]
0x1800218db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218e0  nop
0x1800218e1  xor     eax, eax
0x1800218e3  add     rsp, 48h
0x1800218e7  pop     r15
0x1800218e9  pop     r14
0x1800218eb  pop     r13
0x1800218ed  pop     r12
0x1800218ef  pop     rdi
0x1800218f0  pop     rsi
0x1800218f1  pop     rbp
0x1800218f2  pop     rbx
0x1800218f3  retn
```
