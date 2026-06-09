# AIXPolicyHelper::InstallAttempts::GetCurrentInstallAttempts(HKEY__ *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001a038`
- end: `0x18001a14d`
- name: `?GetCurrentInstallAttempts@InstallAttempts@AIXPolicyHelper@@SA?AU12@PEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `277`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001b7fc`
- `0x18002d050`

## callees

- `0x1800122f0`
- `0x180018648`
- `0x180018758`
- `0x18001a038`
- `0x18002062c`
- `0x18002073c`
- `0x1800233ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a139`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a139`

## string_xrefs

- `0x18001a098`: `AttemptedInstallCount`
- `0x18001a0b3`: `shellcommon\internal\shell\inc\AIXPolicyHelper.h`
- `0x18001a0f2`: `shellcommon\internal\shell\inc\AIXPolicyHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned int *__fastcall AIXPolicyHelper::InstallAttempts::GetCurrentInstallAttempts(
        unsigned int *a1,
        __int64 a2,
        const WCHAR *a3)
{
  unsigned int v5; // r14d
  unsigned int CurrentBuildRevision; // esi
  LSTATUS v7; // eax
  wil::details::in1diag3 *v8; // rcx
  __int64 v9; // rdx
  int value_dword; // eax
  int v11; // edi
  __int64 v12; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+28h]
  unsigned int v15; // [rsp+50h] [rbp+30h] BYREF
  __int64 v16; // [rsp+58h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+40h] BYREF

  v16 = a2;
  v5 = 0;
  CurrentBuildRevision = AIXPolicyHelper::GetCurrentBuildRevision((AIXPolicyHelper *)a1);
  hKey = 0;
  if ( *((_QWORD *)a3 + 3) > 7u )
    a3 = *(const WCHAR **)a3;
  v7 = wil::reg::open_unique_key_nothrow(HKEY_LOCAL_MACHINE, a3, &hKey, 0);
  v8 = retaddr;
  if ( v7 < 0 )
  {
    v9 = 758;
LABEL_10:
    wil::details::in1diag3::_Log_Hr(
      v8,
      (void *)v9,
      (int)"shellcommon\\internal\\shell\\inc\\AIXPolicyHelper.h",
      (const char *)(unsigned int)v7);
    goto LABEL_12;
  }
  LODWORD(v16) = 0;
  value_dword = wil::reg::get_value_dword_nothrow<unsigned long,0>(hKey, L"AttemptedInstallCount", &v16);
  if ( value_dword >= 0 )
    v5 = v16;
  else
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2F9,
      (int)"shellcommon\\internal\\shell\\inc\\AIXPolicyHelper.h",
      (const char *)(unsigned int)value_dword);
  v15 = 0;
  v7 = wil::reg::get_value_dword_nothrow<unsigned long,0>(hKey, L"LastBuild", &v15);
  v8 = retaddr;
  if ( v7 < 0 )
  {
    v9 = 767;
    goto LABEL_10;
  }
  CurrentBuildRevision = v15;
LABEL_12:
  *a1 = CurrentBuildRevision;
  a1[1] = v5;
  v11 = 5;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56769107>::__private_GetVariant(`wil::Feature<__WilFeatureTraits_Feature_56769107>::GetImpl'::`2'::impl) == 1 )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_56769107>::GetCachedVariantState(v12, &v16);
    v11 = HIDWORD(v16);
  }
  a1[2] = v11;
  if ( hKey )
    RegCloseKey(hKey);
  return a1;
}

