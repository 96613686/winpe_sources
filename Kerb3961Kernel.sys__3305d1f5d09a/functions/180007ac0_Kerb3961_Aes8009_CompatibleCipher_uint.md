# Kerb3961::Aes8009::CompatibleCipher(uint)

- ea: `0x180007ac0`
- end: `0x180007ac7`
- name: `?CompatibleCipher@Aes8009@Kerb3961@@EEAA_NI@Z`
- size: `7`
- prototype: `bool __fastcall(Kerb3961::Aes8009 *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
bool __fastcall Kerb3961::Aes8009::CompatibleCipher(Kerb3961::Aes8009 *this, int a2)
{
  return a2 == *((_DWORD *)this + 16);
}

```

## disassembly

```asm
0x180007ac0  cmp     edx, [rcx+40h]
0x180007ac3  setz    al
0x180007ac6  retn
```
