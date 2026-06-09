# MapPlatformConfig::GetChinaVariant(bool)

- ea: `0x180022a54`
- end: `0x180022be0`
- name: `?GetChinaVariant@MapPlatformConfig@@CA_N_N@Z`
- size: `396`
- prototype: `bool __fastcall(__int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015b40`
- `0x180016e80`

## callees

- `0x180003410`
- `0x1800079d4`
- `0x180008110`
- `0x18000816c`
- `0x18000b09c`
- `0x180020688`
- `0x180020720`
- `0x180020ec8`
- `0x180022a54`
- `0x180022be8`
- `0x180022cf8`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180022b88`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180022bb7`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180022b88`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180022bb7`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180022a9b`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180022af9`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180022a9b`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180022af9`

## string_xrefs

- `0x180022a92`: `MapPlatformConfig::GetChinaVariant`
- `0x180022af0`: `MapPlatformConfig::GetChinaVariant`
- `0x180022b7f`: `MapPlatformConfig::GetChinaVariant`
- `0x180022bae`: `MapPlatformConfig::GetChinaVariant`

## pseudocode

```c
bool __fastcall MapPlatformConfig::GetChinaVariant(__int64 a1)
{
  char v1; // si
  int MapsPersistedRegBoolean; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx
  bool v5; // bl
  int v6; // eax
  int SystemLocaleInfo; // eax
  unsigned __int64 v8; // rdi
  size_t v9; // rbx
  const wchar_t *v10; // rax
  const wchar_t *v11; // rdx
  size_t v12; // r8
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // r8
  bool v16; // zf
  int v17; // eax
  int v18; // eax
  bool v20[8]; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v21[16]; // [rsp+28h] [rbp-50h] BYREF
  size_t v22; // [rsp+38h] [rbp-40h]
  _BYTE v23[32]; // [rsp+48h] [rbp-30h] BYREF

  v1 = a1;
  v20[0] = 0;
  MapsPersistedRegBoolean = RegUtils::GetMapsPersistedRegBoolean(a1, L"OEMChinaVariantWin10", 0, v20);
  if ( MapsPersistedRegBoolean < 0 )
  {
    ZTraceReportPropagationNoThis(MapsPersistedRegBoolean, "MapPlatformConfig::GetChinaVariant", 73);
LABEL_20:
    v5 = v20[0];
    goto LABEL_21;
  }
  v5 = v20[0];
  if ( !v20[0] )
  {
    v6 = RegUtils::GetMapsPersistedRegBoolean(v4, v3, v20);
    if ( v6 != -2147024894 )
    {
      if ( v6 < 0 )
        ZTraceReportOriginationNoThis(v6, "MapPlatformConfig::GetChinaVariant", 105);
      goto LABEL_20;
    }
    std::wstring::wstring((__int64)v21);
    std::wstring::wstring((__int64)v23);
    SystemLocaleInfo = MapPlatformConfig::GetSystemLocaleInfo(v21, v23);
    if ( SystemLocaleInfo < 0 )
    {
      ZTraceReportPropagationNoThis(SystemLocaleInfo, "MapPlatformConfig::GetChinaVariant", 94);
      std::wstring::_Tidy_deallocate((__int64)v23);
      std::wstring::_Tidy_deallocate((__int64)v21);
      goto LABEL_20;
    }
    v8 = std::_WChar_traits<unsigned short>::length(L"CN");
    v9 = v22;
    v10 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    v12 = v9;
    if ( v8 < v9 )
      v12 = v8;
    v13 = std::_WChar_traits<unsigned short>::compare(v10, v11, v12);
    v16 = v13 == 0;
    if ( !v13 )
    {
      if ( v9 >= v8 )
        v17 = v9 > v8;
      else
        v17 = -1;
      v16 = v17 == 0;
    }
    v5 = v16;
    if ( v1 )
    {
      LOBYTE(v15) = v16;
      v18 = RegUtils::SetMapsPersistedRegBoolean(v14, L"ChinaVariant", v15);
      if ( v18 < 0 )
        ZTraceReportOriginationNoThis(v18, "MapPlatformConfig::GetChinaVariant", 100);
    }
    std::wstring::_Tidy_deallocate((__int64)v23);
    std::wstring::_Tidy_deallocate((__int64)v21);
  }
LABEL_21:
  dword_18003531C = v5;
  return v5;
}

```

## disassembly

