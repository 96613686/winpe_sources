# CMedicEtwConsumer::_CreateLogFileName(ushort *,ulong)

- ea: `0x18002f68c`
- end: `0x18002f762`
- name: `?_CreateLogFileName@CMedicEtwConsumer@@AEAAJPEAGK@Z`
- size: `214`
- prototype: `int(CMedicEtwConsumer *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x18002fd1c`

## callees

- `0x1800050a0`
- `0x18000c638`
- `0x18002f68c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18002f6be`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18002f6be`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002f73b`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002f73b`

## pseudocode

```c
HRESULT __fastcall CMedicEtwConsumer::_CreateLogFileName(CMedicEtwConsumer *this, unsigned __int16 *a2)
{
  HRESULT result; // eax
  const WCHAR *v5; // r8
  int wMonth; // [rsp+20h] [rbp-268h]
  int wDay; // [rsp+28h] [rbp-260h]
  int wHour; // [rsp+30h] [rbp-258h]
  int wMinute; // [rsp+38h] [rbp-250h]
  int wSecond; // [rsp+40h] [rbp-248h]
  int wMilliseconds; // [rsp+48h] [rbp-240h]
  struct _SYSTEMTIME SystemTime; // [rsp+50h] [rbp-238h] BYREF
  WCHAR pszMore[264]; // [rsp+60h] [rbp-228h] BYREF

  SystemTime = 0;
  GetSystemTime(&SystemTime);
  wMilliseconds = SystemTime.wMilliseconds;
  wSecond = SystemTime.wSecond;
  wMinute = SystemTime.wMinute;
  wHour = SystemTime.wHour;
  wDay = SystemTime.wDay;
  wMonth = SystemTime.wMonth;
  result = StringCchPrintfW(
             pszMore,
             0x104u,
             L"waasmedic.%04u%02u%02u_%02u%02u%02u_%03u.etl",
             SystemTime.wYear,
             wMonth,
             wDay,
             wHour,
             wMinute,
             wSecond,
             wMilliseconds);
  if ( result >= 0 )
  {
    v5 = (const WCHAR *)((char *)this + 48);
    if ( *((_QWORD *)this + 9) > 7u )
      v5 = *(const WCHAR **)v5;
    return PathCchCombine(a2, 0x104u, v5, pszMore);
  }
  return result;
}

```

## disassembly

```asm
0x18002f68c  mov     [rsp+arg_10], rbx
0x18002f691  push    rdi
0x18002f692  sub     rsp, 280h
0x18002f699  mov     rax, cs:__security_cookie
0x18002f6a0  xor     rax, rsp
0x18002f6a3  mov     [rsp+288h+var_18], rax
0x18002f6ab  mov     rbx, rcx
0x18002f6ae  xorps   xmm0, xmm0
0x18002f6b1  lea     rcx, [rsp+288h+SystemTime]; lpSystemTime
0x18002f6b6  mov     rdi, rdx
0x18002f6b9  movups  xmmword ptr [rsp+288h+SystemTime.wYear], xmm0
0x18002f6be  call    cs:__imp_GetSystemTime
0x18002f6c4  movzx   edx, [rsp+288h+SystemTime.wSecond]
0x18002f6c9  movzx   r8d, [rsp+288h+SystemTime.wMinute]
0x18002f6cf  movzx   ecx, [rsp+288h+SystemTime.wMonth]
0x18002f6d4  movzx   eax, [rsp+288h+SystemTime.wMilliseconds]
0x18002f6d9  movzx   r10d, [rsp+288h+SystemTime.wHour]
0x18002f6df  movzx   r11d, [rsp+288h+SystemTime.wDay]
0x18002f6e5  movzx   r9d, [rsp+288h+SystemTime.wYear]
0x18002f6eb  mov     [rsp+288h+var_240], eax
0x18002f6ef  mov     [rsp+288h+var_248], edx
0x18002f6f3  mov     edx, 104h; unsigned __int64
0x18002f6f8  mov     [rsp+288h+var_250], r8d
0x18002f6fd  lea     r8, aWaasmedic04u02; "waasmedic.%04u%02u%02u_%02u%02u%02u_%03"...
0x18002f704  mov     [rsp+288h+var_258], r10d
0x18002f709  mov     [rsp+288h+var_260], r11d
0x18002f70e  mov     [rsp+288h+var_268], ecx
0x18002f712  lea     rcx, [rsp+288h+pszMore]; unsigned __int16 *
0x18002f717  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002f71c  test    eax, eax
0x18002f71e  js      short loc_18002F741
0x18002f720  lea     r8, [rbx+30h]
0x18002f724  cmp     qword ptr [r8+18h], 7
0x18002f729  jbe     short loc_18002F72E
0x18002f72b  mov     r8, [r8]; pszPathIn
0x18002f72e  lea     r9, [rsp+288h+pszMore]; pszMore
0x18002f733  mov     edx, 104h; cchPathOut
0x18002f738  mov     rcx, rdi; pszPathOut
0x18002f73b  call    cs:__imp_PathCchCombine
0x18002f741  mov     rcx, [rsp+288h+var_18]
0x18002f749  xor     rcx, rsp; StackCookie
0x18002f74c  call    __security_check_cookie
0x18002f751  mov     rbx, [rsp+288h+arg_10]
0x18002f759  add     rsp, 280h
0x18002f760  pop     rdi
0x18002f761  retn
```
