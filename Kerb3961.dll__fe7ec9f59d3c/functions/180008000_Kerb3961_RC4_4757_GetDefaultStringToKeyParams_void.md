# Kerb3961::RC4_4757::GetDefaultStringToKeyParams(void)

- ea: `0x180008000`
- end: `0x180008010`
- name: `?GetDefaultStringToKeyParams@RC4_4757@Kerb3961@@EEAA?BU?$ReturnType@UReadOnlyBinaryResult@Kerb3961@@$1??$SingleGetter@UReadOnlyBinaryResult@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UReadOnlyBinaryResult@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@XZ`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall Kerb3961::RC4_4757::GetDefaultStringToKeyParams(__int64 a1, __int64 a2)
{
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 16) = 0;
  return a2;
}

```

## disassembly

```asm
0x180008000  xor     eax, eax
0x180008002  mov     [rdx], rax
0x180008005  mov     [rdx+8], rax
0x180008009  mov     [rdx+10h], eax
0x18000800c  mov     rax, rdx
0x18000800f  retn
```
