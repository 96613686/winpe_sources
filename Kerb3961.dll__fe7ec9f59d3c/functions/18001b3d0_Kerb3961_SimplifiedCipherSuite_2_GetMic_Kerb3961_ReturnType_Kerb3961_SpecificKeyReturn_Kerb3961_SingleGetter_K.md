# Kerb3961::SimplifiedCipherSuite<2>::GetMic(Kerb3961::ReturnType<Kerb3961::SpecificKeyReturn,&Kerb3961::SingleGetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn const &),&Kerb3961::SingleSetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn &)> &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x18001b3d0`
- end: `0x18001b431`
- name: `?GetMic@?$SimplifiedCipherSuite@$01@Kerb3961@@MEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002c64`
- `0x18001b3d0`
- `0x18001e010`

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
0x18001b3d0  push    rbx
0x18001b3d2  sub     rsp, 30h
0x18001b3d6  add     rcx, 0FFFFFFFFFFFFFFF8h
0x18001b3da  mov     rbx, rdx
0x18001b3dd  cmp     [r8], rcx
0x18001b3e0  jz      short loc_18001B406
0x18001b3e2  lea     rcx, aSpecifickeyAlg; "specificKey.algorithm == this"
0x18001b3e9  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18001b3ee  mov     qword ptr [rbx], 0
0x18001b3f5  mov     qword ptr [rbx+8], 0
0x18001b3fd  mov     dword ptr [rbx+10h], 0C000000Dh
0x18001b404  jmp     short loc_18001B428
0x18001b406  mov     r8, [r8+8]
0x18001b40a  cmp     qword ptr [r8], 0
0x18001b40e  ja      short loc_18001B419
0x18001b410  lea     rcx, aKeyKcLength0; "key->Kc.length > 0"
0x18001b417  jmp     short loc_18001B3E9
0x18001b419  mov     rax, [rcx]
0x18001b41c  mov     rax, [rax+1A8h]
0x18001b423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b428  mov     rax, rbx
0x18001b42b  add     rsp, 30h
0x18001b42f  pop     rbx
0x18001b430  retn
```
