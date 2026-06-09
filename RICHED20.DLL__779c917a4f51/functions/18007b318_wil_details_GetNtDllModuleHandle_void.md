# wil_details_GetNtDllModuleHandle(void)

- ea: `0x18007b318`
- end: `0x18007b341`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180076e00`
- `0x18007b348`

## callees

- `0x18007b318`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18007b32f`
- `KERNEL32!GetModuleHandleW` at `0x18007b32f`

## string_xrefs

- `0x18007b328`: `ntdll.dll`

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
0x18007b318  sub     rsp, 28h
0x18007b31c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18007b323  test    rax, rax
0x18007b326  jnz     short loc_18007B33C
0x18007b328  lea     rcx, ModuleName; "ntdll.dll"
0x18007b32f  call    cs:__imp_GetModuleHandleW
0x18007b335  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18007b33c  add     rsp, 28h
0x18007b340  retn
```
