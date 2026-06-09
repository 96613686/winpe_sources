# Kerb3961::RC4_4757::RandomToKey(Kerb3961::ReadOnlyBinary const &)

- ea: `0x1800103f0`
- end: `0x18001044c`
- name: `?RandomToKey@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@@Z`
- size: `92`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180003a54`
- `0x1800103f0`
- `0x180011760`

## pseudocode

```c
__int64 __fastcall Kerb3961::RC4_4757::RandomToKey(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD v5[3]; // [rsp+20h] [rbp-18h] BYREF

  if ( *a3 >= 0x10u )
  {
    v5[1] = a3[1];
    v5[0] = 16;
    Kerb3961::CopyBuffer(a2, (__int64)v5);
  }
  else
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"randomSeed.length >= KEY_SIZE",
      (const char *)a2);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741811;
  }
  return a2;
}

```

## disassembly

```asm
0x1800103f0  push    rbx
0x1800103f2  sub     rsp, 30h
0x1800103f6  cmp     qword ptr [r8], 10h
0x1800103fa  mov     rbx, rdx
0x1800103fd  jnb     short loc_180010423
0x1800103ff  lea     rcx, aRandomseedLeng; "randomSeed.length >= KEY_SIZE"
0x180010406  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18001040b  mov     qword ptr [rbx], 0
0x180010412  mov     qword ptr [rbx+8], 0
0x18001041a  mov     dword ptr [rbx+10h], 0C000000Dh
0x180010421  jmp     short loc_180010442
0x180010423  mov     rax, [r8+8]
0x180010427  lea     rdx, [rsp+38h+var_18]
0x18001042c  mov     rcx, rbx
0x18001042f  mov     [rsp+38h+var_10], rax
0x180010434  mov     [rsp+38h+var_18], 10h
0x18001043d  call    ?CopyBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@@Z; Kerb3961::CopyBuffer(Kerb3961::ReadOnlyBinary const &)
0x180010442  mov     rax, rbx
0x180010445  add     rsp, 30h
0x180010449  pop     rbx
0x18001044a  retn
```
