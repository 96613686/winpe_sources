# wil_details_GetNtDllModuleHandle(void)

- ea: `0x180040854`
- end: `0x180040886`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `50`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18003f480`
- `0x18004088c`

## callees

- `0x180040854`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180040874`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180040874`

## string_xrefs

- `0x18004086d`: `ntdll.dll`

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
0x180040854  sub     rsp, 38h
0x180040858  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180040861  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180040868  test    rax, rax
0x18004086b  jnz     short loc_180040881
0x18004086d  lea     rcx, aNtdllDll; "ntdll.dll"
0x180040874  call    cs:__imp_GetModuleHandleW
0x18004087a  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180040881  add     rsp, 38h
0x180040885  retn
```
