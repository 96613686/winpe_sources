# __scrt_get_show_window_mode

- ea: `0x14000174c`
- end: `0x140001786`
- name: `__scrt_get_show_window_mode`
- size: `58`
- prototype: `WORD()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001180`

## callees

- `0x140001fb0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x140001768`
- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x140001768`

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
0x14000174c  sub     rsp, 98h
0x140001753  xor     edx, edx; Val
0x140001755  lea     rcx, [rsp+98h+StartupInfo]; void *
0x14000175a  lea     r8d, [rdx+68h]; Size
0x14000175e  call    memset_0
0x140001763  lea     rcx, [rsp+98h+StartupInfo]; lpStartupInfo
0x140001768  call    cs:__imp_GetStartupInfoW
0x14000176e  test    byte ptr [rsp+98h+StartupInfo.dwFlags], 1
0x140001773  mov     eax, 0Ah
0x140001778  cmovnz  ax, [rsp+98h+StartupInfo.wShowWindow]
0x14000177e  add     rsp, 98h
0x140001785  retn
```
