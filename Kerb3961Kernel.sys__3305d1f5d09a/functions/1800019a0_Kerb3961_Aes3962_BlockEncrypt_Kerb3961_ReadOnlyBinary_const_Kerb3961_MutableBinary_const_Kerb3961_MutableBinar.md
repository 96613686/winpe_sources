# Kerb3961::Aes3962::BlockEncrypt(Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &,Kerb3961::MutableBinary const &)

- ea: `0x1800019a0`
- end: `0x1800019ee`
- name: `?BlockEncrypt@Aes3962@Kerb3961@@EEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@AEBUMutableBinary@2@1@Z`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800019a0`
- `0x18000a1c8`
- `0x180011760`

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
0x1800019a0  push    rbx
0x1800019a2  sub     rsp, 30h
0x1800019a6  mov     rax, [rsp+38h+arg_20]
0x1800019ab  mov     rbx, rdx
0x1800019ae  cmp     qword ptr [rax], 10h
0x1800019b2  jnb     short loc_1800019C8
0x1800019b4  lea     rcx, aCleartextLengt; "clearText.length >= AES_BLOCK_SIZE"
0x1800019bb  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800019c0  mov     dword ptr [rbx], 0C0000023h
0x1800019c6  jmp     short loc_1800019E4
0x1800019c8  mov     rdx, [rcx+0A8h]
0x1800019cf  mov     rcx, rbx
0x1800019d2  mov     [rsp+38h+var_10], rax
0x1800019d7  mov     [rsp+38h+var_18], r9
0x1800019dc  mov     r9, r8
0x1800019df  call    ?EncryptCTS@Kerb3961@@YA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@1@PEAX_KAEBUReadOnlyBinary@1@AEBUMutableBinary@1@3@Z; Kerb3961::EncryptCTS(void *,unsigned __int64,Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &,Kerb3961::MutableBinary const &)
0x1800019e4  mov     rax, rbx
0x1800019e7  add     rsp, 30h
0x1800019eb  pop     rbx
0x1800019ec  retn
```
