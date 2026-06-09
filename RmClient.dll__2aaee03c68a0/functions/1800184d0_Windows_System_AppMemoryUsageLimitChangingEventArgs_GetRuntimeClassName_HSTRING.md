# Windows::System::AppMemoryUsageLimitChangingEventArgs::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x1800184d0`
- end: `0x1800184ed`
- name: `?GetRuntimeClassName@AppMemoryUsageLimitChangingEventArgs@System@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `HRESULT __fastcall(Windows::System::AppMemoryUsageLimitChangingEventArgs *this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800184e6`

## pseudocode

```c
HRESULT __fastcall Windows::System::AppMemoryUsageLimitChangingEventArgs::GetRuntimeClassName(
        Windows::System::AppMemoryUsageLimitChangingEventArgs *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.System.AppMemoryUsageLimitChangingEventArgs", 0x33u, a2);
}

```

## disassembly

```asm
0x1800184d0  mov     qword ptr [rdx], 0
0x1800184d7  lea     rcx, ?RuntimeClass_Windows_System_AppMemoryUsageLimitChangingEventArgs@@3QBGB; "Windows.System.AppMemoryUsageLimitChang"...
0x1800184de  mov     r8, rdx
0x1800184e1  mov     edx, 33h ; '3'
0x1800184e6  jmp     cs:__imp_WindowsCreateString
```
