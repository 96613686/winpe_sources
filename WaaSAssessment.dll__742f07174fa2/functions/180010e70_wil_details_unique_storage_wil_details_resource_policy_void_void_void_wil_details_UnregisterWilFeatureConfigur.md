# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x180010e70`
- end: `0x180010ed5`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180011114`

## callees

- `0x180010e70`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010eb4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010eb4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010e9d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010e9d`

## string_xrefs

- `0x180010e96`: `ntdll.dll`
- `0x180010eaa`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x180010e70  push    rbx
0x180010e72  sub     rsp, 20h
0x180010e76  mov     rbx, [rcx]
0x180010e79  test    rbx, rbx
0x180010e7c  jz      short loc_180010ECF
0x180010e7e  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x180010e85  test    rax, rax
0x180010e88  jnz     short loc_180010EC6
0x180010e8a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180010e91  test    rax, rax
0x180010e94  jnz     short loc_180010EAA
0x180010e96  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180010e9d  call    cs:__imp_GetModuleHandleW
0x180010ea3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180010eaa  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x180010eb1  mov     rcx, rax; hModule
0x180010eb4  call    cs:__imp_GetProcAddress
0x180010eba  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x180010ec1  test    rax, rax
0x180010ec4  jz      short loc_180010ECF
0x180010ec6  mov     rcx, rbx
0x180010ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ece  nop
0x180010ecf  add     rsp, 20h
0x180010ed3  pop     rbx
0x180010ed4  retn
```
