# wil::details::UnregisterWilFeatureConfigurationChange(void *)

- ea: `0x1800287ac`
- end: `0x180028818`
- name: `?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z`
- size: `108`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180024110`

## callees

- `0x1800287ac`
- `0x18005f010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800287d4`
- `KERNEL32!GetModuleHandleW` at `0x1800287d4`
- `KERNEL32!GetProcAddress` at `0x1800287f1`
- `KERNEL32!GetProcAddress` at `0x1800287f1`

## string_xrefs

- `0x1800287cd`: `ntdll.dll`
- `0x1800287e7`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x1800287ac  push    rbx
0x1800287ae  sub     rsp, 20h
0x1800287b2  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x1800287b9  mov     rbx, rcx
0x1800287bc  test    rax, rax
0x1800287bf  jnz     short loc_180028809
0x1800287c1  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800287c8  test    rax, rax
0x1800287cb  jnz     short loc_1800287E7
0x1800287cd  lea     rcx, aNtdllDll; "ntdll.dll"
0x1800287d4  call    cs:__imp_GetModuleHandleW
0x1800287db  nop     dword ptr [rax+rax+00h]
0x1800287e0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800287e7  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x1800287ee  mov     rcx, rax; hModule
0x1800287f1  call    cs:__imp_GetProcAddress
0x1800287f8  nop     dword ptr [rax+rax+00h]
0x1800287fd  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x180028804  test    rax, rax
0x180028807  jz      short loc_180028811
0x180028809  mov     rcx, rbx
0x18002880c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028811  add     rsp, 20h
0x180028815  pop     rbx
0x180028816  retn
```
