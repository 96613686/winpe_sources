# Kerb3961::Aes3962::GetChecksumName(void)

- ea: `0x18001b250`
- end: `0x18001b270`
- name: `?GetChecksumName@Aes3962@Kerb3961@@EEAA?BU?$ReturnType@UReadOnlyStringResult@Kerb3961@@$1??$SingleGetter@UReadOnlyStringResult@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UReadOnlyStringResult@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@XZ`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall Kerb3961::Aes3962::GetChecksumName(__int64 a1, __int64 a2)
{
  __int64 v2; // r8
  __int64 result; // rax

  v2 = *(_QWORD *)(a1 + 128);
  *(_QWORD *)a2 = *(_QWORD *)(a1 + 136);
  result = a2;
  *(_QWORD *)(a2 + 8) = v2;
  *(_DWORD *)(a2 + 16) = 0;
  return result;
}

```

## disassembly

```asm
0x18001b250  mov     rax, [rcx+88h]
0x18001b257  mov     r8, [rcx+80h]
0x18001b25e  mov     [rdx], rax
0x18001b261  mov     rax, rdx
0x18001b264  mov     [rdx+8], r8
0x18001b268  mov     dword ptr [rdx+10h], 0
0x18001b26f  retn
```
