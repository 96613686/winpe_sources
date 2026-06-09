# CMetadataPngItxtReaderWriter::SetValue(uint,tagPROPVARIANT const *)

- ea: `0x1800bbec0`
- end: `0x1800bc283`
- name: `?SetValue@CMetadataPngItxtReaderWriter@@MEAAJIPEBUtagPROPVARIANT@@@Z`
- size: `963`
- prototype: `__int64 __fastcall(CMetadataPngItxtReaderWriter *__hidden this, unsigned int, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c6800`

## callees

- `0x18003573c`
- `0x180042ae8`
- `0x18004f894`
- `0x180064b00`
- `0x1800931e0`
- `0x180093784`
- `0x1800a5864`
- `0x1800bbec0`
- `0x1800bd9d4`
- `0x1800c6800`
- `0x1800c68e0`
- `0x1800c7288`
- `0x1801b1550`
- `0x1801b15f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bbfb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bc0a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bc15f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bc20c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bbfb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bc0a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bc15f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bc20c`

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
0x1800bbec0  mov     [rsp-28h+arg_0], rbx
0x1800bbec5  mov     [rsp-28h+arg_8], rsi
0x1800bbeca  push    rbp
0x1800bbecb  push    rdi
0x1800bbecc  push    r12
0x1800bbece  push    r14
0x1800bbed0  push    r15
0x1800bbed2  mov     rbp, rsp
0x1800bbed5  sub     rsp, 20h
0x1800bbed9  xor     r12d, r12d
0x1800bbedc  mov     rsi, r8
0x1800bbedf  mov     [rbp+pullResult], r12
0x1800bbee3  mov     rdi, rcx
0x1800bbee6  mov     ebx, r12d
0x1800bbee9  sub     edx, 1
0x1800bbeec  jz      loc_1800BC1C9
0x1800bbef2  sub     edx, 1
0x1800bbef5  jz      loc_1800BC1B2
0x1800bbefb  sub     edx, 1
0x1800bbefe  jz      loc_1800BC0F2
0x1800bbf04  sub     edx, 1
0x1800bbf07  jz      loc_1800BC009
0x1800bbf0d  sub     edx, 1
0x1800bbf10  jz      short loc_1800BBF38
0x1800bbf12  cmp     edx, 1
0x1800bbf15  jz      short loc_1800BBF21
0x1800bbf17  mov     ebx, 80070057h
0x1800bbf1c  jmp     loc_1800BC229
0x1800bbf21  mov     rdx, rsi; struct tagPROPVARIANT *
0x1800bbf24  call    ?SetEmbeddedXMP@CMetadataPngItxtReaderWriter@@IEAAJPEBUtagPROPVARIANT@@@Z; CMetadataPngItxtReaderWriter::SetEmbeddedXMP(tagPROPVARIANT const *)
0x1800bbf29  mov     ebx, eax
0x1800bbf2b  test    eax, eax
0x1800bbf2d  jns     loc_1800BC269
0x1800bbf33  jmp     loc_1800BC083
0x1800bbf38  mov     rcx, [r8+8]; unsigned __int16 *
0x1800bbf3c  test    rcx, rcx
0x1800bbf3f  jnz     short loc_1800BBF4E
0x1800bbf41  mov     rcx, rdi; this
0x1800bbf44  call    ?ClearText@CMetadataPngItxtReaderWriter@@IEAAXXZ; CMetadataPngItxtReaderWriter::ClearText(void)
0x1800bbf49  jmp     loc_1800BC269
0x1800bbf4e  lea     r8, [rbp+pullResult]; unsigned __int64 *
0x1800bbf52  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800bbf57  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800bbf5c  mov     r9d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800bbf63  mov     ebx, eax
0x1800bbf65  test    eax, eax
0x1800bbf67  jns     short loc_1800BBF7A
0x1800bbf69  test    r9d, r9d
0x1800bbf6c  jnz     loc_1800BC090
0x1800bbf72  test    eax, eax
0x1800bbf74  js      loc_1800BC269
0x1800bbf7a  mov     r14, [rbp+pullResult]
0x1800bbf7e  test    r14, r14
0x1800bbf81  jz      short loc_1800BBF41
0x1800bbf83  lea     r8, [rbp+pullResult]; pullResult
0x1800bbf87  mov     [rbp+pullResult], r12
0x1800bbf8b  mov     edx, 2; ullMultiplier
0x1800bbf90  lea     rcx, [r14+1]; ullMultiplicand
0x1800bbf94  call    ULongLongMult
0x1800bbf99  test    eax, eax
0x1800bbf9b  jns     short loc_1800BBFAA
0x1800bbf9d  mov     ebx, 80070216h
0x1800bbfa2  test    r9d, r9d
0x1800bbfa5  jmp     loc_1800BC230
0x1800bbfaa  mov     rcx, rdi; this
0x1800bbfad  call    ?ClearText@CMetadataPngItxtReaderWriter@@IEAAXXZ; CMetadataPngItxtReaderWriter::ClearText(void)
0x1800bbfb2  mov     rcx, [rbp+pullResult]; cb
0x1800bbfb6  call    cs:__imp_CoTaskMemAlloc
0x1800bbfbd  nop     dword ptr [rax+rax+00h]
0x1800bbfc2  mov     [rdi+0D0h], rax
0x1800bbfc9  test    rax, rax
0x1800bbfcc  jz      loc_1800BC224
0x1800bbfd2  mov     r8, [rsi+8]; unsigned __int16 *
0x1800bbfd6  lea     rdx, [r14+1]; unsigned __int64
0x1800bbfda  mov     rcx, rax; unsigned __int16 *
0x1800bbfdd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800bbfe2  mov     ebx, eax
0x1800bbfe4  test    eax, eax
0x1800bbfe6  jns     short loc_1800BBFFD
0x1800bbfe8  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800bbfef  jnz     loc_1800BC090
0x1800bbff5  test    eax, eax
0x1800bbff7  js      loc_1800BC269
0x1800bbffd  mov     [rdi+0D8h], r14
0x1800bc004  jmp     loc_1800BC269
0x1800bc009  mov     rcx, [r8+8]; unsigned __int16 *
0x1800bc00d  test    rcx, rcx
0x1800bc010  jnz     short loc_1800BC01F
0x1800bc012  mov     rcx, rdi; this
0x1800bc015  call    ?ClearTranslatedKey@CMetadataPngItxtReaderWriter@@IEAAXXZ; CMetadataPngItxtReaderWriter::ClearTranslatedKey(void)
0x1800bc01a  jmp     loc_1800BC269
0x1800bc01f  lea     r8, [rbp+pullResult]; unsigned __int64 *
0x1800bc023  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800bc028  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800bc02d  mov     r9d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800bc034  mov     ebx, eax
0x1800bc036  test    eax, eax
0x1800bc038  jns     short loc_1800BC047
0x1800bc03a  test    r9d, r9d
0x1800bc03d  jnz     short loc_1800BC090
0x1800bc03f  test    eax, eax
0x1800bc041  js      loc_1800BC269
0x1800bc047  mov     r14, [rbp+pullResult]
0x1800bc04b  test    r14, r14
0x1800bc04e  jz      short loc_1800BC012
0x1800bc050  lea     r8, [rbp+pullResult]; pullResult
0x1800bc054  mov     [rbp+pullResult], r12
0x1800bc058  mov     edx, 2; ullMultiplier
0x1800bc05d  lea     rcx, [r14+1]; ullMultiplicand
0x1800bc061  call    ULongLongMult
0x1800bc066  test    eax, eax
0x1800bc068  js      loc_1800BBF9D
0x1800bc06e  mov     rdx, [rsi+8]; unsigned __int16 *
0x1800bc072  mov     r8, r14; unsigned __int64
0x1800bc075  mov     rcx, rdi; this
0x1800bc078  call    ?HrCheckTranslatedKey@CMetadataPngItxtReaderWriter@@MEAAJPEAG_K@Z; CMetadataPngItxtReaderWriter::HrCheckTranslatedKey(ushort *,unsigned __int64)
0x1800bc07d  mov     ebx, eax
0x1800bc07f  test    eax, eax
0x1800bc081  jns     short loc_1800BC097
0x1800bc083  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800bc08a  jz      loc_1800BC269
0x1800bc090  mov     ecx, eax
0x1800bc092  jmp     loc_1800BC234
0x1800bc097  mov     rcx, rdi; this
0x1800bc09a  call    ?ClearTranslatedKey@CMetadataPngItxtReaderWriter@@IEAAXXZ; CMetadataPngItxtReaderWriter::ClearTranslatedKey(void)
0x1800bc09f  mov     rcx, [rbp+pullResult]; cb
0x1800bc0a3  call    cs:__imp_CoTaskMemAlloc
0x1800bc0aa  nop     dword ptr [rax+rax+00h]
0x1800bc0af  mov     [rdi+0C0h], rax
0x1800bc0b6  test    rax, rax
0x1800bc0b9  jz      loc_1800BC224
0x1800bc0bf  mov     r8, [rsi+8]; unsigned __int16 *
0x1800bc0c3  lea     rdx, [r14+1]; unsigned __int64
0x1800bc0c7  mov     rcx, rax; unsigned __int16 *
0x1800bc0ca  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800bc0cf  mov     ebx, eax
0x1800bc0d1  test    eax, eax
0x1800bc0d3  jns     short loc_1800BC0E6
0x1800bc0d5  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800bc0dc  jnz     short loc_1800BC090
0x1800bc0de  test    eax, eax
0x1800bc0e0  js      loc_1800BC269
0x1800bc0e6  mov     [rdi+0C8h], r14
0x1800bc0ed  jmp     loc_1800BC269
0x1800bc0f2  mov     rcx, [r8+8]; char *
0x1800bc0f6  test    rcx, rcx
0x1800bc0f9  jnz     short loc_1800BC108
0x1800bc0fb  mov     rcx, rdi; this
0x1800bc0fe  call    ?ClearLanguageTag@CMetadataPngItxtReaderWriter@@IEAAXXZ; CMetadataPngItxtReaderWriter::ClearLanguageTag(void)
0x1800bc103  jmp     loc_1800BC269
0x1800bc108  lea     r8, [rbp+pullResult]; unsigned __int64 *
0x1800bc10c  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800bc111  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x1800bc116  mov     ebx, eax
0x1800bc118  test    eax, eax
0x1800bc11a  jns     short loc_1800BC131
0x1800bc11c  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800bc123  jnz     loc_1800BC090
0x1800bc129  test    eax, eax
0x1800bc12b  js      loc_1800BC269
0x1800bc131  mov     r14, [rbp+pullResult]
0x1800bc135  mov     rcx, rdi; this
0x1800bc138  test    r14, r14
0x1800bc13b  jz      short loc_1800BC0FE
0x1800bc13d  mov     rdx, [rsi+8]; char *
0x1800bc141  mov     r8, r14; unsigned __int64
0x1800bc144  call    ?HrCheckLanguageTag@CMetadataPngItxtReaderWriter@@MEAAJPEAD_K@Z; CMetadataPngItxtReaderWriter::HrCheckLanguageTag(char *,unsigned __int64)
0x1800bc149  mov     ebx, eax
0x1800bc14b  test    eax, eax
0x1800bc14d  js      loc_1800BC083
0x1800bc153  mov     rcx, rdi; this
0x1800bc156  call    ?ClearLanguageTag@CMetadataPngItxtReaderWriter@@IEAAXXZ; CMetadataPngItxtReaderWriter::ClearLanguageTag(void)
0x1800bc15b  lea     rcx, [r14+1]; cb
0x1800bc15f  call    cs:__imp_CoTaskMemAlloc
0x1800bc166  nop     dword ptr [rax+rax+00h]
0x1800bc16b  mov     [rdi+0B0h], rax
0x1800bc172  test    rax, rax
0x1800bc175  jz      loc_1800BC224
0x1800bc17b  mov     r8, [rsi+8]; char *
0x1800bc17f  lea     rdx, [r14+1]; unsigned __int64
0x1800bc183  mov     rcx, rax; char *
0x1800bc186  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800bc18b  mov     ebx, eax
0x1800bc18d  test    eax, eax
0x1800bc18f  jns     short loc_1800BC1A6
0x1800bc191  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800bc198  jnz     loc_1800BC090
0x1800bc19e  test    eax, eax
0x1800bc1a0  js      loc_1800BC269
0x1800bc1a6  mov     [rdi+0B8h], r14
0x1800bc1ad  jmp     loc_1800BC269
0x1800bc1b2  mov     al, [r8+8]
0x1800bc1b6  cmp     al, 2
0x1800bc1b8  jnb     loc_1800BBF17
0x1800bc1be  mov     [rcx+0A8h], al
0x1800bc1c4  jmp     loc_1800BC269
0x1800bc1c9  mov     rcx, [r8+8]; char *
0x1800bc1cd  test    rcx, rcx
0x1800bc1d0  jz      loc_1800BBF17
0x1800bc1d6  lea     r8, [rbp+pullResult]; unsigned __int64 *
0x1800bc1da  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800bc1df  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x1800bc1e4  mov     ebx, eax
0x1800bc1e6  test    eax, eax
0x1800bc1e8  js      loc_1800BC083
0x1800bc1ee  mov     r14, [rbp+pullResult]
0x1800bc1f2  lea     rax, [r14-1]
0x1800bc1f6  cmp     rax, 4Eh ; 'N'
0x1800bc1fa  ja      loc_1800BBF17
0x1800bc200  mov     rcx, rdi; this
0x1800bc203  call    ?ClearKey@CMetadataPngItxtReaderWriter@@IEAAXXZ; CMetadataPngItxtReaderWriter::ClearKey(void)
0x1800bc208  lea     rcx, [r14+1]; cb
0x1800bc20c  call    cs:__imp_CoTaskMemAlloc
0x1800bc213  nop     dword ptr [rax+rax+00h]
0x1800bc218  mov     [rdi+98h], rax
0x1800bc21f  test    rax, rax
0x1800bc222  jnz     short loc_1800BC23B
0x1800bc224  mov     ebx, 8007000Eh
0x1800bc229  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800bc230  jz      short loc_1800BC269
0x1800bc232  mov     ecx, ebx; int
0x1800bc234  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800bc239  jmp     short loc_1800BC269
0x1800bc23b  mov     r8, [rsi+8]; char *
0x1800bc23f  lea     rdx, [r14+1]; unsigned __int64
0x1800bc243  mov     rcx, rax; char *
0x1800bc246  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800bc24b  mov     ebx, eax
0x1800bc24d  test    eax, eax
0x1800bc24f  jns     short loc_1800BC262
0x1800bc251  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800bc258  jnz     loc_1800BC090
0x1800bc25e  test    eax, eax
0x1800bc260  js      short loc_1800BC269
0x1800bc262  mov     [rdi+0A0h], r14
0x1800bc269  mov     rsi, [rsp+20h+arg_8]
0x1800bc26e  mov     eax, ebx
0x1800bc270  mov     rbx, [rsp+20h+arg_0]
0x1800bc275  add     rsp, 20h
0x1800bc279  pop     r15
0x1800bc27b  pop     r14
0x1800bc27d  pop     r12
0x1800bc27f  pop     rdi
0x1800bc280  pop     rbp
0x1800bc281  retn
```
