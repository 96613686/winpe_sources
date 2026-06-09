# tpm12class::TPMW8_GetCapability::DecodeRsp(ushort *)

- ea: `0x1800a7d90`
- end: `0x1800a8540`
- name: `?DecodeRsp@TPMW8_GetCapability@tpm12class@@UEAAJPEAG@Z`
- size: `1968`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_GetCapability *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180007270`
- `0x180007c7c`
- `0x180058420`
- `0x1800a0700`
- `0x1800a7d90`
- `0x1800a9374`
- `0x1800a9838`
- `0x1800a98e4`
- `0x1800aa038`
- `0x1800aa334`
- `0x1800aa62c`
- `0x1800c0010`

## string_xrefs

- `0x1800a7f45`: `commandCode`
- `0x1800a7fbf`: `commandCode`
- `0x1800a8039`: `commandCode`
- `0x1800a8012`: `%scommands[%d].`
- `0x1800a7f98`: `%sppCommands[%d].`
- `0x1800a7f1e`: `%sauditCommands[%d].`

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
0x1800a7d90  mov     [rsp-8+arg_10], rbx
0x1800a7d95  push    rbp
0x1800a7d96  push    rsi
0x1800a7d97  push    rdi
0x1800a7d98  push    r12
0x1800a7d9a  push    r13
0x1800a7d9c  push    r14
0x1800a7d9e  push    r15
0x1800a7da0  lea     rbp, [rsp-140h]
0x1800a7da8  sub     rsp, 240h
0x1800a7daf  mov     rax, cs:__security_cookie
0x1800a7db6  xor     rax, rsp
0x1800a7db9  mov     [rbp+170h+var_40], rax
0x1800a7dc0  mov     rsi, rdx
0x1800a7dc3  mov     rdi, rcx
0x1800a7dc6  xor     r13d, r13d
0x1800a7dc9  lea     rcx, [rsp+270h+var_23E]; void *
0x1800a7dce  xor     edx, edx; Val
0x1800a7dd0  mov     [rsp+270h+var_240], r13w
0x1800a7dd6  mov     r8d, 1FEh; Size
0x1800a7ddc  mov     ebx, r13d
0x1800a7ddf  call    memset_0
0x1800a7de4  call    ?TraceEnabled@@YAEXZ; TraceEnabled(void)
0x1800a7de9  test    al, al
0x1800a7deb  jz      loc_1800A8513
0x1800a7df1  mov     rdx, rsi; unsigned __int16 *
0x1800a7df4  mov     rcx, rdi; this
0x1800a7df7  call    ?DecodeRsp@TPMW8_COMMAND@tpm12class@@UEAAJPEAG@Z; tpm12class::TPMW8_COMMAND::DecodeRsp(ushort *)
0x1800a7dfc  mov     ebx, eax
0x1800a7dfe  test    eax, eax
0x1800a7e00  js      loc_1800A8513
0x1800a7e06  lea     rcx, aTpm2Getcapabil; "--TPM2_GetCapability: Parameters-------"...
0x1800a7e0d  call    ?TraceDirect@@YAJPEAG@Z; TraceDirect(ushort *)
0x1800a7e12  mov     ebx, eax
0x1800a7e14  test    eax, eax
0x1800a7e16  js      loc_1800A8513
0x1800a7e1c  mov     r8b, [rdi+0CCh]; unsigned __int8
0x1800a7e23  lea     rax, ?st_TPMW8I_YES_NO@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8I_YES_NO
0x1800a7e2a  mov     [rsp+270h+var_248], r13b; char
0x1800a7e2f  lea     rdx, aMoredata; "moreData"
0x1800a7e36  mov     rcx, rsi; unsigned __int16 *
0x1800a7e39  mov     [rsp+270h+var_250], rax; struct TPM_SYMBOLTABLE_ENTRY *
0x1800a7e3e  call    ?TraceUINT8Value@@YAJPEAG0EEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT8Value(ushort *,ushort *,uchar,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800a7e43  mov     ebx, eax
0x1800a7e45  test    eax, eax
0x1800a7e47  js      loc_1800A8513
0x1800a7e4d  mov     r8d, [rdi+0D0h]; unsigned int
0x1800a7e54  lea     rax, ?st_TPMW8_CAP@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_CAP
0x1800a7e5b  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x1800a7e60  lea     rdx, aCapability; "capability"
0x1800a7e67  xor     r9d, r9d; unsigned __int8
0x1800a7e6a  mov     [rsp+270h+var_250], rax; struct TPM_SYMBOLTABLE_ENTRY *
0x1800a7e6f  mov     rcx, rsi; unsigned __int16 *
0x1800a7e72  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800a7e77  mov     ebx, eax
0x1800a7e79  test    eax, eax
0x1800a7e7b  js      loc_1800A8513
0x1800a7e81  cmp     dword ptr [rdi+0D0h], 100h
0x1800a7e8b  lea     r12d, [r13+1]
0x1800a7e8f  jz      short loc_1800A7EBE
0x1800a7e91  mov     r8d, [rdi+0D4h]; unsigned int
0x1800a7e98  lea     rdx, aCount; "count"
0x1800a7e9f  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x1800a7ea4  mov     r9b, r12b; unsigned __int8
0x1800a7ea7  mov     rcx, rsi; unsigned __int16 *
0x1800a7eaa  mov     [rsp+270h+var_250], r13; struct TPM_SYMBOLTABLE_ENTRY *
0x1800a7eaf  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800a7eb4  mov     ebx, eax
0x1800a7eb6  test    eax, eax
0x1800a7eb8  js      loc_1800A8513
0x1800a7ebe  mov     eax, [rdi+0D0h]
0x1800a7ec4  cmp     eax, 5
0x1800a7ec7  ja      loc_1800A8220
0x1800a7ecd  jz      loc_1800A81A0
0x1800a7ed3  test    eax, eax
0x1800a7ed5  jz      loc_1800A80E7
0x1800a7edb  sub     eax, r12d
0x1800a7ede  jz      loc_1800A806D
0x1800a7ee4  sub     eax, r12d
0x1800a7ee7  jz      loc_1800A7FF3
0x1800a7eed  sub     eax, r12d
0x1800a7ef0  jz      loc_1800A7F79
0x1800a7ef6  cmp     eax, r12d
0x1800a7ef9  jnz     loc_1800A8247
0x1800a7eff  mov     r14d, r13d
0x1800a7f02  lea     r15, ?st_TPMW8_CC@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_CC
0x1800a7f09  cmp     r14d, [rdi+0D4h]
0x1800a7f10  jnb     loc_1800A8513
0x1800a7f16  mov     r9, rsi
0x1800a7f19  mov     dword ptr [rsp+270h+var_250], r14d
0x1800a7f1e  lea     r8, aSauditcommands; "%sauditCommands[%d]."
0x1800a7f25  mov     edx, 100h; unsigned __int64
0x1800a7f2a  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800a7f2f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a7f34  mov     ebx, eax
0x1800a7f36  test    eax, eax
0x1800a7f38  js      loc_1800A8513
0x1800a7f3e  mov     r8, [rdi+0F8h]
0x1800a7f45  lea     rdx, aCommandcode; "commandCode"
0x1800a7f4c  mov     eax, r14d
0x1800a7f4f  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800a7f54  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x1800a7f59  xor     r9d, r9d; unsigned __int8
0x1800a7f5c  mov     [rsp+270h+var_250], r15; struct TPM_SYMBOLTABLE_ENTRY *
0x1800a7f61  mov     r8d, [r8+rax*4]; unsigned int
0x1800a7f65  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800a7f6a  mov     ebx, eax
0x1800a7f6c  test    eax, eax
0x1800a7f6e  js      loc_1800A8513
0x1800a7f74  add     r14d, r12d
0x1800a7f77  jmp     short loc_1800A7F09
0x1800a7f79  mov     r14d, r13d
0x1800a7f7c  lea     r15, ?st_TPMW8_CC@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_CC
0x1800a7f83  cmp     r14d, [rdi+0D4h]
0x1800a7f8a  jnb     loc_1800A8513
0x1800a7f90  mov     r9, rsi
0x1800a7f93  mov     dword ptr [rsp+270h+var_250], r14d
0x1800a7f98  lea     r8, aSppcommandsD; "%sppCommands[%d]."
0x1800a7f9f  mov     edx, 100h; unsigned __int64
0x1800a7fa4  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800a7fa9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a7fae  mov     ebx, eax
0x1800a7fb0  test    eax, eax
0x1800a7fb2  js      loc_1800A8513
0x1800a7fb8  mov     r8, [rdi+0F0h]
0x1800a7fbf  lea     rdx, aCommandcode; "commandCode"
0x1800a7fc6  mov     eax, r14d
0x1800a7fc9  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800a7fce  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x1800a7fd3  xor     r9d, r9d; unsigned __int8
0x1800a7fd6  mov     [rsp+270h+var_250], r15; struct TPM_SYMBOLTABLE_ENTRY *
0x1800a7fdb  mov     r8d, [r8+rax*4]; unsigned int
0x1800a7fdf  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800a7fe4  mov     ebx, eax
0x1800a7fe6  test    eax, eax
0x1800a7fe8  js      loc_1800A8513
0x1800a7fee  add     r14d, r12d
0x1800a7ff1  jmp     short loc_1800A7F83
0x1800a7ff3  mov     r14d, r13d
0x1800a7ff6  lea     r15, ?st_TPMW8_CC@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_CC
0x1800a7ffd  cmp     r14d, [rdi+0D4h]
0x1800a8004  jnb     loc_1800A8513
0x1800a800a  mov     r9, rsi
0x1800a800d  mov     dword ptr [rsp+270h+var_250], r14d
0x1800a8012  lea     r8, aScommandsD; "%scommands[%d]."
0x1800a8019  mov     edx, 100h; unsigned __int64
0x1800a801e  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800a8023  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a8028  mov     ebx, eax
0x1800a802a  test    eax, eax
0x1800a802c  js      loc_1800A8513
0x1800a8032  mov     r8, [rdi+0E8h]
0x1800a8039  lea     rdx, aCommandcode; "commandCode"
0x1800a8040  mov     eax, r14d
0x1800a8043  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800a8048  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x1800a804d  xor     r9d, r9d; unsigned __int8
0x1800a8050  mov     [rsp+270h+var_250], r15; struct TPM_SYMBOLTABLE_ENTRY *
0x1800a8055  mov     r8d, [r8+rax*4]; unsigned int
0x1800a8059  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800a805e  mov     ebx, eax
0x1800a8060  test    eax, eax
0x1800a8062  js      loc_1800A8513
0x1800a8068  add     r14d, r12d
0x1800a806b  jmp     short loc_1800A7FFD
0x1800a806d  mov     r14d, r13d
0x1800a8070  cmp     r14d, [rdi+0D4h]
0x1800a8077  jnb     loc_1800A8513
0x1800a807d  mov     r9, rsi
0x1800a8080  mov     dword ptr [rsp+270h+var_250], r14d
0x1800a8085  lea     r8, aShandlesD; "%shandles[%d]."
0x1800a808c  mov     edx, 100h; unsigned __int64
0x1800a8091  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800a8096  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a809b  mov     ebx, eax
0x1800a809d  test    eax, eax
0x1800a809f  js      loc_1800A8513
0x1800a80a5  mov     r8, [rdi+0E0h]
0x1800a80ac  lea     rcx, ?st_TPMW8_RH@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_RH
0x1800a80b3  mov     eax, r14d
0x1800a80b6  lea     rdx, aHandle; "handle"
0x1800a80bd  mov     [rsp+270h+var_248], r12b; unsigned __int8
0x1800a80c2  xor     r9d, r9d; unsigned __int8
0x1800a80c5  mov     [rsp+270h+var_250], rcx; struct TPM_SYMBOLTABLE_ENTRY *
0x1800a80ca  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800a80cf  mov     r8d, [r8+rax*4]; unsigned int
0x1800a80d3  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800a80d8  mov     ebx, eax
0x1800a80da  test    eax, eax
0x1800a80dc  js      loc_1800A8513
0x1800a80e2  add     r14d, r12d
0x1800a80e5  jmp     short loc_1800A8070
0x1800a80e7  mov     r14d, r13d
0x1800a80ea  lea     r15, ?st_TPMW8_ALG@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_ALG
0x1800a80f1  cmp     r14d, [rdi+0D4h]
0x1800a80f8  jnb     loc_1800A8513
0x1800a80fe  mov     r9, rsi
0x1800a8101  mov     dword ptr [rsp+270h+var_250], r14d
0x1800a8106  lea     r8, aSalgorithmsD; "%salgorithms[%d]."
0x1800a810d  mov     edx, 100h; unsigned __int64
0x1800a8112  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800a8117  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a811c  mov     ebx, eax
0x1800a811e  test    eax, eax
0x1800a8120  js      loc_1800A8513
0x1800a8126  mov     r8, [rdi+0D8h]
0x1800a812d  lea     rdx, aAlg; "alg"
0x1800a8134  mov     r12d, r14d
0x1800a8137  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800a813c  mov     [rsp+270h+var_248], r13b; char
0x1800a8141  xor     r9d, r9d; unsigned __int8
0x1800a8144  mov     [rsp+270h+var_250], r15; struct TPM_SYMBOLTABLE_ENTRY *
0x1800a8149  movzx   r8d, word ptr [r8+r12*8]; unsigned __int16
0x1800a814e  call    ?TraceUINT16Value@@YAJPEAG0GEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT16Value(ushort *,ushort *,ushort,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800a8153  mov     ebx, eax
0x1800a8155  test    eax, eax
0x1800a8157  js      loc_1800A8513
0x1800a815d  mov     rax, [rdi+0D8h]
0x1800a8164  lea     rdx, aAlg; "alg"
0x1800a816b  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x1800a8170  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800a8175  xor     r9d, r9d; unsigned __int8
0x1800a8178  movzx   r8d, word ptr [rax+r12*8]; unsigned int
0x1800a817d  lea     rax, ?st_TPMW8A_ALGORITHM@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8A_ALGORITHM
0x1800a8184  mov     [rsp+270h+var_250], rax; struct TPM_SYMBOLTABLE_ENTRY *
0x1800a8189  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800a818e  mov     ebx, eax
0x1800a8190  test    eax, eax
0x1800a8192  js      loc_1800A8513
0x1800a8198  inc     r14d
0x1800a819b  jmp     loc_1800A80F1
0x1800a81a0  mov     r14d, r13d
0x1800a81a3  lea     r15, ?st_TPMW8_ALG@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_ALG
0x1800a81aa  cmp     r14d, [rdi+0D4h]
0x1800a81b1  jnb     loc_1800A8513
0x1800a81b7  mov     r9, rsi
0x1800a81ba  mov     dword ptr [rsp+270h+var_250], r14d
0x1800a81bf  lea     r8, aSpcrsD; "%spcrs[%d]."
0x1800a81c6  mov     edx, 100h; unsigned __int64
0x1800a81cb  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800a81d0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a81d5  mov     ebx, eax
0x1800a81d7  test    eax, eax
0x1800a81d9  js      loc_1800A8513
0x1800a81df  mov     eax, r14d
0x1800a81e2  lea     rdx, aHashalg; "hashAlg"
0x1800a81e9  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x1800a81ee  xor     r9d, r9d; unsigned __int8
0x1800a81f1  mov     [rsp+270h+var_250], r15; struct TPM_SYMBOLTABLE_ENTRY *
0x1800a81f6  lea     rcx, [rax+rax*8]
0x1800a81fa  mov     rax, [rdi+100h]
0x1800a8201  movzx   r8d, word ptr [rax+rcx*8+38h]; unsigned int
0x1800a8207  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800a820c  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800a8211  mov     ebx, eax
0x1800a8213  test    eax, eax
0x1800a8215  js      loc_1800A8513
0x1800a821b  add     r14d, r12d
0x1800a821e  jmp     short loc_1800A81AA
0x1800a8220  sub     eax, 6
0x1800a8223  jz      loc_1800A8466
0x1800a8229  sub     eax, r12d
0x1800a822c  jz      loc_1800A83B9
0x1800a8232  sub     eax, r12d
0x1800a8235  jz      loc_1800A833E
0x1800a823b  sub     eax, r12d
0x1800a823e  jz      short loc_1800A8298
0x1800a8240  cmp     eax, 0F7h
0x1800a8245  jz      short loc_1800A8251
0x1800a8247  mov     eax, 80004001h
0x1800a824c  jmp     loc_1800A8515
0x1800a8251  mov     r9, rsi
0x1800a8254  lea     r8, aSvendorpropert; "%svendorProperties."
0x1800a825b  mov     edx, 100h; unsigned __int64
0x1800a8260  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800a8265  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a826a  mov     ebx, eax
0x1800a826c  test    eax, eax
0x1800a826e  js      loc_1800A8513
0x1800a8274  mov     r9d, [rdi+130h]; unsigned int
0x1800a827b  lea     rdx, aVendorspecific_1; "vendorSpecificData"
0x1800a8282  mov     r8, [rdi+128h]; unsigned __int8 *
0x1800a8289  mov     rcx, rsi; unsigned __int16 *
0x1800a828c  call    ?TraceBufferValue@@YAJPEAG0PEAEI@Z; TraceBufferValue(ushort *,ushort *,uchar *,uint)
0x1800a8291  mov     ebx, eax
0x1800a8293  jmp     loc_1800A8513
0x1800a8298  mov     r14d, r13d
0x1800a829b  cmp     r14d, [rdi+0D4h]
0x1800a82a2  jnb     loc_1800A8513
0x1800a82a8  mov     r9, rsi
0x1800a82ab  mov     dword ptr [rsp+270h+var_250], r14d
0x1800a82b0  lea     r8, aSauthpoliciesD; "%sauthPolicies[%d]."
0x1800a82b7  mov     edx, 100h; unsigned __int64
0x1800a82bc  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1800a82c1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a82c6  mov     ebx, eax
0x1800a82c8  test    eax, eax
0x1800a82ca  js      loc_1800A8513
0x1800a82d0  mov     r8, [rdi+120h]
0x1800a82d7  lea     rdx, aHandle; "handle"
  ... truncated ...
```
