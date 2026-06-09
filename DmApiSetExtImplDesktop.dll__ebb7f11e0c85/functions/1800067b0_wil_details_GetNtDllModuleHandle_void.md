# wil_details_GetNtDllModuleHandle(void)

- ea: `0x1800067b0`
- end: `0x1800067e0`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `48`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800036a0`
- `0x1800067e8`

## callees

- `0x1800067b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800067c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800067c7`

## string_xrefs

- `0x1800067c0`: `ntdll.dll`

## pseudocode

```c
HINSTANCE wil_details_GetNtDllModuleHandle(void)
{
  HINSTANCE result; // rax

  result = (HINSTANCE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    result = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = (__int64)result;
  }
  return result;
}

```

## disassembly

```asm
0x1800067b0  sub     rsp, 28h
0x1800067b4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800067bb  test    rax, rax
0x1800067be  jnz     short loc_1800067DA
0x1800067c0  lea     rcx, ModuleName; "ntdll.dll"
0x1800067c7  call    cs:__imp_GetModuleHandleW
0x1800067ce  nop     dword ptr [rax+rax+00h]
0x1800067d3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800067da  add     rsp, 28h
0x1800067de  retn
```
