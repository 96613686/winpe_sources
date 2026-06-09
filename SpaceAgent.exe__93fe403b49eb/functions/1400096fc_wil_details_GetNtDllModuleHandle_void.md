# wil_details_GetNtDllModuleHandle(void)

- ea: `0x1400096fc`
- end: `0x140009725`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140005500`
- `0x14000972c`

## callees

- `0x1400096fc`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140009713`
- `KERNEL32!GetModuleHandleW` at `0x140009713`

## string_xrefs

- `0x14000970c`: `ntdll.dll`

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
0x1400096fc  sub     rsp, 28h
0x140009700  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009707  test    rax, rax
0x14000970a  jnz     short loc_140009720
0x14000970c  lea     rcx, ModuleName; "ntdll.dll"
0x140009713  call    cs:__imp_GetModuleHandleW
0x140009719  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009720  add     rsp, 28h
0x140009724  retn
```
