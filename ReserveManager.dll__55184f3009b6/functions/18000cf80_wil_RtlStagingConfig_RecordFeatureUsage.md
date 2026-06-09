# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x18000cf80`
- end: `0x18000d01b`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b910`

## callees

- `0x180003870`
- `0x18000cf80`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000cfcf`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000cfcf`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000cfe6`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000cfe6`

## string_xrefs

- `0x18000cfc8`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_RecordFeatureUsage(int a1, unsigned __int16 a2, int a3)
{
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v6; // [rsp+20h] [rbp-18h] BYREF
  int v7; // [rsp+24h] [rbp-14h]

  v6 = a1;
  v7 = a2;
  if ( a3 )
    HIWORD(v7) |= 1u;
  ProcAddress = (FARPROC)g_wil_details_pfnRtlNotifyFeatureUsage;
  if ( g_wil_details_pfnRtlNotifyFeatureUsage )
    return ((__int64 (__fastcall *)(int *))ProcAddress)(&v6);
  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "RtlNotifyFeatureUsage");
  g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)ProcAddress;
  if ( ProcAddress )
    return ((__int64 (__fastcall *)(int *))ProcAddress)(&v6);
  else
    return 3221225785LL;
}

```

## disassembly

```asm
0x18000cf80  sub     rsp, 38h
0x18000cf84  mov     rax, cs:__security_cookie
0x18000cf8b  xor     rax, rsp
0x18000cf8e  mov     [rsp+38h+var_10], rax
0x18000cf93  mov     [rsp+38h+var_18], 0
0x18000cf9c  mov     dword ptr [rsp+38h+var_18], ecx
0x18000cfa0  mov     word ptr [rsp+38h+var_18+4], dx
0x18000cfa5  test    r8d, r8d
0x18000cfa8  jz      short loc_18000CFB0
0x18000cfaa  or      word ptr [rsp+38h+var_18+6], 1
0x18000cfb0  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000cfb7  test    rax, rax
0x18000cfba  jnz     short loc_18000CFFF
0x18000cfbc  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cfc3  test    rax, rax
0x18000cfc6  jnz     short loc_18000CFDC
0x18000cfc8  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000cfcf  call    cs:__imp_GetModuleHandleW
0x18000cfd5  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cfdc  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000cfe3  mov     rcx, rax; hModule
0x18000cfe6  call    cs:__imp_GetProcAddress
0x18000cfec  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000cff3  test    rax, rax
0x18000cff6  jnz     short loc_18000CFFF
0x18000cff8  mov     eax, 0C0000139h
0x18000cffd  jmp     short loc_18000D009
0x18000cfff  lea     rcx, [rsp+38h+var_18]
0x18000d004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d009  mov     rcx, [rsp+38h+var_10]
0x18000d00e  xor     rcx, rsp; StackCookie
0x18000d011  call    __security_check_cookie
0x18000d016  add     rsp, 38h
0x18000d01a  retn
```
