# wil_details_GetNtDllModuleHandle(void)

- ea: `0x140002910`
- end: `0x140002939`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400016b0`
- `0x140002d0c`
- `0x140009760`

## callees

- `0x140002910`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140002927`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140002927`

## string_xrefs

- `0x140002920`: `ntdll.dll`

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
0x140002910  sub     rsp, 28h
0x140002914  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000291b  test    rax, rax
0x14000291e  jnz     short loc_140002934
0x140002920  lea     rcx, ModuleName; "ntdll.dll"
0x140002927  call    cs:__imp_GetModuleHandleW
0x14000292d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140002934  add     rsp, 28h
0x140002938  retn
```
