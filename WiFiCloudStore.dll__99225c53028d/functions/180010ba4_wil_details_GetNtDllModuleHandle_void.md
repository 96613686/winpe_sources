# wil_details_GetNtDllModuleHandle(void)

- ea: `0x180010ba4`
- end: `0x180010bcf`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `43`
- prototype: `HINSTANCE(void)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000f8f0`
- `0x180010864`
- `0x180010890`
- `0x180010b60`
- `0x18002c230`

## callees

- `0x180010ba4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010bc0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010bc0`

## string_xrefs

- `0x180010bb9`: `ntdll.dll`

## pseudocode

```c
HINSTANCE wil_details_GetNtDllModuleHandle(void)
{
  HINSTANCE result; // rax

  result = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    result = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = result;
  }
  return result;
}

```

## disassembly

```asm
0x180010ba4  sub     rsp, 28h
0x180010ba8  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180010baf  test    rax, rax
0x180010bb2  jz      short loc_180010BB9
0x180010bb4  add     rsp, 28h
0x180010bb8  retn
0x180010bb9  lea     rcx, ModuleName; "ntdll.dll"
0x180010bc0  call    cs:__imp_GetModuleHandleW
0x180010bc6  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180010bcd  jmp     short loc_180010BB4
```
