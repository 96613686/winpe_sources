# ConvertExifDateStringsOnRead(tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x18000cde0`
- end: `0x18000cf99`
- name: `?ConvertExifDateStringsOnRead@@YAJPEBUtagPROPVARIANT@@0PEAU1@@Z`
- size: `441`
- prototype: `__int64 __fastcall(const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c8e0`

## callees

- `0x18000cde0`
- `0x180016a40`
- `0x180017508`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf1a`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x18000cec6`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x18000cec6`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000cede`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000cede`

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
0x18000cde0  mov     r11, rsp
0x18000cde3  push    rbp
0x18000cde4  push    rbx
0x18000cde5  push    rsi
0x18000cde6  push    rdi
0x18000cde7  push    r14
0x18000cde9  mov     rbp, rsp
0x18000cdec  sub     rsp, 70h
0x18000cdf0  mov     rax, cs:__security_cookie
0x18000cdf7  xor     rax, rsp
0x18000cdfa  mov     [rbp+var_10], rax
0x18000cdfe  xorps   xmm0, xmm0
0x18000ce01  xor     eax, eax
0x18000ce03  movups  xmmword ptr [r8], xmm0
0x18000ce07  xor     r14d, r14d
0x18000ce0a  mov     [r8+10h], rax
0x18000ce0e  cmp     word ptr [rcx], 1Fh
0x18000ce12  mov     rsi, r8
0x18000ce15  mov     rdi, rdx
0x18000ce18  movups  xmmword ptr [rbp+LocalTime.wYear], xmm0
0x18000ce1c  jnz     loc_18000CF10
0x18000ce22  mov     rcx, [rcx+8]; Buffer
0x18000ce26  lea     rax, [rbp+LocalTime.wSecond]
0x18000ce2a  mov     [r11-60h], rax
0x18000ce2e  lea     r9, [rbp+LocalTime.wMonth]
0x18000ce32  lea     rax, [rbp+LocalTime.wMinute]
0x18000ce36  mov     ebx, 80004005h
0x18000ce3b  mov     [r11-68h], rax
0x18000ce3f  lea     r8, [rbp+LocalTime]
0x18000ce43  lea     rax, [rbp+LocalTime.wHour]
0x18000ce47  mov     [r11-70h], rax
0x18000ce4b  lea     rdx, a4hd2hd2hd2hd2h; "%4hd:%2hd:%2hd %2hd:%2hd:%2hd"
0x18000ce52  lea     rax, [rbp+LocalTime.wDay]
0x18000ce56  mov     [r11-78h], rax
0x18000ce5a  call    swscanf_s
0x18000ce5f  cmp     eax, 1
0x18000ce62  cmovge  ebx, r14d
0x18000ce66  cmp     [rdi], r14w
0x18000ce6a  jz      short loc_18000CEA6
0x18000ce6c  cmp     word ptr [rdi], 1Fh
0x18000ce70  jnz     loc_18000CF37
0x18000ce76  mov     rcx, [rdi+8]; Buffer
0x18000ce7a  lea     r8, [rbp+LocalTime.wMilliseconds]
0x18000ce7e  lea     rdx, a2hd; "%2hd"
0x18000ce85  call    swscanf_s
0x18000ce8a  cmp     eax, 1
0x18000ce8d  jl      short loc_18000CEA6
0x18000ce8f  movzx   ecx, [rbp+LocalTime.wMilliseconds]
0x18000ce93  movzx   eax, cx
0x18000ce96  shl     ax, 2
0x18000ce9a  add     cx, ax
0x18000ce9d  add     cx, cx
0x18000cea0  mov     [rbp+LocalTime.wMilliseconds], cx
0x18000cea4  jmp     short loc_18000CEAA
0x18000cea6  test    ebx, ebx
0x18000cea8  js      short loc_18000CEF6
0x18000ceaa  cmp     [rbp+LocalTime.wYear], r14w
0x18000ceaf  jz      loc_18000CF8F
0x18000ceb5  xorps   xmm0, xmm0
0x18000ceb8  lea     r8, [rbp+UniversalTime]; lpUniversalTime
0x18000cebc  lea     rdx, [rbp+LocalTime]; lpLocalTime
0x18000cec0  xor     ecx, ecx; lpTimeZoneInformation
0x18000cec2  movups  xmmword ptr [rbp+UniversalTime.wYear], xmm0
0x18000cec6  call    cs:__imp_TzSpecificLocalTimeToSystemTime
0x18000cecd  nop     dword ptr [rax+rax+00h]
0x18000ced2  test    eax, eax
0x18000ced4  jz      short loc_18000CF1A
0x18000ced6  lea     rdx, [rsi+8]; lpFileTime
0x18000ceda  lea     rcx, [rbp+UniversalTime]; lpSystemTime
0x18000cede  call    cs:__imp_SystemTimeToFileTime
0x18000cee5  nop     dword ptr [rax+rax+00h]
0x18000ceea  test    eax, eax
0x18000ceec  jz      short loc_18000CF1A
0x18000ceee  mov     word ptr [rsi], 40h ; '@'
0x18000cef3  mov     ebx, r14d
0x18000cef6  mov     eax, ebx
0x18000cef8  mov     rcx, [rbp+var_10]
0x18000cefc  xor     rcx, rsp; StackCookie
0x18000ceff  call    __security_check_cookie
0x18000cf04  add     rsp, 70h
0x18000cf08  pop     r14
0x18000cf0a  pop     rdi
0x18000cf0b  pop     rsi
0x18000cf0c  pop     rbx
0x18000cf0d  pop     rbp
0x18000cf0e  retn
0x18000cf10  mov     ebx, 80070057h
0x18000cf15  jmp     loc_18000CE66
0x18000cf1a  call    cs:__imp_GetLastError
0x18000cf21  nop     dword ptr [rax+rax+00h]
0x18000cf26  mov     ebx, eax
0x18000cf28  test    eax, eax
0x18000cf2a  jle     short loc_18000CEF6
0x18000cf2c  movzx   ebx, ax
0x18000cf2f  or      ebx, 80070000h
0x18000cf35  jmp     short loc_18000CEF6
0x18000cf37  mov     eax, 101Fh
0x18000cf3c  cmp     [rdi], ax
0x18000cf3f  jz      short loc_18000CF48
0x18000cf41  mov     ebx, 80070057h
0x18000cf46  jmp     short loc_18000CEF6
0x18000cf48  cmp     [rdi+8], r14d
0x18000cf4c  jbe     loc_18000CEA6
0x18000cf52  mov     rcx, [rdi+10h]
0x18000cf56  lea     r8, [rbp+LocalTime.wMilliseconds]
0x18000cf5a  lea     rdx, a2hd; "%2hd"
0x18000cf61  mov     rcx, [rcx]; Buffer
0x18000cf64  call    swscanf_s
0x18000cf69  cmp     eax, 1
0x18000cf6c  jl      loc_18000CEA6
0x18000cf72  movzx   ecx, [rbp+LocalTime.wMilliseconds]
0x18000cf76  mov     ebx, r14d
0x18000cf79  movzx   eax, cx
0x18000cf7c  shl     ax, 2
0x18000cf80  add     cx, ax
0x18000cf83  add     cx, cx
0x18000cf86  mov     [rbp+LocalTime.wMilliseconds], cx
0x18000cf8a  jmp     loc_18000CEA6
0x18000cf8f  mov     ebx, 8000FFFFh
0x18000cf94  jmp     loc_18000CEF6
```
