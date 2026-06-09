# Kerb3961::SimplifiedCipherSuite<2>::GetMic(Kerb3961::ReturnType<Kerb3961::SpecificKeyReturn,&Kerb3961::SingleGetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn const &),&Kerb3961::SingleSetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn &)> &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180005550`
- end: `0x1800055b2`
- name: `?GetMic@?$SimplifiedCipherSuite@$01@Kerb3961@@MEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@@Z`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180005550`
- `0x180011760`
- `0x180012240`

## pseudocode

```c
__int64 __fastcall Kerb3961::SimplifiedCipherSuite<2>::GetMic(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rcx
  char *v5; // rcx

  v3 = a1 - 8;
  if ( *(_QWORD *)a3 == v3 )
  {
    if ( **(_QWORD **)(a3 + 8) )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 424LL))(v3);
      return a2;
    }
    v5 = "key->Kc.length > 0";
  }
  else
  {
    v5 = "specificKey.algorithm == this";
  }
  Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v5, (const char *)a2);
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 16) = -1073741811;
  return a2;
}

```

## disassembly

```asm
0x180005550  push    rbx
0x180005552  sub     rsp, 30h
0x180005556  add     rcx, 0FFFFFFFFFFFFFFF8h
0x18000555a  mov     rbx, rdx
0x18000555d  cmp     [r8], rcx
0x180005560  jz      short loc_180005586
0x180005562  lea     rcx, aSpecifickeyAlg; "specificKey.algorithm == this"
0x180005569  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000556e  mov     qword ptr [rbx], 0
0x180005575  mov     qword ptr [rbx+8], 0
0x18000557d  mov     dword ptr [rbx+10h], 0C000000Dh
0x180005584  jmp     short loc_1800055A8
0x180005586  mov     r8, [r8+8]
0x18000558a  cmp     qword ptr [r8], 0
0x18000558e  ja      short loc_180005599
0x180005590  lea     rcx, aKeyKcLength0; "key->Kc.length > 0"
0x180005597  jmp     short loc_180005569
0x180005599  mov     rax, [rcx]
0x18000559c  mov     rax, [rax+1A8h]
0x1800055a3  call    _guard_dispatch_icall
0x1800055a8  mov     rax, rbx
0x1800055ab  add     rsp, 30h
0x1800055af  pop     rbx
0x1800055b0  retn
```
