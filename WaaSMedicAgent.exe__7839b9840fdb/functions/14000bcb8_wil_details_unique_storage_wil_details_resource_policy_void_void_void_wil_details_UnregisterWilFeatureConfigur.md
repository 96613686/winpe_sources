# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x14000bcb8`
- end: `0x14000bd26`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `110`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x14000bdac`

## callees

- `0x14000bcb8`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000bd05`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000bd05`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000bcee`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000bcee`

## string_xrefs

- `0x14000bce7`: `ntdll.dll`
- `0x14000bcfb`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x14000bcb8  push    rbx
0x14000bcba  sub     rsp, 30h
0x14000bcbe  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x14000bcc7  mov     rbx, [rcx]
0x14000bcca  test    rbx, rbx
0x14000bccd  jz      short loc_14000BD20
0x14000bccf  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x14000bcd6  test    rax, rax
0x14000bcd9  jnz     short loc_14000BD17
0x14000bcdb  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000bce2  test    rax, rax
0x14000bce5  jnz     short loc_14000BCFB
0x14000bce7  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000bcee  call    cs:__imp_GetModuleHandleW
0x14000bcf4  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000bcfb  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x14000bd02  mov     rcx, rax; hModule
0x14000bd05  call    cs:__imp_GetProcAddress
0x14000bd0b  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x14000bd12  test    rax, rax
0x14000bd15  jz      short loc_14000BD20
0x14000bd17  mov     rcx, rbx
0x14000bd1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bd1f  nop
0x14000bd20  add     rsp, 30h
0x14000bd24  pop     rbx
0x14000bd25  retn
```
