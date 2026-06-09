# Concurrency::details::_AsyncTaskThunk_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0___::[Platform::Object]::__abi_GetRuntimeClassName

- ea: `0x14001f6a0`
- end: `0x14001f6b4`
- name: `Concurrency::details::_AsyncTaskThunk_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0___::[Platform::Object]::__abi_GetRuntimeClassName`
- size: `20`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x14001f6c0`
- `0x14001f6d0`
- `0x14001f6e0`
- `0x14001f6f0`
- `0x14001f700`
- `0x14001f710`
- `0x14001f720`
- `0x14001f730`

## callees

- `0x140002850`

## string_xrefs

- `0x14001f6a3`: `Concurrency.details.?$_AsyncTaskThunk@U?$_AsyncAttributes@V<lambda_012995b310defc0ef83a366488a71671>@@XXU?$_TaskTypeTraits@X$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@`

## pseudocode

```c
HRESULT __fastcall Concurrency::details::_AsyncTaskThunk_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0___::_Platform::Object_::__abi_GetRuntimeClassName(
        __int64 a1,
        HSTRING *a2)
{
  return __winRT::__windowsCreateString(
           L"Concurrency.details.?$_AsyncTaskThunk@U?$_AsyncAttributes@V<lambda_012995b310defc0ef83a366488a71671>@@XXU?$_T"
            "askTypeTraits@X$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@",
           0xB4u,
           a2);
}

```

## disassembly

```asm
0x14001f6a0  mov     r8, rdx; string
0x14001f6a3  lea     rcx, aConcurrencyDet_0; "Concurrency.details.?$_AsyncTaskThunk@U"...
0x14001f6aa  mov     edx, 0B4h; length
0x14001f6af  jmp     ?__windowsCreateString@__winRT@@YAJPEB_WHPEAPEAUHSTRING__@@@Z; __winRT::__windowsCreateString(wchar_t const *,int,HSTRING__ * *)
```
