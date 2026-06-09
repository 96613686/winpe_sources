# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x180003870`
- end: `0x1800038d6`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180003cb4`

## callees

- `0x180003870`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000389d`
- `KERNEL32!GetModuleHandleW` at `0x18000389d`
- `KERNEL32!GetProcAddress` at `0x1800038b4`
- `KERNEL32!GetProcAddress` at `0x1800038b4`

## string_xrefs

- `0x180003896`: `ntdll.dll`
- `0x1800038aa`: `RtlUnregisterFeatureConfigurationChangeNotification`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x180003870  push    rbx
0x180003872  sub     rsp, 20h
0x180003876  mov     rbx, [rcx]
0x180003879  test    rbx, rbx
0x18000387c  jz      short loc_1800038D0
0x18000387e  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x180003885  test    rax, rax
0x180003888  jnz     short loc_1800038C7
0x18000388a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180003891  test    rax, rax
0x180003894  jnz     short loc_1800038AA
0x180003896  lea     rcx, ModuleName; "ntdll.dll"
0x18000389d  call    cs:__imp_GetModuleHandleW
0x1800038a3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800038aa  lea     rdx, ProcName; "RtlUnregisterFeatureConfigurationChange"...
0x1800038b1  mov     rcx, rax; hModule
0x1800038b4  call    cs:__imp_GetProcAddress
0x1800038ba  nop
0x1800038bb  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x1800038c2  test    rax, rax
0x1800038c5  jz      short loc_1800038D0
0x1800038c7  mov     rcx, rbx
0x1800038ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038cf  nop
0x1800038d0  add     rsp, 20h
0x1800038d4  pop     rbx
0x1800038d5  retn
```
