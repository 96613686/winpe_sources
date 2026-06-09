# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x1800e62a4`
- end: `0x1800e6309`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `101`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800e6548`

## callees

- `0x1800e62a4`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e62e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e62e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800e62d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800e62d1`

## string_xrefs

- `0x1800e62ca`: `ntdll.dll`
- `0x1800e62de`: `RtlUnregisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
        __int64 *a1)
{
  __int64 v1; // rbx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax

  v1 = *a1;
  if ( *a1 )
  {
    ProcAddress = (FARPROC)g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification;
    if ( g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification )
      goto LABEL_6;
    ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlUnregisterFeatureConfigurationChangeNotification");
    g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification = (__int64)ProcAddress;
    if ( ProcAddress )
LABEL_6:
      ((void (__fastcall *)(__int64))ProcAddress)(v1);
  }
}

```

## disassembly

```asm
0x1800e62a4  push    rbx
0x1800e62a6  sub     rsp, 20h
0x1800e62aa  mov     rbx, [rcx]
0x1800e62ad  test    rbx, rbx
0x1800e62b0  jz      short loc_1800E6303
0x1800e62b2  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x1800e62b9  test    rax, rax
0x1800e62bc  jnz     short loc_1800E62FA
0x1800e62be  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800e62c5  test    rax, rax
0x1800e62c8  jnz     short loc_1800E62DE
0x1800e62ca  lea     rcx, ModuleName; "ntdll.dll"
0x1800e62d1  call    cs:__imp_GetModuleHandleW
0x1800e62d7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800e62de  lea     rdx, ProcName; "RtlUnregisterFeatureConfigurationChange"...
0x1800e62e5  mov     rcx, rax; hModule
0x1800e62e8  call    cs:__imp_GetProcAddress
0x1800e62ee  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x1800e62f5  test    rax, rax
0x1800e62f8  jz      short loc_1800E6303
0x1800e62fa  mov     rcx, rbx
0x1800e62fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6302  nop
0x1800e6303  add     rsp, 20h
0x1800e6307  pop     rbx
0x1800e6308  retn
```
