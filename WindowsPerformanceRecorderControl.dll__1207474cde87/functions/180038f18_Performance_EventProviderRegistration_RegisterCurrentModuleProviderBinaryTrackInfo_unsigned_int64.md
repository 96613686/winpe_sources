# Performance::EventProviderRegistration::RegisterCurrentModuleProviderBinaryTrackInfo(unsigned __int64)

- ea: `0x180038f18`
- end: `0x180038f5e`
- name: `?RegisterCurrentModuleProviderBinaryTrackInfo@EventProviderRegistration@Performance@@YAX_K@Z`
- size: `70`
- prototype: `void __fastcall(Performance::EventProviderRegistration *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180056c80`

## callees

- `0x180038f18`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180038f28`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180038f28`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180038f3d`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180038f3d`

## string_xrefs

- `0x180038f21`: `api-ms-win-eventing-provider-l1-1-0.dll`

## pseudocode

```c
void __fastcall Performance::EventProviderRegistration::RegisterCurrentModuleProviderBinaryTrackInfo(
        Performance::EventProviderRegistration *this)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  ModuleHandleW = GetModuleHandleW(L"api-ms-win-eventing-provider-l1-1-0.dll");
  if ( ModuleHandleW )
  {
    ProcAddress = GetProcAddress(ModuleHandleW, "EventSetInformation");
    if ( ProcAddress )
      ((void (__fastcall *)(Performance::EventProviderRegistration *, _QWORD, _QWORD, _QWORD))ProcAddress)(
        this,
        0,
        0,
        0);
  }
}

```

## disassembly

```asm
0x180038f18  push    rbx
0x180038f1a  sub     rsp, 30h
0x180038f1e  mov     rbx, rcx
0x180038f21  lea     rcx, ModuleName; "api-ms-win-eventing-provider-l1-1-0.dll"
0x180038f28  call    cs:__imp_GetModuleHandleW
0x180038f2e  test    rax, rax
0x180038f31  jz      short loc_180038F58
0x180038f33  lea     rdx, aEventsetinform; "EventSetInformation"
0x180038f3a  mov     rcx, rax; hModule
0x180038f3d  call    cs:__imp_GetProcAddress
0x180038f43  test    rax, rax
0x180038f46  jz      short loc_180038F58
0x180038f48  xor     r9d, r9d
0x180038f4b  xor     r8d, r8d
0x180038f4e  xor     edx, edx
0x180038f50  mov     rcx, rbx
0x180038f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038f58  add     rsp, 30h
0x180038f5c  pop     rbx
0x180038f5d  retn
```
