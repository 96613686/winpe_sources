# CRemoteTextAppIntegration::OnFeatureModeUpdating(uint,uint,uint,Windows::UI::Internal::Text::Remote::RemoteTextTextInputFeature,int,Windows::UI::Internal::Text::Remote::RemoteTextEditControlRange,HSTRING__ *,uint)

- ea: `0x18001f120`
- end: `0x18001f360`
- name: `?OnFeatureModeUpdating@CRemoteTextAppIntegration@@UEAAJIIIW4RemoteTextTextInputFeature@Remote@Text@Internal@UI@Windows@@HURemoteTextEditControlRange@34567@PEAUHSTRING__@@I@Z`
- size: `576`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002270`
- `0x180003e44`
- `0x180006a14`
- `0x180018cd0`
- `0x18001f120`
- `0x180024b70`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f17b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f302`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f17b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f302`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f155`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f2cf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f155`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f2cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f27a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f27a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001f292`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001f292`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRemoteTextAppIntegration::OnFeatureModeUpdating(
        RTL_SRWLOCK *a1,
        int a2,
        int a3,
        int a4,
        int a5,
        int a6,
        __int64 a7,
        HSTRING string,
        int a9)
{
  RTL_SRWLOCK *v13; // r14
  __int64 v14; // rbx
  char *v15; // rax
  char *v16; // rdi
  _QWORD *v18; // rbx
  PVOID v19; // rbx
  _DWORD *Ptr; // rdx
  signed __int32 v21; // eax
  char *v22; // [rsp+20h] [rbp-68h] BYREF
  _QWORD v23[11]; // [rsp+30h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  RTL_SRWLOCK *v25; // [rsp+90h] [rbp+8h] BYREF

  v13 = a1 + 27;
  if ( a1[27].Ptr )
  {
    AcquireSRWLockExclusive(a1 + 28);
    if ( v13->Ptr )
      v14 = (__int64)(*((_QWORD *)v13->Ptr + 3) - *((_QWORD *)v13->Ptr + 2)) >> 3;
    else
      v14 = 0;
    if ( v13 != (RTL_SRWLOCK *)-8LL )
      ReleaseSRWLockExclusive(v13 + 1);
    if ( v14 )
    {
      v15 = (char *)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
      v16 = v15;
      if ( !v15 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x535,
          (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextappintegration\\lib\\remotetextappintegration.cpp",
          (const char *)0x8007000ELL,
          (int)v22);
        return 2147942414LL;
      }
      v18 = v15 + 16;
      Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v15 + 16));
      *((_QWORD *)v16 + 7) = 1;
      *(_QWORD *)v16 = &Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextFeatureModeUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable';
      *((_QWORD *)v16 + 1) = &CRemoteTextFeatureModeUpdatingEventArgs::`vftable'{for `IWeakReferenceSource'};
      *v18 = &Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextFeatureModeUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      *(_QWORD *)v16 = &CRemoteTextFeatureModeUpdatingEventArgs::`vftable';
      *((_QWORD *)v16 + 1) = &CRemoteTextFeatureModeUpdatingEventArgs::`vftable'{for `IWeakReferenceSource'};
      *v18 = &Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextFeatureModeUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
      *((_QWORD *)v16 + 12) = 0;
      *((_DWORD *)v16 + 16) = a2;
      *((_DWORD *)v16 + 17) = a3;
      *((_DWORD *)v16 + 18) = a4;
      *((_DWORD *)v16 + 19) = a5;
      *((_DWORD *)v16 + 20) = a6;
      *(_QWORD *)(v16 + 84) = a7;
      *((_DWORD *)v16 + 23) = a9;
      WindowsDeleteString(0);
      *((_QWORD *)v16 + 12) = 0;
      WindowsDuplicateString(string, (HSTRING *)v16 + 12);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v16 + 8LL))(v16);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v16 + 16LL))(v16);
      v22 = v16;
      v25 = a1 - 2;
      v19 = 0;
      AcquireSRWLockExclusive(v13 + 1);
      Ptr = v13->Ptr;
      if ( v13->Ptr )
      {
        v19 = v13->Ptr;
        do
          v21 = Ptr[3];
        while ( v21 != 0x7FFFFFFF && v21 != _InterlockedCompareExchange(Ptr + 3, v21 + 1, v21) );
      }
      if ( v13 != (RTL_SRWLOCK *)-8LL )
        ReleaseSRWLockExclusive(v13 + 1);
      if ( v19 )
      {
        v23[0] = &v25;
        v23[1] = &v22;
        Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_63f70fd3a6236e7362d86e89a2498b35_,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextNonComponentUIHostDetectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(
          v23,
          v19,
          v13);
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v19);
      }
      (*(void (__fastcall **)(char *))(*(_QWORD *)v16 + 16LL))(v16);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001f120  push    rbx
