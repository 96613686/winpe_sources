# WinHttpConnection::Initialize(ushort const *,ushort,WinHttpSession &)

- ea: `0x180097ef4`
- end: `0x1800981c2`
- name: `?Initialize@WinHttpConnection@@QEAAJPEBGGAEAVWinHttpSession@@@Z`
- size: `718`
- prototype: `int(WinHttpConnection *__hidden this, const unsigned __int16 *, unsigned __int16, struct WinHttpSession *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180097cb8`

## callees

- `0x180004a24`
- `0x180085c44`
- `0x180085ee8`
- `0x18008758c`
- `0x18008aa28`
- `0x18008aa9c`
- `0x18008aecc`
- `0x18008bff8`
- `0x180097ef4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180097f7c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180097f92`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009819f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180097f7c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180097f92`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009819f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098113`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098113`
- `WINHTTP!WinHttpConnect` at `0x180098104`
- `WINHTTP!WinHttpConnect` at `0x180098104`

## string_xrefs

- `0x18009807a`: `CopyStringNullSafeW`
- `0x18009813c`: `EventWriteWinhttpConnectFailureEvent`
- `0x180098143`: `Logger::WriteWinhttpConnectFailureEvent`
- `0x180098014`: `%s: pcszServerName is too large to be included in URL_COMPONENTS.`

## pseudocode

```c
__int64 __fastcall WinHttpConnection::Initialize(
        WinHttpConnection *this,
        const unsigned __int16 *a2,
        __int64 a3,
        struct WinHttpSession *a4)
{
  unsigned int v6; // ebx
  void *v7; // rcx
  const WCHAR **v8; // r14
  void *v9; // rcx
  int v10; // eax
  int v11; // eax
  unsigned __int16 *v12; // r12
  int v13; // eax
  const wchar_t *v14; // r8
  struct WinHttpSession *v15; // rcx
  INTERNET_PORT v16; // r8
  const WCHAR *v17; // rdx
  HINTERNET v18; // rax
  DWORD LastError; // eax
  int v20; // edx
  int v21; // ecx
  unsigned int v22; // eax
  __int64 v24; // [rsp+28h] [rbp-69h]
  void *Block; // [rsp+38h] [rbp-59h] BYREF
  unsigned __int64 v26; // [rsp+40h] [rbp-51h] BYREF
  _BYTE v27[160]; // [rsp+48h] [rbp-49h] BYREF
  unsigned __int64 v28; // [rsp+100h] [rbp+6Fh] BYREF
  unsigned __int16 v29; // [rsp+108h] [rbp+77h] BYREF
  struct WinHttpSession *v30; // [rsp+110h] [rbp+7Fh]

