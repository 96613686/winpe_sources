# CDynamicArray<CReaderReference>::~CDynamicArray<CReaderReference>(void)

- ea: `0x180014dec`
- end: `0x180014e23`
- name: `??1?$CDynamicArray@VCReaderReference@@@@UEAA@XZ`
- size: `55`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180033470`
- `0x1800336c0`
- `0x1800336e0`
- `0x180033700`
- `0x180033b50`
- `0x180033b70`
- `0x180034f5e`

## callees

- `0x180014dec`
- `0x180023168`

## pseudocode

```c
void __fastcall CDynamicArray<CReaderReference>::~CDynamicArray<CReaderReference>(_QWORD *a1)
{
  void *v2; // rcx

  *a1 = &CDynamicArray<CServiceThread>::`vftable';
  v2 = (void *)a1[2];
  if ( v2 )
  {
    operator delete[](v2);
    a1[2] = 0;
    a1[1] = 0;
  }
}

```

## disassembly

```asm
0x180014dec  push    rbx
0x180014dee  sub     rsp, 20h
0x180014df2  lea     rax, ??_7?$CDynamicArray@VCServiceThread@@@@6B@; const CDynamicArray<CServiceThread>::`vftable'
0x180014df9  mov     rbx, rcx
0x180014dfc  mov     [rcx], rax
0x180014dff  mov     rcx, [rcx+10h]; Block
0x180014e03  test    rcx, rcx
0x180014e06  jz      short loc_180014E1D
0x180014e08  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180014e0d  mov     qword ptr [rbx+10h], 0
0x180014e15  mov     qword ptr [rbx+8], 0
0x180014e1d  add     rsp, 20h
0x180014e21  pop     rbx
0x180014e22  retn
```
