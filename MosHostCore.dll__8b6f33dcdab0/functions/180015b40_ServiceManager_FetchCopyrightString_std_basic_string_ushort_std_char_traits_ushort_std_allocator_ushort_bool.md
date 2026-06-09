# ServiceManager::FetchCopyrightString(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,bool *)

- ea: `0x180015b40`
- end: `0x180015dda`
- name: `?FetchCopyrightString@ServiceManager@@AEAAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEA_N@Z`
- size: `666`
- prototype: `__int64 __fastcall(_DWORD *, __int64, bool *)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, service_task`

## callers

- `0x180016240`
- `0x18001d9a0`

## callees

- `0x180003410`
- `0x1800079d4`
- `0x180008110`
- `0x18000816c`
- `0x18000b09c`
- `0x18001191c`
- `0x180012514`
- `0x180015b40`
- `0x180020978`
- `0x180020a1c`
- `0x18002110c`
- `0x1800211f4`
- `0x1800228ec`
- `0x1800229b8`
- `0x180022a2c`
- `0x180022a54`

## import_xrefs

- `MapsStore!MapsStore_GetCopyright` at `0x180015c3c`
- `MapsStore!MapsStore_GetCopyright` at `0x180015c3c`
- `MapsStore!MapsStore_GetGSCode` at `0x180015d2e`
- `MapsStore!MapsStore_GetGSCode` at `0x180015d2e`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180015d0f`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180015d0f`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180015c60`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180015d4a`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180015c60`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180015d4a`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180015bae`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180015bae`

## string_xrefs

- `0x180015b8c`: `LastMapCopyrightExpiry`
- `0x180015cb9`: `LastMapCopyrightExpiry`
- `0x180015bcf`: `LastMapCopyright`
- `0x180015c9c`: `LastMapCopyright`
- `0x180015ced`: `LastMapCopyright`
- `0x180015ba5`: `ServiceManager::FetchCopyrightString`
- `0x180015c59`: `ServiceManager::FetchCopyrightString`
- `0x180015d06`: `ServiceManager::FetchCopyrightString`
- `0x180015d41`: `ServiceManager::FetchCopyrightString`

## pseudocode

