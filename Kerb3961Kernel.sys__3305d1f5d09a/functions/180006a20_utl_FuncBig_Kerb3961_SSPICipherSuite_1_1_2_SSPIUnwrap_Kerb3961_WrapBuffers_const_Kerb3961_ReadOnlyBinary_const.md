# utl::_FuncBig<`Kerb3961::SSPICipherSuite<1,1,2>::SSPIUnwrap(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,bool,bool)'::`15'::_lambda_1_,Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,Kerb3961::ReadOnlyBinary const &>::_CopyInto(void *)

- ea: `0x180006a20`
- end: `0x180006a78`
- name: `?_CopyInto@?$_FuncBig@V_lambda_1_@?P@??SSPIUnwrap@?$SSPICipherSuite@$00$00$01@Kerb3961@@EEAA?AU?$ReturnType@UVerifyMICResult@Kerb3961@@$1??$SingleGetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEAU32@AEAU12@@Z@4@AEBUWrapBuffers@4@AEBUReadOnlyBinary@4@11_N2@Z@U?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@4@AEBU74@@utl@@UEBA_NPEAX@Z`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006a20`
- `0x180011ab8`

## pseudocode

```c
char __fastcall __CopyInto____FuncBig_V_lambda_1___P___SSPIUnwrap___SSPICipherSuite__00_00_01_Kerb3961__EEAA_AU__ReturnType_UVerifyMICResult_Kerb3961___1___SingleGetter_UVerifyMICResult_Kerb3961___0M__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UVerifyMICResult_Kerb3961___0M__2_YAAEAU32_AEAU12__Z_4_AEBUWrapBuffers_4_AEBUReadOnlyBinary_4_11_N2_Z_U__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_4_AEBU74__utl__UEBA_NPEAX_Z(
        __int64 a1,
        const struct std::nothrow_t *a2)
{
  _OWORD *v2; // rdi
  _OWORD *v4; // rax

  v2 = *(_OWORD **)(a1 + 8);
  v4 = operator new[](0x20u, a2);
  if ( v4 )
  {
    *((_QWORD *)a2 + 1) = v4;
    *(_QWORD *)a2 = ___7___FuncBig_V_lambda_1___P___SSPIUnwrap___SSPICipherSuite__00_00_01_Kerb3961__EEAA_AU__ReturnType_UVerifyMICResult_Kerb3961___1___SingleGetter_UVerifyMICResult_Kerb3961___0M__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UVerifyMICResult_Kerb3961___0M__2_YAAEAU32_AEAU12__Z_4_AEBUWrapBuffers_4_AEBUReadOnlyBinary_4_11_N2_Z_U__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_4_AEBU74__utl__6B_;
    *v4 = *v2;
    v4[1] = v2[1];
    return 1;
  }
  else
  {
    *(_QWORD *)a2 = &utl::_FuncEmpty<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::ResultBlock const & Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::ResultBlock & Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,Kerb3961::ReadOnlyBinary const &>::`vftable';
    return 0;
  }
}

```

## disassembly

```asm
0x180006a20  mov     [rsp+arg_0], rbx
0x180006a25  push    rdi
0x180006a26  sub     rsp, 20h
0x180006a2a  mov     rdi, [rcx+8]
0x180006a2e  mov     rbx, rdx
0x180006a31  mov     ecx, 20h ; ' '; unsigned __int64
0x180006a36  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006a3b  test    rax, rax
0x180006a3e  jnz     short loc_180006A4E
0x180006a40  lea     rax, ??_7?$_FuncEmpty@U?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@2@@utl@@6B@; const utl::_FuncEmpty<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,Kerb3961::ReadOnlyBinary const &>::`vftable'
0x180006a47  mov     [rbx], rax
0x180006a4a  xor     al, al
0x180006a4c  jmp     short loc_180006A6C
0x180006a4e  mov     [rbx+8], rax
0x180006a52  lea     rcx, ??_7?$_FuncBig@V_lambda_1_@?P@??SSPIUnwrap@?$SSPICipherSuite@$00$00$01@Kerb3961@@EEAA?AU?$ReturnType@UVerifyMICResult@Kerb3961@@$1??$SingleGetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEAU32@AEAU12@@Z@4@AEBUWrapBuffers@4@AEBUReadOnlyBinary@4@11_N2@Z@U?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@4@AEBU74@@utl@@6B@; const utl::_FuncBig<`Kerb3961::SSPICipherSuite<1,1,2>::SSPIUnwrap(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,bool,bool)'::`15'::_lambda_1_,Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,Kerb3961::ReadOnlyBinary const &>::`vftable'
0x180006a59  mov     [rbx], rcx
0x180006a5c  movups  xmm0, xmmword ptr [rdi]
0x180006a5f  movups  xmmword ptr [rax], xmm0
0x180006a62  movups  xmm1, xmmword ptr [rdi+10h]
0x180006a66  movups  xmmword ptr [rax+10h], xmm1
0x180006a6a  mov     al, 1
0x180006a6c  mov     rbx, [rsp+28h+arg_0]
0x180006a71  add     rsp, 20h
0x180006a75  pop     rdi
0x180006a76  retn
```
