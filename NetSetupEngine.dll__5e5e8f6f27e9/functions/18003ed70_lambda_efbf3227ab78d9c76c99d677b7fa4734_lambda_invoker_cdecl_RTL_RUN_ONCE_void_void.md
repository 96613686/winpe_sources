# _lambda_efbf3227ab78d9c76c99d677b7fa4734_::_lambda_invoker_cdecl_(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18003ed70`
- end: `0x18003edd8`
- name: `?_lambda_invoker_cdecl_@_lambda_efbf3227ab78d9c76c99d677b7fa4734_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `104`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18003ed97`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18003edaa`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18003edbe`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18003ed97`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18003edaa`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18003edbe`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18003ed84`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18003ed84`

## string_xrefs

- `0x18003ed7a`: `ntdll.dll`
- `0x18003ed9d`: `NtCommitRegistryTransaction`
- `0x18003ed8d`: `NtCreateRegistryTransaction`
- `0x18003edb0`: `NtRollbackRegistryTransaction`

## pseudocode

```c
__int64 __fastcall _lambda_efbf3227ab78d9c76c99d677b7fa4734_::_lambda_invoker_cdecl_(
        PINIT_ONCE InitOnce,
        FARPROC *Parameter,
        PVOID *Context)
{
  HMODULE ModuleHandleW; // rbx

  ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
  *Parameter = GetProcAddress(ModuleHandleW, "NtCreateRegistryTransaction");
  Parameter[1] = GetProcAddress(ModuleHandleW, "NtCommitRegistryTransaction");
  Parameter[2] = GetProcAddress(ModuleHandleW, "NtRollbackRegistryTransaction");
  return 1;
}

```

## disassembly

```asm
0x18003ed70  mov     [rsp+arg_0], rbx
0x18003ed75  push    rdi
0x18003ed76  sub     rsp, 20h
0x18003ed7a  lea     rcx, ModuleName; "ntdll.dll"
0x18003ed81  mov     rdi, rdx
0x18003ed84  call    cs:__imp_GetModuleHandleW
0x18003ed8a  mov     rcx, rax; hModule
0x18003ed8d  lea     rdx, aNtcreateregist; "NtCreateRegistryTransaction"
0x18003ed94  mov     rbx, rax
0x18003ed97  call    cs:__imp_GetProcAddress
0x18003ed9d  lea     rdx, aNtcommitregist; "NtCommitRegistryTransaction"
0x18003eda4  mov     rcx, rbx; hModule
0x18003eda7  mov     [rdi], rax
0x18003edaa  call    cs:__imp_GetProcAddress
0x18003edb0  lea     rdx, aNtrollbackregi; "NtRollbackRegistryTransaction"
0x18003edb7  mov     rcx, rbx; hModule
0x18003edba  mov     [rdi+8], rax
0x18003edbe  call    cs:__imp_GetProcAddress
0x18003edc4  mov     rbx, [rsp+28h+arg_0]
0x18003edc9  mov     [rdi+10h], rax
0x18003edcd  mov     eax, 1
0x18003edd2  add     rsp, 20h
0x18003edd6  pop     rdi
0x18003edd7  retn
```
