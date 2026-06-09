# Kerb3961::RC4_4757::PseudoRandom(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180010260`
- end: `0x180010289`
- name: `?PseudoRandom@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000a6c0`

## pseudocode

```c
__int64 __fastcall Kerb3961::RC4_4757::PseudoRandom(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4)
{
  Kerb3961::GetHmac(a2, (char *)0x31, a3, a4, 0);
  return a2;
}

```

## disassembly

```asm
0x180010260  push    rbx
0x180010262  sub     rsp, 30h
0x180010266  mov     rbx, rdx
0x180010269  mov     [rsp+38h+var_18], 0
0x180010272  mov     rcx, rbx
0x180010275  mov     edx, 31h ; '1'
0x18001027a  call    ?GetHmac@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@PEAXAEBUReadOnlyBinary@1@1_K@Z; Kerb3961::GetHmac(void *,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)
0x18001027f  mov     rax, rbx
0x180010282  add     rsp, 30h
0x180010286  pop     rbx
0x180010287  retn
```
