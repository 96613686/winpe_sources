# ConvertDateToExifStringsOnWrite(tagPROPVARIANT const *,tagPROPVARIANT *,tagPROPVARIANT *)

- ea: `0x18001329c`
- end: `0x180013466`
- name: `?ConvertDateToExifStringsOnWrite@@YAJPEBUtagPROPVARIANT@@PEAU1@1@Z`
- size: `458`
- prototype: `int(const struct tagPROPVARIANT *, struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012330`

## callees

- `0x1800076b0`
- `0x180007d90`
- `0x18001329c`
- `0x180016020`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001343b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001343b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013303`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013358`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013303`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013358`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800132f9`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800132f9`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x18001334e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x18001334e`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x180013336`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x180013336`

## pseudocode

```c
__int64 __fastcall ConvertDateToExifStringsOnWrite(
        const struct tagPROPVARIANT *a1,
        struct tagPROPVARIANT *a2,
        struct tagPROPVARIANT *a3)
{
  bool v5; // zf
  signed int v6; // eax
  signed int v7; // ebx
  signed int LastError; // eax
  int wMonth; // r10d
  __int64 wYear; // r9
  unsigned __int16 *bstrVal; // rcx
  int v12; // eax
  PROPVARIANT *v13; // rcx
  unsigned __int16 *v14; // rcx
  unsigned int v15; // edx
  int wDay; // [rsp+28h] [rbp-58h]
  int wHour; // [rsp+30h] [rbp-50h]
  int wMinute; // [rsp+38h] [rbp-48h]
  int wSecond; // [rsp+40h] [rbp-40h]
  struct _SYSTEMTIME LocalTime; // [rsp+50h] [rbp-30h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-20h] BYREF

  *(_OWORD *)&a2->vt = 0;
  a2->bstrblobVal.pData = 0;
  *(_OWORD *)&a3->vt = 0;
  a3->bstrblobVal.pData = 0;
  v5 = a1->vt == 64;
  SystemTime = 0;
  LocalTime = 0;
  if ( !v5 )
  {
    v7 = -2147024809;
    if ( a1->vt != 7 || !VariantTimeToSystemTime(a1->dblVal, &SystemTime) )
      return (unsigned int)v7;
LABEL_9:
    if ( !SystemTimeToTzSpecificLocalTime(0, &SystemTime, &LocalTime) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( v7 < 0 )
        return (unsigned int)v7;
    }
    v7 = CoTaskMemAllocWithInit(0x28u, (void **)&a2->puuid);
    if ( v7 < 0 )
      return (unsigned int)v7;
    wMonth = LocalTime.wMonth;
    wYear = LocalTime.wYear;
    wSecond = LocalTime.wSecond;
    wMinute = LocalTime.wMinute;
    bstrVal = a2->bstrVal;
    wHour = LocalTime.wHour;
    wDay = LocalTime.wDay;
    a2->vt = 31;
    v12 = StringCchPrintfW(
            bstrVal,
            0x14u,
            L"%04d:%02d:%02d %02d:%02d:%02d",
            wYear,
            wMonth,
            wDay,
            wHour,
            wMinute,
            wSecond);
    v7 = v12;
    if ( v12 == -2147024774 )
    {
      v7 = -2147024809;
    }
    else if ( v12 >= 0 )
    {
      v7 = CoTaskMemAllocWithInit(6u, (void **)&a3->puuid);
      if ( v7 < 0 )
        return (unsigned int)v7;
      v14 = a3->bstrVal;
      v15 = LocalTime.wMilliseconds + 5;
      a3->vt = 31;
      v7 = StringCchPrintfW(v14, 3u, L"%02d", v15 / 0xA);
      if ( v7 >= 0 )
        return (unsigned int)v7;
      v13 = a3;
LABEL_21:
      PropVariantClear(v13);
      return (unsigned int)v7;
    }
    v13 = a2;
    goto LABEL_21;
  }
  if ( FileTimeToSystemTime(&a1->filetime, &SystemTime) )
    goto LABEL_9;
  v6 = GetLastError();
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 >= 0 )
    goto LABEL_9;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001329c  mov     [rsp-28h+arg_18], rbx
