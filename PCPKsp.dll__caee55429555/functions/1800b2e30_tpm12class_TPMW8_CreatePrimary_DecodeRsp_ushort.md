# tpm12class::TPMW8_CreatePrimary::DecodeRsp(ushort *)

- ea: `0x1800b2e30`
- end: `0x1800b31a9`
- name: `?DecodeRsp@TPMW8_CreatePrimary@tpm12class@@UEAAJPEAG@Z`
- size: `889`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_CreatePrimary *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18002a750`
- `0x18003cce0`
- `0x18004c1e8`
- `0x1800764d0`
- `0x18007704c`
- `0x1800a5650`
- `0x1800a5860`
- `0x1800a5b20`
- `0x1800b2e30`
- `0x1800bacf4`
- `0x1800bada0`
- `0x1800bb4d4`
- `0x1800bb7d0`
- `0x1800c8010`

## string_xrefs

- `0x1800b2ea1`: `--TPM2_CreatePrimary: Handles----------------------------------------\n`
- `0x1800b2eeb`: `--TPM2_CreatePrimary: Parameters-------------------------------------\n`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_CreatePrimary::DecodeRsp(
        tpm12class::TPMW8_CreatePrimary *this,
        unsigned __int16 *a2)
{
  int v4; // ebx
  __int64 v5; // rcx
  __int64 v6; // rcx
  unsigned __int16 v8; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v9[510]; // [rsp+32h] [rbp-CEh] BYREF

  v8 = 0;
  v4 = 0;
  memset_0(v9, 0, sizeof(v9));
  if ( TraceEnabled() )
  {
    v4 = tpm12class::TPMW8_COMMAND::DecodeRsp(this, a2);
    if ( v4 >= 0 )
    {
      v4 = TraceDirect(L"--TPM2_CreatePrimary: Handles----------------------------------------\r\n");
      if ( v4 >= 0 )
      {
        v4 = TraceUINT32Value(
               a2,
               L"objectHandle",
               *((_DWORD *)this + 110),
               0,
               (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8_RH,
               1u);
        if ( v4 >= 0 )
        {
          v4 = TraceDirect(L"--TPM2_CreatePrimary: Parameters-------------------------------------\r\n");
          if ( v4 >= 0 )
          {
            v4 = tpm12class::TPMW8_COMMAND::DecodeParameterSizeRsp(this, a2);
            if ( v4 >= 0 )
            {
              v4 = StringCchCopyW(&v8, 0x100u, a2);
              if ( v4 >= 0 )
              {
                v4 = StringCchCatW(&v8, 0x100u, L"outPublic.");
                if ( v4 >= 0 )
                {
                  v4 = TraceIdentifier(&v8, L"TPM2B_PUBLIC");
                  if ( v4 >= 0 )
                  {
                    v4 = TraceUINT16Value(&v8, L"size", *((_WORD *)this + 98), 1u, 0, 0);
                    if ( v4 >= 0 )
                    {
                      v5 = *((_QWORD *)this + 56);
                      if ( !v5
                        || (v4 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v5 + 40LL))(
                                   v5,
                                   &v8),
                            v4 >= 0) )
                      {
                        v4 = StringCchCopyW(&v8, 0x100u, a2);
                        if ( v4 >= 0 )
                        {
                          v4 = StringCchCatW(&v8, 0x100u, L"creationData.");
                          if ( v4 >= 0 )
                          {
                            v4 = TraceIdentifier(&v8, L"TPM2B_CREATION_DATA");
                            if ( v4 >= 0 )
                            {
                              v4 = TraceUINT16Value(&v8, L"size", *((_WORD *)this + 99), 1u, 0, 0);
                              if ( v4 >= 0 )
                              {
                                v6 = *((_QWORD *)this + 57);
                                if ( !v6
                                  || (v4 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v6 + 40LL))(
                                             v6,
                                             &v8),
                                      v4 >= 0) )
                                {
                                  v4 = StringCchCopyW(&v8, 0x100u, a2);
                                  if ( v4 >= 0 )
                                  {
                                    v4 = StringCchCatW(&v8, 0x100u, L"creationHash.");
                                    if ( v4 >= 0 )
                                    {
                                      v4 = (*(__int64 (__fastcall **)(char *, unsigned __int16 *))(*((_QWORD *)this + 58)
                                                                                                 + 40LL))(
                                             (char *)this + 464,
                                             &v8);
                                      if ( v4 >= 0 )
                                      {
                                        v4 = StringCchCopyW(&v8, 0x100u, a2);
                                        if ( v4 >= 0 )
                                        {
                                          v4 = StringCchCatW(&v8, 0x100u, L"creationTicket.");
                                          if ( v4 >= 0 )
                                          {
                                            v4 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(**((_QWORD **)this + 67) + 40LL))(
                                                   *((_QWORD *)this + 67),
                                                   &v8);
                                            if ( v4 >= 0 )
                                            {
                                              v4 = StringCchCopyW(&v8, 0x100u, a2);
                                              if ( v4 >= 0 )
                                              {
                                                v4 = StringCchCatW(&v8, 0x100u, L"name.");
                                                if ( v4 >= 0 )
                                                {
                                                  v4 = (*(__int64 (__fastcall **)(char *, unsigned __int16 *))(*((_QWORD *)this + 68) + 40LL))(
                                                         (char *)this + 544,
                                                         &v8);
                                                  if ( v4 >= 0 )
                                                    return (unsigned int)tpm12class::TPMW8_COMMAND::DecodeAuthorizationsRsp(
                                                                           this,
                                                                           a2);
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
        }
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800b2e30  mov     [rsp-8+arg_10], rbx
0x1800b2e35  mov     [rsp-8+arg_18], rsi
0x1800b2e3a  push    rbp
0x1800b2e3b  push    rdi
0x1800b2e3c  push    r15
0x1800b2e3e  lea     rbp, [rsp-140h]
0x1800b2e46  sub     rsp, 240h
0x1800b2e4d  mov     rax, cs:__security_cookie
0x1800b2e54  xor     rax, rsp
0x1800b2e57  mov     [rbp+150h+var_20], rax
0x1800b2e5e  mov     rsi, rdx
0x1800b2e61  mov     rdi, rcx
0x1800b2e64  xor     eax, eax
0x1800b2e66  lea     rcx, [rsp+250h+var_21E]; void *
0x1800b2e6b  xor     edx, edx; Val
0x1800b2e6d  mov     [rsp+250h+var_220], ax
0x1800b2e72  mov     r8d, 1FEh; Size
0x1800b2e78  xor     ebx, ebx
0x1800b2e7a  call    memset_0
0x1800b2e7f  call    ?TraceEnabled@@YAEXZ; TraceEnabled(void)
0x1800b2e84  test    al, al
0x1800b2e86  jz      loc_1800B317F
0x1800b2e8c  mov     rdx, rsi; unsigned __int16 *
0x1800b2e8f  mov     rcx, rdi; this
0x1800b2e92  call    ?DecodeRsp@TPMW8_COMMAND@tpm12class@@UEAAJPEAG@Z; tpm12class::TPMW8_COMMAND::DecodeRsp(ushort *)
0x1800b2e97  mov     ebx, eax
0x1800b2e99  test    eax, eax
0x1800b2e9b  js      loc_1800B317F
0x1800b2ea1  lea     rcx, aTpm2Createprim; "--TPM2_CreatePrimary: Handles----------"...
0x1800b2ea8  call    ?TraceDirect@@YAJPEAG@Z; TraceDirect(ushort *)
0x1800b2ead  mov     ebx, eax
0x1800b2eaf  test    eax, eax
0x1800b2eb1  js      loc_1800B317F
0x1800b2eb7  mov     r8d, [rdi+1B8h]; unsigned int
0x1800b2ebe  lea     rax, ?st_TPMW8_RH@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_RH
0x1800b2ec5  mov     [rsp+250h+var_228], 1; unsigned __int8
0x1800b2eca  lea     rdx, aObjecthandle; "objectHandle"
0x1800b2ed1  xor     r9d, r9d; unsigned __int8
0x1800b2ed4  mov     [rsp+250h+var_230], rax; struct TPM_SYMBOLTABLE_ENTRY *
0x1800b2ed9  mov     rcx, rsi; unsigned __int16 *
0x1800b2edc  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800b2ee1  mov     ebx, eax
0x1800b2ee3  test    eax, eax
0x1800b2ee5  js      loc_1800B317F
0x1800b2eeb  lea     rcx, aTpm2Createprim_0; "--TPM2_CreatePrimary: Parameters-------"...
0x1800b2ef2  call    ?TraceDirect@@YAJPEAG@Z; TraceDirect(ushort *)
0x1800b2ef7  mov     ebx, eax
0x1800b2ef9  test    eax, eax
0x1800b2efb  js      loc_1800B317F
0x1800b2f01  mov     rdx, rsi; unsigned __int16 *
0x1800b2f04  mov     rcx, rdi; this
0x1800b2f07  call    ?DecodeParameterSizeRsp@TPMW8_COMMAND@tpm12class@@UEAAJPEAG@Z; tpm12class::TPMW8_COMMAND::DecodeParameterSizeRsp(ushort *)
0x1800b2f0c  mov     ebx, eax
0x1800b2f0e  test    eax, eax
0x1800b2f10  js      loc_1800B317F
0x1800b2f16  mov     r15d, 100h
0x1800b2f1c  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800b2f21  mov     edx, r15d; unsigned __int64
0x1800b2f24  mov     r8, rsi; unsigned __int16 *
0x1800b2f27  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b2f2c  mov     ebx, eax
0x1800b2f2e  test    eax, eax
0x1800b2f30  js      loc_1800B317F
0x1800b2f36  lea     r8, aOutpublic; "outPublic."
0x1800b2f3d  mov     edx, r15d; unsigned __int64
0x1800b2f40  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800b2f45  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800b2f4a  mov     ebx, eax
0x1800b2f4c  test    eax, eax
0x1800b2f4e  js      loc_1800B317F
0x1800b2f54  lea     rdx, aTpm2bPublic; "TPM2B_PUBLIC"
0x1800b2f5b  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800b2f60  call    ?TraceIdentifier@@YAJPEAG0@Z; TraceIdentifier(ushort *,ushort *)
0x1800b2f65  mov     ebx, eax
0x1800b2f67  test    eax, eax
0x1800b2f69  js      loc_1800B317F
0x1800b2f6f  movzx   r8d, word ptr [rdi+0C4h]; unsigned __int16
0x1800b2f77  lea     rdx, aSize; "size"
0x1800b2f7e  mov     [rsp+250h+var_228], 0; char
0x1800b2f83  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800b2f88  mov     r9b, 1; unsigned __int8
0x1800b2f8b  mov     [rsp+250h+var_230], 0; struct TPM_SYMBOLTABLE_ENTRY *
0x1800b2f94  call    ?TraceUINT16Value@@YAJPEAG0GEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT16Value(ushort *,ushort *,ushort,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800b2f99  mov     ebx, eax
0x1800b2f9b  test    eax, eax
0x1800b2f9d  js      loc_1800B317F
0x1800b2fa3  mov     rcx, [rdi+1C0h]
0x1800b2faa  test    rcx, rcx
0x1800b2fad  jz      short loc_1800B2FCA
0x1800b2faf  mov     rax, [rcx]
0x1800b2fb2  lea     rdx, [rsp+250h+var_220]
0x1800b2fb7  mov     rax, [rax+28h]
0x1800b2fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2fc0  mov     ebx, eax
0x1800b2fc2  test    eax, eax
0x1800b2fc4  js      loc_1800B317F
0x1800b2fca  mov     r8, rsi; unsigned __int16 *
0x1800b2fcd  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800b2fd2  mov     rdx, r15; unsigned __int64
0x1800b2fd5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b2fda  mov     ebx, eax
0x1800b2fdc  test    eax, eax
0x1800b2fde  js      loc_1800B317F
0x1800b2fe4  lea     r8, aCreationdata; "creationData."
0x1800b2feb  mov     rdx, r15; unsigned __int64
0x1800b2fee  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800b2ff3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800b2ff8  mov     ebx, eax
0x1800b2ffa  test    eax, eax
0x1800b2ffc  js      loc_1800B317F
0x1800b3002  lea     rdx, aTpm2bCreationD; "TPM2B_CREATION_DATA"
0x1800b3009  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800b300e  call    ?TraceIdentifier@@YAJPEAG0@Z; TraceIdentifier(ushort *,ushort *)
0x1800b3013  mov     ebx, eax
0x1800b3015  test    eax, eax
0x1800b3017  js      loc_1800B317F
0x1800b301d  movzx   r8d, word ptr [rdi+0C6h]; unsigned __int16
0x1800b3025  lea     rdx, aSize; "size"
0x1800b302c  mov     [rsp+250h+var_228], 0; char
0x1800b3031  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800b3036  mov     r9b, 1; unsigned __int8
0x1800b3039  mov     [rsp+250h+var_230], 0; struct TPM_SYMBOLTABLE_ENTRY *
0x1800b3042  call    ?TraceUINT16Value@@YAJPEAG0GEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT16Value(ushort *,ushort *,ushort,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800b3047  mov     ebx, eax
0x1800b3049  test    eax, eax
0x1800b304b  js      loc_1800B317F
0x1800b3051  mov     rcx, [rdi+1C8h]
0x1800b3058  test    rcx, rcx
0x1800b305b  jz      short loc_1800B3078
0x1800b305d  mov     rax, [rcx]
0x1800b3060  lea     rdx, [rsp+250h+var_220]
0x1800b3065  mov     rax, [rax+28h]
0x1800b3069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b306e  mov     ebx, eax
0x1800b3070  test    eax, eax
0x1800b3072  js      loc_1800B317F
0x1800b3078  mov     r8, rsi; unsigned __int16 *
0x1800b307b  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800b3080  mov     rdx, r15; unsigned __int64
0x1800b3083  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b3088  mov     ebx, eax
0x1800b308a  test    eax, eax
0x1800b308c  js      loc_1800B317F
0x1800b3092  lea     r8, aCreationhash; "creationHash."
0x1800b3099  mov     rdx, r15; unsigned __int64
0x1800b309c  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800b30a1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800b30a6  mov     ebx, eax
0x1800b30a8  test    eax, eax
0x1800b30aa  js      loc_1800B317F
0x1800b30b0  lea     rcx, [rdi+1D0h]
0x1800b30b7  mov     rax, [rcx]
0x1800b30ba  lea     rdx, [rsp+250h+var_220]
0x1800b30bf  mov     rax, [rax+28h]
0x1800b30c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b30c8  mov     ebx, eax
0x1800b30ca  test    eax, eax
0x1800b30cc  js      loc_1800B317F
0x1800b30d2  mov     r8, rsi; unsigned __int16 *
0x1800b30d5  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800b30da  mov     rdx, r15; unsigned __int64
0x1800b30dd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b30e2  mov     ebx, eax
0x1800b30e4  test    eax, eax
0x1800b30e6  js      loc_1800B317F
0x1800b30ec  lea     r8, aCreationticket; "creationTicket."
0x1800b30f3  mov     rdx, r15; unsigned __int64
0x1800b30f6  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800b30fb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800b3100  mov     ebx, eax
0x1800b3102  test    eax, eax
0x1800b3104  js      short loc_1800B317F
0x1800b3106  mov     rcx, [rdi+218h]
0x1800b310d  lea     rdx, [rsp+250h+var_220]
0x1800b3112  mov     rax, [rcx]
0x1800b3115  mov     rax, [rax+28h]
0x1800b3119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b311e  mov     ebx, eax
0x1800b3120  test    eax, eax
0x1800b3122  js      short loc_1800B317F
0x1800b3124  mov     r8, rsi; unsigned __int16 *
0x1800b3127  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800b312c  mov     rdx, r15; unsigned __int64
0x1800b312f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b3134  mov     ebx, eax
0x1800b3136  test    eax, eax
0x1800b3138  js      short loc_1800B317F
0x1800b313a  lea     r8, aName_0; "name."
0x1800b3141  mov     rdx, r15; unsigned __int64
0x1800b3144  lea     rcx, [rsp+250h+var_220]; unsigned __int16 *
0x1800b3149  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800b314e  mov     ebx, eax
0x1800b3150  test    eax, eax
0x1800b3152  js      short loc_1800B317F
0x1800b3154  lea     rcx, [rdi+220h]
0x1800b315b  mov     rax, [rcx]
0x1800b315e  lea     rdx, [rsp+250h+var_220]
0x1800b3163  mov     rax, [rax+28h]
0x1800b3167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b316c  mov     ebx, eax
0x1800b316e  test    eax, eax
0x1800b3170  js      short loc_1800B317F
0x1800b3172  mov     rdx, rsi; unsigned __int16 *
0x1800b3175  mov     rcx, rdi; this
0x1800b3178  call    ?DecodeAuthorizationsRsp@TPMW8_COMMAND@tpm12class@@UEAAJPEAG@Z; tpm12class::TPMW8_COMMAND::DecodeAuthorizationsRsp(ushort *)
0x1800b317d  mov     ebx, eax
0x1800b317f  mov     eax, ebx
0x1800b3181  mov     rcx, [rbp+150h+var_20]
0x1800b3188  xor     rcx, rsp; StackCookie
0x1800b318b  call    __security_check_cookie
0x1800b3190  lea     r11, [rsp+250h+var_10]
0x1800b3198  mov     rbx, [r11+30h]
0x1800b319c  mov     rsi, [r11+38h]
0x1800b31a0  mov     rsp, r11
0x1800b31a3  pop     r15
0x1800b31a5  pop     rdi
0x1800b31a6  pop     rbp
0x1800b31a7  retn
```
