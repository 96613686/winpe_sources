# Microsoft::WRL::Details::CreateActivationFactory<SecurityMitigationsBrokerStatics>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180003580`
- end: `0x1800036ef`
- name: `??$CreateActivationFactory@VSecurityMitigationsBrokerStatics@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `367`
- prototype: `__int64 __fastcall(_BYTE *, __int64, _DWORD *, SecurityMitigationsBrokerStatics **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001924`
- `0x180003580`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateActivationFactory<SecurityMitigationsBrokerStatics>(
        _BYTE *a1,
        __int64 a2,
        _DWORD *a3,
        SecurityMitigationsBrokerStatics **a4)
{
  char *v7; // rax
  SecurityMitigationsBrokerStatics *v8; // rbx
  struct Microsoft::WRL::Details::ModuleBase *v10; // rcx
  volatile signed __int32 *v11; // rsi
  SecurityMitigationsBrokerStatics *v12; // r15
  _QWORD *v13; // r12
  _DWORD *v14; // r13
  signed __int32 v15; // eax

  v7 = (char *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = (SecurityMitigationsBrokerStatics *)v7;
  if ( !v7 )
    return 2147942414LL;
  v10 = Microsoft::WRL::Details::ModuleBase::module_;
  v11 = (volatile signed __int32 *)(v7 + 20);
  *((_DWORD *)v7 + 5) = 1;
  v12 = (SecurityMitigationsBrokerStatics *)(v7 + 8);
  *(_QWORD *)v7 = &Microsoft::WRL::ActivationFactory<Windows::Internal::ISecurityMitigationsBrokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `IActivationFactory'};
  *((_QWORD *)v7 + 1) = &Microsoft::WRL::ActivationFactory<Windows::Internal::ISecurityMitigationsBrokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Windows::Internal::ISecurityMitigationsBrokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
  v13 = v7 + 32;
  *((_QWORD *)v7 + 4) = 0;
  v14 = v7 + 40;
  *((_DWORD *)v7 + 10) = 4;
  if ( v10 )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v10 + 8LL))(v10);
  *(_QWORD *)v8 = &SecurityMitigationsBrokerStatics::`vftable'{for `IActivationFactory'};
  *(_QWORD *)v12 = &SecurityMitigationsBrokerStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Windows::Internal::ISecurityMitigationsBrokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
  SecurityMitigationsBrokerStatics::AddRef(v8);
  (*(void (__fastcall **)(SecurityMitigationsBrokerStatics *))(*(_QWORD *)v8 + 16LL))(v8);
  if ( *a3 == 53 )
  {
    if ( a3[1] != *(_DWORD *)&GUID_00000035_0000_0000_c000_000000000046.Data2
      || a3[2] != *(_DWORD *)GUID_00000035_0000_0000_c000_000000000046.Data4
      || a3[3] != *(_DWORD *)&GUID_00000035_0000_0000_c000_000000000046.Data4[4] )
    {
LABEL_9:
      (*(void (__fastcall **)(SecurityMitigationsBrokerStatics *))(*(_QWORD *)v8 + 16LL))(v8);
      return 2147500034LL;
    }
  }
  else
  {
    if ( *a3 != -1288957124
      || a3[1] != *(_DWORD *)&GUID_b32c133c_e4dd_43a0_b85c_b0e5717683c5.Data2
      || a3[2] != *(_DWORD *)GUID_b32c133c_e4dd_43a0_b85c_b0e5717683c5.Data4
      || a3[3] != *(_DWORD *)&GUID_b32c133c_e4dd_43a0_b85c_b0e5717683c5.Data4[4] )
    {
      goto LABEL_9;
    }
    v8 = v12;
  }
  *a4 = v8;
  if ( (*a1 & 4) == 0 )
  {
    do
    {
      if ( *v11 == 0x7FFFFFFF )
        break;
      v15 = *v11;
    }
    while ( v15 != _InterlockedCompareExchange(v11, v15 + 1, v15) );
  }
  *v14 = *(_DWORD *)a1;
  *v13 = a2;
  return 0;
}

