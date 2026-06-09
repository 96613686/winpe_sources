# Kerb3961::Aes3962::GetCipherName(void)

- ea: `0x18001b2d0`
- end: `0x18001b2ed`
- name: `?GetCipherName@Aes3962@Kerb3961@@EEAA?BU?$ReturnType@UReadOnlyStringResult@Kerb3961@@$1??$SingleGetter@UReadOnlyStringResult@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UReadOnlyStringResult@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@XZ`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall Kerb3961::Aes3962::GetCipherName(__int64 a1, __int64 a2)
{
  __int64 v2; // r8
  __int64 result; // rax

  v2 = *(_QWORD *)(a1 + 120);
  *(_QWORD *)a2 = *(_QWORD *)(a1 + 128);
  result = a2;
  *(_QWORD *)(a2 + 8) = v2;
  *(_DWORD *)(a2 + 16) = 0;
  return result;
}

```

## disassembly

```asm
0x18001b2d0  mov     rax, [rcx+80h]
0x18001b2d7  mov     r8, [rcx+78h]
0x18001b2db  mov     [rdx], rax
0x18001b2de  mov     rax, rdx
0x18001b2e1  mov     [rdx+8], r8
0x18001b2e5  mov     dword ptr [rdx+10h], 0
0x18001b2ec  retn
```
