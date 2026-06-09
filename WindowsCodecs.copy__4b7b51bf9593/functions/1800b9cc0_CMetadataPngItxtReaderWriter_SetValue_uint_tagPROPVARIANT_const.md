# CMetadataPngItxtReaderWriter::SetValue(uint,tagPROPVARIANT const *)

- ea: `0x1800b9cc0`
- end: `0x1800ba06a`
- name: `?SetValue@CMetadataPngItxtReaderWriter@@MEAAJIPEBUtagPROPVARIANT@@@Z`
- size: `938`
- prototype: `__int64 __fastcall(CMetadataPngItxtReaderWriter *__hidden this, unsigned int, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c441c`

## callees

- `0x18001dd10`
- `0x180020e14`
- `0x180041dec`
- `0x180045650`
- `0x180067e88`
- `0x1800a7784`
- `0x1800a77c4`
- `0x1800b9cc0`
- `0x1800bb784`
- `0x1800c441c`
- `0x1800c44fc`
- `0x1800c4f58`
- `0x1801adf50`
- `0x1801adfe0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b9db6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b9e9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b9f53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b9ffa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b9db6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b9e9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b9f53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b9ffa`

## pseudocode

```c
__int64 __fastcall CMetadataPngItxtReaderWriter::SetValue(
        CMetadataPngItxtReaderWriter *this,
        int a2,
        const struct tagPROPVARIANT *a3)
{
  unsigned int v5; // ebx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // eax
  const unsigned __int16 *v12; // rcx
  ULONGLONG v13; // r14
  int v14; // r9d
  bool v15; // zf
  unsigned __int16 *v16; // rax
  const unsigned __int16 *bstrVal; // rcx
  ULONGLONG v18; // r14
  int v19; // ecx
  unsigned __int16 *v20; // rax
  const char *v21; // rcx
  CMetadataPngItxtReaderWriter *v22; // rcx
  ULONGLONG v23; // r14
  char *v24; // rax
  CHAR cVal; // al
  const char *pszVal; // rcx
  ULONGLONG v27; // r14
  char *v28; // rax
  ULONGLONG pullResult; // [rsp+68h] [rbp+48h] BYREF

  pullResult = 0;
  v5 = 0;
  v6 = a2 - 1;
  if ( !v6 )
  {
    pszVal = a3->pszVal;
    if ( !pszVal )
      goto LABEL_7;
    v11 = StringCchLengthA(pszVal, 0x7FFFFFFFu, &pullResult);
    v5 = v11;
    if ( v11 < 0 )
      goto LABEL_31;
    v27 = pullResult;
    if ( pullResult - 1 > 0x4E )
      goto LABEL_7;
    CMetadataPngItxtReaderWriter::ClearKey(this);
    v28 = (char *)CoTaskMemAlloc(v27 + 1);
    *((_QWORD *)this + 19) = v28;
    if ( v28 )
    {
      v11 = StringCchCopyA(v28, v27 + 1, a3->pszVal);
      v5 = v11;
      if ( v11 >= 0 )
      {
        *((_QWORD *)this + 20) = v27;
        return v5;
      }
      if ( !(_DWORD)g_doStackCaptures )
        return v5;
      goto LABEL_32;
    }
    goto LABEL_57;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    cVal = a3->cVal;
    if ( (unsigned __int8)cVal < 2u )
    {
      *((_BYTE *)this + 168) = cVal;
      return v5;
    }
    goto LABEL_7;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    v21 = a3->pszVal;
    if ( v21 )
    {
      v11 = StringCchLengthA(v21, 0x7FFFFFFFu, &pullResult);
      v5 = v11;
      if ( v11 < 0 )
      {
        if ( !(_DWORD)g_doStackCaptures )
          return v5;
        goto LABEL_32;
      }
      v23 = pullResult;
      v22 = this;
      if ( pullResult )
      {
        v11 = CMetadataPngItxtReaderWriter::HrCheckLanguageTag(this, a3->pszVal, pullResult);
        v5 = v11;
        if ( v11 >= 0 )
        {
          CMetadataPngItxtReaderWriter::ClearLanguageTag(this);
          v24 = (char *)CoTaskMemAlloc(v23 + 1);
          *((_QWORD *)this + 22) = v24;
          if ( v24 )
          {
            v11 = StringCchCopyA(v24, v23 + 1, a3->pszVal);
            v5 = v11;
            if ( v11 >= 0 )
            {
              *((_QWORD *)this + 23) = v23;
              return v5;
            }
            if ( !(_DWORD)g_doStackCaptures )
              return v5;
            goto LABEL_32;
          }
          goto LABEL_57;
        }
        goto LABEL_31;
      }
    }
    else
    {
      v22 = this;
    }
    CMetadataPngItxtReaderWriter::ClearLanguageTag(v22);
    return v5;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    bstrVal = a3->bstrVal;
    if ( !bstrVal )
      goto LABEL_24;
    v11 = StringCchLengthW(bstrVal, 0x7FFFFFFFu, &pullResult);
    v5 = v11;
    if ( v11 < 0 )
    {
      if ( !(_DWORD)g_doStackCaptures )
        return v5;
      goto LABEL_32;
    }
    v18 = pullResult;
    if ( !pullResult )
    {
LABEL_24:
      CMetadataPngItxtReaderWriter::ClearTranslatedKey(this);
      return v5;
    }
    pullResult = 0;
    if ( ULongLongMult(v18 + 1, 2u, &pullResult) < 0 )
    {
LABEL_17:
      v5 = -2147024362;
      v15 = v14 == 0;
      goto LABEL_59;
    }
    v11 = CMetadataPngItxtReaderWriter::HrCheckTranslatedKey(this, a3->bstrVal, v18);
    v5 = v11;
    if ( v11 >= 0 )
    {
      CMetadataPngItxtReaderWriter::ClearTranslatedKey(this);
      v20 = (unsigned __int16 *)CoTaskMemAlloc(pullResult);
      *((_QWORD *)this + 24) = v20;
      if ( v20 )
      {
        v11 = StringCchCopyW(v20, v18 + 1, a3->bstrVal);
        v5 = v11;
        if ( v11 >= 0 )
        {
          *((_QWORD *)this + 25) = v18;
          return v5;
        }
        if ( !(_DWORD)g_doStackCaptures )
          return v5;
        goto LABEL_32;
      }
      goto LABEL_57;
    }
LABEL_31:
    if ( !(_DWORD)g_doStackCaptures )
      return v5;
    goto LABEL_32;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    v12 = a3->bstrVal;
    if ( !v12 )
      goto LABEL_11;
    v11 = StringCchLengthW(v12, 0x7FFFFFFFu, &pullResult);
    v5 = v11;
    if ( v11 < 0 )
    {
      if ( !(_DWORD)g_doStackCaptures )
        return v5;
      goto LABEL_32;
    }
    v13 = pullResult;
    if ( !pullResult )
    {
LABEL_11:
      CMetadataPngItxtReaderWriter::ClearText(this);
      return v5;
    }
    pullResult = 0;
    if ( ULongLongMult(v13 + 1, 2u, &pullResult) < 0 )
      goto LABEL_17;
    CMetadataPngItxtReaderWriter::ClearText(this);
    v16 = (unsigned __int16 *)CoTaskMemAlloc(pullResult);
    *((_QWORD *)this + 26) = v16;
    if ( v16 )
    {
      v11 = StringCchCopyW(v16, v13 + 1, a3->bstrVal);
      v5 = v11;
      if ( v11 >= 0 )
      {
        *((_QWORD *)this + 27) = v13;
        return v5;
      }
      if ( !(_DWORD)g_doStackCaptures )
        return v5;
LABEL_32:
      v19 = v11;
LABEL_61:
      DoStackCapture(v19);
      return v5;
    }
LABEL_57:
    v5 = -2147024882;
    goto LABEL_58;
  }
  if ( v10 == 1 )
  {
    v11 = CMetadataPngItxtReaderWriter::SetEmbeddedXMP(this, a3);
    v5 = v11;
    if ( v11 >= 0 )
      return v5;
    goto LABEL_31;
  }
LABEL_7:
  v5 = -2147024809;
LABEL_58:
  v15 = (_DWORD)g_doStackCaptures == 0;
LABEL_59:
  if ( !v15 )
  {
    v19 = v5;
    goto LABEL_61;
  }
  return v5;
}

```

