# MapPlatformConfig::GetChinaVariant(bool)

- ea: `0x18000d6c4`
- end: `0x18000d8b1`
- name: `?GetChinaVariant@MapPlatformConfig@@CA_N_N@Z`
- size: `493`
- prototype: `bool __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000d8b8`

## callees

- `0x180001c80`
- `0x180002802`
- `0x180006c44`
- `0x18000ca6c`
- `0x18000cc50`
- `0x18000ccec`
- `0x18000d6c4`
- `0x18000db14`
- `0x18000ded0`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000d87c`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000d87c`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000d71a`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000d766`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000d790`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000d804`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000d71a`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000d766`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000d790`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000d804`

## string_xrefs

- `0x18000d711`: `MapPlatformConfig::GetChinaVariant`
- `0x18000d7fb`: `MapPlatformConfig::GetChinaVariant`
- `0x18000d873`: `MapPlatformConfig::GetChinaVariant`

## pseudocode

```c
bool __fastcall MapPlatformConfig::GetChinaVariant(__int64 a1, __int64 a2, __int64 a3)
{
  int MapsPersistedRegBoolean; // eax
  bool v4; // bl
  int PersistedRegistryLocation; // eax
  const unsigned __int16 *v6; // rdx
  int v7; // eax
  int RegBoolean; // eax
  int SystemLocaleInfo; // eax
  const wchar_t *v10; // rdx
  unsigned __int64 v11; // rbx
  const wchar_t *v12; // rcx
  size_t v13; // r8
  int v14; // eax
  bool v15; // zf
  int v16; // eax
  bool v18[8]; // [rsp+20h] [rbp-E0h] BYREF
  wchar_t *S1[2]; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int64 v20; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v21; // [rsp+40h] [rbp-C0h]
  _OWORD v22[2]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF

  v18[0] = 0;
  MapsPersistedRegBoolean = RegUtils::GetMapsPersistedRegBoolean(0, L"OEMChinaVariantWin10", a3, v18);
  if ( MapsPersistedRegBoolean >= 0 )
  {
    v4 = v18[0];
    if ( !v18[0] )
    {
      memset_0(SubKey, 0, 0x208u);
      PersistedRegistryLocation = RegUtils::GetPersistedRegistryLocation(0, (__int64)SubKey);
      if ( PersistedRegistryLocation >= 0 )
      {
        RegBoolean = RegUtils::GetRegBoolean(SubKey, v6, v18);
        if ( RegBoolean >= 0 )
          v7 = 0;
        else
          v7 = ZTraceReportPropagationNoThis(RegBoolean, "RegUtils::GetMapsPersistedRegBoolean", 524);
        v4 = v18[0];
      }
      else
      {
        v7 = ZTraceReportPropagationNoThis(PersistedRegistryLocation, "RegUtils::GetMapsPersistedRegBoolean", 519);
      }
      if ( v7 == -2147024894 )
      {
        *(_OWORD *)S1 = 0;
        v20 = 0;
        v21 = 7;
        LOWORD(S1[0]) = 0;
        v22[0] = 0;
        v22[1] = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v22[0]) = 0;
        SystemLocaleInfo = MapPlatformConfig::GetSystemLocaleInfo(S1, v22);
        if ( SystemLocaleInfo >= 0 )
        {
          v11 = v20;
          v12 = (const wchar_t *)S1;
          if ( v21 > 7 )
            v12 = S1[0];
          v13 = v20;
          if ( v20 > 2 )
            v13 = 2;
          v14 = wmemcmp(v12, v10, v13);
          v15 = v14 == 0;
          if ( !v14 )
          {
            if ( v11 >= 2 )
              v16 = v11 > 2;
            else
              v16 = -1;
            v15 = v16 == 0;
          }
          v4 = v15;
        }
        else
        {
          ZTraceReportPropagationNoThis(SystemLocaleInfo, "MapPlatformConfig::GetChinaVariant", 94);
        }
        std::wstring::~wstring((char **)v22);
        std::wstring::~wstring((char **)S1);
      }
      else if ( v7 < 0 )
      {
        ZTraceReportOriginationNoThis(v7, "MapPlatformConfig::GetChinaVariant", 105);
      }
    }
  }
  else
  {
    ZTraceReportPropagationNoThis(MapsPersistedRegBoolean, "MapPlatformConfig::GetChinaVariant", 73);
    v4 = v18[0];
  }
  dword_1800181BC = v4;
  return v4;
}

```

## disassembly

