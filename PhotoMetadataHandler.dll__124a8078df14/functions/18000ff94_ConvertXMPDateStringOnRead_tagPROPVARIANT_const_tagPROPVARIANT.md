# ConvertXMPDateStringOnRead(tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x18000ff94`
- end: `0x18001007b`
- name: `?ConvertXMPDateStringOnRead@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z`
- size: `231`
- prototype: `int(const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000ef00`

## callees

- `0x18000dda0`
- `0x18000ff94`
- `0x18001014c`
- `0x180016020`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ffba`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ffba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001004d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001004d`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x180010028`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x180010028`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001003a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001003a`

## pseudocode

```c
int __fastcall ConvertXMPDateStringOnRead(const struct tagPROPVARIANT *a1, struct tagPROPVARIANT *a2)
{
  bool v4; // zf
  int result; // eax
  const unsigned __int16 *bstrVal; // rcx
  int v7; // [rsp+20h] [rbp-30h] BYREF
  SYSTEMTIME LocalTime; // [rsp+28h] [rbp-28h] BYREF
  struct _SYSTEMTIME UniversalTime; // [rsp+38h] [rbp-18h] BYREF

  PropVariantClear(a2);
  v4 = a1->vt == 31;
  LocalTime = 0;
  result = -2147024809;
  UniversalTime = 0;
  if ( v4 )
  {
    RemoveISO8601TimeZoneOffset(a1->bstrVal);
    bstrVal = a1->bstrVal;
    v7 = -1;
    result = ISO8601ToSYSTEMTIMEExW(bstrVal, &LocalTime, (enum Iso8601ParsingStage *)&v7);
    if ( result >= 0 && v7 < 2 )
    {
      LocalTime.wDay = 1;
      if ( v7 < 1 )
        LocalTime.wMonth = 1;
      result = 0;
    }
  }
  if ( LocalTime.wYear )
  {
    if ( TzSpecificLocalTimeToSystemTime(0, &LocalTime, &UniversalTime)
      && SystemTimeToFileTime(&UniversalTime, &a2->filetime) )
    {
      a2->vt = 64;
      return 0;
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000ff94  mov     [rsp-18h+arg_10], rbx
0x18000ff99  push    rbp
0x18000ff9a  push    rsi
0x18000ff9b  push    rdi
0x18000ff9c  mov     rbp, rsp
0x18000ff9f  sub     rsp, 50h
0x18000ffa3  mov     rax, cs:__security_cookie
0x18000ffaa  xor     rax, rsp
0x18000ffad  mov     [rbp+var_8], rax
0x18000ffb1  mov     rdi, rcx
0x18000ffb4  mov     rbx, rdx
0x18000ffb7  mov     rcx, rdx; pvar
0x18000ffba  call    cs:__imp_PropVariantClear
0x18000ffc0  xor     esi, esi
0x18000ffc2  xorps   xmm0, xmm0
0x18000ffc5  cmp     word ptr [rdi], 1Fh
0x18000ffc9  xorps   xmm1, xmm1
0x18000ffcc  movups  xmmword ptr [rbp+LocalTime.wYear], xmm0
0x18000ffd0  mov     eax, 80070057h
0x18000ffd5  movups  xmmword ptr [rbp+UniversalTime.wYear], xmm1
0x18000ffd9  jnz     short loc_180010018
0x18000ffdb  mov     rcx, [rdi+8]; unsigned __int16 *
0x18000ffdf  call    ?RemoveISO8601TimeZoneOffset@@YAXPEAG@Z; RemoveISO8601TimeZoneOffset(ushort *)
0x18000ffe4  mov     rcx, [rdi+8]; unsigned __int16 *
0x18000ffe8  lea     r8, [rbp+var_30]; enum Iso8601ParsingStage *
0x18000ffec  lea     rdx, [rbp+LocalTime]; struct _SYSTEMTIME *
0x18000fff0  mov     [rbp+var_30], 0FFFFFFFFh
0x18000fff7  call    ?ISO8601ToSYSTEMTIMEExW@@YAJPEBGPEAU_SYSTEMTIME@@PEAW4Iso8601ParsingStage@@@Z; ISO8601ToSYSTEMTIMEExW(ushort const *,_SYSTEMTIME *,Iso8601ParsingStage *)
0x18000fffc  test    eax, eax
0x18000fffe  js      short loc_180010018
0x180010000  cmp     [rbp+var_30], 2
0x180010004  jge     short loc_180010018
0x180010006  lea     eax, [rsi+1]
0x180010009  mov     [rbp+LocalTime.wDay], ax
0x18001000d  cmp     [rbp+var_30], eax
0x180010010  jge     short loc_180010016
0x180010012  mov     [rbp+LocalTime.wMonth], ax
0x180010016  mov     eax, esi
0x180010018  cmp     [rbp+LocalTime.wYear], si
0x18001001c  jz      short loc_18001005F
0x18001001e  lea     r8, [rbp+UniversalTime]; lpUniversalTime
0x180010022  xor     ecx, ecx; lpTimeZoneInformation
0x180010024  lea     rdx, [rbp+LocalTime]; lpLocalTime
0x180010028  call    cs:__imp_TzSpecificLocalTimeToSystemTime
0x18001002e  test    eax, eax
0x180010030  jz      short loc_18001004D
0x180010032  lea     rdx, [rbx+8]; lpFileTime
0x180010036  lea     rcx, [rbp+UniversalTime]; lpSystemTime
0x18001003a  call    cs:__imp_SystemTimeToFileTime
0x180010040  test    eax, eax
0x180010042  jz      short loc_18001004D
0x180010044  mov     word ptr [rbx], 40h ; '@'
0x180010049  mov     eax, esi
0x18001004b  jmp     short loc_18001005F
0x18001004d  call    cs:__imp_GetLastError
0x180010053  test    eax, eax
0x180010055  jle     short loc_18001005F
0x180010057  movzx   eax, ax
0x18001005a  or      eax, 80070000h
0x18001005f  mov     rcx, [rbp+var_8]
0x180010063  xor     rcx, rsp; StackCookie
0x180010066  call    __security_check_cookie
0x18001006b  mov     rbx, [rsp+50h+arg_10]
0x180010073  add     rsp, 50h
0x180010077  pop     rdi
0x180010078  pop     rsi
0x180010079  pop     rbp
0x18001007a  retn
```