## disassembly

```asm
0x1800b9cc0  mov     [rsp-28h+arg_0], rbx
0x1800b9cc5  mov     [rsp-28h+arg_8], rsi
0x1800b9cca  push    rbp
0x1800b9ccb  push    rdi
0x1800b9ccc  push    r12
0x1800b9cce  push    r14
0x1800b9cd0  push    r15
0x1800b9cd2  mov     rbp, rsp
0x1800b9cd5  sub     rsp, 20h
0x1800b9cd9  xor     r12d, r12d
0x1800b9cdc  mov     rsi, r8
0x1800b9cdf  mov     [rbp+pullResult], r12
0x1800b9ce3  mov     rdi, rcx
0x1800b9ce6  mov     ebx, r12d
0x1800b9ce9  sub     edx, 1
0x1800b9cec  jz      loc_1800B9FB7
0x1800b9cf2  sub     edx, 1
0x1800b9cf5  jz      loc_1800B9FA0
0x1800b9cfb  sub     edx, 1
0x1800b9cfe  jz      loc_1800B9EE6
0x1800b9d04  sub     edx, 1
0x1800b9d07  jz      loc_1800B9E03
0x1800b9d0d  sub     edx, 1
0x1800b9d10  jz      short loc_1800B9D38
0x1800b9d12  cmp     edx, 1
0x1800b9d15  jz      short loc_1800B9D21
0x1800b9d17  mov     ebx, 80070057h
0x1800b9d1c  jmp     loc_1800BA011
0x1800b9d21  mov     rdx, rsi; struct tagPROPVARIANT *
0x1800b9d24  call    ?SetEmbeddedXMP@CMetadataPngItxtReaderWriter@@IEAAJPEBUtagPROPVARIANT@@@Z; CMetadataPngItxtReaderWriter::SetEmbeddedXMP(tagPROPVARIANT const *)
0x1800b9d29  mov     ebx, eax
0x1800b9d2b  test    eax, eax
0x1800b9d2d  jns     loc_1800BA051
0x1800b9d33  jmp     loc_1800B9E7D
0x1800b9d38  mov     rcx, [r8+8]; unsigned __int16 *
0x1800b9d3c  test    rcx, rcx
0x1800b9d3f  jnz     short loc_1800B9D4E
0x1800b9d41  mov     rcx, rdi; this
0x1800b9d44  call    ?ClearText@CMetadataPngItxtReaderWriter@@IEAAXXZ; CMetadataPngItxtReaderWriter::ClearText(void)
0x1800b9d49  jmp     loc_1800BA051
0x1800b9d4e  lea     r8, [rbp+pullResult]; unsigned __int64 *
0x1800b9d52  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800b9d57  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800b9d5c  mov     r9d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800b9d63  mov     ebx, eax
0x1800b9d65  test    eax, eax
0x1800b9d67  jns     short loc_1800B9D7A
0x1800b9d69  test    r9d, r9d
0x1800b9d6c  jnz     loc_1800B9E8A
0x1800b9d72  test    eax, eax
0x1800b9d74  js      loc_1800BA051
0x1800b9d7a  mov     r14, [rbp+pullResult]
0x1800b9d7e  test    r14, r14
0x1800b9d81  jz      short loc_1800B9D41
0x1800b9d83  lea     r8, [rbp+pullResult]; pullResult
0x1800b9d87  mov     [rbp+pullResult], r12
0x1800b9d8b  mov     edx, 2; ullMultiplier
0x1800b9d90  lea     rcx, [r14+1]; ullMultiplicand
0x1800b9d94  call    ULongLongMult
0x1800b9d99  test    eax, eax
0x1800b9d9b  jns     short loc_1800B9DAA
0x1800b9d9d  mov     ebx, 80070216h
0x1800b9da2  test    r9d, r9d
0x1800b9da5  jmp     loc_1800BA018
0x1800b9daa  mov     rcx, rdi; this
0x1800b9dad  call    ?ClearText@CMetadataPngItxtReaderWriter@@IEAAXXZ; CMetadataPngItxtReaderWriter::ClearText(void)
0x1800b9db2  mov     rcx, [rbp+pullResult]; cb
0x1800b9db6  call    cs:__imp_CoTaskMemAlloc
0x1800b9dbc  mov     [rdi+0D0h], rax
0x1800b9dc3  test    rax, rax
0x1800b9dc6  jz      loc_1800BA00C
0x1800b9dcc  mov     r8, [rsi+8]; unsigned __int16 *
0x1800b9dd0  lea     rdx, [r14+1]; unsigned __int64
0x1800b9dd4  mov     rcx, rax; unsigned __int16 *
0x1800b9dd7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b9ddc  mov     ebx, eax
0x1800b9dde  test    eax, eax
0x1800b9de0  jns     short loc_1800B9DF7
0x1800b9de2  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800b9de9  jnz     loc_1800B9E8A
0x1800b9def  test    eax, eax
0x1800b9df1  js      loc_1800BA051
0x1800b9df7  mov     [rdi+0D8h], r14
0x1800b9dfe  jmp     loc_1800BA051
0x1800b9e03  mov     rcx, [r8+8]; unsigned __int16 *
0x1800b9e07  test    rcx, rcx
0x1800b9e0a  jnz     short loc_1800B9E19
0x1800b9e0c  mov     rcx, rdi; this
0x1800b9e0f  call    ?ClearTranslatedKey@CMetadataPngItxtReaderWriter@@IEAAXXZ; CMetadataPngItxtReaderWriter::ClearTranslatedKey(void)
0x1800b9e14  jmp     loc_1800BA051
0x1800b9e19  lea     r8, [rbp+pullResult]; unsigned __int64 *
0x1800b9e1d  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800b9e22  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800b9e27  mov     r9d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800b9e2e  mov     ebx, eax
0x1800b9e30  test    eax, eax
0x1800b9e32  jns     short loc_1800B9E41
0x1800b9e34  test    r9d, r9d
0x1800b9e37  jnz     short loc_1800B9E8A
0x1800b9e39  test    eax, eax
0x1800b9e3b  js      loc_1800BA051
0x1800b9e41  mov     r14, [rbp+pullResult]
0x1800b9e45  test    r14, r14
0x1800b9e48  jz      short loc_1800B9E0C
0x1800b9e4a  lea     r8, [rbp+pullResult]; pullResult
0x1800b9e4e  mov     [rbp+pullResult], r12
0x1800b9e52  mov     edx, 2; ullMultiplier
0x1800b9e57  lea     rcx, [r14+1]; ullMultiplicand
0x1800b9e5b  call    ULongLongMult
0x1800b9e60  test    eax, eax
0x1800b9e62  js      loc_1800B9D9D
0x1800b9e68  mov     rdx, [rsi+8]; unsigned __int16 *
0x1800b9e6c  mov     r8, r14; unsigned __int64
0x1800b9e6f  mov     rcx, rdi; this
0x1800b9e72  call    ?HrCheckTranslatedKey@CMetadataPngItxtReaderWriter@@MEAAJPEAG_K@Z; CMetadataPngItxtReaderWriter::HrCheckTranslatedKey(ushort *,unsigned __int64)
0x1800b9e77  mov     ebx, eax
0x1800b9e79  test    eax, eax
0x1800b9e7b  jns     short loc_1800B9E91
0x1800b9e7d  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800b9e84  jz      loc_1800BA051
0x1800b9e8a  mov     ecx, eax
0x1800b9e8c  jmp     loc_1800BA01C
0x1800b9e91  mov     rcx, rdi; this
0x1800b9e94  call    ?ClearTranslatedKey@CMetadataPngItxtReaderWriter@@IEAAXXZ; CMetadataPngItxtReaderWriter::ClearTranslatedKey(void)
0x1800b9e99  mov     rcx, [rbp+pullResult]; cb
0x1800b9e9d  call    cs:__imp_CoTaskMemAlloc
0x1800b9ea3  mov     [rdi+0C0h], rax
0x1800b9eaa  test    rax, rax
0x1800b9ead  jz      loc_1800BA00C
0x1800b9eb3  mov     r8, [rsi+8]; unsigned __int16 *
0x1800b9eb7  lea     rdx, [r14+1]; unsigned __int64
0x1800b9ebb  mov     rcx, rax; unsigned __int16 *
0x1800b9ebe  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b9ec3  mov     ebx, eax
0x1800b9ec5  test    eax, eax
0x1800b9ec7  jns     short loc_1800B9EDA
0x1800b9ec9  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800b9ed0  jnz     short loc_1800B9E8A
0x1800b9ed2  test    eax, eax
0x1800b9ed4  js      loc_1800BA051
0x1800b9eda  mov     [rdi+0C8h], r14
0x1800b9ee1  jmp     loc_1800BA051
0x1800b9ee6  mov     rcx, [r8+8]; char *
0x1800b9eea  test    rcx, rcx
0x1800b9eed  jnz     short loc_1800B9EFC
0x1800b9eef  mov     rcx, rdi; this
0x1800b9ef2  call    ?ClearLanguageTag@CMetadataPngItxtReaderWriter@@IEAAXXZ; CMetadataPngItxtReaderWriter::ClearLanguageTag(void)
0x1800b9ef7  jmp     loc_1800BA051
0x1800b9efc  lea     r8, [rbp+pullResult]; unsigned __int64 *
0x1800b9f00  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800b9f05  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x1800b9f0a  mov     ebx, eax
0x1800b9f0c  test    eax, eax
0x1800b9f0e  jns     short loc_1800B9F25
0x1800b9f10  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800b9f17  jnz     loc_1800B9E8A
0x1800b9f1d  test    eax, eax
0x1800b9f1f  js      loc_1800BA051
0x1800b9f25  mov     r14, [rbp+pullResult]
0x1800b9f29  mov     rcx, rdi; this
0x1800b9f2c  test    r14, r14
0x1800b9f2f  jz      short loc_1800B9EF2
0x1800b9f31  mov     rdx, [rsi+8]; char *
0x1800b9f35  mov     r8, r14; unsigned __int64
0x1800b9f38  call    ?HrCheckLanguageTag@CMetadataPngItxtReaderWriter@@MEAAJPEAD_K@Z; CMetadataPngItxtReaderWriter::HrCheckLanguageTag(char *,unsigned __int64)
0x1800b9f3d  mov     ebx, eax
0x1800b9f3f  test    eax, eax
0x1800b9f41  js      loc_1800B9E7D
0x1800b9f47  mov     rcx, rdi; this
0x1800b9f4a  call    ?ClearLanguageTag@CMetadataPngItxtReaderWriter@@IEAAXXZ; CMetadataPngItxtReaderWriter::ClearLanguageTag(void)
0x1800b9f4f  lea     rcx, [r14+1]; cb
0x1800b9f53  call    cs:__imp_CoTaskMemAlloc
0x1800b9f59  mov     [rdi+0B0h], rax
0x1800b9f60  test    rax, rax
0x1800b9f63  jz      loc_1800BA00C
0x1800b9f69  mov     r8, [rsi+8]; char *
0x1800b9f6d  lea     rdx, [r14+1]; unsigned __int64
0x1800b9f71  mov     rcx, rax; char *
0x1800b9f74  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800b9f79  mov     ebx, eax
0x1800b9f7b  test    eax, eax
0x1800b9f7d  jns     short loc_1800B9F94
0x1800b9f7f  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800b9f86  jnz     loc_1800B9E8A
0x1800b9f8c  test    eax, eax
0x1800b9f8e  js      loc_1800BA051
0x1800b9f94  mov     [rdi+0B8h], r14
0x1800b9f9b  jmp     loc_1800BA051
0x1800b9fa0  mov     al, [r8+8]
0x1800b9fa4  cmp     al, 2
0x1800b9fa6  jnb     loc_1800B9D17
0x1800b9fac  mov     [rcx+0A8h], al
0x1800b9fb2  jmp     loc_1800BA051
0x1800b9fb7  mov     rcx, [r8+8]; char *
0x1800b9fbb  test    rcx, rcx
0x1800b9fbe  jz      loc_1800B9D17
0x1800b9fc4  lea     r8, [rbp+pullResult]; unsigned __int64 *
0x1800b9fc8  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800b9fcd  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x1800b9fd2  mov     ebx, eax
0x1800b9fd4  test    eax, eax
0x1800b9fd6  js      loc_1800B9E7D
0x1800b9fdc  mov     r14, [rbp+pullResult]
0x1800b9fe0  lea     rax, [r14-1]
0x1800b9fe4  cmp     rax, 4Eh ; 'N'
0x1800b9fe8  ja      loc_1800B9D17
0x1800b9fee  mov     rcx, rdi; this
0x1800b9ff1  call    ?ClearKey@CMetadataPngItxtReaderWriter@@IEAAXXZ; CMetadataPngItxtReaderWriter::ClearKey(void)
0x1800b9ff6  lea     rcx, [r14+1]; cb
0x1800b9ffa  call    cs:__imp_CoTaskMemAlloc
0x1800ba000  mov     [rdi+98h], rax
0x1800ba007  test    rax, rax
0x1800ba00a  jnz     short loc_1800BA023
0x1800ba00c  mov     ebx, 8007000Eh
0x1800ba011  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800ba018  jz      short loc_1800BA051
0x1800ba01a  mov     ecx, ebx; int
0x1800ba01c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800ba021  jmp     short loc_1800BA051
0x1800ba023  mov     r8, [rsi+8]; char *
0x1800ba027  lea     rdx, [r14+1]; unsigned __int64
0x1800ba02b  mov     rcx, rax; char *
0x1800ba02e  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800ba033  mov     ebx, eax
0x1800ba035  test    eax, eax
0x1800ba037  jns     short loc_1800BA04A
0x1800ba039  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800ba040  jnz     loc_1800B9E8A
0x1800ba046  test    eax, eax
0x1800ba048  js      short loc_1800BA051
0x1800ba04a  mov     [rdi+0A0h], r14
0x1800ba051  mov     rsi, [rsp+20h+arg_8]
0x1800ba056  mov     eax, ebx
0x1800ba058  mov     rbx, [rsp+20h+arg_0]
0x1800ba05d  add     rsp, 20h
0x1800ba061  pop     r15
0x1800ba063  pop     r14
0x1800ba065  pop     r12
0x1800ba067  pop     rdi
0x1800ba068  pop     rbp
0x1800ba069  retn
```