```asm
0x18000d6c4  mov     [rsp-8+arg_0], rbx
0x18000d6c9  mov     [rsp-8+arg_8], rdi
0x18000d6ce  push    rbp
0x18000d6cf  lea     rbp, [rsp-190h]
0x18000d6d7  sub     rsp, 290h
0x18000d6de  mov     rax, cs:__security_cookie
0x18000d6e5  xor     rax, rsp
0x18000d6e8  mov     [rbp+190h+var_10], rax
0x18000d6ef  mov     [rsp+290h+var_270], 0
0x18000d6f4  lea     r9, [rsp+290h+var_270]
0x18000d6f9  lea     rdx, aOemchinavarian; "OEMChinaVariantWin10"
0x18000d700  xor     ecx, ecx
0x18000d702  call    ?GetMapsPersistedRegBoolean@RegUtils@@SAJW4MapsRegKeys@@PEBG_NPEA_N@Z; RegUtils::GetMapsPersistedRegBoolean(MapsRegKeys,ushort const *,bool,bool *)
0x18000d707  test    eax, eax
0x18000d709  jns     short loc_18000D729
0x18000d70b  mov     r8d, 49h ; 'I'
0x18000d711  lea     rdx, aMapplatformcon_1; "MapPlatformConfig::GetChinaVariant"
0x18000d718  mov     ecx, eax
0x18000d71a  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000d720  mov     bl, [rsp+290h+var_270]
0x18000d724  jmp     loc_18000D882
0x18000d729  mov     bl, [rsp+290h+var_270]
0x18000d72d  test    bl, bl
0x18000d72f  jnz     loc_18000D882
0x18000d735  xor     edx, edx; Val
0x18000d737  mov     r8d, 208h; Size
0x18000d73d  lea     rcx, [rsp+290h+SubKey]; void *
0x18000d742  call    memset_0
0x18000d747  lea     rdx, [rsp+290h+SubKey]
0x18000d74c  xor     ecx, ecx
0x18000d74e  call    ?GetPersistedRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z; RegUtils::GetPersistedRegistryLocation(MapsRegKeys,ushort *,ulong)
0x18000d753  test    eax, eax
0x18000d755  jns     short loc_18000D76E
0x18000d757  mov     r8d, 207h
0x18000d75d  lea     rdx, aRegutilsGetmap_1; "RegUtils::GetMapsPersistedRegBoolean"
0x18000d764  mov     ecx, eax
0x18000d766  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000d76c  jmp     short loc_18000D79E
0x18000d76e  lea     r8, [rsp+290h+var_270]; bool *
0x18000d773  lea     rcx, [rsp+290h+SubKey]; lpSubKey
0x18000d778  call    ?GetRegBoolean@RegUtils@@SAJPEBG0PEA_N@Z; RegUtils::GetRegBoolean(ushort const *,ushort const *,bool *)
0x18000d77d  test    eax, eax
0x18000d77f  jns     short loc_18000D798
0x18000d781  mov     r8d, 20Ch
0x18000d787  lea     rdx, aRegutilsGetmap_1; "RegUtils::GetMapsPersistedRegBoolean"
0x18000d78e  mov     ecx, eax
0x18000d790  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000d796  jmp     short loc_18000D79A
0x18000d798  xor     eax, eax
0x18000d79a  mov     bl, [rsp+290h+var_270]
0x18000d79e  cmp     eax, 80070002h
0x18000d7a3  jnz     loc_18000D869
0x18000d7a9  xorps   xmm0, xmm0
0x18000d7ac  movups  xmmword ptr [rsp+290h+S1], xmm0
0x18000d7b1  mov     [rsp+290h+var_258], 0
0x18000d7ba  mov     [rsp+290h+var_250], 7
0x18000d7c3  xor     eax, eax
0x18000d7c5  mov     word ptr [rsp+290h+S1], ax
0x18000d7ca  movups  [rsp+290h+var_248], xmm0
0x18000d7cf  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000d7d7  movdqu  [rsp+290h+var_238], xmm1
0x18000d7dd  mov     word ptr [rsp+290h+var_248], ax
0x18000d7e2  lea     rdx, [rsp+290h+var_248]
0x18000d7e7  lea     rcx, [rsp+290h+S1]
0x18000d7ec  call    ?GetSystemLocaleInfo@MapPlatformConfig@@SAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; MapPlatformConfig::GetSystemLocaleInfo(std::wstring *,std::wstring *)
0x18000d7f1  test    eax, eax
0x18000d7f3  jns     short loc_18000D822
0x18000d7f5  mov     r8d, 5Eh ; '^'
0x18000d7fb  lea     rdx, aMapplatformcon_1; "MapPlatformConfig::GetChinaVariant"
0x18000d802  mov     ecx, eax
0x18000d804  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000d80a  nop
0x18000d80b  lea     rcx, [rsp+290h+var_248]
0x18000d810  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d815  nop
0x18000d816  lea     rcx, [rsp+290h+S1]
0x18000d81b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d820  jmp     short loc_18000D882
0x18000d822  mov     rbx, [rsp+290h+var_258]
0x18000d827  lea     rcx, [rsp+290h+S1]
0x18000d82c  cmp     [rsp+290h+var_250], 7
0x18000d832  cmova   rcx, [rsp+290h+S1]; S1
0x18000d838  mov     r8, rbx
0x18000d83b  mov     edi, 2
0x18000d840  cmp     rbx, rdi
0x18000d843  cmova   r8, rdi; N
0x18000d847  call    wmemcmp
0x18000d84c  test    eax, eax
0x18000d84e  jnz     short loc_18000D864
0x18000d850  cmp     rbx, rdi
0x18000d853  jnb     short loc_18000D85A
0x18000d855  or      eax, 0FFFFFFFFh
0x18000d858  jmp     short loc_18000D862
0x18000d85a  xor     eax, eax
0x18000d85c  cmp     rbx, rdi
0x18000d85f  setnbe  al
0x18000d862  test    eax, eax
0x18000d864  setz    bl
0x18000d867  jmp     short loc_18000D80B
0x18000d869  test    eax, eax
0x18000d86b  jns     short loc_18000D882
0x18000d86d  mov     r8d, 69h ; 'i'
0x18000d873  lea     rdx, aMapplatformcon_1; "MapPlatformConfig::GetChinaVariant"
0x18000d87a  mov     ecx, eax
0x18000d87c  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000d882  movzx   ecx, bl
0x18000d885  mov     cs:dword_1800181BC, ecx
0x18000d88b  mov     al, bl
0x18000d88d  mov     rcx, [rbp+190h+var_10]
0x18000d894  xor     rcx, rsp; StackCookie
0x18000d897  call    __security_check_cookie
0x18000d89c  lea     r11, [rsp+290h+var_s0]
0x18000d8a4  mov     rbx, [r11+10h]
0x18000d8a8  mov     rdi, [r11+18h]
0x18000d8ac  mov     rsp, r11
0x18000d8af  pop     rbp
0x18000d8b0  retn
```
