# wil::details::UnregisterWilFeatureConfigurationChange(void *)

- ea: `0x180011abc`
- end: `0x180011b28`
- name: `?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z`
- size: `108`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b048`

## callees

- `0x180011abc`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011ae4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011ae4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011b01`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011b01`

## string_xrefs

- `0x180011add`: `ntdll.dll`
- `0x180011af7`: `RtlUnregisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::UnregisterWilFeatureConfigurationChange(wil::details *this, void *a2)
{
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax

  ProcAddress = (FARPROC)g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification;
  if ( g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification )
    goto LABEL_5;
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "RtlUnregisterFeatureConfigurationChangeNotification");
  g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification = (__int64)ProcAddress;
  if ( ProcAddress )
LABEL_5:
    ((void (__fastcall *)(wil::details *, void *))ProcAddress)(this, a2);
}

```

## disassembly

```asm
0x180011abc  push    rbx
0x180011abe  sub     rsp, 20h
0x180011ac2  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x180011ac9  mov     rbx, rcx
0x180011acc  test    rax, rax
0x180011acf  jnz     short loc_180011B19
0x180011ad1  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011ad8  test    rax, rax
0x180011adb  jnz     short loc_180011AF7
0x180011add  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180011ae4  call    cs:__imp_GetModuleHandleW
0x180011aeb  nop     dword ptr [rax+rax+00h]
0x180011af0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011af7  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x180011afe  mov     rcx, rax; hModule
0x180011b01  call    cs:__imp_GetProcAddress
0x180011b08  nop     dword ptr [rax+rax+00h]
0x180011b0d  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x180011b14  test    rax, rax
0x180011b17  jz      short loc_180011B21
0x180011b19  mov     rcx, rbx
0x180011b1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b21  add     rsp, 20h
0x180011b25  pop     rbx
0x180011b26  retn
```
