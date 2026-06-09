# __loaddll

- ea: `0x40bb7c`
- end: `0x40bb92`
- name: `__loaddll`
- size: `22`
- prototype: `intptr_t __cdecl(char *FileName)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x408282`

## callees

- `0x40b9d7`

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
0x40bb7c  mov     edi, edi
0x40bb7e  push    ebp
0x40bb7f  mov     ebp, esp
0x40bb81  push    0; enum _crt_exit_return_mode
0x40bb83  push    0; enum _crt_exit_cleanup_mode
0x40bb85  push    [ebp+FileName]; uExitCode
0x40bb88  call    ?common_exit@@YAXHW4_crt_exit_cleanup_mode@@W4_crt_exit_return_mode@@@Z
0x40bb8d  add     esp, 0Ch
0x40bb90  pop     ebp
0x40bb91  retn
```
