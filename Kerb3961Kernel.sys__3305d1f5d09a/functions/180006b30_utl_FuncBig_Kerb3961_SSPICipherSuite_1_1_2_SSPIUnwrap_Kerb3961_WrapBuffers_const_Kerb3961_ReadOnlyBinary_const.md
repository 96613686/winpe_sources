# utl::_FuncBig<`Kerb3961::SSPICipherSuite<1,1,2>::SSPIUnwrap(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,bool,bool)'::`15'::_lambda_1_,Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,Kerb3961::ReadOnlyBinary const &>::_Invoke(Kerb3961::ReadOnlyBinary const &)

- ea: `0x180006b30`
- end: `0x180006b96`
- name: `?_Invoke@?$_FuncBig@V_lambda_1_@?P@??SSPIUnwrap@?$SSPICipherSuite@$00$00$01@Kerb3961@@EEAA?AU?$ReturnType@UVerifyMICResult@Kerb3961@@$1??$SingleGetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEAU32@AEAU12@@Z@4@AEBUWrapBuffers@4@AEBUReadOnlyBinary@4@11_N2@Z@U?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@4@AEBU74@@utl@@UEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@4@@Z`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001e7c`
- `0x1800059e4`
- `0x180006b30`
- `0x180011760`

## string_xrefs

- `0x180006b5c`: `decrypted.length == effectiveInput.length + ((compatFixes == GssApiCompatibilityFixes::RC4) ? trailerBuffer.length : 0)`

## pseudocode

```c
__int64 __fastcall __Invoke____FuncBig_V_lambda_1___P___SSPIUnwrap___SSPICipherSuite__00_00_01_Kerb3961__EEAA_AU__ReturnType_UVerifyMICResult_Kerb3961___1___SingleGetter_UVerifyMICResult_Kerb3961___0M__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UVerifyMICResult_Kerb3961___0M__2_YAAEAU32_AEAU12__Z_4_AEBUWrapBuffers_4_AEBUReadOnlyBinary_4_11_N2_Z_U__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_4_AEBU74__utl__UEAA_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_Kerb3961__AEBUReadOnlyBinary_4__Z(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v4; // rdx

  v4 = *(_QWORD *)(a1 + 8);
  if ( *a3 )
  {
    if ( *a3 == **(_QWORD **)(v4 + 24) )
    {
      Kerb3961::SSPICipherSuite<1,1,2>::InterleaveDecryptionAndIntegrity(a2, *(_QWORD *)(v4 + 8));
    }
    else
    {
      Kerb3961::Logging::Verify::ConditionFailed(
        (Kerb3961::Logging::Verify *)"decrypted.length == effectiveInput.length + ((compatFixes == GssApiCompatibilityFix"
                                     "es::RC4) ? trailerBuffer.length : 0)",
        (const char *)v4);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = -2146893041;
    }
  }
  else
  {
    Kerb3961::SSPICipherSuite<1,1,2>::CoalesceAuthWrapBuffers(0, a2, *(_QWORD *)(v4 + 8));
  }
  return a2;
}

```

## disassembly

```asm
0x180006b30  push    rbx
0x180006b32  sub     rsp, 20h
0x180006b36  mov     rbx, rdx
0x180006b39  mov     rdx, [rcx+8]; char *
0x180006b3d  mov     rcx, [r8]
0x180006b40  test    rcx, rcx
0x180006b43  jnz     short loc_180006B53
0x180006b45  mov     r8, [rdx+8]
0x180006b49  mov     rdx, rbx
0x180006b4c  call    ?CoalesceAuthWrapBuffers@?$SSPICipherSuite@$00$00$01@Kerb3961@@IEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@AEBUReadOnlyBinary@2@@Z; Kerb3961::SSPICipherSuite<1,1,2>::CoalesceAuthWrapBuffers(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &)
0x180006b51  jmp     short loc_180006B8C
0x180006b53  mov     rax, [rdx+18h]
0x180006b57  cmp     rcx, [rax]
0x180006b5a  jz      short loc_180006B80
0x180006b5c  lea     rcx, aDecryptedLengt; "decrypted.length == effectiveInput.leng"...
0x180006b63  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180006b68  mov     qword ptr [rbx], 0
0x180006b6f  mov     qword ptr [rbx+8], 0
0x180006b77  mov     dword ptr [rbx+10h], 8009030Fh
0x180006b7e  jmp     short loc_180006B8C
0x180006b80  mov     rdx, [rdx+8]
0x180006b84  mov     rcx, rbx
0x180006b87  call    ?InterleaveDecryptionAndIntegrity@?$SSPICipherSuite@$00$00$01@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@AEBUReadOnlyBinary@2@@Z; Kerb3961::SSPICipherSuite<1,1,2>::InterleaveDecryptionAndIntegrity(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &)
0x180006b8c  mov     rax, rbx
0x180006b8f  add     rsp, 20h
0x180006b93  pop     rbx
0x180006b94  retn
```
