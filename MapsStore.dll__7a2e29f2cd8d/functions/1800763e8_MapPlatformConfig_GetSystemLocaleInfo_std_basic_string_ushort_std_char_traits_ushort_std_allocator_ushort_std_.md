# MapPlatformConfig::GetSystemLocaleInfo(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x1800763e8`
- end: `0x1800764f1`
- name: `?GetSystemLocaleInfo@MapPlatformConfig@@SAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `265`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180019030`
- `0x18001944c`

## callees

- `0x18000d090`
- `0x18001d108`
- `0x1800763e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076436`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076488`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076436`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076488`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18007642c`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18007647e`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18007642c`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18007647e`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180076460`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180076460`

## string_xrefs

- `0x180076457`: `MapPlatformConfig::GetSystemLocaleInfo`

## pseudocode

```c
__int64 __fastcall MapPlatformConfig::GetSystemLocaleInfo(__int64 a1, __int64 a2)
{
  signed int LastError; // eax
  int v5; // r8d
  unsigned int v6; // ebx
  WCHAR v8[88]; // [rsp+20h] [rbp-178h] BYREF
  WCHAR LCData[88]; // [rsp+D0h] [rbp-C8h] BYREF

  if ( GetLocaleInfoEx(L"!x-sys-default-locale", 0x5Cu, LCData, 85) > 0 )
  {
    if ( GetLocaleInfoEx(L"!x-sys-default-locale", 0x5Au, v8, 85) > 0 )
    {
      v6 = 0;
      std::wstring::assign(a1, v8);
      std::wstring::assign(a2, LCData);
      return v6;
    }
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    v5 = 294;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    v5 = 293;
  }
  return (unsigned int)ZTraceReportOriginationNoThis(LastError, "MapPlatformConfig::GetSystemLocaleInfo", v5);
}

```

## disassembly

```asm
0x1800763e8  mov     [rsp+arg_10], rbx
0x1800763ed  mov     [rsp+arg_18], rsi
0x1800763f2  push    rdi
0x1800763f3  sub     rsp, 190h
0x1800763fa  mov     rax, cs:__security_cookie
0x180076401  xor     rax, rsp
0x180076404  mov     [rsp+198h+var_18], rax
0x18007640c  mov     ebx, 55h ; 'U'
0x180076411  lea     r8, [rsp+198h+LCData]; lpLCData
0x180076419  mov     rsi, rdx
0x18007641c  mov     rdi, rcx
0x18007641f  mov     r9d, ebx; cchData
0x180076422  lea     rcx, LocaleName; "!x-sys-default-locale"
0x180076429  lea     edx, [rbx+7]; LCType
0x18007642c  call    cs:__imp_GetLocaleInfoEx
0x180076432  test    eax, eax
0x180076434  jg      short loc_18007646A
0x180076436  call    cs:__imp_GetLastError
0x18007643c  test    eax, eax
0x18007643e  jz      short loc_18007644C
0x180076440  jle     short loc_180076451
0x180076442  movzx   eax, ax
0x180076445  or      eax, 80070000h
0x18007644a  jmp     short loc_180076451
0x18007644c  mov     eax, 80390004h
0x180076451  mov     r8d, 125h
0x180076457  lea     rdx, aMapplatformcon; "MapPlatformConfig::GetSystemLocaleInfo"
0x18007645e  mov     ecx, eax
0x180076460  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180076466  mov     ebx, eax
0x180076468  jmp     short loc_1800764CA
0x18007646a  mov     r9d, ebx; cchData
0x18007646d  lea     r8, [rsp+198h+var_178]; lpLCData
0x180076472  mov     edx, 5Ah ; 'Z'; LCType
0x180076477  lea     rcx, LocaleName; "!x-sys-default-locale"
0x18007647e  call    cs:__imp_GetLocaleInfoEx
0x180076484  test    eax, eax
0x180076486  jg      short loc_1800764AB
0x180076488  call    cs:__imp_GetLastError
0x18007648e  test    eax, eax
0x180076490  jz      short loc_18007649E
0x180076492  jle     short loc_1800764A3
0x180076494  movzx   eax, ax
0x180076497  or      eax, 80070000h
0x18007649c  jmp     short loc_1800764A3
0x18007649e  mov     eax, 80390004h
0x1800764a3  mov     r8d, 126h
0x1800764a9  jmp     short loc_180076457
0x1800764ab  lea     rdx, [rsp+198h+var_178]
0x1800764b0  mov     rcx, rdi
0x1800764b3  xor     ebx, ebx
0x1800764b5  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800764ba  lea     rdx, [rsp+198h+LCData]
0x1800764c2  mov     rcx, rsi
0x1800764c5  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800764ca  mov     eax, ebx
0x1800764cc  mov     rcx, [rsp+198h+var_18]
0x1800764d4  xor     rcx, rsp; StackCookie
0x1800764d7  call    __security_check_cookie
0x1800764dc  lea     r11, [rsp+198h+var_8]
0x1800764e4  mov     rbx, [r11+20h]
0x1800764e8  mov     rsi, [r11+28h]
0x1800764ec  mov     rsp, r11
0x1800764ef  pop     rdi
0x1800764f0  retn
```
