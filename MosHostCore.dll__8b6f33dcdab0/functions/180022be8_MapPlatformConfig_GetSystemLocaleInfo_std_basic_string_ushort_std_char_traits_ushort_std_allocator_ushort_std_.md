# MapPlatformConfig::GetSystemLocaleInfo(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180022be8`
- end: `0x180022cf1`
- name: `?GetSystemLocaleInfo@MapPlatformConfig@@SAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `265`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001e664`
- `0x180022a54`

## callees

- `0x180003410`
- `0x18000af48`
- `0x180022be8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022c36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022c88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022c36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022c88`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180022c2c`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180022c7e`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180022c2c`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180022c7e`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180022c60`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180022c60`

## string_xrefs

- `0x180022c57`: `MapPlatformConfig::GetSystemLocaleInfo`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180022be8  mov     [rsp+arg_10], rbx
0x180022bed  mov     [rsp+arg_18], rsi
0x180022bf2  push    rdi
0x180022bf3  sub     rsp, 190h
0x180022bfa  mov     rax, cs:__security_cookie
0x180022c01  xor     rax, rsp
0x180022c04  mov     [rsp+198h+var_18], rax
0x180022c0c  mov     ebx, 55h ; 'U'
0x180022c11  lea     r8, [rsp+198h+LCData]; lpLCData
0x180022c19  mov     rsi, rdx
0x180022c1c  mov     rdi, rcx
0x180022c1f  mov     r9d, ebx; cchData
0x180022c22  lea     rcx, LocaleName; "!x-sys-default-locale"
0x180022c29  lea     edx, [rbx+7]; LCType
0x180022c2c  call    cs:__imp_GetLocaleInfoEx
0x180022c32  test    eax, eax
0x180022c34  jg      short loc_180022C6A
0x180022c36  call    cs:__imp_GetLastError
0x180022c3c  test    eax, eax
0x180022c3e  jz      short loc_180022C4C
0x180022c40  jle     short loc_180022C51
0x180022c42  movzx   eax, ax
0x180022c45  or      eax, 80070000h
0x180022c4a  jmp     short loc_180022C51
0x180022c4c  mov     eax, 80390004h
0x180022c51  mov     r8d, 125h
0x180022c57  lea     rdx, aMapplatformcon_1; "MapPlatformConfig::GetSystemLocaleInfo"
0x180022c5e  mov     ecx, eax
0x180022c60  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180022c66  mov     ebx, eax
0x180022c68  jmp     short loc_180022CCA
0x180022c6a  mov     r9d, ebx; cchData
0x180022c6d  lea     r8, [rsp+198h+var_178]; lpLCData
0x180022c72  mov     edx, 5Ah ; 'Z'; LCType
0x180022c77  lea     rcx, LocaleName; "!x-sys-default-locale"
0x180022c7e  call    cs:__imp_GetLocaleInfoEx
0x180022c84  test    eax, eax
0x180022c86  jg      short loc_180022CAB
0x180022c88  call    cs:__imp_GetLastError
0x180022c8e  test    eax, eax
0x180022c90  jz      short loc_180022C9E
0x180022c92  jle     short loc_180022CA3
0x180022c94  movzx   eax, ax
0x180022c97  or      eax, 80070000h
0x180022c9c  jmp     short loc_180022CA3
0x180022c9e  mov     eax, 80390004h
0x180022ca3  mov     r8d, 126h
0x180022ca9  jmp     short loc_180022C57
0x180022cab  lea     rdx, [rsp+198h+var_178]
0x180022cb0  mov     rcx, rdi
0x180022cb3  xor     ebx, ebx
0x180022cb5  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180022cba  lea     rdx, [rsp+198h+LCData]
0x180022cc2  mov     rcx, rsi
0x180022cc5  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180022cca  mov     eax, ebx
0x180022ccc  mov     rcx, [rsp+198h+var_18]
0x180022cd4  xor     rcx, rsp; StackCookie
0x180022cd7  call    __security_check_cookie
0x180022cdc  lea     r11, [rsp+198h+var_8]
0x180022ce4  mov     rbx, [r11+20h]
0x180022ce8  mov     rsi, [r11+28h]
0x180022cec  mov     rsp, r11
0x180022cef  pop     rdi
0x180022cf0  retn
```
