# MapPlatformConfig::GetLocaleMapConfiguration(ILocaleMapConfiguration * *)

- ea: `0x18000d8b8`
- end: `0x18000db0c`
- name: `?GetLocaleMapConfiguration@MapPlatformConfig@@SAJPEAPEAUILocaleMapConfiguration@@@Z`
- size: `596`
- prototype: `__int64 __fastcall(struct ILocaleMapConfiguration **)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180008dc0`
- `0x180009cc0`

## callees

- `0x180001c80`
- `0x180006c44`
- `0x18000c860`
- `0x18000d6c4`
- `0x18000d8b8`
- `0x18000dcc8`
- `0x18000e7f8`
- `0x180010010`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000d966`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000d966`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000d929`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000da09`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000d929`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000da09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000da51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000da51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d93a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d9ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000da3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dad2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dae0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d93a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d9ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000da3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dad2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dae0`
- `Bcp47Langs!GetUserLanguages` at `0x18000d94d`
- `Bcp47Langs!GetUserLanguages` at `0x18000d94d`
- `MapConfiguration!ConfigurationManager_Create` at `0x18000d910`
- `MapConfiguration!ConfigurationManager_Create` at `0x18000d910`

## string_xrefs

- `0x18000da00`: `MapPlatformConfig::GetUserRegion`
- `0x18000d95d`: `MapPlatformConfig::GetUserProfileLanguages`
- `0x18000d920`: `MapPlatformConfig::GetLocaleMapConfiguration`

## pseudocode

```c
__int64 __fastcall MapPlatformConfig::GetLocaleMapConfiguration(struct ILocaleMapConfiguration **a1)
{
  HRESULT v2; // eax
  int v3; // r8d
  unsigned int v4; // ebx
  int UserLanguages; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r8
  PCNZWCH *v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  PCNZWCH *v14; // rdi
  UINT32 v15; // edx
  const WCHAR *v16; // rcx
  int UserRegionInternal; // eax
  unsigned __int64 v18; // rbx
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, HSTRING, HSTRING, __int64, struct ILocaleMapConfiguration **); // rbx
  __int64 v21; // r9
  __int64 v22; // rcx
  HSTRING v24; // [rsp+30h] [rbp-50h] BYREF
  HSTRING string; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v26[2]; // [rsp+40h] [rbp-40h] BYREF
  PCNZWCH sourceString[2]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v28; // [rsp+60h] [rbp-20h]
  unsigned __int64 v29; // [rsp+68h] [rbp-18h]

  string = 0;
  v24 = 0;
  *(_OWORD *)sourceString = 0;
  v28 = 0;
  v29 = 7;
  LOWORD(sourceString[0]) = 0;
  v26[0] = 0;
  v26[1] = 0;
  v2 = ConfigurationManager_Create(v26);
  if ( v2 < 0 )
  {
    v3 = 223;
LABEL_3:
    v4 = ZTraceReportPropagationNoThis(v2, "MapPlatformConfig::GetLocaleMapConfiguration", v3);
    goto LABEL_31;
  }
  WindowsDeleteString(string);
  string = 0;
  UserLanguages = GetUserLanguages(59, &string);
  if ( UserLanguages < 0 )
  {
    v2 = ZTraceReportOriginationNoThis(UserLanguages, "MapPlatformConfig::GetUserProfileLanguages", 207);
    if ( v2 < 0 )
    {
      v3 = 224;
      goto LABEL_3;
    }
  }
  if ( MapPlatformConfig::GetChinaVariant(v7, v6, v8) )
  {
    if ( v29 < 3 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)sourceString,
        3u,
        v9,
        L"CHN");
    }
    else
    {
      v10 = sourceString;
      if ( v29 > 7 )
        v10 = (PCNZWCH *)sourceString[0];
      v28 = 3;
      memmove_0(v10, L"CHN", 6u);
      *((_WORD *)v10 + 3) = 0;
    }
  }
  else
  {
    UserRegionInternal = MapPlatformConfig::GetUserRegionInternal(sourceString);
    if ( UserRegionInternal < 0 )
    {
      v2 = ZTraceReportPropagationNoThis(UserRegionInternal, "MapPlatformConfig::GetUserRegion", 169);
      if ( v2 < 0 )
      {
        v3 = 225;
        goto LABEL_3;
      }
    }
  }
  if ( v29 <= 7 )
  {
    v14 = sourceString;
  }
  else
  {
    v14 = (PCNZWCH *)sourceString[0];
    if ( !sourceString[0] )
    {
      WindowsDeleteString(v24);
      v15 = 0;
      v16 = (const WCHAR *)&qword_180012888;
LABEL_24:
      v24 = 0;
      v2 = WindowsCreateString(v16, v15, &v24);
      goto LABEL_26;
    }
  }
  v18 = -1;
  do
    ++v18;
  while ( *((_WORD *)v14 + v18) );
  if ( v18 <= 0xFFFFFFFF )
  {
    WindowsDeleteString(v24);
    v15 = v18;
    v16 = (const WCHAR *)v14;
    goto LABEL_24;
  }
  v2 = -2147024362;
LABEL_26:
  if ( v2 < 0 )
  {
    v3 = 226;
    goto LABEL_3;
  }
  v19 = v26[0];
  v20 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, __int64, struct ILocaleMapConfiguration **))(*(_QWORD *)v26[0] + 48LL);
  LOBYTE(v21) = MapPlatformConfig::GetChinaVariant(v12, v11, v13);
  v2 = v20(v19, string, v24, v21, a1);
  if ( v2 < 0 )
  {
    v3 = 227;
    goto LABEL_3;
  }
  v4 = 0;
LABEL_31:
  v22 = v26[0];
  if ( v26[0] )
  {
    v26[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  std::wstring::~wstring((char **)sourceString);
  WindowsDeleteString(v24);
  v24 = 0;
  WindowsDeleteString(string);
  return v4;
}

```

