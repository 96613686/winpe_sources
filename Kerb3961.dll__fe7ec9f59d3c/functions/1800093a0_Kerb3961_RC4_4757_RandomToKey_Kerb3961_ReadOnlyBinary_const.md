# Kerb3961::RC4_4757::RandomToKey(Kerb3961::ReadOnlyBinary const &)

- ea: `0x1800093a0`
- end: `0x1800093fb`
- name: `?RandomToKey@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@@Z`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002c64`
- `0x18000712c`
- `0x1800093a0`

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
0x1800093a0  push    rbx
0x1800093a2  sub     rsp, 30h
0x1800093a6  cmp     qword ptr [r8], 10h
0x1800093aa  mov     rbx, rdx
0x1800093ad  jnb     short loc_1800093D3
0x1800093af  lea     rcx, aRandomseedLeng; "randomSeed.length >= KEY_SIZE"
0x1800093b6  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800093bb  mov     qword ptr [rbx], 0
0x1800093c2  mov     qword ptr [rbx+8], 0
0x1800093ca  mov     dword ptr [rbx+10h], 0C000000Dh
0x1800093d1  jmp     short loc_1800093F2
0x1800093d3  mov     rax, [r8+8]
0x1800093d7  lea     rdx, [rsp+38h+var_18]
0x1800093dc  mov     rcx, rbx
0x1800093df  mov     [rsp+38h+var_10], rax
0x1800093e4  mov     [rsp+38h+var_18], 10h
0x1800093ed  call    ?CopyBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@@Z; Kerb3961::CopyBuffer(Kerb3961::ReadOnlyBinary const &)
0x1800093f2  mov     rax, rbx
0x1800093f5  add     rsp, 30h
0x1800093f9  pop     rbx
0x1800093fa  retn
```
