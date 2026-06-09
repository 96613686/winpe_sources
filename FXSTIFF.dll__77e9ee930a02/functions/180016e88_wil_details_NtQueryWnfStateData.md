# wil_details_NtQueryWnfStateData

- ea: `0x180016e88`
- end: `0x180016f29`
- name: `wil_details_NtQueryWnfStateData`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180014820`
- `0x180016afc`

## callees

- `0x180016e88`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180016eb7`
- `KERNEL32!GetModuleHandleW` at `0x180016eb7`
- `KERNEL32!GetProcAddress` at `0x180016ed4`
- `KERNEL32!GetProcAddress` at `0x180016ed4`

## string_xrefs

- `0x180016eb0`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil_details_NtQueryWnfStateData(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  FARPROC ProcAddress; // r10
  HMODULE ModuleHandleW; // rax

  ProcAddress = (FARPROC)g_wil_details_pfnNtQueryWnfStateData;
  if ( g_wil_details_pfnNtQueryWnfStateData )
    return ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, __int64, __int64, __int64))ProcAddress)(
             a1,
             0,
             0,
             a4,
             a5,
             a6);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "NtQueryWnfStateData");
  g_wil_details_pfnNtQueryWnfStateData = (__int64)ProcAddress;
  if ( ProcAddress )
    return ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, __int64, __int64, __int64))ProcAddress)(
             a1,
             0,
             0,
             a4,
             a5,
             a6);
  else
    return 3221225785LL;
}

```

## disassembly

```asm
0x180016e88  mov     [rsp+arg_0], rbx
0x180016e8d  push    rdi
0x180016e8e  sub     rsp, 40h
0x180016e92  mov     rbx, r9
0x180016e95  mov     rdi, rcx
0x180016e98  mov     r10, cs:g_wil_details_pfnNtQueryWnfStateData
0x180016e9f  test    r10, r10
0x180016ea2  jnz     short loc_180016EF6
0x180016ea4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180016eab  test    rax, rax
0x180016eae  jnz     short loc_180016ECA
0x180016eb0  lea     rcx, ModuleName; "ntdll.dll"
0x180016eb7  call    cs:__imp_GetModuleHandleW
0x180016ebe  nop     dword ptr [rax+rax+00h]
0x180016ec3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180016eca  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180016ed1  mov     rcx, rax; hModule
0x180016ed4  call    cs:__imp_GetProcAddress
0x180016edb  nop     dword ptr [rax+rax+00h]
0x180016ee0  mov     r10, rax
0x180016ee3  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180016eea  test    rax, rax
0x180016eed  jnz     short loc_180016EF6
0x180016eef  mov     eax, 0C0000139h
0x180016ef4  jmp     short loc_180016F1D
0x180016ef6  mov     rax, [rsp+48h+arg_28]
0x180016efb  mov     [rsp+48h+var_20], rax
0x180016f00  mov     rax, [rsp+48h+arg_20]
0x180016f05  mov     [rsp+48h+var_28], rax
0x180016f0a  mov     r9, rbx
0x180016f0d  xor     r8d, r8d
0x180016f10  xor     edx, edx
0x180016f12  mov     rcx, rdi
0x180016f15  mov     rax, r10
0x180016f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f1d  mov     rbx, [rsp+48h+arg_0]
0x180016f22  add     rsp, 40h
0x180016f26  pop     rdi
0x180016f27  retn
```
