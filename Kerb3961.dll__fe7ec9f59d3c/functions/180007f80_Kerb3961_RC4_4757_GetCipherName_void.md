# Kerb3961::RC4_4757::GetCipherName(void)

- ea: `0x180007f80`
- end: `0x180007f9a`
- name: `?GetCipherName@RC4_4757@Kerb3961@@EEAA?BU?$ReturnType@UReadOnlyStringResult@Kerb3961@@$1??$SingleGetter@UReadOnlyStringResult@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UReadOnlyStringResult@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@XZ`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall Kerb3961::RC4_4757::GetCipherName(__int64 a1, __int64 a2)
{
  __int64 v2; // r8
  __int64 result; // rax

  v2 = *(_QWORD *)(a1 + 40);
  *(_QWORD *)a2 = *(_QWORD *)(a1 + 48);
  result = a2;
  *(_QWORD *)(a2 + 8) = v2;
  *(_DWORD *)(a2 + 16) = 0;
  return result;
}

```

## disassembly

```asm
0x180007f80  mov     rax, [rcx+30h]
0x180007f84  mov     r8, [rcx+28h]
0x180007f88  mov     [rdx], rax
0x180007f8b  mov     rax, rdx
0x180007f8e  mov     [rdx+8], r8
0x180007f92  mov     dword ptr [rdx+10h], 0
0x180007f99  retn
```
