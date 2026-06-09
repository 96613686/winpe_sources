# Kerb3961::Aes3962::HashData(Kerb3961::ReadOnlyBinary const &)

- ea: `0x18001b510`
- end: `0x18001b552`
- name: `?HashData@Aes3962@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@@Z`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000f754`

## pseudocode

```c
__int64 __fastcall Kerb3961::Aes3962::HashData(__int64 a1, __int64 a2, __int64 a3)
{
  const char *v4; // rdx
  _QWORD v6[3]; // [rsp+30h] [rbp-18h] BYREF

  v6[0] = 0;
  v4 = *(const char **)(a1 + 176);
  v6[1] = 0;
  Kerb3961::GetHashCommon(a2, v4, v6, a3, 0x14u);
  return a2;
}

```

## disassembly

```asm
0x18001b510  mov     rax, rsp
0x18001b513  push    rbx
0x18001b514  sub     rsp, 40h
0x18001b518  mov     rbx, rdx
0x18001b51b  mov     qword ptr [rax-18h], 0
0x18001b523  mov     rdx, [rcx+0B0h]
0x18001b52a  mov     r9, r8
0x18001b52d  mov     rcx, rbx
0x18001b530  mov     qword ptr [rax-10h], 0
0x18001b538  lea     r8, [rax-18h]
0x18001b53c  mov     qword ptr [rax-28h], 14h
0x18001b544  call    ?GetHashCommon@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@PEAXAEBUReadOnlyBinary@1@1_K@Z; Kerb3961::GetHashCommon(void *,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)
0x18001b549  mov     rax, rbx
0x18001b54c  add     rsp, 40h
0x18001b550  pop     rbx
0x18001b551  retn
```
