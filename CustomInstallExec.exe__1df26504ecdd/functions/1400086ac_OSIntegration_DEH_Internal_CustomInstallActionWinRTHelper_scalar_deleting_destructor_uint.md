# OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::`scalar deleting destructor'(uint)

- ea: `0x1400086ac`
- end: `0x1400086e0`
- name: `??_GCustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@QEAAPEAXI@Z`
- size: `52`
- prototype: `OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper *__fastcall(OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper *this, char)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x140007e9c`
- `0x1400082ec`

## callees

- `0x140003644`
- `0x1400084d0`
- `0x1400086ac`

## pseudocode

```c
OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper *__fastcall OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::`scalar deleting destructor'(
        OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper *this,
        char a2)
{
  OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::~CustomInstallActionWinRTHelper(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1400086ac  mov     [rsp+arg_0], rbx
0x1400086b1  push    rdi
0x1400086b2  sub     rsp, 20h
0x1400086b6  mov     ebx, edx
0x1400086b8  mov     rdi, rcx
0x1400086bb  call    ??1CustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@QEAA@XZ; OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::~CustomInstallActionWinRTHelper(void)
0x1400086c0  test    bl, 1
0x1400086c3  jz      short loc_1400086D2
0x1400086c5  mov     edx, 68h ; 'h'; unsigned __int64
0x1400086ca  mov     rcx, rdi; void *
0x1400086cd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400086d2  mov     rbx, [rsp+28h+arg_0]
0x1400086d7  mov     rax, rdi
0x1400086da  add     rsp, 20h
0x1400086de  pop     rdi
0x1400086df  retn
```