  v30 = a4;
  v28 = 0;
  v26 = 0;
  Block = 0;
  v29 = 0;
  if ( !a2 )
  {
    v6 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"WinHttpConnection::Initialize", L"pcszServerName");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"WinHttpConnection::Initialize", L"pcszServerName");
    return v6;
  }
  v7 = (void *)*((_QWORD *)this + 5);
  v8 = (const WCHAR **)((char *)this + 40);
  if ( v7 )
  {
    free(v7);
    *v8 = 0;
  }
  v9 = (void *)*((_QWORD *)this + 3);
  if ( v9 )
    free(v9);
  memset_0(v27, 0, 0x68u);
  memset_0((char *)this + 16, 0, 0x68u);
  *((_DWORD *)this + 4) = 104;
  *((_WORD *)this + 26) = 443;
  *((_DWORD *)this + 9) = 2;
  v10 = StringLen(a2, &v28);
  v6 = v10;
  if ( v10 < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"WinHttpConnection::Initialize",
      L"StringLen",
      (unsigned int)v10);
    return v6;
  }
  if ( v28 > 0xFFFFFFFF )
  {
    v6 = -2147024809;
    Logger::TraceError(
      L"%s: pcszServerName is too large to be included in URL_COMPONENTS.",
      L"WinHttpConnection::Initialize");
    return v6;
  }
  v11 = ExtractPortFromHostname(a2, (unsigned __int16 **)&Block, &v29);
  v12 = (unsigned __int16 *)Block;
  if ( v11 )
  {
    v13 = CopyStringNullSafeW(a2, (unsigned __int16 **)this + 5);
    v6 = v13;
    if ( v13 < 0 )
      goto LABEL_13;
  }
  else
  {
    Logger::TraceVerbose(
      L"%s: Found port in original server string '%s'.  Ignoring passed port '%hu' and connecting to %s:%hu.",
      L"WinHttpConnection::Initialize",
      a2,
      443,
      Block,
      v29);
    v13 = CopyStringNullSafeW(v12, (unsigned __int16 **)this + 5);
    v6 = v13;
    if ( v13 < 0 )
    {
LABEL_13:
      v14 = L"CopyStringNullSafeW";
LABEL_14:
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"WinHttpConnection::Initialize",
        v14,
        (unsigned int)v13);
      goto LABEL_27;
    }
    *((_WORD *)this + 26) = v29;
  }
  v13 = CopyStringNullSafeW(L"https", (unsigned __int16 **)this + 3);
  v6 = v13;
  if ( v13 < 0 )
    goto LABEL_13;
  v13 = StringLen(*((const unsigned __int16 **)this + 3), &v26);
  v6 = v13;
  if ( v13 < 0 )
  {
    v14 = L"StringLen";
    goto LABEL_14;
  }
  v15 = v30;
  v16 = *((_WORD *)this + 26);
  v17 = *v8;
  *((_DWORD *)this + 12) = v28;
  *((_DWORD *)this + 8) = v26;
  v18 = WinHttpConnect(*((HINTERNET *)v15 + 1), v17, v16, 0);
  *((_QWORD *)this + 1) = v18;
  if ( v18 )
  {
    Logger::TraceVerbose(
      L"%s: Connected to %s:%hu.",
      L"WinHttpConnection::Initialize",
      *v8,
      *((unsigned __int16 *)this + 26));
LABEL_27:
    if ( v12 )
      free(v12);
    return v6;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
  {
    v22 = McTemplateU0zhq_EventWriteTransfer(v21, v20, (unsigned int)*v8, *((unsigned __int16 *)this + 26), LastError);
    if ( v22 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"Logger::WriteWinhttpConnectFailureEvent",
        L"EventWriteWinhttpConnectFailureEvent",
        v22);
  }
  LODWORD(v24) = v6;
  Logger::TraceError(
    L"%s: WinHttpConnect(%s, %hu) failed with error code: 0x%08x",
    L"WinHttpConnection::Initialize",
    *v8,
    *((unsigned __int16 *)this + 26),
    v24);
  if ( (int)v6 > 0 )
    return (unsigned __int16)v6 | 0x80070000;
  return v6;
}

