# ConvertIPTCDateTimeStringsOnRead(tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x18000c58c`
- end: `0x18000c7b5`
- name: `?ConvertIPTCDateTimeStringsOnRead@@YAJPEBUtagPROPVARIANT@@0PEAU1@@Z`
- size: `553`
- prototype: `int(const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000c300`

## callees

- `0x18000bff0`
- `0x18000c58c`
- `0x180016020`
- `0x180016ab8`
- `0x180016b18`
- `0x18002005c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000c5b8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000c5b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c77e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c77e`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x18000c75a`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x18000c75a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000c76c`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000c76c`

## pseudocode

```c
__int64 __fastcall ConvertIPTCDateTimeStringsOnRead(
        const struct tagPROPVARIANT *a1,
        const struct tagPROPVARIANT *a2,
        struct tagPROPVARIANT *a3)
{
  unsigned __int64 v6; // rdx
  int vt; // ecx
  int v8; // ebx
  int v9; // ecx
  const unsigned __int16 *bstrVal; // rcx
  unsigned __int64 v11; // rdx
  const char *pszVal; // rcx
  const unsigned __int16 *v13; // rcx
  const char *v14; // rcx
  signed int LastError; // eax
  unsigned __int64 v17; // [rsp+30h] [rbp-30h] BYREF
  SYSTEMTIME LocalTime; // [rsp+38h] [rbp-28h] BYREF
  struct _SYSTEMTIME UniversalTime; // [rsp+48h] [rbp-18h] BYREF

