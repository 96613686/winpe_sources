# _PolicyTaskHelpers::TryDeleteSnapshotCaptureForLoggedInUser_::_1_::catch$21

- ea: `0x1800319af`
- end: `0x1800319e8`
- name: `_PolicyTaskHelpers::TryDeleteSnapshotCaptureForLoggedInUser_::_1_::catch$21`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x18001e298`

## string_xrefs

- `0x1800319c3`: `pcshell\shell\aix\shellconfigtask\lib\..\inc\ShellConfigTaskHelpers.h`

## pseudocode

```c
__int64 __fastcall PolicyTaskHelpers::TryDeleteSnapshotCaptureForLoggedInUser_::_1_::catch_21(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 168),
                           (void *)0x386,
                           (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\..\\inc\\ShellConfigTaskHelpers.h",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800319af  mov     [rsp+arg_8], rdx
0x1800319b4  push    rbp
0x1800319b5  sub     rsp, 20h
0x1800319b9  mov     rbp, rdx
0x1800319bc  mov     rcx, [rbp+0A8h]; this
0x1800319c3  lea     r8, aPcshellShellAi_0; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x1800319ca  mov     edx, 386h; void *
0x1800319cf  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800319d4  mov     [rbp+20h], eax
0x1800319d7  mov     rax, 0
0x1800319e1  add     rsp, 20h
0x1800319e5  pop     rbp
0x1800319e6  retn
```
