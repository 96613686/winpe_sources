# WwanManagerUtils::_Intialize(void)

- ea: `0x18007dec0`
- end: `0x18007e2b3`
- name: `?_Intialize@WwanManagerUtils@@SAXXZ`
- size: `1011`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007a924`

## callees

- `0x1800085d0`
- `0x180008abc`
- `0x1800095f4`
- `0x180010e94`
- `0x180011650`
- `0x1800117a8`
- `0x180011a1c`
- `0x180012300`
- `0x180013288`
- `0x180013588`
- `0x180014b5c`
- `0x180014c68`
- `0x180014f1c`
- `0x18007d540`
- `0x18007dec0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18007dfe1`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18007e0e8`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18007e1e8`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18007dfe1`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18007e0e8`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18007e1e8`

## string_xrefs

- `0x18007dfbf`: `nw code %d already in the normal pace retry list`
- `0x18007e019`: ` no config at subkey [%s] value name [%s] code 0x%x`
- `0x18007e120`: ` no config at subkey [%s] value name [%s] code 0x%x`
- `0x18007e220`: ` no config at subkey [%s] value name [%s] code 0x%x`
- `0x18007e0c6`: `nw code %d already in the slow pace retry list`
- `0x18007e1c6`: `nw code %d already in the glacier pace retry list`
- `0x18007e262`: ` config %s has data %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void WwanManagerUtils::_Intialize(void)
{
  __int64 v0; // rax
  int String; // eax
  const wchar_t *v2; // rsi
  unsigned int v3; // eax
  wchar_t *v4; // rax
  int v5; // eax
  const wchar_t *v6; // rsi
  unsigned int v7; // eax
  wchar_t *v8; // rax
  int v9; // eax
  const wchar_t *v10; // rsi
  unsigned int v11; // eax
  wchar_t *v12; // rax
  __int64 v13; // [rsp+20h] [rbp-39h]
  __int64 v14; // [rsp+28h] [rbp-31h]
  unsigned int v15; // [rsp+30h] [rbp-29h] BYREF
  unsigned int v16; // [rsp+34h] [rbp-25h] BYREF
  StateSeparation *v17; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v18[8]; // [rsp+40h] [rbp-19h] BYREF
  char v19; // [rsp+48h] [rbp-11h]
  _BYTE v20[32]; // [rsp+50h] [rbp-9h] BYREF

  std::wstring::wstring(v20);
  v15 = 0;
  v17 = (StateSeparation *)operator new(0x20u);
  v0 = StateSeparation::StateSeparation(v17, 2);
  std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(&v17, v0);
  String = StateSeparation::GetString(v17, L"ConnectionRetryPace", L"NormalPaceRetryNwCauseCodes", v20);
  if ( String )
  {
    WwanLog::Info(
      "WwanManagerUtils::_Intialize",
      0,
      L" no config at subkey [%s] value name [%s] code 0x%x",
      L"ConnectionRetryPace",
      L"NormalPaceRetryNwCauseCodes",
      String);
  }
  else
  {
    v2 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v20);
    WwanLog::Info("WwanManagerUtils::_Intialize", 0, L" string [%s] at reg [%s]", v2, L"NormalPaceRetryNwCauseCodes");
    while ( v2 && *v2 )
    {
      v3 = swscanf_s(v2, L"%d", &v15);
      if ( v3 != 1 )
      {
        WwanLog::Info("WwanManagerUtils::_Intialize", 0, L" no more nw cause code for normal pace retry (%d)", v3);
        break;
      }
      std::_Hash<std::_Uset_traits<unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<unsigned long>,0>>::emplace<unsigned long const &>(
        &WwanManagerUtils::m_nwCauseNormalPaceOEM,
        v18,
        &v15);
      if ( v19 )
        WwanLog::Info("WwanManagerUtils::_Intialize", 0, L" nw cause code %d for normal pace retry", v15);
      else
        WwanLog::Error("WwanManagerUtils::_Intialize", 0, L"nw code %d already in the normal pace retry list", v15);
      v4 = wcschr(v2, 0x2Cu);
      v2 = v4 + 1;
      if ( !v4 )
        v2 = 0;
    }
  }
  v5 = StateSeparation::GetString(v17, L"ConnectionRetryPace", L"SlowPaceRetryNwCauseCodes", v20);
  if ( v5 )
  {
    LODWORD(v14) = v5;
    WwanLog::Info(
      "WwanManagerUtils::_Intialize",
      0,
      L" no config at subkey [%s] value name [%s] code 0x%x",
      L"ConnectionRetryPace",
      L"SlowPaceRetryNwCauseCodes",
      v14);
  }
  else
  {
    v6 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v20);
    WwanLog::Info("WwanManagerUtils::_Intialize", 0, L" string [%s] at reg [%s]", v6, L"SlowPaceRetryNwCauseCodes");
    while ( v6 && *v6 )
    {
      v7 = swscanf_s(v6, L"%d", &v15);
      if ( v7 != 1 )
      {
        WwanLog::Info("WwanManagerUtils::_Intialize", 0, L" no more nw cause code for slow pace retry (%d)", v7);
        break;
      }
      std::_Hash<std::_Uset_traits<unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<unsigned long>,0>>::emplace<unsigned long const &>(
        &WwanManagerUtils::m_nwCauseSlowPaceOEM,
        v18,
        &v15);
      if ( v19 )
        WwanLog::Info("WwanManagerUtils::_Intialize", 0, L" nw cause code %d for slow pace retry", v15);
      else
        WwanLog::Error("WwanManagerUtils::_Intialize", 0, L"nw code %d already in the slow pace retry list", v15);
      v8 = wcschr(v6, 0x2Cu);
      v6 = v8 + 1;
      if ( !v8 )
        v6 = 0;
    }
  }
  v9 = StateSeparation::GetString(v17, L"ConnectionRetryPace", L"GlacierPaceRetryNwCauseCodes", v20);
  if ( v9 )
  {
    LODWORD(v14) = v9;
    WwanLog::Info(
      "WwanManagerUtils::_Intialize",
      0,
      L" no config at subkey [%s] value name [%s] code 0x%x",
      L"ConnectionRetryPace",
      L"GlacierPaceRetryNwCauseCodes",
      v14);
  }
  else
  {
    v10 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v20);
    WwanLog::Info("WwanManagerUtils::_Intialize", 0, L" string [%s] at reg [%s]", v10, L"GlacierPaceRetryNwCauseCodes");
    while ( v10 && *v10 )
    {
      v11 = swscanf_s(v10, L"%d", &v15);
      if ( v11 != 1 )
      {
        WwanLog::Info("WwanManagerUtils::_Intialize", 0, L" no more nw cause code for glacier pace retry (%d)", v11);
        break;
      }
      std::_Hash<std::_Uset_traits<unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<unsigned long>,0>>::emplace<unsigned long const &>(
        &WwanManagerUtils::m_nwCauseGlacierPaceOEM,
        v18,
        &v15);
      if ( v19 )
        WwanLog::Info("WwanManagerUtils::_Intialize", 0, L" nw cause code %d for glacier pace retry", v15);
      else
        WwanLog::Error("WwanManagerUtils::_Intialize", 0, L"nw code %d already in the glacier pace retry list", v15);
      v12 = wcschr(v10, 0x2Cu);
      v10 = v12 + 1;
      if ( !v12 )
        v10 = 0;
    }
  }
  v16 = 0;
  if ( !StateSeparation::GetDWORD(v17, L"IPTypeSelection", L"OldMBIMModem", &v16) )
  {
    LODWORD(v13) = v16;
    WwanLog::Info("WwanManagerUtils::_Intialize", 0, L" config %s has data %d", L"OldMBIMModem", v13);
    WwanManagerUtils::m_ConfigUseOriginalConnIPType = v16 == 1;
  }
  std::unique_ptr<StateSeparation>::~unique_ptr<StateSeparation>(&v17);
  std::wstring::_Tidy_deallocate(v20);
}

```

