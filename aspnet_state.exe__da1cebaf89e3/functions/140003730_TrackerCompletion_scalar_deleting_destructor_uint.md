# TrackerCompletion::`scalar deleting destructor'(uint)

- ea: `0x140003730`
- end: `0x140003772`
- name: `??_GTrackerCompletion@@UEAAPEAXI@Z`
- size: `66`
- prototype: `struct IUnknown **__fastcall(struct IUnknown **this, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140001390`
- `0x14000366c`
- `0x140003730`
- `0x140004fc8`

## pseudocode

```c
struct IUnknown **__fastcall TrackerCompletion::`scalar deleting destructor'(struct IUnknown **this, char a2)
{
  TrackerCompletion::~TrackerCompletion(this);
  if ( (a2 & 1) != 0 )
  {
    if ( (a2 & 4) != 0 )
      __global_delete(this, 0x40u);
    else
      MemFree(this);
  }
  return this;
}

```

## disassembly

```asm
0x140003730  mov     [rsp+arg_0], rbx
0x140003735  push    rdi
0x140003736  sub     rsp, 20h
0x14000373a  mov     edi, edx
0x14000373c  mov     rbx, rcx
0x14000373f  call    ??1TrackerCompletion@@UEAA@XZ; TrackerCompletion::~TrackerCompletion(void)
0x140003744  test    dil, 1
0x140003748  jz      short loc_140003764
0x14000374a  mov     rcx, rbx; void *
0x14000374d  test    dil, 4
0x140003751  jnz     short loc_14000375A
0x140003753  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x140003758  jmp     short loc_140003764
0x14000375a  mov     edx, 40h ; '@'; unsigned __int64
0x14000375f  call    ?__global_delete@@YAXPEAX_K@Z; __global_delete(void *,unsigned __int64)
0x140003764  mov     rax, rbx
0x140003767  mov     rbx, [rsp+28h+arg_0]
0x14000376c  add     rsp, 20h
0x140003770  pop     rdi
0x140003771  retn
```
