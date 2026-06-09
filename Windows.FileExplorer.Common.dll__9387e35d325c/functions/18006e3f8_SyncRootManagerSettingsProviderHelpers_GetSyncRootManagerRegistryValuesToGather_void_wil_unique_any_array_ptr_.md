# SyncRootManagerSettingsProviderHelpers::GetSyncRootManagerRegistryValuesToGather(void *,wil::unique_any_array_ptr<SettingsProviderRegistryValue,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,SyncRootManagerSettingsProviderHelpers::provider_deleter,unsigned __int64> &,CloudFilesTelemetry::SyncRootManagerSettingsProvider_GatherSyncRootRegistrySettingsInHost &)

- ea: `0x18006e3f8`
- end: `0x18006e60c`
- name: `?GetSyncRootManagerRegistryValuesToGather@SyncRootManagerSettingsProviderHelpers@@YAXPEAXAEAV?$unique_any_array_ptr@USettingsProviderRegistryValue@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@Uprovider_deleter@SyncRootManagerSettingsProviderHelpers@@_K@wil@@AEAVSyncRootManagerSettingsProvider_GatherSyncRootRegistrySettingsInHost@CloudFilesTelemetry@@@Z`
- size: `532`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18006dd30`

## callees

- `0x180004d6c`
- `0x180007900`
- `0x180015fa0`
- `0x180016440`
- `0x18001d320`
- `0x18002a780`
- `0x180035e1c`
- `0x180036144`
- `0x180036238`
- `0x180037780`
- `0x18006b7d0`
- `0x18006cbf0`
- `0x18006d3a4`
- `0x18006d828`
- `0x18006e054`
- `0x18006e34c`
- `0x18006e3f8`
- `0x18006fdc0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e4b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e4b6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006e464`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006e464`

## string_xrefs

- `0x18006e5f7`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\SyncRootManagerSettingsProviderHelpers.h`
- `0x18006e4bc`: `{{USERSID}}`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SyncRootManagerSettingsProviderHelpers::GetSyncRootManagerRegistryValuesToGather(
        PSID Sid,
        __int64 a2,
        __int64 a3)
{
  const char *v5; // r9
  __int64 *unique; // rax
  __int64 v7; // rsi
  HLOCAL v8; // rcx
  unsigned __int64 v9; // rdi
  __int64 i; // rcx
  __int64 v11; // rbx
  _OWORD *SettingsProviderRegistryValueStruct; // rax
  __int128 v13; // xmm1
  HLOCAL hMem; // [rsp+30h] [rbp-69h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-61h] BYREF
  __int64 v17; // [rsp+40h] [rbp-59h] BYREF
  __int64 v18; // [rsp+48h] [rbp-51h]
  unsigned int v19[2]; // [rsp+58h] [rbp-41h] BYREF
  _QWORD v20[2]; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v21[32]; // [rsp+70h] [rbp-29h] BYREF
  __int64 v22[3]; // [rsp+90h] [rbp-9h] BYREF
  _BYTE v23[16]; // [rsp+B0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  SyncRootManagerSettingsProviderHelpers::GetSyncRootManagerKey((unsigned int)v19);
  hMem = *(HLOCAL *)v19;
  SyncRootManagerSettingsProviderHelpers::GetKeySubkeyNames(&v17, &hMem);
  StringSid = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &StringSid,
    0);
  if ( !ConvertSidToStringSidW(Sid, &StringSid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x5B,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\SyncRootManagerSettingsProviderHelpers.h",
      v5);
  unique = (__int64 *)wil::make_unique_hlocal<SettingsProviderRegistryValue [0]>(&hMem, (v18 - v17) >> 5);
  v7 = *unique;
  *unique = 0;
  v20[0] = v7;
  v20[1] = (v18 - v17) >> 5;
  v8 = hMem;
  hMem = 0;
  if ( v8 )
    LocalFree(v8);
  std::wstring::wstring(v22, L"{{USERSID}}");
  std::wstring::wstring(v23, StringSid);
  v9 = 0;
  for ( i = v17; v9 < (v18 - v17) >> 5; i = v17 )
  {
    v11 = 32 * v9;
    if ( std::wstring::find(32 * v9 + i, v23) != -1 )
      std::wstring::_Replace<unsigned short>((void *)(v11 + v17), v22[2]);
    SettingsProviderRegistryValueStruct = (_OWORD *)SyncRootManagerSettingsProviderHelpers::CreateSettingsProviderRegistryValueStruct(
                                                      v21,
                                                      v11 + v17);
    v13 = SettingsProviderRegistryValueStruct[1];
    *(_OWORD *)(v11 + v7) = *SettingsProviderRegistryValueStruct;
    *(_OWORD *)(v11 + v7 + 16) = v13;
    ++v9;
  }
  wil::unique_any_array_ptr<SettingsProviderRegistryValue,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,SyncRootManagerSettingsProviderHelpers::provider_deleter,unsigned __int64>::operator=(
    &g_hostSyncRootManagerRegistryValuesToMirror,
    v20);
  hMem = (HLOCAL)((v18 - v17) >> 5);
  CloudFilesTelemetry::SyncRootManagerSettingsProvider_GatherSyncRootRegistrySettingsInHost::SyncRootManagerSettingsProvider_SubKeysUnderSyncRootGatheredInHost<unsigned __int64>(
    a3,
    &hMem);
  std::wstring::_Tidy_deallocate(v23);
  std::wstring::_Tidy_deallocate(v22);
  wil::unique_any_array_ptr<SettingsProviderRegistryValue,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,SyncRootManagerSettingsProviderHelpers::provider_deleter,unsigned __int64>::reset(v20);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&StringSid);
  std::vector<std::wstring>::_Tidy(&v17);
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v19);
}

```

