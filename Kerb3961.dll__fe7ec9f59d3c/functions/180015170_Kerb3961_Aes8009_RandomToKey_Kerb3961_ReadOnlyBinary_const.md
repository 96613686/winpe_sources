# Kerb3961::Aes8009::RandomToKey(Kerb3961::ReadOnlyBinary const &)

- ea: `0x180015170`
- end: `0x1800151ca`
- name: `?RandomToKey@Aes8009@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@@Z`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002c64`
- `0x18000712c`
- `0x180015170`

## pseudocode

```c
__int64 __fastcall Kerb3961::Aes8009::RandomToKey(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD v5[3]; // [rsp+20h] [rbp-18h] BYREF

  if ( *a3 >= *(_QWORD *)(a1 + 64) )
  {
    v5[0] = *(_QWORD *)(a1 + 64);
    v5[1] = a3[1];
    Kerb3961::CopyBuffer(a2, (__int64)v5);
  }
  else
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"randomSeed.length >= m_keySize",
      (const char *)a2);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741789;
  }
  return a2;
}

```

## disassembly

```asm
0x180015170  push    rbx
0x180015172  sub     rsp, 30h
0x180015176  mov     rax, [rcx+40h]
0x18001517a  mov     rbx, rdx
0x18001517d  cmp     [r8], rax
0x180015180  jnb     short loc_1800151A6
0x180015182  lea     rcx, aRandomseedLeng_0; "randomSeed.length >= m_keySize"
0x180015189  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18001518e  mov     qword ptr [rbx], 0
0x180015195  mov     qword ptr [rbx+8], 0
0x18001519d  mov     dword ptr [rbx+10h], 0C0000023h
0x1800151a4  jmp     short loc_1800151C1
0x1800151a6  mov     [rsp+38h+var_18], rax
0x1800151ab  lea     rdx, [rsp+38h+var_18]
0x1800151b0  mov     rax, [r8+8]
0x1800151b4  mov     rcx, rbx
0x1800151b7  mov     [rsp+38h+var_10], rax
0x1800151bc  call    ?CopyBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@@Z; Kerb3961::CopyBuffer(Kerb3961::ReadOnlyBinary const &)
0x1800151c1  mov     rax, rbx
0x1800151c4  add     rsp, 30h
0x1800151c8  pop     rbx
0x1800151c9  retn
```
