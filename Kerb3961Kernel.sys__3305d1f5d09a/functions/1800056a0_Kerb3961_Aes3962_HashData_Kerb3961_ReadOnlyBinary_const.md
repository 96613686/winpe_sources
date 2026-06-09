# Kerb3961::Aes3962::HashData(Kerb3961::ReadOnlyBinary const &)

- ea: `0x1800056a0`
- end: `0x1800056e3`
- name: `?HashData@Aes3962@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@@Z`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a500`

## pseudocode

```c
__int64 __fastcall Kerb3961::Aes3962::HashData(__int64 a1, __int64 a2, __int64 a3)
{
  char *v4; // rdx
  _QWORD v6[3]; // [rsp+30h] [rbp-18h] BYREF

  v6[0] = 0;
  v4 = *(char **)(a1 + 176);
  v6[1] = 0;
  Kerb3961::GetHashCommon(a2, v4, v6, a3, (const char *)0x14);
  return a2;
}

```

## disassembly

```asm
0x1800056a0  mov     rax, rsp
0x1800056a3  push    rbx
0x1800056a4  sub     rsp, 40h
0x1800056a8  mov     rbx, rdx
0x1800056ab  mov     qword ptr [rax-18h], 0
0x1800056b3  mov     rdx, [rcx+0B0h]
0x1800056ba  mov     r9, r8
0x1800056bd  mov     rcx, rbx
0x1800056c0  mov     qword ptr [rax-10h], 0
0x1800056c8  lea     r8, [rax-18h]
0x1800056cc  mov     qword ptr [rax-28h], 14h
0x1800056d4  call    ?GetHashCommon@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@PEAXAEBUReadOnlyBinary@1@1_K@Z; Kerb3961::GetHashCommon(void *,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)
0x1800056d9  mov     rax, rbx
0x1800056dc  add     rsp, 40h
0x1800056e0  pop     rbx
0x1800056e1  retn
```
