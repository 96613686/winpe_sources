# tpm12class::TPMW8_PCR_Read::DecodeRsp(ushort *)

- ea: `0x1800b9430`
- end: `0x1800b961d`
- name: `?DecodeRsp@TPMW8_PCR_Read@tpm12class@@UEAAJPEAG@Z`
- size: `493`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_PCR_Read *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180011bd0`
- `0x18002a750`
- `0x18003cce0`
- `0x18004c1e8`
- `0x1800764d0`
- `0x18007704c`
- `0x1800a5b20`
- `0x1800b9430`
- `0x1800bacf4`
- `0x1800bb7d0`
- `0x1800c8010`

## string_xrefs

- `0x1800b949a`: `--TPM2_PCR_Read: Parameters------------------------------------------\n`
- `0x1800b94b7`: `pcrUpdateCounter`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_PCR_Read::DecodeRsp(tpm12class::TPMW8_PCR_Read *this, unsigned __int16 *a2)
{
  int v4; // ebx
  __int64 v5; // rsi
  struct TPM_SYMBOLTABLE_ENTRY *v7; // [rsp+20h] [rbp-238h]
  unsigned __int16 v8; // [rsp+30h] [rbp-228h] BYREF
  _BYTE v9[510]; // [rsp+32h] [rbp-226h] BYREF

  v8 = 0;
  v4 = 0;
  memset_0(v9, 0, sizeof(v9));
  if ( TraceEnabled() )
  {
    v4 = tpm12class::TPMW8_COMMAND::DecodeRsp(this, a2);
    if ( v4 >= 0 )
    {
      v4 = TraceDirect(L"--TPM2_PCR_Read: Parameters------------------------------------------\r\n");
      if ( v4 >= 0 )
      {
        v4 = TraceUINT32Value(a2, L"pcrUpdateCounter", *((_DWORD *)this + 66), 1u, 0, 0);
        if ( v4 >= 0 )
        {
          v4 = StringCchCopyW(&v8, 0x100u, a2);
          if ( v4 >= 0 )
          {
            v4 = StringCchCatW(&v8, 0x100u, L"pcrSelectionOut.");
            if ( v4 >= 0 )
            {
              v4 = (*(__int64 (__fastcall **)(char *, unsigned __int16 *))(*((_QWORD *)this + 34) + 40LL))(
                     (char *)this + 272,
                     &v8);
              if ( v4 >= 0 )
              {
                v4 = StringCchPrintfW(&v8, 0x100u, L"%spcrValues.", a2);
                if ( v4 >= 0 )
                {
                  v4 = TraceUINT32Value(&v8, L"count", *((_DWORD *)this + 86), 1u, 0, 0);
                  if ( v4 >= 0 )
                  {
                    if ( *((_DWORD *)this + 86) )
                    {
                      v5 = 0;
                      do
                      {
                        LODWORD(v7) = v5;
                        v4 = StringCchPrintfW(&v8, 0x100u, L"%spcrValues.digests[%d].", a2, v7);
                        if ( v4 < 0 )
                          break;
                        v4 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)(*((_QWORD *)this + 44)
                                                                                                + 72 * v5)
                                                                                    + 40LL))(
                               *((_QWORD *)this + 44) + 72 * v5,
                               &v8);
                        if ( v4 < 0 )
                          break;
                        v5 = (unsigned int)(v5 + 1);
                      }
                      while ( (unsigned int)v5 < *((_DWORD *)this + 86) );
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
0x1800b9430  mov     [rsp+arg_10], rbx
0x1800b9435  mov     [rsp+arg_18], rbp
0x1800b943a  push    rsi
0x1800b943b  push    rdi
0x1800b943c  push    r15
0x1800b943e  sub     rsp, 240h
0x1800b9445  mov     rax, cs:__security_cookie
0x1800b944c  xor     rax, rsp
0x1800b944f  mov     [rsp+258h+var_28], rax
0x1800b9457  mov     rbp, rdx
0x1800b945a  mov     rdi, rcx
0x1800b945d  xor     eax, eax
0x1800b945f  lea     rcx, [rsp+258h+var_226]; void *
0x1800b9464  xor     edx, edx; Val
0x1800b9466  mov     [rsp+258h+var_228], ax
0x1800b946b  mov     r8d, 1FEh; Size
0x1800b9471  xor     ebx, ebx
0x1800b9473  call    memset_0
0x1800b9478  call    ?TraceEnabled@@YAEXZ; TraceEnabled(void)
0x1800b947d  test    al, al
0x1800b947f  jz      loc_1800B95F2
0x1800b9485  mov     rdx, rbp; unsigned __int16 *
0x1800b9488  mov     rcx, rdi; this
0x1800b948b  call    ?DecodeRsp@TPMW8_COMMAND@tpm12class@@UEAAJPEAG@Z; tpm12class::TPMW8_COMMAND::DecodeRsp(ushort *)
0x1800b9490  mov     ebx, eax
0x1800b9492  test    eax, eax
0x1800b9494  js      loc_1800B95F2
0x1800b949a  lea     rcx, aTpm2PcrReadPar; "--TPM2_PCR_Read: Parameters------------"...
0x1800b94a1  call    ?TraceDirect@@YAJPEAG@Z; TraceDirect(ushort *)
0x1800b94a6  mov     ebx, eax
0x1800b94a8  test    eax, eax
0x1800b94aa  js      loc_1800B95F2
0x1800b94b0  mov     r8d, [rdi+108h]; unsigned int
0x1800b94b7  lea     rdx, aPcrupdatecount; "pcrUpdateCounter"
0x1800b94be  mov     [rsp+258h+var_230], 0; unsigned __int8
0x1800b94c3  mov     r9b, 1; unsigned __int8
0x1800b94c6  mov     rcx, rbp; unsigned __int16 *
0x1800b94c9  mov     [rsp+258h+var_238], 0; struct TPM_SYMBOLTABLE_ENTRY *
0x1800b94d2  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800b94d7  mov     ebx, eax
0x1800b94d9  test    eax, eax
0x1800b94db  js      loc_1800B95F2
0x1800b94e1  mov     r15d, 100h
0x1800b94e7  lea     rcx, [rsp+258h+var_228]; unsigned __int16 *
0x1800b94ec  mov     edx, r15d; unsigned __int64
0x1800b94ef  mov     r8, rbp; unsigned __int16 *
0x1800b94f2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b94f7  mov     ebx, eax
0x1800b94f9  test    eax, eax
0x1800b94fb  js      loc_1800B95F2
0x1800b9501  lea     r8, aPcrselectionou; "pcrSelectionOut."
0x1800b9508  mov     edx, r15d; unsigned __int64
0x1800b950b  lea     rcx, [rsp+258h+var_228]; unsigned __int16 *
0x1800b9510  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800b9515  mov     ebx, eax
0x1800b9517  test    eax, eax
0x1800b9519  js      loc_1800B95F2
0x1800b951f  lea     rcx, [rdi+110h]
0x1800b9526  mov     rax, [rcx]
0x1800b9529  lea     rdx, [rsp+258h+var_228]
0x1800b952e  mov     rax, [rax+28h]
0x1800b9532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9537  mov     ebx, eax
0x1800b9539  test    eax, eax
0x1800b953b  js      loc_1800B95F2
0x1800b9541  mov     r9, rbp
0x1800b9544  lea     r8, aSpcrvalues; "%spcrValues."
0x1800b954b  mov     edx, r15d; unsigned __int64
0x1800b954e  lea     rcx, [rsp+258h+var_228]; unsigned __int16 *
0x1800b9553  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b9558  mov     ebx, eax
0x1800b955a  test    eax, eax
0x1800b955c  js      loc_1800B95F2
0x1800b9562  mov     r8d, [rdi+158h]; unsigned int
0x1800b9569  lea     rdx, aCount; "count"
0x1800b9570  mov     [rsp+258h+var_230], 0; unsigned __int8
0x1800b9575  lea     rcx, [rsp+258h+var_228]; unsigned __int16 *
0x1800b957a  mov     r9b, 1; unsigned __int8
0x1800b957d  mov     [rsp+258h+var_238], 0; struct TPM_SYMBOLTABLE_ENTRY *
0x1800b9586  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800b958b  mov     ebx, eax
0x1800b958d  test    eax, eax
0x1800b958f  js      short loc_1800B95F2
0x1800b9591  mov     eax, [rdi+158h]
0x1800b9597  test    eax, eax
0x1800b9599  jz      short loc_1800B95F2
0x1800b959b  xor     esi, esi
0x1800b959d  test    eax, eax
0x1800b959f  jz      short loc_1800B95F2
0x1800b95a1  mov     r9, rbp
0x1800b95a4  mov     dword ptr [rsp+258h+var_238], esi
0x1800b95a8  lea     r8, aSpcrvaluesDige; "%spcrValues.digests[%d]."
0x1800b95af  mov     rdx, r15; unsigned __int64
0x1800b95b2  lea     rcx, [rsp+258h+var_228]; unsigned __int16 *
0x1800b95b7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b95bc  mov     ebx, eax
0x1800b95be  test    eax, eax
0x1800b95c0  js      short loc_1800B95F2
0x1800b95c2  mov     rax, [rdi+160h]
0x1800b95c9  lea     rcx, [rsi+rsi*8]
0x1800b95cd  lea     rdx, [rsp+258h+var_228]
0x1800b95d2  lea     rcx, [rax+rcx*8]
0x1800b95d6  mov     rax, [rcx]
0x1800b95d9  mov     rax, [rax+28h]
0x1800b95dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b95e2  mov     ebx, eax
0x1800b95e4  test    eax, eax
0x1800b95e6  js      short loc_1800B95F2
0x1800b95e8  inc     esi
0x1800b95ea  cmp     esi, [rdi+158h]
0x1800b95f0  jb      short loc_1800B95A1
0x1800b95f2  mov     eax, ebx
0x1800b95f4  mov     rcx, [rsp+258h+var_28]
0x1800b95fc  xor     rcx, rsp; StackCookie
0x1800b95ff  call    __security_check_cookie
0x1800b9604  lea     r11, [rsp+258h+var_18]
0x1800b960c  mov     rbx, [r11+30h]
0x1800b9610  mov     rbp, [r11+38h]
0x1800b9614  mov     rsp, r11
0x1800b9617  pop     r15
0x1800b9619  pop     rdi
0x1800b961a  pop     rsi
0x1800b961b  retn
```
