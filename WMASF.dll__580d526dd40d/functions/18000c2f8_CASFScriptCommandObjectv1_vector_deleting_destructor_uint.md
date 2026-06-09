# CASFScriptCommandObjectv1::`vector deleting destructor'(uint)

- ea: `0x18000c2f8`
- end: `0x18000c32c`
- name: `??_ECASFScriptCommandObjectv1@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(CASFScriptCommandObjectv1 *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000c270`

## callees

- `0x1800011c0`
- `0x18000c208`
- `0x18000c2f8`

## pseudocode

```c
CASFScriptCommandObjectv1 *__fastcall CASFScriptCommandObjectv1::`vector deleting destructor'(
        CASFScriptCommandObjectv1 *this,
        char a2)
{
  CASFScriptCommandObjectv1::~CASFScriptCommandObjectv1(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000c2f8  mov     [rsp+arg_0], rbx
0x18000c2fd  push    rdi
0x18000c2fe  sub     rsp, 20h
0x18000c302  mov     ebx, edx
0x18000c304  mov     rdi, rcx
0x18000c307  call    ??1CASFScriptCommandObjectv1@@UEAA@XZ; CASFScriptCommandObjectv1::~CASFScriptCommandObjectv1(void)
0x18000c30c  test    bl, 1
0x18000c30f  jz      short loc_18000C31E
0x18000c311  mov     edx, 368h
0x18000c316  mov     rcx, rdi; Block
0x18000c319  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c31e  mov     rbx, [rsp+28h+arg_0]
0x18000c323  mov     rax, rdi
0x18000c326  add     rsp, 20h
0x18000c32a  pop     rdi
0x18000c32b  retn
```
