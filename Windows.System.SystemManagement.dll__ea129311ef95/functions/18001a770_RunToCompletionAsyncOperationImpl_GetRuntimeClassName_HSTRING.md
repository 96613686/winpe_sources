# RunToCompletionAsyncOperationImpl::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x18001a770`
- end: `0x18001a78d`
- name: `?GetRuntimeClassName@RunToCompletionAsyncOperationImpl@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(RunToCompletionAsyncOperationImpl *__hidden this, HSTRING *)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18001a7a0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001a786`

## pseudocode

```c
HRESULT __fastcall RunToCompletionAsyncOperationImpl::GetRuntimeClassName(
        RunToCompletionAsyncOperationImpl *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Foundation.IAsyncOperation`1<Windows.System.ProcessLauncherResult>", 0x4Au, a2);
}

```

## disassembly

```asm
0x18001a770  mov     qword ptr [rdx], 0
0x18001a777  lea     rcx, aWindowsFoundat_2; "Windows.Foundation.IAsyncOperation`1<Wi"...
0x18001a77e  mov     r8, rdx
0x18001a781  mov     edx, 4Ah ; 'J'
0x18001a786  jmp     cs:__imp_WindowsCreateString
```
