# WinApiLite::GetThreadDesktop(ulong)

- ea: `0x180017200`
- end: `0x180017209`
- name: `?GetThreadDesktop@WinApiLite@@UEAAPEAUHDESK__@@K@Z`
- size: `9`
- prototype: `HDESK __fastcall(WinApiLite *this, DWORD)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x180017202`

## pseudocode

```c
HDESK __fastcall WinApiLite::GetThreadDesktop(WinApiLite *this, DWORD a2)
{
  return GetThreadDesktop(a2);
}

```

## disassembly

```asm
0x180017200  mov     ecx, edx
0x180017202  jmp     cs:__imp_GetThreadDesktop
```
