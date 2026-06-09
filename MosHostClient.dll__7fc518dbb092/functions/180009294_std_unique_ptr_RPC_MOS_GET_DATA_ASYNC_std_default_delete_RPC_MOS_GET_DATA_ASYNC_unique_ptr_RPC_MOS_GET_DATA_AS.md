# std::unique_ptr<RPC_MOS_GET_DATA_ASYNC,std::default_delete<RPC_MOS_GET_DATA_ASYNC>>::~unique_ptr<RPC_MOS_GET_DATA_ASYNC,std::default_delete<RPC_MOS_GET_DATA_ASYNC>>(void)

- ea: `0x180009294`
- end: `0x1800092d3`
- name: `??1?$unique_ptr@URPC_MOS_GET_DATA_ASYNC@@U?$default_delete@URPC_MOS_GET_DATA_ASYNC@@@std@@@std@@QEAA@XZ`
- size: `63`
- prototype: `void __fastcall(_QWORD **, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800113cb`
- `0x1800114e7`

## callees

- `0x180002534`
- `0x180009294`
- `0x180012010`

## pseudocode

```c
void __fastcall std::unique_ptr<RPC_MOS_GET_DATA_ASYNC>::~unique_ptr<RPC_MOS_GET_DATA_ASYNC>(_QWORD **a1, __int64 a2)
{
  _QWORD *v2; // rbx
  _QWORD *v3; // rcx

  v2 = *a1;
  if ( *a1 )
  {
    v3 = (_QWORD *)v2[7];
    if ( v3 )
    {
      LOBYTE(a2) = v3 != v2;
      (*(void (__fastcall **)(_QWORD *, __int64))(*v3 + 32LL))(v3, a2);
      v2[7] = 0;
    }
    operator delete(v2);
  }
}

```

## disassembly

```asm
0x180009294  push    rbx
0x180009296  sub     rsp, 20h
0x18000929a  mov     rbx, [rcx]
0x18000929d  test    rbx, rbx
0x1800092a0  jz      short loc_1800092CD
0x1800092a2  mov     rcx, [rbx+38h]
0x1800092a6  test    rcx, rcx
0x1800092a9  jz      short loc_1800092C5
0x1800092ab  mov     rax, [rcx]
0x1800092ae  cmp     rcx, rbx
0x1800092b1  setnz   dl
0x1800092b4  mov     rax, [rax+20h]
0x1800092b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092bd  mov     qword ptr [rbx+38h], 0
0x1800092c5  mov     rcx, rbx; Block
0x1800092c8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800092cd  add     rsp, 20h
0x1800092d1  pop     rbx
0x1800092d2  retn
```
