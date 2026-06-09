# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x180023814`
- end: `0x1800238af`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `155`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001cda0`
- `0x180027740`

## callees

- `0x180003520`
- `0x180023814`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002387a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002387a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180023863`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180023863`

## string_xrefs

- `0x18002385c`: `ntdll.dll`

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
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x180023814  sub     rsp, 38h
0x180023818  mov     rax, cs:__security_cookie
0x18002381f  xor     rax, rsp
0x180023822  mov     [rsp+38h+var_10], rax
0x180023827  mov     [rsp+38h+var_18], 0
0x180023830  mov     dword ptr [rsp+38h+var_18], ecx
0x180023834  mov     word ptr [rsp+38h+var_18+4], dx
0x180023839  test    r8d, r8d
0x18002383c  jz      short loc_180023844
0x18002383e  or      word ptr [rsp+38h+var_18+6], 1
0x180023844  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18002384b  test    rax, rax
0x18002384e  jnz     short loc_180023893
0x180023850  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180023857  test    rax, rax
0x18002385a  jnz     short loc_180023870
0x18002385c  lea     rcx, ModuleName; "ntdll.dll"
0x180023863  call    cs:__imp_GetModuleHandleW
0x180023869  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180023870  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180023877  mov     rcx, rax; hModule
0x18002387a  call    cs:__imp_GetProcAddress
0x180023880  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180023887  test    rax, rax
0x18002388a  jnz     short loc_180023893
0x18002388c  mov     eax, 0C0000139h
0x180023891  jmp     short loc_18002389D
0x180023893  lea     rcx, [rsp+38h+var_18]
0x180023898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002389d  mov     rcx, [rsp+38h+var_10]
0x1800238a2  xor     rcx, rsp; StackCookie
0x1800238a5  call    __security_check_cookie
0x1800238aa  add     rsp, 38h
0x1800238ae  retn
```
