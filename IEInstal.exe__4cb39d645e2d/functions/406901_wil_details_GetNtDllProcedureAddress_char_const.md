# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x406901`
- end: `0x406927`
- name: `?wil_details_GetNtDllProcedureAddress@@YGP6GHXZPBD@Z`
- size: `38`
- prototype: `FARPROC __thiscall(const CHAR *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x406980`

## callees

- `0x406901`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x40691f`
- `KERNEL32!GetProcAddress` at `0x40691f`
- `KERNEL32!GetModuleHandleW` at `0x406912`
- `KERNEL32!GetModuleHandleW` at `0x406912`

## string_xrefs

- `0x40690d`: `ntdll.dll`

## pseudocode

```c
FARPROC __thiscall wil_details_GetNtDllProcedureAddress(const CHAR *this)
{
  HMODULE ModuleHandleW; // eax

  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  return GetProcAddress(ModuleHandleW, this);
}

```

## disassembly

```asm
0x406901  mov     eax, ?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YGPAUHINSTANCE__@@XZ@4PAU2@A; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x406906  push    esi
0x406907  mov     esi, ecx
0x406909  test    eax, eax
0x40690b  jnz     short loc_40691D
0x40690d  push    offset aNtdllDll; "ntdll.dll"
0x406912  call    ds:__imp__GetModuleHandleW@4; GetModuleHandleW(x)
0x406918  mov     ?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YGPAUHINSTANCE__@@XZ@4PAU2@A, eax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x40691d  push    esi; lpProcName
0x40691e  push    eax; hModule
0x40691f  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x406925  pop     esi
0x406926  retn
```