0x18001f122  push    rbp
0x18001f123  push    rsi
0x18001f124  push    rdi
0x18001f125  push    r12
0x18001f127  push    r13
0x18001f129  push    r14
0x18001f12b  push    r15
0x18001f12d  sub     rsp, 48h
0x18001f131  mov     r15d, r9d
0x18001f134  mov     r12d, r8d
0x18001f137  mov     r13d, edx
0x18001f13a  mov     rbp, rcx
0x18001f13d  lea     r14, [rcx+0D8h]
0x18001f144  cmp     qword ptr [r14], 0
0x18001f148  jz      loc_18001F34D
0x18001f14e  lea     rsi, [r14+8]
0x18001f152  mov     rcx, rsi; SRWLock
0x18001f155  call    cs:__imp_AcquireSRWLockExclusive
0x18001f15b  mov     rax, [r14]
0x18001f15e  test    rax, rax
0x18001f161  jnz     short loc_18001F167
0x18001f163  xor     ebx, ebx
0x18001f165  jmp     short loc_18001F173
0x18001f167  mov     rbx, [rax+18h]
0x18001f16b  sub     rbx, [rax+10h]
0x18001f16f  sar     rbx, 3
0x18001f173  test    rsi, rsi
0x18001f176  jz      short loc_18001F181
0x18001f178  mov     rcx, rsi; SRWLock
0x18001f17b  call    cs:__imp_ReleaseSRWLockExclusive
0x18001f181  test    rbx, rbx
0x18001f184  jz      loc_18001F34D
0x18001f18a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001f191  mov     ecx, 68h ; 'h'; unsigned __int64
0x18001f196  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001f19b  mov     rdi, rax
0x18001f19e  test    rax, rax
0x18001f1a1  jnz     short loc_18001F1CC
0x18001f1a3  mov     rcx, [rsp+88h]; this
0x18001f1ab  mov     ebx, 8007000Eh
0x18001f1b0  mov     r9d, ebx; char *
0x18001f1b3  lea     r8, aMincoreTextinp_14; "mincore\\textinput\\dev\\virtualization"...
0x18001f1ba  mov     edx, 535h; void *
0x18001f1bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f1c4  nop
0x18001f1c5  mov     eax, ebx
0x18001f1c7  jmp     loc_18001F34F
0x18001f1cc  lea     rbx, [rax+10h]
0x18001f1d0  mov     rcx, rbx; this
0x18001f1d3  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18001f1d8  mov     qword ptr [rdi+38h], 1
0x18001f1e0  lea     rax, ??_7?$RuntimeClass@UIRemoteTextFeatureModeUpdatingEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextFeatureModeUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable'
0x18001f1e7  mov     [rdi], rax
0x18001f1ea  lea     rax, ??_7CRemoteTextFeatureModeUpdatingEventArgs@@6BIWeakReferenceSource@@@; const CRemoteTextFeatureModeUpdatingEventArgs::`vftable'{for `IWeakReferenceSource'}
0x18001f1f1  mov     [rdi+8], rax
0x18001f1f5  lea     rax, ??_7?$RuntimeClass@UIRemoteTextFeatureModeUpdatingEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextFeatureModeUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001f1fc  mov     [rbx], rax
0x18001f1ff  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18001f206  test    rcx, rcx
0x18001f209  jz      short loc_18001F218
0x18001f20b  mov     rax, [rcx]
0x18001f20e  mov     rax, [rax+8]
0x18001f212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f217  nop
0x18001f218  lea     rax, ??_7CRemoteTextFeatureModeUpdatingEventArgs@@6B@; const CRemoteTextFeatureModeUpdatingEventArgs::`vftable'
0x18001f21f  mov     [rdi], rax
0x18001f222  lea     rax, ??_7CRemoteTextFeatureModeUpdatingEventArgs@@6BIWeakReferenceSource@@@; const CRemoteTextFeatureModeUpdatingEventArgs::`vftable'{for `IWeakReferenceSource'}
0x18001f229  mov     [rdi+8], rax
0x18001f22d  lea     rax, ??_7?$RuntimeClass@UIRemoteTextFeatureModeUpdatingEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextFeatureModeUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001f234  mov     [rbx], rax
0x18001f237  lea     rbx, [rdi+60h]
0x18001f23b  mov     qword ptr [rbx], 0
0x18001f242  mov     [rdi+40h], r13d
0x18001f246  mov     [rdi+44h], r12d
0x18001f24a  mov     [rdi+48h], r15d
0x18001f24e  mov     eax, [rsp+88h+arg_20]
0x18001f255  mov     [rdi+4Ch], eax
0x18001f258  mov     eax, [rsp+88h+arg_28]
0x18001f25f  mov     [rdi+50h], eax
0x18001f262  mov     rax, [rsp+88h+arg_30]
0x18001f26a  mov     [rdi+54h], rax
0x18001f26e  mov     eax, [rsp+88h+arg_40]
0x18001f275  mov     [rdi+5Ch], eax
0x18001f278  xor     ecx, ecx; string
0x18001f27a  call    cs:__imp_WindowsDeleteString
0x18001f280  mov     qword ptr [rbx], 0
0x18001f287  mov     rdx, rbx; newString
0x18001f28a  mov     rcx, [rsp+88h+string]; string
0x18001f292  call    cs:__imp_WindowsDuplicateString
0x18001f298  nop
0x18001f299  mov     rax, [rdi]
0x18001f29c  mov     rcx, rdi
0x18001f29f  mov     rax, [rax+8]
0x18001f2a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2a8  nop
0x18001f2a9  mov     rax, [rdi]
0x18001f2ac  mov     rcx, rdi
0x18001f2af  mov     rax, [rax+10h]
0x18001f2b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2b8  nop
0x18001f2b9  mov     [rsp+88h+var_68], rdi
0x18001f2be  lea     rax, [rbp-10h]
0x18001f2c2  mov     [rsp+88h+arg_0], rax
0x18001f2ca  xor     ebx, ebx
0x18001f2cc  mov     rcx, rsi; SRWLock
0x18001f2cf  call    cs:__imp_AcquireSRWLockExclusive
0x18001f2d5  mov     rdx, [r14]
0x18001f2d8  test    rdx, rdx
0x18001f2db  jz      short loc_18001F2FA
0x18001f2dd  mov     rbx, rdx
0x18001f2e0  mov     r8d, 7FFFFFFFh
0x18001f2e6  jmp     short loc_18001F2F2
0x18001f2e8  lea     ecx, [rax+1]
0x18001f2eb  lock cmpxchg [rdx+0Ch], ecx
0x18001f2f0  jz      short loc_18001F2FA
0x18001f2f2  mov     eax, [rdx+0Ch]
0x18001f2f5  cmp     eax, r8d
0x18001f2f8  jnz     short loc_18001F2E8
0x18001f2fa  test    rsi, rsi
0x18001f2fd  jz      short loc_18001F308
0x18001f2ff  mov     rcx, rsi; SRWLock
0x18001f302  call    cs:__imp_ReleaseSRWLockExclusive
0x18001f308  test    rbx, rbx
0x18001f30b  jz      short loc_18001F33D
0x18001f30d  lea     rax, [rsp+88h+arg_0]
0x18001f315  mov     [rsp+88h+var_58], rax
0x18001f31a  lea     rax, [rsp+88h+var_68]
0x18001f31f  mov     [rsp+88h+var_50], rax
0x18001f324  mov     r8, r14
0x18001f327  mov     rdx, rbx
0x18001f32a  lea     rcx, [rsp+88h+var_58]
0x18001f32f  call    ??$InvokeDelegates@V_lambda_63f70fd3a6236e7362d86e89a2498b35_@@U?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextNonComponentUIHostDetectedEventArgs@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@?$InvokeTraits@$0?1@WRL@Microsoft@@SAJV_lambda_63f70fd3a6236e7362d86e89a2498b35_@@PEAVEventTargetArray@Details@12@PEAV?$EventSource@U?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextNonComponentUIHostDetectedEventArgs@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@12@@Z; Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_63f70fd3a6236e7362d86e89a2498b35_,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextNonComponentUIHostDetectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(_lambda_63f70fd3a6236e7362d86e89a2498b35_,Microsoft::WRL::Details::EventTargetArray *,Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextNonComponentUIHostDetectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> *)
0x18001f334  mov     rcx, rbx
0x18001f337  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001f33c  nop
0x18001f33d  mov     rax, [rdi]
0x18001f340  mov     rcx, rdi
0x18001f343  mov     rax, [rax+10h]
0x18001f347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f34c  nop
0x18001f34d  xor     eax, eax
0x18001f34f  add     rsp, 48h
0x18001f353  pop     r15
0x18001f355  pop     r14
0x18001f357  pop     r13
0x18001f359  pop     r12
0x18001f35b  pop     rdi
0x18001f35c  pop     rsi
0x18001f35d  pop     rbp
0x18001f35e  pop     rbx
0x18001f35f  retn
```
