# ConvertDateToXMPStringOnWrite(tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x18001ed94`
- end: `0x18001ef11`
- name: `?ConvertDateToXMPStringOnWrite@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z`
- size: `381`
- prototype: `int(const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001cae0`

## callees

- `0x180007d90`
- `0x18000e364`
- `0x18001014c`
- `0x180016020`
- `0x18001ed94`
- `0x180021a5c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001edc3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001eed9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001edc3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001eed9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001edf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001edf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee4a`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001edeb`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001edeb`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x18001ee40`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x18001ee40`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x18001eec6`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x18001eec6`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18001ee28`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18001ee28`

## pseudocode

```c
__int64 __fastcall ConvertDateToXMPStringOnWrite(const struct tagPROPVARIANT *a1, struct tagPROPVARIANT *a2)
{
  bool v4; // zf
  signed int LastError; // eax
  int v6; // ebx
  signed int v7; // eax
  unsigned __int16 **p_bstrVal; // rdi
  __int64 v9; // rdx
  WCHAR *v10; // r14
  ULONGLONG pullResult[2]; // [rsp+20h] [rbp-60h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+30h] [rbp-50h] BYREF
  struct _SYSTEMTIME LocalTime; // [rsp+40h] [rbp-40h] BYREF
  CHAR pszSrc[32]; // [rsp+50h] [rbp-30h] BYREF

  PropVariantClear(a2);
  v4 = a1->vt == 64;
  SystemTime = 0;
  LocalTime = 0;
  if ( v4 )
  {
    if ( !FileTimeToSystemTime(&a1->filetime, &SystemTime) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 < 0 )
        return (unsigned int)v6;
    }
  }
  else
  {
    v6 = -2147024809;
    if ( a1->vt != 7 || !VariantTimeToSystemTime(a1->dblVal, &SystemTime) )
      return (unsigned int)v6;
  }
  if ( SystemTimeToTzSpecificLocalTime(0, &SystemTime, &LocalTime) )
    goto LABEL_23;
  v7 = GetLastError();
  v6 = v7;
  if ( v7 > 0 )
    v6 = (unsigned __int16)v7 | 0x80070000;
  if ( v6 >= 0 )
  {
LABEL_23:
    pullResult[0] = 0;
    v6 = ULongLongMult(0x19u, 2u, pullResult);
    if ( v6 >= 0 )
    {
      p_bstrVal = &a2->bstrVal;
      v6 = CoTaskMemAllocWithInit(pullResult[0], (void **)&a2->puuid);
      if ( v6 >= 0 )
      {
        v10 = *p_bstrVal;
        *(struct _SYSTEMTIME *)pullResult = LocalTime;
        a2->vt = 31;
        v6 = SysTimeToiso8601(pullResult, v9, pszSrc);
        if ( v6 >= 0 )
        {
          if ( SHAnsiToUnicode(pszSrc, v10, 25) <= 25 )
          {
            RemoveISO8601TimeZoneOffset(*p_bstrVal);
            return 0;
          }
          v6 = -2147418113;
        }
        PropVariantClear(a2);
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001ed94  mov     [rsp-18h+arg_10], rbx
0x18001ed99  mov     [rsp-18h+arg_18], rsi
0x18001ed9e  push    rbp
0x18001ed9f  push    rdi
0x18001eda0  push    r14
0x18001eda2  mov     rbp, rsp
0x18001eda5  sub     rsp, 80h
0x18001edac  mov     rax, cs:__security_cookie
0x18001edb3  xor     rax, rsp
0x18001edb6  mov     [rbp+var_10], rax
0x18001edba  mov     rdi, rcx
0x18001edbd  mov     rsi, rdx
0x18001edc0  mov     rcx, rdx; pvar
0x18001edc3  call    cs:__imp_PropVariantClear
0x18001edc9  cmp     word ptr [rdi], 40h ; '@'
0x18001edcd  xorps   xmm0, xmm0
0x18001edd0  xorps   xmm1, xmm1
0x18001edd3  mov     r14d, 80070000h
0x18001edd9  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18001eddd  movups  xmmword ptr [rbp+LocalTime.wYear], xmm1
0x18001ede1  jnz     short loc_18001EE10
0x18001ede3  lea     rcx, [rdi+8]; lpFileTime
0x18001ede7  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x18001edeb  call    cs:__imp_FileTimeToSystemTime
0x18001edf1  test    eax, eax
0x18001edf3  jnz     short loc_18001EE36
0x18001edf5  call    cs:__imp_GetLastError
0x18001edfb  mov     ebx, eax
0x18001edfd  test    eax, eax
0x18001edff  jle     short loc_18001EE07
0x18001ee01  movzx   ebx, ax
0x18001ee04  or      ebx, r14d
0x18001ee07  test    ebx, ebx
0x18001ee09  jns     short loc_18001EE36
0x18001ee0b  jmp     loc_18001EEDF
0x18001ee10  cmp     word ptr [rdi], 7
0x18001ee14  mov     ebx, 80070057h
0x18001ee19  jnz     loc_18001EEDF
0x18001ee1f  movsd   xmm0, qword ptr [rdi+8]; vtime
0x18001ee24  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x18001ee28  call    cs:__imp_VariantTimeToSystemTime
0x18001ee2e  test    eax, eax
0x18001ee30  jz      loc_18001EEDF
0x18001ee36  lea     r8, [rbp+LocalTime]; lpLocalTime
0x18001ee3a  xor     ecx, ecx; lpTimeZoneInformation
0x18001ee3c  lea     rdx, [rbp+SystemTime]; lpUniversalTime
0x18001ee40  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x18001ee46  test    eax, eax
0x18001ee48  jnz     short loc_18001EE60
0x18001ee4a  call    cs:__imp_GetLastError
0x18001ee50  mov     ebx, eax
0x18001ee52  test    eax, eax
0x18001ee54  jle     short loc_18001EE5C
0x18001ee56  movzx   ebx, ax
0x18001ee59  or      ebx, r14d
0x18001ee5c  test    ebx, ebx
0x18001ee5e  js      short loc_18001EEDF
0x18001ee60  mov     edx, 2; ullMultiplier
0x18001ee65  mov     [rbp+pullResult], 0
0x18001ee6d  lea     r8, [rbp+pullResult]; pullResult
0x18001ee71  lea     ecx, [rdx+17h]; ullMultiplicand
0x18001ee74  call    ULongLongMult
0x18001ee79  mov     ebx, eax
0x18001ee7b  test    eax, eax
0x18001ee7d  js      short loc_18001EEDF
0x18001ee7f  mov     rcx, [rbp+pullResult]; Size
0x18001ee83  lea     rdi, [rsi+8]
0x18001ee87  mov     rdx, rdi; void **
0x18001ee8a  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x18001ee8f  mov     ebx, eax
0x18001ee91  test    eax, eax
0x18001ee93  js      short loc_18001EEDF
0x18001ee95  movaps  xmm0, xmmword ptr [rbp+LocalTime.wYear]
0x18001ee99  lea     r8, [rbp+pszSrc]
0x18001ee9d  mov     r14, [rdi]
0x18001eea0  lea     rcx, [rbp+pullResult]
0x18001eea4  movdqa  xmmword ptr [rbp+pullResult], xmm0
0x18001eea9  mov     word ptr [rsi], 1Fh
0x18001eeae  call    _SysTimeToiso8601
0x18001eeb3  mov     ebx, eax
0x18001eeb5  test    eax, eax
0x18001eeb7  js      short loc_18001EED6
0x18001eeb9  mov     r8d, 19h; cwchBuf
0x18001eebf  lea     rcx, [rbp+pszSrc]; pszSrc
0x18001eec3  mov     rdx, r14; pwszDst
0x18001eec6  call    cs:__imp_SHAnsiToUnicode
0x18001eecc  cmp     eax, 19h
0x18001eecf  jle     short loc_18001EF05
0x18001eed1  mov     ebx, 8000FFFFh
0x18001eed6  mov     rcx, rsi; pvar
0x18001eed9  call    cs:__imp_PropVariantClear
0x18001eedf  mov     eax, ebx
0x18001eee1  mov     rcx, [rbp+var_10]
0x18001eee5  xor     rcx, rsp; StackCookie
0x18001eee8  call    __security_check_cookie
0x18001eeed  lea     r11, [rsp+80h+var_s0]
0x18001eef5  mov     rbx, [r11+30h]
0x18001eef9  mov     rsi, [r11+38h]
0x18001eefd  mov     rsp, r11
0x18001ef00  pop     r14
0x18001ef02  pop     rdi
0x18001ef03  pop     rbp
0x18001ef04  retn
0x18001ef05  mov     rcx, [rdi]; unsigned __int16 *
0x18001ef08  call    ?RemoveISO8601TimeZoneOffset@@YAXPEAG@Z; RemoveISO8601TimeZoneOffset(ushort *)
0x18001ef0d  xor     ebx, ebx
0x18001ef0f  jmp     short loc_18001EEDF
```
