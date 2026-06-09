# tpm12class::TPM_COMMAND::DecodeRqu(ushort *)

- ea: `0x1800a1540`
- end: `0x1800a1611`
- name: `?DecodeRqu@TPM_COMMAND@tpm12class@@UEAAJPEAG@Z`
- size: `209`
- prototype: `int(tpm12class::TPM_COMMAND *__hidden this, unsigned __int16 *)`
- caller_count: `21`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800a12b0`
- `0x1800a17e0`
- `0x1800a19a0`
- `0x1800a1b80`
- `0x1800a2a30`
- `0x1800a3380`
- `0x1800ace40`
- `0x1800ad3d0`
- `0x1800ad7e0`
- `0x1800add10`
- `0x1800ae330`
- `0x1800ae890`
- `0x1800aeef0`
- `0x1800af6b0`
- `0x1800afd20`
- `0x1800b0590`
- `0x1800b22c0`
- `0x1800b84f0`
- `0x1800be710`
- `0x1800be960`
- `0x1800bed70`

## callees

- `0x18002a750`
- `0x1800a1540`
- `0x1800bada0`
- `0x1800bb4d4`
- `0x1800bb7d0`

## string_xrefs

- `0x1800a1564`: `TPM_COMMAND`
- `0x1800a15af`: `paramSize`

## pseudocode

```c
__int64 __fastcall tpm12class::TPM_COMMAND::DecodeRqu(tpm12class::TPM_COMMAND *this, unsigned __int16 *a2)
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
        v4 = TraceUINT32Value(a2, L"paramSize", *((_DWORD *)this + 14), 1u, 0, 0);
        if ( v4 >= 0 )
          return (unsigned int)TraceUINT32Value(
                                 a2,
                                 L"ordinal",
                                 *((_DWORD *)this + 21),
                                 0,
                                 (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPM_COMMAND_CODE,
                                 0);
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800a1540  mov     [rsp+arg_0], rbx
0x1800a1545  mov     [rsp+arg_8], rsi
0x1800a154a  push    rdi
0x1800a154b  sub     rsp, 30h
0x1800a154f  mov     rdi, rdx
0x1800a1552  mov     rsi, rcx
0x1800a1555  xor     ebx, ebx
0x1800a1557  call    ?TraceEnabled@@YAEXZ; TraceEnabled(void)
0x1800a155c  test    al, al
0x1800a155e  jz      loc_1800A15FE
0x1800a1564  lea     rdx, aTpmCommand; "TPM_COMMAND"
0x1800a156b  mov     rcx, rdi; unsigned __int16 *
0x1800a156e  call    ?TraceIdentifier@@YAJPEAG0@Z; TraceIdentifier(ushort *,ushort *)
0x1800a1573  mov     ebx, eax
0x1800a1575  test    eax, eax
0x1800a1577  js      loc_1800A15FE
0x1800a157d  movzx   r8d, word ptr [rsi+50h]; unsigned __int16
0x1800a1582  lea     rax, ?st_TPM_TAG@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPM_TAG
0x1800a1589  mov     [rsp+38h+var_10], 0; char
0x1800a158e  lea     rdx, aTag; "tag"
0x1800a1595  xor     r9d, r9d; unsigned __int8
0x1800a1598  mov     [rsp+38h+var_18], rax; struct TPM_SYMBOLTABLE_ENTRY *
0x1800a159d  mov     rcx, rdi; unsigned __int16 *
0x1800a15a0  call    ?TraceUINT16Value@@YAJPEAG0GEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT16Value(ushort *,ushort *,ushort,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800a15a5  mov     ebx, eax
0x1800a15a7  test    eax, eax
0x1800a15a9  js      short loc_1800A15FE
0x1800a15ab  mov     r8d, [rsi+38h]; unsigned int
0x1800a15af  lea     rdx, aParamsize; "paramSize"
0x1800a15b6  mov     [rsp+38h+var_10], 0; unsigned __int8
0x1800a15bb  mov     r9b, 1; unsigned __int8
0x1800a15be  mov     rcx, rdi; unsigned __int16 *
0x1800a15c1  mov     [rsp+38h+var_18], 0; struct TPM_SYMBOLTABLE_ENTRY *
0x1800a15ca  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800a15cf  mov     ebx, eax
0x1800a15d1  test    eax, eax
0x1800a15d3  js      short loc_1800A15FE
0x1800a15d5  mov     r8d, [rsi+54h]; unsigned int
0x1800a15d9  lea     rax, ?st_TPM_COMMAND_CODE@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPM_COMMAND_CODE
0x1800a15e0  mov     [rsp+38h+var_10], 0; unsigned __int8
0x1800a15e5  lea     rdx, aOrdinal; "ordinal"
0x1800a15ec  xor     r9d, r9d; unsigned __int8
0x1800a15ef  mov     [rsp+38h+var_18], rax; struct TPM_SYMBOLTABLE_ENTRY *
0x1800a15f4  mov     rcx, rdi; unsigned __int16 *
0x1800a15f7  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800a15fc  mov     ebx, eax
0x1800a15fe  mov     rsi, [rsp+38h+arg_8]
0x1800a1603  mov     eax, ebx
0x1800a1605  mov     rbx, [rsp+38h+arg_0]
0x1800a160a  add     rsp, 30h
0x1800a160e  pop     rdi
0x1800a160f  retn
```
