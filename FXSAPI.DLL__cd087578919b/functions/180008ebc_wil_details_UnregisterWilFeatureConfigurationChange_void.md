# wil::details::UnregisterWilFeatureConfigurationChange(void *)

- ea: `0x180008ebc`
- end: `0x180008f28`
- name: `?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z`
- size: `108`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000309c`

## callees

- `0x180008ebc`
- `0x18003e010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180008f01`
- `KERNEL32!GetProcAddress` at `0x180008f01`
- `KERNEL32!GetModuleHandleW` at `0x180008ee4`
- `KERNEL32!GetModuleHandleW` at `0x180008ee4`

## string_xrefs

- `0x180008edd`: `ntdll.dll`
- `0x180008ef7`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x180008ebc  push    rbx
0x180008ebe  sub     rsp, 20h
0x180008ec2  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x180008ec9  mov     rbx, rcx
0x180008ecc  test    rax, rax
0x180008ecf  jnz     short loc_180008F19
0x180008ed1  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008ed8  test    rax, rax
0x180008edb  jnz     short loc_180008EF7
0x180008edd  lea     rcx, ModuleName; "ntdll.dll"
0x180008ee4  call    cs:__imp_GetModuleHandleW
0x180008eeb  nop     dword ptr [rax+rax+00h]
0x180008ef0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008ef7  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x180008efe  mov     rcx, rax; hModule
0x180008f01  call    cs:__imp_GetProcAddress
0x180008f08  nop     dword ptr [rax+rax+00h]
0x180008f0d  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x180008f14  test    rax, rax
0x180008f17  jz      short loc_180008F21
0x180008f19  mov     rcx, rbx
0x180008f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f21  add     rsp, 20h
0x180008f25  pop     rbx
0x180008f26  retn
```
