# Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>::`vector deleting destructor'(uint)

- ea: `0x180007ad0`
- end: `0x180007b1f`
- name: `??_E?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@UEAAPEAXI@Z`
- size: `79`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001984`
- `0x180007ad0`
- `0x180019010`

## pseudocode

```c
_QWORD *__fastcall Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>::`vector deleting destructor'(
        _QWORD *Block,
        char a2)
{
  __int64 v4; // rcx

  v4 = Block[2];
  if ( v4 )
  {
    Block[2] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  *((_DWORD *)Block + 3) = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180007ad0  mov     [rsp+arg_0], rbx
0x180007ad5  push    rdi
0x180007ad6  sub     rsp, 20h
0x180007ada  mov     rbx, rcx
0x180007add  mov     edi, edx
0x180007adf  mov     rcx, [rcx+10h]
0x180007ae3  test    rcx, rcx
0x180007ae6  jz      short loc_180007AFC
0x180007ae8  mov     qword ptr [rbx+10h], 0
0x180007af0  mov     rax, [rcx]
0x180007af3  mov     rax, [rax+10h]
0x180007af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007afc  mov     dword ptr [rbx+0Ch], 0C0000001h
0x180007b03  test    dil, 1
0x180007b07  jz      short loc_180007B11
0x180007b09  mov     rcx, rbx; Block
0x180007b0c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007b11  mov     rax, rbx
0x180007b14  mov     rbx, [rsp+28h+arg_0]
0x180007b19  add     rsp, 20h
0x180007b1d  pop     rdi
0x180007b1e  retn
```
