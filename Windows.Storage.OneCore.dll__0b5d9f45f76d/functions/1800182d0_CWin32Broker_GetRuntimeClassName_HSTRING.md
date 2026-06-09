# CWin32Broker::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x1800182d0`
- end: `0x1800182ed`
- name: `?GetRuntimeClassName@CWin32Broker@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(CWin32Broker *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800182e6`

## string_xrefs

- `0x1800182d7`: `Windows.Internal.Storage.Win32Broker`

## pseudocode

```c
HRESULT __fastcall CWin32Broker::GetRuntimeClassName(CWin32Broker *this, HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Internal.Storage.Win32Broker", 0x24u, a2);
}

```

## disassembly

```asm
0x1800182d0  mov     qword ptr [rdx], 0
0x1800182d7  lea     rcx, ?RuntimeClass_Windows_Internal_Storage_Win32Broker@@3QBGB; "Windows.Internal.Storage.Win32Broker"
0x1800182de  mov     r8, rdx
0x1800182e1  mov     edx, 24h ; '$'
0x1800182e6  jmp     cs:__imp_WindowsCreateString
```
