# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x14000bfc0`
- end: `0x14000c022`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `98`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x14000bfc0`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000bfe7`
- `KERNEL32!GetModuleHandleW` at `0x14000bfe7`
- `KERNEL32!GetProcAddress` at `0x14000bffe`
- `KERNEL32!GetProcAddress` at `0x14000bffe`

## string_xrefs

- `0x14000bfe0`: `ntdll.dll`

## pseudocode

```c
FARPROC __fastcall wil::details::RtlNtStatusToDosErrorNoTeb(wil::details *this)
{
  FARPROC result; // rax
  unsigned int v2; // ebx
  HMODULE ModuleHandleW; // rax

  result = (FARPROC)`wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb;
  v2 = (unsigned int)this;
  if ( `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb )
    return (FARPROC)((__int64 (__fastcall *)(_QWORD))result)(v2);
  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  result = GetProcAddress(ModuleHandleW, "RtlNtStatusToDosErrorNoTeb");
  `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(_QWORD))result)(v2);
  return result;
}

```

## disassembly

```asm
0x14000bfc0  push    rbx
0x14000bfc2  sub     rsp, 20h
0x14000bfc6  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x14000bfcd  mov     ebx, ecx
0x14000bfcf  test    rax, rax
0x14000bfd2  jnz     short loc_14000C016
0x14000bfd4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000bfdb  test    rax, rax
0x14000bfde  jnz     short loc_14000BFF4
0x14000bfe0  lea     rcx, ModuleName; "ntdll.dll"
0x14000bfe7  call    cs:__imp_GetModuleHandleW
0x14000bfed  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000bff4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x14000bffb  mov     rcx, rax; hModule
0x14000bffe  call    cs:__imp_GetProcAddress
0x14000c004  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x14000c00b  test    rax, rax
0x14000c00e  jnz     short loc_14000C016
0x14000c010  add     rsp, 20h
0x14000c014  pop     rbx
0x14000c015  retn
0x14000c016  mov     ecx, ebx
0x14000c018  add     rsp, 20h
0x14000c01c  pop     rbx
0x14000c01d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
