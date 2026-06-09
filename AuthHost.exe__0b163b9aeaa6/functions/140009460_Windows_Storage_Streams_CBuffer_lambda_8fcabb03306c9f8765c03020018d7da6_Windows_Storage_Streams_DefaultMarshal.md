# Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x140009460`
- end: `0x14000947d`
- name: `?GetRuntimeClassName@?$CBuffer@V_lambda_8fcabb03306c9f8765c03020018d7da6_@@UDefaultMarshaler@Streams@Storage@Windows@@@Streams@Storage@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140009476`

## pseudocode

```c
HRESULT __fastcall Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>::GetRuntimeClassName(
        __int64 a1,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Storage.Streams.IBuffer", 0x1Fu, a2);
}

```

## disassembly

```asm
0x140009460  mov     qword ptr [rdx], 0
0x140009467  lea     rcx, aWindowsStorage; "Windows.Storage.Streams.IBuffer"
0x14000946e  mov     r8, rdx
0x140009471  mov     edx, 1Fh
0x140009476  jmp     cs:__imp_WindowsCreateString
```
