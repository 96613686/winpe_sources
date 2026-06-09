# CRemoteTextAppIntegration::OnCompositionInfoUpdating(uint,uint,uint,uint,Windows::UI::Internal::Text::Remote::RemoteTextEditControlRange,HSTRING__ *)

- ea: `0x18001e2c0`
- end: `0x18001e4ec`
- name: `?OnCompositionInfoUpdating@CRemoteTextAppIntegration@@UEAAJIIIIURemoteTextEditControlRange@Remote@Text@Internal@UI@Windows@@PEAUHSTRING__@@@Z`
- size: `556`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002270`
- `0x180003e44`
- `0x180006a14`
- `0x180018cd0`
- `0x18001e2c0`
- `0x180024b70`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e31b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e48e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e31b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e48e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e2f5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e45b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e2f5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e45b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e406`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e406`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001e41e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001e41e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRemoteTextAppIntegration::OnCompositionInfoUpdating(
        RTL_SRWLOCK *a1,
        int a2,
        int a3,
        int a4,
        int a5,
        __int64 a6,
        HSTRING string)
{
  RTL_SRWLOCK *v11; // r14
  __int64 v12; // rbx
  char *v13; // rax
  char *v14; // rdi
  _QWORD *v16; // rbx
  PVOID v17; // rbx
  _DWORD *Ptr; // rdx
  signed __int32 v19; // eax
  char *v20; // [rsp+20h] [rbp-68h] BYREF
  _QWORD v21[11]; // [rsp+30h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  RTL_SRWLOCK *v23; // [rsp+90h] [rbp+8h] BYREF

  v11 = a1 + 42;
  if ( a1[42].Ptr )
  {
    AcquireSRWLockExclusive(a1 + 43);
    if ( v11->Ptr )
      v12 = (__int64)(*((_QWORD *)v11->Ptr + 3) - *((_QWORD *)v11->Ptr + 2)) >> 3;
    else
      v12 = 0;
    if ( v11 != (RTL_SRWLOCK *)-8LL )
      ReleaseSRWLockExclusive(v11 + 1);
    if ( v12 )
    {
      v13 = (char *)operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
      v14 = v13;
      if ( !v13 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x578,
          (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextappintegration\\lib\\remotetextappintegration.cpp",
          (const char *)0x8007000ELL,
          (int)v20);
        return 2147942414LL;
      }
      v16 = v13 + 16;
      Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v13 + 16));
      *((_QWORD *)v14 + 7) = 1;
      *(_QWORD *)v14 = &Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextCompositionInfoUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable';
      *((_QWORD *)v14 + 1) = &Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextCompositionInfoUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'};
      *v16 = &Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextCompositionInfoUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      *(_QWORD *)v14 = &CRemoteTextCompositionInfoUpdatingEventArgs::`vftable';
      *((_QWORD *)v14 + 1) = &Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextCompositionInfoUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'};
      *v16 = &Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextCompositionInfoUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
      *((_QWORD *)v14 + 11) = 0;
      *((_DWORD *)v14 + 16) = a2;
      *((_DWORD *)v14 + 17) = a3;
      *((_DWORD *)v14 + 18) = a4;
      *((_DWORD *)v14 + 19) = a5;
      *((_QWORD *)v14 + 10) = a6;
      WindowsDeleteString(0);
      *((_QWORD *)v14 + 11) = 0;
      WindowsDuplicateString(string, (HSTRING *)v14 + 11);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v14 + 8LL))(v14);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))(v14);
      v20 = v14;
      v23 = a1 - 2;
      v17 = 0;
      AcquireSRWLockExclusive(v11 + 1);
      Ptr = v11->Ptr;
      if ( v11->Ptr )
      {
        v17 = v11->Ptr;
        do
          v19 = Ptr[3];
        while ( v19 != 0x7FFFFFFF && v19 != _InterlockedCompareExchange(Ptr + 3, v19 + 1, v19) );
      }
      if ( v11 != (RTL_SRWLOCK *)-8LL )
        ReleaseSRWLockExclusive(v11 + 1);
      if ( v17 )
      {
        v21[0] = &v23;
        v21[1] = &v20;
        Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_63f70fd3a6236e7362d86e89a2498b35_,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextNonComponentUIHostDetectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(
          v21,
          v17,
          v11);
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v17);
      }
      (*(void (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))(v14);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001e2c0  push    rbx
0x18001e2c2  push    rbp
0x18001e2c3  push    rsi
0x18001e2c4  push    rdi
0x18001e2c5  push    r12
0x18001e2c7  push    r13
0x18001e2c9  push    r14
0x18001e2cb  push    r15
0x18001e2cd  sub     rsp, 48h
0x18001e2d1  mov     r15d, r9d
0x18001e2d4  mov     r12d, r8d
0x18001e2d7  mov     r13d, edx
0x18001e2da  mov     rbp, rcx
0x18001e2dd  lea     r14, [rcx+150h]
0x18001e2e4  cmp     qword ptr [r14], 0
0x18001e2e8  jz      loc_18001E4D9
0x18001e2ee  lea     rsi, [r14+8]
0x18001e2f2  mov     rcx, rsi; SRWLock
0x18001e2f5  call    cs:__imp_AcquireSRWLockExclusive
0x18001e2fb  mov     rax, [r14]
0x18001e2fe  test    rax, rax
0x18001e301  jnz     short loc_18001E307
0x18001e303  xor     ebx, ebx
0x18001e305  jmp     short loc_18001E313
0x18001e307  mov     rbx, [rax+18h]
0x18001e30b  sub     rbx, [rax+10h]
0x18001e30f  sar     rbx, 3
0x18001e313  test    rsi, rsi
0x18001e316  jz      short loc_18001E321
0x18001e318  mov     rcx, rsi; SRWLock
0x18001e31b  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e321  test    rbx, rbx
0x18001e324  jz      loc_18001E4D9
0x18001e32a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001e331  mov     ecx, 60h ; '`'; unsigned __int64
0x18001e336  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001e33b  mov     rdi, rax
0x18001e33e  test    rax, rax
0x18001e341  jnz     short loc_18001E36C
0x18001e343  mov     rcx, [rsp+88h]; this
0x18001e34b  mov     ebx, 8007000Eh
0x18001e350  mov     r9d, ebx; char *
0x18001e353  lea     r8, aMincoreTextinp_14; "mincore\\textinput\\dev\\virtualization"...
0x18001e35a  mov     edx, 578h; void *
0x18001e35f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e364  nop
0x18001e365  mov     eax, ebx
0x18001e367  jmp     loc_18001E4DB
0x18001e36c  lea     rbx, [rax+10h]
0x18001e370  mov     rcx, rbx; this
0x18001e373  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18001e378  mov     qword ptr [rdi+38h], 1
0x18001e380  lea     rax, ??_7?$RuntimeClass@UIRemoteTextCompositionInfoUpdatingEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextCompositionInfoUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable'
0x18001e387  mov     [rdi], rax
0x18001e38a  lea     rax, ??_7?$RuntimeClass@UIRemoteTextCompositionInfoUpdatingEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextCompositionInfoUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'}
0x18001e391  mov     [rdi+8], rax
0x18001e395  lea     rax, ??_7?$RuntimeClass@UIRemoteTextCompositionInfoUpdatingEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextCompositionInfoUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001e39c  mov     [rbx], rax
0x18001e39f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18001e3a6  test    rcx, rcx
0x18001e3a9  jz      short loc_18001E3B8
0x18001e3ab  mov     rax, [rcx]
0x18001e3ae  mov     rax, [rax+8]
0x18001e3b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3b7  nop
0x18001e3b8  lea     rax, ??_7CRemoteTextCompositionInfoUpdatingEventArgs@@6B@; const CRemoteTextCompositionInfoUpdatingEventArgs::`vftable'
0x18001e3bf  mov     [rdi], rax
0x18001e3c2  lea     rax, ??_7?$RuntimeClass@UIRemoteTextCompositionInfoUpdatingEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextCompositionInfoUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'}
0x18001e3c9  mov     [rdi+8], rax
0x18001e3cd  lea     rax, ??_7?$RuntimeClass@UIRemoteTextCompositionInfoUpdatingEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextCompositionInfoUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001e3d4  mov     [rbx], rax
0x18001e3d7  lea     rbx, [rdi+58h]
0x18001e3db  mov     qword ptr [rbx], 0
0x18001e3e2  mov     [rdi+40h], r13d
0x18001e3e6  mov     [rdi+44h], r12d
0x18001e3ea  mov     [rdi+48h], r15d
0x18001e3ee  mov     eax, [rsp+88h+arg_20]
0x18001e3f5  mov     [rdi+4Ch], eax
0x18001e3f8  mov     rax, [rsp+88h+arg_28]
0x18001e400  mov     [rdi+50h], rax
0x18001e404  xor     ecx, ecx; string
0x18001e406  call    cs:__imp_WindowsDeleteString
0x18001e40c  mov     qword ptr [rbx], 0
0x18001e413  mov     rdx, rbx; newString
0x18001e416  mov     rcx, [rsp+88h+string]; string
0x18001e41e  call    cs:__imp_WindowsDuplicateString
0x18001e424  nop
0x18001e425  mov     rax, [rdi]
0x18001e428  mov     rcx, rdi
0x18001e42b  mov     rax, [rax+8]
0x18001e42f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e434  nop
0x18001e435  mov     rax, [rdi]
0x18001e438  mov     rcx, rdi
0x18001e43b  mov     rax, [rax+10h]
0x18001e43f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e444  nop
0x18001e445  mov     [rsp+88h+var_68], rdi
0x18001e44a  lea     rax, [rbp-10h]
0x18001e44e  mov     [rsp+88h+arg_0], rax
0x18001e456  xor     ebx, ebx
0x18001e458  mov     rcx, rsi; SRWLock
0x18001e45b  call    cs:__imp_AcquireSRWLockExclusive
0x18001e461  mov     rdx, [r14]
0x18001e464  test    rdx, rdx
0x18001e467  jz      short loc_18001E486
0x18001e469  mov     rbx, rdx
0x18001e46c  mov     r8d, 7FFFFFFFh
0x18001e472  jmp     short loc_18001E47E
0x18001e474  lea     ecx, [rax+1]
0x18001e477  lock cmpxchg [rdx+0Ch], ecx
0x18001e47c  jz      short loc_18001E486
0x18001e47e  mov     eax, [rdx+0Ch]
0x18001e481  cmp     eax, r8d
0x18001e484  jnz     short loc_18001E474
0x18001e486  test    rsi, rsi
0x18001e489  jz      short loc_18001E494
0x18001e48b  mov     rcx, rsi; SRWLock
0x18001e48e  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e494  test    rbx, rbx
0x18001e497  jz      short loc_18001E4C9
0x18001e499  lea     rax, [rsp+88h+arg_0]
0x18001e4a1  mov     [rsp+88h+var_58], rax
0x18001e4a6  lea     rax, [rsp+88h+var_68]
0x18001e4ab  mov     [rsp+88h+var_50], rax
0x18001e4b0  mov     r8, r14
0x18001e4b3  mov     rdx, rbx
0x18001e4b6  lea     rcx, [rsp+88h+var_58]
0x18001e4bb  call    ??$InvokeDelegates@V_lambda_63f70fd3a6236e7362d86e89a2498b35_@@U?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextNonComponentUIHostDetectedEventArgs@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@?$InvokeTraits@$0?1@WRL@Microsoft@@SAJV_lambda_63f70fd3a6236e7362d86e89a2498b35_@@PEAVEventTargetArray@Details@12@PEAV?$EventSource@U?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextNonComponentUIHostDetectedEventArgs@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@12@@Z; Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_63f70fd3a6236e7362d86e89a2498b35_,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextNonComponentUIHostDetectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(_lambda_63f70fd3a6236e7362d86e89a2498b35_,Microsoft::WRL::Details::EventTargetArray *,Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextNonComponentUIHostDetectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> *)
0x18001e4c0  mov     rcx, rbx
0x18001e4c3  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001e4c8  nop
0x18001e4c9  mov     rax, [rdi]
0x18001e4cc  mov     rcx, rdi
0x18001e4cf  mov     rax, [rax+10h]
0x18001e4d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4d8  nop
0x18001e4d9  xor     eax, eax
0x18001e4db  add     rsp, 48h
0x18001e4df  pop     r15
0x18001e4e1  pop     r14
0x18001e4e3  pop     r13
0x18001e4e5  pop     r12
0x18001e4e7  pop     rdi
0x18001e4e8  pop     rsi
0x18001e4e9  pop     rbp
0x18001e4ea  pop     rbx
0x18001e4eb  retn
```
