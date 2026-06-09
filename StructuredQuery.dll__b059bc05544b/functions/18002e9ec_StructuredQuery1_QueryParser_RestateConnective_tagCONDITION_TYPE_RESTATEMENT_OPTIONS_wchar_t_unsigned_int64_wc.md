# StructuredQuery1::QueryParser::RestateConnective(tagCONDITION_TYPE,RESTATEMENT_OPTIONS,wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *)

- ea: `0x18002e9ec`
- end: `0x18002ec3b`
- name: `?RestateConnective@QueryParser@StructuredQuery1@@AEAAJW4tagCONDITION_TYPE@@W4RESTATEMENT_OPTIONS@@PEA_W_KPEAPEA_WPEA_K@Z`
- size: `591`
- prototype: `int __high(enum tagCONDITION_TYPE, enum RESTATEMENT_OPTIONS, wchar_t *, unsigned __int64, wchar_t **, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002ce3c`
- `0x18002d5f4`
- `0x18006d84c`

## callees

- `0x18002e548`
- `0x18002e9ec`
- `0x18002eda8`
- `0x180059920`
- `0x180059be8`
- `0x18005daf0`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18002eb41`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18002eb41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002eb60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002eb60`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::QueryParser::RestateConnective(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
        StructuredQuery1 *a4,
        wchar_t *a5,
        StructuredQuery1 **a6,
        wchar_t **a7)
{
  StructuredQuery1 *v7; // r14
  wchar_t *v8; // r15
  int v10; // r13d
  int Error; // ebx
  int v12; // r9d
  wchar_t **v13; // r10
  WCHAR *v14; // rdi
  const wchar_t *v15; // r12
  __int64 v16; // rcx
  __int64 v17; // rcx
  DWORD v18; // edx
  unsigned __int64 *cchDest; // [rsp+28h] [rbp-D8h]
  unsigned __int64 *cchDesta; // [rsp+28h] [rbp-D8h]
  unsigned __int64 *cchDestb; // [rsp+28h] [rbp-D8h]
  wchar_t v23[4]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t **v24; // [rsp+38h] [rbp-C8h]
  LPCWSTR lpSrcStr; // [rsp+40h] [rbp-C0h] BYREF
  StructuredQuery1 **v26; // [rsp+48h] [rbp-B8h]
  WCHAR DestStr[264]; // [rsp+50h] [rbp-B0h] BYREF

  v7 = a4;
  v8 = a5;
  *(_QWORD *)v23 = a4;
  v26 = a6;
  v10 = a3;
  v24 = a7;
  Error = StructuredQuery1::NullTerminateOutputBuffer(a4, a5, a3);
  if ( Error >= 0 )
  {
    if ( v12 )
    {
      if ( v12 != 1 )
      {
        if ( v12 != 2 )
        {
          Error = -2147418113;
          goto LABEL_26;
        }
        v14 = (WCHAR *)L"NOT";
        v15 = (const wchar_t *)&cchOriginalDestLength;
        v16 = *(_QWORD *)(*(_QWORD *)(a1 + 104) + 152LL);
LABEL_10:
        if ( (v10 & 1) == 0 )
        {
          if ( *(_DWORD *)(a1 + 84) == v12 )
          {
            v15 = (const wchar_t *)&cchOriginalDestLength;
            v14 = (WCHAR *)&cchOriginalDestLength;
          }
          else
          {
            v17 = *(_QWORD *)(v16 + 16);
            lpSrcStr = 0;
            Error = StructuredQuery1::DefaultPhraseCommon(v17, *(_DWORD *)(a1 + 80) != 2, &lpSrcStr);
            if ( Error < 0 )
              goto LABEL_25;
            if ( *(_DWORD *)(a1 + 80) != 2 || (v18 = 16777472, v10 != 2) )
              v18 = 16777728;
            if ( LCMapStringW(*(_DWORD *)(a1 + 56), v18, lpSrcStr, -1, DestStr, 260) )
            {
              v14 = DestStr;
            }
            else
            {
              v14 = 0;
              Error = ResultFromKnownLastError();
            }
            CoTaskMemFree((LPVOID)lpSrcStr);
            if ( Error < 0 )
              goto LABEL_25;
          }
        }
        Error = StructuredQuery1::RestatementStringCchCopy(v7, v8, (unsigned __int64)v15, v23, &a5, cchDest);
        if ( Error >= 0 )
        {
          Error = StructuredQuery1::RestatementStringCchCopy(
                    *(StructuredQuery1 **)v23,
                    a5,
                    (unsigned __int64)v14,
                    v23,
                    &a5,
                    cchDesta);
          if ( Error >= 0 )
            Error = StructuredQuery1::RestatementStringCchCopy(
                      *(StructuredQuery1 **)v23,
                      a5,
                      (unsigned __int64)L" ",
                      v23,
                      &a5,
                      cchDestb);
        }
        v7 = *(StructuredQuery1 **)v23;
        v8 = a5;
LABEL_25:
        v13 = v24;
        goto LABEL_26;
      }
      v14 = L"OR";
      v16 = *(_QWORD *)(*(_QWORD *)(a1 + 104) + 144LL);
    }
    else
    {
      v14 = L"AND";
      v16 = *(_QWORD *)(*(_QWORD *)(a1 + 104) + 136LL);
    }
    v15 = L" ";
    goto LABEL_10;
  }
LABEL_26:
  if ( v26 )
    *v26 = v7;
  if ( v13 )
    *v13 = v8;
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18002e9ec  mov     [rsp-8+arg_8], rbx
0x18002e9f1  push    rbp
0x18002e9f2  push    rsi
0x18002e9f3  push    rdi
0x18002e9f4  push    r12
0x18002e9f6  push    r13
0x18002e9f8  push    r14
0x18002e9fa  push    r15
0x18002e9fc  lea     rbp, [rsp-170h]
0x18002ea04  sub     rsp, 270h
0x18002ea0b  mov     rax, cs:__security_cookie
0x18002ea12  xor     rax, rsp
0x18002ea15  mov     [rbp+1A0h+var_40], rax
0x18002ea1c  mov     rax, [rbp+1A0h+arg_28]
0x18002ea23  mov     r14, r9
0x18002ea26  mov     r15, [rbp+1A0h+arg_20]
0x18002ea2d  mov     r9d, edx
0x18002ea30  mov     r10, [rbp+1A0h+arg_30]
0x18002ea37  mov     rsi, rcx
0x18002ea3a  mov     rdx, r15; wchar_t *
0x18002ea3d  mov     qword ptr [rsp+2A0h+var_270], r14
0x18002ea42  mov     rcx, r14; this
0x18002ea45  mov     [rsp+2A0h+var_258], rax
0x18002ea4a  mov     r13d, r8d
0x18002ea4d  mov     [rsp+2A0h+var_268], r10
0x18002ea52  call    ?NullTerminateOutputBuffer@StructuredQuery1@@YAJPEA_W_K@Z; StructuredQuery1::NullTerminateOutputBuffer(wchar_t *,unsigned __int64)
0x18002ea57  mov     ebx, eax
0x18002ea59  test    eax, eax
0x18002ea5b  js      loc_18002EBFA
0x18002ea61  lea     rdx, cchOriginalDestLength
0x18002ea68  mov     ecx, r9d
0x18002ea6b  test    r9d, r9d
0x18002ea6e  jz      short loc_18002EAAF
0x18002ea70  sub     ecx, 1
0x18002ea73  jz      short loc_18002EA9B
0x18002ea75  cmp     ecx, 1
0x18002ea78  jz      short loc_18002EA84
0x18002ea7a  mov     ebx, 8000FFFFh
0x18002ea7f  jmp     loc_18002EBFA
0x18002ea84  mov     rax, [rsi+68h]
0x18002ea88  lea     rdi, aNot; "NOT"
0x18002ea8f  mov     r12, rdx
0x18002ea92  mov     rcx, [rax+98h]
0x18002ea99  jmp     short loc_18002EAC8
0x18002ea9b  mov     rax, [rsi+68h]
0x18002ea9f  lea     rdi, aOr_0; "OR"
0x18002eaa6  mov     rcx, [rax+90h]
0x18002eaad  jmp     short loc_18002EAC1
0x18002eaaf  mov     rax, [rsi+68h]
0x18002eab3  lea     rdi, aAnd_0; "AND"
0x18002eaba  mov     rcx, [rax+88h]
0x18002eac1  lea     r12, pszTrimChars; " "
0x18002eac8  test    r13b, 1
0x18002eacc  jnz     loc_18002EB6E
0x18002ead2  cmp     [rsi+54h], r9d
0x18002ead6  jnz     short loc_18002EAE3
0x18002ead8  mov     r12, rdx
0x18002eadb  mov     rdi, rdx
0x18002eade  jmp     loc_18002EB6E
0x18002eae3  mov     rcx, [rcx+10h]
0x18002eae7  lea     r8, [rsp+2A0h+lpSrcStr]
0x18002eaec  xor     edx, edx
0x18002eaee  mov     [rsp+2A0h+lpSrcStr], 0
0x18002eaf7  cmp     dword ptr [rsi+50h], 2
0x18002eafb  setnz   dl
0x18002eafe  call    ?DefaultPhraseCommon@StructuredQuery1@@YAJPEB_WW4DEFAULT_PHRASE_FLAGS@1@PEAPEA_W@Z; StructuredQuery1::DefaultPhraseCommon(wchar_t const *,StructuredQuery1::DEFAULT_PHRASE_FLAGS,wchar_t * *)
0x18002eb03  mov     ebx, eax
0x18002eb05  test    eax, eax
0x18002eb07  js      loc_18002EBF5
0x18002eb0d  cmp     dword ptr [rsi+50h], 2
0x18002eb11  jnz     short loc_18002EB1E
0x18002eb13  mov     edx, 1000100h
0x18002eb18  cmp     r13d, 2
0x18002eb1c  jz      short loc_18002EB23
0x18002eb1e  mov     edx, 1000200h; dwMapFlags
0x18002eb23  mov     r8, [rsp+2A0h+lpSrcStr]; lpSrcStr
0x18002eb28  lea     rax, [rsp+2A0h+DestStr]
0x18002eb2d  mov     ecx, [rsi+38h]; Locale
0x18002eb30  or      r9d, 0FFFFFFFFh; cchSrc
0x18002eb34  mov     dword ptr [rsp+2A0h+cchDest], 104h; unsigned __int64 *
0x18002eb3c  mov     [rsp+2A0h+lpDestStr], rax; lpDestStr
0x18002eb41  call    cs:__imp_LCMapStringW
0x18002eb47  test    eax, eax
0x18002eb49  jz      short loc_18002EB52
0x18002eb4b  lea     rdi, [rsp+2A0h+DestStr]
0x18002eb50  jmp     short loc_18002EB5B
0x18002eb52  xor     edi, edi
0x18002eb54  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002eb59  mov     ebx, eax
0x18002eb5b  mov     rcx, [rsp+2A0h+lpSrcStr]; pv
0x18002eb60  call    cs:__imp_CoTaskMemFree
0x18002eb66  test    ebx, ebx
0x18002eb68  js      loc_18002EBF5
0x18002eb6e  lea     rax, [rbp+1A0h+arg_20]
0x18002eb75  mov     r8, r12; unsigned __int64
0x18002eb78  lea     r9, [rsp+2A0h+var_270]; wchar_t *
0x18002eb7d  mov     [rsp+2A0h+lpDestStr], rax; wchar_t **
0x18002eb82  mov     rdx, r15; wchar_t *
0x18002eb85  mov     rcx, r14; this
0x18002eb88  call    ?RestatementStringCchCopy@StructuredQuery1@@YAJPEA_W_KPEB_WPEAPEA_WPEA_K@Z; StructuredQuery1::RestatementStringCchCopy(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *)
0x18002eb8d  mov     ebx, eax
0x18002eb8f  test    eax, eax
0x18002eb91  js      short loc_18002EBE9
0x18002eb93  mov     rdx, [rbp+1A0h+arg_20]; wchar_t *
0x18002eb9a  lea     rax, [rbp+1A0h+arg_20]
0x18002eba1  mov     rcx, qword ptr [rsp+2A0h+var_270]; this
0x18002eba6  lea     r9, [rsp+2A0h+var_270]; wchar_t *
0x18002ebab  mov     r8, rdi; unsigned __int64
0x18002ebae  mov     [rsp+2A0h+lpDestStr], rax; wchar_t **
0x18002ebb3  call    ?RestatementStringCchCopy@StructuredQuery1@@YAJPEA_W_KPEB_WPEAPEA_WPEA_K@Z; StructuredQuery1::RestatementStringCchCopy(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *)
0x18002ebb8  mov     ebx, eax
0x18002ebba  test    eax, eax
0x18002ebbc  js      short loc_18002EBE9
0x18002ebbe  mov     rdx, [rbp+1A0h+arg_20]; wchar_t *
0x18002ebc5  lea     rax, [rbp+1A0h+arg_20]
0x18002ebcc  mov     rcx, qword ptr [rsp+2A0h+var_270]; this
0x18002ebd1  lea     r9, [rsp+2A0h+var_270]; wchar_t *
0x18002ebd6  lea     r8, pszTrimChars; " "
0x18002ebdd  mov     [rsp+2A0h+lpDestStr], rax; wchar_t **
0x18002ebe2  call    ?RestatementStringCchCopy@StructuredQuery1@@YAJPEA_W_KPEB_WPEAPEA_WPEA_K@Z; StructuredQuery1::RestatementStringCchCopy(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *)
0x18002ebe7  mov     ebx, eax
0x18002ebe9  mov     r14, qword ptr [rsp+2A0h+var_270]
0x18002ebee  mov     r15, [rbp+1A0h+arg_20]
0x18002ebf5  mov     r10, [rsp+2A0h+var_268]
0x18002ebfa  mov     rax, [rsp+2A0h+var_258]
0x18002ebff  test    rax, rax
0x18002ec02  jz      short loc_18002EC07
0x18002ec04  mov     [rax], r14
0x18002ec07  test    r10, r10
0x18002ec0a  jz      short loc_18002EC0F
0x18002ec0c  mov     [r10], r15
0x18002ec0f  mov     eax, ebx
0x18002ec11  mov     rcx, [rbp+1A0h+var_40]
0x18002ec18  xor     rcx, rsp; StackCookie
0x18002ec1b  call    __security_check_cookie
0x18002ec20  mov     rbx, [rsp+2A0h+arg_8]
0x18002ec28  add     rsp, 270h
0x18002ec2f  pop     r15
0x18002ec31  pop     r14
0x18002ec33  pop     r13
0x18002ec35  pop     r12
0x18002ec37  pop     rdi
0x18002ec38  pop     rsi
0x18002ec39  pop     rbp
0x18002ec3a  retn
```
