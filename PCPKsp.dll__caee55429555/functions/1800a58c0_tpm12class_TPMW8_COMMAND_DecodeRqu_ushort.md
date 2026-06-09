# tpm12class::TPMW8_COMMAND::DecodeRqu(ushort *)

- ea: `0x1800a58c0`
- end: `0x1800a5994`
- name: `?DecodeRqu@TPMW8_COMMAND@tpm12class@@UEAAJPEAG@Z`
- size: `212`
- prototype: `int(tpm12class::TPMW8_COMMAND *__hidden this, unsigned __int16 *)`
- caller_count: `36`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800a4600`
- `0x1800a5e00`
- `0x1800aabe0`
- `0x1800aad00`
- `0x1800ab390`
- `0x1800ab800`
- `0x1800ab980`
- `0x1800abb40`
- `0x1800abf00`
- `0x1800ac2f0`
- `0x1800ac720`
- `0x1800ac970`
- `0x1800b26b0`
- `0x1800b2b20`
- `0x1800b3440`
- `0x1800b3b00`
- `0x1800b3ee0`
- `0x1800b4560`
- `0x1800b4690`
- `0x1800b4760`
- `0x1800b4d80`
- `0x1800b5020`
- `0x1800b57b0`
- `0x1800b5bd0`
- `0x1800b62e0`
- `0x1800b6940`
- `0x1800b6bc0`
- `0x1800b6fa0`
- `0x1800b7680`
- `0x1800b7c60`
- `0x1800b8090`
- `0x1800b9340`
- `0x1800b9870`
- `0x1800b9d50`
- `0x1800ba230`
- `0x1800c2b00`

## callees

- `0x18002a750`
- `0x1800a58c0`
- `0x1800bada0`
- `0x1800bb4d4`
- `0x1800bb7d0`

## string_xrefs

- `0x1800a5968`: `commandCode`
- `0x1800a58e4`: `TPMW8_COMMAND`
- `0x1800a592f`: `commandSize`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_COMMAND::DecodeRqu(tpm12class::TPMW8_COMMAND *this, unsigned __int16 *a2)
{
  int v4; // ebx

  v4 = 0;
  if ( TraceEnabled() )
  {
    v4 = TraceIdentifier(a2, L"TPMW8_COMMAND");
    if ( v4 >= 0 )
    {
      v4 = TraceUINT16Value(a2, L"tag", *((_WORD *)this + 28), 0, (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8_ST, 0);
      if ( v4 >= 0 )
      {
        v4 = TraceUINT32Value(a2, L"commandSize", *((_DWORD *)this + 15), 1u, 0, 0);
        if ( v4 >= 0 )
          return (unsigned int)TraceUINT32Value(
                                 a2,
                                 L"commandCode",
                                 *((_DWORD *)this + 40),
                                 0,
                                 (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8_CC,
                                 0);
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800a58c0  mov     [rsp+arg_0], rbx
0x1800a58c5  mov     [rsp+arg_8], rsi
0x1800a58ca  push    rdi
0x1800a58cb  sub     rsp, 30h
0x1800a58cf  mov     rdi, rdx
0x1800a58d2  mov     rsi, rcx
0x1800a58d5  xor     ebx, ebx
0x1800a58d7  call    ?TraceEnabled@@YAEXZ; TraceEnabled(void)
0x1800a58dc  test    al, al
0x1800a58de  jz      loc_1800A5981
0x1800a58e4  lea     rdx, aTpmw8Command; "TPMW8_COMMAND"
0x1800a58eb  mov     rcx, rdi; unsigned __int16 *
0x1800a58ee  call    ?TraceIdentifier@@YAJPEAG0@Z; TraceIdentifier(ushort *,ushort *)
0x1800a58f3  mov     ebx, eax
0x1800a58f5  test    eax, eax
0x1800a58f7  js      loc_1800A5981
0x1800a58fd  movzx   r8d, word ptr [rsi+38h]; unsigned __int16
0x1800a5902  lea     rax, ?st_TPMW8_ST@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_ST
0x1800a5909  mov     [rsp+38h+var_10], 0; char
0x1800a590e  lea     rdx, aTag; "tag"
0x1800a5915  xor     r9d, r9d; unsigned __int8
0x1800a5918  mov     [rsp+38h+var_18], rax; struct TPM_SYMBOLTABLE_ENTRY *
0x1800a591d  mov     rcx, rdi; unsigned __int16 *
0x1800a5920  call    ?TraceUINT16Value@@YAJPEAG0GEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT16Value(ushort *,ushort *,ushort,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800a5925  mov     ebx, eax
0x1800a5927  test    eax, eax
0x1800a5929  js      short loc_1800A5981
0x1800a592b  mov     r8d, [rsi+3Ch]; unsigned int
0x1800a592f  lea     rdx, aCommandsize; "commandSize"
0x1800a5936  mov     [rsp+38h+var_10], 0; unsigned __int8
0x1800a593b  mov     r9b, 1; unsigned __int8
0x1800a593e  mov     rcx, rdi; unsigned __int16 *
0x1800a5941  mov     [rsp+38h+var_18], 0; struct TPM_SYMBOLTABLE_ENTRY *
0x1800a594a  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800a594f  mov     ebx, eax
0x1800a5951  test    eax, eax
0x1800a5953  js      short loc_1800A5981
0x1800a5955  mov     r8d, [rsi+0A0h]; unsigned int
0x1800a595c  lea     rax, ?st_TPMW8_CC@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_CC
0x1800a5963  mov     [rsp+38h+var_10], 0; unsigned __int8
0x1800a5968  lea     rdx, aCommandcode; "commandCode"
0x1800a596f  xor     r9d, r9d; unsigned __int8
0x1800a5972  mov     [rsp+38h+var_18], rax; struct TPM_SYMBOLTABLE_ENTRY *
0x1800a5977  mov     rcx, rdi; unsigned __int16 *
0x1800a597a  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800a597f  mov     ebx, eax
0x1800a5981  mov     rsi, [rsp+38h+arg_8]
0x1800a5986  mov     eax, ebx
0x1800a5988  mov     rbx, [rsp+38h+arg_0]
0x1800a598d  add     rsp, 30h
0x1800a5991  pop     rdi
0x1800a5992  retn
```