```

## disassembly

```asm
0x180097ef4  mov     rax, rsp
0x180097ef7  mov     [rax+8], rbx
0x180097efb  mov     [rax+20h], r9
0x180097eff  mov     [rax+18h], r8w
0x180097f04  push    rbp
0x180097f05  push    rsi
0x180097f06  push    rdi
0x180097f07  push    r12
0x180097f09  push    r13
0x180097f0b  push    r14
0x180097f0d  push    r15
0x180097f0f  lea     rbp, [rax-5Fh]
0x180097f13  sub     rsp, 0B0h
0x180097f1a  xor     r12d, r12d
0x180097f1d  mov     r15, rdx
0x180097f20  mov     [rbp+57h+arg_8], r12
0x180097f24  mov     rsi, rcx
0x180097f27  mov     [rbp+57h+var_A8], r12
0x180097f2b  mov     [rbp+57h+Block], r12
0x180097f2f  mov     [rbp+57h+arg_10], r12w
0x180097f34  test    rdx, rdx
0x180097f37  jnz     short loc_180097F6F
0x180097f39  lea     rdi, aWinhttpconnect_0; "WinHttpConnection::Initialize"
0x180097f40  mov     ebx, 80070057h
0x180097f45  mov     rdx, rdi
0x180097f48  lea     r8, aPcszservername; "pcszServerName"
0x180097f4f  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180097f56  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180097f5b  lea     rdx, aPcszservername; "pcszServerName"
0x180097f62  mov     rcx, rdi; unsigned __int16 *
0x180097f65  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180097f6a  jmp     loc_1800981A5
0x180097f6f  mov     rcx, [rcx+28h]; Block
0x180097f73  lea     r14, [rsi+28h]
0x180097f77  test    rcx, rcx
0x180097f7a  jz      short loc_180097F85
0x180097f7c  call    cs:__imp_free
0x180097f82  mov     [r14], r12
0x180097f85  lea     r13, [rsi+18h]
0x180097f89  mov     rcx, [r13+0]; Block
0x180097f8d  test    rcx, rcx
0x180097f90  jz      short loc_180097F98
0x180097f92  call    cs:__imp_free
0x180097f98  mov     edi, 68h ; 'h'
0x180097f9d  lea     rcx, [rbp+57h+var_A0]; void *
0x180097fa1  mov     r8d, edi; Size
0x180097fa4  xor     edx, edx; Val
0x180097fa6  call    memset_0
0x180097fab  mov     r8d, edi; Size
0x180097fae  lea     rcx, [rsi+10h]; void *
0x180097fb2  xor     edx, edx; Val
0x180097fb4  call    memset_0
0x180097fb9  lea     rdx, [rbp+57h+arg_8]; unsigned __int64 *
0x180097fbd  mov     [rsi+10h], edi
0x180097fc0  mov     rcx, r15; unsigned __int16 *
0x180097fc3  mov     word ptr [rsi+34h], 1BBh
0x180097fc9  mov     dword ptr [rsi+24h], 2
0x180097fd0  call    ?StringLen@@YAJPEBGPEA_K@Z; StringLen(ushort const *,unsigned __int64 *)
0x180097fd5  mov     ebx, eax
0x180097fd7  test    eax, eax
0x180097fd9  jns     short loc_180097FFD
0x180097fdb  mov     r9d, eax
0x180097fde  lea     r8, aStringlen; "StringLen"
0x180097fe5  lea     rdx, aWinhttpconnect_0; "WinHttpConnection::Initialize"
0x180097fec  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180097ff3  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180097ff8  jmp     loc_1800981A5
0x180097ffd  mov     eax, 0FFFFFFFFh
0x180098002  cmp     [rbp+57h+arg_8], rax
0x180098006  jbe     short loc_180098025
0x180098008  lea     rdx, aWinhttpconnect_0; "WinHttpConnection::Initialize"
0x18009800f  mov     ebx, 80070057h
0x180098014  lea     rcx, aSPcszservernam; "%s: pcszServerName is too large to be i"...
0x18009801b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180098020  jmp     loc_1800981A5
0x180098025  lea     r8, [rbp+57h+arg_10]; unsigned __int16 *
0x180098029  mov     rcx, r15; Source
0x18009802c  lea     rdx, [rbp+57h+Block]; unsigned __int16 **
0x180098030  call    ?ExtractPortFromHostname@@YAJPEBGPEAPEAGPEAG@Z; ExtractPortFromHostname(ushort const *,ushort * *,ushort *)
0x180098035  mov     r12, [rbp+57h+Block]
0x180098039  lea     rdi, aWinhttpconnect_0; "WinHttpConnection::Initialize"
0x180098040  test    eax, eax
0x180098042  jnz     short loc_1800980A2
0x180098044  movzx   eax, [rbp+57h+arg_10]
0x180098048  lea     rcx, aSFoundPortInOr; "%s: Found port in original server strin"...
0x18009804f  mov     [rsp+28h], eax
0x180098053  mov     r9d, 1BBh
0x180098059  mov     r8, r15
0x18009805c  mov     qword ptr [rsp+0E0h+var_C0], r12
0x180098061  mov     rdx, rdi
0x180098064  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180098069  mov     rdx, r14; unsigned __int16 **
0x18009806c  mov     rcx, r12; unsigned __int16 *
0x18009806f  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x180098074  mov     ebx, eax
0x180098076  test    eax, eax
0x180098078  jns     short loc_180098098
0x18009807a  lea     r8, aCopystringnull; "CopyStringNullSafeW"
0x180098081  mov     r9d, eax
0x180098084  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18009808b  mov     rdx, rdi
0x18009808e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180098093  jmp     loc_180098197
0x180098098  movzx   eax, [rbp+57h+arg_10]
0x18009809c  mov     [rsi+34h], ax
0x1800980a0  jmp     short loc_1800980B3
0x1800980a2  mov     rdx, r14; unsigned __int16 **
0x1800980a5  mov     rcx, r15; unsigned __int16 *
0x1800980a8  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x1800980ad  mov     ebx, eax
0x1800980af  test    eax, eax
0x1800980b1  js      short loc_18009807A
0x1800980b3  mov     rdx, r13; unsigned __int16 **
0x1800980b6  lea     rcx, aHttps_0; "https"
0x1800980bd  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x1800980c2  mov     ebx, eax
0x1800980c4  test    eax, eax
0x1800980c6  js      short loc_18009807A
0x1800980c8  mov     rcx, [r13+0]; unsigned __int16 *
0x1800980cc  lea     rdx, [rbp+57h+var_A8]; unsigned __int64 *
0x1800980d0  call    ?StringLen@@YAJPEBGPEA_K@Z; StringLen(ushort const *,unsigned __int64 *)
0x1800980d5  mov     ebx, eax
0x1800980d7  test    eax, eax
0x1800980d9  jns     short loc_1800980E4
0x1800980db  lea     r8, aStringlen; "StringLen"
0x1800980e2  jmp     short loc_180098081
0x1800980e4  mov     rax, [rbp+57h+arg_8]
0x1800980e8  xor     r9d, r9d; dwReserved
0x1800980eb  mov     rcx, [rbp+57h+arg_18]
0x1800980ef  movzx   r8d, word ptr [rsi+34h]; nServerPort
0x1800980f4  mov     rdx, [r14]; pswzServerName
0x1800980f7  mov     [rsi+30h], eax
0x1800980fa  mov     eax, dword ptr [rbp+57h+var_A8]
0x1800980fd  mov     [rsi+20h], eax
0x180098100  mov     rcx, [rcx+8]; hSession
0x180098104  call    cs:__imp_WinHttpConnect
0x18009810a  mov     [rsi+8], rax
0x18009810e  test    rax, rax
0x180098111  jnz     short loc_180098180
0x180098113  call    cs:__imp_GetLastError
0x180098119  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x180098120  mov     ebx, eax
0x180098122  jz      short loc_180098156
0x180098124  movzx   r9d, word ptr [rsi+34h]
0x180098129  mov     r8, [r14]
0x18009812c  mov     [rsp+0E0h+var_C0], eax
0x180098130  call    McTemplateU0zhq_EventWriteTransfer
0x180098135  test    eax, eax
0x180098137  jz      short loc_180098156
0x180098139  mov     r9d, eax
0x18009813c  lea     r8, aEventwritewinh_8; "EventWriteWinhttpConnectFailureEvent"
0x180098143  lea     rdx, aLoggerWritewin_5; "Logger::WriteWinhttpConnectFailureEvent"
0x18009814a  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180098151  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180098156  movzx   r9d, word ptr [rsi+34h]
0x18009815b  lea     rcx, aSWinhttpconnec; "%s: WinHttpConnect(%s, %hu) failed with"...
0x180098162  mov     r8, [r14]
0x180098165  mov     rdx, rdi
0x180098168  mov     [rsp+0E0h+var_C0], ebx
0x18009816c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180098171  test    ebx, ebx
0x180098173  jle     short loc_1800981A5
0x180098175  movzx   ebx, bx
0x180098178  or      ebx, 80070000h
0x18009817e  jmp     short loc_1800981A5
0x180098180  movzx   r9d, word ptr [rsi+34h]
0x180098185  lea     rcx, aSConnectedToSH; "%s: Connected to %s:%hu."
0x18009818c  mov     r8, [r14]
0x18009818f  mov     rdx, rdi
0x180098192  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180098197  test    r12, r12
0x18009819a  jz      short loc_1800981A5
0x18009819c  mov     rcx, r12; Block
0x18009819f  call    cs:__imp_free
0x1800981a5  mov     eax, ebx
0x1800981a7  mov     rbx, [rsp+0E0h+arg_0]
0x1800981af  add     rsp, 0B0h
0x1800981b6  pop     r15
0x1800981b8  pop     r14
0x1800981ba  pop     r13
0x1800981bc  pop     r12
0x1800981be  pop     rdi
0x1800981bf  pop     rsi
0x1800981c0  pop     rbp
0x1800981c1  retn
```
