# ConvertExifDateStringsOnRead(tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x18000c7bc`
- end: `0x18000c962`
- name: `?ConvertExifDateStringsOnRead@@YAJPEBUtagPROPVARIANT@@0PEAU1@@Z`
- size: `422`
- prototype: `__int64 __fastcall(const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c300`

## callees

- `0x18000c7bc`
- `0x180016020`
- `0x180016ab8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c8e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c8e9`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x18000c8a2`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x18000c8a2`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000c8b4`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000c8b4`

## pseudocode

```c
__int64 __fastcall ConvertExifDateStringsOnRead(
        const struct tagPROPVARIANT *a1,
        const struct tagPROPVARIANT *a2,
        struct tagPROPVARIANT *a3)
{
  bool v3; // zf
  int v6; // ebx
  signed int LastError; // eax
  SYSTEMTIME LocalTime; // [rsp+40h] [rbp-30h] BYREF
  struct _SYSTEMTIME UniversalTime; // [rsp+50h] [rbp-20h] BYREF

  *(_OWORD *)&a3->vt = 0;
  a3->bstrblobVal.pData = 0;
  v3 = a1->vt == 31;
  LocalTime = 0;
  if ( v3 )
  {
    v6 = -2147467259;
    if ( swscanf_s(
           a1->bstrVal,
           L"%4hd:%2hd:%2hd %2hd:%2hd:%2hd",
           &LocalTime,
           &LocalTime.wMonth,
           &LocalTime.wDay,
           &LocalTime.wHour,
           &LocalTime.wMinute,
           &LocalTime.wSecond) >= 1 )
      v6 = 0;
  }
  else
  {
    v6 = -2147024809;
  }
  if ( !a2->vt )
    goto LABEL_8;
  if ( a2->vt != 31 )
  {
    if ( a2->vt != 4127 )
      return (unsigned int)-2147024809;
    if ( a2->lVal && swscanf_s(*(const wchar_t *const *)a2->bstrblobVal.pData, L"%2hd", &LocalTime.wMilliseconds) >= 1 )
    {
      v6 = 0;
      LocalTime.wMilliseconds *= 10;
    }
LABEL_8:
    if ( v6 < 0 )
      return (unsigned int)v6;
    goto LABEL_9;
  }
  if ( swscanf_s(a2->bstrVal, L"%2hd", &LocalTime.wMilliseconds) < 1 )
    goto LABEL_8;
  LocalTime.wMilliseconds *= 10;
LABEL_9:
  if ( LocalTime.wYear )
  {
    UniversalTime = 0;
    if ( TzSpecificLocalTimeToSystemTime(0, &LocalTime, &UniversalTime)
      && SystemTimeToFileTime(&UniversalTime, &a3->filetime) )
    {
      a3->vt = 64;
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000c7bc  mov     r11, rsp
0x18000c7bf  push    rbp
0x18000c7c0  push    rbx
0x18000c7c1  push    rsi
0x18000c7c2  push    rdi
0x18000c7c3  push    r14
0x18000c7c5  mov     rbp, rsp
0x18000c7c8  sub     rsp, 70h
0x18000c7cc  mov     rax, cs:__security_cookie
0x18000c7d3  xor     rax, rsp
0x18000c7d6  mov     [rbp+var_10], rax
0x18000c7da  xorps   xmm0, xmm0
0x18000c7dd  xor     eax, eax
0x18000c7df  movups  xmmword ptr [r8], xmm0
0x18000c7e3  xor     r14d, r14d
0x18000c7e6  mov     [r8+10h], rax
0x18000c7ea  cmp     word ptr [rcx], 1Fh
0x18000c7ee  mov     rsi, r8
0x18000c7f1  mov     rdi, rdx
0x18000c7f4  movups  xmmword ptr [rbp+LocalTime.wYear], xmm0
0x18000c7f8  jnz     loc_18000C8DF
0x18000c7fe  mov     rcx, [rcx+8]; Buffer
0x18000c802  lea     rax, [rbp+LocalTime.wSecond]
0x18000c806  mov     [r11-60h], rax
0x18000c80a  lea     r9, [rbp+LocalTime.wMonth]
0x18000c80e  lea     rax, [rbp+LocalTime.wMinute]
0x18000c812  mov     ebx, 80004005h
0x18000c817  mov     [r11-68h], rax
0x18000c81b  lea     r8, [rbp+LocalTime]
0x18000c81f  lea     rax, [rbp+LocalTime.wHour]
0x18000c823  mov     [r11-70h], rax
0x18000c827  lea     rdx, a4hd2hd2hd2hd2h; "%4hd:%2hd:%2hd %2hd:%2hd:%2hd"
0x18000c82e  lea     rax, [rbp+LocalTime.wDay]
0x18000c832  mov     [r11-78h], rax
0x18000c836  call    swscanf_s
0x18000c83b  cmp     eax, 1
0x18000c83e  cmovge  ebx, r14d
0x18000c842  cmp     [rdi], r14w
0x18000c846  jz      short loc_18000C882
0x18000c848  cmp     word ptr [rdi], 1Fh
0x18000c84c  jnz     loc_18000C900
0x18000c852  mov     rcx, [rdi+8]; Buffer
0x18000c856  lea     r8, [rbp+LocalTime.wMilliseconds]
0x18000c85a  lea     rdx, a2hd; "%2hd"
0x18000c861  call    swscanf_s
0x18000c866  cmp     eax, 1
0x18000c869  jl      short loc_18000C882
0x18000c86b  movzx   ecx, [rbp+LocalTime.wMilliseconds]
0x18000c86f  movzx   eax, cx
0x18000c872  shl     ax, 2
0x18000c876  add     cx, ax
0x18000c879  add     cx, cx
0x18000c87c  mov     [rbp+LocalTime.wMilliseconds], cx
0x18000c880  jmp     short loc_18000C886
0x18000c882  test    ebx, ebx
0x18000c884  js      short loc_18000C8C6
0x18000c886  cmp     [rbp+LocalTime.wYear], r14w
0x18000c88b  jz      loc_18000C958
0x18000c891  xorps   xmm0, xmm0
0x18000c894  lea     r8, [rbp+UniversalTime]; lpUniversalTime
0x18000c898  lea     rdx, [rbp+LocalTime]; lpLocalTime
0x18000c89c  xor     ecx, ecx; lpTimeZoneInformation
0x18000c89e  movups  xmmword ptr [rbp+UniversalTime.wYear], xmm0
0x18000c8a2  call    cs:__imp_TzSpecificLocalTimeToSystemTime
0x18000c8a8  test    eax, eax
0x18000c8aa  jz      short loc_18000C8E9
0x18000c8ac  lea     rdx, [rsi+8]; lpFileTime
0x18000c8b0  lea     rcx, [rbp+UniversalTime]; lpSystemTime
0x18000c8b4  call    cs:__imp_SystemTimeToFileTime
0x18000c8ba  test    eax, eax
0x18000c8bc  jz      short loc_18000C8E9
0x18000c8be  mov     word ptr [rsi], 40h ; '@'
0x18000c8c3  mov     ebx, r14d
0x18000c8c6  mov     eax, ebx
0x18000c8c8  mov     rcx, [rbp+var_10]
0x18000c8cc  xor     rcx, rsp; StackCookie
0x18000c8cf  call    __security_check_cookie
0x18000c8d4  add     rsp, 70h
0x18000c8d8  pop     r14
0x18000c8da  pop     rdi
0x18000c8db  pop     rsi
0x18000c8dc  pop     rbx
0x18000c8dd  pop     rbp
0x18000c8de  retn
0x18000c8df  mov     ebx, 80070057h
0x18000c8e4  jmp     loc_18000C842
0x18000c8e9  call    cs:__imp_GetLastError
0x18000c8ef  mov     ebx, eax
0x18000c8f1  test    eax, eax
0x18000c8f3  jle     short loc_18000C8C6
0x18000c8f5  movzx   ebx, ax
0x18000c8f8  or      ebx, 80070000h
0x18000c8fe  jmp     short loc_18000C8C6
0x18000c900  mov     eax, 101Fh
0x18000c905  cmp     [rdi], ax
0x18000c908  jz      short loc_18000C911
0x18000c90a  mov     ebx, 80070057h
0x18000c90f  jmp     short loc_18000C8C6
0x18000c911  cmp     [rdi+8], r14d
0x18000c915  jbe     loc_18000C882
0x18000c91b  mov     rcx, [rdi+10h]
0x18000c91f  lea     r8, [rbp+LocalTime.wMilliseconds]
0x18000c923  lea     rdx, a2hd; "%2hd"
0x18000c92a  mov     rcx, [rcx]; Buffer
0x18000c92d  call    swscanf_s
0x18000c932  cmp     eax, 1
0x18000c935  jl      loc_18000C882
0x18000c93b  movzx   ecx, [rbp+LocalTime.wMilliseconds]
0x18000c93f  mov     ebx, r14d
0x18000c942  movzx   eax, cx
0x18000c945  shl     ax, 2
0x18000c949  add     cx, ax
0x18000c94c  add     cx, cx
0x18000c94f  mov     [rbp+LocalTime.wMilliseconds], cx
0x18000c953  jmp     loc_18000C882
0x18000c958  mov     ebx, 8000FFFFh
0x18000c95d  jmp     loc_18000C8C6
```
