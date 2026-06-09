# ConvertDateToExifStringsOnWrite(tagPROPVARIANT const *,tagPROPVARIANT *,tagPROPVARIANT *)

- ea: `0x180013bf8`
- end: `0x180013de7`
- name: `?ConvertDateToExifStringsOnWrite@@YAJPEBUtagPROPVARIANT@@PEAU1@1@Z`
- size: `495`
- prototype: `int(const struct tagPROPVARIANT *, struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012be0`

## callees

- `0x1800089f0`
- `0x1800096a0`
- `0x180013bf8`
- `0x180016a40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013db5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013db5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013c65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ccc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013c65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ccc`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180013c55`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180013c55`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x180013cbc`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x180013cbc`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x180013c9e`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x180013c9e`

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
0x180013bf8  mov     [rsp-28h+arg_18], rbx
0x180013bfd  push    rbp
0x180013bfe  push    rsi
0x180013bff  push    rdi
0x180013c00  push    r12
0x180013c02  push    r14
0x180013c04  mov     rbp, rsp
0x180013c07  sub     rsp, 80h
0x180013c0e  mov     rax, cs:__security_cookie
0x180013c15  xor     rax, rsp
0x180013c18  mov     [rbp+var_10], rax
0x180013c1c  xor     eax, eax
0x180013c1e  xorps   xmm0, xmm0
0x180013c21  movups  xmmword ptr [rdx], xmm0
0x180013c24  mov     [rdx+10h], rax
0x180013c28  mov     rsi, r8
0x180013c2b  xorps   xmm1, xmm1
0x180013c2e  mov     rdi, rdx
0x180013c31  movups  xmmword ptr [r8], xmm1
0x180013c35  mov     [r8+10h], rax
0x180013c39  mov     r14d, 80070000h
0x180013c3f  cmp     word ptr [rcx], 40h ; '@'
0x180013c43  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180013c47  movups  xmmword ptr [rbp+LocalTime.wYear], xmm1
0x180013c4b  jnz     short loc_180013C86
0x180013c4d  add     rcx, 8; lpFileTime
0x180013c51  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x180013c55  call    cs:__imp_FileTimeToSystemTime
0x180013c5c  nop     dword ptr [rax+rax+00h]
0x180013c61  test    eax, eax
0x180013c63  jnz     short loc_180013CB2
0x180013c65  call    cs:__imp_GetLastError
0x180013c6c  nop     dword ptr [rax+rax+00h]
0x180013c71  mov     ebx, eax
0x180013c73  test    eax, eax
0x180013c75  jle     short loc_180013C7D
0x180013c77  movzx   ebx, ax
0x180013c7a  or      ebx, r14d
0x180013c7d  test    ebx, ebx
0x180013c7f  jns     short loc_180013CB2
0x180013c81  jmp     loc_180013DC1
0x180013c86  cmp     word ptr [rcx], 7
0x180013c8a  mov     ebx, 80070057h
0x180013c8f  jnz     loc_180013DC1
0x180013c95  movsd   xmm0, qword ptr [rcx+8]; vtime
0x180013c9a  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x180013c9e  call    cs:__imp_VariantTimeToSystemTime
0x180013ca5  nop     dword ptr [rax+rax+00h]
0x180013caa  test    eax, eax
0x180013cac  jz      loc_180013DC1
0x180013cb2  lea     r8, [rbp+LocalTime]; lpLocalTime
0x180013cb6  xor     ecx, ecx; lpTimeZoneInformation
0x180013cb8  lea     rdx, [rbp+SystemTime]; lpUniversalTime
0x180013cbc  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x180013cc3  nop     dword ptr [rax+rax+00h]
0x180013cc8  test    eax, eax
0x180013cca  jnz     short loc_180013CEC
0x180013ccc  call    cs:__imp_GetLastError
0x180013cd3  nop     dword ptr [rax+rax+00h]
0x180013cd8  mov     ebx, eax
0x180013cda  test    eax, eax
0x180013cdc  jle     short loc_180013CE4
0x180013cde  movzx   ebx, ax
0x180013ce1  or      ebx, r14d
0x180013ce4  test    ebx, ebx
0x180013ce6  js      loc_180013DC1
0x180013cec  lea     rdx, [rdi+8]; void **
0x180013cf0  mov     ecx, 28h ; '('; Size
0x180013cf5  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x180013cfa  mov     ebx, eax
0x180013cfc  test    eax, eax
0x180013cfe  js      loc_180013DC1
0x180013d04  movzx   ecx, [rbp+LocalTime.wMinute]
0x180013d08  mov     r12d, 1Fh
0x180013d0e  movzx   edx, [rbp+LocalTime.wHour]
0x180013d12  movzx   r8d, [rbp+LocalTime.wDay]
0x180013d17  movzx   eax, [rbp+LocalTime.wSecond]
0x180013d1b  movzx   r10d, [rbp+LocalTime.wMonth]
0x180013d20  movzx   r9d, [rbp+LocalTime.wYear]
0x180013d25  mov     [rsp+80h+var_40], eax
0x180013d29  mov     [rsp+80h+var_48], ecx
0x180013d2d  mov     rcx, [rdi+8]; unsigned __int16 *
0x180013d31  mov     [rsp+80h+var_50], edx
0x180013d35  lea     edx, [r12-0Bh]; unsigned __int64
0x180013d3a  mov     [rsp+80h+var_58], r8d
0x180013d3f  lea     r8, a04d02d02d02d02; "%04d:%02d:%02d %02d:%02d:%02d"
0x180013d46  mov     [rdi], r12w
0x180013d4a  mov     [rsp+80h+var_60], r10d
0x180013d4f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013d54  mov     ebx, eax
0x180013d56  cmp     eax, 8007007Ah
0x180013d5b  jnz     short loc_180013D62
0x180013d5d  lea     ebx, [rax-23h]
0x180013d60  jmp     short loc_180013D66
0x180013d62  test    eax, eax
0x180013d64  jns     short loc_180013D6B
0x180013d66  mov     rcx, rdi
0x180013d69  jmp     short loc_180013DB5
0x180013d6b  lea     rdx, [rsi+8]; void **
0x180013d6f  mov     ecx, 6; Size
0x180013d74  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x180013d79  mov     ebx, eax
0x180013d7b  test    eax, eax
0x180013d7d  js      short loc_180013DC1
0x180013d7f  movzx   edx, [rbp+LocalTime.wMilliseconds]
0x180013d83  lea     r8, a02d; "%02d"
0x180013d8a  mov     rcx, [rsi+8]; unsigned __int16 *
0x180013d8e  add     edx, 5
0x180013d91  mov     eax, 0CCCCCCCDh
0x180013d96  mov     [rsi], r12w
0x180013d9a  mul     edx
0x180013d9c  shr     edx, 3
0x180013d9f  mov     r9d, edx
0x180013da2  mov     edx, 3; unsigned __int64
0x180013da7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013dac  mov     ebx, eax
0x180013dae  test    eax, eax
0x180013db0  jns     short loc_180013DC1
0x180013db2  mov     rcx, rsi; pvar
0x180013db5  call    cs:__imp_PropVariantClear
0x180013dbc  nop     dword ptr [rax+rax+00h]
0x180013dc1  mov     eax, ebx
0x180013dc3  mov     rcx, [rbp+var_10]
0x180013dc7  xor     rcx, rsp; StackCookie
0x180013dca  call    __security_check_cookie
0x180013dcf  mov     rbx, [rsp+80h+arg_18]
0x180013dd7  add     rsp, 80h
0x180013dde  pop     r14
0x180013de0  pop     r12
0x180013de2  pop     rdi
0x180013de3  pop     rsi
0x180013de4  pop     rbp
0x180013de5  retn
```
