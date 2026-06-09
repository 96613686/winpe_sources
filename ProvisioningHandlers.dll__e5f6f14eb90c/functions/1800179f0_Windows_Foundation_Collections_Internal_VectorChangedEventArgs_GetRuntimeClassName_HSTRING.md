# Windows::Foundation::Collections::Internal::VectorChangedEventArgs::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x1800179f0`
- end: `0x180017a0d`
- name: `?GetRuntimeClassName@VectorChangedEventArgs@Internal@Collections@Foundation@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(Windows::Foundation::Collections::Internal::VectorChangedEventArgs *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180017a06`

## pseudocode

```c
HRESULT __fastcall Windows::Foundation::Collections::Internal::VectorChangedEventArgs::GetRuntimeClassName(
        Windows::Foundation::Collections::Internal::VectorChangedEventArgs *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Foundation.Collections.IVectorChangedEventArgs", 0x36u, a2);
}

```

## disassembly

```asm
0x1800179f0  mov     qword ptr [rdx], 0
0x1800179f7  lea     rcx, aWindowsFoundat_2; "Windows.Foundation.Collections.IVectorC"...
0x1800179fe  mov     r8, rdx
0x180017a01  mov     edx, 36h ; '6'
0x180017a06  jmp     cs:__imp_WindowsCreateString
```
