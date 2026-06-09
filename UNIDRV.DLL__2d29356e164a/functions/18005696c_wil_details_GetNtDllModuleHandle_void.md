# wil_details_GetNtDllModuleHandle(void)

- ea: `0x18005696c`
- end: `0x180056995`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180052200`
- `0x18005699c`

## callees

- `0x18005696c`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180056983`
- `KERNEL32!GetModuleHandleW` at `0x180056983`

## string_xrefs

- `0x18005697c`: `ntdll.dll`

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
0x18005696c  sub     rsp, 28h
0x180056970  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180056977  test    rax, rax
0x18005697a  jnz     short loc_180056990
0x18005697c  lea     rcx, aNtdllDll; "ntdll.dll"
0x180056983  call    cs:__imp_GetModuleHandleW
0x180056989  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180056990  add     rsp, 28h
0x180056994  retn
```
