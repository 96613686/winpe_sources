# GetLogPath(ushort const *,_SYSTEMTIME const *,ushort *,ulong)

- ea: `0x140001e2c`
- end: `0x140002132`
- name: `?GetLogPath@@YAJPEBGPEBU_SYSTEMTIME@@PEAGK@Z`
- size: `774`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const struct _SYSTEMTIME *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140003218`

## callees

- `0x140001e2c`
- `0x140002c08`
- `0x1400036d8`
- `0x140003918`
- `0x140003c2c`
- `0x14000ae32`
- `0x14000ae60`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x14000205d`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14000205d`
- `KERNEL32!GetTimeFormatEx` at `0x140001f8b`
- `KERNEL32!GetTimeFormatEx` at `0x140001f8b`
- `KERNEL32!GetDateFormatEx` at `0x140001eb3`
- `KERNEL32!GetDateFormatEx` at `0x140001eb3`
- `KERNEL32!IsDebuggerPresent` at `0x140001f1c`
- `KERNEL32!IsDebuggerPresent` at `0x14000201c`
- `KERNEL32!IsDebuggerPresent` at `0x1400020cb`
- `KERNEL32!IsDebuggerPresent` at `0x140001f1c`
- `KERNEL32!IsDebuggerPresent` at `0x14000201c`
- `KERNEL32!IsDebuggerPresent` at `0x1400020cb`
- `KERNEL32!GetLastError` at `0x140001ec1`
- `KERNEL32!GetLastError` at `0x140001f95`
- `KERNEL32!GetLastError` at `0x140002070`
- `KERNEL32!GetLastError` at `0x140001ec1`
- `KERNEL32!GetLastError` at `0x140001f95`
- `KERNEL32!GetLastError` at `0x140002070`

## string_xrefs

- `0x140001ee1`: `GetLogPath`
- `0x140001fed`: `GetLogPath`
- `0x140002093`: `GetLogPath`
- `0x1400020aa`: `dwResult != 0 && dwResult <= cchPath`
- `0x140001fcb`: `%%temp%%\WmsSelfHealingSvc-%s-%s.log`

## pseudocode

```c
__int64 __fastcall GetLogPath(const unsigned __int16 *a1, const struct _SYSTEMTIME *a2, unsigned __int16 *a3)
{
  signed int LastError; // eax
  signed int v6; // ebx
  unsigned int v7; // r15d
  __int64 v8; // r9
  __int64 v9; // r8
  signed int v10; // eax
  int v11; // eax
  signed int v12; // eax
  const unsigned __int16 *cchDate; // [rsp+28h] [rbp-290h]
  LPCWSTR lpCalendar; // [rsp+30h] [rbp-288h]
  LPCWSTR lpCalendara; // [rsp+30h] [rbp-288h]
  signed int v17; // [rsp+38h] [rbp-280h]
  signed int v18; // [rsp+38h] [rbp-280h]
  WCHAR TimeStr[8]; // [rsp+40h] [rbp-278h] BYREF
  __int64 v20; // [rsp+50h] [rbp-268h]
  WCHAR DateStr[8]; // [rsp+58h] [rbp-260h] BYREF
  __int64 v22; // [rsp+68h] [rbp-250h]
  WCHAR Src[264]; // [rsp+70h] [rbp-248h] BYREF

  v22 = 0;
  LOWORD(v20) = 0;
  *(_OWORD *)DateStr = 0;
  *(_OWORD *)TimeStr = 0;
  memset_0(Src, 0, 0x208u);
  if ( !GetDateFormatEx(&LocaleName, 0, a2, L"yyyyy-MM-dd", DateStr, 12, 0) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    v7 = 718;
LABEL_5:
    if ( v6 >= 0 )
      v6 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
      v7,
      L"GetLogPath",
      L"CBRAEx",
      L"fSuccess",
      v6);
    if ( IsDebuggerPresent() )
    {
      v17 = v6;
      v8 = v7;
      lpCalendara = L"fSuccess";
LABEL_9:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
        v8,
        L"GetLogPath",
        L"CBRAEx",
        lpCalendara,
        v17,
        *(_QWORD *)TimeStr,
        *(_QWORD *)&TimeStr[4],
        v20,
        *(_QWORD *)DateStr,
        *(_QWORD *)&DateStr[4],
        v22);
      return (unsigned int)v6;
    }
    LODWORD(lpCalendar) = v6;
    v9 = v7;
    cchDate = L"fSuccess";
