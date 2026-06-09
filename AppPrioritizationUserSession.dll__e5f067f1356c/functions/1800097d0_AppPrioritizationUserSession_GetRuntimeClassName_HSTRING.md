# AppPrioritizationUserSession::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x1800097d0`
- end: `0x1800097ed`
- name: `?GetRuntimeClassName@AppPrioritizationUserSession@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(AppPrioritizationUserSession *__hidden this, HSTRING *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180009800`
- `0x180009810`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800097e6`

## pseudocode

```c
HRESULT __fastcall AppPrioritizationUserSession::GetRuntimeClassName(AppPrioritizationUserSession *this, HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"AppPrioritizationUserSession", 0x1Cu, a2);
}

```

## disassembly

```asm
0x1800097d0  mov     qword ptr [rdx], 0
0x1800097d7  lea     rcx, aAppprioritizat_0; "AppPrioritizationUserSession"
0x1800097de  mov     r8, rdx
0x1800097e1  mov     edx, 1Ch
0x1800097e6  jmp     cs:__imp_WindowsCreateString
```
