# CONFIG_HISTORY::Release(void)

- ea: `0x180003e30`
- end: `0x180003e69`
- name: `?Release@CONFIG_HISTORY@@UEAAKXZ`
- size: `57`
- prototype: `unsigned int __fastcall(CONFIG_HISTORY *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x180001048`
- `0x180002b4c`
- `0x180003e30`

## pseudocode

```c
__int64 __fastcall CONFIG_HISTORY::Release(CONFIG_HISTORY *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 5);
  if ( !v2 && this )
  {
    CONFIG_HISTORY::~CONFIG_HISTORY(this);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x180003e30  mov     [rsp+arg_0], rbx
0x180003e35  push    rdi
0x180003e36  sub     rsp, 20h
0x180003e3a  mov     rbx, rcx
0x180003e3d  or      edi, 0FFFFFFFFh
0x180003e40  lock xadd [rcx+14h], edi
0x180003e45  sub     edi, 1
0x180003e48  jnz     short loc_180003E5C
0x180003e4a  test    rcx, rcx
0x180003e4d  jz      short loc_180003E5C
0x180003e4f  call    ??1CONFIG_HISTORY@@QEAA@XZ; CONFIG_HISTORY::~CONFIG_HISTORY(void)
0x180003e54  mov     rcx, rbx; Block
0x180003e57  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003e5c  mov     rbx, [rsp+28h+arg_0]
0x180003e61  mov     eax, edi
0x180003e63  add     rsp, 20h
0x180003e67  pop     rdi
0x180003e68  retn
```