0x1800132a1  push    rbp
0x1800132a2  push    rsi
0x1800132a3  push    rdi
0x1800132a4  push    r12
0x1800132a6  push    r14
0x1800132a8  mov     rbp, rsp
0x1800132ab  sub     rsp, 80h
0x1800132b2  mov     rax, cs:__security_cookie
0x1800132b9  xor     rax, rsp
0x1800132bc  mov     [rbp+var_10], rax
0x1800132c0  xor     eax, eax
0x1800132c2  xorps   xmm0, xmm0
0x1800132c5  movups  xmmword ptr [rdx], xmm0
0x1800132c8  mov     [rdx+10h], rax
0x1800132cc  mov     rsi, r8
0x1800132cf  xorps   xmm1, xmm1
0x1800132d2  mov     rdi, rdx
0x1800132d5  movups  xmmword ptr [r8], xmm1
0x1800132d9  mov     [r8+10h], rax
0x1800132dd  mov     r14d, 80070000h
0x1800132e3  cmp     word ptr [rcx], 40h ; '@'
0x1800132e7  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x1800132eb  movups  xmmword ptr [rbp+LocalTime.wYear], xmm1
0x1800132ef  jnz     short loc_18001331E
0x1800132f1  add     rcx, 8; lpFileTime
0x1800132f5  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x1800132f9  call    cs:__imp_FileTimeToSystemTime
0x1800132ff  test    eax, eax
0x180013301  jnz     short loc_180013344
0x180013303  call    cs:__imp_GetLastError
0x180013309  mov     ebx, eax
0x18001330b  test    eax, eax
0x18001330d  jle     short loc_180013315
0x18001330f  movzx   ebx, ax
0x180013312  or      ebx, r14d
0x180013315  test    ebx, ebx
0x180013317  jns     short loc_180013344
0x180013319  jmp     loc_180013441
0x18001331e  cmp     word ptr [rcx], 7
0x180013322  mov     ebx, 80070057h
0x180013327  jnz     loc_180013441
0x18001332d  movsd   xmm0, qword ptr [rcx+8]; vtime
0x180013332  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x180013336  call    cs:__imp_VariantTimeToSystemTime
0x18001333c  test    eax, eax
0x18001333e  jz      loc_180013441
0x180013344  lea     r8, [rbp+LocalTime]; lpLocalTime
0x180013348  xor     ecx, ecx; lpTimeZoneInformation
0x18001334a  lea     rdx, [rbp+SystemTime]; lpUniversalTime
0x18001334e  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x180013354  test    eax, eax
0x180013356  jnz     short loc_180013372
0x180013358  call    cs:__imp_GetLastError
0x18001335e  mov     ebx, eax
0x180013360  test    eax, eax
0x180013362  jle     short loc_18001336A
0x180013364  movzx   ebx, ax
0x180013367  or      ebx, r14d
0x18001336a  test    ebx, ebx
0x18001336c  js      loc_180013441
0x180013372  lea     rdx, [rdi+8]; void **
0x180013376  mov     ecx, 28h ; '('; Size
0x18001337b  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x180013380  mov     ebx, eax
0x180013382  test    eax, eax
0x180013384  js      loc_180013441
0x18001338a  movzx   ecx, [rbp+LocalTime.wMinute]
0x18001338e  mov     r12d, 1Fh
0x180013394  movzx   edx, [rbp+LocalTime.wHour]
0x180013398  movzx   r8d, [rbp+LocalTime.wDay]
0x18001339d  movzx   eax, [rbp+LocalTime.wSecond]
0x1800133a1  movzx   r10d, [rbp+LocalTime.wMonth]
0x1800133a6  movzx   r9d, [rbp+LocalTime.wYear]
0x1800133ab  mov     [rsp+80h+var_40], eax
0x1800133af  mov     [rsp+80h+var_48], ecx
0x1800133b3  mov     rcx, [rdi+8]; unsigned __int16 *
0x1800133b7  mov     [rsp+80h+var_50], edx
0x1800133bb  lea     edx, [r12-0Bh]; unsigned __int64
0x1800133c0  mov     [rsp+80h+var_58], r8d
0x1800133c5  lea     r8, a04d02d02d02d02; "%04d:%02d:%02d %02d:%02d:%02d"
0x1800133cc  mov     [rdi], r12w
0x1800133d0  mov     [rsp+80h+var_60], r10d
0x1800133d5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800133da  mov     ebx, eax
0x1800133dc  cmp     eax, 8007007Ah
0x1800133e1  jnz     short loc_1800133E8
0x1800133e3  lea     ebx, [rax-23h]
0x1800133e6  jmp     short loc_1800133EC
0x1800133e8  test    eax, eax
0x1800133ea  jns     short loc_1800133F1
0x1800133ec  mov     rcx, rdi
0x1800133ef  jmp     short loc_18001343B
0x1800133f1  lea     rdx, [rsi+8]; void **
0x1800133f5  mov     ecx, 6; Size
0x1800133fa  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x1800133ff  mov     ebx, eax
0x180013401  test    eax, eax
0x180013403  js      short loc_180013441
0x180013405  movzx   edx, [rbp+LocalTime.wMilliseconds]
0x180013409  lea     r8, a02d; "%02d"
0x180013410  mov     rcx, [rsi+8]; unsigned __int16 *
0x180013414  add     edx, 5
0x180013417  mov     eax, 0CCCCCCCDh
0x18001341c  mov     [rsi], r12w
0x180013420  mul     edx
0x180013422  shr     edx, 3
0x180013425  mov     r9d, edx
0x180013428  mov     edx, 3; unsigned __int64
0x18001342d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013432  mov     ebx, eax
0x180013434  test    eax, eax
0x180013436  jns     short loc_180013441
0x180013438  mov     rcx, rsi; pvar
0x18001343b  call    cs:__imp_PropVariantClear
0x180013441  mov     eax, ebx
0x180013443  mov     rcx, [rbp+var_10]
0x180013447  xor     rcx, rsp; StackCookie
0x18001344a  call    __security_check_cookie
0x18001344f  mov     rbx, [rsp+80h+arg_18]
0x180013457  add     rsp, 80h
0x18001345e  pop     r14
0x180013460  pop     r12
0x180013462  pop     rdi
0x180013463  pop     rsi
0x180013464  pop     rbp
0x180013465  retn
```
