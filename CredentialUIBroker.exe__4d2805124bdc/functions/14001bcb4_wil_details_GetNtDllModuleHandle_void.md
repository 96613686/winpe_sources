# wil_details_GetNtDllModuleHandle(void)

- ea: `0x14001bcb4`
- end: `0x14001bcdd`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000c600`
- `0x14001bce4`

## callees

- `0x14001bcb4`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14001bccb`
- `KERNEL32!GetModuleHandleW` at `0x14001bccb`

## string_xrefs

- `0x14001bcc4`: `ntdll.dll`

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
0x14001bcb4  sub     rsp, 28h
0x14001bcb8  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14001bcbf  test    rax, rax
0x14001bcc2  jnz     short loc_14001BCD8
0x14001bcc4  lea     rcx, ModuleName; "ntdll.dll"
0x14001bccb  call    cs:__imp_GetModuleHandleW
0x14001bcd1  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14001bcd8  add     rsp, 28h
0x14001bcdc  retn
```