```c
__int64 __fastcall ServiceManager::FetchCopyrightString(_DWORD *a1, __int64 a2, bool *a3)
{
  unsigned __int64 CurrentFileTimeAsUint64; // r15
  __int64 v7; // rcx
  __int64 v8; // r8
  int MapsPersistedRegQword; // eax
  __int64 v10; // rcx
  int v11; // r8d
  int v12; // ebx
  bool v13; // r14
  __int64 v14; // rax
  int v15; // ecx
  int Copyright; // eax
  int v17; // r8d
  int v18; // ecx
  __int64 v19; // rax
  unsigned __int64 v20; // rsi
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rcx
  int MapsPersistedRegString; // eax
  int GSCode; // eax
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rax
  unsigned __int64 v30; // [rsp+20h] [rbp-50h] BYREF
  _BYTE v31[16]; // [rsp+28h] [rbp-48h] BYREF
  __int64 v32; // [rsp+38h] [rbp-38h]
  _BYTE v33[16]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v34; // [rsp+58h] [rbp-18h]

  v30 = 0;
  std::wstring::wstring((__int64)v31);
  CurrentFileTimeAsUint64 = TimeUtils::GetCurrentFileTimeAsUint64();
  MapsPersistedRegQword = RegUtils::GetMapsPersistedRegQword(v7, L"LastMapCopyrightExpiry", v8, &v30);
  if ( MapsPersistedRegQword >= 0 )
  {
    v13 = 0;
    if ( CurrentFileTimeAsUint64 >= v30 )
    {
      v14 = v32;
    }
    else
    {
      MapsPersistedRegQword = RegUtils::GetMapsPersistedRegString(v10, L"LastMapCopyright");
      if ( MapsPersistedRegQword < 0 )
      {
        v11 = 2900;
        goto LABEL_3;
      }
      v14 = v32;
      v13 = v32 != 0;
    }
    v12 = 0;
    if ( !v14 )
    {
      CriticalSectionWithConditionVariable::Lock(a1 + 850, v33);
      v15 = a1[882];
      if ( ((v15 - 2) & 0xFFFFFFFC) == 0 && v15 != 4 )
      {
        LODWORD(v30) = 0;
        Copyright = MapsStore_GetCopyright(v31, &v30);
        if ( Copyright != -2147024875 )
          v12 = Copyright;
        if ( v12 < 0 )
        {
          v17 = 2922;
          v18 = v12;
LABEL_16:
          v12 = ZTraceReportPropagation(v18, "ServiceManager::FetchCopyrightString", v17, a1);
          RelockableGate::~RelockableGate((RelockableGate *)v33);
          goto LABEL_34;
        }
        v19 = (unsigned int)v30;
        if ( (unsigned int)v30 > 0x15180 )
        {
          v19 = 86400;
          LODWORD(v30) = 86400;
        }
        v20 = CurrentFileTimeAsUint64 + 10000000 * v19;
        if ( v32 )
        {
          v21 = RegUtils::SetMapsPersistedRegString(86400, L"LastMapCopyright", (__int64)v31);
          if ( v21 < 0 )
          {
            v17 = 2935;
LABEL_22:
            v18 = v21;
            goto LABEL_16;
          }
          v21 = RegUtils::SetMapsPersistedRegQword(v22, L"LastMapCopyrightExpiry", v20);
          if ( v21 < 0 )
          {
            v17 = 2936;
            goto LABEL_22;
          }
          v13 = 1;
        }
      }
      RelockableGate::~RelockableGate((RelockableGate *)v33);
      if ( !v32 )
      {
        MapsPersistedRegString = RegUtils::GetMapsPersistedRegString(v23, L"LastMapCopyright");
        if ( MapsPersistedRegString < 0 )
          ZTraceReportIgnore(MapsPersistedRegString, "ServiceManager::FetchCopyrightString", 2944, a1);
      }
    }
    if ( MapPlatformConfig::GetChinaVariant(0) )
    {
      std::wstring::wstring((__int64)v33);
      GSCode = MapsStore_GetGSCode(v33);
      if ( GSCode < 0 )
      {
        v12 = ZTraceReportPropagation(GSCode, "ServiceManager::FetchCopyrightString", 2951, a1);
        std::wstring::_Tidy_deallocate((__int64)v33);
        goto LABEL_34;
      }
      v26 = std::_WChar_traits<unsigned short>::length(L" ");
      std::wstring::_Append<unsigned short>(v31, v27, v26);
      v28 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
      std::wstring::_Append<unsigned short>(v31, v28, v34);
      std::wstring::_Tidy_deallocate((__int64)v33);
    }
    std::wstring::operator=(a2, v31);
    *a3 = v13;
    goto LABEL_34;
  }
  v11 = 2895;
LABEL_3:
  v12 = ZTraceReportOrigination(MapsPersistedRegQword, "ServiceManager::FetchCopyrightString", v11, a1);
LABEL_34:
  std::wstring::_Tidy_deallocate((__int64)v31);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180015b40  mov     [rsp-38h+arg_18], rbx
0x180015b45  push    rbp
0x180015b46  push    rsi
0x180015b47  push    rdi
0x180015b48  push    r12
0x180015b4a  push    r13
0x180015b4c  push    r14
0x180015b4e  push    r15
0x180015b50  mov     rbp, rsp
0x180015b53  sub     rsp, 70h
0x180015b57  mov     rax, cs:__security_cookie
0x180015b5e  xor     rax, rsp
0x180015b61  mov     [rbp+var_8], rax
0x180015b65  mov     r13, r8
0x180015b68  mov     r12, rdx
0x180015b6b  mov     rdi, rcx
0x180015b6e  mov     [rbp+var_50], 0
0x180015b76  lea     rcx, [rbp+var_48]
0x180015b7a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180015b7f  nop
0x180015b80  call    ?GetCurrentFileTimeAsUint64@TimeUtils@@SA_KXZ; TimeUtils::GetCurrentFileTimeAsUint64(void)
0x180015b85  mov     r15, rax
0x180015b88  lea     r9, [rbp+var_50]
0x180015b8c  lea     rdx, aLastmapcopyrig; "LastMapCopyrightExpiry"
0x180015b93  call    ?GetMapsPersistedRegQword@RegUtils@@SAJW4MapsRegKeys@@PEBG_KPEA_K@Z; RegUtils::GetMapsPersistedRegQword(MapsRegKeys,ushort const *,unsigned __int64,unsigned __int64 *)
0x180015b98  test    eax, eax
0x180015b9a  jns     short loc_180015BBB
0x180015b9c  mov     r8d, 0B4Fh
0x180015ba2  mov     r9, rdi
0x180015ba5  lea     rdx, aServicemanager_34; "ServiceManager::FetchCopyrightString"
0x180015bac  mov     ecx, eax
0x180015bae  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x180015bb4  mov     ebx, eax
0x180015bb6  jmp     loc_180015DAB
0x180015bbb  xor     r14b, r14b
0x180015bbe  cmp     r15, [rbp+var_50]
0x180015bc2  jnb     short loc_180015BF4
0x180015bc4  lea     r9, [rbp+var_48]
0x180015bc8  lea     r8, dword_180027ABC
0x180015bcf  lea     rdx, aLastmapcopyrig_0; "LastMapCopyright"
0x180015bd6  call    ?GetMapsPersistedRegString@RegUtils@@SAJW4MapsRegKeys@@PEBG1PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegUtils::GetMapsPersistedRegString(MapsRegKeys,ushort const *,ushort const *,std::wstring *)
0x180015bdb  test    eax, eax
0x180015bdd  jns     short loc_180015BE7
0x180015bdf  mov     r8d, 0B54h
0x180015be5  jmp     short loc_180015BA2
0x180015be7  mov     rax, [rbp+var_38]
0x180015beb  test    rax, rax
0x180015bee  setnz   r14b
0x180015bf2  jmp     short loc_180015BF8
0x180015bf4  mov     rax, [rbp+var_38]
0x180015bf8  xor     ebx, ebx
0x180015bfa  test    rax, rax
0x180015bfd  jnz     loc_180015D15
0x180015c03  lea     rcx, [rdi+0D48h]
0x180015c0a  lea     rdx, [rbp+var_28]
0x180015c0e  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x180015c13  nop
0x180015c14  mov     ecx, [rdi+0DC8h]
0x180015c1a  lea     eax, [rcx-2]
0x180015c1d  test    eax, 0FFFFFFFCh
0x180015c22  jnz     loc_180015CD4
0x180015c28  cmp     ecx, 4
0x180015c2b  jz      loc_180015CD4
0x180015c31  mov     dword ptr [rbp+var_50], ebx
0x180015c34  lea     rdx, [rbp+var_50]
0x180015c38  lea     rcx, [rbp+var_48]
0x180015c3c  call    cs:__imp_?MapsStore_GetCopyright@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAI@Z; MapsStore_GetCopyright(std::wstring *,uint *)
0x180015c42  cmp     eax, 80070015h
0x180015c47  cmovnz  ebx, eax
0x180015c4a  test    ebx, ebx
0x180015c4c  jns     short loc_180015C76
0x180015c4e  mov     r8d, 0B6Ah
0x180015c54  mov     ecx, ebx
0x180015c56  mov     r9, rdi
0x180015c59  lea     rdx, aServicemanager_34; "ServiceManager::FetchCopyrightString"
0x180015c60  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180015c66  mov     ebx, eax
0x180015c68  lea     rcx, [rbp+var_28]; this
0x180015c6c  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x180015c71  jmp     loc_180015DAB
0x180015c76  mov     eax, dword ptr [rbp+var_50]
0x180015c79  mov     ecx, 15180h
0x180015c7e  cmp     eax, ecx
0x180015c80  jbe     short loc_180015C87
0x180015c82  mov     eax, ecx
0x180015c84  mov     dword ptr [rbp+var_50], eax
0x180015c87  imul    rsi, rax, 989680h
0x180015c8e  add     rsi, r15
0x180015c91  cmp     [rbp+var_38], 0
0x180015c96  jz      short loc_180015CD4
0x180015c98  lea     r8, [rbp+var_48]
0x180015c9c  lea     rdx, aLastmapcopyrig_0; "LastMapCopyright"
0x180015ca3  call    ?SetMapsPersistedRegString@RegUtils@@SAJW4MapsRegKeys@@PEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegUtils::SetMapsPersistedRegString(MapsRegKeys,ushort const *,std::wstring const &)
0x180015ca8  test    eax, eax
0x180015caa  jns     short loc_180015CB6
0x180015cac  mov     r8d, 0B77h
0x180015cb2  mov     ecx, eax
0x180015cb4  jmp     short loc_180015C56
0x180015cb6  mov     r8, rsi
0x180015cb9  lea     rdx, aLastmapcopyrig; "LastMapCopyrightExpiry"
0x180015cc0  call    ?SetMapsPersistedRegQword@RegUtils@@SAJW4MapsRegKeys@@PEBG_K@Z; RegUtils::SetMapsPersistedRegQword(MapsRegKeys,ushort const *,unsigned __int64)
0x180015cc5  test    eax, eax
0x180015cc7  jns     short loc_180015CD1
0x180015cc9  mov     r8d, 0B78h
0x180015ccf  jmp     short loc_180015CB2
0x180015cd1  mov     r14b, 1
0x180015cd4  lea     rcx, [rbp+var_28]; this
0x180015cd8  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x180015cdd  mov     rax, [rbp+var_38]
0x180015ce1  test    rax, rax
0x180015ce4  jnz     short loc_180015D15
0x180015ce6  lea     r9, [rbp+var_48]
0x180015cea  xor     r8d, r8d
0x180015ced  lea     rdx, aLastmapcopyrig_0; "LastMapCopyright"
0x180015cf4  call    ?GetMapsPersistedRegString@RegUtils@@SAJW4MapsRegKeys@@PEBG1PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegUtils::GetMapsPersistedRegString(MapsRegKeys,ushort const *,ushort const *,std::wstring *)
0x180015cf9  test    eax, eax
0x180015cfb  jns     short loc_180015D15
0x180015cfd  mov     r9, rdi
0x180015d00  mov     r8d, 0B80h
0x180015d06  lea     rdx, aServicemanager_34; "ServiceManager::FetchCopyrightString"
0x180015d0d  mov     ecx, eax
0x180015d0f  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x180015d15  xor     ecx, ecx; bool
0x180015d17  call    ?GetChinaVariant@MapPlatformConfig@@CA_N_N@Z; MapPlatformConfig::GetChinaVariant(bool)
0x180015d1c  test    al, al
0x180015d1e  jz      short loc_180015D9B
0x180015d20  lea     rcx, [rbp+var_28]
0x180015d24  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180015d29  nop
0x180015d2a  lea     rcx, [rbp+var_28]
0x180015d2e  call    cs:__imp_?MapsStore_GetGSCode@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MapsStore_GetGSCode(std::wstring *)
0x180015d34  test    eax, eax
0x180015d36  jns     short loc_180015D5D
0x180015d38  mov     r9, rdi
0x180015d3b  mov     r8d, 0B87h
0x180015d41  lea     rdx, aServicemanager_34; "ServiceManager::FetchCopyrightString"
0x180015d48  mov     ecx, eax
0x180015d4a  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180015d50  mov     ebx, eax
0x180015d52  lea     rcx, [rbp+var_28]
0x180015d56  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015d5b  jmp     short loc_180015DAB
0x180015d5d  lea     rcx, asc_180029998; " "
0x180015d64  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180015d69  mov     r8, rax
0x180015d6c  mov     rdx, rcx
0x180015d6f  lea     rcx, [rbp+var_48]
0x180015d73  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180015d78  lea     rcx, [rbp+var_28]
0x180015d7c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180015d81  mov     rdx, rax
0x180015d84  mov     r8, [rbp+var_18]
0x180015d88  lea     rcx, [rbp+var_48]
0x180015d8c  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180015d91  nop
0x180015d92  lea     rcx, [rbp+var_28]
0x180015d96  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015d9b  lea     rdx, [rbp+var_48]
0x180015d9f  mov     rcx, r12
0x180015da2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180015da7  mov     [r13+0], r14b
0x180015dab  lea     rcx, [rbp+var_48]
0x180015daf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015db4  mov     eax, ebx
0x180015db6  mov     rcx, [rbp+var_8]
0x180015dba  xor     rcx, rsp; StackCookie
0x180015dbd  call    __security_check_cookie
0x180015dc2  mov     rbx, [rsp+70h+arg_18]
0x180015dca  add     rsp, 70h
0x180015dce  pop     r15
0x180015dd0  pop     r14
0x180015dd2  pop     r13
0x180015dd4  pop     r12
0x180015dd6  pop     rdi
0x180015dd7  pop     rsi
0x180015dd8  pop     rbp
0x180015dd9  retn
```
