# tpm12class::TPM_CreateMigrationBlob::DecodeRsp(ushort *)

- ea: `0x1800af850`
- end: `0x1800af94b`
- name: `?DecodeRsp@TPM_CreateMigrationBlob@tpm12class@@UEAAJPEAG@Z`
- size: `251`
- prototype: `__int64 __fastcall(tpm12class::TPM_CreateMigrationBlob *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18002a750`
- `0x1800a1620`
- `0x1800af850`
- `0x1800ba830`
- `0x1800bada0`
- `0x1800bb7d0`

## string_xrefs

- `0x1800af889`: `TPM_CreateMigrationBlob`
- `0x1800af8a6`: `randomSize`

## pseudocode

```c
__int64 __fastcall tpm12class::TPM_CreateMigrationBlob::DecodeRsp(
        tpm12class::TPM_CreateMigrationBlob *this,
        unsigned __int16 *a2)
{
  int v4; // ebx

  v4 = 0;
  if ( TraceEnabled() )
  {
    v4 = tpm12class::TPM_COMMAND::DecodeRsp(this, a2);
    if ( v4 >= 0 )
    {
      v4 = TraceIdentifier(a2, L"TPM_CreateMigrationBlob");
      if ( v4 >= 0 )
      {
        v4 = TraceUINT32Value(a2, L"randomSize", *((_DWORD *)this + 28), 1u, 0, 0);
        if ( v4 >= 0 )
        {
          v4 = TraceBufferValue(a2, L"random", *((unsigned __int8 **)this + 17), *((_DWORD *)this + 32));
          if ( v4 >= 0 )
          {
            v4 = TraceUINT32Value(a2, L"outDataSize", *((_DWORD *)this + 28), 1u, 0, 0);
            if ( v4 >= 0 )
              return (unsigned int)TraceBufferValue(
                                     a2,
                                     L"outData",
                                     *((unsigned __int8 **)this + 19),
                                     *((_DWORD *)this + 36));
          }
        }
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800af850  mov     [rsp+arg_0], rbx
0x1800af855  mov     [rsp+arg_8], rsi
0x1800af85a  push    rdi
0x1800af85b  sub     rsp, 30h
0x1800af85f  mov     rsi, rdx
0x1800af862  mov     rdi, rcx
0x1800af865  xor     ebx, ebx
0x1800af867  call    ?TraceEnabled@@YAEXZ; TraceEnabled(void)
0x1800af86c  test    al, al
0x1800af86e  jz      loc_1800AF938
0x1800af874  mov     rdx, rsi; unsigned __int16 *
0x1800af877  mov     rcx, rdi; this
0x1800af87a  call    ?DecodeRsp@TPM_COMMAND@tpm12class@@UEAAJPEAG@Z; tpm12class::TPM_COMMAND::DecodeRsp(ushort *)
0x1800af87f  mov     ebx, eax
0x1800af881  test    eax, eax
0x1800af883  js      loc_1800AF938
0x1800af889  lea     rdx, aTpmCreatemigra; "TPM_CreateMigrationBlob"
0x1800af890  mov     rcx, rsi; unsigned __int16 *
0x1800af893  call    ?TraceIdentifier@@YAJPEAG0@Z; TraceIdentifier(ushort *,ushort *)
0x1800af898  mov     ebx, eax
0x1800af89a  test    eax, eax
0x1800af89c  js      loc_1800AF938
0x1800af8a2  mov     r8d, [rdi+70h]; unsigned int
0x1800af8a6  lea     rdx, aRandomsize; "randomSize"
0x1800af8ad  mov     [rsp+38h+var_10], 0; unsigned __int8
0x1800af8b2  mov     r9b, 1; unsigned __int8
0x1800af8b5  mov     rcx, rsi; unsigned __int16 *
0x1800af8b8  mov     [rsp+38h+var_18], 0; struct TPM_SYMBOLTABLE_ENTRY *
0x1800af8c1  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800af8c6  mov     ebx, eax
0x1800af8c8  test    eax, eax
0x1800af8ca  js      short loc_1800AF938
0x1800af8cc  mov     r9d, [rdi+80h]; unsigned int
0x1800af8d3  lea     rdx, aRandom; "random"
0x1800af8da  mov     r8, [rdi+88h]; unsigned __int8 *
0x1800af8e1  mov     rcx, rsi; unsigned __int16 *
0x1800af8e4  call    ?TraceBufferValue@@YAJPEAG0PEAEI@Z; TraceBufferValue(ushort *,ushort *,uchar *,uint)
0x1800af8e9  mov     ebx, eax
0x1800af8eb  test    eax, eax
0x1800af8ed  js      short loc_1800AF938
0x1800af8ef  mov     r8d, [rdi+70h]; unsigned int
0x1800af8f3  lea     rdx, aOutdatasize; "outDataSize"
0x1800af8fa  mov     [rsp+38h+var_10], 0; unsigned __int8
0x1800af8ff  mov     r9b, 1; unsigned __int8
0x1800af902  mov     rcx, rsi; unsigned __int16 *
0x1800af905  mov     [rsp+38h+var_18], 0; struct TPM_SYMBOLTABLE_ENTRY *
0x1800af90e  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800af913  mov     ebx, eax
0x1800af915  test    eax, eax
0x1800af917  js      short loc_1800AF938
0x1800af919  mov     r9d, [rdi+90h]; unsigned int
0x1800af920  lea     rdx, aOutdata; "outData"
0x1800af927  mov     r8, [rdi+98h]; unsigned __int8 *
0x1800af92e  mov     rcx, rsi; unsigned __int16 *
0x1800af931  call    ?TraceBufferValue@@YAJPEAG0PEAEI@Z; TraceBufferValue(ushort *,ushort *,uchar *,uint)
0x1800af936  mov     ebx, eax
0x1800af938  mov     rsi, [rsp+38h+arg_8]
0x1800af93d  mov     eax, ebx
0x1800af93f  mov     rbx, [rsp+38h+arg_0]
0x1800af944  add     rsp, 30h
0x1800af948  pop     rdi
0x1800af949  retn
```
