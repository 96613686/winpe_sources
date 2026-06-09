# Kerb3961::Aes8009::PseudoRandom(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180008f50`
- end: `0x180008f8f`
- name: `?PseudoRandom@Aes8009@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180007e9c`

## pseudocode

```c
__int64 __fastcall Kerb3961::Aes8009::PseudoRandom(__int64 a1, __int64 a2, int a3, __int128 *a4)
{
  __int128 v6; // [rsp+30h] [rbp-18h] BYREF

  *(_QWORD *)&v6 = 3;
  *((_QWORD *)&v6 + 1) = "prf";
  Kerb3961::Aes8009::DeriveKey(a1, a2, a3, &v6, a4, *(unsigned int *)(a1 + 160));
  return a2;
}

```

## disassembly

```asm
0x180008f50  mov     r11, rsp
0x180008f53  push    rbx
0x180008f54  sub     rsp, 40h
0x180008f58  lea     rax, aPrf; "prf"
0x180008f5f  mov     qword ptr [r11-18h], 3
0x180008f67  mov     [r11-10h], rax
0x180008f6b  mov     rbx, rdx
0x180008f6e  mov     eax, [rcx+0A0h]
0x180008f74  mov     [r11-20h], rax
0x180008f78  mov     [r11-28h], r9
0x180008f7c  lea     r9, [r11-18h]
0x180008f80  call    ?DeriveKey@Aes8009@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00_K@Z; Kerb3961::Aes8009::DeriveKey(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)
0x180008f85  mov     rax, rbx
0x180008f88  add     rsp, 40h
0x180008f8c  pop     rbx
0x180008f8d  retn
```
