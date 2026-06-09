# s_GetLogPath

- ea: `0x18004d348`
- end: `0x18004d483`
- name: `s_GetLogPath`
- size: `315`
- prototype: `__int64 __fastcall(PCWSTR pszMore)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x18004d0b0`

## callees

- `0x180006900`
- `0x180007c82`
- `0x18000ebd0`
- `0x18000ecc4`
- `0x18000eec0`
- `0x18004d348`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18004d3a3`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18004d3a3`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18004d38b`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18004d38b`

## pseudocode

```c
__int64 __fastcall s_GetLogPath(PCWSTR pszMore, int a2, __int64 a3, unsigned __int16 *a4)
{
  unsigned int v7; // ebx
  int wMonth; // [rsp+20h] [rbp-E0h]
  int wDay; // [rsp+28h] [rbp-D8h]
  int wHour; // [rsp+30h] [rbp-D0h]
  int wMinute; // [rsp+38h] [rbp-C8h]
  int wSecond; // [rsp+40h] [rbp-C0h]
  struct _SYSTEMTIME SystemTime; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v15[104]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[264]; // [rsp+130h] [rbp+30h] BYREF

  v7 = 0;
  if ( GetTempPathW(0x104u, Buffer) )
  {
    if ( PathCchAppend(Buffer, 0x104u, pszMore) >= 0 )
    {
      SystemTime = 0;
      GetLocalTime_0(&SystemTime);
      wSecond = SystemTime.wSecond;
      wMinute = SystemTime.wMinute;
      wHour = SystemTime.wHour;
      wDay = SystemTime.wDay;
      wMonth = SystemTime.wMonth;
      if ( StringCchPrintfW(
             v15,
             0x64u,
             L"-%04d%02d%02d%02d%02d%02d",
             SystemTime.wYear,
             wMonth,
             wDay,
             wHour,
             wMinute,
             wSecond) >= 0
        && StringCchCatW(Buffer, 0x104u, v15) >= 0
        && (!a2 || StringCchCatW(Buffer, 0x104u, L"-Norm") >= 0)
        && StringCchCopyW(a4, 0x104u, Buffer) >= 0 )
      {
        return 1;
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18004d348  mov     [rsp-8+arg_8], rbx
0x18004d34d  push    rbp
0x18004d34e  push    rsi
0x18004d34f  push    rdi
0x18004d350  push    r14
0x18004d352  push    r15
0x18004d354  lea     rbp, [rsp-250h]
0x18004d35c  sub     rsp, 350h
0x18004d363  mov     rax, cs:__security_cookie
0x18004d36a  xor     rax, rsp
0x18004d36d  mov     [rbp+270h+var_30], rax
0x18004d374  mov     edi, edx
0x18004d376  mov     rsi, rcx
0x18004d379  mov     r15d, 104h
0x18004d37f  lea     rdx, [rbp+270h+Buffer]; lpBuffer
0x18004d383  mov     ecx, r15d; nBufferLength
0x18004d386  mov     r14, r9
0x18004d389  xor     ebx, ebx
0x18004d38b  call    cs:__imp_GetTempPathW
0x18004d391  test    eax, eax
0x18004d393  jz      loc_18004D45B
0x18004d399  mov     r8, rsi; pszMore
0x18004d39c  lea     rcx, [rbp+270h+Buffer]; pszPath
0x18004d3a0  mov     edx, r15d; cchPath
0x18004d3a3  call    cs:__imp_PathCchAppend
0x18004d3a9  test    eax, eax
0x18004d3ab  js      loc_18004D45B
0x18004d3b1  xorps   xmm0, xmm0
0x18004d3b4  lea     rcx, [rsp+370h+SystemTime]; lpSystemTime
0x18004d3b9  movups  xmmword ptr [rsp+370h+SystemTime.wYear], xmm0
0x18004d3be  call    GetLocalTime_0
0x18004d3c3  movzx   ecx, [rsp+370h+SystemTime.wMinute]
0x18004d3c8  movzx   edx, [rsp+370h+SystemTime.wHour]
0x18004d3cd  movzx   r8d, [rsp+370h+SystemTime.wDay]
0x18004d3d3  movzx   eax, [rsp+370h+SystemTime.wSecond]
0x18004d3d8  movzx   r10d, [rsp+370h+SystemTime.wMonth]
0x18004d3de  movzx   r9d, [rsp+370h+SystemTime.wYear]
0x18004d3e4  mov     [rsp+370h+var_330], eax
0x18004d3e8  mov     [rsp+370h+var_338], ecx
0x18004d3ec  lea     rcx, [rsp+370h+var_310]; unsigned __int16 *
0x18004d3f1  mov     [rsp+370h+var_340], edx
0x18004d3f5  lea     edx, [rbx+64h]; unsigned __int64
0x18004d3f8  mov     [rsp+370h+var_348], r8d
0x18004d3fd  lea     r8, a04d02d02d02d02; "-%04d%02d%02d%02d%02d%02d"
0x18004d404  mov     [rsp+370h+var_350], r10d
0x18004d409  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004d40e  test    eax, eax
0x18004d410  js      short loc_18004D45B
0x18004d412  lea     r8, [rsp+370h+var_310]; unsigned __int16 *
0x18004d417  mov     edx, r15d; unsigned __int64
0x18004d41a  lea     rcx, [rbp+270h+Buffer]; unsigned __int16 *
0x18004d41e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004d423  test    eax, eax
0x18004d425  js      short loc_18004D45B
0x18004d427  test    edi, edi
0x18004d429  jz      short loc_18004D442
0x18004d42b  lea     r8, aNorm; "-Norm"
0x18004d432  mov     edx, r15d; unsigned __int64
0x18004d435  lea     rcx, [rbp+270h+Buffer]; unsigned __int16 *
0x18004d439  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004d43e  test    eax, eax
0x18004d440  js      short loc_18004D45B
0x18004d442  lea     r8, [rbp+270h+Buffer]; unsigned __int16 *
0x18004d446  mov     rdx, r15; unsigned __int64
0x18004d449  mov     rcx, r14; unsigned __int16 *
0x18004d44c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004d451  test    eax, eax
0x18004d453  mov     ecx, 1
0x18004d458  cmovns  ebx, ecx
0x18004d45b  mov     eax, ebx
0x18004d45d  mov     rcx, [rbp+270h+var_30]
0x18004d464  xor     rcx, rsp; StackCookie
0x18004d467  call    __security_check_cookie
0x18004d46c  mov     rbx, [rsp+370h+arg_8]
0x18004d474  add     rsp, 350h
0x18004d47b  pop     r15
0x18004d47d  pop     r14
0x18004d47f  pop     rdi
0x18004d480  pop     rsi
0x18004d481  pop     rbp
0x18004d482  retn
```
