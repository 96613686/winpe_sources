# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x14000f948`
- end: `0x14000f9ad`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `101`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x14000fa20`

## callees

- `0x14000f948`
- `0x140024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000f98c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000f98c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000f975`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000f975`

## string_xrefs

- `0x14000f96e`: `ntdll.dll`
- `0x14000f982`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
    ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x14000f948  push    rbx
0x14000f94a  sub     rsp, 20h
0x14000f94e  mov     rbx, [rcx]
0x14000f951  test    rbx, rbx
0x14000f954  jz      short loc_14000F9A7
0x14000f956  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x14000f95d  test    rax, rax
0x14000f960  jnz     short loc_14000F99E
0x14000f962  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000f969  test    rax, rax
0x14000f96c  jnz     short loc_14000F982
0x14000f96e  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000f975  call    cs:__imp_GetModuleHandleW
0x14000f97b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000f982  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x14000f989  mov     rcx, rax; hModule
0x14000f98c  call    cs:__imp_GetProcAddress
0x14000f992  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x14000f999  test    rax, rax
0x14000f99c  jz      short loc_14000F9A7
0x14000f99e  mov     rcx, rbx
0x14000f9a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f9a6  nop
0x14000f9a7  add     rsp, 20h
0x14000f9ab  pop     rbx
0x14000f9ac  retn
```
