# Kerb3961::RC4_4757::CompatibleCipher(uint)

- ea: `0x18000f2b0`
- end: `0x18000f2b7`
- name: `?CompatibleCipher@RC4_4757@Kerb3961@@EEAA_NI@Z`
- size: `7`
- prototype: `bool __fastcall(Kerb3961::RC4_4757 *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
bool __fastcall Kerb3961::RC4_4757::CompatibleCipher(Kerb3961::RC4_4757 *this, int a2)
{
  return a2 == *((_DWORD *)this + 4);
}

```

## disassembly

```asm
0x18000f2b0  cmp     edx, [rcx+10h]
0x18000f2b3  setz    al
0x18000f2b6  retn
```
