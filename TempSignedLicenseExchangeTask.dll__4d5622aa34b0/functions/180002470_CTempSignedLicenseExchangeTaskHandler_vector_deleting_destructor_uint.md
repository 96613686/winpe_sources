# CTempSignedLicenseExchangeTaskHandler::`vector deleting destructor'(uint)

- ea: `0x180002470`
- end: `0x1800024a4`
- name: `??_ECTempSignedLicenseExchangeTaskHandler@@UEAAPEAXI@Z`
- size: `52`
- prototype: `CTempSignedLicenseExchangeTaskHandler *__fastcall(CTempSignedLicenseExchangeTaskHandler *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180001424`
- `0x1800023c8`
- `0x180002470`

## pseudocode

```c
CTempSignedLicenseExchangeTaskHandler *__fastcall CTempSignedLicenseExchangeTaskHandler::`vector deleting destructor'(
        CTempSignedLicenseExchangeTaskHandler *this,
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
0x180002470  mov     [rsp+arg_0], rbx
0x180002475  push    rdi
0x180002476  sub     rsp, 20h
0x18000247a  mov     ebx, edx
0x18000247c  mov     rdi, rcx
0x18000247f  call    ??1CWinTaskHandler@@MEAA@XZ; CWinTaskHandler::~CWinTaskHandler(void)
0x180002484  test    bl, 1
0x180002487  jz      short loc_180002496
0x180002489  mov     edx, 38h ; '8'; unsigned __int64
0x18000248e  mov     rcx, rdi; void *
0x180002491  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002496  mov     rbx, [rsp+28h+arg_0]
0x18000249b  mov     rax, rdi
0x18000249e  add     rsp, 20h
0x1800024a2  pop     rdi
0x1800024a3  retn
```
