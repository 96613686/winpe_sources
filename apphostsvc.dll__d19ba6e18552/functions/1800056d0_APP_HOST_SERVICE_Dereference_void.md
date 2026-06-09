# APP_HOST_SERVICE::Dereference(void)

- ea: `0x1800056d0`
- end: `0x1800056fe`
- name: `?Dereference@APP_HOST_SERVICE@@UEAAXXZ`
- size: `46`
- prototype: `void __fastcall(APP_HOST_SERVICE *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task`

## callees

- `0x180001048`
- `0x180005448`
- `0x1800056d0`

## pseudocode

```c
void __fastcall APP_HOST_SERVICE::Dereference(APP_HOST_SERVICE *this)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 3, 0xFFFFFFFF) == 1 )
  {
    if ( this )
    {
      APP_HOST_SERVICE::~APP_HOST_SERVICE(this);
      operator delete(this);
    }
  }
}

```

## disassembly

```asm
0x1800056d0  push    rbx
0x1800056d2  sub     rsp, 20h
0x1800056d6  mov     rbx, rcx
0x1800056d9  or      eax, 0FFFFFFFFh
0x1800056dc  lock xadd [rcx+0Ch], eax
0x1800056e1  cmp     eax, 1
0x1800056e4  jnz     short loc_1800056F8
0x1800056e6  test    rcx, rcx
0x1800056e9  jz      short loc_1800056F8
0x1800056eb  call    ??1APP_HOST_SERVICE@@QEAA@XZ; APP_HOST_SERVICE::~APP_HOST_SERVICE(void)
0x1800056f0  mov     rcx, rbx; Block
0x1800056f3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800056f8  add     rsp, 20h
0x1800056fc  pop     rbx
0x1800056fd  retn
```
