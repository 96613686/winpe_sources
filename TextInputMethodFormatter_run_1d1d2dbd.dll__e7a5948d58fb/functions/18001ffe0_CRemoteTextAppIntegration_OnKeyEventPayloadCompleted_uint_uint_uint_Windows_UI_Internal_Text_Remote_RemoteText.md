# CRemoteTextAppIntegration::OnKeyEventPayloadCompleted(uint,uint,uint,Windows::UI::Internal::Text::Remote::RemoteTextKeyEventHostInfo,int,int)

- ea: `0x18001ffe0`
- end: `0x180020219`
- name: `?OnKeyEventPayloadCompleted@CRemoteTextAppIntegration@@UEAAJIIIURemoteTextKeyEventHostInfo@Remote@Text@Internal@UI@Windows@@HH@Z`
- size: `569`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002270`
- `0x180003e44`
- `0x180006a14`
- `0x180018cd0`
- `0x18001ffe0`
- `0x180024b70`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002003b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800201be`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002003b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800201be`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020015`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002018b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020015`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002018b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRemoteTextAppIntegration::OnKeyEventPayloadCompleted(
        RTL_SRWLOCK *a1,
        int a2,
        int a3,
        int a4,
        __int64 a5,
        int a6,
        int a7)
{
  RTL_SRWLOCK *v11; // r14
  __int64 v12; // rbx
  char *v13; // rax
  char *v14; // rdi
  _QWORD *v16; // rbx
  __int64 v17; // rbx
  _DWORD *Ptr; // rdx
  signed __int32 v19; // eax
  RTL_SRWLOCK *v20; // [rsp+20h] [rbp-68h] BYREF
  char *v21; // [rsp+28h] [rbp-60h] BYREF
  _QWORD v22[11]; // [rsp+30h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v11 = a1 + 60;
  if ( a1[60].Ptr )
  {
    AcquireSRWLockExclusive(a1 + 61);
    if ( v11->Ptr )
      v12 = (__int64)(*((_QWORD *)v11->Ptr + 3) - *((_QWORD *)v11->Ptr + 2)) >> 3;
    else
      v12 = 0;
    if ( v11 != (RTL_SRWLOCK *)-8LL )
      ReleaseSRWLockExclusive(v11 + 1);
    if ( v12 )
    {
      v13 = (char *)operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
      v14 = v13;
      if ( !v13 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5D6,
          (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextappintegration\\lib\\remotetextappintegration.cpp",
          (const char *)0x8007000ELL,
          (int)v20);
        return 2147942414LL;
      }
      v16 = v13 + 16;
      Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v13 + 16));
      *((_QWORD *)v14 + 7) = 1;
      *(_QWORD *)v14 = &Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextKeyEventPayloadCompletedEventArgs,Microsoft::WRL::FtmBase>::`vftable';
      *((_QWORD *)v14 + 1) = &Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextKeyEventPayloadCompletedEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'};
      *v16 = &Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextKeyEventPayloadCompletedEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      *(_QWORD *)v14 = &CRemoteTextKeyEventPayloadCompletedEventArgs::`vftable';
      *((_QWORD *)v14 + 1) = &Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextKeyEventPayloadCompletedEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'};
      *v16 = &Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextKeyEventPayloadCompletedEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
      *((_DWORD *)v14 + 16) = a2;
      *((_DWORD *)v14 + 17) = a3;
      *((_DWORD *)v14 + 18) = a4;
      v14[76] = 0;
      *((_OWORD *)v14 + 5) = *(_OWORD *)a5;
      *((_OWORD *)v14 + 6) = *(_OWORD *)(a5 + 16);
      *((_OWORD *)v14 + 7) = *(_OWORD *)(a5 + 32);
      *((_OWORD *)v14 + 8) = *(_OWORD *)(a5 + 48);
      *((_QWORD *)v14 + 18) = *(_QWORD *)(a5 + 64);
      *((_DWORD *)v14 + 38) = a6;
      *((_DWORD *)v14 + 39) = a7;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v14 + 8LL))(v14);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))(v14);
      v21 = v14;
      v20 = a1 - 2;
      v17 = 0;
      AcquireSRWLockExclusive(v11 + 1);
      Ptr = v11->Ptr;
      if ( v11->Ptr )
      {
        v17 = (__int64)v11->Ptr;
        do
          v19 = Ptr[3];
        while ( v19 != 0x7FFFFFFF && v19 != _InterlockedCompareExchange(Ptr + 3, v19 + 1, v19) );
      }
      if ( v11 != (RTL_SRWLOCK *)-8LL )
        ReleaseSRWLockExclusive(v11 + 1);
      if ( v17 )
      {
        v22[0] = &v20;
        v22[1] = &v21;
        Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_63f70fd3a6236e7362d86e89a2498b35_,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextNonComponentUIHostDetectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(
          v22,
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
0x18001ffe0  push    rbx
0x18001ffe2  push    rbp
0x18001ffe3  push    rsi
0x18001ffe4  push    rdi
0x18001ffe5  push    r12
0x18001ffe7  push    r13
0x18001ffe9  push    r14
0x18001ffeb  push    r15
0x18001ffed  sub     rsp, 48h
0x18001fff1  mov     r15d, r9d
0x18001fff4  mov     r12d, r8d
0x18001fff7  mov     r13d, edx
0x18001fffa  mov     rbp, rcx
0x18001fffd  lea     r14, [rcx+1E0h]
0x180020004  cmp     qword ptr [r14], 0
0x180020008  jz      loc_180020206
0x18002000e  lea     rsi, [r14+8]
0x180020012  mov     rcx, rsi; SRWLock
0x180020015  call    cs:__imp_AcquireSRWLockExclusive
0x18002001b  mov     rax, [r14]
0x18002001e  test    rax, rax
0x180020021  jnz     short loc_180020027
0x180020023  xor     ebx, ebx
0x180020025  jmp     short loc_180020033
0x180020027  mov     rbx, [rax+18h]
0x18002002b  sub     rbx, [rax+10h]
0x18002002f  sar     rbx, 3
0x180020033  test    rsi, rsi
0x180020036  jz      short loc_180020041
0x180020038  mov     rcx, rsi; SRWLock
0x18002003b  call    cs:__imp_ReleaseSRWLockExclusive
0x180020041  test    rbx, rbx
0x180020044  jz      loc_180020206
0x18002004a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180020051  mov     ecx, 0A0h; unsigned __int64
0x180020056  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002005b  mov     rdi, rax
0x18002005e  test    rax, rax
0x180020061  jnz     short loc_18002008C
0x180020063  mov     rcx, [rsp+88h]; this
0x18002006b  mov     ebx, 8007000Eh
0x180020070  mov     r9d, ebx; char *
0x180020073  lea     r8, aMincoreTextinp_14; "mincore\\textinput\\dev\\virtualization"...
0x18002007a  mov     edx, 5D6h; void *
0x18002007f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020084  nop
0x180020085  mov     eax, ebx
0x180020087  jmp     loc_180020208
0x18002008c  lea     rbx, [rax+10h]
0x180020090  mov     rcx, rbx; this
0x180020093  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180020098  mov     qword ptr [rdi+38h], 1
0x1800200a0  lea     rax, ??_7?$RuntimeClass@UIRemoteTextKeyEventPayloadCompletedEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextKeyEventPayloadCompletedEventArgs,Microsoft::WRL::FtmBase>::`vftable'
0x1800200a7  mov     [rdi], rax
0x1800200aa  lea     rax, ??_7?$RuntimeClass@UIRemoteTextKeyEventPayloadCompletedEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextKeyEventPayloadCompletedEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'}
0x1800200b1  mov     [rdi+8], rax
0x1800200b5  lea     rax, ??_7?$RuntimeClass@UIRemoteTextKeyEventPayloadCompletedEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextKeyEventPayloadCompletedEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800200bc  mov     [rbx], rax
0x1800200bf  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800200c6  test    rcx, rcx
0x1800200c9  jz      short loc_1800200D8
0x1800200cb  mov     rax, [rcx]
0x1800200ce  mov     rax, [rax+8]
0x1800200d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200d7  nop
0x1800200d8  lea     rax, ??_7CRemoteTextKeyEventPayloadCompletedEventArgs@@6B@; const CRemoteTextKeyEventPayloadCompletedEventArgs::`vftable'
0x1800200df  mov     [rdi], rax
0x1800200e2  lea     rax, ??_7?$RuntimeClass@UIRemoteTextKeyEventPayloadCompletedEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextKeyEventPayloadCompletedEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'}
0x1800200e9  mov     [rdi+8], rax
0x1800200ed  lea     rax, ??_7?$RuntimeClass@UIRemoteTextKeyEventPayloadCompletedEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextKeyEventPayloadCompletedEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800200f4  mov     [rbx], rax
0x1800200f7  mov     [rdi+40h], r13d
0x1800200fb  mov     [rdi+44h], r12d
0x1800200ff  mov     [rdi+48h], r15d
0x180020103  mov     byte ptr [rdi+4Ch], 0
0x180020107  mov     rax, [rsp+88h+arg_20]
0x18002010f  movups  xmm0, xmmword ptr [rax]
0x180020112  movups  xmmword ptr [rdi+50h], xmm0
0x180020116  movups  xmm1, xmmword ptr [rax+10h]
0x18002011a  movups  xmmword ptr [rdi+60h], xmm1
0x18002011e  movups  xmm0, xmmword ptr [rax+20h]
0x180020122  movups  xmmword ptr [rdi+70h], xmm0
0x180020126  movups  xmm1, xmmword ptr [rax+30h]
0x18002012a  movups  xmmword ptr [rdi+80h], xmm1
0x180020131  movsd   xmm0, qword ptr [rax+40h]
0x180020136  movsd   qword ptr [rdi+90h], xmm0
0x18002013e  mov     eax, [rsp+88h+arg_28]
0x180020145  mov     [rdi+98h], eax
0x18002014b  mov     eax, [rsp+88h+arg_30]
0x180020152  mov     [rdi+9Ch], eax
0x180020158  mov     rax, [rdi]
0x18002015b  mov     rcx, rdi
0x18002015e  mov     rax, [rax+8]
0x180020162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020167  nop
0x180020168  mov     rax, [rdi]
0x18002016b  mov     rcx, rdi
0x18002016e  mov     rax, [rax+10h]
0x180020172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020177  nop
0x180020178  mov     [rsp+88h+var_60], rdi
0x18002017d  lea     rax, [rbp-10h]
0x180020181  mov     [rsp+88h+var_68], rax
0x180020186  xor     ebx, ebx
0x180020188  mov     rcx, rsi; SRWLock
0x18002018b  call    cs:__imp_AcquireSRWLockExclusive
0x180020191  mov     rdx, [r14]
0x180020194  test    rdx, rdx
0x180020197  jz      short loc_1800201B6
0x180020199  mov     rbx, rdx
0x18002019c  mov     r8d, 7FFFFFFFh
0x1800201a2  jmp     short loc_1800201AE
0x1800201a4  lea     ecx, [rax+1]
0x1800201a7  lock cmpxchg [rdx+0Ch], ecx
0x1800201ac  jz      short loc_1800201B6
0x1800201ae  mov     eax, [rdx+0Ch]
0x1800201b1  cmp     eax, r8d
0x1800201b4  jnz     short loc_1800201A4
0x1800201b6  test    rsi, rsi
0x1800201b9  jz      short loc_1800201C4
0x1800201bb  mov     rcx, rsi; SRWLock
0x1800201be  call    cs:__imp_ReleaseSRWLockExclusive
0x1800201c4  test    rbx, rbx
0x1800201c7  jz      short loc_1800201F6
0x1800201c9  lea     rax, [rsp+88h+var_68]
0x1800201ce  mov     [rsp+88h+var_58], rax
0x1800201d3  lea     rax, [rsp+88h+var_60]
0x1800201d8  mov     [rsp+88h+var_50], rax
0x1800201dd  mov     r8, r14
0x1800201e0  mov     rdx, rbx
0x1800201e3  lea     rcx, [rsp+88h+var_58]
0x1800201e8  call    ??$InvokeDelegates@V_lambda_63f70fd3a6236e7362d86e89a2498b35_@@U?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextNonComponentUIHostDetectedEventArgs@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@?$InvokeTraits@$0?1@WRL@Microsoft@@SAJV_lambda_63f70fd3a6236e7362d86e89a2498b35_@@PEAVEventTargetArray@Details@12@PEAV?$EventSource@U?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextNonComponentUIHostDetectedEventArgs@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@12@@Z; Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_63f70fd3a6236e7362d86e89a2498b35_,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextNonComponentUIHostDetectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(_lambda_63f70fd3a6236e7362d86e89a2498b35_,Microsoft::WRL::Details::EventTargetArray *,Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextNonComponentUIHostDetectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> *)
0x1800201ed  mov     rcx, rbx
0x1800201f0  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x1800201f5  nop
0x1800201f6  mov     rax, [rdi]
0x1800201f9  mov     rcx, rdi
0x1800201fc  mov     rax, [rax+10h]
0x180020200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020205  nop
0x180020206  xor     eax, eax
0x180020208  add     rsp, 48h
0x18002020c  pop     r15
0x18002020e  pop     r14
0x180020210  pop     r13
0x180020212  pop     r12
0x180020214  pop     rdi
0x180020215  pop     rsi
0x180020216  pop     rbp
0x180020217  pop     rbx
0x180020218  retn
```
