# _anonymous_namespace_::ServiceLifetimeManager::_scalar_deleting_destructor_

- ea: `0x140005ae0`
- end: `0x140005b14`
- name: `_anonymous_namespace_::ServiceLifetimeManager::_scalar_deleting_destructor_`
- size: `52`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x140007920`

## callees

- `0x140005a10`
- `0x140005ae0`
- `0x14001382c`

## pseudocode

```c
void *__fastcall anonymous_namespace_::ServiceLifetimeManager::_scalar_deleting_destructor_(void *Block, char a2)
{
  anonymous_namespace_::ServiceLifetimeManager::_ServiceLifetimeManager((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x140005ae0  mov     [rsp+arg_0], rbx
0x140005ae5  push    rdi
0x140005ae6  sub     rsp, 20h
0x140005aea  mov     ebx, edx
0x140005aec  mov     rdi, rcx
0x140005aef  call    _anonymous_namespace___ServiceLifetimeManager___ServiceLifetimeManager
0x140005af4  test    bl, 1
0x140005af7  jz      short loc_140005B06
0x140005af9  mov     edx, 230h
0x140005afe  mov     rcx, rdi; Block
0x140005b01  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140005b06  mov     rbx, [rsp+28h+arg_0]
0x140005b0b  mov     rax, rdi
0x140005b0e  add     rsp, 20h
0x140005b12  pop     rdi
0x140005b13  retn
```