LABEL_28:
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
      v9,
      L"GetLogPath",
      L"CBRAEx",
      cchDate,
      lpCalendar);
    return (unsigned int)v6;
  }
  if ( !GetTimeFormatEx(&LocaleName, 0, a2, L"HH-mm-ss", TimeStr, 9) )
  {
    v10 = GetLastError();
    v6 = v10;
    if ( v10 > 0 )
      v6 = (unsigned __int16)v10 | 0x80070000;
    v7 = 721;
    goto LABEL_5;
  }
  v11 = StringCchPrintfW(Src, 0x104u, L"%%temp%%\\WmsSelfHealingSvc-%s-%s.log", DateStr, TimeStr);
  v6 = v11;
  if ( v11 >= 0 )
  {
    if ( ExpandEnvironmentStringsW(Src, a3, 0x104u) - 1 > 0x103 )
    {
      v12 = GetLastError();
      v6 = v12;
      if ( v12 > 0 )
        v6 = (unsigned __int16)v12 | 0x80070000;
      if ( v6 >= 0 )
        v6 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
        0x2D8u,
        L"GetLogPath",
        L"CBRAEx",
        L"dwResult != 0 && dwResult <= cchPath",
        v6);
      if ( IsDebuggerPresent() )
      {
        v17 = v6;
        v8 = 728;
        lpCalendara = L"dwResult != 0 && dwResult <= cchPath";
        goto LABEL_9;
      }
      LODWORD(lpCalendar) = v6;
      v9 = 728;
      cchDate = L"dwResult != 0 && dwResult <= cchPath";
      goto LABEL_28;
    }
  }
  else
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
      0x2D4u,
      L"GetLogPath",
      L"CHRA",
      L"hr",
      v11);
    if ( IsDebuggerPresent() )
    {
      v18 = v6;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
        724,
        L"GetLogPath",
        L"CHRA",
        L"hr",
        v18,
        *(_QWORD *)TimeStr,
        *(_QWORD *)&TimeStr[4],
        v20,
        *(_QWORD *)DateStr,
        *(_QWORD *)&DateStr[4],
        v22);
    }
    else
    {
      LODWORD(lpCalendar) = v6;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
        724,
        L"GetLogPath",
        L"CHRA",
        L"hr",
        lpCalendar);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140001e2c  mov     [rsp+arg_0], rbx
