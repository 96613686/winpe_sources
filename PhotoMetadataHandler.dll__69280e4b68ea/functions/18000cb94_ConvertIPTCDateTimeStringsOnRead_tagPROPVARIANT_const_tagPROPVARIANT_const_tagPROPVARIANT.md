# ConvertIPTCDateTimeStringsOnRead(tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x18000cb94`
- end: `0x18000cdda`
- name: `?ConvertIPTCDateTimeStringsOnRead@@YAJPEBUtagPROPVARIANT@@0PEAU1@@Z`
- size: `582`
- prototype: `int(const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000c8e0`

## callees

- `0x18000c5a0`
- `0x18000cb94`
- `0x180016a40`
- `0x180017508`
- `0x180017568`
- `0x180021034`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000cbc0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000cbc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd9c`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x18000cd6c`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x18000cd6c`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000cd84`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000cd84`

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
0x18000cb94  push    rbp
0x18000cb96  push    rbx
0x18000cb97  push    rsi
0x18000cb98  push    rdi
0x18000cb99  push    r12
0x18000cb9b  push    r14
0x18000cb9d  push    r15
0x18000cb9f  mov     rbp, rsp
0x18000cba2  sub     rsp, 60h
0x18000cba6  mov     rax, cs:__security_cookie
0x18000cbad  xor     rax, rsp
0x18000cbb0  mov     [rbp+var_8], rax
0x18000cbb4  mov     r14, rcx
0x18000cbb7  mov     r15, r8
0x18000cbba  mov     rcx, r8; pvar
0x18000cbbd  mov     rsi, rdx
0x18000cbc0  call    cs:__imp_PropVariantClear
0x18000cbc7  nop     dword ptr [rax+rax+00h]
0x18000cbcc  movzx   ecx, word ptr [r14]
0x18000cbd0  xorps   xmm0, xmm0
0x18000cbd3  xorps   xmm1, xmm1
0x18000cbd6  mov     r12d, 80070057h
0x18000cbdc  mov     ebx, r12d
0x18000cbdf  movups  xmmword ptr [rbp+LocalTime.wYear], xmm0
0x18000cbe3  movups  xmmword ptr [rbp+UniversalTime.wYear], xmm1
0x18000cbe7  sub     ecx, 1Eh
0x18000cbea  jz      short loc_18000CC4A
0x18000cbec  cmp     ecx, 1
0x18000cbef  jnz     loc_18000CDBC
0x18000cbf5  mov     rcx, [r14+8]; unsigned __int16 *
0x18000cbf9  xor     edi, edi
0x18000cbfb  test    rcx, rcx
0x18000cbfe  jz      loc_18000CDBC
0x18000cc04  lea     r8, [rbp+var_30]; unsigned __int64 *
0x18000cc08  mov     [rbp+var_30], rdi
0x18000cc0c  mov     edx, 7FFFFFFFh; unsigned __int64
0x18000cc11  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000cc16  mov     ebx, eax
0x18000cc18  test    eax, eax
0x18000cc1a  js      loc_18000CDBC
0x18000cc20  cmp     [rbp+var_30], 8
0x18000cc25  jb      short loc_18000CC9B
0x18000cc27  mov     rcx, [r14+8]; Buffer
0x18000cc2b  lea     rax, [rbp+LocalTime.wDay]
0x18000cc2f  lea     r9, [rbp+LocalTime.wMonth]
0x18000cc33  mov     [rsp+60h+var_40], rax
0x18000cc38  lea     r8, [rbp+LocalTime]
0x18000cc3c  lea     rdx, a4hu2hu2hu; "%4hu%2hu%2hu"
0x18000cc43  call    swscanf_s
0x18000cc48  jmp     short loc_18000CC99
0x18000cc4a  xor     edi, edi
0x18000cc4c  cmp     [r14+8], rdi
0x18000cc50  jz      loc_18000CDBC
0x18000cc56  mov     rcx, [r14+8]; char *
0x18000cc5a  lea     r8, [rbp+var_30]; unsigned __int64 *
0x18000cc5e  mov     [rbp+var_30], rdi
0x18000cc62  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x18000cc67  mov     ebx, eax
0x18000cc69  test    eax, eax
0x18000cc6b  js      loc_18000CDBC
0x18000cc71  cmp     [rbp+var_30], 8
0x18000cc76  jb      short loc_18000CC9B
0x18000cc78  mov     rcx, [r14+8]; Buffer
0x18000cc7c  lea     rax, [rbp+LocalTime.wDay]
0x18000cc80  lea     r9, [rbp+LocalTime.wMonth]
0x18000cc84  mov     [rsp+60h+var_40], rax
0x18000cc89  lea     r8, [rbp+LocalTime]
0x18000cc8d  lea     rdx, a4hu2hu2hu_0; "%4hu%2hu%2hu"
0x18000cc94  call    sscanf_s
0x18000cc99  mov     ebx, edi
0x18000cc9b  movzx   ecx, word ptr [rsi]
0x18000cc9e  test    ecx, ecx
0x18000cca0  jz      loc_18000CD5C
0x18000cca6  sub     ecx, 1Eh
0x18000cca9  jz      short loc_18000CD0F
0x18000ccab  cmp     ecx, 1
0x18000ccae  jnz     loc_18000CDB9
0x18000ccb4  mov     rcx, [rsi+8]; unsigned __int16 *
0x18000ccb8  test    rcx, rcx
0x18000ccbb  jz      short loc_18000CD03
0x18000ccbd  lea     r8, [rbp+var_30]; unsigned __int64 *
0x18000ccc1  mov     [rbp+var_30], rdi
0x18000ccc5  mov     edx, 7FFFFFFFh; unsigned __int64
0x18000ccca  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000cccf  mov     ebx, eax
0x18000ccd1  test    eax, eax
0x18000ccd3  js      loc_18000CDBC
0x18000ccd9  cmp     [rbp+var_30], 0Bh
0x18000ccde  jb      short loc_18000CD06
0x18000cce0  mov     rcx, [rsi+8]; Buffer
0x18000cce4  lea     rax, [rbp+LocalTime.wSecond]
0x18000cce8  lea     r9, [rbp+LocalTime.wMinute]
0x18000ccec  mov     [rsp+60h+var_40], rax
0x18000ccf1  lea     r8, [rbp+LocalTime.wHour]
0x18000ccf5  lea     rdx, a2hu2hu2hu; "%2hu%2hu%2hu"
0x18000ccfc  call    swscanf_s
0x18000cd01  jmp     short loc_18000CD06
0x18000cd03  mov     ebx, r12d
0x18000cd06  test    ebx, ebx
0x18000cd08  jns     short loc_18000CD5C
0x18000cd0a  jmp     loc_18000CDBC
0x18000cd0f  cmp     [rsi+8], rdi
0x18000cd13  jz      loc_18000CDB9
0x18000cd19  mov     rcx, [rsi+8]; char *
0x18000cd1d  lea     r8, [rbp+var_30]; unsigned __int64 *
0x18000cd21  mov     [rbp+var_30], rdi
0x18000cd25  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x18000cd2a  mov     ebx, eax
0x18000cd2c  test    eax, eax
0x18000cd2e  js      loc_18000CDBC
0x18000cd34  cmp     [rbp+var_30], 0Bh
0x18000cd39  jb      short loc_18000CD5C
0x18000cd3b  mov     rcx, [rsi+8]; Buffer
0x18000cd3f  lea     rax, [rbp+LocalTime.wSecond]
0x18000cd43  lea     r9, [rbp+LocalTime.wMinute]
0x18000cd47  mov     [rsp+60h+var_40], rax
0x18000cd4c  lea     r8, [rbp+LocalTime.wHour]
0x18000cd50  lea     rdx, a2hu2hu2hu_0; "%2hu%2hu%2hu"
0x18000cd57  call    sscanf_s
0x18000cd5c  cmp     [rbp+LocalTime.wYear], di
0x18000cd60  jz      short loc_18000CDB9
0x18000cd62  lea     r8, [rbp+UniversalTime]; lpUniversalTime
0x18000cd66  xor     ecx, ecx; lpTimeZoneInformation
0x18000cd68  lea     rdx, [rbp+LocalTime]; lpLocalTime
0x18000cd6c  call    cs:__imp_TzSpecificLocalTimeToSystemTime
0x18000cd73  nop     dword ptr [rax+rax+00h]
0x18000cd78  test    eax, eax
0x18000cd7a  jz      short loc_18000CD9C
0x18000cd7c  lea     rdx, [r15+8]; lpFileTime
0x18000cd80  lea     rcx, [rbp+UniversalTime]; lpSystemTime
0x18000cd84  call    cs:__imp_SystemTimeToFileTime
0x18000cd8b  nop     dword ptr [rax+rax+00h]
0x18000cd90  test    eax, eax
0x18000cd92  jz      short loc_18000CD9C
0x18000cd94  mov     word ptr [r15], 40h ; '@'
0x18000cd9a  jmp     short loc_18000CDBC
0x18000cd9c  call    cs:__imp_GetLastError
0x18000cda3  nop     dword ptr [rax+rax+00h]
0x18000cda8  mov     ebx, eax
0x18000cdaa  test    eax, eax
0x18000cdac  jle     short loc_18000CDBC
0x18000cdae  movzx   ebx, ax
0x18000cdb1  or      ebx, 80070000h
0x18000cdb7  jmp     short loc_18000CDBC
0x18000cdb9  mov     ebx, r12d
0x18000cdbc  mov     eax, ebx
0x18000cdbe  mov     rcx, [rbp+var_8]
0x18000cdc2  xor     rcx, rsp; StackCookie
0x18000cdc5  call    __security_check_cookie
0x18000cdca  add     rsp, 60h
0x18000cdce  pop     r15
0x18000cdd0  pop     r14
0x18000cdd2  pop     r12
0x18000cdd4  pop     rdi
0x18000cdd5  pop     rsi
0x18000cdd6  pop     rbx
0x18000cdd7  pop     rbp
0x18000cdd8  retn
```
