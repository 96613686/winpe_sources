# Kerb3961::RC4_4757::PseudoRandom(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180009160`
- end: `0x180009188`
- name: `?PseudoRandom@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000f908`

## pseudocode

```c
__int64 __fastcall Kerb3961::RC4_4757::PseudoRandom(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4)
{
  Kerb3961::GetHmac(a2, (const char *)0x31, a3, a4, 0);
  return a2;
}

```

## disassembly

```asm
0x180009160  push    rbx
0x180009162  sub     rsp, 30h
0x180009166  mov     rbx, rdx
0x180009169  mov     [rsp+38h+var_18], 0
0x180009172  mov     rcx, rbx
0x180009175  mov     edx, 31h ; '1'
0x18000917a  call    ?GetHmac@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@PEAXAEBUReadOnlyBinary@1@1_K@Z; Kerb3961::GetHmac(void *,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)
0x18000917f  mov     rax, rbx
0x180009182  add     rsp, 30h
0x180009186  pop     rbx
0x180009187  retn
```
