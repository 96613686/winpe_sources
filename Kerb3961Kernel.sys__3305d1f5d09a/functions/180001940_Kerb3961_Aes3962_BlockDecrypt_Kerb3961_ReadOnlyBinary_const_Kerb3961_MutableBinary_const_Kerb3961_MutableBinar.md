# Kerb3961::Aes3962::BlockDecrypt(Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &,Kerb3961::MutableBinary const &)

- ea: `0x180001940`
- end: `0x18000198e`
- name: `?BlockDecrypt@Aes3962@Kerb3961@@EEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@AEBUMutableBinary@2@1@Z`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001940`
- `0x180009c48`
- `0x180011760`

## pseudocode

```c
NTSTATUS *__fastcall Kerb3961::Aes3962::BlockDecrypt(
        __int64 a1,
        NTSTATUS *a2,
        _QWORD *a3,
        _QWORD *a4,
        unsigned int *a5)
{
  if ( *(_QWORD *)a5 >= 0x10u )
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
0x180001940  push    rbx
0x180001942  sub     rsp, 30h
0x180001946  mov     rax, [rsp+38h+arg_20]
0x18000194b  mov     rbx, rdx
0x18000194e  cmp     qword ptr [rax], 10h
0x180001952  jnb     short loc_180001968
0x180001954  lea     rcx, aCiphertextLeng_1; "cipherText.length >= AES_BLOCK_SIZE"
0x18000195b  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180001960  mov     dword ptr [rbx], 0C0000023h
0x180001966  jmp     short loc_180001984
0x180001968  mov     rdx, [rcx+0A8h]
0x18000196f  mov     rcx, rbx
0x180001972  mov     [rsp+38h+var_10], rax
0x180001977  mov     [rsp+38h+var_18], r9
0x18000197c  mov     r9, r8
0x18000197f  call    ?DecryptCTS@Kerb3961@@YA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@1@PEAX_KAEBUReadOnlyBinary@1@AEBUMutableBinary@1@3@Z; Kerb3961::DecryptCTS(void *,unsigned __int64,Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &,Kerb3961::MutableBinary const &)
0x180001984  mov     rax, rbx
0x180001987  add     rsp, 30h
0x18000198b  pop     rbx
0x18000198c  retn
```