0x140001e31  push    rbp
0x140001e32  push    rsi
0x140001e33  push    rdi
0x140001e34  push    r14
0x140001e36  push    r15
0x140001e38  sub     rsp, 290h
0x140001e3f  mov     rax, cs:__security_cookie
0x140001e46  xor     rax, rsp
0x140001e49  mov     [rsp+2B8h+var_38], rax
0x140001e51  xor     eax, eax
0x140001e53  lea     rcx, [rsp+2B8h+Src]; void *
0x140001e58  mov     rdi, r8
0x140001e5b  mov     [rsp+2B8h+var_250], rax
0x140001e60  mov     rbx, rdx
0x140001e63  mov     word ptr [rsp+2B8h+var_268], ax
0x140001e68  xorps   xmm0, xmm0
0x140001e6b  xorps   xmm1, xmm1
0x140001e6e  xor     edx, edx; Val
0x140001e70  mov     r8d, 208h; Size
0x140001e76  movups  xmmword ptr [rsp+2B8h+DateStr], xmm0
0x140001e7b  movups  xmmword ptr [rsp+2B8h+TimeStr], xmm1
0x140001e80  call    memset_0
0x140001e85  lea     rax, [rsp+2B8h+DateStr]
0x140001e8a  mov     [rsp+2B8h+lpCalendar], 0; lpCalendar
0x140001e93  mov     [rsp+2B8h+cchDate], 0Ch; cchDate
0x140001e9b  lea     r9, Format; "yyyyy-MM-dd"
0x140001ea2  mov     r8, rbx; lpDate
0x140001ea5  mov     [rsp+2B8h+lpDateStr], rax; lpDateStr
0x140001eaa  xor     edx, edx; dwFlags
0x140001eac  lea     rcx, LocaleName; lpLocaleName
0x140001eb3  call    cs:__imp_GetDateFormatEx
0x140001eb9  test    eax, eax
0x140001ebb  jnz     loc_140001F66
0x140001ec1  call    cs:__imp_GetLastError
0x140001ec7  mov     ebx, eax
0x140001ec9  test    eax, eax
0x140001ecb  jle     short loc_140001ED6
0x140001ecd  movzx   ebx, ax
0x140001ed0  or      ebx, 80070000h
0x140001ed6  mov     r15d, 2CEh
0x140001edc  mov     eax, 80004005h
0x140001ee1  lea     rsi, aGetlogpath; "GetLogPath"
0x140001ee8  test    ebx, ebx
0x140001eea  lea     rbp, aCbraex; "CBRAEx"
0x140001ef1  lea     rdi, aTermsrvWmsSrcP; "termsrv\\wms\\src\\platform\\wmsselfhea"...
0x140001ef8  mov     r8, rsi; unsigned __int16 *
0x140001efb  cmovns  ebx, eax
0x140001efe  lea     r14, aFsuccess; "fSuccess"
0x140001f05  mov     [rsp+2B8h+cchDate], ebx; int
0x140001f09  mov     r9, rbp; unsigned __int16 *
0x140001f0c  mov     edx, r15d; unsigned int
0x140001f0f  mov     [rsp+2B8h+lpDateStr], r14; unsigned __int16 *
0x140001f14  mov     rcx, rdi; unsigned __int16 *
0x140001f17  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140001f1c  call    cs:__imp_IsDebuggerPresent
0x140001f22  test    eax, eax
0x140001f24  jz      short loc_140001F55
0x140001f26  mov     [rsp+2B8h+var_280], ebx
0x140001f2a  mov     r9d, r15d
0x140001f2d  mov     [rsp+2B8h+lpCalendar], r14
0x140001f32  mov     qword ptr [rsp+2B8h+cchDate], rbp
0x140001f37  mov     r8, rdi
0x140001f3a  mov     [rsp+2B8h+lpDateStr], rsi
0x140001f3f  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140001f46  mov     ecx, 2; unsigned __int8
0x140001f4b  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140001f50  jmp     loc_140002109
0x140001f55  mov     dword ptr [rsp+2B8h+lpCalendar], ebx
0x140001f59  mov     r8d, r15d
0x140001f5c  mov     qword ptr [rsp+2B8h+cchDate], r14
0x140001f61  jmp     loc_1400020F2
0x140001f66  lea     rax, [rsp+2B8h+TimeStr]
0x140001f6b  mov     [rsp+2B8h+cchDate], 9; cchTime
0x140001f73  lea     r9, aHhMmSs; "HH-mm-ss"
0x140001f7a  mov     [rsp+2B8h+lpDateStr], rax; lpTimeStr
0x140001f7f  mov     r8, rbx; lpTime
0x140001f82  lea     rcx, LocaleName; lpLocaleName
0x140001f89  xor     edx, edx; dwFlags
0x140001f8b  call    cs:__imp_GetTimeFormatEx
0x140001f91  test    eax, eax
0x140001f93  jnz     short loc_140001FB5
0x140001f95  call    cs:__imp_GetLastError
0x140001f9b  mov     ebx, eax
0x140001f9d  test    eax, eax
0x140001f9f  jle     short loc_140001FAA
0x140001fa1  movzx   ebx, ax
0x140001fa4  or      ebx, 80070000h
0x140001faa  mov     r15d, 2D1h
0x140001fb0  jmp     loc_140001EDC
0x140001fb5  lea     rax, [rsp+2B8h+TimeStr]
0x140001fba  mov     esi, 104h
0x140001fbf  mov     edx, esi; unsigned __int64
0x140001fc1  mov     [rsp+2B8h+lpDateStr], rax
0x140001fc6  lea     r9, [rsp+2B8h+DateStr]
0x140001fcb  lea     r8, aTempWmsselfhea; "%%temp%%\\WmsSelfHealingSvc-%s-%s.log"
0x140001fd2  lea     rcx, [rsp+2B8h+Src]; unsigned __int16 *
0x140001fd7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140001fdc  mov     ebx, eax
0x140001fde  test    eax, eax
0x140001fe0  jns     short loc_140002052
0x140001fe2  mov     [rsp+2B8h+cchDate], eax; int
0x140001fe6  lea     r15, aChra; "CHRA"
0x140001fed  lea     rsi, aGetlogpath; "GetLogPath"
0x140001ff4  mov     ebp, 2D4h
0x140001ff9  lea     rdi, aTermsrvWmsSrcP; "termsrv\\wms\\src\\platform\\wmsselfhea"...
0x140002000  mov     r9, r15; unsigned __int16 *
0x140002003  lea     r14, aHr; "hr"
0x14000200a  mov     r8, rsi; unsigned __int16 *
0x14000200d  mov     edx, ebp; unsigned int
0x14000200f  mov     [rsp+2B8h+lpDateStr], r14; unsigned __int16 *
0x140002014  mov     rcx, rdi; unsigned __int16 *
0x140002017  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000201c  call    cs:__imp_IsDebuggerPresent
0x140002022  test    eax, eax
0x140002024  jz      short loc_14000203C
0x140002026  mov     [rsp+2B8h+var_280], ebx
0x14000202a  mov     r9d, ebp
0x14000202d  mov     [rsp+2B8h+lpCalendar], r14
0x140002032  mov     qword ptr [rsp+2B8h+cchDate], r15
0x140002037  jmp     loc_140001F37
0x14000203c  mov     dword ptr [rsp+2B8h+lpCalendar], ebx
0x140002040  mov     r8d, ebp
0x140002043  mov     qword ptr [rsp+2B8h+cchDate], r14
0x140002048  mov     [rsp+2B8h+lpDateStr], r15
0x14000204d  jmp     loc_1400020F7
0x140002052  mov     r8d, esi; nSize
0x140002055  lea     rcx, [rsp+2B8h+Src]; lpSrc
0x14000205a  mov     rdx, rdi; lpDst
0x14000205d  call    cs:__imp_ExpandEnvironmentStringsW
0x140002063  dec     eax
0x140002065  cmp     eax, 103h
0x14000206a  jbe     loc_140002109
0x140002070  call    cs:__imp_GetLastError
0x140002076  mov     ebx, eax
0x140002078  test    eax, eax
0x14000207a  jle     short loc_140002085
0x14000207c  movzx   ebx, ax
0x14000207f  or      ebx, 80070000h
0x140002085  mov     eax, 80004005h
0x14000208a  lea     rbp, aCbraex; "CBRAEx"
0x140002091  test    ebx, ebx
0x140002093  lea     rsi, aGetlogpath; "GetLogPath"
0x14000209a  mov     r14d, 2D8h
0x1400020a0  lea     rdi, aTermsrvWmsSrcP; "termsrv\\wms\\src\\platform\\wmsselfhea"...
0x1400020a7  cmovns  ebx, eax
0x1400020aa  lea     r15, aDwresult0Dwres; "dwResult != 0 && dwResult <= cchPath"
0x1400020b1  mov     [rsp+2B8h+cchDate], ebx; int
0x1400020b5  mov     r9, rbp; unsigned __int16 *
0x1400020b8  mov     r8, rsi; unsigned __int16 *
0x1400020bb  mov     [rsp+2B8h+lpDateStr], r15; unsigned __int16 *
0x1400020c0  mov     edx, r14d; unsigned int
0x1400020c3  mov     rcx, rdi; unsigned __int16 *
0x1400020c6  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400020cb  call    cs:__imp_IsDebuggerPresent
0x1400020d1  test    eax, eax
0x1400020d3  jz      short loc_1400020E6
0x1400020d5  mov     [rsp+2B8h+var_280], ebx
0x1400020d9  mov     r9d, r14d
0x1400020dc  mov     [rsp+2B8h+lpCalendar], r15
0x1400020e1  jmp     loc_140001F32
0x1400020e6  mov     dword ptr [rsp+2B8h+lpCalendar], ebx
0x1400020ea  mov     r8d, r14d
0x1400020ed  mov     qword ptr [rsp+2B8h+cchDate], r15
0x1400020f2  mov     [rsp+2B8h+lpDateStr], rbp
0x1400020f7  mov     r9, rsi
0x1400020fa  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140002101  mov     rdx, rdi
0x140002104  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140002109  mov     eax, ebx
0x14000210b  mov     rcx, [rsp+2B8h+var_38]
0x140002113  xor     rcx, rsp; StackCookie
0x140002116  call    __security_check_cookie
0x14000211b  mov     rbx, [rsp+2B8h+arg_0]
0x140002123  add     rsp, 290h
0x14000212a  pop     r15
0x14000212c  pop     r14
0x14000212e  pop     rdi
0x14000212f  pop     rsi
0x140002130  pop     rbp
0x140002131  retn
```
