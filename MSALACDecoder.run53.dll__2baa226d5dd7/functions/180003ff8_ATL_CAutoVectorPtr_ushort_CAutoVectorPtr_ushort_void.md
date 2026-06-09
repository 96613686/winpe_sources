# ATL::CAutoVectorPtr<ushort>::~CAutoVectorPtr<ushort>(void)

- ea: `0x180003ff8`
- end: `0x180004016`
- name: `??1?$CAutoVectorPtr@G@ATL@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000a100`
- `0x18000a112`

## callees

- `0x180001144`

## pseudocode

```c
void __fastcall ATL::CAutoVectorPtr<unsigned short>::~CAutoVectorPtr<unsigned short>(void **a1)
{
  operator delete(*a1);
  *a1 = 0;
}

```

## disassembly

```asm
0x180003ff8  push    rbx
0x180003ffa  sub     rsp, 20h
0x180003ffe  mov     rbx, rcx
0x180004001  mov     rcx, [rcx]; Block
0x180004004  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004009  mov     qword ptr [rbx], 0
0x180004010  add     rsp, 20h
0x180004014  pop     rbx
0x180004015  retn
```
