# IIsSchema::Release(void)

- ea: `0x18001b5ec`
- end: `0x18001b625`
- name: `?Release@IIsSchema@@QEAAJXZ`
- size: `57`
- prototype: `__int64 __fastcall(IIsSchema *__hidden this)`
- caller_count: `15`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180001dcc`
- `0x1800029e0`
- `0x180003aac`
- `0x180004188`
- `0x18000474c`
- `0x1800080a8`
- `0x180009240`
- `0x180009350`
- `0x180009428`
- `0x18000d524`
- `0x18000fee8`
- `0x180013378`
- `0x18001364c`
- `0x180015664`
- `0x1800193c0`

## callees

- `0x1800010f0`
- `0x180019bbc`
- `0x18001b5ec`

## pseudocode

```c
__int64 __fastcall IIsSchema::Release(IIsSchema *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 22);
  if ( !v2 && this )
  {
    IIsSchema::~IIsSchema(this);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x18001b5ec  mov     [rsp+arg_0], rbx
0x18001b5f1  push    rdi
0x18001b5f2  sub     rsp, 20h
0x18001b5f6  mov     rbx, rcx
0x18001b5f9  or      edi, 0FFFFFFFFh
0x18001b5fc  lock xadd [rcx+58h], edi
0x18001b601  sub     edi, 1
0x18001b604  jnz     short loc_18001B618
0x18001b606  test    rcx, rcx
0x18001b609  jz      short loc_18001B618
0x18001b60b  call    ??1IIsSchema@@AEAA@XZ; IIsSchema::~IIsSchema(void)
0x18001b610  mov     rcx, rbx; Block
0x18001b613  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001b618  mov     rbx, [rsp+28h+arg_0]
0x18001b61d  mov     eax, edi
0x18001b61f  add     rsp, 20h
0x18001b623  pop     rdi
0x18001b624  retn
```
