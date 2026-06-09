# wil::details::UnregisterWilFeatureConfigurationChange(void *)

- ea: `0x18000fe44`
- end: `0x18000feb0`
- name: `?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z`
- size: `108`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a0b0`

## callees

- `0x18000fe44`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fe89`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fe89`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fe6c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fe6c`

## string_xrefs

- `0x18000fe65`: `ntdll.dll`
- `0x18000fe7f`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x18000fe44  push    rbx
0x18000fe46  sub     rsp, 20h
0x18000fe4a  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18000fe51  mov     rbx, rcx
0x18000fe54  test    rax, rax
0x18000fe57  jnz     short loc_18000FEA1
0x18000fe59  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000fe60  test    rax, rax
0x18000fe63  jnz     short loc_18000FE7F
0x18000fe65  lea     rcx, aNtdllDll; "ntdll.dll"
0x18000fe6c  call    cs:__imp_GetModuleHandleW
0x18000fe73  nop     dword ptr [rax+rax+00h]
0x18000fe78  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000fe7f  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18000fe86  mov     rcx, rax; hModule
0x18000fe89  call    cs:__imp_GetProcAddress
0x18000fe90  nop     dword ptr [rax+rax+00h]
0x18000fe95  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18000fe9c  test    rax, rax
0x18000fe9f  jz      short loc_18000FEA9
0x18000fea1  mov     rcx, rbx
0x18000fea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fea9  add     rsp, 20h
0x18000fead  pop     rbx
0x18000feae  retn
```
