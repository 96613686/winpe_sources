# Kerb3961::Aes3962::BlockDecrypt(Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &,Kerb3961::MutableBinary const &)

- ea: `0x180018bc0`
- end: `0x180018c0d`
- name: `?BlockDecrypt@Aes3962@Kerb3961@@EEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@AEBUMutableBinary@2@1@Z`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002c64`
- `0x18000eee8`
- `0x180018bc0`

## pseudocode

```c
NTSTATUS *__fastcall Kerb3961::Aes3962::BlockDecrypt(__int64 a1, NTSTATUS *a2, _QWORD *a3, _QWORD *a4, _QWORD *a5)
{
  if ( *a5 >= 0x10u )
  {
    Kerb3961::DecryptCTS(a2, *(char **)(a1 + 168), a3, a3, a4, a5);
  }
  else
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"cipherText.length >= AES_BLOCK_SIZE",
      (const char *)a2);
    *a2 = -1073741789;
  }
  return a2;
}

```

## disassembly

```asm
0x180018bc0  push    rbx
0x180018bc2  sub     rsp, 30h
0x180018bc6  mov     rax, [rsp+38h+arg_20]
0x180018bcb  mov     rbx, rdx
0x180018bce  cmp     qword ptr [rax], 10h
0x180018bd2  jnb     short loc_180018BE8
0x180018bd4  lea     rcx, aCiphertextLeng_1; "cipherText.length >= AES_BLOCK_SIZE"
0x180018bdb  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180018be0  mov     dword ptr [rbx], 0C0000023h
0x180018be6  jmp     short loc_180018C04
0x180018be8  mov     rdx, [rcx+0A8h]
0x180018bef  mov     rcx, rbx
0x180018bf2  mov     [rsp+38h+var_10], rax
0x180018bf7  mov     [rsp+38h+var_18], r9
0x180018bfc  mov     r9, r8
0x180018bff  call    ?DecryptCTS@Kerb3961@@YA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@1@PEAX_KAEBUReadOnlyBinary@1@AEBUMutableBinary@1@3@Z; Kerb3961::DecryptCTS(void *,unsigned __int64,Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &,Kerb3961::MutableBinary const &)
0x180018c04  mov     rax, rbx
0x180018c07  add     rsp, 30h
0x180018c0b  pop     rbx
0x180018c0c  retn
```
