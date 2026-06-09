# tpm12class::TPMW8_GetCapability::DecodeRsp(ushort *)

- ea: `0x1800a46f0`
- end: `0x1800a4ea0`
- name: `?DecodeRsp@TPMW8_GetCapability@tpm12class@@UEAAJPEAG@Z`
- size: `1968`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_GetCapability *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180011bd0`
- `0x18002a750`
- `0x1800764d0`
- `0x18007704c`
- `0x1800a46f0`
- `0x1800a5b20`
- `0x1800ba830`
- `0x1800bacf4`
- `0x1800bb4d4`
- `0x1800bb7d0`
- `0x1800bbbf8`
- `0x1800c8010`

## string_xrefs

- `0x1800a4972`: `%scommands[%d].`
- `0x1800a48a5`: `commandCode`
- `0x1800a491f`: `commandCode`
- `0x1800a4999`: `commandCode`
- `0x1800a48f8`: `%sppCommands[%d].`
- `0x1800a487e`: `%sauditCommands[%d].`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_GetCapability::DecodeRsp(
        tpm12class::TPMW8_GetCapability *this,
        unsigned __int16 *a2)
{
  int v4; // ebx
  unsigned __int8 v5; // r9
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int nn; // r14d
  unsigned int mm; // r14d
  unsigned int kk; // r14d
  unsigned int jj; // r14d
  unsigned int ii; // r14d
  unsigned int n; // r14d
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int m; // r14d
  __int64 v22; // r15
  unsigned int k; // r14d
  unsigned int j; // r14d
  unsigned int i; // r14d
  struct TPM_SYMBOLTABLE_ENTRY *v26; // [rsp+20h] [rbp-E0h]
  unsigned __int16 v27; // [rsp+30h] [rbp-D0h] BYREF
  char v28[510]; // [rsp+32h] [rbp-CEh] BYREF

  v27 = 0;
  v4 = 0;
  memset_0(v28, 0, sizeof(v28));
  if ( TraceEnabled() )
  {
    v4 = tpm12class::TPMW8_COMMAND::DecodeRsp(this, a2);
    if ( v4 >= 0 )
    {
      v4 = TraceDirect(L"--TPM2_GetCapability: Parameters---------------------------------------\r\n");
      if ( v4 >= 0 )
      {
        v4 = TraceUINT8Value(
               a2,
               L"moreData",
               *((_BYTE *)this + 204),
               v5,
               (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8I_YES_NO,
               0);
        if ( v4 >= 0 )
        {
          v4 = TraceUINT32Value(
                 a2,
                 L"capability",
                 *((_DWORD *)this + 52),
                 0,
                 (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8_CAP,
                 0);
          if ( v4 >= 0 )
          {
            if ( *((_DWORD *)this + 52) == 256
              || (v4 = TraceUINT32Value(a2, L"count", *((_DWORD *)this + 53), 1u, 0, 0), v4 >= 0) )
            {
              v6 = *((_DWORD *)this + 52);
              if ( v6 > 5 )
              {
                v16 = v6 - 6;
                if ( !v16 )
                {
                  for ( i = 0; i < *((_DWORD *)this + 53); ++i )
                  {
                    LODWORD(v26) = i;
                    v4 = StringCchPrintfW(&v27, 0x100u, L"%stpmProperties[%d].", a2, v26);
                    if ( v4 < 0 )
                      break;
                    v4 = TraceUINT32Value(
                           &v27,
                           L"property",
                           *(_DWORD *)(*((_QWORD *)this + 33) + 8LL * i),
                           0,
                           (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8_PT,
                           1u);
                    if ( v4 < 0 )
                      break;
                    v4 = TraceUINT32Value(&v27, L"value", *(_DWORD *)(*((_QWORD *)this + 33) + 8LL * i + 4), 1u, 0, 0);
                    if ( v4 < 0 )
                      break;
                  }
                  return (unsigned int)v4;
                }
                v17 = v16 - 1;
                if ( !v17 )
                {
                  for ( j = 0; j < *((_DWORD *)this + 53); ++j )
                  {
                    LODWORD(v26) = j;
                    v4 = StringCchPrintfW(&v27, 0x100u, L"%spcrProperties[%d].", a2, v26);
                    if ( v4 < 0 )
                      break;
                    v4 = TraceUINT32Value(
                           &v27,
                           L"property",
                           *(_DWORD *)(*((_QWORD *)this + 34) + 8LL * j),
                           0,
                           (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8_PT_PCR,
                           0);
                    if ( v4 < 0 )
                      break;
                    v4 = TraceBufferValue(
                           &v27,
                           L"pcrSelect",
                           (unsigned __int8 *)(*((_QWORD *)this + 34) + 5LL + 8LL * j),
                           *(unsigned __int8 *)(*((_QWORD *)this + 34) + 8LL * j + 4));
                    if ( v4 < 0 )
                      break;
                  }
                  return (unsigned int)v4;
                }
                v18 = v17 - 1;
                if ( !v18 )
                {
                  for ( k = 0; k < *((_DWORD *)this + 53); ++k )
                  {
                    LODWORD(v26) = k;
                    v4 = StringCchPrintfW(&v27, 0x100u, L"%seccCurves[%d].", a2, v26);
                    if ( v4 < 0 )
                      break;
                    v4 = TraceUINT16Value(
                           &v27,
                           L"curveID",
                           *(_WORD *)(*((_QWORD *)this + 35) + 2LL * k),
                           0,
                           (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8_ECC_CURVE,
                           0);
                    if ( v4 < 0 )
                      break;
                  }
                  return (unsigned int)v4;
                }
                v19 = v18 - 1;
                if ( !v19 )
                {
                  for ( m = 0; m < *((_DWORD *)this + 53); ++m )
                  {
                    LODWORD(v26) = m;
                    v4 = StringCchPrintfW(&v27, 0x100u, L"%sauthPolicies[%d].", a2, v26);
                    if ( v4 < 0 )
                      break;
                    v22 = 136LL * m;
                    v4 = TraceUINT32Value(&v27, L"handle", *(_DWORD *)(v22 + *((_QWORD *)this + 36)), 0, 0, 0);
                    if ( v4 < 0 )
                      break;
                    v4 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)(v22
                                                                                            + *((_QWORD *)this + 36)
                                                                                            + 8LL)
                                                                                + 40LL))(
                           v22 + *((_QWORD *)this + 36) + 8LL,
                           &v27);
                    if ( v4 < 0 )
                      break;
                  }
                  return (unsigned int)v4;
                }
                if ( v19 == 247 )
                {
                  v4 = StringCchPrintfW(&v27, 0x100u, L"%svendorProperties.", a2);
                  if ( v4 >= 0 )
                    return (unsigned int)TraceBufferValue(
                                           a2,
                                           L"vendorSpecificData",
                                           *((unsigned __int8 **)this + 37),
                                           *((_DWORD *)this + 76));
                  return (unsigned int)v4;
                }
              }
              else
              {
                if ( v6 == 5 )
                {
                  for ( n = 0; n < *((_DWORD *)this + 53); ++n )
                  {
                    LODWORD(v26) = n;
                    v4 = StringCchPrintfW(&v27, 0x100u, L"%spcrs[%d].", a2, v26);
                    if ( v4 < 0 )
                      break;
                    v4 = TraceUINT32Value(
                           &v27,
                           L"hashAlg",
                           *(unsigned __int16 *)(*((_QWORD *)this + 32) + 72LL * n + 56),
                           0,
                           (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8_ALG,
                           0);
                    if ( v4 < 0 )
                      break;
                  }
                  return (unsigned int)v4;
                }
                if ( !v6 )
                {
                  for ( ii = 0; ii < *((_DWORD *)this + 53); ++ii )
                  {
                    LODWORD(v26) = ii;
                    v4 = StringCchPrintfW(&v27, 0x100u, L"%salgorithms[%d].", a2, v26);
                    if ( v4 < 0 )
                      break;
                    v4 = TraceUINT16Value(
                           &v27,
                           L"alg",
                           *(_WORD *)(*((_QWORD *)this + 27) + 8LL * ii),
                           0,
                           (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8_ALG,
                           0);
                    if ( v4 < 0 )
                      break;
                    v4 = TraceUINT32Value(
                           &v27,
                           L"alg",
                           *(unsigned __int16 *)(*((_QWORD *)this + 27) + 8LL * ii),
                           0,
                           (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8A_ALGORITHM,
                           0);
                    if ( v4 < 0 )
                      break;
                  }
                  return (unsigned int)v4;
                }
                v7 = v6 - 1;
                if ( !v7 )
                {
                  for ( jj = 0; jj < *((_DWORD *)this + 53); ++jj )
                  {
                    LODWORD(v26) = jj;
                    v4 = StringCchPrintfW(&v27, 0x100u, L"%shandles[%d].", a2, v26);
                    if ( v4 < 0 )
                      break;
                    v4 = TraceUINT32Value(
                           &v27,
                           L"handle",
                           *(_DWORD *)(*((_QWORD *)this + 28) + 4LL * jj),
                           0,
                           (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8_RH,
                           1u);
                    if ( v4 < 0 )
                      break;
                  }
                  return (unsigned int)v4;
                }
                v8 = v7 - 1;
                if ( !v8 )
                {
                  for ( kk = 0; kk < *((_DWORD *)this + 53); ++kk )
                  {
                    LODWORD(v26) = kk;
                    v4 = StringCchPrintfW(&v27, 0x100u, L"%scommands[%d].", a2, v26);
                    if ( v4 < 0 )
                      break;
                    v4 = TraceUINT32Value(
                           &v27,
                           L"commandCode",
                           *(_DWORD *)(*((_QWORD *)this + 29) + 4LL * kk),
                           0,
                           (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8_CC,
                           0);
                    if ( v4 < 0 )
                      break;
                  }
                  return (unsigned int)v4;
                }
                v9 = v8 - 1;
                if ( !v9 )
                {
                  for ( mm = 0; mm < *((_DWORD *)this + 53); ++mm )
                  {
                    LODWORD(v26) = mm;
                    v4 = StringCchPrintfW(&v27, 0x100u, L"%sppCommands[%d].", a2, v26);
                    if ( v4 < 0 )
                      break;
                    v4 = TraceUINT32Value(
                           &v27,
                           L"commandCode",
                           *(_DWORD *)(*((_QWORD *)this + 30) + 4LL * mm),
                           0,
                           (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8_CC,
                           0);
                    if ( v4 < 0 )
                      break;
                  }
                  return (unsigned int)v4;
                }
                if ( v9 == 1 )
                {
                  for ( nn = 0; nn < *((_DWORD *)this + 53); ++nn )
                  {
                    LODWORD(v26) = nn;
                    v4 = StringCchPrintfW(&v27, 0x100u, L"%sauditCommands[%d].", a2, v26);
                    if ( v4 < 0 )
                      break;
                    v4 = TraceUINT32Value(
                           &v27,
                           L"commandCode",
                           *(_DWORD *)(*((_QWORD *)this + 31) + 4LL * nn),
                           0,
                           (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8_CC,
                           0);
                    if ( v4 < 0 )
                      break;
                  }
                  return (unsigned int)v4;
                }
              }
              return 2147500033LL;
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
0x1800a46f0  mov     [rsp-8+arg_10], rbx
0x1800a46f5  push    rbp
0x1800a46f6  push    rsi
0x1800a46f7  push    rdi
0x1800a46f8  push    r12
0x1800a46fa  push    r13
0x1800a46fc  push    r14
0x1800a46fe  push    r15
0x1800a4700  lea     rbp, [rsp-140h]
0x1800a4708  sub     rsp, 240h
0x1800a470f  mov     rax, cs:__security_cookie
0x1800a4716  xor     rax, rsp
0x1800a4719  mov     [rbp+170h+var_40], rax
0x1800a4720  mov     rsi, rdx
0x1800a4723  mov     rdi, rcx
0x1800a4726  xor     r13d, r13d
0x1800a4729  lea     rcx, [rsp+270h+var_23E]; void *
0x1800a472e  xor     edx, edx; Val
0x1800a4730  mov     [rsp+270h+var_240], r13w
0x1800a4736  mov     r8d, 1FEh; Size
0x1800a473c  mov     ebx, r13d
0x1800a473f  call    memset_0
0x1800a4744  call    ?TraceEnabled@@YAEXZ; TraceEnabled(void)
0x1800a4749  test    al, al
0x1800a474b  jz      loc_1800A4E73
0x1800a4751  mov     rdx, rsi; unsigned __int16 *
0x1800a4754  mov     rcx, rdi; this
0x1800a4757  call    ?DecodeRsp@TPMW8_COMMAND@tpm12class@@UEAAJPEAG@Z; tpm12class::TPMW8_COMMAND::DecodeRsp(ushort *)
0x1800a475c  mov     ebx, eax
0x1800a475e  test    eax, eax
0x1800a4760  js      loc_1800A4E73
0x1800a4766  lea     rcx, aTpm2Getcapabil; "--TPM2_GetCapability: Parameters-------"...
0x1800a476d  call    ?TraceDirect@@YAJPEAG@Z; TraceDirect(ushort *)
0x1800a4772  mov     ebx, eax
0x1800a4774  test    eax, eax
0x1800a4776  js      loc_1800A4E73
0x1800a477c  mov     r8b, [rdi+0CCh]; unsigned __int8
0x1800a4783  lea     rax, ?st_TPMW8I_YES_NO@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8I_YES_NO
0x1800a478a  mov     [rsp+270h+var_248], r13b; char
0x1800a478f  lea     rdx, aMoredata; "moreData"
0x1800a4796  mov     rcx, rsi; unsigned __int16 *
0x1800a4799  mov     [rsp+270h+var_250], rax; struct TPM_SYMBOLTABLE_ENTRY *
0x1800a479e  call    ?TraceUINT8Value@@YAJPEAG0EEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT8Value(ushort *,ushort *,uchar,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800a47a3  mov     ebx, eax
0x1800a47a5  test    eax, eax
0x1800a47a7  js      loc_1800A4E73
0x1800a47ad  mov     r8d, [rdi+0D0h]; unsigned int
0x1800a47b4  lea     rax, ?st_TPMW8_CAP@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_CAP
0x1800a47bb  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x1800a47c0  lea     rdx, aCapability; "capability"
0x1800a47c7  xor     r9d, r9d; unsigned __int8
0x1800a47ca  mov     [rsp+270h+var_250], rax; struct TPM_SYMBOLTABLE_ENTRY *
0x1800a47cf  mov     rcx, rsi; unsigned __int16 *
0x1800a47d2  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800a47d7  mov     ebx, eax
0x1800a47d9  test    eax, eax
0x1800a47db  js      loc_1800A4E73
0x1800a47e1  cmp     dword ptr [rdi+0D0h], 100h
0x1800a47eb  lea     r12d, [r13+1]
0x1800a47ef  jz      short loc_1800A481E
0x1800a47f1  mov     r8d, [rdi+0D4h]; unsigned int
0x1800a47f8  lea     rdx, aCount; "count"
0x1800a47ff  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x1800a4804  mov     r9b, r12b; unsigned __int8
0x1800a4807  mov     rcx, rsi; unsigned __int16 *
0x1800a480a  mov     [rsp+270h+var_250], r13; struct TPM_SYMBOLTABLE_ENTRY *
0x1800a480f  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800a4814  mov     ebx, eax
0x1800a4816  test    eax, eax
0x1800a4818  js      loc_1800A4E73
0x1800a481e  mov     eax, [rdi+0D0h]
0x1800a4824  cmp     eax, 5
0x1800a4827  ja      loc_1800A4B80
0x1800a482d  jz      loc_1800A4B00
0x1800a4833  test    eax, eax
0x1800a4835  jz      loc_1800A4A47
0x1800a483b  sub     eax, r12d
0x1800a483e  jz      loc_1800A49CD
0x1800a4844  sub     eax, r12d
0x1800a4847  jz      loc_1800A4953
0x1800a484d  sub     eax, r12d
0x1800a4850  jz      loc_1800A48D9
0x1800a4856  cmp     eax, r12d
0x1800a4859  jnz     loc_1800A4BA7
0x1800a485f  mov     r14d, r13d
0x1800a4862  lea     r15, ?st_TPMW8_CC@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_CC
0x1800a4869  cmp     r14d, [rdi+0D4h]
0x1800a4870  jnb     loc_1800A4E73
0x1800a4876  mov     r9, rsi
0x1800a4879  mov     dword ptr [rsp+270h+var_250], r14d
0x1800a487e  lea     r8, aSauditcommands; "%sauditCommands[%d]."
0x1800a4885  mov     edx, 100h; unsigned __int64
0x1800a488a  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800a488f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a4894  mov     ebx, eax
0x1800a4896  test    eax, eax
0x1800a4898  js      loc_1800A4E73
0x1800a489e  mov     r8, [rdi+0F8h]
0x1800a48a5  lea     rdx, aCommandcode; "commandCode"
0x1800a48ac  mov     eax, r14d
0x1800a48af  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800a48b4  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x1800a48b9  xor     r9d, r9d; unsigned __int8
0x1800a48bc  mov     [rsp+270h+var_250], r15; struct TPM_SYMBOLTABLE_ENTRY *
0x1800a48c1  mov     r8d, [r8+rax*4]; unsigned int
0x1800a48c5  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800a48ca  mov     ebx, eax
0x1800a48cc  test    eax, eax
0x1800a48ce  js      loc_1800A4E73
0x1800a48d4  add     r14d, r12d
0x1800a48d7  jmp     short loc_1800A4869
0x1800a48d9  mov     r14d, r13d
0x1800a48dc  lea     r15, ?st_TPMW8_CC@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_CC
0x1800a48e3  cmp     r14d, [rdi+0D4h]
0x1800a48ea  jnb     loc_1800A4E73
0x1800a48f0  mov     r9, rsi
0x1800a48f3  mov     dword ptr [rsp+270h+var_250], r14d
0x1800a48f8  lea     r8, aSppcommandsD; "%sppCommands[%d]."
0x1800a48ff  mov     edx, 100h; unsigned __int64
0x1800a4904  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800a4909  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a490e  mov     ebx, eax
0x1800a4910  test    eax, eax
0x1800a4912  js      loc_1800A4E73
0x1800a4918  mov     r8, [rdi+0F0h]
0x1800a491f  lea     rdx, aCommandcode; "commandCode"
0x1800a4926  mov     eax, r14d
0x1800a4929  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800a492e  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x1800a4933  xor     r9d, r9d; unsigned __int8
0x1800a4936  mov     [rsp+270h+var_250], r15; struct TPM_SYMBOLTABLE_ENTRY *
0x1800a493b  mov     r8d, [r8+rax*4]; unsigned int
0x1800a493f  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800a4944  mov     ebx, eax
0x1800a4946  test    eax, eax
0x1800a4948  js      loc_1800A4E73
0x1800a494e  add     r14d, r12d
0x1800a4951  jmp     short loc_1800A48E3
0x1800a4953  mov     r14d, r13d
0x1800a4956  lea     r15, ?st_TPMW8_CC@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_CC
0x1800a495d  cmp     r14d, [rdi+0D4h]
0x1800a4964  jnb     loc_1800A4E73
0x1800a496a  mov     r9, rsi
0x1800a496d  mov     dword ptr [rsp+270h+var_250], r14d
0x1800a4972  lea     r8, aScommandsD; "%scommands[%d]."
0x1800a4979  mov     edx, 100h; unsigned __int64
0x1800a497e  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800a4983  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a4988  mov     ebx, eax
0x1800a498a  test    eax, eax
0x1800a498c  js      loc_1800A4E73
0x1800a4992  mov     r8, [rdi+0E8h]
0x1800a4999  lea     rdx, aCommandcode; "commandCode"
0x1800a49a0  mov     eax, r14d
0x1800a49a3  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800a49a8  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x1800a49ad  xor     r9d, r9d; unsigned __int8
0x1800a49b0  mov     [rsp+270h+var_250], r15; struct TPM_SYMBOLTABLE_ENTRY *
0x1800a49b5  mov     r8d, [r8+rax*4]; unsigned int
0x1800a49b9  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800a49be  mov     ebx, eax
0x1800a49c0  test    eax, eax
0x1800a49c2  js      loc_1800A4E73
0x1800a49c8  add     r14d, r12d
0x1800a49cb  jmp     short loc_1800A495D
0x1800a49cd  mov     r14d, r13d
0x1800a49d0  cmp     r14d, [rdi+0D4h]
0x1800a49d7  jnb     loc_1800A4E73
0x1800a49dd  mov     r9, rsi
0x1800a49e0  mov     dword ptr [rsp+270h+var_250], r14d
0x1800a49e5  lea     r8, aShandlesD; "%shandles[%d]."
0x1800a49ec  mov     edx, 100h; unsigned __int64
0x1800a49f1  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800a49f6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a49fb  mov     ebx, eax
0x1800a49fd  test    eax, eax
0x1800a49ff  js      loc_1800A4E73
0x1800a4a05  mov     r8, [rdi+0E0h]
0x1800a4a0c  lea     rcx, ?st_TPMW8_RH@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_RH
0x1800a4a13  mov     eax, r14d
0x1800a4a16  lea     rdx, aHandle; "handle"
0x1800a4a1d  mov     [rsp+270h+var_248], r12b; unsigned __int8
0x1800a4a22  xor     r9d, r9d; unsigned __int8
0x1800a4a25  mov     [rsp+270h+var_250], rcx; struct TPM_SYMBOLTABLE_ENTRY *
0x1800a4a2a  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800a4a2f  mov     r8d, [r8+rax*4]; unsigned int
0x1800a4a33  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800a4a38  mov     ebx, eax
0x1800a4a3a  test    eax, eax
0x1800a4a3c  js      loc_1800A4E73
0x1800a4a42  add     r14d, r12d
0x1800a4a45  jmp     short loc_1800A49D0
0x1800a4a47  mov     r14d, r13d
0x1800a4a4a  lea     r15, ?st_TPMW8_ALG@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_ALG
0x1800a4a51  cmp     r14d, [rdi+0D4h]
0x1800a4a58  jnb     loc_1800A4E73
0x1800a4a5e  mov     r9, rsi
0x1800a4a61  mov     dword ptr [rsp+270h+var_250], r14d
0x1800a4a66  lea     r8, aSalgorithmsD; "%salgorithms[%d]."
0x1800a4a6d  mov     edx, 100h; unsigned __int64
0x1800a4a72  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800a4a77  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a4a7c  mov     ebx, eax
0x1800a4a7e  test    eax, eax
0x1800a4a80  js      loc_1800A4E73
0x1800a4a86  mov     r8, [rdi+0D8h]
0x1800a4a8d  lea     rdx, aAlg; "alg"
0x1800a4a94  mov     r12d, r14d
0x1800a4a97  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800a4a9c  mov     [rsp+270h+var_248], r13b; char
0x1800a4aa1  xor     r9d, r9d; unsigned __int8
0x1800a4aa4  mov     [rsp+270h+var_250], r15; struct TPM_SYMBOLTABLE_ENTRY *
0x1800a4aa9  movzx   r8d, word ptr [r8+r12*8]; unsigned __int16
0x1800a4aae  call    ?TraceUINT16Value@@YAJPEAG0GEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT16Value(ushort *,ushort *,ushort,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800a4ab3  mov     ebx, eax
0x1800a4ab5  test    eax, eax
0x1800a4ab7  js      loc_1800A4E73
0x1800a4abd  mov     rax, [rdi+0D8h]
0x1800a4ac4  lea     rdx, aAlg; "alg"
0x1800a4acb  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x1800a4ad0  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800a4ad5  xor     r9d, r9d; unsigned __int8
0x1800a4ad8  movzx   r8d, word ptr [rax+r12*8]; unsigned int
0x1800a4add  lea     rax, ?st_TPMW8A_ALGORITHM@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8A_ALGORITHM
0x1800a4ae4  mov     [rsp+270h+var_250], rax; struct TPM_SYMBOLTABLE_ENTRY *
0x1800a4ae9  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800a4aee  mov     ebx, eax
0x1800a4af0  test    eax, eax
0x1800a4af2  js      loc_1800A4E73
0x1800a4af8  inc     r14d
0x1800a4afb  jmp     loc_1800A4A51
0x1800a4b00  mov     r14d, r13d
0x1800a4b03  lea     r15, ?st_TPMW8_ALG@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_ALG
0x1800a4b0a  cmp     r14d, [rdi+0D4h]
0x1800a4b11  jnb     loc_1800A4E73
0x1800a4b17  mov     r9, rsi
0x1800a4b1a  mov     dword ptr [rsp+270h+var_250], r14d
0x1800a4b1f  lea     r8, aSpcrsD; "%spcrs[%d]."
0x1800a4b26  mov     edx, 100h; unsigned __int64
0x1800a4b2b  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800a4b30  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a4b35  mov     ebx, eax
0x1800a4b37  test    eax, eax
0x1800a4b39  js      loc_1800A4E73
0x1800a4b3f  mov     eax, r14d
0x1800a4b42  lea     rdx, aHashalg; "hashAlg"
0x1800a4b49  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x1800a4b4e  xor     r9d, r9d; unsigned __int8
0x1800a4b51  mov     [rsp+270h+var_250], r15; struct TPM_SYMBOLTABLE_ENTRY *
0x1800a4b56  lea     rcx, [rax+rax*8]
0x1800a4b5a  mov     rax, [rdi+100h]
0x1800a4b61  movzx   r8d, word ptr [rax+rcx*8+38h]; unsigned int
0x1800a4b67  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800a4b6c  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800a4b71  mov     ebx, eax
0x1800a4b73  test    eax, eax
0x1800a4b75  js      loc_1800A4E73
0x1800a4b7b  add     r14d, r12d
0x1800a4b7e  jmp     short loc_1800A4B0A
0x1800a4b80  sub     eax, 6
0x1800a4b83  jz      loc_1800A4DC6
0x1800a4b89  sub     eax, r12d
0x1800a4b8c  jz      loc_1800A4D19
0x1800a4b92  sub     eax, r12d
0x1800a4b95  jz      loc_1800A4C9E
0x1800a4b9b  sub     eax, r12d
0x1800a4b9e  jz      short loc_1800A4BF8
0x1800a4ba0  cmp     eax, 0F7h
0x1800a4ba5  jz      short loc_1800A4BB1
0x1800a4ba7  mov     eax, 80004001h
0x1800a4bac  jmp     loc_1800A4E75
0x1800a4bb1  mov     r9, rsi
0x1800a4bb4  lea     r8, aSvendorpropert; "%svendorProperties."
0x1800a4bbb  mov     edx, 100h; unsigned __int64
0x1800a4bc0  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800a4bc5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a4bca  mov     ebx, eax
0x1800a4bcc  test    eax, eax
0x1800a4bce  js      loc_1800A4E73
0x1800a4bd4  mov     r9d, [rdi+130h]; unsigned int
0x1800a4bdb  lea     rdx, aVendorspecific_1; "vendorSpecificData"
0x1800a4be2  mov     r8, [rdi+128h]; unsigned __int8 *
0x1800a4be9  mov     rcx, rsi; unsigned __int16 *
0x1800a4bec  call    ?TraceBufferValue@@YAJPEAG0PEAEI@Z; TraceBufferValue(ushort *,ushort *,uchar *,uint)
0x1800a4bf1  mov     ebx, eax
0x1800a4bf3  jmp     loc_1800A4E73
0x1800a4bf8  mov     r14d, r13d
0x1800a4bfb  cmp     r14d, [rdi+0D4h]
0x1800a4c02  jnb     loc_1800A4E73
0x1800a4c08  mov     r9, rsi
0x1800a4c0b  mov     dword ptr [rsp+270h+var_250], r14d
0x1800a4c10  lea     r8, aSauthpoliciesD; "%sauthPolicies[%d]."
0x1800a4c17  mov     edx, 100h; unsigned __int64
0x1800a4c1c  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800a4c21  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a4c26  mov     ebx, eax
0x1800a4c28  test    eax, eax
0x1800a4c2a  js      loc_1800A4E73
0x1800a4c30  mov     r8, [rdi+120h]
0x1800a4c37  lea     rdx, aHandle; "handle"
  ... truncated ...
```
