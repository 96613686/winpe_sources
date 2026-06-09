# wil::details::UnregisterWilFeatureConfigurationChange(void *)

- ea: `0x140070f68`
- end: `0x140070fd4`
- name: `?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z`
- size: `108`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x14006bf98`

## callees

- `0x140070f68`
- `0x14008b010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140070fad`
- `KERNEL32!GetProcAddress` at `0x140070fad`
- `KERNEL32!GetModuleHandleW` at `0x140070f90`
- `KERNEL32!GetModuleHandleW` at `0x140070f90`

## string_xrefs

- `0x140070f89`: `ntdll.dll`
- `0x140070fa3`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x140070f68  push    rbx
0x140070f6a  sub     rsp, 20h
0x140070f6e  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x140070f75  mov     rbx, rcx
0x140070f78  test    rax, rax
0x140070f7b  jnz     short loc_140070FC5
0x140070f7d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140070f84  test    rax, rax
0x140070f87  jnz     short loc_140070FA3
0x140070f89  lea     rcx, ModuleName; "ntdll.dll"
0x140070f90  call    cs:__imp_GetModuleHandleW
0x140070f97  nop     dword ptr [rax+rax+00h]
0x140070f9c  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140070fa3  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x140070faa  mov     rcx, rax; hModule
0x140070fad  call    cs:__imp_GetProcAddress
0x140070fb4  nop     dword ptr [rax+rax+00h]
0x140070fb9  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x140070fc0  test    rax, rax
0x140070fc3  jz      short loc_140070FCD
0x140070fc5  mov     rcx, rbx
0x140070fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140070fcd  add     rsp, 20h
0x140070fd1  pop     rbx
0x140070fd2  retn
```
