# details::AsyncOperationBase_&launchForActiveCallAsyncName_Windows::Foundation::IAsyncOperation_bool__details::OpInfo_Windows::Foundation::IAsyncOperation_bool_____::GetRuntimeClassName

- ea: `0x18000b640`
- end: `0x18000b65d`
- name: `details::AsyncOperationBase_&launchForActiveCallAsyncName_Windows::Foundation::IAsyncOperation_bool__details::OpInfo_Windows::Foundation::IAsyncOperation_bool_____::GetRuntimeClassName`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000b670`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000b656`

## pseudocode

```c
HRESULT __fastcall details::AsyncOperationBase__launchForActiveCallAsyncName_Windows::Foundation::IAsyncOperation_bool__details::OpInfo_Windows::Foundation::IAsyncOperation_bool_____::GetRuntimeClassName(
        __int64 a1,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Foundation.IAsyncOperation`1<Boolean>", 0x2Du, a2);
}

```

## disassembly

```asm
0x18000b640  mov     qword ptr [rdx], 0
0x18000b647  lea     rcx, aWindowsFoundat; "Windows.Foundation.IAsyncOperation`1<Bo"...
0x18000b64e  mov     r8, rdx
0x18000b651  mov     edx, 2Dh ; '-'
0x18000b656  jmp     cs:__imp_WindowsCreateString
```
