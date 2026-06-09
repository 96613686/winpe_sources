# Kerb3961::RC4_4757::GetChecksumName(void)

- ea: `0x180007ef0`
- end: `0x180007f0a`
- name: `?GetChecksumName@RC4_4757@Kerb3961@@EEAA?BU?$ReturnType@UReadOnlyStringResult@Kerb3961@@$1??$SingleGetter@UReadOnlyStringResult@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UReadOnlyStringResult@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@XZ`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall Kerb3961::RC4_4757::GetChecksumName(__int64 a1, __int64 a2)
{
  __int64 v2; // r8
  __int64 result; // rax

  v2 = *(_QWORD *)(a1 + 48);
  *(_QWORD *)a2 = *(_QWORD *)(a1 + 56);
  result = a2;
  *(_QWORD *)(a2 + 8) = v2;
  *(_DWORD *)(a2 + 16) = 0;
  return result;
}

```

## disassembly

```asm
0x180007ef0  mov     rax, [rcx+38h]
0x180007ef4  mov     r8, [rcx+30h]
0x180007ef8  mov     [rdx], rax
0x180007efb  mov     rax, rdx
0x180007efe  mov     [rdx+8], r8
0x180007f02  mov     dword ptr [rdx+10h], 0
0x180007f09  retn
```
