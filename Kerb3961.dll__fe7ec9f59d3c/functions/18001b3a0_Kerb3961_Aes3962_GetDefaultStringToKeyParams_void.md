# Kerb3961::Aes3962::GetDefaultStringToKeyParams(void)

- ea: `0x18001b3a0`
- end: `0x18001b3bd`
- name: `?GetDefaultStringToKeyParams@Aes3962@Kerb3961@@EEAA?BU?$ReturnType@UReadOnlyBinaryResult@Kerb3961@@$1??$SingleGetter@UReadOnlyBinaryResult@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UReadOnlyBinaryResult@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@XZ`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall Kerb3961::Aes3962::GetDefaultStringToKeyParams(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  *(_QWORD *)a2 = 4;
  *(_QWORD *)(a2 + 8) = &`Kerb3961::Aes3962::GetDefaultStringToKeyParams'::`2'::params;
  result = a2;
  *(_DWORD *)(a2 + 16) = 0;
  return result;
}

```

## disassembly

```asm
0x18001b3a0  lea     rax, ?params@?1??GetDefaultStringToKeyParams@Aes3962@Kerb3961@@EEAA?BU?$ReturnType@UReadOnlyBinaryResult@Kerb3961@@$1??$SingleGetter@UReadOnlyBinaryResult@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UReadOnlyBinaryResult@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@3@XZ@4QBEB; uchar const near * const `Kerb3961::Aes3962::GetDefaultStringToKeyParams(void)'::`2'::params
0x18001b3a7  mov     qword ptr [rdx], 4
0x18001b3ae  mov     [rdx+8], rax
0x18001b3b2  mov     rax, rdx
0x18001b3b5  mov     dword ptr [rdx+10h], 0
0x18001b3bc  retn
```
