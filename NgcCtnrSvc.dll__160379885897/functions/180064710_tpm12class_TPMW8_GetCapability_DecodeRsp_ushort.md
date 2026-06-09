# tpm12class::TPMW8_GetCapability::DecodeRsp(ushort *)

- ea: `0x180064710`
- end: `0x180064ec0`
- name: `?DecodeRsp@TPMW8_GetCapability@tpm12class@@UEAAJPEAG@Z`
- size: `1968`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_GetCapability *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x18001505c`
- `0x18002c640`
- `0x18002d518`
- `0x180064710`
- `0x180067390`
- `0x18006c23c`
- `0x18006c700`
- `0x18006c7ac`
- `0x18006cc3c`
- `0x18006cf38`
- `0x18006d230`
- `0x180080010`

## string_xrefs

- `0x180064992`: `%scommands[%d].`
- `0x1800648c5`: `commandCode`
- `0x18006493f`: `commandCode`
- `0x1800649b9`: `commandCode`
- `0x180064918`: `%sppCommands[%d].`
- `0x18006489e`: `%sauditCommands[%d].`

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
0x180064710  mov     [rsp-8+arg_10], rbx
0x180064715  push    rbp
0x180064716  push    rsi
0x180064717  push    rdi
0x180064718  push    r12
0x18006471a  push    r13
0x18006471c  push    r14
0x18006471e  push    r15
0x180064720  lea     rbp, [rsp-140h]
0x180064728  sub     rsp, 240h
0x18006472f  mov     rax, cs:__security_cookie
0x180064736  xor     rax, rsp
0x180064739  mov     [rbp+170h+var_40], rax
0x180064740  mov     rsi, rdx
0x180064743  mov     rdi, rcx
0x180064746  xor     r13d, r13d
0x180064749  lea     rcx, [rsp+270h+var_23E]; void *
0x18006474e  xor     edx, edx; Val
0x180064750  mov     [rsp+270h+var_240], r13w
0x180064756  mov     r8d, 1FEh; Size
0x18006475c  mov     ebx, r13d
0x18006475f  call    memset_0
0x180064764  call    ?TraceEnabled@@YAEXZ; TraceEnabled(void)
0x180064769  test    al, al
0x18006476b  jz      loc_180064E93
0x180064771  mov     rdx, rsi; unsigned __int16 *
0x180064774  mov     rcx, rdi; this
0x180064777  call    ?DecodeRsp@TPMW8_COMMAND@tpm12class@@UEAAJPEAG@Z; tpm12class::TPMW8_COMMAND::DecodeRsp(ushort *)
0x18006477c  mov     ebx, eax
0x18006477e  test    eax, eax
0x180064780  js      loc_180064E93
0x180064786  lea     rcx, aTpm2Getcapabil; "--TPM2_GetCapability: Parameters-------"...
0x18006478d  call    ?TraceDirect@@YAJPEAG@Z; TraceDirect(ushort *)
0x180064792  mov     ebx, eax
0x180064794  test    eax, eax
0x180064796  js      loc_180064E93
0x18006479c  mov     r8b, [rdi+0CCh]; unsigned __int8
0x1800647a3  lea     rax, ?st_TPMW8I_YES_NO@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8I_YES_NO
0x1800647aa  mov     [rsp+270h+var_248], r13b; char
0x1800647af  lea     rdx, aMoredata; "moreData"
0x1800647b6  mov     rcx, rsi; unsigned __int16 *
0x1800647b9  mov     [rsp+270h+var_250], rax; struct TPM_SYMBOLTABLE_ENTRY *
0x1800647be  call    ?TraceUINT8Value@@YAJPEAG0EEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT8Value(ushort *,ushort *,uchar,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800647c3  mov     ebx, eax
0x1800647c5  test    eax, eax
0x1800647c7  js      loc_180064E93
0x1800647cd  mov     r8d, [rdi+0D0h]; unsigned int
0x1800647d4  lea     rax, ?st_TPMW8_CAP@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_CAP
0x1800647db  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x1800647e0  lea     rdx, aCapability; "capability"
0x1800647e7  xor     r9d, r9d; unsigned __int8
0x1800647ea  mov     [rsp+270h+var_250], rax; struct TPM_SYMBOLTABLE_ENTRY *
0x1800647ef  mov     rcx, rsi; unsigned __int16 *
0x1800647f2  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800647f7  mov     ebx, eax
0x1800647f9  test    eax, eax
0x1800647fb  js      loc_180064E93
0x180064801  cmp     dword ptr [rdi+0D0h], 100h
0x18006480b  lea     r12d, [r13+1]
0x18006480f  jz      short loc_18006483E
0x180064811  mov     r8d, [rdi+0D4h]; unsigned int
0x180064818  lea     rdx, aCount; "count"
0x18006481f  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x180064824  mov     r9b, r12b; unsigned __int8
0x180064827  mov     rcx, rsi; unsigned __int16 *
0x18006482a  mov     [rsp+270h+var_250], r13; struct TPM_SYMBOLTABLE_ENTRY *
0x18006482f  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x180064834  mov     ebx, eax
0x180064836  test    eax, eax
0x180064838  js      loc_180064E93
0x18006483e  mov     eax, [rdi+0D0h]
0x180064844  cmp     eax, 5
0x180064847  ja      loc_180064BA0
0x18006484d  jz      loc_180064B20
0x180064853  test    eax, eax
0x180064855  jz      loc_180064A67
0x18006485b  sub     eax, r12d
0x18006485e  jz      loc_1800649ED
0x180064864  sub     eax, r12d
0x180064867  jz      loc_180064973
0x18006486d  sub     eax, r12d
0x180064870  jz      loc_1800648F9
0x180064876  cmp     eax, r12d
0x180064879  jnz     loc_180064BC7
0x18006487f  mov     r14d, r13d
0x180064882  lea     r15, ?st_TPMW8_CC@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_CC
0x180064889  cmp     r14d, [rdi+0D4h]
0x180064890  jnb     loc_180064E93
0x180064896  mov     r9, rsi
0x180064899  mov     dword ptr [rsp+270h+var_250], r14d
0x18006489e  lea     r8, aSauditcommands; "%sauditCommands[%d]."
0x1800648a5  mov     edx, 100h; unsigned __int64
0x1800648aa  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800648af  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800648b4  mov     ebx, eax
0x1800648b6  test    eax, eax
0x1800648b8  js      loc_180064E93
0x1800648be  mov     r8, [rdi+0F8h]
0x1800648c5  lea     rdx, aCommandcode; "commandCode"
0x1800648cc  mov     eax, r14d
0x1800648cf  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800648d4  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x1800648d9  xor     r9d, r9d; unsigned __int8
0x1800648dc  mov     [rsp+270h+var_250], r15; struct TPM_SYMBOLTABLE_ENTRY *
0x1800648e1  mov     r8d, [r8+rax*4]; unsigned int
0x1800648e5  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800648ea  mov     ebx, eax
0x1800648ec  test    eax, eax
0x1800648ee  js      loc_180064E93
0x1800648f4  add     r14d, r12d
0x1800648f7  jmp     short loc_180064889
0x1800648f9  mov     r14d, r13d
0x1800648fc  lea     r15, ?st_TPMW8_CC@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_CC
0x180064903  cmp     r14d, [rdi+0D4h]
0x18006490a  jnb     loc_180064E93
0x180064910  mov     r9, rsi
0x180064913  mov     dword ptr [rsp+270h+var_250], r14d
0x180064918  lea     r8, aSppcommandsD; "%sppCommands[%d]."
0x18006491f  mov     edx, 100h; unsigned __int64
0x180064924  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x180064929  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006492e  mov     ebx, eax
0x180064930  test    eax, eax
0x180064932  js      loc_180064E93
0x180064938  mov     r8, [rdi+0F0h]
0x18006493f  lea     rdx, aCommandcode; "commandCode"
0x180064946  mov     eax, r14d
0x180064949  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x18006494e  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x180064953  xor     r9d, r9d; unsigned __int8
0x180064956  mov     [rsp+270h+var_250], r15; struct TPM_SYMBOLTABLE_ENTRY *
0x18006495b  mov     r8d, [r8+rax*4]; unsigned int
0x18006495f  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x180064964  mov     ebx, eax
0x180064966  test    eax, eax
0x180064968  js      loc_180064E93
0x18006496e  add     r14d, r12d
0x180064971  jmp     short loc_180064903
0x180064973  mov     r14d, r13d
0x180064976  lea     r15, ?st_TPMW8_CC@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_CC
0x18006497d  cmp     r14d, [rdi+0D4h]
0x180064984  jnb     loc_180064E93
0x18006498a  mov     r9, rsi
0x18006498d  mov     dword ptr [rsp+270h+var_250], r14d
0x180064992  lea     r8, aScommandsD; "%scommands[%d]."
0x180064999  mov     edx, 100h; unsigned __int64
0x18006499e  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800649a3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800649a8  mov     ebx, eax
0x1800649aa  test    eax, eax
0x1800649ac  js      loc_180064E93
0x1800649b2  mov     r8, [rdi+0E8h]
0x1800649b9  lea     rdx, aCommandcode; "commandCode"
0x1800649c0  mov     eax, r14d
0x1800649c3  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800649c8  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x1800649cd  xor     r9d, r9d; unsigned __int8
0x1800649d0  mov     [rsp+270h+var_250], r15; struct TPM_SYMBOLTABLE_ENTRY *
0x1800649d5  mov     r8d, [r8+rax*4]; unsigned int
0x1800649d9  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800649de  mov     ebx, eax
0x1800649e0  test    eax, eax
0x1800649e2  js      loc_180064E93
0x1800649e8  add     r14d, r12d
0x1800649eb  jmp     short loc_18006497D
0x1800649ed  mov     r14d, r13d
0x1800649f0  cmp     r14d, [rdi+0D4h]
0x1800649f7  jnb     loc_180064E93
0x1800649fd  mov     r9, rsi
0x180064a00  mov     dword ptr [rsp+270h+var_250], r14d
0x180064a05  lea     r8, aShandlesD; "%shandles[%d]."
0x180064a0c  mov     edx, 100h; unsigned __int64
0x180064a11  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x180064a16  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180064a1b  mov     ebx, eax
0x180064a1d  test    eax, eax
0x180064a1f  js      loc_180064E93
0x180064a25  mov     r8, [rdi+0E0h]
0x180064a2c  lea     rcx, ?st_TPMW8_RH@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_RH
0x180064a33  mov     eax, r14d
0x180064a36  lea     rdx, aHandle; "handle"
0x180064a3d  mov     [rsp+270h+var_248], r12b; unsigned __int8
0x180064a42  xor     r9d, r9d; unsigned __int8
0x180064a45  mov     [rsp+270h+var_250], rcx; struct TPM_SYMBOLTABLE_ENTRY *
0x180064a4a  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x180064a4f  mov     r8d, [r8+rax*4]; unsigned int
0x180064a53  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x180064a58  mov     ebx, eax
0x180064a5a  test    eax, eax
0x180064a5c  js      loc_180064E93
0x180064a62  add     r14d, r12d
0x180064a65  jmp     short loc_1800649F0
0x180064a67  mov     r14d, r13d
0x180064a6a  lea     r15, ?st_TPMW8_ALG@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_ALG
0x180064a71  cmp     r14d, [rdi+0D4h]
0x180064a78  jnb     loc_180064E93
0x180064a7e  mov     r9, rsi
0x180064a81  mov     dword ptr [rsp+270h+var_250], r14d
0x180064a86  lea     r8, aSalgorithmsD; "%salgorithms[%d]."
0x180064a8d  mov     edx, 100h; unsigned __int64
0x180064a92  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x180064a97  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180064a9c  mov     ebx, eax
0x180064a9e  test    eax, eax
0x180064aa0  js      loc_180064E93
0x180064aa6  mov     r8, [rdi+0D8h]
0x180064aad  lea     rdx, aAlg; "alg"
0x180064ab4  mov     r12d, r14d
0x180064ab7  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x180064abc  mov     [rsp+270h+var_248], r13b; char
0x180064ac1  xor     r9d, r9d; unsigned __int8
0x180064ac4  mov     [rsp+270h+var_250], r15; struct TPM_SYMBOLTABLE_ENTRY *
0x180064ac9  movzx   r8d, word ptr [r8+r12*8]; unsigned __int16
0x180064ace  call    ?TraceUINT16Value@@YAJPEAG0GEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT16Value(ushort *,ushort *,ushort,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x180064ad3  mov     ebx, eax
0x180064ad5  test    eax, eax
0x180064ad7  js      loc_180064E93
0x180064add  mov     rax, [rdi+0D8h]
0x180064ae4  lea     rdx, aAlg; "alg"
0x180064aeb  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x180064af0  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x180064af5  xor     r9d, r9d; unsigned __int8
0x180064af8  movzx   r8d, word ptr [rax+r12*8]; unsigned int
0x180064afd  lea     rax, ?st_TPMW8A_ALGORITHM@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8A_ALGORITHM
0x180064b04  mov     [rsp+270h+var_250], rax; struct TPM_SYMBOLTABLE_ENTRY *
0x180064b09  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x180064b0e  mov     ebx, eax
0x180064b10  test    eax, eax
0x180064b12  js      loc_180064E93
0x180064b18  inc     r14d
0x180064b1b  jmp     loc_180064A71
0x180064b20  mov     r14d, r13d
0x180064b23  lea     r15, ?st_TPMW8_ALG@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_ALG
0x180064b2a  cmp     r14d, [rdi+0D4h]
0x180064b31  jnb     loc_180064E93
0x180064b37  mov     r9, rsi
0x180064b3a  mov     dword ptr [rsp+270h+var_250], r14d
0x180064b3f  lea     r8, aSpcrsD; "%spcrs[%d]."
0x180064b46  mov     edx, 100h; unsigned __int64
0x180064b4b  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x180064b50  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180064b55  mov     ebx, eax
0x180064b57  test    eax, eax
0x180064b59  js      loc_180064E93
0x180064b5f  mov     eax, r14d
0x180064b62  lea     rdx, aHashalg; "hashAlg"
0x180064b69  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x180064b6e  xor     r9d, r9d; unsigned __int8
0x180064b71  mov     [rsp+270h+var_250], r15; struct TPM_SYMBOLTABLE_ENTRY *
0x180064b76  lea     rcx, [rax+rax*8]
0x180064b7a  mov     rax, [rdi+100h]
0x180064b81  movzx   r8d, word ptr [rax+rcx*8+38h]; unsigned int
0x180064b87  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x180064b8c  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x180064b91  mov     ebx, eax
0x180064b93  test    eax, eax
0x180064b95  js      loc_180064E93
0x180064b9b  add     r14d, r12d
0x180064b9e  jmp     short loc_180064B2A
0x180064ba0  sub     eax, 6
0x180064ba3  jz      loc_180064DE6
0x180064ba9  sub     eax, r12d
0x180064bac  jz      loc_180064D39
0x180064bb2  sub     eax, r12d
0x180064bb5  jz      loc_180064CBE
0x180064bbb  sub     eax, r12d
0x180064bbe  jz      short loc_180064C18
0x180064bc0  cmp     eax, 0F7h
0x180064bc5  jz      short loc_180064BD1
0x180064bc7  mov     eax, 80004001h
0x180064bcc  jmp     loc_180064E95
0x180064bd1  mov     r9, rsi
0x180064bd4  lea     r8, aSvendorpropert; "%svendorProperties."
0x180064bdb  mov     edx, 100h; unsigned __int64
0x180064be0  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x180064be5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180064bea  mov     ebx, eax
0x180064bec  test    eax, eax
0x180064bee  js      loc_180064E93
0x180064bf4  mov     r9d, [rdi+130h]; unsigned int
0x180064bfb  lea     rdx, aVendorspecific; "vendorSpecificData"
0x180064c02  mov     r8, [rdi+128h]; unsigned __int8 *
0x180064c09  mov     rcx, rsi; unsigned __int16 *
0x180064c0c  call    ?TraceBufferValue@@YAJPEAG0PEAEI@Z; TraceBufferValue(ushort *,ushort *,uchar *,uint)
0x180064c11  mov     ebx, eax
0x180064c13  jmp     loc_180064E93
0x180064c18  mov     r14d, r13d
0x180064c1b  cmp     r14d, [rdi+0D4h]
0x180064c22  jnb     loc_180064E93
0x180064c28  mov     r9, rsi
0x180064c2b  mov     dword ptr [rsp+270h+var_250], r14d
0x180064c30  lea     r8, aSauthpoliciesD; "%sauthPolicies[%d]."
0x180064c37  mov     edx, 100h; unsigned __int64
0x180064c3c  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x180064c41  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180064c46  mov     ebx, eax
0x180064c48  test    eax, eax
0x180064c4a  js      loc_180064E93
0x180064c50  mov     r8, [rdi+120h]
0x180064c57  lea     rdx, aHandle; "handle"
  ... truncated ...
```