```

## disassembly

```asm
0x180003580  mov     [rsp+arg_8], rdx
0x180003585  push    rbx
0x180003586  push    rbp
0x180003587  push    rsi
0x180003588  push    rdi
0x180003589  push    r12
0x18000358b  push    r13
0x18000358d  push    r14
0x18000358f  push    r15
0x180003591  sub     rsp, 28h
0x180003595  mov     rbp, rcx
0x180003598  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000359f  mov     ecx, 30h ; '0'; unsigned __int64
0x1800035a4  mov     r14, r9
0x1800035a7  mov     rdi, r8
0x1800035aa  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800035af  mov     rbx, rax
0x1800035b2  test    rax, rax
0x1800035b5  jnz     short loc_1800035C1
0x1800035b7  mov     eax, 8007000Eh
0x1800035bc  jmp     loc_18000367F
0x1800035c1  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800035c8  lea     rsi, [rax+14h]
0x1800035cc  mov     dword ptr [rsi], 1
0x1800035d2  lea     r15, [rax+8]
0x1800035d6  lea     rax, ??_7?$ActivationFactory@UISecurityMitigationsBrokerStatics@Internal@Windows@@VNil@Details@WRL@Microsoft@@V4567@$0A@@WRL@Microsoft@@6BIActivationFactory@@@; const Microsoft::WRL::ActivationFactory<Windows::Internal::ISecurityMitigationsBrokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `IActivationFactory'}
0x1800035dd  mov     [rbx], rax
0x1800035e0  lea     rax, ??_7?$ActivationFactory@UISecurityMitigationsBrokerStatics@Internal@Windows@@VNil@Details@WRL@Microsoft@@V4567@$0A@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$00UISecurityMitigationsBrokerStatics@Internal@Windows@@VNil@Details@23@V7823@V7823@@Details@12@@; const Microsoft::WRL::ActivationFactory<Windows::Internal::ISecurityMitigationsBrokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Windows::Internal::ISecurityMitigationsBrokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x1800035e7  mov     [r15], rax
0x1800035ea  lea     r12, [rbx+20h]
0x1800035ee  mov     qword ptr [r12], 0
0x1800035f6  lea     r13, [rbx+28h]
0x1800035fa  mov     dword ptr [r13+0], 4
0x180003602  test    rcx, rcx
0x180003605  jz      short loc_180003613
0x180003607  mov     rax, [rcx]
0x18000360a  mov     rax, [rax+8]
0x18000360e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003613  lea     rax, ??_7SecurityMitigationsBrokerStatics@@6BIActivationFactory@@@; const SecurityMitigationsBrokerStatics::`vftable'{for `IActivationFactory'}
0x18000361a  mov     rcx, rbx
0x18000361d  mov     [rbx], rax
0x180003620  lea     rax, ??_7SecurityMitigationsBrokerStatics@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$00UISecurityMitigationsBrokerStatics@Internal@Windows@@VNil@Details@23@V7823@V7823@@Details@WRL@Microsoft@@@; const SecurityMitigationsBrokerStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Windows::Internal::ISecurityMitigationsBrokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x180003627  mov     [r15], rax
0x18000362a  mov     rax, cs:off_1800081B0
0x180003631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003636  mov     rax, [rbx]
0x180003639  mov     rcx, rbx
0x18000363c  mov     rax, [rax+10h]
0x180003640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003645  cmp     dword ptr [rdi], 35h ; '5'
0x180003648  jnz     short loc_180003690
0x18000364a  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data2
0x180003650  cmp     [rdi+4], eax
0x180003653  jnz     short loc_18000366B
0x180003655  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4
0x18000365b  cmp     [rdi+8], eax
0x18000365e  jnz     short loc_18000366B
0x180003660  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4+4
0x180003666  cmp     [rdi+0Ch], eax
0x180003669  jz      short loc_1800036BC
0x18000366b  mov     rax, [rbx]
0x18000366e  mov     rcx, rbx
0x180003671  mov     rax, [rax+10h]
0x180003675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000367a  mov     eax, 80004002h
0x18000367f  add     rsp, 28h
0x180003683  pop     r15
0x180003685  pop     r14
0x180003687  pop     r13
0x180003689  pop     r12
0x18000368b  pop     rdi
0x18000368c  pop     rsi
0x18000368d  pop     rbp
0x18000368e  pop     rbx
0x18000368f  retn
0x180003690  cmp     dword ptr [rdi], 0B32C133Ch
0x180003696  jnz     short loc_18000366B
0x180003698  mov     eax, dword ptr cs:_GUID_b32c133c_e4dd_43a0_b85c_b0e5717683c5.Data2
0x18000369e  cmp     [rdi+4], eax
0x1800036a1  jnz     short loc_18000366B
0x1800036a3  mov     eax, dword ptr cs:_GUID_b32c133c_e4dd_43a0_b85c_b0e5717683c5.Data4
0x1800036a9  cmp     [rdi+8], eax
0x1800036ac  jnz     short loc_18000366B
0x1800036ae  mov     eax, dword ptr cs:_GUID_b32c133c_e4dd_43a0_b85c_b0e5717683c5.Data4+4
0x1800036b4  cmp     [rdi+0Ch], eax
0x1800036b7  jnz     short loc_18000366B
0x1800036b9  mov     rbx, r15
0x1800036bc  mov     [r14], rbx
0x1800036bf  test    byte ptr [rbp+0], 4
0x1800036c3  jnz     short loc_1800036DB
0x1800036c5  mov     edx, 7FFFFFFFh
0x1800036ca  jmp     short loc_1800036D5
0x1800036cc  lea     ecx, [rax+1]
0x1800036cf  lock cmpxchg [rsi], ecx
0x1800036d3  jz      short loc_1800036DB
0x1800036d5  mov     eax, [rsi]
0x1800036d7  cmp     eax, edx
0x1800036d9  jnz     short loc_1800036CC
0x1800036db  mov     eax, [rbp+0]
0x1800036de  mov     [r13+0], eax
0x1800036e2  mov     rax, [rsp+68h+arg_8]
0x1800036e7  mov     [r12], rax
0x1800036eb  xor     eax, eax
0x1800036ed  jmp     short loc_18000367F
```
