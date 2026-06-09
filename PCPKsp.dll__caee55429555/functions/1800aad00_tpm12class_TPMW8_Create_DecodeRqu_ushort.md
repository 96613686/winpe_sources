# tpm12class::TPMW8_Create::DecodeRqu(ushort *)

- ea: `0x1800aad00`
- end: `0x1800ab006`
- name: `?DecodeRqu@TPMW8_Create@tpm12class@@UEAAJPEAG@Z`
- size: `774`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_Create *__hidden this, unsigned __int16 *)`
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
- `0x1800aad00`
- `0x1800bacf4`
- `0x1800bada0`
- `0x1800bb4d4`
- `0x1800c8010`

## string_xrefs

- `0x1800aaf5a`: `outsideInfo.`
- `0x1800aad71`: `--TPM2_Create: Handles-----------------------------------------------\n`
- `0x1800aadc8`: `--TPM2_Create: Parameters--------------------------------------------\n`
- `0x1800aae1c`: `TPM2B_SENSITIVE_CREATE`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_Create::DecodeRqu(tpm12class::TPMW8_Create *this, unsigned __int16 *a2)
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
      v4 = TraceDirect(L"--TPM2_Create: Handles-----------------------------------------------\r\n");
      if ( v4 >= 0 )
      {
        v4 = tpm12class::TPMW8_COMMAND::DecodeHandle(
               v5,
               a2,
               L"parentHandle",
               *((_DWORD *)this + 50),
               (tpm12class::TPMW8_Create *)((char *)this + 208));
        if ( v4 >= 0 )
        {
          v4 = tpm12class::TPMW8_COMMAND::DecodeAuthorizationsRqu(this, a2);
          if ( v4 >= 0 )
          {
            v4 = TraceDirect(L"--TPM2_Create: Parameters--------------------------------------------\r\n");
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
0x1800aad00  mov     [rsp-8+arg_10], rbx
0x1800aad05  mov     [rsp-8+arg_18], rsi
0x1800aad0a  push    rbp
0x1800aad0b  push    rdi
0x1800aad0c  push    r15
0x1800aad0e  lea     rbp, [rsp-140h]
0x1800aad16  sub     rsp, 240h
0x1800aad1d  mov     rax, cs:__security_cookie
0x1800aad24  xor     rax, rsp
0x1800aad27  mov     [rbp+150h+var_20], rax
0x1800aad2e  mov     rsi, rdx
0x1800aad31  mov     rdi, rcx
0x1800aad34  xor     eax, eax
0x1800aad36  lea     rcx, [rsp+250h+var_21E]; void *
0x1800aad3b  xor     edx, edx; Val
0x1800aad3d  mov     [rsp+250h+var_220], ax
0x1800aad42  mov     r8d, 1FEh; Size
0x1800aad48  xor     ebx, ebx
0x1800aad4a  call    memset_0
0x1800aad4f  call    ?TraceEnabled@@YAEXZ; TraceEnabled(void)
0x1800aad54  test    al, al
0x1800aad56  jz      loc_1800AAFDC
0x1800aad5c  mov     rdx, rsi; unsigned __int16 *
0x1800aad5f  mov     rcx, rdi; this
0x1800aad62  call    ?DecodeRqu@TPMW8_COMMAND@tpm12class@@UEAAJPEAG@Z; tpm12class::TPMW8_COMMAND::DecodeRqu(ushort *)
0x1800aad67  mov     ebx, eax
0x1800aad69  test    eax, eax
0x1800aad6b  js      loc_1800AAFDC
0x1800aad71  lea     rcx, aTpm2CreateHand; "--TPM2_Create: Handles-----------------"...
0x1800aad78  call    ?TraceDirect@@YAJPEAG@Z; TraceDirect(ushort *)
0x1800aad7d  mov     ebx, eax
0x1800aad7f  test    eax, eax
0x1800aad81  js      loc_1800AAFDC
0x1800aad87  mov     r9d, [rdi+0C8h]; unsigned int
0x1800aad8e  lea     rax, [rdi+0D0h]
0x1800aad95  lea     r8, aParenthandle; "parentHandle"
0x1800aad9c  mov     [rsp+250h+var_230], rax; struct tpm12class::TPMW82B_BUFFER *
0x1800aada1  mov     rdx, rsi; unsigned __int16 *
0x1800aada4  call    ?DecodeHandle@TPMW8_COMMAND@tpm12class@@QEAAJPEAG0IPEAVTPMW82B_BUFFER@2@@Z; tpm12class::TPMW8_COMMAND::DecodeHandle(ushort *,ushort *,uint,tpm12class::TPMW82B_BUFFER *)
0x1800aada9  mov     ebx, eax
0x1800aadab  test    eax, eax
0x1800aadad  js      loc_1800AAFDC
0x1800aadb3  mov     rdx, rsi; unsigned __int16 *
0x1800aadb6  mov     rcx, rdi; this
0x1800aadb9  call    ?DecodeAuthorizationsRqu@TPMW8_COMMAND@tpm12class@@UEAAJPEAG@Z; tpm12class::TPMW8_COMMAND::DecodeAuthorizationsRqu(ushort *)
0x1800aadbe  mov     ebx, eax
0x1800aadc0  test    eax, eax
0x1800aadc2  js      loc_1800AAFDC
0x1800aadc8  lea     rcx, aTpm2CreatePara; "--TPM2_Create: Parameters--------------"...
0x1800aadcf  call    ?TraceDirect@@YAJPEAG@Z; TraceDirect(ushort *)
0x1800aadd4  mov     ebx, eax
0x1800aadd6  test    eax, eax
0x1800aadd8  js      loc_1800AAFDC
0x1800aadde  mov     r15d, 100h
0x1800aade4  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800aade9  mov     edx, r15d; unsigned __int64
0x1800aadec  mov     r8, rsi; unsigned __int16 *
0x1800aadef  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800aadf4  mov     ebx, eax
0x1800aadf6  test    eax, eax
0x1800aadf8  js      loc_1800AAFDC
0x1800aadfe  lea     r8, aSensitive; "sensitive."
0x1800aae05  mov     edx, r15d; unsigned __int64
0x1800aae08  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800aae0d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800aae12  mov     ebx, eax
0x1800aae14  test    eax, eax
0x1800aae16  js      loc_1800AAFDC
0x1800aae1c  lea     rdx, aTpm2bSensitive_0; "TPM2B_SENSITIVE_CREATE"
0x1800aae23  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800aae28  call    ?TraceIdentifier@@YAJPEAG0@Z; TraceIdentifier(ushort *,ushort *)
0x1800aae2d  mov     ebx, eax
0x1800aae2f  test    eax, eax
0x1800aae31  js      loc_1800AAFDC
0x1800aae37  movzx   r8d, word ptr [rdi+0C0h]; unsigned __int16
0x1800aae3f  lea     rdx, aSize; "size"
0x1800aae46  mov     [rsp+250h+var_228], 0; char
0x1800aae4b  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800aae50  mov     r9b, 1; unsigned __int8
0x1800aae53  mov     [rsp+250h+var_230], 0; struct TPM_SYMBOLTABLE_ENTRY *
0x1800aae5c  call    ?TraceUINT16Value@@YAJPEAG0GEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT16Value(ushort *,ushort *,ushort,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800aae61  mov     ebx, eax
0x1800aae63  test    eax, eax
0x1800aae65  js      loc_1800AAFDC
0x1800aae6b  mov     rcx, [rdi+118h]
0x1800aae72  test    rcx, rcx
0x1800aae75  jz      short loc_1800AAE92
0x1800aae77  mov     rax, [rcx]
0x1800aae7a  lea     rdx, [rsp+250h+var_220]
0x1800aae7f  mov     rax, [rax+28h]
0x1800aae83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aae88  mov     ebx, eax
0x1800aae8a  test    eax, eax
0x1800aae8c  js      loc_1800AAFDC
0x1800aae92  mov     r8, rsi; unsigned __int16 *
0x1800aae95  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800aae9a  mov     rdx, r15; unsigned __int64
0x1800aae9d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800aaea2  mov     ebx, eax
0x1800aaea4  test    eax, eax
0x1800aaea6  js      loc_1800AAFDC
0x1800aaeac  lea     r8, aInpublic; "inPublic."
0x1800aaeb3  mov     rdx, r15; unsigned __int64
0x1800aaeb6  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800aaebb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800aaec0  mov     ebx, eax
0x1800aaec2  test    eax, eax
0x1800aaec4  js      loc_1800AAFDC
0x1800aaeca  lea     rdx, aTpm2bPublic; "TPM2B_PUBLIC"
0x1800aaed1  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800aaed6  call    ?TraceIdentifier@@YAJPEAG0@Z; TraceIdentifier(ushort *,ushort *)
0x1800aaedb  mov     ebx, eax
0x1800aaedd  test    eax, eax
0x1800aaedf  js      loc_1800AAFDC
0x1800aaee5  movzx   r8d, word ptr [rdi+0C2h]; unsigned __int16
0x1800aaeed  lea     rdx, aSize; "size"
0x1800aaef4  mov     [rsp+250h+var_228], 0; char
0x1800aaef9  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800aaefe  mov     r9b, 1; unsigned __int8
0x1800aaf01  mov     [rsp+250h+var_230], 0; struct TPM_SYMBOLTABLE_ENTRY *
0x1800aaf0a  call    ?TraceUINT16Value@@YAJPEAG0GEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT16Value(ushort *,ushort *,ushort,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800aaf0f  mov     ebx, eax
0x1800aaf11  test    eax, eax
0x1800aaf13  js      loc_1800AAFDC
0x1800aaf19  mov     rcx, [rdi+120h]
0x1800aaf20  test    rcx, rcx
0x1800aaf23  jz      short loc_1800AAF40
0x1800aaf25  mov     rax, [rcx]
0x1800aaf28  lea     rdx, [rsp+250h+var_220]
0x1800aaf2d  mov     rax, [rax+28h]
0x1800aaf31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aaf36  mov     ebx, eax
0x1800aaf38  test    eax, eax
0x1800aaf3a  js      loc_1800AAFDC
0x1800aaf40  mov     r8, rsi; unsigned __int16 *
0x1800aaf43  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800aaf48  mov     rdx, r15; unsigned __int64
0x1800aaf4b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800aaf50  mov     ebx, eax
0x1800aaf52  test    eax, eax
0x1800aaf54  js      loc_1800AAFDC
0x1800aaf5a  lea     r8, aOutsideinfo; "outsideInfo."
0x1800aaf61  mov     rdx, r15; unsigned __int64
0x1800aaf64  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800aaf69  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800aaf6e  mov     ebx, eax
0x1800aaf70  test    eax, eax
0x1800aaf72  js      short loc_1800AAFDC
0x1800aaf74  lea     rcx, [rdi+128h]
0x1800aaf7b  mov     rax, [rcx]
0x1800aaf7e  lea     rdx, [rsp+250h+var_220]
0x1800aaf83  mov     rax, [rax+28h]
0x1800aaf87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aaf8c  mov     ebx, eax
0x1800aaf8e  test    eax, eax
0x1800aaf90  js      short loc_1800AAFDC
0x1800aaf92  mov     r8, rsi; unsigned __int16 *
0x1800aaf95  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800aaf9a  mov     rdx, r15; unsigned __int64
0x1800aaf9d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800aafa2  mov     ebx, eax
0x1800aafa4  test    eax, eax
0x1800aafa6  js      short loc_1800AAFDC
0x1800aafa8  lea     r8, aCreationpcr; "creationPcr."
0x1800aafaf  mov     rdx, r15; unsigned __int64
0x1800aafb2  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800aafb7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800aafbc  mov     ebx, eax
0x1800aafbe  test    eax, eax
0x1800aafc0  js      short loc_1800AAFDC
0x1800aafc2  lea     rcx, [rdi+170h]
0x1800aafc9  mov     rax, [rcx]
0x1800aafcc  lea     rdx, [rsp+250h+var_220]
0x1800aafd1  mov     rax, [rax+28h]
0x1800aafd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aafda  mov     ebx, eax
0x1800aafdc  mov     eax, ebx
0x1800aafde  mov     rcx, [rbp+150h+var_20]
0x1800aafe5  xor     rcx, rsp; StackCookie
0x1800aafe8  call    __security_check_cookie
0x1800aafed  lea     r11, [rsp+250h+var_10]
0x1800aaff5  mov     rbx, [r11+30h]
0x1800aaff9  mov     rsi, [r11+38h]
0x1800aaffd  mov     rsp, r11
0x1800ab000  pop     r15
0x1800ab002  pop     rdi
0x1800ab003  pop     rbp
0x1800ab004  retn
```
