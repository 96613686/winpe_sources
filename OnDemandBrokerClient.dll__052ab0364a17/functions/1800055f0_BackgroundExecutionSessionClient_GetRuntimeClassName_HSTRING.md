# BackgroundExecutionSessionClient::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x1800055f0`
- end: `0x18000560a`
- name: `?GetRuntimeClassName@BackgroundExecutionSessionClient@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `26`
- prototype: `HRESULT __fastcall(BackgroundExecutionSessionClient *this, HSTRING *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180005610`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180005603`

## pseudocode

```c
HRESULT __fastcall BackgroundExecutionSessionClient::GetRuntimeClassName(
        BackgroundExecutionSessionClient *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString((PCNZWCH)&dword_180009694, 0, a2);
}

```

## disassembly

```asm
0x1800055f0  mov     qword ptr [rdx], 0
0x1800055f7  lea     rcx, dword_180009694
0x1800055fe  mov     r8, rdx
0x180005601  xor     edx, edx
0x180005603  jmp     cs:__imp_WindowsCreateString
```
