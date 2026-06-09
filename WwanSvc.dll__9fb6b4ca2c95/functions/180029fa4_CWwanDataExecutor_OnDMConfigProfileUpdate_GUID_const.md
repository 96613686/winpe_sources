# CWwanDataExecutor::OnDMConfigProfileUpdate(_GUID const &)

- ea: `0x180029fa4`
- end: `0x18002a170`
- name: `?OnDMConfigProfileUpdate@CWwanDataExecutor@@QEAAXAEBU_GUID@@@Z`
- size: `460`
- prototype: `void __fastcall(CWwanDataExecutor *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update`

## callers

- `0x18002cb70`

## callees

- `0x1800085d0`
- `0x1800094f4`
- `0x1800111ac`
- `0x180012300`
- `0x180014f1c`
- `0x1800196bc`
- `0x180029fa4`
- `0x180033880`
- `0x18003bc04`
- `0x1800a1778`
- `0x1800a1e24`
- `0x1800c8520`

## import_xrefs

- `WwanPrfl!WwanProfileInit` at `0x18002a00e`
- `WwanPrfl!WwanProfileInit` at `0x18002a00e`
- `WwanPrfl!WwanProfileDeinit` at `0x18002a142`
- `WwanPrfl!WwanProfileDeinit` at `0x18002a142`

## string_xrefs

- `0x18002a027`: `Data Executor is not ready with ICCID`
- `0x18002a030`: `CWwanDataExecutor::OnDMConfigProfileUpdate`
- `0x18002a080`: `CWwanDataExecutor::OnDMConfigProfileUpdate`
- `0x18002a0c2`: `CWwanDataExecutor::OnDMConfigProfileUpdate`
- `0x18002a0e2`: `CWwanDataExecutor::OnDMConfigProfileUpdate`
- `0x18002a131`: `CWwanDataExecutor::OnDMConfigProfileUpdate`
- `0x18002a079`: `found no DM config profiles for ICCID [%s]`
- `0x18002a0db`: `found DM config profile list for ICCID [%s], will not try wildcard iccid`
- `0x18002a128`: `WwanPmGetDMConfigProfileInEffect() failed: %u`

## pseudocode

```c
void __fastcall CWwanDataExecutor::OnDMConfigProfileUpdate(CWwanDataExecutor *this, const struct _GUID *a2)
{
  unsigned int v4; // r8d
  __int64 v5; // rdx
  __int64 DMConfigProfileInEffect; // rbx
  _QWORD v7[4]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v8[6320]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v9[8]; // [rsp+18F0h] [rbp+17F0h] BYREF
  _BYTE v10[26]; // [rsp+1900h] [rbp+1800h] BYREF

  memset(v10, 0, sizeof(v10));
  *(_OWORD *)v9 = 0;
  memset_0(v8, 0, sizeof(v8));
  WwanProfileInit(v8);
  if ( CWwanDataExecutorState::GetExecutorICCID(this, v9, v4) )
  {
    WwanLog::Info("CWwanDataExecutor::OnDMConfigProfileUpdate", 0, L"Data Executor is not ready with ICCID");
  }
  else
  {
    LODWORD(DMConfigProfileInEffect) = WwanPmGetDMConfigProfileInEffect(v9, a2, v8);
    if ( (_DWORD)DMConfigProfileInEffect == 1168 )
    {
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,WWAN_PROFILE>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,WWAN_PROFILE>>>>>>(
        v7,
        v5);
      WwanLog::Info("CWwanDataExecutor::OnDMConfigProfileUpdate", 0, L"found no DM config profiles for ICCID [%s]", v9);
      if ( (unsigned int)WwanPmGetDMConfigProfileListInEffect(v9, v7) == 1168 )
      {
        DMConfigProfileInEffect = (unsigned int)WwanPmGetDMConfigProfileInEffect(L"IccidAny", a2, v8);
        WwanLog::Info(
          "CWwanDataExecutor::OnDMConfigProfileUpdate",
          0,
          L"get wildcard iccid profile, returned %u",
          DMConfigProfileInEffect);
      }
      else
      {
        WwanLog::Info(
          "CWwanDataExecutor::OnDMConfigProfileUpdate",
          0,
          L"found DM config profile list for ICCID [%s], will not try wildcard iccid",
          v9);
        LODWORD(DMConfigProfileInEffect) = 1168;
      }
      if ( v7[0] )
        std::_Deallocate<16>(v7[0], (v7[2] - v7[0]) & 0xFFFFFFFFFFFFFFF8uLL);
    }
    if ( (_DWORD)DMConfigProfileInEffect )
    {
      if ( (_DWORD)DMConfigProfileInEffect != 1168 )
        WwanLog::Error(
          "CWwanDataExecutor::OnDMConfigProfileUpdate",
          0,
          L"WwanPmGetDMConfigProfileInEffect() failed: %u",
          (unsigned int)DMConfigProfileInEffect);
    }
    else
    {
      CWwanModemProfileController::DmConfigConnUpdateIfNeeded(
        (CWwanDataExecutor *)((char *)this + 56),
        (const struct WWAN_PROFILE *)v8);
    }
  }
  WwanProfileDeinit(v8);
}

```

