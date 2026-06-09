# CMpeg2StatsCOM::`vector deleting destructor'(uint)

- ea: `0x180011640`
- end: `0x180011674`
- name: `??_ECMpeg2StatsCOM@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(CMpeg2StatsCOM *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001048`
- `0x180010f0c`
- `0x180011640`

## pseudocode

```c
CMpeg2StatsCOM *__fastcall CMpeg2StatsCOM::`vector deleting destructor'(CMpeg2StatsCOM *this, unsigned __int64 a2)
{
  char v2; // bl

  v2 = a2;
  CMpeg2StatsCOM::~CMpeg2StatsCOM(this, a2);
  if ( (v2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180011640  mov     [rsp+arg_0], rbx
0x180011645  push    rdi
0x180011646  sub     rsp, 20h
0x18001164a  mov     ebx, edx
0x18001164c  mov     rdi, rcx
0x18001164f  call    ??1CMpeg2StatsCOM@@UEAA@XZ; CMpeg2StatsCOM::~CMpeg2StatsCOM(void)
0x180011654  test    bl, 1
0x180011657  jz      short loc_180011666
0x180011659  mov     edx, 88h; unsigned __int64
0x18001165e  mov     rcx, rdi; void *
0x180011661  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011666  mov     rbx, [rsp+28h+arg_0]
0x18001166b  mov     rax, rdi
0x18001166e  add     rsp, 20h
0x180011672  pop     rdi
0x180011673  retn
```
