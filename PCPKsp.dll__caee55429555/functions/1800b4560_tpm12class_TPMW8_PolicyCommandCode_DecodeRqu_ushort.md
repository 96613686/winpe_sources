# tpm12class::TPMW8_PolicyCommandCode::DecodeRqu(ushort *)

- ea: `0x1800b4560`
- end: `0x1800b462c`
- name: `?DecodeRqu@TPMW8_PolicyCommandCode@tpm12class@@UEAAJPEAG@Z`
- size: `204`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_PolicyCommandCode *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18002a750`
- `0x1800a58c0`
- `0x1800b4560`
- `0x1800bacf4`
- `0x1800bb7d0`

## string_xrefs

- `0x1800b4599`: `--TPM2_PolicyCommandCode: Handles--------------------------------------\n`
- `0x1800b45db`: `--TPM2_PolicyCommandCode: Parameters-----------------------------------\n`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_PolicyCommandCode::DecodeRqu(
        tpm12class::TPMW8_PolicyCommandCode *this,
        unsigned __int16 *a2)
{
  int v4; // ebx

  v4 = 0;
  if ( TraceEnabled() )
  {
    v4 = tpm12class::TPMW8_COMMAND::DecodeRqu(this, a2);
    if ( v4 >= 0 )
    {
      v4 = TraceDirect(L"--TPM2_PolicyCommandCode: Handles--------------------------------------\r\n");
      if ( v4 >= 0 )
      {
        v4 = TraceUINT32Value(
               a2,
               L"policySession",
               *((_DWORD *)this + 48),
               0,
               (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8_RH,
               1u);
        if ( v4 >= 0 )
        {
          v4 = TraceDirect(L"--TPM2_PolicyCommandCode: Parameters-----------------------------------\r\n");
          if ( v4 >= 0 )
            return (unsigned int)TraceUINT32Value(
                                   a2,
                                   L"code",
                                   *((_DWORD *)this + 49),
                                   0,
                                   (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8_CC,
                                   0);
        }
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800b4560  mov     [rsp+arg_0], rbx
0x1800b4565  mov     [rsp+arg_8], rsi
0x1800b456a  push    rdi
0x1800b456b  sub     rsp, 30h
0x1800b456f  mov     rdi, rdx
0x1800b4572  mov     rsi, rcx
0x1800b4575  xor     ebx, ebx
0x1800b4577  call    ?TraceEnabled@@YAEXZ; TraceEnabled(void)
0x1800b457c  test    al, al
0x1800b457e  jz      loc_1800B4619
0x1800b4584  mov     rdx, rdi; unsigned __int16 *
0x1800b4587  mov     rcx, rsi; this
0x1800b458a  call    ?DecodeRqu@TPMW8_COMMAND@tpm12class@@UEAAJPEAG@Z; tpm12class::TPMW8_COMMAND::DecodeRqu(ushort *)
0x1800b458f  mov     ebx, eax
0x1800b4591  test    eax, eax
0x1800b4593  js      loc_1800B4619
0x1800b4599  lea     rcx, aTpm2Policycomm_0; "--TPM2_PolicyCommandCode: Handles------"...
0x1800b45a0  call    ?TraceDirect@@YAJPEAG@Z; TraceDirect(ushort *)
0x1800b45a5  mov     ebx, eax
0x1800b45a7  test    eax, eax
0x1800b45a9  js      short loc_1800B4619
0x1800b45ab  mov     r8d, [rsi+0C0h]; unsigned int
0x1800b45b2  lea     rax, ?st_TPMW8_RH@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_RH
0x1800b45b9  mov     [rsp+38h+var_10], 1; unsigned __int8
0x1800b45be  lea     rdx, aPolicysession; "policySession"
0x1800b45c5  xor     r9d, r9d; unsigned __int8
0x1800b45c8  mov     [rsp+38h+var_18], rax; struct TPM_SYMBOLTABLE_ENTRY *
0x1800b45cd  mov     rcx, rdi; unsigned __int16 *
0x1800b45d0  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800b45d5  mov     ebx, eax
0x1800b45d7  test    eax, eax
0x1800b45d9  js      short loc_1800B4619
0x1800b45db  lea     rcx, aTpm2Policycomm; "--TPM2_PolicyCommandCode: Parameters---"...
0x1800b45e2  call    ?TraceDirect@@YAJPEAG@Z; TraceDirect(ushort *)
0x1800b45e7  mov     ebx, eax
0x1800b45e9  test    eax, eax
0x1800b45eb  js      short loc_1800B4619
0x1800b45ed  mov     r8d, [rsi+0C4h]; unsigned int
0x1800b45f4  lea     rax, ?st_TPMW8_CC@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_CC
0x1800b45fb  mov     [rsp+38h+var_10], 0; unsigned __int8
0x1800b4600  lea     rdx, aCode; "code"
0x1800b4607  xor     r9d, r9d; unsigned __int8
0x1800b460a  mov     [rsp+38h+var_18], rax; struct TPM_SYMBOLTABLE_ENTRY *
0x1800b460f  mov     rcx, rdi; unsigned __int16 *
0x1800b4612  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800b4617  mov     ebx, eax
0x1800b4619  mov     rsi, [rsp+38h+arg_8]
0x1800b461e  mov     eax, ebx
0x1800b4620  mov     rbx, [rsp+38h+arg_0]
0x1800b4625  add     rsp, 30h
0x1800b4629  pop     rdi
0x1800b462a  retn
```
