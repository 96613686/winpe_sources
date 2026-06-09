# ConvertIPTCDateTimeOnWrite(tagPROPVARIANT const *,tagPROPVARIANT *,tagPROPVARIANT *)

- ea: `0x1800130bc`
- end: `0x180013293`
- name: `?ConvertIPTCDateTimeOnWrite@@YAJPEBUtagPROPVARIANT@@PEAU1@1@Z`
- size: `471`
- prototype: `int(const struct tagPROPVARIANT *, struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012330`

## callees

- `0x1800076b0`
- `0x180007d90`
- `0x18000e364`
- `0x1800130bc`
- `0x180016020`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800130e9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800130f2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013274`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800130e9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800130f2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013274`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013169`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013169`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180013120`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180013120`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x18001315f`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x18001315f`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x180013147`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x180013147`

## pseudocode

```c
__int64 __fastcall ConvertIPTCDateTimeOnWrite(
        const struct tagPROPVARIANT *a1,
        struct tagPROPVARIANT *a2,
        struct tagPROPVARIANT *a3)
{
  signed int v6; // ebx
  bool v7; // zf
  BOOL v8; // eax
  signed int LastError; // eax
  __int64 wYear; // r9
  unsigned __int16 *bstrVal; // rcx
  int v12; // eax
  PROPVARIANT *v13; // rcx
  __int64 wHour; // r9
  unsigned __int16 *v15; // rcx
  int wMonth; // [rsp+20h] [rbp-40h]
  __int64 v18; // [rsp+20h] [rbp-40h]
  int wDay; // [rsp+28h] [rbp-38h]
  __int64 v20; // [rsp+28h] [rbp-38h]
  ULONGLONG pullResult; // [rsp+30h] [rbp-30h] BYREF
  struct _SYSTEMTIME LocalTime; // [rsp+38h] [rbp-28h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-18h] BYREF

  v6 = -2147024809;
  PropVariantClear(a2);
  PropVariantClear(a3);
  v7 = a1->vt == 7;
  SystemTime = 0;
  LocalTime = 0;
  if ( v7 )
  {
    if ( !VariantTimeToSystemTime(a1->dblVal, &SystemTime) )
      return (unsigned int)v6;
  }
  else
  {
    if ( a1->vt != 64 )
      return (unsigned int)v6;
    v8 = FileTimeToSystemTime(&a1->filetime, &SystemTime);
    v6 = !v8 ? 0x80070057 : 0;
    if ( !v8 )
      return (unsigned int)v6;
  }
  if ( SystemTimeToTzSpecificLocalTime(0, &SystemTime, &LocalTime) )
    goto LABEL_24;
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( v6 >= 0 )
  {
LABEL_24:
    pullResult = 0;
    v6 = ULongLongMult(9u, 2u, &pullResult);
    if ( v6 >= 0 )
    {
      v6 = CoTaskMemAllocWithInit(pullResult, (void **)&a2->puuid);
      if ( v6 >= 0 )
      {
        wYear = LocalTime.wYear;
        wDay = LocalTime.wDay;
        wMonth = LocalTime.wMonth;
        bstrVal = a2->bstrVal;
        a2->vt = 31;
        v12 = StringCchPrintfW(bstrVal, 9u, L"%04u%02u%02u", wYear, wMonth, wDay);
        v6 = v12;
        if ( v12 == -2147024774 )
        {
          v6 = -2147024809;
        }
        else if ( v12 >= 0 )
        {
          pullResult = 0;
          v6 = ULongLongMult(0xCu, 2u, &pullResult);
          if ( v6 < 0 )
            return (unsigned int)v6;
          v6 = CoTaskMemAllocWithInit(pullResult, (void **)&a3->puuid);
          if ( v6 < 0 )
            return (unsigned int)v6;
          wHour = LocalTime.wHour;
          v15 = a3->bstrVal;
          LODWORD(v20) = LocalTime.wSecond;
          LODWORD(v18) = LocalTime.wMinute;
          a3->vt = 31;
          v6 = StringCchPrintfW(v15, 0xCu, L"%02u%02u%02u+0000", wHour, v18, v20);
          if ( v6 >= 0 )
            return (unsigned int)v6;
          v13 = a3;
LABEL_20:
          PropVariantClear(v13);
          return (unsigned int)v6;
        }
        v13 = a2;
        goto LABEL_20;
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800130bc  push    rbp
0x1800130be  push    rbx
0x1800130bf  push    rsi
0x1800130c0  push    rdi
0x1800130c1  push    r14
0x1800130c3  mov     rbp, rsp
0x1800130c6  sub     rsp, 60h
0x1800130ca  mov     rax, cs:__security_cookie
0x1800130d1  xor     rax, rsp
0x1800130d4  mov     [rbp+var_8], rax
0x1800130d8  mov     r14, rcx
0x1800130db  mov     rsi, r8
0x1800130de  mov     rcx, rdx; pvar
0x1800130e1  mov     rdi, rdx
0x1800130e4  mov     ebx, 80070057h
0x1800130e9  call    cs:__imp_PropVariantClear
0x1800130ef  mov     rcx, rsi; pvar
0x1800130f2  call    cs:__imp_PropVariantClear
0x1800130f8  cmp     word ptr [r14], 7
0x1800130fd  xorps   xmm0, xmm0
0x180013100  xorps   xmm1, xmm1
0x180013103  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180013107  movups  xmmword ptr [rbp+LocalTime.wYear], xmm1
0x18001310b  jz      short loc_18001313D
0x18001310d  cmp     word ptr [r14], 40h ; '@'
0x180013112  jnz     loc_18001327A
0x180013118  lea     rcx, [r14+8]; lpFileTime
0x18001311c  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x180013120  call    cs:__imp_FileTimeToSystemTime
0x180013126  mov     ecx, eax
0x180013128  neg     eax
0x18001312a  sbb     ebx, ebx
0x18001312c  not     ebx
0x18001312e  and     ebx, 80070057h
0x180013134  test    ecx, ecx
0x180013136  jnz     short loc_180013155
0x180013138  jmp     loc_18001327A
0x18001313d  movsd   xmm0, qword ptr [r14+8]; vtime
0x180013143  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x180013147  call    cs:__imp_VariantTimeToSystemTime
0x18001314d  test    eax, eax
0x18001314f  jz      loc_18001327A
0x180013155  lea     r8, [rbp+LocalTime]; lpLocalTime
0x180013159  xor     ecx, ecx; lpTimeZoneInformation
0x18001315b  lea     rdx, [rbp+SystemTime]; lpUniversalTime
0x18001315f  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x180013165  test    eax, eax
0x180013167  jnz     short loc_180013186
0x180013169  call    cs:__imp_GetLastError
0x18001316f  mov     ebx, eax
0x180013171  test    eax, eax
0x180013173  jle     short loc_18001317E
0x180013175  movzx   ebx, ax
0x180013178  or      ebx, 80070000h
0x18001317e  test    ebx, ebx
0x180013180  js      loc_18001327A
0x180013186  mov     edx, 2; ullMultiplier
0x18001318b  mov     [rbp+pullResult], 0
0x180013193  lea     r8, [rbp+pullResult]; pullResult
0x180013197  lea     ecx, [rdx+7]; ullMultiplicand
0x18001319a  call    ULongLongMult
0x18001319f  mov     ebx, eax
0x1800131a1  test    eax, eax
0x1800131a3  js      loc_18001327A
0x1800131a9  mov     rcx, [rbp+pullResult]; Size
0x1800131ad  lea     rdx, [rdi+8]; void **
0x1800131b1  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x1800131b6  mov     ebx, eax
0x1800131b8  test    eax, eax
0x1800131ba  js      loc_18001327A
0x1800131c0  movzx   ecx, [rbp+LocalTime.wMonth]
0x1800131c4  lea     r8, a04u02u02u; "%04u%02u%02u"
0x1800131cb  movzx   eax, [rbp+LocalTime.wDay]
0x1800131cf  mov     edx, 9; unsigned __int64
0x1800131d4  movzx   r9d, [rbp+LocalTime.wYear]
0x1800131d9  mov     dword ptr [rsp+60h+var_38], eax
0x1800131dd  mov     dword ptr [rsp+60h+var_40], ecx
0x1800131e1  mov     rcx, [rdi+8]; unsigned __int16 *
0x1800131e5  mov     word ptr [rdi], 1Fh
0x1800131ea  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800131ef  mov     ebx, eax
0x1800131f1  cmp     eax, 8007007Ah
0x1800131f6  jnz     short loc_1800131FD
0x1800131f8  lea     ebx, [rax-23h]
0x1800131fb  jmp     short loc_180013201
0x1800131fd  test    eax, eax
0x1800131ff  jns     short loc_180013206
0x180013201  mov     rcx, rdi
0x180013204  jmp     short loc_180013274
0x180013206  mov     edx, 2; ullMultiplier
0x18001320b  mov     [rbp+pullResult], 0
0x180013213  lea     r8, [rbp+pullResult]; pullResult
0x180013217  lea     r14d, [rdx+0Ah]
0x18001321b  mov     ecx, r14d; ullMultiplicand
0x18001321e  call    ULongLongMult
0x180013223  mov     ebx, eax
0x180013225  test    eax, eax
0x180013227  js      short loc_18001327A
0x180013229  mov     rcx, [rbp+pullResult]; Size
0x18001322d  lea     rdx, [rsi+8]; void **
0x180013231  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x180013236  mov     ebx, eax
0x180013238  test    eax, eax
0x18001323a  js      short loc_18001327A
0x18001323c  movzx   r8d, [rbp+LocalTime.wMinute]
0x180013241  mov     edx, r14d; unsigned __int64
0x180013244  movzx   eax, [rbp+LocalTime.wSecond]
0x180013248  movzx   r9d, [rbp+LocalTime.wHour]
0x18001324d  mov     rcx, [rsi+8]; unsigned __int16 *
0x180013251  mov     dword ptr [rsp+60h+var_38], eax
0x180013255  mov     dword ptr [rsp+60h+var_40], r8d
0x18001325a  lea     r8, a02u02u02u0000; "%02u%02u%02u+0000"
0x180013261  mov     word ptr [rsi], 1Fh
0x180013266  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001326b  mov     ebx, eax
0x18001326d  test    eax, eax
0x18001326f  jns     short loc_18001327A
0x180013271  mov     rcx, rsi; pvar
0x180013274  call    cs:__imp_PropVariantClear
0x18001327a  mov     eax, ebx
0x18001327c  mov     rcx, [rbp+var_8]
0x180013280  xor     rcx, rsp; StackCookie
0x180013283  call    __security_check_cookie
0x180013288  add     rsp, 60h
0x18001328c  pop     r14
0x18001328e  pop     rdi
0x18001328f  pop     rsi
0x180013290  pop     rbx
0x180013291  pop     rbp
0x180013292  retn
```
