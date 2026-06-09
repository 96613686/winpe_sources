# wil::details::BufferOverBlob::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x1800200a0`
- end: `0x1800200bd`
- name: `?GetRuntimeClassName@BufferOverBlob@details@wil@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(wil::details::BufferOverBlob *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800200b6`

## pseudocode

```c
HRESULT __fastcall wil::details::BufferOverBlob::GetRuntimeClassName(wil::details::BufferOverBlob *this, HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Storage.Streams.IBuffer", 0x1Fu, a2);
}

```

## disassembly

```asm
0x1800200a0  mov     qword ptr [rdx], 0
0x1800200a7  lea     rcx, ?InterfaceName_Windows_Storage_Streams_IBuffer@@3QB_WB; "Windows.Storage.Streams.IBuffer"
0x1800200ae  mov     r8, rdx
0x1800200b1  mov     edx, 1Fh
0x1800200b6  jmp     cs:__imp_WindowsCreateString
```