## disassembly

```asm
0x18007dec0  push    rbp
0x18007dec2  push    rsi
0x18007dec3  push    rdi
0x18007dec4  push    r12
0x18007dec6  push    r14
0x18007dec8  push    r15
0x18007deca  lea     rbp, [rsp-2Fh]
0x18007decf  sub     rsp, 88h
0x18007ded6  mov     rax, cs:__security_cookie
0x18007dedd  xor     rax, rsp
0x18007dee0  mov     [rbp+57h+var_40], rax
0x18007dee4  lea     rcx, [rbp+57h+var_60]
0x18007dee8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18007deed  nop
0x18007deee  xor     r14d, r14d
0x18007def1  mov     [rbp+57h+var_80], r14d
0x18007def5  lea     ecx, [r14+20h]; Size
0x18007def9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007defe  mov     [rbp+57h+var_78], rax
0x18007df02  lea     edx, [r14+2]
0x18007df06  mov     rcx, rax
0x18007df09  call    ??0StateSeparation@@QEAA@W4_REG_ROOT_PATH@@@Z; StateSeparation::StateSeparation(_REG_ROOT_PATH)
0x18007df0e  nop
0x18007df0f  mov     rdx, rax
0x18007df12  lea     rcx, [rbp+57h+var_78]
0x18007df16  call    ??$?0U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@$0A@@?$unique_ptr@U_WWAN_SET_LTE_ATTACH@@U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@@std@@QEAA@PEAU_WWAN_SET_LTE_ATTACH@@@Z; std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(_WWAN_SET_LTE_ATTACH *)
0x18007df1b  nop
0x18007df1c  lea     r9, [rbp+57h+var_60]
0x18007df20  lea     rdi, aNormalpaceretr; "NormalPaceRetryNwCauseCodes"
0x18007df27  mov     r8, rdi
0x18007df2a  lea     r12, aConnectionretr; "ConnectionRetryPace"
0x18007df31  mov     rdx, r12
0x18007df34  mov     rcx, [rbp+57h+var_78]
0x18007df38  call    ?GetString@StateSeparation@@QEAAKPEBG0PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StateSeparation::GetString(ushort const *,ushort const *,std::wstring *)
0x18007df3d  test    eax, eax
0x18007df3f  jnz     loc_18007E00D
0x18007df45  lea     rcx, [rbp+57h+var_60]
0x18007df49  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007df4e  mov     rsi, rax
0x18007df51  mov     [rsp+0B0h+var_90], rdi
0x18007df56  mov     r9, rax
0x18007df59  lea     r8, aStringSAtRegS; " string [%s] at reg [%s]"
0x18007df60  xor     edx, edx; struct _GUID *
0x18007df62  lea     rdi, aWwanmanageruti_1; "WwanManagerUtils::_Intialize"
0x18007df69  mov     rcx, rdi; char *
0x18007df6c  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18007df71  test    rsi, rsi
0x18007df74  jz      loc_18007E031
0x18007df7a  cmp     [rsi], r14w
0x18007df7e  jz      loc_18007E031
0x18007df84  lea     r8, [rbp+57h+var_80]
0x18007df88  lea     rdx, aD; "%d"
0x18007df8f  mov     rcx, rsi; Buffer
0x18007df92  call    swscanf_s
0x18007df97  cmp     eax, 1
0x18007df9a  jnz     short loc_18007DFF7
0x18007df9c  lea     r8, [rbp+57h+var_80]
0x18007dfa0  lea     rdx, [rbp+57h+var_70]
0x18007dfa4  lea     rcx, ?m_nwCauseNormalPaceOEM@WwanManagerUtils@@0V?$unordered_set@KU?$hash@K@std@@U?$equal_to@K@2@V?$allocator@K@2@@std@@A; std::unordered_set<ulong> WwanManagerUtils::m_nwCauseNormalPaceOEM
0x18007dfab  call    ??$emplace@AEBK@?$_Hash@V?$_Uset_traits@KV?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@K@std@@@std@@@std@@_N@1@AEBK@Z; std::_Hash<std::_Uset_traits<ulong,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<ulong>,0>>::emplace<ulong const &>(ulong const &)
0x18007dfb0  mov     r9d, [rbp+57h+var_80]
0x18007dfb4  xor     edx, edx; struct _GUID *
0x18007dfb6  mov     rcx, rdi; char *
0x18007dfb9  cmp     [rbp+57h+var_68], r14b
0x18007dfbd  jnz     short loc_18007DFCD
0x18007dfbf  lea     r8, aNwCodeDAlready_0; "nw code %d already in the normal pace r"...
0x18007dfc6  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18007dfcb  jmp     short loc_18007DFD9
0x18007dfcd  lea     r8, aNwCauseCodeDFo_0; " nw cause code %d for normal pace retry"
0x18007dfd4  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18007dfd9  mov     edx, 2Ch ; ','; Ch
0x18007dfde  mov     rcx, rsi; Str
0x18007dfe1  call    cs:__imp_wcschr
0x18007dfe7  lea     rsi, [rax+2]
0x18007dfeb  test    rax, rax
0x18007dfee  cmovz   rsi, rax
0x18007dff2  jmp     loc_18007DF71
0x18007dff7  mov     r9d, eax
0x18007dffa  lea     r8, aNoMoreNwCauseC_1; " no more nw cause code for normal pace "...
0x18007e001  xor     edx, edx; struct _GUID *
0x18007e003  mov     rcx, rdi; char *
0x18007e006  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18007e00b  jmp     short loc_18007E031
0x18007e00d  mov     dword ptr [rsp+0B0h+var_88], eax
0x18007e011  mov     [rsp+0B0h+var_90], rdi
0x18007e016  mov     r9, r12
0x18007e019  lea     r8, aNoConfigAtSubk; " no config at subkey [%s] value name [%"...
0x18007e020  xor     edx, edx; struct _GUID *
0x18007e022  lea     rdi, aWwanmanageruti_1; "WwanManagerUtils::_Intialize"
0x18007e029  mov     rcx, rdi; char *
0x18007e02c  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18007e031  lea     r9, [rbp+57h+var_60]
0x18007e035  lea     r15, aSlowpaceretryn; "SlowPaceRetryNwCauseCodes"
0x18007e03c  mov     r8, r15
0x18007e03f  mov     rdx, r12
0x18007e042  mov     rcx, [rbp+57h+var_78]
0x18007e046  call    ?GetString@StateSeparation@@QEAAKPEBG0PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StateSeparation::GetString(ushort const *,ushort const *,std::wstring *)
0x18007e04b  test    eax, eax
0x18007e04d  jnz     loc_18007E114
0x18007e053  lea     rcx, [rbp+57h+var_60]
0x18007e057  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007e05c  mov     rsi, rax
0x18007e05f  mov     [rsp+0B0h+var_90], r15
0x18007e064  mov     r9, rax
0x18007e067  lea     r8, aStringSAtRegS; " string [%s] at reg [%s]"
0x18007e06e  xor     edx, edx; struct _GUID *
0x18007e070  mov     rcx, rdi; char *
0x18007e073  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18007e078  test    rsi, rsi
0x18007e07b  jz      loc_18007E131
0x18007e081  cmp     [rsi], r14w
0x18007e085  jz      loc_18007E131
0x18007e08b  lea     r8, [rbp+57h+var_80]
0x18007e08f  lea     rdx, aD; "%d"
0x18007e096  mov     rcx, rsi; Buffer
0x18007e099  call    swscanf_s
0x18007e09e  cmp     eax, 1
0x18007e0a1  jnz     short loc_18007E0FE
0x18007e0a3  lea     r8, [rbp+57h+var_80]
0x18007e0a7  lea     rdx, [rbp+57h+var_70]
0x18007e0ab  lea     rcx, ?m_nwCauseSlowPaceOEM@WwanManagerUtils@@0V?$unordered_set@KU?$hash@K@std@@U?$equal_to@K@2@V?$allocator@K@2@@std@@A; std::unordered_set<ulong> WwanManagerUtils::m_nwCauseSlowPaceOEM
0x18007e0b2  call    ??$emplace@AEBK@?$_Hash@V?$_Uset_traits@KV?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@K@std@@@std@@@std@@_N@1@AEBK@Z; std::_Hash<std::_Uset_traits<ulong,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<ulong>,0>>::emplace<ulong const &>(ulong const &)
0x18007e0b7  mov     r9d, [rbp+57h+var_80]
0x18007e0bb  xor     edx, edx; struct _GUID *
0x18007e0bd  mov     rcx, rdi; char *
0x18007e0c0  cmp     [rbp+57h+var_68], r14b
0x18007e0c4  jnz     short loc_18007E0D4
0x18007e0c6  lea     r8, aNwCodeDAlready_1; "nw code %d already in the slow pace ret"...
0x18007e0cd  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18007e0d2  jmp     short loc_18007E0E0
0x18007e0d4  lea     r8, aNwCauseCodeDFo_1; " nw cause code %d for slow pace retry"
0x18007e0db  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18007e0e0  mov     edx, 2Ch ; ','; Ch
0x18007e0e5  mov     rcx, rsi; Str
0x18007e0e8  call    cs:__imp_wcschr
0x18007e0ee  lea     rsi, [rax+2]
0x18007e0f2  test    rax, rax
0x18007e0f5  cmovz   rsi, rax
0x18007e0f9  jmp     loc_18007E078
0x18007e0fe  mov     r9d, eax
0x18007e101  lea     r8, aNoMoreNwCauseC_0; " no more nw cause code for slow pace re"...
0x18007e108  xor     edx, edx; struct _GUID *
0x18007e10a  mov     rcx, rdi; char *
0x18007e10d  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18007e112  jmp     short loc_18007E131
0x18007e114  mov     dword ptr [rsp+0B0h+var_88], eax
0x18007e118  mov     [rsp+0B0h+var_90], r15
0x18007e11d  mov     r9, r12
0x18007e120  lea     r8, aNoConfigAtSubk; " no config at subkey [%s] value name [%"...
0x18007e127  xor     edx, edx; struct _GUID *
0x18007e129  mov     rcx, rdi; char *
0x18007e12c  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18007e131  lea     r9, [rbp+57h+var_60]
0x18007e135  lea     r15, aGlacierpaceret; "GlacierPaceRetryNwCauseCodes"
0x18007e13c  mov     r8, r15
0x18007e13f  mov     rdx, r12
0x18007e142  mov     rcx, [rbp+57h+var_78]
0x18007e146  call    ?GetString@StateSeparation@@QEAAKPEBG0PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StateSeparation::GetString(ushort const *,ushort const *,std::wstring *)
0x18007e14b  test    eax, eax
0x18007e14d  jnz     loc_18007E214
0x18007e153  lea     rcx, [rbp+57h+var_60]
0x18007e157  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007e15c  mov     rsi, rax
0x18007e15f  mov     [rsp+0B0h+var_90], r15
0x18007e164  mov     r9, rax
0x18007e167  lea     r8, aStringSAtRegS; " string [%s] at reg [%s]"
0x18007e16e  xor     edx, edx; struct _GUID *
0x18007e170  mov     rcx, rdi; char *
0x18007e173  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18007e178  test    rsi, rsi
0x18007e17b  jz      loc_18007E231
0x18007e181  cmp     [rsi], r14w
0x18007e185  jz      loc_18007E231
0x18007e18b  lea     r8, [rbp+57h+var_80]
0x18007e18f  lea     rdx, aD; "%d"
0x18007e196  mov     rcx, rsi; Buffer
0x18007e199  call    swscanf_s
0x18007e19e  cmp     eax, 1
0x18007e1a1  jnz     short loc_18007E1FE
0x18007e1a3  lea     r8, [rbp+57h+var_80]
0x18007e1a7  lea     rdx, [rbp+57h+var_70]
0x18007e1ab  lea     rcx, ?m_nwCauseGlacierPaceOEM@WwanManagerUtils@@0V?$unordered_set@KU?$hash@K@std@@U?$equal_to@K@2@V?$allocator@K@2@@std@@A; std::unordered_set<ulong> WwanManagerUtils::m_nwCauseGlacierPaceOEM
0x18007e1b2  call    ??$emplace@AEBK@?$_Hash@V?$_Uset_traits@KV?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@K@std@@@std@@@std@@_N@1@AEBK@Z; std::_Hash<std::_Uset_traits<ulong,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<ulong>,0>>::emplace<ulong const &>(ulong const &)
0x18007e1b7  mov     r9d, [rbp+57h+var_80]
0x18007e1bb  xor     edx, edx; struct _GUID *
0x18007e1bd  mov     rcx, rdi; char *
0x18007e1c0  cmp     [rbp+57h+var_68], r14b
0x18007e1c4  jnz     short loc_18007E1D4
0x18007e1c6  lea     r8, aNwCodeDAlready; "nw code %d already in the glacier pace "...
0x18007e1cd  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18007e1d2  jmp     short loc_18007E1E0
0x18007e1d4  lea     r8, aNwCauseCodeDFo; " nw cause code %d for glacier pace retr"...
0x18007e1db  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18007e1e0  mov     edx, 2Ch ; ','; Ch
0x18007e1e5  mov     rcx, rsi; Str
0x18007e1e8  call    cs:__imp_wcschr
0x18007e1ee  lea     rsi, [rax+2]
0x18007e1f2  test    rax, rax
0x18007e1f5  cmovz   rsi, rax
0x18007e1f9  jmp     loc_18007E178
0x18007e1fe  mov     r9d, eax
0x18007e201  lea     r8, aNoMoreNwCauseC; " no more nw cause code for glacier pace"...
0x18007e208  xor     edx, edx; struct _GUID *
0x18007e20a  mov     rcx, rdi; char *
0x18007e20d  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18007e212  jmp     short loc_18007E231
0x18007e214  mov     dword ptr [rsp+0B0h+var_88], eax
0x18007e218  mov     [rsp+0B0h+var_90], r15
0x18007e21d  mov     r9, r12
0x18007e220  lea     r8, aNoConfigAtSubk; " no config at subkey [%s] value name [%"...
0x18007e227  xor     edx, edx; struct _GUID *
0x18007e229  mov     rcx, rdi; char *
0x18007e22c  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18007e231  mov     [rbp+57h+var_7C], r14d
0x18007e235  lea     r9, [rbp+57h+var_7C]; unsigned int *
0x18007e239  lea     r8, aOldmbimmodem; "OldMBIMModem"
0x18007e240  lea     rdx, aIptypeselectio; "IPTypeSelection"
0x18007e247  mov     rcx, [rbp+57h+var_78]; this
0x18007e24b  call    ?GetDWORD@StateSeparation@@QEAAKPEBG0PEAK@Z; StateSeparation::GetDWORD(ushort const *,ushort const *,ulong *)
0x18007e250  test    eax, eax
0x18007e252  jnz     short loc_18007E283
0x18007e254  mov     eax, [rbp+57h+var_7C]
0x18007e257  mov     dword ptr [rsp+0B0h+var_90], eax
0x18007e25b  lea     r9, aOldmbimmodem; "OldMBIMModem"
0x18007e262  lea     r8, aConfigSHasData; " config %s has data %d"
0x18007e269  xor     edx, edx; struct _GUID *
0x18007e26b  mov     rcx, rdi; char *
0x18007e26e  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18007e273  mov     eax, r14d
0x18007e276  cmp     [rbp+57h+var_7C], 1
0x18007e27a  setz    al
0x18007e27d  mov     cs:?m_ConfigUseOriginalConnIPType@WwanManagerUtils@@0HA, eax; int WwanManagerUtils::m_ConfigUseOriginalConnIPType
0x18007e283  lea     rcx, [rbp+57h+var_78]
0x18007e287  call    ??1?$unique_ptr@VStateSeparation@@U?$default_delete@VStateSeparation@@@std@@@std@@QEAA@XZ; std::unique_ptr<StateSeparation>::~unique_ptr<StateSeparation>(void)
0x18007e28c  nop
0x18007e28d  lea     rcx, [rbp+57h+var_60]
0x18007e291  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007e296  mov     rcx, [rbp+57h+var_40]
0x18007e29a  xor     rcx, rsp; StackCookie
0x18007e29d  call    __security_check_cookie
0x18007e2a2  add     rsp, 88h
0x18007e2a9  pop     r15
0x18007e2ab  pop     r14
0x18007e2ad  pop     r12
0x18007e2af  pop     rdi
0x18007e2b0  pop     rsi
0x18007e2b1  pop     rbp
0x18007e2b2  retn
```
