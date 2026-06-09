# __loaddll

- ea: `0x40ed93`
- end: `0x40eda9`
- name: `__loaddll`
- size: `22`
- prototype: `intptr_t __cdecl(char *FileName)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x40b702`

## callees

- `0x40ebee`

## pseudocode

```c
intptr_t __cdecl _loaddll(char *FileName)
{
  intptr_t result; // eax

  common_exit((UINT)FileName, _crt_exit_full_cleanup, _crt_exit_terminate_process);
  return result;
}

```

## disassembly

```asm
0x40ed93  mov     edi, edi
0x40ed95  push    ebp
0x40ed96  mov     ebp, esp
0x40ed98  push    0; enum _crt_exit_return_mode
0x40ed9a  push    0; enum _crt_exit_cleanup_mode
0x40ed9c  push    [ebp+FileName]; uExitCode
0x40ed9f  call    ?common_exit@@YAXHW4_crt_exit_cleanup_mode@@W4_crt_exit_return_mode@@@Z
0x40eda4  add     esp, 0Ch
0x40eda7  pop     ebp
0x40eda8  retn
```