## disassembly

```asm
0x18006e3f8  mov     [rsp-8+arg_8], rbx
0x18006e3fd  mov     [rsp-8+arg_18], rsi
0x18006e402  push    rbp
0x18006e403  push    rdi
0x18006e404  push    r14
0x18006e406  lea     rbp, [rsp-47h]
0x18006e40b  sub     rsp, 0E0h
0x18006e412  mov     rax, cs:__security_cookie
0x18006e419  xor     rax, rsp
0x18006e41c  mov     [rbp+57h+var_20], rax
0x18006e420  mov     r14, r8
0x18006e423  mov     rbx, rcx
0x18006e426  lea     rcx, [rbp+57h+var_98]; unsigned int
0x18006e42a  call    ?GetSyncRootManagerKey@SyncRootManagerSettingsProviderHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; SyncRootManagerSettingsProviderHelpers::GetSyncRootManagerKey(void)
0x18006e42f  nop
0x18006e430  mov     rax, qword ptr [rbp+57h+var_98]
0x18006e434  mov     [rbp+57h+hMem], rax
0x18006e438  lea     rdx, [rbp+57h+hMem]
0x18006e43c  lea     rcx, [rbp+57h+var_B0]
0x18006e440  call    ?GetKeySubkeyNames@SyncRootManagerSettingsProviderHelpers@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBQEAUHKEY__@@@Z; SyncRootManagerSettingsProviderHelpers::GetKeySubkeyNames(HKEY__ * const &)
0x18006e445  nop
0x18006e446  mov     [rbp+57h+StringSid], 0
0x18006e44e  xor     edx, edx
0x18006e450  lea     rcx, [rbp+57h+StringSid]
0x18006e454  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18006e459  mov     rdi, [rbp+5Fh]
0x18006e45d  lea     rdx, [rbp+57h+StringSid]; StringSid
0x18006e461  mov     rcx, rbx; Sid
0x18006e464  call    cs:__imp_ConvertSidToStringSidW
0x18006e46a  test    eax, eax
0x18006e46c  jz      loc_18006E5F7
0x18006e472  mov     rdx, [rbp+57h+var_A8]
0x18006e476  sub     rdx, [rbp+57h+var_B0]
0x18006e47a  sar     rdx, 5
0x18006e47e  lea     rcx, [rbp+57h+hMem]
0x18006e482  call    ??$make_unique_hlocal@$$BY0A@USettingsProviderRegistryValue@@@wil@@YA?AV?$unique_ptr@$$BY0A@USettingsProviderRegistryValue@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<SettingsProviderRegistryValue [0]>(unsigned __int64)
0x18006e487  mov     rsi, [rax]
0x18006e48a  mov     qword ptr [rax], 0
0x18006e491  mov     [rbp+57h+var_90], rsi
0x18006e495  mov     rax, [rbp+57h+var_A8]
0x18006e499  sub     rax, [rbp+57h+var_B0]
0x18006e49d  sar     rax, 5
0x18006e4a1  mov     [rbp+57h+var_88], rax
0x18006e4a5  mov     rcx, [rbp+57h+hMem]; hMem
0x18006e4a9  mov     [rbp+57h+hMem], 0
0x18006e4b1  test    rcx, rcx
0x18006e4b4  jz      short loc_18006E4BC
0x18006e4b6  call    cs:__imp_LocalFree
0x18006e4bc  lea     rdx, aUsersid; "{{USERSID}}"
0x18006e4c3  lea     rcx, [rbp+57h+var_60]
0x18006e4c7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006e4cc  nop
0x18006e4cd  mov     rdx, [rbp+57h+StringSid]
0x18006e4d1  lea     rcx, [rbp+57h+var_40]
0x18006e4d5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006e4da  nop
0x18006e4db  xor     edi, edi
0x18006e4dd  mov     rax, [rbp+57h+var_A8]
0x18006e4e1  mov     rcx, [rbp+57h+var_B0]
0x18006e4e5  sub     rax, rcx
0x18006e4e8  sar     rax, 5
0x18006e4ec  test    rax, rax
0x18006e4ef  jz      short loc_18006E56B
0x18006e4f1  mov     rbx, rdi
0x18006e4f4  shl     rbx, 5
0x18006e4f8  add     rcx, rbx
0x18006e4fb  lea     rdx, [rbp+57h+var_40]
0x18006e4ff  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x18006e504  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006e508  jz      short loc_18006E534
0x18006e50a  mov     rcx, [rbp+57h+var_B0]
0x18006e50e  add     rcx, rbx; Src
0x18006e511  mov     rdx, [rbp+57h+var_50]
0x18006e515  lea     r9, [rbp+57h+var_60]
0x18006e519  cmp     [rbp+57h+var_48], 7
0x18006e51e  cmova   r9, [rbp+57h+var_60]
0x18006e523  mov     [rsp+0F0h+var_D0], rdx; __int64
0x18006e528  mov     r8, [rbp+57h+var_30]
0x18006e52c  mov     rdx, rax
0x18006e52f  call    ??$_Replace@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_K_KQEBG0@Z; std::wstring::_Replace<ushort>(unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x18006e534  mov     rdx, [rbp+57h+var_B0]
0x18006e538  add     rdx, rbx
0x18006e53b  lea     rcx, [rbp+57h+var_80]
0x18006e53f  call    ?CreateSettingsProviderRegistryValueStruct@SyncRootManagerSettingsProviderHelpers@@YA?AUSettingsProviderRegistryValue@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SyncRootManagerSettingsProviderHelpers::CreateSettingsProviderRegistryValueStruct(std::wstring const &)
0x18006e544  movups  xmm0, xmmword ptr [rax]
0x18006e547  movups  xmm1, xmmword ptr [rax+10h]
0x18006e54b  movups  xmmword ptr [rbx+rsi], xmm0
0x18006e54f  movups  xmmword ptr [rbx+rsi+10h], xmm1
0x18006e554  inc     rdi
0x18006e557  mov     rax, [rbp+57h+var_A8]
0x18006e55b  mov     rcx, [rbp+57h+var_B0]
0x18006e55f  sub     rax, rcx
0x18006e562  sar     rax, 5
0x18006e566  cmp     rdi, rax
0x18006e569  jb      short loc_18006E4F1
0x18006e56b  lea     rdx, [rbp+57h+var_90]
0x18006e56f  lea     rcx, ?g_hostSyncRootManagerRegistryValuesToMirror@@3V?$unique_any_array_ptr@USettingsProviderRegistryValue@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@Uprovider_deleter@SyncRootManagerSettingsProviderHelpers@@_K@wil@@A; wil::unique_any_array_ptr<SettingsProviderRegistryValue,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,SyncRootManagerSettingsProviderHelpers::provider_deleter,unsigned __int64> g_hostSyncRootManagerRegistryValuesToMirror
0x18006e576  call    ??4?$unique_any_array_ptr@USettingsProviderRegistryValue@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@Uprovider_deleter@SyncRootManagerSettingsProviderHelpers@@_K@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_array_ptr<SettingsProviderRegistryValue,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,SyncRootManagerSettingsProviderHelpers::provider_deleter,unsigned __int64>::operator=(wil::unique_any_array_ptr<SettingsProviderRegistryValue,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,SyncRootManagerSettingsProviderHelpers::provider_deleter,unsigned __int64> &&)
0x18006e57b  mov     rax, [rbp+57h+var_A8]
0x18006e57f  sub     rax, [rbp+57h+var_B0]
0x18006e583  sar     rax, 5
0x18006e587  mov     [rbp+57h+hMem], rax
0x18006e58b  lea     rdx, [rbp+57h+hMem]
0x18006e58f  mov     rcx, r14
0x18006e592  call    ??$SyncRootManagerSettingsProvider_SubKeysUnderSyncRootGatheredInHost@_K@SyncRootManagerSettingsProvider_GatherSyncRootRegistrySettingsInHost@CloudFilesTelemetry@@QEAAX$$QEA_K@Z; CloudFilesTelemetry::SyncRootManagerSettingsProvider_GatherSyncRootRegistrySettingsInHost::SyncRootManagerSettingsProvider_SubKeysUnderSyncRootGatheredInHost<unsigned __int64>(unsigned __int64 &&)
0x18006e597  nop
0x18006e598  lea     rcx, [rbp+57h+var_40]
0x18006e59c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006e5a1  nop
0x18006e5a2  lea     rcx, [rbp+57h+var_60]
0x18006e5a6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006e5ab  nop
0x18006e5ac  lea     rcx, [rbp+57h+var_90]
0x18006e5b0  call    ?reset@?$unique_any_array_ptr@USettingsProviderRegistryValue@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@Uprovider_deleter@SyncRootManagerSettingsProviderHelpers@@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<SettingsProviderRegistryValue,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,SyncRootManagerSettingsProviderHelpers::provider_deleter,unsigned __int64>::reset(void)
0x18006e5b5  nop
0x18006e5b6  lea     rcx, [rbp+57h+StringSid]; void *
0x18006e5ba  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18006e5bf  nop
0x18006e5c0  lea     rcx, [rbp+57h+var_B0]
0x18006e5c4  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18006e5c9  nop
0x18006e5ca  lea     rcx, [rbp+57h+var_98]
0x18006e5ce  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18006e5d3  mov     rcx, [rbp+57h+var_20]
0x18006e5d7  xor     rcx, rsp; StackCookie
0x18006e5da  call    __security_check_cookie
0x18006e5df  lea     r11, [rsp+0F0h+var_10]
0x18006e5e7  mov     rbx, [r11+28h]
0x18006e5eb  mov     rsi, [r11+38h]
0x18006e5ef  mov     rsp, r11
0x18006e5f2  pop     r14
0x18006e5f4  pop     rdi
0x18006e5f5  pop     rbp
0x18006e5f6  retn
0x18006e5f7  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\fileexplorer\\windo"...
0x18006e5fe  mov     edx, 5Bh ; '['; void *
0x18006e603  mov     rcx, rdi; this
0x18006e606  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
