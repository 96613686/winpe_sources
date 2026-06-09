# wil_details_GetNtDllModuleHandle(void)

- ea: `0x14000c600`
- end: `0x14000c629`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140006180`
- `0x14000c630`

## callees

- `0x14000c600`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000c617`
- `KERNEL32!GetModuleHandleW` at `0x14000c617`

## string_xrefs

- `0x14000c610`: `ntdll.dll`

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
0x14000c600  sub     rsp, 28h
0x14000c604  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c60b  test    rax, rax
0x14000c60e  jnz     short loc_14000C624
0x14000c610  lea     rcx, aNtdllDll; "ntdll.dll"
0x14000c617  call    cs:__imp_GetModuleHandleW
0x14000c61d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c624  add     rsp, 28h
0x14000c628  retn
```
