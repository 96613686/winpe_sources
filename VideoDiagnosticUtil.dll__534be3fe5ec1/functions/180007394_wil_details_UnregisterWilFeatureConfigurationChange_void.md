# wil::details::UnregisterWilFeatureConfigurationChange(void *)

- ea: `0x180007394`
- end: `0x180007400`
- name: `?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z`
- size: `108`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180002f20`

## callees

- `0x180007394`
- `0x18000a010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800073d9`
- `KERNEL32!GetProcAddress` at `0x1800073d9`
- `KERNEL32!GetModuleHandleW` at `0x1800073bc`
- `KERNEL32!GetModuleHandleW` at `0x1800073bc`

## string_xrefs

- `0x1800073b5`: `ntdll.dll`
- `0x1800073cf`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x180007394  push    rbx
0x180007396  sub     rsp, 20h
0x18000739a  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x1800073a1  mov     rbx, rcx
0x1800073a4  test    rax, rax
0x1800073a7  jnz     short loc_1800073F1
0x1800073a9  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800073b0  test    rax, rax
0x1800073b3  jnz     short loc_1800073CF
0x1800073b5  lea     rcx, ModuleName; "ntdll.dll"
0x1800073bc  call    cs:__imp_GetModuleHandleW
0x1800073c3  nop     dword ptr [rax+rax+00h]
0x1800073c8  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800073cf  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x1800073d6  mov     rcx, rax; hModule
0x1800073d9  call    cs:__imp_GetProcAddress
0x1800073e0  nop     dword ptr [rax+rax+00h]
0x1800073e5  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x1800073ec  test    rax, rax
0x1800073ef  jz      short loc_1800073F9
0x1800073f1  mov     rcx, rbx
0x1800073f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073f9  add     rsp, 20h
0x1800073fd  pop     rbx
0x1800073fe  retn
```
