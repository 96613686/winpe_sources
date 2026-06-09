# utl::_FuncBig<`Kerb3961::SSPICipherSuite<1,1,1>::SSPIUnwrap(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,bool,bool)'::`15'::_lambda_1_,Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,Kerb3961::ReadOnlyBinary const &>::_Invoke(Kerb3961::ReadOnlyBinary const &)

- ea: `0x18000a090`
- end: `0x18000a0fe`
- name: `?_Invoke@?$_FuncBig@V_lambda_1_@?P@??SSPIUnwrap@?$SSPICipherSuite@$00$00$00@Kerb3961@@EEAA?AU?$ReturnType@UVerifyMICResult@Kerb3961@@$1??$SingleGetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEAU32@AEAU12@@Z@4@AEBUWrapBuffers@4@AEBUReadOnlyBinary@4@11_N2@Z@U?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@4@AEBU74@@utl@@UEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@4@@Z`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002c64`
- `0x180004b40`
- `0x180008a5c`
- `0x18000a090`

## string_xrefs

- `0x18000a0c5`: `decrypted.length == effectiveInput.length + ((compatFixes == GssApiCompatibilityFixes::RC4) ? trailerBuffer.length : 0)`

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
    Kerb3961::SSPICipherSuite<1,1,1>::CoalesceAuthWrapBuffers(a1, a2, *(_QWORD **)(v4 + 8), *(_QWORD *)(v4 + 16));
  }
  return a2;
}

```

## disassembly

```asm
0x18000a090  push    rbx
0x18000a092  sub     rsp, 20h
0x18000a096  cmp     qword ptr [r8], 0
0x18000a09a  mov     rbx, rdx
0x18000a09d  mov     r10, [rcx+8]
0x18000a0a1  jnz     short loc_18000A0B2
0x18000a0a3  mov     r9, [r10+10h]
0x18000a0a7  mov     r8, [r10+8]
0x18000a0ab  call    ?CoalesceAuthWrapBuffers@?$SSPICipherSuite@$00$00$00@Kerb3961@@IEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@AEBUReadOnlyBinary@2@@Z; Kerb3961::SSPICipherSuite<1,1,1>::CoalesceAuthWrapBuffers(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &)
0x18000a0b0  jmp     short loc_18000A0F5
0x18000a0b2  mov     rax, [r10+18h]
0x18000a0b6  mov     rcx, [r10+10h]
0x18000a0ba  mov     rdx, [rax]
0x18000a0bd  add     rdx, [rcx]; char *
0x18000a0c0  cmp     [r8], rdx
0x18000a0c3  jz      short loc_18000A0E9
0x18000a0c5  lea     rcx, aDecryptedLengt; "decrypted.length == effectiveInput.leng"...
0x18000a0cc  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000a0d1  mov     qword ptr [rbx], 0
0x18000a0d8  mov     qword ptr [rbx+8], 0
0x18000a0e0  mov     dword ptr [rbx+10h], 8009030Fh
0x18000a0e7  jmp     short loc_18000A0F5
0x18000a0e9  mov     rdx, [r10+8]
0x18000a0ed  mov     rcx, rbx
0x18000a0f0  call    ?InterleaveDecryptionAndIntegrity@?$SSPICipherSuite@$00$00$00@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@AEBUReadOnlyBinary@2@@Z; Kerb3961::SSPICipherSuite<1,1,1>::InterleaveDecryptionAndIntegrity(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &)
0x18000a0f5  mov     rax, rbx
0x18000a0f8  add     rsp, 20h
0x18000a0fc  pop     rbx
0x18000a0fd  retn
```