```

## disassembly

```asm
0x18001a038  mov     [rsp-28h+arg_8], rdx
0x18001a03d  push    rbp
0x18001a03e  push    rbx
0x18001a03f  push    rsi
0x18001a040  push    rdi
0x18001a041  push    r14; int
0x18001a043  mov     rbp, rsp
0x18001a046  sub     rsp, 20h
0x18001a04a  mov     rdi, r8
0x18001a04d  mov     rbx, rcx
0x18001a050  xor     r14d, r14d
0x18001a053  call    ?GetCurrentBuildRevision@AIXPolicyHelper@@YAKXZ; AIXPolicyHelper::GetCurrentBuildRevision(void)
0x18001a058  mov     esi, eax
0x18001a05a  mov     [rbp+hKey], r14
0x18001a05e  cmp     qword ptr [rdi+18h], 7
0x18001a063  jbe     short loc_18001A068
0x18001a065  mov     rdi, [rdi]
0x18001a068  xor     r9d, r9d
0x18001a06b  lea     r8, [rbp+hKey]; phkResult
0x18001a06f  mov     rdx, rdi; lpSubKey
0x18001a072  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001a079  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18001a07e  mov     rcx, [rbp+28h]
0x18001a082  test    eax, eax
0x18001a084  jns     short loc_18001A08D
0x18001a086  mov     edx, 2F6h
0x18001a08b  jmp     short loc_18001A0F2
0x18001a08d  mov     dword ptr [rbp+arg_8], 0
0x18001a094  lea     r8, [rbp+arg_8]
0x18001a098  lea     rdx, aAttemptedinsta; "AttemptedInstallCount"
0x18001a09f  mov     rcx, [rbp+hKey]
0x18001a0a3  call    ??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBGPEAK@Z; wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,ushort const *,ulong *)
0x18001a0a8  mov     rcx, [rbp+28h]; this
0x18001a0ac  test    eax, eax
0x18001a0ae  jns     short loc_18001A0C6
0x18001a0b0  mov     r9d, eax; char *
0x18001a0b3  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\AIXP"...
0x18001a0ba  mov     edx, 2F9h; void *
0x18001a0bf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001a0c4  jmp     short loc_18001A0CA
0x18001a0c6  mov     r14d, dword ptr [rbp+arg_8]
0x18001a0ca  mov     [rbp+arg_0], 0
0x18001a0d1  lea     r8, [rbp+arg_0]
0x18001a0d5  lea     rdx, aLastbuild; "LastBuild"
0x18001a0dc  mov     rcx, [rbp+hKey]
0x18001a0e0  call    ??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBGPEAK@Z; wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,ushort const *,ulong *)
0x18001a0e5  mov     rcx, [rbp+28h]; this
0x18001a0e9  test    eax, eax
0x18001a0eb  jns     short loc_18001A103
0x18001a0ed  mov     edx, 2FFh; void *
0x18001a0f2  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\AIXP"...
0x18001a0f9  mov     r9d, eax; char *
0x18001a0fc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001a101  jmp     short loc_18001A106
0x18001a103  mov     esi, [rbp+arg_0]
0x18001a106  mov     [rbx], esi
0x18001a108  mov     [rbx+4], r14d
0x18001a10c  mov     edi, 5
0x18001a111  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56769107@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56769107@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56769107> `wil::Feature<__WilFeatureTraits_Feature_56769107>::GetImpl(void)'::`2'::impl
0x18001a118  call    ?__private_GetVariant@?$FeatureImpl@U__WilFeatureTraits_Feature_56769107@@@details@wil@@QEAA?AW4Variant_56769107@@W4VariantReportingKind@3@_N@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56769107>::__private_GetVariant(wil::VariantReportingKind,bool)
0x18001a11d  cmp     al, 1
0x18001a11f  jnz     short loc_18001A12D
0x18001a121  lea     rdx, [rbp+arg_8]
0x18001a125  call    ?GetCachedVariantState@?$FeatureImpl@U__WilFeatureTraits_Feature_56769107@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56769107>::GetCachedVariantState(void)
0x18001a12a  mov     edi, dword ptr [rbp+arg_8+4]
0x18001a12d  mov     [rbx+8], edi
0x18001a130  mov     rcx, [rbp+hKey]; hKey
0x18001a134  test    rcx, rcx
0x18001a137  jz      short loc_18001A13F
0x18001a139  call    cs:__imp_RegCloseKey
0x18001a13f  mov     rax, rbx
0x18001a142  add     rsp, 20h
0x18001a146  pop     r14
0x18001a148  pop     rdi
0x18001a149  pop     rsi
0x18001a14a  pop     rbx
0x18001a14b  pop     rbp
0x18001a14c  retn
```
