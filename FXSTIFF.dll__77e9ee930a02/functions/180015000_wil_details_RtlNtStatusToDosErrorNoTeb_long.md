# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180015000`
- end: `0x18001506c`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `108`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180015000`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180015027`
- `KERNEL32!GetModuleHandleW` at `0x180015027`
- `KERNEL32!GetProcAddress` at `0x180015044`
- `KERNEL32!GetProcAddress` at `0x180015044`

## string_xrefs

- `0x180015020`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
FARPROC __fastcall wil::details::RtlNtStatusToDosErrorNoTeb(wil::details *this)
{
  unsigned int v1; // ebx
  FARPROC result; // rax
  HMODULE ModuleHandleW; // rax

  v1 = (unsigned int)this;
  result = (FARPROC)`wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb;
  if ( `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb )
    return (FARPROC)((__int64 (__fastcall *)(_QWORD))result)(v1);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  result = GetProcAddress(ModuleHandleW, "RtlNtStatusToDosErrorNoTeb");
  `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(_QWORD))result)(v1);
  return result;
}

```

## disassembly

```asm
0x180015000  push    rbx
0x180015002  sub     rsp, 20h
0x180015006  mov     ebx, ecx
0x180015008  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18001500f  test    rax, rax
0x180015012  jnz     short loc_18001505D
0x180015014  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001501b  test    rax, rax
0x18001501e  jnz     short loc_18001503A
0x180015020  lea     rcx, ModuleName; "ntdll.dll"
0x180015027  call    cs:__imp_GetModuleHandleW
0x18001502e  nop     dword ptr [rax+rax+00h]
0x180015033  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001503a  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180015041  mov     rcx, rax; hModule
0x180015044  call    cs:__imp_GetProcAddress
0x18001504b  nop     dword ptr [rax+rax+00h]
0x180015050  nop
0x180015051  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180015058  test    rax, rax
0x18001505b  jz      short loc_180015065
0x18001505d  mov     ecx, ebx
0x18001505f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015064  nop
0x180015065  add     rsp, 20h
0x180015069  pop     rbx
0x18001506a  retn
```
