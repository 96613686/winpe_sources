# utl::_FuncBig<`Kerb3961::SSPICipherSuite<1,1,1>::SSPIUnwrap(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,bool,bool)'::`15'::_lambda_1_,Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,Kerb3961::ReadOnlyBinary const &>::_Invoke(Kerb3961::ReadOnlyBinary const &)

- ea: `0x180010bd0`
- end: `0x180010c41`
- name: `?_Invoke@?$_FuncBig@V_lambda_1_@?P@??SSPIUnwrap@?$SSPICipherSuite@$00$00$00@Kerb3961@@EEAA?AU?$ReturnType@UVerifyMICResult@Kerb3961@@$1??$SingleGetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEAU32@AEAU12@@Z@4@AEBUWrapBuffers@4@AEBUReadOnlyBinary@4@11_N2@Z@U?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@4@AEBU74@@utl@@UEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@4@@Z`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000d3c0`
- `0x180010060`
- `0x180010bd0`
- `0x180011760`

## string_xrefs

- `0x180010c07`: `decrypted.length == effectiveInput.length + ((compatFixes == GssApiCompatibilityFixes::RC4) ? trailerBuffer.length : 0)`

## pseudocode

```c
__int64 __fastcall __Invoke____FuncBig_V_lambda_1___P___SSPIUnwrap___SSPICipherSuite__00_00_00_Kerb3961__EEAA_AU__ReturnType_UVerifyMICResult_Kerb3961___1___SingleGetter_UVerifyMICResult_Kerb3961___0M__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UVerifyMICResult_Kerb3961___0M__2_YAAEAU32_AEAU12__Z_4_AEBUWrapBuffers_4_AEBUReadOnlyBinary_4_11_N2_Z_U__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_4_AEBU74__utl__UEAA_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_Kerb3961__AEBUReadOnlyBinary_4__Z(
        __int64 a1,
        __int64 a2,
        const char **a3)
{
  __int64 v4; // r10
  const char *v5; // rdx

  v4 = *(_QWORD *)(a1 + 8);
  if ( *a3 )
  {
    v5 = (const char *)(**(_QWORD **)(v4 + 16) + **(_QWORD **)(v4 + 24));
    if ( *a3 == v5 )
    {
      Kerb3961::SSPICipherSuite<1,1,1>::InterleaveDecryptionAndIntegrity(a2, *(_QWORD *)(v4 + 8));
    }
    else
    {
      Kerb3961::Logging::Verify::ConditionFailed(
        (Kerb3961::Logging::Verify *)"decrypted.length == effectiveInput.length + ((compatFixes == GssApiCompatibilityFix"
                                     "es::RC4) ? trailerBuffer.length : 0)",
        v5);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = -2146893041;
    }
  }
  else
  {
    Kerb3961::SSPICipherSuite<1,1,1>::CoalesceAuthWrapBuffers(a1, a2, *(_QWORD *)(v4 + 8), *(_QWORD *)(v4 + 16));
  }
  return a2;
}

```

## disassembly

```asm
0x180010bd0  push    rbx
0x180010bd2  sub     rsp, 20h
0x180010bd6  mov     r9, [r8]
0x180010bd9  mov     rbx, rdx
0x180010bdc  mov     r10, [rcx+8]
0x180010be0  test    r9, r9
0x180010be3  jnz     short loc_180010BF4
0x180010be5  mov     r9, [r10+10h]
0x180010be9  mov     r8, [r10+8]
0x180010bed  call    ?CoalesceAuthWrapBuffers@?$SSPICipherSuite@$00$00$00@Kerb3961@@IEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@AEBUReadOnlyBinary@2@@Z; Kerb3961::SSPICipherSuite<1,1,1>::CoalesceAuthWrapBuffers(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &)
0x180010bf2  jmp     short loc_180010C37
0x180010bf4  mov     rax, [r10+18h]
0x180010bf8  mov     rcx, [r10+10h]
0x180010bfc  mov     rdx, [rax]
0x180010bff  add     rdx, [rcx]; char *
0x180010c02  cmp     r9, rdx
0x180010c05  jz      short loc_180010C2B
0x180010c07  lea     rcx, aDecryptedLengt; "decrypted.length == effectiveInput.leng"...
0x180010c0e  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180010c13  mov     qword ptr [rbx], 0
0x180010c1a  mov     qword ptr [rbx+8], 0
0x180010c22  mov     dword ptr [rbx+10h], 8009030Fh
0x180010c29  jmp     short loc_180010C37
0x180010c2b  mov     rdx, [r10+8]
0x180010c2f  mov     rcx, rbx
0x180010c32  call    ?InterleaveDecryptionAndIntegrity@?$SSPICipherSuite@$00$00$00@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@AEBUReadOnlyBinary@2@@Z; Kerb3961::SSPICipherSuite<1,1,1>::InterleaveDecryptionAndIntegrity(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &)
0x180010c37  mov     rax, rbx
0x180010c3a  add     rsp, 20h
0x180010c3e  pop     rbx
0x180010c3f  retn
```