## disassembly

```asm
0x180029fa4  mov     [rsp-8+arg_10], rbx
0x180029fa9  mov     [rsp-8+arg_18], rsi
0x180029fae  push    rbp
0x180029faf  push    r14
0x180029fb1  push    r15
0x180029fb3  lea     rbp, [rsp-1830h]
0x180029fbb  mov     eax, 1930h
0x180029fc0  call    _alloca_probe
0x180029fc5  sub     rsp, rax
0x180029fc8  mov     rax, cs:__security_cookie
0x180029fcf  xor     rax, rsp
0x180029fd2  mov     [rbp+1840h+var_20], rax
0x180029fd9  xorps   xmm0, xmm0
0x180029fdc  mov     rsi, rdx
0x180029fdf  mov     r14, rcx
0x180029fe2  xor     edx, edx; Val
0x180029fe4  movups  xmmword ptr [rbp+1840h+var_40], xmm0
0x180029feb  mov     r8d, 18B0h; Size
0x180029ff1  lea     rcx, [rsp+1940h+var_1900]; void *
0x180029ff6  movups  xmmword ptr [rbp+1840h+var_40+0Ah], xmm0
0x180029ffd  movups  xmmword ptr [rbp+1840h+var_50], xmm0
0x18002a004  call    memset_0
0x18002a009  lea     rcx, [rsp+1940h+var_1900]
0x18002a00e  call    cs:__imp_WwanProfileInit
0x18002a014  lea     rdx, [rbp+1840h+var_50]; unsigned __int16 *
0x18002a01b  mov     rcx, r14; this
0x18002a01e  call    ?GetExecutorICCID@CWwanDataExecutorState@@QEAAKPEAGK@Z; CWwanDataExecutorState::GetExecutorICCID(ushort *,ulong)
0x18002a023  test    eax, eax
0x18002a025  jz      short loc_18002A041
0x18002a027  lea     r8, aDataExecutorIs_0; "Data Executor is not ready with ICCID"
0x18002a02e  xor     edx, edx; struct _GUID *
0x18002a030  lea     rcx, aCwwandataexecu_56; "CWwanDataExecutor::OnDMConfigProfileUpd"...
0x18002a037  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18002a03c  jmp     loc_18002A13D
0x18002a041  lea     r8, [rsp+1940h+var_1900]
0x18002a046  mov     rdx, rsi
0x18002a049  lea     rcx, [rbp+1840h+var_50]
0x18002a050  call    WwanPmGetDMConfigProfileInEffect
0x18002a055  mov     r15d, 490h
0x18002a05b  mov     ebx, eax
0x18002a05d  cmp     eax, r15d
0x18002a060  jnz     loc_18002A10C
0x18002a066  lea     rcx, [rsp+1940h+var_1920]
0x18002a06b  call    ??$?0AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UWWAN_PROFILE@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UWWAN_PROFILE@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UWWAN_PROFILE@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,WWAN_PROFILE>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,WWAN_PROFILE>>>>>>(std::allocator<std::pair<std::wstring const,WWAN_PROFILE>> const &)
0x18002a070  lea     r9, [rbp+1840h+var_50]
0x18002a077  xor     edx, edx; struct _GUID *
0x18002a079  lea     r8, aFoundNoDmConfi_0; "found no DM config profiles for ICCID ["...
0x18002a080  lea     rcx, aCwwandataexecu_56; "CWwanDataExecutor::OnDMConfigProfileUpd"...
0x18002a087  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18002a08c  lea     rdx, [rsp+1940h+var_1920]
0x18002a091  lea     rcx, [rbp+1840h+var_50]
0x18002a098  call    WwanPmGetDMConfigProfileListInEffect
0x18002a09d  cmp     eax, r15d
0x18002a0a0  jnz     short loc_18002A0D2
0x18002a0a2  lea     r8, [rsp+1940h+var_1900]
0x18002a0a7  mov     rdx, rsi
0x18002a0aa  lea     rcx, aIccidany; "IccidAny"
0x18002a0b1  call    WwanPmGetDMConfigProfileInEffect
0x18002a0b6  mov     r9d, eax
0x18002a0b9  lea     r8, aGetWildcardIcc; "get wildcard iccid profile, returned %u"
0x18002a0c0  xor     edx, edx; struct _GUID *
0x18002a0c2  lea     rcx, aCwwandataexecu_56; "CWwanDataExecutor::OnDMConfigProfileUpd"...
0x18002a0c9  mov     ebx, eax
0x18002a0cb  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18002a0d0  jmp     short loc_18002A0F1
0x18002a0d2  lea     r9, [rbp+1840h+var_50]
0x18002a0d9  xor     edx, edx; struct _GUID *
0x18002a0db  lea     r8, aFoundDmConfigP; "found DM config profile list for ICCID "...
0x18002a0e2  lea     rcx, aCwwandataexecu_56; "CWwanDataExecutor::OnDMConfigProfileUpd"...
0x18002a0e9  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18002a0ee  mov     ebx, r15d
0x18002a0f1  mov     rcx, [rsp+1940h+var_1920]
0x18002a0f6  test    rcx, rcx
0x18002a0f9  jz      short loc_18002A10C
0x18002a0fb  mov     rdx, [rsp+1940h+var_1910]
0x18002a100  sub     rdx, rcx
0x18002a103  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18002a107  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002a10c  test    ebx, ebx
0x18002a10e  jnz     short loc_18002A120
0x18002a110  lea     rcx, [r14+38h]; this
0x18002a114  lea     rdx, [rsp+1940h+var_1900]; struct WWAN_PROFILE *
0x18002a119  call    ?DmConfigConnUpdateIfNeeded@CWwanModemProfileController@@IEAAKAEBUWWAN_PROFILE@@@Z; CWwanModemProfileController::DmConfigConnUpdateIfNeeded(WWAN_PROFILE const &)
0x18002a11e  jmp     short loc_18002A13D
0x18002a120  cmp     ebx, r15d
0x18002a123  jz      short loc_18002A13D
0x18002a125  mov     r9d, ebx
0x18002a128  lea     r8, aWwanpmgetdmcon_2; "WwanPmGetDMConfigProfileInEffect() fail"...
0x18002a12f  xor     edx, edx; struct _GUID *
0x18002a131  lea     rcx, aCwwandataexecu_56; "CWwanDataExecutor::OnDMConfigProfileUpd"...
0x18002a138  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18002a13d  lea     rcx, [rsp+1940h+var_1900]
0x18002a142  call    cs:__imp_WwanProfileDeinit
0x18002a148  mov     rcx, [rbp+1840h+var_20]
0x18002a14f  xor     rcx, rsp; StackCookie
0x18002a152  call    __security_check_cookie
0x18002a157  lea     r11, [rsp+1940h+var_10]
0x18002a15f  mov     rbx, [r11+30h]
0x18002a163  mov     rsi, [r11+38h]
0x18002a167  mov     rsp, r11
0x18002a16a  pop     r15
0x18002a16c  pop     r14
0x18002a16e  pop     rbp
0x18002a16f  retn
```
