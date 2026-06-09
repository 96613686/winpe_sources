# CCredentials::~CCredentials(void)

- ea: `0x180019590`
- end: `0x1800195b0`
- name: `??1CCredentials@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(CCredentials *__hidden this)`
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x180001c20`
- `0x180001cc0`
- `0x180001dcc`
- `0x180002620`
- `0x1800029e0`
- `0x180003aac`
- `0x180004188`
- `0x1800080a8`
- `0x1800085a0`
- `0x180008900`
- `0x180009240`
- `0x180009350`
- `0x18000cd44`
- `0x18000d524`
- `0x18000fee8`
- `0x1800193c0`

## callees

- `0x180019648`
- `0x18001969c`

## pseudocode

```c
void __fastcall CCredentials::~CCredentials(CCredentials *this)
{
  CCredentials::FreeUserName((unsigned __int16 **)this);
  CCredentials::FreePassword((unsigned __int16 **)this + 1, (unsigned int *)this + 5);
}

```

## disassembly

```asm
0x180019590  push    rbx
0x180019592  sub     rsp, 20h
0x180019596  mov     rbx, rcx
0x180019599  call    ?FreeUserName@CCredentials@@CAXAEAPEAG@Z; CCredentials::FreeUserName(ushort * &)
0x18001959e  lea     rdx, [rbx+14h]; unsigned int *
0x1800195a2  lea     rcx, [rbx+8]; unsigned __int16 **
0x1800195a6  add     rsp, 20h
0x1800195aa  pop     rbx
0x1800195ab  jmp     ?FreePassword@CCredentials@@CAXAEAPEAGAEAK@Z; CCredentials::FreePassword(ushort * &,ulong &)
```
