# __scrt_get_show_window_mode

- ea: `0x140002318`
- end: `0x140002352`
- name: `__scrt_get_show_window_mode`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001ac0`

## callees

- `0x140002352`

## import_xrefs

- `KERNEL32!GetStartupInfoW` at `0x140002334`
- `KERNEL32!GetStartupInfoW` at `0x140002334`

## pseudocode

```c
WORD _scrt_get_show_window_mode()
{
  WORD result; // ax
  _STARTUPINFOW StartupInfo; // [rsp+20h] [rbp-78h] BYREF

  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  GetStartupInfoW(&StartupInfo);
  result = 10;
  if ( (StartupInfo.dwFlags & 1) != 0 )
    return StartupInfo.wShowWindow;
  return result;
}

```

## disassembly

```asm
0x140002318  sub     rsp, 98h
0x14000231f  xor     edx, edx; Val
0x140002321  lea     rcx, [rsp+98h+StartupInfo]; void *
0x140002326  lea     r8d, [rdx+68h]; Size
0x14000232a  call    memset_0
0x14000232f  lea     rcx, [rsp+98h+StartupInfo]; lpStartupInfo
0x140002334  call    cs:__imp_GetStartupInfoW
0x14000233a  test    byte ptr [rsp+98h+StartupInfo.dwFlags], 1
0x14000233f  mov     eax, 0Ah
0x140002344  cmovnz  ax, [rsp+98h+StartupInfo.wShowWindow]
0x14000234a  add     rsp, 98h
0x140002351  retn
```
