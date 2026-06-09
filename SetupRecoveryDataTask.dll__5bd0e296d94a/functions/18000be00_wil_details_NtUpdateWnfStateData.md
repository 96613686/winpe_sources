# wil_details_NtUpdateWnfStateData

- ea: `0x18000be00`
- end: `0x18000beaa`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180007f30`
- `0x18000b430`

## callees

- `0x18000be00`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000be4e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000be4e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000be37`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000be37`

## string_xrefs

- `0x18000be30`: `ntdll.dll`
- `0x18000be44`: `NtUpdateWnfStateData`

## pseudocode

```c
__int64 __fastcall wil_details_NtUpdateWnfStateData(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        int a6,
        int a7)
{
  __int64 (__fastcall *v7)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int); // r10
  HMODULE ModuleHandleW; // rax

  v7 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int))g_wil_details_pfnNtUpdateWnfStateData;
  if ( g_wil_details_pfnNtUpdateWnfStateData )
    return v7(a1, a2, a3, 0, 0, a6, a7);
  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  g_wil_details_pfnNtUpdateWnfStateData = (__int64)GetProcAddress(ModuleHandleW, "NtUpdateWnfStateData");
  v7 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int))g_wil_details_pfnNtUpdateWnfStateData;
  if ( g_wil_details_pfnNtUpdateWnfStateData )
    return v7(a1, a2, a3, 0, 0, a6, a7);
  else
    return 3221225785LL;
}

```

## disassembly

```asm
0x18000be00  mov     [rsp+arg_0], rbx
0x18000be05  mov     [rsp+arg_8], rsi
0x18000be0a  push    rdi
0x18000be0b  sub     rsp, 40h
0x18000be0f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000be16  mov     ebx, r8d
0x18000be19  mov     rdi, rdx
0x18000be1c  mov     rsi, rcx
0x18000be1f  test    r10, r10
0x18000be22  jnz     short loc_18000BE6A
0x18000be24  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000be2b  test    rax, rax
0x18000be2e  jnz     short loc_18000BE44
0x18000be30  lea     rcx, ModuleName; "ntdll.dll"
0x18000be37  call    cs:__imp_GetModuleHandleW
0x18000be3d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000be44  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000be4b  mov     rcx, rax; hModule
0x18000be4e  call    cs:__imp_GetProcAddress
0x18000be54  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000be5b  mov     r10, rax
0x18000be5e  test    rax, rax
0x18000be61  jnz     short loc_18000BE6A
0x18000be63  mov     eax, 0C0000139h
0x18000be68  jmp     short loc_18000BE9A
0x18000be6a  mov     eax, [rsp+48h+arg_30]
0x18000be71  xor     r9d, r9d
0x18000be74  mov     [rsp+48h+var_18], eax
0x18000be78  mov     r8d, ebx
0x18000be7b  mov     eax, [rsp+48h+arg_28]
0x18000be7f  mov     rdx, rdi
0x18000be82  mov     [rsp+48h+var_20], eax
0x18000be86  mov     rcx, rsi
0x18000be89  mov     rax, r10
0x18000be8c  mov     [rsp+48h+var_28], 0
0x18000be95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be9a  mov     rbx, [rsp+48h+arg_0]
0x18000be9f  mov     rsi, [rsp+48h+arg_8]
0x18000bea4  add     rsp, 40h
0x18000bea8  pop     rdi
0x18000bea9  retn
```
