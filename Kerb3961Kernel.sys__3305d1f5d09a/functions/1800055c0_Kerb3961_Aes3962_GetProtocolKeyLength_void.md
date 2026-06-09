# Kerb3961::Aes3962::GetProtocolKeyLength(void)

- ea: `0x1800055c0`
- end: `0x1800055c5`
- name: `?GetProtocolKeyLength@Aes3962@Kerb3961@@EEAA_KXZ`
- size: `5`
- prototype: `unsigned __int64 __fastcall(Kerb3961::Aes3962 *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
unsigned __int64 __fastcall Kerb3961::Aes3962::GetProtocolKeyLength(Kerb3961::Aes3962 *this)
{
  return *((_QWORD *)this + 13);
}

```

## disassembly

```asm
0x1800055c0  mov     rax, [rcx+68h]
0x1800055c4  retn
```
