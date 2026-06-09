# TimeUpdate::`scalar deleting destructor'(uint)

- ea: `0x180005bc0`
- end: `0x180005bf4`
- name: `??_GTimeUpdate@@UEAAPEAXI@Z`
- size: `52`
- prototype: `TimeUpdate *__fastcall(TimeUpdate *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callees

- `0x180002f84`
- `0x18000591c`
- `0x180005bc0`

## pseudocode

```c
TimeUpdate *__fastcall TimeUpdate::`scalar deleting destructor'(TimeUpdate *this, char a2)
{
  TimeUpdate::~TimeUpdate(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180005bc0  mov     [rsp+arg_0], rbx
0x180005bc5  push    rdi
0x180005bc6  sub     rsp, 20h
0x180005bca  mov     ebx, edx
0x180005bcc  mov     rdi, rcx
0x180005bcf  call    ??1TimeUpdate@@UEAA@XZ; TimeUpdate::~TimeUpdate(void)
0x180005bd4  test    bl, 1
0x180005bd7  jz      short loc_180005BE6
0x180005bd9  mov     edx, 288h
0x180005bde  mov     rcx, rdi; Block
0x180005be1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005be6  mov     rbx, [rsp+28h+arg_0]
0x180005beb  mov     rax, rdi
0x180005bee  add     rsp, 20h
0x180005bf2  pop     rdi
0x180005bf3  retn
```
