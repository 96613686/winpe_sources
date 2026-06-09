# Kerb3961::Aes3962::BlockEncrypt(Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &,Kerb3961::MutableBinary const &)

- ea: `0x180018c20`
- end: `0x180018c6d`
- name: `?BlockEncrypt@Aes3962@Kerb3961@@EEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@AEBUMutableBinary@2@1@Z`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002c64`
- `0x18000f438`
- `0x180018c20`

## pseudocode

```c
NTSTATUS *__fastcall Kerb3961::Aes3962::BlockEncrypt(__int64 a1, NTSTATUS *a2, _QWORD *a3, _QWORD *a4, _QWORD *a5)
{
  if ( *a5 >= 0x10u )
  {
    Kerb3961::EncryptCTS(a2, *(char **)(a1 + 168), a3, a3, a4, a5);
  }
  else
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"clearText.length >= AES_BLOCK_SIZE",
      (const char *)a2);
    *a2 = -1073741789;
  }
  return a2;
}

```

## disassembly

```asm
0x180018c20  push    rbx
0x180018c22  sub     rsp, 30h
0x180018c26  mov     rax, [rsp+38h+arg_20]
0x180018c2b  mov     rbx, rdx
0x180018c2e  cmp     qword ptr [rax], 10h
0x180018c32  jnb     short loc_180018C48
0x180018c34  lea     rcx, aCleartextLengt; "clearText.length >= AES_BLOCK_SIZE"
0x180018c3b  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180018c40  mov     dword ptr [rbx], 0C0000023h
0x180018c46  jmp     short loc_180018C64
0x180018c48  mov     rdx, [rcx+0A8h]
0x180018c4f  mov     rcx, rbx
0x180018c52  mov     [rsp+38h+var_10], rax
0x180018c57  mov     [rsp+38h+var_18], r9
0x180018c5c  mov     r9, r8
0x180018c5f  call    ?EncryptCTS@Kerb3961@@YA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@1@PEAX_KAEBUReadOnlyBinary@1@AEBUMutableBinary@1@3@Z; Kerb3961::EncryptCTS(void *,unsigned __int64,Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &,Kerb3961::MutableBinary const &)
0x180018c64  mov     rax, rbx
0x180018c67  add     rsp, 30h
0x180018c6b  pop     rbx
0x180018c6c  retn
```