```asm
0x180022a54  push    rbp
0x180022a56  push    rbx
0x180022a57  push    rsi
0x180022a58  push    rdi
0x180022a59  mov     rbp, rsp
0x180022a5c  sub     rsp, 78h
0x180022a60  mov     rax, cs:__security_cookie
0x180022a67  xor     rax, rsp
0x180022a6a  mov     [rbp+var_10], rax
0x180022a6e  mov     sil, cl
0x180022a71  mov     [rbp+var_58], 0
0x180022a75  lea     r9, [rbp+var_58]
0x180022a79  xor     r8d, r8d
0x180022a7c  lea     rdx, aOemchinavarian; "OEMChinaVariantWin10"
0x180022a83  call    ?GetMapsPersistedRegBoolean@RegUtils@@SAJW4MapsRegKeys@@PEBG_NPEA_N@Z; RegUtils::GetMapsPersistedRegBoolean(MapsRegKeys,ushort const *,bool,bool *)
0x180022a88  test    eax, eax
0x180022a8a  jns     short loc_180022AA6
0x180022a8c  mov     r8d, 49h ; 'I'
0x180022a92  lea     rdx, aMapplatformcon_0; "MapPlatformConfig::GetChinaVariant"
0x180022a99  mov     ecx, eax
0x180022a9b  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180022aa1  jmp     loc_180022BBD
0x180022aa6  mov     bl, [rbp+var_58]
0x180022aa9  test    bl, bl
0x180022aab  jnz     loc_180022BC0
0x180022ab1  lea     r8, [rbp+var_58]
0x180022ab5  call    ?GetMapsPersistedRegBoolean@RegUtils@@SAJW4MapsRegKeys@@PEBGPEA_N@Z; RegUtils::GetMapsPersistedRegBoolean(MapsRegKeys,ushort const *,bool *)
0x180022aba  cmp     eax, 80070002h
0x180022abf  jnz     loc_180022BA4
0x180022ac5  lea     rcx, [rbp+var_50]
0x180022ac9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180022ace  nop
0x180022acf  lea     rcx, [rbp+var_30]
0x180022ad3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180022ad8  nop
0x180022ad9  lea     rdx, [rbp+var_30]
0x180022add  lea     rcx, [rbp+var_50]
0x180022ae1  call    ?GetSystemLocaleInfo@MapPlatformConfig@@SAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; MapPlatformConfig::GetSystemLocaleInfo(std::wstring *,std::wstring *)
0x180022ae6  test    eax, eax
0x180022ae8  jns     short loc_180022B18
0x180022aea  mov     r8d, 5Eh ; '^'
0x180022af0  lea     rdx, aMapplatformcon_0; "MapPlatformConfig::GetChinaVariant"
0x180022af7  mov     ecx, eax
0x180022af9  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180022aff  nop
0x180022b00  lea     rcx, [rbp+var_30]
0x180022b04  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022b09  nop
0x180022b0a  lea     rcx, [rbp+var_50]
0x180022b0e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022b13  jmp     loc_180022BBD
0x180022b18  lea     rcx, aCn; "CN"
0x180022b1f  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180022b24  mov     rdi, rax
0x180022b27  mov     rbx, [rbp+var_40]
0x180022b2b  lea     rcx, [rbp+var_50]
0x180022b2f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180022b34  mov     r8, rbx
0x180022b37  cmp     rdi, rbx
0x180022b3a  cmovb   r8, rdi; N
0x180022b3e  mov     rcx, rax; S1
0x180022b41  call    ?compare@?$_WChar_traits@G@std@@SAHQEBG0_K@Z; std::_WChar_traits<ushort>::compare(ushort const * const,ushort const * const,unsigned __int64)
0x180022b46  test    eax, eax
0x180022b48  jnz     short loc_180022B5E
0x180022b4a  cmp     rbx, rdi
0x180022b4d  jnb     short loc_180022B54
0x180022b4f  or      eax, 0FFFFFFFFh
0x180022b52  jmp     short loc_180022B5C
0x180022b54  xor     eax, eax
0x180022b56  cmp     rbx, rdi
0x180022b59  setnbe  al
0x180022b5c  test    eax, eax
0x180022b5e  setz    bl
0x180022b61  test    sil, sil
0x180022b64  jz      short loc_180022B8F
0x180022b66  mov     r8b, bl
0x180022b69  lea     rdx, aChinavariant; "ChinaVariant"
0x180022b70  call    ?SetMapsPersistedRegBoolean@RegUtils@@SAJW4MapsRegKeys@@PEBG_N@Z; RegUtils::SetMapsPersistedRegBoolean(MapsRegKeys,ushort const *,bool)
0x180022b75  test    eax, eax
0x180022b77  jns     short loc_180022B8F
0x180022b79  mov     r8d, 64h ; 'd'
0x180022b7f  lea     rdx, aMapplatformcon_0; "MapPlatformConfig::GetChinaVariant"
0x180022b86  mov     ecx, eax
0x180022b88  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180022b8e  nop
0x180022b8f  lea     rcx, [rbp+var_30]
0x180022b93  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022b98  nop
0x180022b99  lea     rcx, [rbp+var_50]
0x180022b9d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022ba2  jmp     short loc_180022BC0
0x180022ba4  test    eax, eax
0x180022ba6  jns     short loc_180022BBD
0x180022ba8  mov     r8d, 69h ; 'i'
0x180022bae  lea     rdx, aMapplatformcon_0; "MapPlatformConfig::GetChinaVariant"
0x180022bb5  mov     ecx, eax
0x180022bb7  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180022bbd  mov     bl, [rbp+var_58]
0x180022bc0  movzx   ecx, bl
0x180022bc3  mov     cs:dword_18003531C, ecx
0x180022bc9  mov     al, bl
0x180022bcb  mov     rcx, [rbp+var_10]
0x180022bcf  xor     rcx, rsp; StackCookie
0x180022bd2  call    __security_check_cookie
0x180022bd7  add     rsp, 78h
0x180022bdb  pop     rdi
0x180022bdc  pop     rsi
0x180022bdd  pop     rbx
0x180022bde  pop     rbp
0x180022bdf  retn
```