## disassembly

```asm
0x18000d8b8  mov     [rsp-18h+arg_8], rbx
0x18000d8bd  mov     [rsp-18h+arg_10], rsi
0x18000d8c2  push    rbp
0x18000d8c3  push    rdi
0x18000d8c4  push    r14
0x18000d8c6  mov     rbp, rsp
0x18000d8c9  sub     rsp, 80h
0x18000d8d0  mov     rax, cs:__security_cookie
0x18000d8d7  xor     rax, rsp
0x18000d8da  mov     [rbp+var_10], rax
0x18000d8de  mov     rsi, rcx
0x18000d8e1  xor     r14d, r14d
0x18000d8e4  mov     [rbp+string], r14
0x18000d8e8  mov     [rbp+var_50], r14
0x18000d8ec  xorps   xmm0, xmm0
0x18000d8ef  movups  xmmword ptr [rbp+sourceString], xmm0
0x18000d8f3  mov     [rbp+var_20], r14
0x18000d8f7  mov     [rbp+var_18], 7
0x18000d8ff  mov     word ptr [rbp+sourceString], r14w
0x18000d904  mov     [rbp+var_40], r14
0x18000d908  mov     [rbp+var_38], r14
0x18000d90c  lea     rcx, [rbp+var_40]
0x18000d910  call    cs:__imp_ConfigurationManager_Create
0x18000d916  test    eax, eax
0x18000d918  jns     short loc_18000D936
0x18000d91a  mov     r8d, 0DFh
0x18000d920  lea     rdx, aMapplatformcon_0; "MapPlatformConfig::GetLocaleMapConfigur"...
0x18000d927  mov     ecx, eax
0x18000d929  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000d92f  mov     ebx, eax
0x18000d931  jmp     loc_18000DAAA
0x18000d936  mov     rcx, [rbp+string]; string
0x18000d93a  call    cs:__imp_WindowsDeleteString
0x18000d940  mov     [rbp+string], r14
0x18000d944  mov     ecx, 3Bh ; ';'
0x18000d949  lea     rdx, [rbp+string]
0x18000d94d  call    cs:__imp_GetUserLanguages
0x18000d953  test    eax, eax
0x18000d955  jns     short loc_18000D978
0x18000d957  mov     r8d, 0CFh
0x18000d95d  lea     rdx, aMapplatformcon_2; "MapPlatformConfig::GetUserProfileLangua"...
0x18000d964  mov     ecx, eax
0x18000d966  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000d96c  test    eax, eax
0x18000d96e  jns     short loc_18000D978
0x18000d970  mov     r8d, 0E0h
0x18000d976  jmp     short loc_18000D920
0x18000d978  call    ?GetChinaVariant@MapPlatformConfig@@CA_N_N@Z; MapPlatformConfig::GetChinaVariant(bool)
0x18000d97d  test    al, al
0x18000d97f  jz      short loc_18000D9ED
0x18000d981  mov     edx, 3
0x18000d986  cmp     [rbp+var_18], rdx
0x18000d98a  jb      short loc_18000D9DB
0x18000d98c  lea     rbx, [rbp+sourceString]
0x18000d990  cmp     [rbp+var_18], 7
0x18000d995  cmova   rbx, [rbp+sourceString]
0x18000d99a  mov     [rbp+var_20], rdx
0x18000d99e  lea     r8d, [rdx+3]; Size
0x18000d9a2  lea     rdx, aChn; "CHN"
0x18000d9a9  mov     rcx, rbx; void *
0x18000d9ac  call    memmove_0
0x18000d9b1  mov     [rbx+6], r14w
0x18000d9b6  cmp     [rbp+var_18], 7
0x18000d9bb  jbe     short loc_18000DA1E
0x18000d9bd  mov     rdi, [rbp+sourceString]
0x18000d9c1  test    rdi, rdi
0x18000d9c4  jnz     short loc_18000DA22
0x18000d9c6  mov     rcx, [rbp+var_50]; string
0x18000d9ca  call    cs:__imp_WindowsDeleteString
0x18000d9d0  xor     edx, edx
0x18000d9d2  lea     rcx, qword_180012888
0x18000d9d9  jmp     short loc_18000DA49
0x18000d9db  lea     r9, aChn; "CHN"
0x18000d9e2  lea     rcx, [rbp+sourceString]
0x18000d9e6  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000d9eb  jmp     short loc_18000D9B6
0x18000d9ed  lea     rcx, [rbp+sourceString]
0x18000d9f1  call    ?GetUserRegionInternal@MapPlatformConfig@@CAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MapPlatformConfig::GetUserRegionInternal(std::wstring *)
0x18000d9f6  test    eax, eax
0x18000d9f8  jns     short loc_18000D9B6
0x18000d9fa  mov     r8d, 0A9h
0x18000da00  lea     rdx, aMapplatformcon_4; "MapPlatformConfig::GetUserRegion"
0x18000da07  mov     ecx, eax
0x18000da09  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000da0f  test    eax, eax
0x18000da11  jns     short loc_18000D9B6
0x18000da13  mov     r8d, 0E1h
0x18000da19  jmp     loc_18000D920
0x18000da1e  lea     rdi, [rbp+sourceString]
0x18000da22  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000da26  inc     rbx
0x18000da29  cmp     [rdi+rbx*2], r14w
0x18000da2e  jnz     short loc_18000DA26
0x18000da30  mov     eax, 0FFFFFFFFh
0x18000da35  cmp     rbx, rax
0x18000da38  ja      short loc_18000DA59
0x18000da3a  mov     rcx, [rbp+var_50]; string
0x18000da3e  call    cs:__imp_WindowsDeleteString
0x18000da44  mov     edx, ebx; length
0x18000da46  mov     rcx, rdi; sourceString
0x18000da49  lea     r8, [rbp+var_50]; string
0x18000da4d  mov     [rbp+var_50], r14
0x18000da51  call    cs:__imp_WindowsCreateString
0x18000da57  jmp     short loc_18000DA5E
0x18000da59  mov     eax, 80070216h
0x18000da5e  test    eax, eax
0x18000da60  jns     short loc_18000DA6D
0x18000da62  mov     r8d, 0E2h
0x18000da68  jmp     loc_18000D920
0x18000da6d  mov     rdi, [rbp+var_40]
0x18000da71  mov     rax, [rdi]
0x18000da74  mov     rbx, [rax+30h]
0x18000da78  call    ?GetChinaVariant@MapPlatformConfig@@CA_N_N@Z; MapPlatformConfig::GetChinaVariant(bool)
0x18000da7d  mov     [rsp+80h+var_60], rsi
0x18000da82  mov     r9b, al
0x18000da85  mov     r8, [rbp+var_50]
0x18000da89  mov     rdx, [rbp+string]
0x18000da8d  mov     rcx, rdi
0x18000da90  mov     rax, rbx
0x18000da93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da98  test    eax, eax
0x18000da9a  jns     short loc_18000DAA7
0x18000da9c  mov     r8d, 0E3h
0x18000daa2  jmp     loc_18000D920
0x18000daa7  mov     ebx, r14d
0x18000daaa  mov     rcx, [rbp+var_40]
0x18000daae  test    rcx, rcx
0x18000dab1  jz      short loc_18000DAC4
0x18000dab3  mov     [rbp+var_40], r14
0x18000dab7  mov     rax, [rcx]
0x18000daba  mov     rax, [rax+10h]
0x18000dabe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dac3  nop
0x18000dac4  lea     rcx, [rbp+sourceString]
0x18000dac8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000dacd  nop
0x18000dace  mov     rcx, [rbp+var_50]; string
0x18000dad2  call    cs:__imp_WindowsDeleteString
0x18000dad8  mov     [rbp+var_50], r14
0x18000dadc  mov     rcx, [rbp+string]; string
0x18000dae0  call    cs:__imp_WindowsDeleteString
0x18000dae6  mov     eax, ebx
0x18000dae8  mov     rcx, [rbp+var_10]
0x18000daec  xor     rcx, rsp; StackCookie
0x18000daef  call    __security_check_cookie
0x18000daf4  lea     r11, [rsp+80h+var_s0]
0x18000dafc  mov     rbx, [r11+28h]
0x18000db00  mov     rsi, [r11+30h]
0x18000db04  mov     rsp, r11
0x18000db07  pop     r14
0x18000db09  pop     rdi
0x18000db0a  pop     rbp
0x18000db0b  retn
```
