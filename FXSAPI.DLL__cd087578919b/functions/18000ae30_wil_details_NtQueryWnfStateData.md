# wil_details_NtQueryWnfStateData

- ea: `0x18000ae30`
- end: `0x18000aed1`
- name: `wil_details_NtQueryWnfStateData`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007350`
- `0x1800099bc`

## callees

- `0x18000ae30`
- `0x18003e010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000ae7c`
- `KERNEL32!GetProcAddress` at `0x18000ae7c`
- `KERNEL32!GetModuleHandleW` at `0x18000ae5f`
- `KERNEL32!GetModuleHandleW` at `0x18000ae5f`

## string_xrefs

- `0x18000ae58`: `ntdll.dll`

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
0x18000ae30  mov     [rsp+arg_0], rbx
0x18000ae35  push    rdi
0x18000ae36  sub     rsp, 40h
0x18000ae3a  mov     r10, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000ae41  mov     rbx, r9
0x18000ae44  mov     rdi, rcx
0x18000ae47  test    r10, r10
0x18000ae4a  jnz     short loc_18000AE9E
0x18000ae4c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ae53  test    rax, rax
0x18000ae56  jnz     short loc_18000AE72
0x18000ae58  lea     rcx, ModuleName; "ntdll.dll"
0x18000ae5f  call    cs:__imp_GetModuleHandleW
0x18000ae66  nop     dword ptr [rax+rax+00h]
0x18000ae6b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ae72  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000ae79  mov     rcx, rax; hModule
0x18000ae7c  call    cs:__imp_GetProcAddress
0x18000ae83  nop     dword ptr [rax+rax+00h]
0x18000ae88  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000ae8f  mov     r10, rax
0x18000ae92  test    rax, rax
0x18000ae95  jnz     short loc_18000AE9E
0x18000ae97  mov     eax, 0C0000139h
0x18000ae9c  jmp     short loc_18000AEC5
0x18000ae9e  mov     rax, [rsp+48h+arg_28]
0x18000aea3  mov     r9, rbx
0x18000aea6  mov     [rsp+48h+var_20], rax
0x18000aeab  xor     r8d, r8d
0x18000aeae  mov     rax, [rsp+48h+arg_20]
0x18000aeb3  xor     edx, edx
0x18000aeb5  mov     [rsp+48h+var_28], rax
0x18000aeba  mov     rcx, rdi
0x18000aebd  mov     rax, r10
0x18000aec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aec5  mov     rbx, [rsp+48h+arg_0]
0x18000aeca  add     rsp, 40h
0x18000aece  pop     rdi
0x18000aecf  retn
```
