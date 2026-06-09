# OSIntegration::DEH::Internal::CustomInstallAction::~CustomInstallAction(void)

- ea: `0x1400084a0`
- end: `0x1400084c8`
- name: `??1CustomInstallAction@Internal@DEH@OSIntegration@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(OSIntegration::DEH::Internal::CustomInstallAction *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400084d0`

## callees

- `0x14000859c`

## pseudocode

```c
void __fastcall OSIntegration::DEH::Internal::CustomInstallAction::~CustomInstallAction(
        OSIntegration::DEH::Internal::CustomInstallAction *this)
{
  Common::StringBuffer::~StringBuffer((OSIntegration::DEH::Internal::CustomInstallAction *)((char *)this + 48));
  Common::StringBuffer::~StringBuffer((OSIntegration::DEH::Internal::CustomInstallAction *)((char *)this + 24));
  Common::StringBuffer::~StringBuffer(this);
}

```

## disassembly

```asm
0x1400084a0  push    rbx
0x1400084a2  sub     rsp, 20h
0x1400084a6  mov     rbx, rcx
0x1400084a9  add     rcx, 30h ; '0'; this
0x1400084ad  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1400084b2  lea     rcx, [rbx+18h]; this
0x1400084b6  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1400084bb  mov     rcx, rbx; this
0x1400084be  add     rsp, 20h
0x1400084c2  pop     rbx
0x1400084c3  jmp     ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
```
