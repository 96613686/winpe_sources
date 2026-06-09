# Microsoft::WRL::Details::MakeAllocator<TimeUpdate>::~MakeAllocator<TimeUpdate>(void)

- ea: `0x1800053d0`
- end: `0x1800053e6`
- name: `??1?$MakeAllocator@VTimeUpdate@@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180008d7c`

## callees

- `0x180002f78`
- `0x1800053d0`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::MakeAllocator<TimeUpdate>::~MakeAllocator<TimeUpdate>(void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x1800053d0  sub     rsp, 28h
0x1800053d4  mov     rcx, [rcx]; Block
0x1800053d7  test    rcx, rcx
0x1800053da  jz      short loc_1800053E1
0x1800053dc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800053e1  add     rsp, 28h
0x1800053e5  retn
```
