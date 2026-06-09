# ConvertDateToXMPStringOnWrite(tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x18001fc4c`
- end: `0x18001fdfe`
- name: `?ConvertDateToXMPStringOnWrite@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z`
- size: `434`
- prototype: `int(const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d860`

## callees

- `0x1800096a0`
- `0x18000ea14`
- `0x180010950`
- `0x180016a40`
- `0x18001fc4c`
- `0x180022b44`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001fc7b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001fdbf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001fc7b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001fdbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fcb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fcb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd20`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001fca9`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001fca9`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x18001fd10`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x18001fd10`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x18001fda6`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x18001fda6`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18001fcf2`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18001fcf2`

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
0x18001fc4c  mov     [rsp-18h+arg_10], rbx
0x18001fc51  mov     [rsp-18h+arg_18], rsi
0x18001fc56  push    rbp
0x18001fc57  push    rdi
0x18001fc58  push    r14
0x18001fc5a  mov     rbp, rsp
0x18001fc5d  sub     rsp, 80h
0x18001fc64  mov     rax, cs:__security_cookie
0x18001fc6b  xor     rax, rsp
0x18001fc6e  mov     [rbp+var_10], rax
0x18001fc72  mov     rdi, rcx
0x18001fc75  mov     rsi, rdx
0x18001fc78  mov     rcx, rdx; pvar
0x18001fc7b  call    cs:__imp_PropVariantClear
0x18001fc82  nop     dword ptr [rax+rax+00h]
0x18001fc87  cmp     word ptr [rdi], 40h ; '@'
0x18001fc8b  xorps   xmm0, xmm0
0x18001fc8e  xorps   xmm1, xmm1
0x18001fc91  mov     r14d, 80070000h
0x18001fc97  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18001fc9b  movups  xmmword ptr [rbp+LocalTime.wYear], xmm1
0x18001fc9f  jnz     short loc_18001FCDA
0x18001fca1  lea     rcx, [rdi+8]; lpFileTime
0x18001fca5  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x18001fca9  call    cs:__imp_FileTimeToSystemTime
0x18001fcb0  nop     dword ptr [rax+rax+00h]
0x18001fcb5  test    eax, eax
0x18001fcb7  jnz     short loc_18001FD06
0x18001fcb9  call    cs:__imp_GetLastError
0x18001fcc0  nop     dword ptr [rax+rax+00h]
0x18001fcc5  mov     ebx, eax
0x18001fcc7  test    eax, eax
0x18001fcc9  jle     short loc_18001FCD1
0x18001fccb  movzx   ebx, ax
0x18001fcce  or      ebx, r14d
0x18001fcd1  test    ebx, ebx
0x18001fcd3  jns     short loc_18001FD06
0x18001fcd5  jmp     loc_18001FDCB
0x18001fcda  cmp     word ptr [rdi], 7
0x18001fcde  mov     ebx, 80070057h
0x18001fce3  jnz     loc_18001FDCB
0x18001fce9  movsd   xmm0, qword ptr [rdi+8]; vtime
0x18001fcee  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x18001fcf2  call    cs:__imp_VariantTimeToSystemTime
0x18001fcf9  nop     dword ptr [rax+rax+00h]
0x18001fcfe  test    eax, eax
0x18001fd00  jz      loc_18001FDCB
0x18001fd06  lea     r8, [rbp+LocalTime]; lpLocalTime
0x18001fd0a  xor     ecx, ecx; lpTimeZoneInformation
0x18001fd0c  lea     rdx, [rbp+SystemTime]; lpUniversalTime
0x18001fd10  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x18001fd17  nop     dword ptr [rax+rax+00h]
0x18001fd1c  test    eax, eax
0x18001fd1e  jnz     short loc_18001FD40
0x18001fd20  call    cs:__imp_GetLastError
0x18001fd27  nop     dword ptr [rax+rax+00h]
0x18001fd2c  mov     ebx, eax
0x18001fd2e  test    eax, eax
0x18001fd30  jle     short loc_18001FD38
0x18001fd32  movzx   ebx, ax
0x18001fd35  or      ebx, r14d
0x18001fd38  test    ebx, ebx
0x18001fd3a  js      loc_18001FDCB
0x18001fd40  mov     edx, 2; ullMultiplier
0x18001fd45  mov     [rbp+pullResult], 0
0x18001fd4d  lea     r8, [rbp+pullResult]; pullResult
0x18001fd51  lea     ecx, [rdx+17h]; ullMultiplicand
0x18001fd54  call    ULongLongMult
0x18001fd59  mov     ebx, eax
0x18001fd5b  test    eax, eax
0x18001fd5d  js      short loc_18001FDCB
0x18001fd5f  mov     rcx, [rbp+pullResult]; Size
0x18001fd63  lea     rdi, [rsi+8]
0x18001fd67  mov     rdx, rdi; void **
0x18001fd6a  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x18001fd6f  mov     ebx, eax
0x18001fd71  test    eax, eax
0x18001fd73  js      short loc_18001FDCB
0x18001fd75  movaps  xmm0, xmmword ptr [rbp+LocalTime.wYear]
0x18001fd79  lea     r8, [rbp+pszSrc]
0x18001fd7d  mov     r14, [rdi]
0x18001fd80  lea     rcx, [rbp+pullResult]
0x18001fd84  movdqa  xmmword ptr [rbp+pullResult], xmm0
0x18001fd89  mov     word ptr [rsi], 1Fh
0x18001fd8e  call    _SysTimeToiso8601
0x18001fd93  mov     ebx, eax
0x18001fd95  test    eax, eax
0x18001fd97  js      short loc_18001FDBC
0x18001fd99  mov     r8d, 19h; cwchBuf
0x18001fd9f  lea     rcx, [rbp+pszSrc]; pszSrc
0x18001fda3  mov     rdx, r14; pwszDst
0x18001fda6  call    cs:__imp_SHAnsiToUnicode
0x18001fdad  nop     dword ptr [rax+rax+00h]
0x18001fdb2  cmp     eax, 19h
0x18001fdb5  jle     short loc_18001FDF2
0x18001fdb7  mov     ebx, 8000FFFFh
0x18001fdbc  mov     rcx, rsi; pvar
0x18001fdbf  call    cs:__imp_PropVariantClear
0x18001fdc6  nop     dword ptr [rax+rax+00h]
0x18001fdcb  mov     eax, ebx
0x18001fdcd  mov     rcx, [rbp+var_10]
0x18001fdd1  xor     rcx, rsp; StackCookie
0x18001fdd4  call    __security_check_cookie
0x18001fdd9  lea     r11, [rsp+80h+var_s0]
0x18001fde1  mov     rbx, [r11+30h]
0x18001fde5  mov     rsi, [r11+38h]
0x18001fde9  mov     rsp, r11
0x18001fdec  pop     r14
0x18001fdee  pop     rdi
0x18001fdef  pop     rbp
0x18001fdf0  retn
0x18001fdf2  mov     rcx, [rdi]; unsigned __int16 *
0x18001fdf5  call    ?RemoveISO8601TimeZoneOffset@@YAXPEAG@Z; RemoveISO8601TimeZoneOffset(ushort *)
0x18001fdfa  xor     ebx, ebx
0x18001fdfc  jmp     short loc_18001FDCB
```
