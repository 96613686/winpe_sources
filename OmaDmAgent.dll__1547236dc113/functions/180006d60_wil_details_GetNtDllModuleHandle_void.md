# wil_details_GetNtDllModuleHandle(void)

- ea: `0x180006d60`
- end: `0x180006d90`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `48`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003620`
- `0x180006d98`

## callees

- `0x180006d60`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180006d77`
- `KERNEL32!GetModuleHandleW` at `0x180006d77`

## string_xrefs

- `0x180006d70`: `ntdll.dll`

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
0x180006d60  sub     rsp, 28h
0x180006d64  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006d6b  test    rax, rax
0x180006d6e  jnz     short loc_180006D8A
0x180006d70  lea     rcx, ModuleName; "ntdll.dll"
0x180006d77  call    cs:__imp_GetModuleHandleW
0x180006d7e  nop     dword ptr [rax+rax+00h]
0x180006d83  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006d8a  add     rsp, 28h
0x180006d8e  retn
```
