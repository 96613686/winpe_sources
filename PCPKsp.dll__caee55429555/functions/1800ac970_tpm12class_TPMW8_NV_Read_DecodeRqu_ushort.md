# tpm12class::TPMW8_NV_Read::DecodeRqu(ushort *)

- ea: `0x1800ac970`
- end: `0x1800acaa1`
- name: `?DecodeRqu@TPMW8_NV_Read@tpm12class@@UEAAJPEAG@Z`
- size: `305`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_NV_Read *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18002a750`
- `0x1800a5470`
- `0x1800a57f4`
- `0x1800a58c0`
- `0x1800ac970`
- `0x1800bacf4`
- `0x1800bb4d4`

## string_xrefs

- `0x1800ac9a9`: `--TPM2_NV_Read: Handles----------------------------------------------\n`
- `0x1800aca24`: `--TPM2_NV_Read: Parameters-------------------------------------------\n`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_NV_Read::DecodeRqu(tpm12class::TPMW8_NV_Read *this, unsigned __int16 *a2)
{
  int v4; // ebx
  tpm12class::TPMW8_COMMAND *v5; // rcx
  tpm12class::TPMW8_COMMAND *v6; // rcx

  v4 = 0;
  if ( TraceEnabled() )
  {
    v4 = tpm12class::TPMW8_COMMAND::DecodeRqu(this, a2);
    if ( v4 >= 0 )
    {
      v4 = TraceDirect(L"--TPM2_NV_Read: Handles----------------------------------------------\r\n");
      if ( v4 >= 0 )
      {
        v4 = tpm12class::TPMW8_COMMAND::DecodeHandle(
               v5,
               a2,
               L"authHandle",
               *((_DWORD *)this + 48),
               (tpm12class::TPMW8_NV_Read *)((char *)this + 200));
        if ( v4 >= 0 )
        {
          v4 = tpm12class::TPMW8_COMMAND::DecodeHandle(
                 v6,
                 a2,
                 L"nvIndex",
                 *((_DWORD *)this + 68),
                 (tpm12class::TPMW8_NV_Read *)((char *)this + 280));
          if ( v4 >= 0 )
          {
            v4 = tpm12class::TPMW8_COMMAND::DecodeAuthorizationsRqu(this, a2);
            if ( v4 >= 0 )
            {
              v4 = TraceDirect(L"--TPM2_NV_Read: Parameters-------------------------------------------\r\n");
              if ( v4 >= 0 )
              {
                v4 = TraceUINT16Value(a2, L"size", *((_WORD *)this + 176), 1u, 0, 0);
                if ( v4 >= 0 )
                  return (unsigned int)TraceUINT16Value(a2, L"offset", *((_WORD *)this + 177), 1u, 0, 0);
              }
            }
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
0x1800ac970  mov     [rsp+arg_0], rbx
0x1800ac975  mov     [rsp+arg_8], rsi
0x1800ac97a  push    rdi
0x1800ac97b  sub     rsp, 30h
0x1800ac97f  mov     rsi, rdx
0x1800ac982  mov     rdi, rcx
0x1800ac985  xor     ebx, ebx
0x1800ac987  call    ?TraceEnabled@@YAEXZ; TraceEnabled(void)
0x1800ac98c  test    al, al
0x1800ac98e  jz      loc_1800ACA8E
0x1800ac994  mov     rdx, rsi; unsigned __int16 *
0x1800ac997  mov     rcx, rdi; this
0x1800ac99a  call    ?DecodeRqu@TPMW8_COMMAND@tpm12class@@UEAAJPEAG@Z; tpm12class::TPMW8_COMMAND::DecodeRqu(ushort *)
0x1800ac99f  mov     ebx, eax
0x1800ac9a1  test    eax, eax
0x1800ac9a3  js      loc_1800ACA8E
0x1800ac9a9  lea     rcx, aTpm2NvReadHand; "--TPM2_NV_Read: Handles----------------"...
0x1800ac9b0  call    ?TraceDirect@@YAJPEAG@Z; TraceDirect(ushort *)
0x1800ac9b5  mov     ebx, eax
0x1800ac9b7  test    eax, eax
0x1800ac9b9  js      loc_1800ACA8E
0x1800ac9bf  mov     r9d, [rdi+0C0h]; unsigned int
0x1800ac9c6  lea     rax, [rdi+0C8h]
0x1800ac9cd  lea     r8, aAuthhandle; "authHandle"
0x1800ac9d4  mov     [rsp+38h+var_18], rax; struct tpm12class::TPMW82B_BUFFER *
0x1800ac9d9  mov     rdx, rsi; unsigned __int16 *
0x1800ac9dc  call    ?DecodeHandle@TPMW8_COMMAND@tpm12class@@QEAAJPEAG0IPEAVTPMW82B_BUFFER@2@@Z; tpm12class::TPMW8_COMMAND::DecodeHandle(ushort *,ushort *,uint,tpm12class::TPMW82B_BUFFER *)
0x1800ac9e1  mov     ebx, eax
0x1800ac9e3  test    eax, eax
0x1800ac9e5  js      loc_1800ACA8E
0x1800ac9eb  mov     r9d, [rdi+110h]; unsigned int
0x1800ac9f2  lea     rax, [rdi+118h]
0x1800ac9f9  lea     r8, aNvindex; "nvIndex"
0x1800aca00  mov     [rsp+38h+var_18], rax; struct tpm12class::TPMW82B_BUFFER *
0x1800aca05  mov     rdx, rsi; unsigned __int16 *
0x1800aca08  call    ?DecodeHandle@TPMW8_COMMAND@tpm12class@@QEAAJPEAG0IPEAVTPMW82B_BUFFER@2@@Z; tpm12class::TPMW8_COMMAND::DecodeHandle(ushort *,ushort *,uint,tpm12class::TPMW82B_BUFFER *)
0x1800aca0d  mov     ebx, eax
0x1800aca0f  test    eax, eax
0x1800aca11  js      short loc_1800ACA8E
0x1800aca13  mov     rdx, rsi; unsigned __int16 *
0x1800aca16  mov     rcx, rdi; this
0x1800aca19  call    ?DecodeAuthorizationsRqu@TPMW8_COMMAND@tpm12class@@UEAAJPEAG@Z; tpm12class::TPMW8_COMMAND::DecodeAuthorizationsRqu(ushort *)
0x1800aca1e  mov     ebx, eax
0x1800aca20  test    eax, eax
0x1800aca22  js      short loc_1800ACA8E
0x1800aca24  lea     rcx, aTpm2NvReadPara; "--TPM2_NV_Read: Parameters-------------"...
0x1800aca2b  call    ?TraceDirect@@YAJPEAG@Z; TraceDirect(ushort *)
0x1800aca30  mov     ebx, eax
0x1800aca32  test    eax, eax
0x1800aca34  js      short loc_1800ACA8E
0x1800aca36  movzx   r8d, word ptr [rdi+160h]; unsigned __int16
0x1800aca3e  lea     rdx, aSize; "size"
0x1800aca45  mov     [rsp+38h+var_10], 0; char
0x1800aca4a  mov     r9b, 1; unsigned __int8
0x1800aca4d  mov     rcx, rsi; unsigned __int16 *
0x1800aca50  mov     [rsp+38h+var_18], 0; struct TPM_SYMBOLTABLE_ENTRY *
0x1800aca59  call    ?TraceUINT16Value@@YAJPEAG0GEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT16Value(ushort *,ushort *,ushort,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800aca5e  mov     ebx, eax
0x1800aca60  test    eax, eax
0x1800aca62  js      short loc_1800ACA8E
0x1800aca64  movzx   r8d, word ptr [rdi+162h]; unsigned __int16
0x1800aca6c  lea     rdx, aOffset; "offset"
0x1800aca73  mov     [rsp+38h+var_10], 0; char
0x1800aca78  mov     r9b, 1; unsigned __int8
0x1800aca7b  mov     rcx, rsi; unsigned __int16 *
0x1800aca7e  mov     [rsp+38h+var_18], 0; struct TPM_SYMBOLTABLE_ENTRY *
0x1800aca87  call    ?TraceUINT16Value@@YAJPEAG0GEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT16Value(ushort *,ushort *,ushort,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800aca8c  mov     ebx, eax
0x1800aca8e  mov     rsi, [rsp+38h+arg_8]
0x1800aca93  mov     eax, ebx
0x1800aca95  mov     rbx, [rsp+38h+arg_0]
0x1800aca9a  add     rsp, 30h
0x1800aca9e  pop     rdi
0x1800aca9f  retn
```
