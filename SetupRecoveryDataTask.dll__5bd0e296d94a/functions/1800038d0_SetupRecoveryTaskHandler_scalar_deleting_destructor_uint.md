# SetupRecoveryTaskHandler::`scalar deleting destructor'(uint)

- ea: `0x1800038d0`
- end: `0x180003900`
- name: `??_GSetupRecoveryTaskHandler@@UEAAPEAXI@Z`
- size: `48`
- prototype: `SetupRecoveryTaskHandler *__fastcall(SetupRecoveryTaskHandler *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task, installer_update`

## callees

- `0x180003160`
- `0x1800038d0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800038ec`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800038ec`

## pseudocode

```c
SetupRecoveryTaskHandler *__fastcall SetupRecoveryTaskHandler::`scalar deleting destructor'(
        SetupRecoveryTaskHandler *this,
        char a2)
{
  CWinTaskHandler::~CWinTaskHandler(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800038d0  mov     [rsp+arg_0], rbx
0x1800038d5  push    rdi
0x1800038d6  sub     rsp, 20h
0x1800038da  mov     ebx, edx
0x1800038dc  mov     rdi, rcx
0x1800038df  call    ??1CWinTaskHandler@@MEAA@XZ; CWinTaskHandler::~CWinTaskHandler(void)
0x1800038e4  test    bl, 1
0x1800038e7  jz      short loc_1800038F2
0x1800038e9  mov     rcx, rdi
0x1800038ec  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800038f2  mov     rbx, [rsp+28h+arg_0]
0x1800038f7  mov     rax, rdi
0x1800038fa  add     rsp, 20h
0x1800038fe  pop     rdi
0x1800038ff  retn
```
