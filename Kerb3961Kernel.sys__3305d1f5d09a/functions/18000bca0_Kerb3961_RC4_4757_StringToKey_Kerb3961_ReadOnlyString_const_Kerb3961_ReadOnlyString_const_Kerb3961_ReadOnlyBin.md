# Kerb3961::RC4_4757::StringToKey(Kerb3961::ReadOnlyString const &,Kerb3961::ReadOnlyString const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x18000bca0`
- end: `0x18000bcba`
- name: `?StringToKey@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyString@2@0AEBUReadOnlyBinary@2@@Z`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall Kerb3961::RC4_4757::StringToKey(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  *(_QWORD *)a2 = 0;
  result = a2;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 16) = -1073741823;
  return result;
}

```

## disassembly

```asm
0x18000bca0  mov     qword ptr [rdx], 0
0x18000bca7  mov     rax, rdx
0x18000bcaa  mov     qword ptr [rdx+8], 0
0x18000bcb2  mov     dword ptr [rdx+10h], 0C0000001h
0x18000bcb9  retn
```
