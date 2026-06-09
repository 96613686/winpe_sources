# wil_details_GetNtDllModuleHandle(void)

- ea: `0x18000fb8c`
- end: `0x18000fbb4`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `40`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180023280`
- `0x180025e58`

## callees

- `0x18000fb8c`
- `0x180016c3e`

## string_xrefs

- `0x18000fb9c`: `ntdll.dll`

## pseudocode

```c
HINSTANCE wil_details_GetNtDllModuleHandle(void)
{
  HINSTANCE result; // rax

  result = (HINSTANCE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    result = GetModuleHandleW_0(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = (__int64)result;
  }
  return result;
}

```

## disassembly

```asm
0x18000fb8c  sub     rsp, 28h
0x18000fb90  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000fb97  test    rax, rax
0x18000fb9a  jnz     short loc_18000FBAF
0x18000fb9c  lea     rcx, ModuleName; "ntdll.dll"
0x18000fba3  call    GetModuleHandleW_0
0x18000fba8  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000fbaf  add     rsp, 28h
0x18000fbb3  retn
```
