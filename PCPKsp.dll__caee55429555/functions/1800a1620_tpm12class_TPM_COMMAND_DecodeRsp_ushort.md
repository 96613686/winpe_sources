# tpm12class::TPM_COMMAND::DecodeRsp(ushort *)

- ea: `0x1800a1620`
- end: `0x1800a16f1`
- name: `?DecodeRsp@TPM_COMMAND@tpm12class@@UEAAJPEAG@Z`
- size: `209`
- prototype: `int(tpm12class::TPM_COMMAND *__hidden this, unsigned __int16 *)`
- caller_count: `22`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002bb88`
- `0x1800a1340`
- `0x1800a1870`
- `0x1800a1a30`
- `0x1800a1c60`
- `0x1800a2c40`
- `0x1800a34a0`
- `0x1800acf20`
- `0x1800ad4b0`
- `0x1800ad900`
- `0x1800addf0`
- `0x1800ae3f0`
- `0x1800ae9f0`
- `0x1800af020`
- `0x1800af850`
- `0x1800afe90`
- `0x1800b0760`
- `0x1800b23a0`
- `0x1800b85e0`
- `0x1800be770`
- `0x1800bea40`
- `0x1800bf020`

## callees

- `0x18002a750`
- `0x1800a1620`
- `0x1800bada0`
- `0x1800bb4d4`
- `0x1800bb7d0`

## string_xrefs

- `0x1800a1644`: `TPM_COMMAND`
- `0x1800a168f`: `paramSize`

## pseudocode

```c
__int64 __fastcall tpm12class::TPM_COMMAND::DecodeRsp(tpm12class::TPM_COMMAND *this, unsigned __int16 *a2)
{
  int v4; // ebx

  v4 = 0;
  if ( TraceEnabled() )
  {
    v4 = TraceIdentifier(a2, L"TPM_COMMAND");
    if ( v4 >= 0 )
    {
      v4 = TraceUINT16Value(a2, L"tag", *((_WORD *)this + 40), 0, (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPM_TAG, 0);
      if ( v4 >= 0 )
      {
        v4 = TraceUINT32Value(a2, L"paramSize", *((_DWORD *)this + 15), 1u, 0, 0);
        if ( v4 >= 0 )
          return (unsigned int)TraceUINT32Value(
                                 a2,
                                 L"returnCode",
                                 *((_DWORD *)this + 22),
                                 0,
                                 (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPM_RESULT,
                                 0);
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800a1620  mov     [rsp+arg_0], rbx
0x1800a1625  mov     [rsp+arg_8], rsi
0x1800a162a  push    rdi
0x1800a162b  sub     rsp, 30h
0x1800a162f  mov     rdi, rdx
0x1800a1632  mov     rsi, rcx
0x1800a1635  xor     ebx, ebx
0x1800a1637  call    ?TraceEnabled@@YAEXZ; TraceEnabled(void)
0x1800a163c  test    al, al
0x1800a163e  jz      loc_1800A16DE
0x1800a1644  lea     rdx, aTpmCommand; "TPM_COMMAND"
0x1800a164b  mov     rcx, rdi; unsigned __int16 *
0x1800a164e  call    ?TraceIdentifier@@YAJPEAG0@Z; TraceIdentifier(ushort *,ushort *)
0x1800a1653  mov     ebx, eax
0x1800a1655  test    eax, eax
0x1800a1657  js      loc_1800A16DE
0x1800a165d  movzx   r8d, word ptr [rsi+50h]; unsigned __int16
0x1800a1662  lea     rax, ?st_TPM_TAG@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPM_TAG
0x1800a1669  mov     [rsp+38h+var_10], 0; char
0x1800a166e  lea     rdx, aTag; "tag"
0x1800a1675  xor     r9d, r9d; unsigned __int8
0x1800a1678  mov     [rsp+38h+var_18], rax; struct TPM_SYMBOLTABLE_ENTRY *
0x1800a167d  mov     rcx, rdi; unsigned __int16 *
0x1800a1680  call    ?TraceUINT16Value@@YAJPEAG0GEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT16Value(ushort *,ushort *,ushort,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800a1685  mov     ebx, eax
0x1800a1687  test    eax, eax
0x1800a1689  js      short loc_1800A16DE
0x1800a168b  mov     r8d, [rsi+3Ch]; unsigned int
0x1800a168f  lea     rdx, aParamsize; "paramSize"
0x1800a1696  mov     [rsp+38h+var_10], 0; unsigned __int8
0x1800a169b  mov     r9b, 1; unsigned __int8
0x1800a169e  mov     rcx, rdi; unsigned __int16 *
0x1800a16a1  mov     [rsp+38h+var_18], 0; struct TPM_SYMBOLTABLE_ENTRY *
0x1800a16aa  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800a16af  mov     ebx, eax
0x1800a16b1  test    eax, eax
0x1800a16b3  js      short loc_1800A16DE
0x1800a16b5  mov     r8d, [rsi+58h]; unsigned int
0x1800a16b9  lea     rax, ?st_TPM_RESULT@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPM_RESULT
0x1800a16c0  mov     [rsp+38h+var_10], 0; unsigned __int8
0x1800a16c5  lea     rdx, aReturncode; "returnCode"
0x1800a16cc  xor     r9d, r9d; unsigned __int8
0x1800a16cf  mov     [rsp+38h+var_18], rax; struct TPM_SYMBOLTABLE_ENTRY *
0x1800a16d4  mov     rcx, rdi; unsigned __int16 *
0x1800a16d7  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800a16dc  mov     ebx, eax
0x1800a16de  mov     rsi, [rsp+38h+arg_8]
0x1800a16e3  mov     eax, ebx
0x1800a16e5  mov     rbx, [rsp+38h+arg_0]
0x1800a16ea  add     rsp, 30h
0x1800a16ee  pop     rdi
0x1800a16ef  retn
```
