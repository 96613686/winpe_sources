# GetPackageProperties(ushort const *,bool *,bool *,bool *,bool *,bool *,bool *,bool *,bool *)

- ea: `0x180036898`
- end: `0x180036d90`
- name: `?GetPackageProperties@@YAJPEBGPEA_N1111111@Z`
- size: `1272`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool *, bool *, bool *, bool *, bool *, bool *, bool *, bool *)`
- caller_count: `5`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002b27c`
- `0x18002bc04`
- `0x18002c480`
- `0x18002ed98`
- `0x180035dbc`

## callees

- `0x1800058b0`
- `0x18000720c`
- `0x18000b2c0`
- `0x18000d3d0`
- `0x180018190`
- `0x180018dbc`
- `0x18002092c`
- `0x18002b1a8`
- `0x180031ccc`
- `0x180036898`
- `0x180038ce4`
- `0x18003bdcc`
- `0x18003bff0`
- `0x18003c0a8`
- `0x18003c618`
- `0x180046e1a`
- `0x180046e50`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180036cc4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180036cc4`
- `ntdll!RtlInitUnicodeString` at `0x180036b8c`
- `ntdll!RtlInitUnicodeString` at `0x180036b8c`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180036bc0`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180036bc0`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180036c07`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180036c07`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003697f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180036d65`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003697f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180036d65`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180036921`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180036921`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x180036b1d`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x180036b1d`

## string_xrefs

- `0x18003693d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`
- `0x180036958`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180036a15`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180036a45`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180036b44`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180036bd1`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180036b7d`: `packageWriteRedirectionCompatibilityShim`

## pseudocode

```c
__int64 __fastcall GetPackageProperties(
        const unsigned __int16 *a1,
        bool *a2,
        bool *a3,
        bool *a4,
        bool *a5,
        bool *a6,
        bool *a7,
        bool *a8,
        bool *a9)
{
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // rcx
  char IsEnabled; // al
  int v14; // eax
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  unsigned int v17; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v18; // [rsp+58h] [rbp-A8h] BYREF
  const unsigned __int16 *v19; // [rsp+80h] [rbp-80h]
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  char v21; // [rsp+98h] [rbp-68h]
  __int128 v22; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v23; // [rsp+B0h] [rbp-50h]
  __int64 v24; // [rsp+B8h] [rbp-48h]
  __int64 v25; // [rsp+C0h] [rbp-40h]
  __int64 v26; // [rsp+C8h] [rbp-38h]
  __int64 v27; // [rsp+D0h] [rbp-30h]
  __int64 v28; // [rsp+D8h] [rbp-28h]
  __int128 v29; // [rsp+E0h] [rbp-20h]
  int v30; // [rsp+F0h] [rbp-10h]
  __int64 v31; // [rsp+F8h] [rbp-8h]
  __int64 v32; // [rsp+100h] [rbp+0h]
  bool *v33; // [rsp+110h] [rbp+10h]
  bool *v34; // [rsp+118h] [rbp+18h]
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  v33 = a7;
  v34 = a9;
  v19 = a1;
  *(_QWORD *)&DestinationString.Length = &v18;
  v18 = 0;
  DestinationString.Buffer = 0;
  v21 = 1;
  v9 = SRCacheManager_Open(0, &DestinationString.Buffer);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&DestinationString);
  if ( (v9 & 0x80000000) == 0 )
  {
    LOBYTE(v10) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID52930508>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_ID52930508>::GetImpl'::`2'::impl,
      v10);
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::GetImpl'::`2'::impl);
    v22 = 0;
    v29 = 0;
    v23 = 0;
    v24 = 0;
    v25 = 0;
    v26 = 0;
    v27 = 0;
    v28 = 0;
    v30 = 0;
    v31 = 0;
    v32 = 0;
    LOBYTE(v17) = 0;
    v14 = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
            &v18,
            v19,
            (-(__int64)(IsEnabled != 0) & 0xFFFFFFFFFFFFFFE0uLL) + 570,
            &v22);
    v9 = v14;
    if ( v14 >= 0 )
      v9 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x1509,
             (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
             (const char *)2,
             (unsigned int)&v17);
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1506,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)v14,
        (int)&v17);
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v22);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      (const char *)v9,
      bIgnoreCase);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14F6,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)v9,
      bIgnoreCasea);
  }
  v11 = v18;
  v18 = 0;
  if ( v11 )
    SRCacheManager_Close();
  return v9;
}

