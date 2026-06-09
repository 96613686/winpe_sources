# tpm12class::TPMW8_CreatePrimary::DecodeRqu(ushort *)

- ea: `0x1800b2b20`
- end: `0x1800b2e26`
- name: `?DecodeRqu@TPMW8_CreatePrimary@tpm12class@@UEAAJPEAG@Z`
- size: `774`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_CreatePrimary *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18002a750`
- `0x18003cce0`
- `0x18004c1e8`
- `0x1800764d0`
- `0x18007704c`
- `0x1800a5470`
- `0x1800a57f4`
- `0x1800a58c0`
- `0x1800b2b20`
- `0x1800bacf4`
- `0x1800bada0`
- `0x1800bb4d4`
- `0x1800c8010`

## string_xrefs

- `0x1800b2d7a`: `outsideInfo.`
- `0x1800b2c3c`: `TPM2B_SENSITIVE_CREATE`
- `0x1800b2b91`: `--TPM2_CreatePrimary: Handles----------------------------------------\n`
- `0x1800b2be8`: `--TPM2_CreatePrimary: Parameters-------------------------------------\n`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_CreatePrimary::DecodeRqu(
        tpm12class::TPMW8_CreatePrimary *this,
        unsigned __int16 *a2)
{
  int v4; // ebx
  tpm12class::TPMW8_COMMAND *v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  unsigned __int16 v9; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v10[510]; // [rsp+32h] [rbp-CEh] BYREF

  v9 = 0;
  v4 = 0;
  memset_0(v10, 0, sizeof(v10));
  if ( TraceEnabled() )
  {
    v4 = tpm12class::TPMW8_COMMAND::DecodeRqu(this, a2);
    if ( v4 >= 0 )
    {
      v4 = TraceDirect(L"--TPM2_CreatePrimary: Handles----------------------------------------\r\n");
      if ( v4 >= 0 )
      {
        v4 = tpm12class::TPMW8_COMMAND::DecodeHandle(
               v5,
               a2,
               L"primaryHandle",
               *((_DWORD *)this + 50),
               (tpm12class::TPMW8_CreatePrimary *)((char *)this + 208));
        if ( v4 >= 0 )
        {
          v4 = tpm12class::TPMW8_COMMAND::DecodeAuthorizationsRqu(this, a2);
          if ( v4 >= 0 )
          {
            v4 = TraceDirect(L"--TPM2_CreatePrimary: Parameters-------------------------------------\r\n");
            if ( v4 >= 0 )
            {
              v4 = StringCchCopyW(&v9, 0x100u, a2);
              if ( v4 >= 0 )
              {
                v4 = StringCchCatW(&v9, 0x100u, L"sensitive.");
                if ( v4 >= 0 )
                {
                  v4 = TraceIdentifier(&v9, L"TPM2B_SENSITIVE_CREATE");
                  if ( v4 >= 0 )
                  {
                    v4 = TraceUINT16Value(&v9, L"size", *((_WORD *)this + 96), 1u, 0, 0);
                    if ( v4 >= 0 )
                    {
                      v6 = *((_QWORD *)this + 35);
                      if ( !v6
                        || (v4 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v6 + 40LL))(
                                   v6,
                                   &v9),
                            v4 >= 0) )
                      {
                        v4 = StringCchCopyW(&v9, 0x100u, a2);
                        if ( v4 >= 0 )
                        {
                          v4 = StringCchCatW(&v9, 0x100u, L"inPublic.");
                          if ( v4 >= 0 )
                          {
                            v4 = TraceIdentifier(&v9, L"TPM2B_PUBLIC");
                            if ( v4 >= 0 )
                            {
                              v4 = TraceUINT16Value(&v9, L"size", *((_WORD *)this + 97), 1u, 0, 0);
                              if ( v4 >= 0 )
                              {
                                v7 = *((_QWORD *)this + 36);
                                if ( !v7
                                  || (v4 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v7 + 40LL))(
                                             v7,
                                             &v9),
                                      v4 >= 0) )
                                {
                                  v4 = StringCchCopyW(&v9, 0x100u, a2);
                                  if ( v4 >= 0 )
                                  {
                                    v4 = StringCchCatW(&v9, 0x100u, L"outsideInfo.");
                                    if ( v4 >= 0 )
                                    {
                                      v4 = (*(__int64 (__fastcall **)(char *, unsigned __int16 *))(*((_QWORD *)this + 37)
                                                                                                 + 40LL))(
                                             (char *)this + 296,
                                             &v9);
                                      if ( v4 >= 0 )
                                      {
                                        v4 = StringCchCopyW(&v9, 0x100u, a2);
                                        if ( v4 >= 0 )
                                        {
                                          v4 = StringCchCatW(&v9, 0x100u, L"creationPcr.");
                                          if ( v4 >= 0 )
                                            return (unsigned int)(*(__int64 (__fastcall **)(char *, unsigned __int16 *))(*((_QWORD *)this + 46) + 40LL))(
                                                                   (char *)this + 368,
                                                                   &v9);
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
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
0x1800b2b20  mov     [rsp-8+arg_10], rbx
0x1800b2b25  mov     [rsp-8+arg_18], rsi
0x1800b2b2a  push    rbp
0x1800b2b2b  push    rdi
0x1800b2b2c  push    r15
0x1800b2b2e  lea     rbp, [rsp-140h]
0x1800b2b36  sub     rsp, 240h
0x1800b2b3d  mov     rax, cs:__security_cookie
0x1800b2b44  xor     rax, rsp
0x1800b2b47  mov     [rbp+150h+var_20], rax
0x1800b2b4e  mov     rsi, rdx
0x1800b2b51  mov     rdi, rcx
0x1800b2b54  xor     eax, eax
0x1800b2b56  lea     rcx, [rsp+250h+var_21E]; void *
0x1800b2b5b  xor     edx, edx; Val
0x1800b2b5d  mov     [rsp+250h+var_220], ax
0x1800b2b62  mov     r8d, 1FEh; Size
0x1800b2b68  xor     ebx, ebx
0x1800b2b6a  call    memset_0
0x1800b2b6f  call    ?TraceEnabled@@YAEXZ; TraceEnabled(void)
0x1800b2b74  test    al, al
0x1800b2b76  jz      loc_1800B2DFC
0x1800b2b7c  mov     rdx, rsi; unsigned __int16 *
0x1800b2b7f  mov     rcx, rdi; this
0x1800b2b82  call    ?DecodeRqu@TPMW8_COMMAND@tpm12class@@UEAAJPEAG@Z; tpm12class::TPMW8_COMMAND::DecodeRqu(ushort *)
0x1800b2b87  mov     ebx, eax
0x1800b2b89  test    eax, eax
0x1800b2b8b  js      loc_1800B2DFC
0x1800b2b91  lea     rcx, aTpm2Createprim; "--TPM2_CreatePrimary: Handles----------"...
0x1800b2b98  call    ?TraceDirect@@YAJPEAG@Z; TraceDirect(ushort *)
0x1800b2b9d  mov     ebx, eax
0x1800b2b9f  test    eax, eax
0x1800b2ba1  js      loc_1800B2DFC
0x1800b2ba7  mov     r9d, [rdi+0C8h]; unsigned int
0x1800b2bae  lea     rax, [rdi+0D0h]
0x1800b2bb5  lea     r8, aPrimaryhandle; "primaryHandle"
0x1800b2bbc  mov     [rsp+250h+var_230], rax; struct tpm12class::TPMW82B_BUFFER *
0x1800b2bc1  mov     rdx, rsi; unsigned __int16 *
0x1800b2bc4  call    ?DecodeHandle@TPMW8_COMMAND@tpm12class@@QEAAJPEAG0IPEAVTPMW82B_BUFFER@2@@Z; tpm12class::TPMW8_COMMAND::DecodeHandle(ushort *,ushort *,uint,tpm12class::TPMW82B_BUFFER *)
0x1800b2bc9  mov     ebx, eax
0x1800b2bcb  test    eax, eax
0x1800b2bcd  js      loc_1800B2DFC
0x1800b2bd3  mov     rdx, rsi; unsigned __int16 *
0x1800b2bd6  mov     rcx, rdi; this
0x1800b2bd9  call    ?DecodeAuthorizationsRqu@TPMW8_COMMAND@tpm12class@@UEAAJPEAG@Z; tpm12class::TPMW8_COMMAND::DecodeAuthorizationsRqu(ushort *)
0x1800b2bde  mov     ebx, eax
0x1800b2be0  test    eax, eax
0x1800b2be2  js      loc_1800B2DFC
0x1800b2be8  lea     rcx, aTpm2Createprim_0; "--TPM2_CreatePrimary: Parameters-------"...
0x1800b2bef  call    ?TraceDirect@@YAJPEAG@Z; TraceDirect(ushort *)
0x1800b2bf4  mov     ebx, eax
0x1800b2bf6  test    eax, eax
0x1800b2bf8  js      loc_1800B2DFC
0x1800b2bfe  mov     r15d, 100h
0x1800b2c04  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800b2c09  mov     edx, r15d; unsigned __int64
0x1800b2c0c  mov     r8, rsi; unsigned __int16 *
0x1800b2c0f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b2c14  mov     ebx, eax
0x1800b2c16  test    eax, eax
0x1800b2c18  js      loc_1800B2DFC
0x1800b2c1e  lea     r8, aSensitive; "sensitive."
0x1800b2c25  mov     edx, r15d; unsigned __int64
0x1800b2c28  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800b2c2d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800b2c32  mov     ebx, eax
0x1800b2c34  test    eax, eax
0x1800b2c36  js      loc_1800B2DFC
0x1800b2c3c  lea     rdx, aTpm2bSensitive_0; "TPM2B_SENSITIVE_CREATE"
0x1800b2c43  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800b2c48  call    ?TraceIdentifier@@YAJPEAG0@Z; TraceIdentifier(ushort *,ushort *)
0x1800b2c4d  mov     ebx, eax
0x1800b2c4f  test    eax, eax
0x1800b2c51  js      loc_1800B2DFC
0x1800b2c57  movzx   r8d, word ptr [rdi+0C0h]; unsigned __int16
0x1800b2c5f  lea     rdx, aSize; "size"
0x1800b2c66  mov     [rsp+250h+var_228], 0; char
0x1800b2c6b  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800b2c70  mov     r9b, 1; unsigned __int8
0x1800b2c73  mov     [rsp+250h+var_230], 0; struct TPM_SYMBOLTABLE_ENTRY *
0x1800b2c7c  call    ?TraceUINT16Value@@YAJPEAG0GEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT16Value(ushort *,ushort *,ushort,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800b2c81  mov     ebx, eax
0x1800b2c83  test    eax, eax
0x1800b2c85  js      loc_1800B2DFC
0x1800b2c8b  mov     rcx, [rdi+118h]
0x1800b2c92  test    rcx, rcx
0x1800b2c95  jz      short loc_1800B2CB2
0x1800b2c97  mov     rax, [rcx]
0x1800b2c9a  lea     rdx, [rsp+250h+var_220]
0x1800b2c9f  mov     rax, [rax+28h]
0x1800b2ca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2ca8  mov     ebx, eax
0x1800b2caa  test    eax, eax
0x1800b2cac  js      loc_1800B2DFC
0x1800b2cb2  mov     r8, rsi; unsigned __int16 *
0x1800b2cb5  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800b2cba  mov     rdx, r15; unsigned __int64
0x1800b2cbd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b2cc2  mov     ebx, eax
0x1800b2cc4  test    eax, eax
0x1800b2cc6  js      loc_1800B2DFC
0x1800b2ccc  lea     r8, aInpublic; "inPublic."
0x1800b2cd3  mov     rdx, r15; unsigned __int64
0x1800b2cd6  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800b2cdb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800b2ce0  mov     ebx, eax
0x1800b2ce2  test    eax, eax
0x1800b2ce4  js      loc_1800B2DFC
0x1800b2cea  lea     rdx, aTpm2bPublic; "TPM2B_PUBLIC"
0x1800b2cf1  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800b2cf6  call    ?TraceIdentifier@@YAJPEAG0@Z; TraceIdentifier(ushort *,ushort *)
0x1800b2cfb  mov     ebx, eax
0x1800b2cfd  test    eax, eax
0x1800b2cff  js      loc_1800B2DFC
0x1800b2d05  movzx   r8d, word ptr [rdi+0C2h]; unsigned __int16
0x1800b2d0d  lea     rdx, aSize; "size"
0x1800b2d14  mov     [rsp+250h+var_228], 0; char
0x1800b2d19  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800b2d1e  mov     r9b, 1; unsigned __int8
0x1800b2d21  mov     [rsp+250h+var_230], 0; struct TPM_SYMBOLTABLE_ENTRY *
0x1800b2d2a  call    ?TraceUINT16Value@@YAJPEAG0GEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT16Value(ushort *,ushort *,ushort,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800b2d2f  mov     ebx, eax
0x1800b2d31  test    eax, eax
0x1800b2d33  js      loc_1800B2DFC
0x1800b2d39  mov     rcx, [rdi+120h]
0x1800b2d40  test    rcx, rcx
0x1800b2d43  jz      short loc_1800B2D60
0x1800b2d45  mov     rax, [rcx]
0x1800b2d48  lea     rdx, [rsp+250h+var_220]
0x1800b2d4d  mov     rax, [rax+28h]
0x1800b2d51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2d56  mov     ebx, eax
0x1800b2d58  test    eax, eax
0x1800b2d5a  js      loc_1800B2DFC
0x1800b2d60  mov     r8, rsi; unsigned __int16 *
0x1800b2d63  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800b2d68  mov     rdx, r15; unsigned __int64
0x1800b2d6b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b2d70  mov     ebx, eax
0x1800b2d72  test    eax, eax
0x1800b2d74  js      loc_1800B2DFC
0x1800b2d7a  lea     r8, aOutsideinfo; "outsideInfo."
0x1800b2d81  mov     rdx, r15; unsigned __int64
0x1800b2d84  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800b2d89  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800b2d8e  mov     ebx, eax
0x1800b2d90  test    eax, eax
0x1800b2d92  js      short loc_1800B2DFC
0x1800b2d94  lea     rcx, [rdi+128h]
0x1800b2d9b  mov     rax, [rcx]
0x1800b2d9e  lea     rdx, [rsp+250h+var_220]
0x1800b2da3  mov     rax, [rax+28h]
0x1800b2da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2dac  mov     ebx, eax
0x1800b2dae  test    eax, eax
0x1800b2db0  js      short loc_1800B2DFC
0x1800b2db2  mov     r8, rsi; unsigned __int16 *
0x1800b2db5  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800b2dba  mov     rdx, r15; unsigned __int64
0x1800b2dbd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b2dc2  mov     ebx, eax
0x1800b2dc4  test    eax, eax
0x1800b2dc6  js      short loc_1800B2DFC
0x1800b2dc8  lea     r8, aCreationpcr; "creationPcr."
0x1800b2dcf  mov     rdx, r15; unsigned __int64
0x1800b2dd2  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800b2dd7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800b2ddc  mov     ebx, eax
0x1800b2dde  test    eax, eax
0x1800b2de0  js      short loc_1800B2DFC
0x1800b2de2  lea     rcx, [rdi+170h]
0x1800b2de9  mov     rax, [rcx]
0x1800b2dec  lea     rdx, [rsp+250h+var_220]
0x1800b2df1  mov     rax, [rax+28h]
0x1800b2df5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2dfa  mov     ebx, eax
0x1800b2dfc  mov     eax, ebx
0x1800b2dfe  mov     rcx, [rbp+150h+var_20]
0x1800b2e05  xor     rcx, rsp; StackCookie
0x1800b2e08  call    __security_check_cookie
0x1800b2e0d  lea     r11, [rsp+250h+var_10]
0x1800b2e15  mov     rbx, [r11+30h]
0x1800b2e19  mov     rsi, [r11+38h]
0x1800b2e1d  mov     rsp, r11
0x1800b2e20  pop     r15
0x1800b2e22  pop     rdi
0x1800b2e23  pop     rbp
0x1800b2e24  retn
```
