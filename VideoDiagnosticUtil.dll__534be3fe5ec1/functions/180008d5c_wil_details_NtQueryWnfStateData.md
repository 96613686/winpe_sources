# wil_details_NtQueryWnfStateData

- ea: `0x180008d5c`
- end: `0x180008dfd`
- name: `wil_details_NtQueryWnfStateData`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006154`
- `0x180008b80`

## callees

- `0x180008d5c`
- `0x18000a010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180008da8`
- `KERNEL32!GetProcAddress` at `0x180008da8`
- `KERNEL32!GetModuleHandleW` at `0x180008d8b`
- `KERNEL32!GetModuleHandleW` at `0x180008d8b`

## string_xrefs

- `0x180008d84`: `ntdll.dll`

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
0x180008d5c  mov     [rsp+arg_0], rbx
0x180008d61  push    rdi
0x180008d62  sub     rsp, 40h
0x180008d66  mov     r10, cs:g_wil_details_pfnNtQueryWnfStateData
0x180008d6d  mov     rbx, r9
0x180008d70  mov     rdi, rcx
0x180008d73  test    r10, r10
0x180008d76  jnz     short loc_180008DCA
0x180008d78  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008d7f  test    rax, rax
0x180008d82  jnz     short loc_180008D9E
0x180008d84  lea     rcx, ModuleName; "ntdll.dll"
0x180008d8b  call    cs:__imp_GetModuleHandleW
0x180008d92  nop     dword ptr [rax+rax+00h]
0x180008d97  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008d9e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180008da5  mov     rcx, rax; hModule
0x180008da8  call    cs:__imp_GetProcAddress
0x180008daf  nop     dword ptr [rax+rax+00h]
0x180008db4  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180008dbb  mov     r10, rax
0x180008dbe  test    rax, rax
0x180008dc1  jnz     short loc_180008DCA
0x180008dc3  mov     eax, 0C0000139h
0x180008dc8  jmp     short loc_180008DF1
0x180008dca  mov     rax, [rsp+48h+arg_28]
0x180008dcf  mov     r9, rbx
0x180008dd2  mov     [rsp+48h+var_20], rax
0x180008dd7  xor     r8d, r8d
0x180008dda  mov     rax, [rsp+48h+arg_20]
0x180008ddf  xor     edx, edx
0x180008de1  mov     [rsp+48h+var_28], rax
0x180008de6  mov     rcx, rdi
0x180008de9  mov     rax, r10
0x180008dec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008df1  mov     rbx, [rsp+48h+arg_0]
0x180008df6  add     rsp, 40h
0x180008dfa  pop     rdi
0x180008dfb  retn
```
