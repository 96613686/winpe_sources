# SmartPtr<IBackgroundCopyManager>::operator&(void)

- ea: `0x18001e044`
- end: `0x18001e073`
- name: `??I?$SmartPtr@UIBackgroundCopyManager@@@@QEAAPEAPEAUIBackgroundCopyManager@@XZ`
- size: `47`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001e07c`
- `0x18001e154`

## callees

- `0x18001e044`
- `0x180021010`

## pseudocode

```c
_QWORD *__fastcall SmartPtr<IBackgroundCopyManager>::operator&(__int64 a1)
{
  _QWORD *v1; // rbx
  __int64 v2; // rcx

  v1 = (_QWORD *)(a1 + 8);
  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
  {
    *v1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return v1;
}

```

## disassembly

```asm
0x18001e044  push    rbx
0x18001e046  sub     rsp, 20h
0x18001e04a  lea     rbx, [rcx+8]
0x18001e04e  mov     rcx, [rbx]
0x18001e051  test    rcx, rcx
0x18001e054  jz      short loc_18001E069
0x18001e056  mov     qword ptr [rbx], 0
0x18001e05d  mov     rdx, [rcx]
0x18001e060  mov     rax, [rdx+10h]
0x18001e064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e069  mov     rax, rbx
0x18001e06c  add     rsp, 20h
0x18001e070  pop     rbx
0x18001e071  retn
```
