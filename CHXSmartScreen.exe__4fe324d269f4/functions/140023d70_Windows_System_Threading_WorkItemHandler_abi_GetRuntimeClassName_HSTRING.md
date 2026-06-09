# Windows::System::Threading::WorkItemHandler::__abi_GetRuntimeClassName(HSTRING__ * *)

- ea: `0x140023d70`
- end: `0x140023d84`
- name: `?__abi_GetRuntimeClassName@WorkItemHandler@Threading@System@Windows@@UE$AAAJPEAPEAUHSTRING__@@@Z`
- size: `20`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140023d90`
- `0x140023da0`

## callees

- `0x140002850`

## string_xrefs

- `0x140023d73`: `Windows.System.Threading.WorkItemHandler`

## pseudocode

```c
HRESULT __fastcall Windows::System::Threading::WorkItemHandler::__abi_GetRuntimeClassName(__int64 a1, HSTRING *a2)
{
  return __winRT::__windowsCreateString(L"Windows.System.Threading.WorkItemHandler", 0x28u, a2);
}

```

## disassembly

```asm
0x140023d70  mov     r8, rdx; string
0x140023d73  lea     rcx, aWindowsSystemT_0; "Windows.System.Threading.WorkItemHandle"...
0x140023d7a  mov     edx, 28h ; '('; length
0x140023d7f  jmp     ?__windowsCreateString@__winRT@@YAJPEB_WHPEAPEAUHSTRING__@@@Z; __winRT::__windowsCreateString(wchar_t const *,int,HSTRING__ * *)
```
