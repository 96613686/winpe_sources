# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x1800041a8`
- end: `0x180004216`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800043f8`

## callees

- `0x1800041a8`
- `0x18006a010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800041de`
- `KERNEL32!GetModuleHandleW` at `0x1800041de`
- `KERNEL32!GetProcAddress` at `0x1800041f5`
- `KERNEL32!GetProcAddress` at `0x1800041f5`

## string_xrefs

- `0x1800041d7`: `ntdll.dll`
- `0x1800041eb`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x1800041a8  push    rbx
0x1800041aa  sub     rsp, 30h
0x1800041ae  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800041b7  mov     rbx, [rcx]
0x1800041ba  test    rbx, rbx
0x1800041bd  jz      short loc_180004210
0x1800041bf  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x1800041c6  test    rax, rax
0x1800041c9  jnz     short loc_180004207
0x1800041cb  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800041d2  test    rax, rax
0x1800041d5  jnz     short loc_1800041EB
0x1800041d7  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800041de  call    cs:__imp_GetModuleHandleW
0x1800041e4  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800041eb  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x1800041f2  mov     rcx, rax; hModule
0x1800041f5  call    cs:__imp_GetProcAddress
0x1800041fb  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x180004202  test    rax, rax
0x180004205  jz      short loc_180004210
0x180004207  mov     rcx, rbx
0x18000420a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000420f  nop
0x180004210  add     rsp, 30h
0x180004214  pop     rbx
0x180004215  retn
```