  PropVariantClear(a3);
  vt = a1->vt;
  v8 = -2147024809;
  LocalTime = 0;
  UniversalTime = 0;
  v9 = vt - 30;
  if ( v9 )
  {
    if ( v9 != 1 )
      return (unsigned int)v8;
    bstrVal = a1->bstrVal;
    if ( !bstrVal )
      return (unsigned int)v8;
    v17 = 0;
    v8 = StringCchLengthW(bstrVal, 0x7FFFFFFFu, &v17);
    if ( v8 < 0 )
      return (unsigned int)v8;
    if ( v17 >= 8 )
    {
      swscanf_s(a1->bstrVal, L"%4hu%2hu%2hu", &LocalTime, &LocalTime.wMonth, &LocalTime.wDay);
LABEL_11:
      v8 = 0;
    }
  }
  else
  {
    if ( !a1->hVal.QuadPart )
      return (unsigned int)v8;
    pszVal = a1->pszVal;
    v17 = 0;
    v8 = StringCchLengthA(pszVal, v6, &v17);
    if ( v8 < 0 )
      return (unsigned int)v8;
    if ( v17 >= 8 )
    {
      sscanf_s(a1->pszVal, "%4hu%2hu%2hu", &LocalTime, &LocalTime.wMonth, &LocalTime.wDay);
      goto LABEL_11;
    }
  }
  if ( !a2->vt )
    goto LABEL_26;
  if ( a2->vt == 30 )
  {
    if ( a2->hVal.QuadPart )
    {
      v14 = a2->pszVal;
      v17 = 0;
      v8 = StringCchLengthA(v14, v11, &v17);
      if ( v8 < 0 )
        return (unsigned int)v8;
      if ( v17 >= 0xB )
        sscanf_s(a2->pszVal, "%2hu%2hu%2hu", &LocalTime.wHour, &LocalTime.wMinute, &LocalTime.wSecond);
      goto LABEL_26;
    }
    return (unsigned int)-2147024809;
  }
  if ( a2->vt != 31 )
    return (unsigned int)-2147024809;
  v13 = a2->bstrVal;
  if ( v13 )
  {
    v17 = 0;
    v8 = StringCchLengthW(v13, 0x7FFFFFFFu, &v17);
    if ( v8 < 0 )
      return (unsigned int)v8;
    if ( v17 >= 0xB )
      swscanf_s(a2->bstrVal, L"%2hu%2hu%2hu", &LocalTime.wHour, &LocalTime.wMinute, &LocalTime.wSecond);
  }
  else
  {
    v8 = -2147024809;
  }
  if ( v8 < 0 )
    return (unsigned int)v8;
LABEL_26:
  if ( !LocalTime.wYear )
    return (unsigned int)-2147024809;
  if ( TzSpecificLocalTimeToSystemTime(0, &LocalTime, &UniversalTime)
    && SystemTimeToFileTime(&UniversalTime, &a3->filetime) )
  {
    a3->vt = 64;
  }
  else
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000c58c  push    rbp
0x18000c58e  push    rbx
0x18000c58f  push    rsi
0x18000c590  push    rdi
0x18000c591  push    r12
0x18000c593  push    r14
0x18000c595  push    r15
0x18000c597  mov     rbp, rsp
0x18000c59a  sub     rsp, 60h
0x18000c59e  mov     rax, cs:__security_cookie
0x18000c5a5  xor     rax, rsp
0x18000c5a8  mov     [rbp+var_8], rax
0x18000c5ac  mov     r14, rcx
0x18000c5af  mov     r15, r8
0x18000c5b2  mov     rcx, r8; pvar
0x18000c5b5  mov     rsi, rdx
0x18000c5b8  call    cs:__imp_PropVariantClear
0x18000c5be  movzx   ecx, word ptr [r14]
0x18000c5c2  xorps   xmm0, xmm0
0x18000c5c5  xorps   xmm1, xmm1
0x18000c5c8  mov     r12d, 80070057h
0x18000c5ce  mov     ebx, r12d
0x18000c5d1  movups  xmmword ptr [rbp+LocalTime.wYear], xmm0
0x18000c5d5  movups  xmmword ptr [rbp+UniversalTime.wYear], xmm1
0x18000c5d9  sub     ecx, 1Eh
0x18000c5dc  jz      short loc_18000C63C
0x18000c5de  cmp     ecx, 1
0x18000c5e1  jnz     loc_18000C798
0x18000c5e7  mov     rcx, [r14+8]; unsigned __int16 *
0x18000c5eb  xor     edi, edi
0x18000c5ed  test    rcx, rcx
0x18000c5f0  jz      loc_18000C798
0x18000c5f6  lea     r8, [rbp+var_30]; unsigned __int64 *
0x18000c5fa  mov     [rbp+var_30], rdi
0x18000c5fe  mov     edx, 7FFFFFFFh; unsigned __int64
0x18000c603  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000c608  mov     ebx, eax
0x18000c60a  test    eax, eax
0x18000c60c  js      loc_18000C798
0x18000c612  cmp     [rbp+var_30], 8
0x18000c617  jb      short loc_18000C68D
0x18000c619  mov     rcx, [r14+8]; Buffer
0x18000c61d  lea     rax, [rbp+LocalTime.wDay]
0x18000c621  lea     r9, [rbp+LocalTime.wMonth]
0x18000c625  mov     [rsp+60h+var_40], rax
0x18000c62a  lea     r8, [rbp+LocalTime]
0x18000c62e  lea     rdx, a4hu2hu2hu; "%4hu%2hu%2hu"
0x18000c635  call    swscanf_s
0x18000c63a  jmp     short loc_18000C68B
0x18000c63c  xor     edi, edi
0x18000c63e  cmp     [r14+8], rdi
0x18000c642  jz      loc_18000C798
0x18000c648  mov     rcx, [r14+8]; char *
0x18000c64c  lea     r8, [rbp+var_30]; unsigned __int64 *
0x18000c650  mov     [rbp+var_30], rdi
0x18000c654  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x18000c659  mov     ebx, eax
0x18000c65b  test    eax, eax
0x18000c65d  js      loc_18000C798
0x18000c663  cmp     [rbp+var_30], 8
0x18000c668  jb      short loc_18000C68D
0x18000c66a  mov     rcx, [r14+8]; Buffer
0x18000c66e  lea     rax, [rbp+LocalTime.wDay]
0x18000c672  lea     r9, [rbp+LocalTime.wMonth]
0x18000c676  mov     [rsp+60h+var_40], rax
0x18000c67b  lea     r8, [rbp+LocalTime]
0x18000c67f  lea     rdx, a4hu2hu2hu_0; "%4hu%2hu%2hu"
0x18000c686  call    sscanf_s
0x18000c68b  mov     ebx, edi
0x18000c68d  movzx   ecx, word ptr [rsi]
0x18000c690  test    ecx, ecx
0x18000c692  jz      loc_18000C74A
0x18000c698  sub     ecx, 1Eh
0x18000c69b  jz      short loc_18000C701
0x18000c69d  cmp     ecx, 1
0x18000c6a0  jnz     loc_18000C795
0x18000c6a6  mov     rcx, [rsi+8]; unsigned __int16 *
0x18000c6aa  test    rcx, rcx
0x18000c6ad  jz      short loc_18000C6F5
0x18000c6af  lea     r8, [rbp+var_30]; unsigned __int64 *
0x18000c6b3  mov     [rbp+var_30], rdi
0x18000c6b7  mov     edx, 7FFFFFFFh; unsigned __int64
0x18000c6bc  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000c6c1  mov     ebx, eax
0x18000c6c3  test    eax, eax
0x18000c6c5  js      loc_18000C798
0x18000c6cb  cmp     [rbp+var_30], 0Bh
0x18000c6d0  jb      short loc_18000C6F8
0x18000c6d2  mov     rcx, [rsi+8]; Buffer
0x18000c6d6  lea     rax, [rbp+LocalTime.wSecond]
0x18000c6da  lea     r9, [rbp+LocalTime.wMinute]
0x18000c6de  mov     [rsp+60h+var_40], rax
0x18000c6e3  lea     r8, [rbp+LocalTime.wHour]
0x18000c6e7  lea     rdx, a2hu2hu2hu; "%2hu%2hu%2hu"
0x18000c6ee  call    swscanf_s
0x18000c6f3  jmp     short loc_18000C6F8
0x18000c6f5  mov     ebx, r12d
0x18000c6f8  test    ebx, ebx
0x18000c6fa  jns     short loc_18000C74A
0x18000c6fc  jmp     loc_18000C798
0x18000c701  cmp     [rsi+8], rdi
0x18000c705  jz      loc_18000C795
0x18000c70b  mov     rcx, [rsi+8]; char *
0x18000c70f  lea     r8, [rbp+var_30]; unsigned __int64 *
0x18000c713  mov     [rbp+var_30], rdi
0x18000c717  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x18000c71c  mov     ebx, eax
0x18000c71e  test    eax, eax
0x18000c720  js      short loc_18000C798
0x18000c722  cmp     [rbp+var_30], 0Bh
0x18000c727  jb      short loc_18000C74A
0x18000c729  mov     rcx, [rsi+8]; Buffer
0x18000c72d  lea     rax, [rbp+LocalTime.wSecond]
0x18000c731  lea     r9, [rbp+LocalTime.wMinute]
0x18000c735  mov     [rsp+60h+var_40], rax
0x18000c73a  lea     r8, [rbp+LocalTime.wHour]
0x18000c73e  lea     rdx, a2hu2hu2hu_0; "%2hu%2hu%2hu"
0x18000c745  call    sscanf_s
0x18000c74a  cmp     [rbp+LocalTime.wYear], di
0x18000c74e  jz      short loc_18000C795
0x18000c750  lea     r8, [rbp+UniversalTime]; lpUniversalTime
0x18000c754  xor     ecx, ecx; lpTimeZoneInformation
0x18000c756  lea     rdx, [rbp+LocalTime]; lpLocalTime
0x18000c75a  call    cs:__imp_TzSpecificLocalTimeToSystemTime
0x18000c760  test    eax, eax
0x18000c762  jz      short loc_18000C77E
0x18000c764  lea     rdx, [r15+8]; lpFileTime
0x18000c768  lea     rcx, [rbp+UniversalTime]; lpSystemTime
0x18000c76c  call    cs:__imp_SystemTimeToFileTime
0x18000c772  test    eax, eax
0x18000c774  jz      short loc_18000C77E
0x18000c776  mov     word ptr [r15], 40h ; '@'
0x18000c77c  jmp     short loc_18000C798
0x18000c77e  call    cs:__imp_GetLastError
0x18000c784  mov     ebx, eax
0x18000c786  test    eax, eax
0x18000c788  jle     short loc_18000C798
0x18000c78a  movzx   ebx, ax
0x18000c78d  or      ebx, 80070000h
0x18000c793  jmp     short loc_18000C798
0x18000c795  mov     ebx, r12d
0x18000c798  mov     eax, ebx
0x18000c79a  mov     rcx, [rbp+var_8]
0x18000c79e  xor     rcx, rsp; StackCookie
0x18000c7a1  call    __security_check_cookie
0x18000c7a6  add     rsp, 60h
0x18000c7aa  pop     r15
0x18000c7ac  pop     r14
0x18000c7ae  pop     r12
0x18000c7b0  pop     rdi
0x18000c7b1  pop     rsi
0x18000c7b2  pop     rbx
0x18000c7b3  pop     rbp
0x18000c7b4  retn
```
