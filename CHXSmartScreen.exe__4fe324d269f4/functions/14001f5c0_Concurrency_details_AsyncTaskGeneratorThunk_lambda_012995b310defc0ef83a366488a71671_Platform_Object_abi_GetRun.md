# Concurrency::details::_AsyncTaskGeneratorThunk__lambda_012995b310defc0ef83a366488a71671___::[Platform::Object]::__abi_GetRuntimeClassName

- ea: `0x14001f5c0`
- end: `0x14001f5d4`
- name: `Concurrency::details::_AsyncTaskGeneratorThunk__lambda_012995b310defc0ef83a366488a71671___::[Platform::Object]::__abi_GetRuntimeClassName`
- size: `20`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x14001f5e0`
- `0x14001f5f0`
- `0x14001f600`
- `0x14001f610`
- `0x14001f620`
- `0x14001f630`
- `0x14001f640`
- `0x14001f650`
- `0x14001f660`
- `0x14001f680`

## callees

- `0x140002850`

## string_xrefs

- `0x14001f5c3`: `Concurrency.details.?$_AsyncTaskGeneratorThunk@V<lambda_012995b310defc0ef83a366488a71671>@@`

## pseudocode

```c
HRESULT __fastcall Concurrency::details::_AsyncTaskGeneratorThunk__lambda_012995b310defc0ef83a366488a71671___::_Platform::Object_::__abi_GetRuntimeClassName(
        __int64 a1,
        HSTRING *a2)
{
  return __winRT::__windowsCreateString(
           L"Concurrency.details.?$_AsyncTaskGeneratorThunk@V<lambda_012995b310defc0ef83a366488a71671>@@",
           0x5Bu,
           a2);
}

```

## disassembly

```asm
0x14001f5c0  mov     r8, rdx; string
0x14001f5c3  lea     rcx, aConcurrencyDet; "Concurrency.details.?$_AsyncTaskGenerat"...
0x14001f5ca  mov     edx, 5Bh ; '['; length
0x14001f5cf  jmp     ?__windowsCreateString@__winRT@@YAJPEB_WHPEAPEAUHSTRING__@@@Z; __winRT::__windowsCreateString(wchar_t const *,int,HSTRING__ * *)
```
