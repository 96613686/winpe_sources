# CASFScriptCommandObjectv2::`vector deleting destructor'(uint)

- ea: `0x18000cd00`
- end: `0x18000cd34`
- name: `??_ECASFScriptCommandObjectv2@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(CASFScriptCommandObjectv2 *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000ccf0`

## callees

- `0x1800011c0`
- `0x18000cc88`
- `0x18000cd00`

## pseudocode

```c
CASFScriptCommandObjectv2 *__fastcall CASFScriptCommandObjectv2::`vector deleting destructor'(
        CASFScriptCommandObjectv2 *this,
        char a2)
{
  CASFScriptCommandObjectv2::~CASFScriptCommandObjectv2(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000cd00  mov     [rsp+arg_0], rbx
0x18000cd05  push    rdi
0x18000cd06  sub     rsp, 20h
0x18000cd0a  mov     ebx, edx
0x18000cd0c  mov     rdi, rcx
0x18000cd0f  call    ??1CASFScriptCommandObjectv2@@UEAA@XZ; CASFScriptCommandObjectv2::~CASFScriptCommandObjectv2(void)
0x18000cd14  test    bl, 1
0x18000cd17  jz      short loc_18000CD26
0x18000cd19  mov     edx, 368h
0x18000cd1e  mov     rcx, rdi; Block
0x18000cd21  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000cd26  mov     rbx, [rsp+28h+arg_0]
0x18000cd2b  mov     rax, rdi
0x18000cd2e  add     rsp, 20h
0x18000cd32  pop     rdi
0x18000cd33  retn
```
