# Kerb3961::Aes8009::GetDefaultStringToKeyParams(void)

- ea: `0x180008b00`
- end: `0x180008b1d`
- name: `?GetDefaultStringToKeyParams@Aes8009@Kerb3961@@EEAA?BU?$ReturnType@UReadOnlyBinaryResult@Kerb3961@@$1??$SingleGetter@UReadOnlyBinaryResult@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UReadOnlyBinaryResult@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@XZ`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall Kerb3961::Aes8009::GetDefaultStringToKeyParams(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  *(_QWORD *)a2 = 4;
  *(_QWORD *)(a2 + 8) = &`Kerb3961::Aes8009::GetDefaultStringToKeyParams'::`2'::params;
  result = a2;
  *(_DWORD *)(a2 + 16) = 0;
  return result;
}

```

## disassembly

```asm
0x180008b00  lea     rax, ?params@?1??GetDefaultStringToKeyParams@Aes8009@Kerb3961@@EEAA?BU?$ReturnType@UReadOnlyBinaryResult@Kerb3961@@$1??$SingleGetter@UReadOnlyBinaryResult@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UReadOnlyBinaryResult@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@3@XZ@4QBEB; uchar const near * const `Kerb3961::Aes8009::GetDefaultStringToKeyParams(void)'::`2'::params
0x180008b07  mov     qword ptr [rdx], 4
0x180008b0e  mov     [rdx+8], rax
0x180008b12  mov     rax, rdx
0x180008b15  mov     dword ptr [rdx+10h], 0
0x180008b1c  retn
```
