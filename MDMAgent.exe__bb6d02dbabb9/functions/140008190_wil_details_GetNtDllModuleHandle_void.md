# wil_details_GetNtDllModuleHandle(void)

- ea: `0x140008190`
- end: `0x1400081c0`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `48`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400052e0`
- `0x1400081c8`

## callees

- `0x140008190`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400081a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400081a7`

## string_xrefs

- `0x1400081a0`: `ntdll.dll`

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
0x140008190  sub     rsp, 28h
0x140008194  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000819b  test    rax, rax
0x14000819e  jnz     short loc_1400081BA
0x1400081a0  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1400081a7  call    cs:__imp_GetModuleHandleW
0x1400081ae  nop     dword ptr [rax+rax+00h]
0x1400081b3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400081ba  add     rsp, 28h
0x1400081be  retn
```
