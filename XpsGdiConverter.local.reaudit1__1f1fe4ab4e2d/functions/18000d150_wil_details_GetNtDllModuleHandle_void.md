# wil_details_GetNtDllModuleHandle(void)

- ea: `0x18000d150`
- end: `0x18000d179`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000af40`
- `0x18000d180`

## callees

- `0x18000d150`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000d167`
- `KERNEL32!GetModuleHandleW` at `0x18000d167`

## string_xrefs

- `0x18000d160`: `ntdll.dll`

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
0x18000d150  sub     rsp, 28h
0x18000d154  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d15b  test    rax, rax
0x18000d15e  jnz     short loc_18000D174
0x18000d160  lea     rcx, aNtdllDll; "ntdll.dll"
0x18000d167  call    cs:__imp_GetModuleHandleW
0x18000d16d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d174  add     rsp, 28h
0x18000d178  retn
```
