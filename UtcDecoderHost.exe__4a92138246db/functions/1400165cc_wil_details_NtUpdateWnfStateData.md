# wil_details_NtUpdateWnfStateData

- ea: `0x1400165cc`
- end: `0x140016676`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x140015230`
- `0x14001638c`

## callees

- `0x1400165cc`
- `0x140018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140016603`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140016603`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001661a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001661a`

## string_xrefs

- `0x1400165fc`: `ntdll.dll`
- `0x140016610`: `NtUpdateWnfStateData`

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
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x1400165cc  mov     [rsp+arg_0], rbx
0x1400165d1  mov     [rsp+arg_8], rsi
0x1400165d6  push    rdi
0x1400165d7  sub     rsp, 40h
0x1400165db  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1400165e2  mov     ebx, r8d
0x1400165e5  mov     rdi, rdx
0x1400165e8  mov     rsi, rcx
0x1400165eb  test    r10, r10
0x1400165ee  jnz     short loc_140016636
0x1400165f0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400165f7  test    rax, rax
0x1400165fa  jnz     short loc_140016610
0x1400165fc  lea     rcx, ModuleName; "ntdll.dll"
0x140016603  call    cs:__imp_GetModuleHandleW
0x140016609  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140016610  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x140016617  mov     rcx, rax; hModule
0x14001661a  call    cs:__imp_GetProcAddress
0x140016620  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x140016627  mov     r10, rax
0x14001662a  test    rax, rax
0x14001662d  jnz     short loc_140016636
0x14001662f  mov     eax, 0C0000139h
0x140016634  jmp     short loc_140016666
0x140016636  mov     eax, [rsp+48h+arg_30]
0x14001663d  xor     r9d, r9d
0x140016640  mov     [rsp+48h+var_18], eax
0x140016644  mov     r8d, ebx
0x140016647  mov     eax, [rsp+48h+arg_28]
0x14001664b  mov     rdx, rdi
0x14001664e  mov     [rsp+48h+var_20], eax
0x140016652  mov     rcx, rsi
0x140016655  mov     rax, r10
0x140016658  mov     [rsp+48h+var_28], 0
0x140016661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016666  mov     rbx, [rsp+48h+arg_0]
0x14001666b  mov     rsi, [rsp+48h+arg_8]
0x140016670  add     rsp, 40h
0x140016674  pop     rdi
0x140016675  retn
```
