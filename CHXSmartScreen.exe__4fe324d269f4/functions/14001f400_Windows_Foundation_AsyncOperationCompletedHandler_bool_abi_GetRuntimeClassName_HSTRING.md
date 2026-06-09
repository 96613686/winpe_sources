# Windows::Foundation::AsyncOperationCompletedHandler<bool>::__abi_GetRuntimeClassName(HSTRING__ * *)

- ea: `0x14001f400`
- end: `0x14001f414`
- name: `?__abi_GetRuntimeClassName@?$AsyncOperationCompletedHandler@_N@Foundation@Windows@@UE$AAAJPEAPEAUHSTRING__@@@Z`
- size: `20`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001f420`
- `0x14001f430`

## callees

- `0x140002850`

## string_xrefs

- `0x14001f403`: `Windows.Foundation.AsyncOperationCompletedHandler`1<Boolean>`

## pseudocode

```c
HRESULT __fastcall Windows::Foundation::AsyncOperationCompletedHandler<bool>::__abi_GetRuntimeClassName(
        __int64 a1,
        HSTRING *a2)
{
  return __winRT::__windowsCreateString(L"Windows.Foundation.AsyncOperationCompletedHandler`1<Boolean>", 0x3Cu, a2);
}

```

## disassembly

```asm
0x14001f400  mov     r8, rdx; string
0x14001f403  lea     rcx, aWindowsFoundat_2; "Windows.Foundation.AsyncOperationComple"...
0x14001f40a  mov     edx, 3Ch ; '<'; length
0x14001f40f  jmp     ?__windowsCreateString@__winRT@@YAJPEB_WHPEAPEAUHSTRING__@@@Z; __winRT::__windowsCreateString(wchar_t const *,int,HSTRING__ * *)
```
