# Kerb3961::SimplifiedCipherSuite<2>::CompatibleCipher(uint)

- ea: `0x1800037d0`
- end: `0x1800037d7`
- name: `?CompatibleCipher@?$SimplifiedCipherSuite@$01@Kerb3961@@MEAA_NI@Z`
- size: `7`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
bool __fastcall Kerb3961::SimplifiedCipherSuite<2>::CompatibleCipher(__int64 a1, int a2)
{
  return a2 == *(_DWORD *)(a1 + 56);
}

```

## disassembly

```asm
0x1800037d0  cmp     edx, [rcx+38h]
0x1800037d3  setz    al
0x1800037d6  retn
```
