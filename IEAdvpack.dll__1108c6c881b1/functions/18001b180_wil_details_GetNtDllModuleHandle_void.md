# wil_details_GetNtDllModuleHandle(void)

- ea: `0x18001b180`
- end: `0x18001b1a9`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180018e00`
- `0x18001b1b0`

## callees

- `0x18001b180`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18001b197`
- `KERNEL32!GetModuleHandleW` at `0x18001b197`

## string_xrefs

- `0x18001b190`: `ntdll.dll`

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
0x18001b180  sub     rsp, 28h
0x18001b184  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001b18b  test    rax, rax
0x18001b18e  jnz     short loc_18001B1A4
0x18001b190  lea     rcx, ModuleName; "ntdll.dll"
0x18001b197  call    cs:__imp_GetModuleHandleW
0x18001b19d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001b1a4  add     rsp, 28h
0x18001b1a8  retn
```
