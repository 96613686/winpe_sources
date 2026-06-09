# wil::details::UnregisterWilFeatureConfigurationChange(void *)

- ea: `0x18001608c`
- end: `0x1800160f9`
- name: `?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z`
- size: `109`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800110a0`

## callees

- `0x18001608c`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800160b4`
- `KERNEL32!GetModuleHandleW` at `0x1800160b4`
- `KERNEL32!GetProcAddress` at `0x1800160d1`
- `KERNEL32!GetProcAddress` at `0x1800160d1`

## string_xrefs

- `0x1800160ad`: `ntdll.dll`
- `0x1800160c7`: `RtlUnregisterFeatureConfigurationChangeNotification`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x18001608c  push    rbx
0x18001608e  sub     rsp, 20h
0x180016092  mov     rbx, rcx
0x180016095  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18001609c  test    rax, rax
0x18001609f  jnz     short loc_1800160EA
0x1800160a1  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800160a8  test    rax, rax
0x1800160ab  jnz     short loc_1800160C7
0x1800160ad  lea     rcx, ModuleName; "ntdll.dll"
0x1800160b4  call    cs:__imp_GetModuleHandleW
0x1800160bb  nop     dword ptr [rax+rax+00h]
0x1800160c0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800160c7  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x1800160ce  mov     rcx, rax; hModule
0x1800160d1  call    cs:__imp_GetProcAddress
0x1800160d8  nop     dword ptr [rax+rax+00h]
0x1800160dd  nop
0x1800160de  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x1800160e5  test    rax, rax
0x1800160e8  jz      short loc_1800160F2
0x1800160ea  mov     rcx, rbx
0x1800160ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160f2  add     rsp, 20h
0x1800160f6  pop     rbx
0x1800160f7  retn
```