```

## disassembly

```asm
0x180036898  push    rbp
0x18003689a  push    rbx
0x18003689b  push    rsi
0x18003689c  push    rdi
0x18003689d  push    r12
0x18003689f  push    r13
0x1800368a1  push    r14
0x1800368a3  push    r15
0x1800368a5  lea     rbp, [rsp-0F8h]
0x1800368ad  sub     rsp, 1F8h
0x1800368b4  mov     rax, cs:__security_cookie
0x1800368bb  xor     rax, rsp
0x1800368be  mov     [rbp+130h+var_50], rax
0x1800368c5  mov     rax, [rbp+130h+arg_30]
0x1800368cc  mov     rsi, rdx
0x1800368cf  mov     r14, [rbp+130h+arg_20]
0x1800368d6  lea     rdx, [rbp+130h+DestinationString.Buffer]
0x1800368da  mov     r13, [rbp+130h+arg_28]
0x1800368e1  mov     r12, r9
0x1800368e4  mov     rdi, [rbp+130h+arg_38]
0x1800368eb  mov     r15, r8
0x1800368ee  mov     [rbp+130h+var_120], rax
0x1800368f2  mov     rax, [rbp+130h+arg_40]
0x1800368f9  mov     [rbp+130h+var_118], rax
0x1800368fd  lea     rax, [rsp+230h+var_1D8]
0x180036902  mov     [rbp+130h+var_1B0], rcx
0x180036906  xor     ecx, ecx
0x180036908  mov     qword ptr [rbp+130h+DestinationString.Length], rax
0x18003690c  mov     [rsp+230h+var_1D8], 0
0x180036915  mov     [rbp+130h+DestinationString.Buffer], 0
0x18003691d  mov     [rbp+130h+var_198], 1
0x180036921  call    cs:__imp_SRCacheManager_Open
0x180036927  lea     rcx, [rbp+130h+DestinationString]
0x18003692b  mov     ebx, eax
0x18003692d  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x180036932  test    ebx, ebx
0x180036934  jns     short loc_18003698C
0x180036936  mov     rcx, [rbp+138h]; this
0x18003693d  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x180036944  mov     r9d, ebx; char *
0x180036947  mov     edx, 0A5h; void *
0x18003694c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036951  mov     rcx, [rbp+138h]; this
0x180036958  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18003695f  mov     r9d, ebx; char *
0x180036962  mov     edx, 14F6h; void *
0x180036967  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003696c  mov     rcx, [rsp+230h+var_1D8]
0x180036971  mov     [rsp+230h+var_1D8], 0
0x18003697a  test    rcx, rcx
0x18003697d  jz      short loc_180036985
0x18003697f  call    cs:__imp_SRCacheManager_Close
0x180036985  mov     eax, ebx
0x180036987  jmp     loc_180036D6D
0x18003698c  mov     dl, 1
0x18003698e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID52930508@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID52930508@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID52930508> `wil::Feature<__WilFeatureTraits_Feature_ID52930508>::GetImpl(void)'::`2'::impl
0x180036995  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ID52930508@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID52930508>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003699a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::GetImpl(void)'::`2'::impl
0x1800369a1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::__private_IsEnabled(void)
0x1800369a6  mov     rdx, [rbp+130h+var_1B0]
0x1800369aa  lea     r9, [rbp+130h+var_190]
0x1800369ae  neg     al
0x1800369b0  lea     rcx, [rsp+230h+var_1D8]
0x1800369b5  xorps   xmm0, xmm0
0x1800369b8  sbb     r8, r8
0x1800369bb  movdqa  [rbp+130h+var_190], xmm0
0x1800369c0  xor     eax, eax
0x1800369c2  movdqa  [rbp+130h+var_150], xmm0
0x1800369c7  mov     [rbp+130h+var_180], rax
0x1800369cb  and     r8, 0FFFFFFFFFFFFFFE0h
0x1800369cf  mov     [rbp+130h+var_178], rax
0x1800369d3  add     r8, 23Ah
0x1800369da  mov     [rbp+130h+var_170], rax
0x1800369de  mov     [rbp+130h+var_168], rax
0x1800369e2  mov     [rbp+130h+var_160], rax
0x1800369e6  mov     [rbp+130h+var_158], rax
0x1800369ea  mov     [rbp+130h+var_140], eax
0x1800369ed  mov     [rbp+130h+var_138], rax
0x1800369f1  mov     [rbp+130h+var_130], rax
0x1800369f5  mov     byte ptr [rsp+230h+var_1E0], al
0x1800369f9  lea     rax, [rsp+230h+var_1E0]
0x1800369fe  mov     qword ptr [rsp+230h+bIgnoreCase], rax; unsigned int
0x180036a03  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x180036a08  mov     ebx, eax
0x180036a0a  test    eax, eax
0x180036a0c  jns     short loc_180036A37
0x180036a0e  mov     rcx, [rbp+138h]; this
0x180036a15  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180036a1c  mov     r9d, eax; char *
0x180036a1f  mov     edx, 1506h; void *
0x180036a24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036a29  lea     rcx, [rbp+130h+var_190]; this
0x180036a2d  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180036a32  jmp     loc_18003696C
0x180036a37  cmp     byte ptr [rsp+230h+var_1E0], 0
0x180036a3c  jnz     short loc_180036A60
0x180036a3e  mov     rcx, [rbp+138h]; this
0x180036a45  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180036a4c  mov     r9d, 2; char *
0x180036a52  mov     edx, 1509h; void *
0x180036a57  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180036a5c  mov     ebx, eax
0x180036a5e  jmp     short loc_180036A29
0x180036a60  mov     ecx, dword ptr [rbp+130h+var_178+4]
0x180036a63  test    rsi, rsi
0x180036a66  jz      short loc_180036A71
0x180036a68  mov     eax, ecx
0x180036a6a  shr     eax, 0Bh
0x180036a6d  and     al, 1
0x180036a6f  mov     [rsi], al
0x180036a71  xor     esi, esi
0x180036a73  test    r15, r15
0x180036a76  jz      short loc_180036A82
0x180036a78  mov     eax, ecx
0x180036a7a  shr     eax, 15h
0x180036a7d  and     al, 1
0x180036a7f  mov     [r15], al
0x180036a82  test    r12, r12
0x180036a85  jz      short loc_180036A92
0x180036a87  mov     eax, ecx
0x180036a89  shr     eax, 16h
0x180036a8c  and     al, 1
0x180036a8e  mov     [r12], al
0x180036a92  mov     r15d, 44h ; 'D'
0x180036a98  test    r14, r14
0x180036a9b  jz      loc_180036C32
0x180036aa1  bt      ecx, 0Bh
0x180036aa5  jb      loc_180036C2E
0x180036aab  bt      ecx, 1Ah
0x180036aaf  jb      loc_180036C2E
0x180036ab5  cmp     qword ptr [rbp+130h+var_150], rsi
0x180036ab9  jnz     loc_180036C2E
0x180036abf  call    IsQueryApplicationCapabilitiesPresent
0x180036ac4  test    al, al
0x180036ac6  jz      loc_180036C32
0x180036acc  lea     rax, [rsp+230h+var_1D0]
0x180036ad1  mov     [rsp+230h+var_1D0], rsi
0x180036ad6  lea     rcx, [rsp+230h+var_1D0]
0x180036adb  mov     [rsp+230h+var_1C0], rax
0x180036ae0  mov     [rsp+230h+var_1C8], rsi
0x180036ae5  mov     [rsp+230h+var_1B8], esi
0x180036ae9  mov     [rsp+230h+var_1B4], 1
0x180036aee  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x180036af3  mov     rcx, [rbp+130h+var_1B0]
0x180036af7  lea     r8, [rsp+230h+var_1B8]
0x180036afc  mov     [rsp+230h+var_1F0], rsi
0x180036b01  lea     rdx, [rsp+230h+var_1D0]
0x180036b06  mov     [rsp+230h+var_1F8], rsi
0x180036b0b  xor     r9d, r9d
0x180036b0e  mov     [rsp+230h+var_200], rsi
0x180036b13  mov     [rsp+230h+var_208], rsi
0x180036b18  mov     qword ptr [rsp+230h+bIgnoreCase], rsi; int
0x180036b1d  call    cs:__imp_QueryApplicationCapabilities
0x180036b23  mov     ebx, eax
0x180036b25  cmp     [rsp+230h+var_1B4], sil
0x180036b2a  jz      short loc_180036B39
0x180036b2c  mov     rcx, [rsp+230h+var_1C0]
0x180036b31  mov     edx, [rsp+230h+var_1B8]
0x180036b35  mov     [rcx+8], rdx
0x180036b39  test    ebx, ebx
0x180036b3b  jns     short loc_180036B7A
0x180036b3d  mov     rcx, [rbp+138h]; this
0x180036b44  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180036b4b  mov     r9d, ebx; char *
0x180036b4e  mov     edx, 1530h; void *
0x180036b53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036b58  lea     rcx, [rsp+230h+var_1D0]
0x180036b5d  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x180036b62  lea     rcx, [rbp+130h+var_190]; this
0x180036b66  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180036b6b  mov     rcx, [rsp+230h+var_1D8]
0x180036b70  mov     [rsp+230h+var_1D8], rsi
0x180036b75  jmp     loc_18003697A
0x180036b7a  xorps   xmm0, xmm0
0x180036b7d  lea     rdx, aPackagewritere; "packageWriteRedirectionCompatibilityShi"...
0x180036b84  lea     rcx, [rbp+130h+DestinationString]; DestinationString
0x180036b88  movups  xmmword ptr [rbp+130h+DestinationString.Length], xmm0
0x180036b8c  call    cs:__imp_RtlInitUnicodeString
0x180036b92  mov     r8, r15; Size
0x180036b95  lea     rcx, [rbp+130h+pSid2]; void *
0x180036b9c  xor     edx, edx; Val
0x180036b9e  call    memset_0
0x180036ba3  mov     r8, r15; Size
0x180036ba6  lea     rcx, [rbp+130h+lpString1]; void *
0x180036baa  xor     edx, edx; Val
0x180036bac  call    memset_0
0x180036bb1  lea     r8, [rbp+130h+pSid2]
0x180036bb8  lea     rdx, [rbp+130h+lpString1]
0x180036bbc  lea     rcx, [rbp+130h+DestinationString]
0x180036bc0  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x180036bc6  test    eax, eax
0x180036bc8  jns     short loc_180036BEC
0x180036bca  mov     rcx, [rbp+138h]; this
0x180036bd1  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180036bd8  mov     r9d, eax; char *
0x180036bdb  mov     edx, 153Ch; void *
0x180036be0  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180036be5  mov     ebx, eax
0x180036be7  jmp     loc_180036B58
0x180036bec  mov     ebx, esi
0x180036bee  cmp     [rsp+230h+var_1C8], rsi
0x180036bf3  jbe     short loc_180036C22
0x180036bf5  mov     rcx, [rsp+230h+var_1D0]
0x180036bfa  lea     rdx, [rbp+130h+pSid2]; pSid2
0x180036c01  mov     eax, ebx
0x180036c03  mov     rcx, [rcx+rax*8]; pSid1
0x180036c07  call    cs:__imp_EqualSid
0x180036c0d  test    eax, eax
0x180036c0f  jnz     short loc_180036C1E
0x180036c11  inc     ebx
0x180036c13  mov     eax, ebx
0x180036c15  cmp     rax, [rsp+230h+var_1C8]
0x180036c1a  jb      short loc_180036BF5
0x180036c1c  jmp     short loc_180036C22
0x180036c1e  mov     byte ptr [r14], 1
0x180036c22  lea     rcx, [rsp+230h+var_1D0]
0x180036c27  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x180036c2c  jmp     short loc_180036C32
0x180036c2e  mov     byte ptr [r14], 1
0x180036c32  test    r13, r13
0x180036c35  jz      short loc_180036C43
0x180036c37  mov     eax, dword ptr [rbp+130h+var_170]
0x180036c3a  shr     eax, 0Fh
0x180036c3d  and     al, 1
0x180036c3f  mov     [r13+0], al
0x180036c43  mov     rbx, [rbp+130h+var_120]
0x180036c47  test    rbx, rbx
0x180036c4a  jz      loc_180036CDB
0x180036c50  mov     dl, 1
0x180036c52  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID52930508@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID52930508@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID52930508> `wil::Feature<__WilFeatureTraits_Feature_ID52930508>::GetImpl(void)'::`2'::impl
0x180036c59  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ID52930508@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID52930508>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180036c5e  xorps   xmm0, xmm0
0x180036c61  lea     rcx, [rbp+130h+var_100]; void *
0x180036c65  mov     r8, r15; Size
0x180036c68  movdqa  xmmword ptr [rbp+130h+lpString1], xmm0
0x180036c6d  xor     edx, edx; Val
0x180036c6f  call    memset_0
0x180036c74  mov     rdx, [rbp+130h+var_180]
0x180036c78  lea     rax, [rsp+230h+var_1E0]
0x180036c7d  lea     r9, [rbp+130h+lpString1]
0x180036c81  mov     qword ptr [rsp+230h+bIgnoreCase], rax
0x180036c86  lea     rcx, [rsp+230h+var_1D8]
0x180036c8b  mov     [rbp+130h+var_B8], rsi
0x180036c8f  mov     [rbp+130h+var_B0], rsi
0x180036c96  mov     byte ptr [rsp+230h+var_1E0], sil
0x180036c9b  call    ?Get@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageFamily_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageFamily_NoThrow &,bool &)
0x180036ca0  test    eax, eax
0x180036ca2  js      short loc_180036CD2
0x180036ca4  cmp     byte ptr [rsp+230h+var_1E0], sil
0x180036ca9  jz      short loc_180036CD2
0x180036cab  mov     rcx, [rbp+130h+lpString1+8]; lpString1
0x180036caf  lea     r8, aMicrosoftwindo; "MicrosoftWindows.Client.AIX_cw5n1h2txye"...
0x180036cb6  or      edx, 0FFFFFFFFh; cchCount1
0x180036cb9  mov     [rsp+230h+bIgnoreCase], 1; bIgnoreCase
0x180036cc1  mov     r9d, edx; cchCount2
0x180036cc4  call    cs:__imp_CompareStringOrdinal
0x180036cca  cmp     eax, 2
0x180036ccd  setz    al
0x180036cd0  mov     [rbx], al
0x180036cd2  lea     rcx, [rbp+130h+lpString1]; this
0x180036cd6  call    ??1PackageFamily_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow(void)
0x180036cdb  test    rdi, rdi
0x180036cde  jz      short loc_180036D2A
0x180036ce0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::GetImpl(void)'::`2'::impl
0x180036ce7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchSysAppsAtRuntime>::__private_IsEnabled(void)
0x180036cec  test    al, al
0x180036cee  jz      short loc_180036D05
0x180036cf0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl(void)'::`2'::impl
0x180036cf7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(void)
0x180036cfc  test    al, al
0x180036cfe  jnz     short loc_180036D1B
0x180036d00  mov     al, sil
0x180036d03  jmp     short loc_180036D23
0x180036d05  cmp     dword ptr [rbp+130h+var_170+4], 2
0x180036d09  jz      short loc_180036D27
0x180036d0b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl(void)'::`2'::impl
0x180036d12  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(void)
0x180036d17  test    al, al
0x180036d19  jz      short loc_180036D27
0x180036d1b  mov     eax, dword ptr [rbp+130h+var_170]
0x180036d1e  shr     eax, 15h
0x180036d21  and     al, 1
0x180036d23  mov     [rdi], al
0x180036d25  jmp     short loc_180036D2A
0x180036d27  mov     [rdi], sil
0x180036d2a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA> `wil::Feature<__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA>::GetImpl(void)'::`2'::impl
0x180036d31  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA>::__private_IsEnabled(void)
0x180036d36  test    al, al
0x180036d38  jz      short loc_180036D4D
0x180036d3a  mov     rcx, [rbp+130h+var_118]
0x180036d3e  test    rcx, rcx
0x180036d41  jz      short loc_180036D4D
0x180036d43  mov     eax, dword ptr [rbp+130h+var_178+4]
0x180036d46  shr     eax, 1Ch
0x180036d49  and     al, 1
0x180036d4b  mov     [rcx], al
0x180036d4d  lea     rcx, [rbp+130h+var_190]; this
0x180036d51  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180036d56  mov     rcx, [rsp+230h+var_1D8]
0x180036d5b  mov     [rsp+230h+var_1D8], rsi
  ... truncated ...
```
