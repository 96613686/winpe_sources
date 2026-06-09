# __loaddll

- ea: `0x410919`
- end: `0x41092f`
- name: `__loaddll`
- size: `22`
- prototype: `intptr_t __cdecl(char *FileName)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x40d5c2`

## callees

- `0x410774`

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
0x410919  mov     edi, edi
0x41091b  push    ebp
0x41091c  mov     ebp, esp
0x41091e  push    0; enum _crt_exit_return_mode
0x410920  push    0; enum _crt_exit_cleanup_mode
0x410922  push    [ebp+FileName]; uExitCode
0x410925  call    ?common_exit@@YAXHW4_crt_exit_cleanup_mode@@W4_crt_exit_return_mode@@@Z
0x41092a  add     esp, 0Ch
0x41092d  pop     ebp
0x41092e  retn
```
