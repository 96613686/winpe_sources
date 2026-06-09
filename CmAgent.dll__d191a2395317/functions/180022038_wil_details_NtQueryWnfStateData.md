# wil_details_NtQueryWnfStateData

- ea: `0x180022038`
- end: `0x1800220d9`
- name: `wil_details_NtQueryWnfStateData`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001a4d8`
- `0x180021e5c`

## callees

- `0x180022038`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022067`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022067`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022084`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022084`

## string_xrefs

- `0x180022060`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall wil_details_NtQueryWnfStateData(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  __int64 (__fastcall *v6)(__int64, _QWORD, _QWORD, __int64, __int64, __int64); // r10
  HMODULE ModuleHandleW; // rax

  v6 = (__int64 (__fastcall *)(__int64, _QWORD, _QWORD, __int64, __int64, __int64))g_wil_details_pfnNtQueryWnfStateData;
  if ( g_wil_details_pfnNtQueryWnfStateData )
    return v6(a1, 0, 0, a4, a5, a6);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  g_wil_details_pfnNtQueryWnfStateData = (__int64)GetProcAddress(ModuleHandleW, "NtQueryWnfStateData");
  v6 = (__int64 (__fastcall *)(__int64, _QWORD, _QWORD, __int64, __int64, __int64))g_wil_details_pfnNtQueryWnfStateData;
  if ( g_wil_details_pfnNtQueryWnfStateData )
    return v6(a1, 0, 0, a4, a5, a6);
  else
    return 3221225785LL;
}

```

## disassembly

```asm
0x180022038  mov     [rsp+arg_0], rbx
0x18002203d  push    rdi
0x18002203e  sub     rsp, 40h
0x180022042  mov     r10, cs:g_wil_details_pfnNtQueryWnfStateData
0x180022049  mov     rbx, r9
0x18002204c  mov     rdi, rcx
0x18002204f  test    r10, r10
0x180022052  jnz     short loc_1800220A6
0x180022054  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002205b  test    rax, rax
0x18002205e  jnz     short loc_18002207A
0x180022060  lea     rcx, ModuleName; "ntdll.dll"
0x180022067  call    cs:__imp_GetModuleHandleW
0x18002206e  nop     dword ptr [rax+rax+00h]
0x180022073  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002207a  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180022081  mov     rcx, rax; hModule
0x180022084  call    cs:__imp_GetProcAddress
0x18002208b  nop     dword ptr [rax+rax+00h]
0x180022090  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180022097  mov     r10, rax
0x18002209a  test    rax, rax
0x18002209d  jnz     short loc_1800220A6
0x18002209f  mov     eax, 0C0000139h
0x1800220a4  jmp     short loc_1800220CD
0x1800220a6  mov     rax, [rsp+48h+arg_28]
0x1800220ab  mov     r9, rbx
0x1800220ae  mov     [rsp+48h+var_20], rax
0x1800220b3  xor     r8d, r8d
0x1800220b6  mov     rax, [rsp+48h+arg_20]
0x1800220bb  xor     edx, edx
0x1800220bd  mov     [rsp+48h+var_28], rax
0x1800220c2  mov     rcx, rdi
0x1800220c5  mov     rax, r10
0x1800220c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220cd  mov     rbx, [rsp+48h+arg_0]
0x1800220d2  add     rsp, 40h
0x1800220d6  pop     rdi
0x1800220d7  retn
```
