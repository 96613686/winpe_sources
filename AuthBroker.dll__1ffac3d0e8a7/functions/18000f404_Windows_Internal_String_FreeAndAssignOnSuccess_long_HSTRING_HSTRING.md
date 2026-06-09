# Windows::Internal::String::FreeAndAssignOnSuccess(long,HSTRING__ *,HSTRING__ * *)

- ea: `0x18000f404`
- end: `0x18000f424`
- name: `?FreeAndAssignOnSuccess@String@Internal@Windows@@CAJJPEAUHSTRING__@@PEAPEAU4@@Z`
- size: `32`
- prototype: `__int64 __fastcall(unsigned int hr, HSTRING__ *newValue, HSTRING__ **target)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800035e0`
- `0x180012b88`
- `0x180016d68`

## callees

- `0x18000f404`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f416`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f416`

## pseudocode

```c
__int64 __fastcall Windows::Internal::String::FreeAndAssignOnSuccess(
        unsigned int hr,
        HSTRING__ *newValue,
        HSTRING__ **target)
{
  HSTRING v4; // rcx

  if ( (hr & 0x80000000) == 0 )
  {
    v4 = *target;
    *target = newValue;
    WindowsDeleteString(v4);
  }
  return hr;
}

```

## disassembly

```asm
0x18000f404  push    rbx
0x18000f406  sub     rsp, 20h
0x18000f40a  mov     ebx, hr
0x18000f40c  test    hr, hr
0x18000f40e  js      short loc_18000F41C
0x18000f410  mov     rcx, [target]; string
0x18000f413  mov     [target], newValue
0x18000f416  call    cs:__imp_WindowsDeleteString
0x18000f41c  mov     eax, ebx
0x18000f41e  add     rsp, 20h
0x18000f422  pop     rbx
0x18000f423  retn
```
