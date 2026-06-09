# Windows::Internal::ComTaskPool::CTaskWrapper__lambda_1acd6cdd80cddfb63618e898b2901780___::_scalar_deleting_destructor_

- ea: `0x14000c890`
- end: `0x14000c8b8`
- name: `Windows::Internal::ComTaskPool::CTaskWrapper__lambda_1acd6cdd80cddfb63618e898b2901780___::_scalar_deleting_destructor_`
- size: `40`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x140003644`
- `0x14000c890`

## pseudocode

```c
_DWORD *__fastcall Windows::Internal::ComTaskPool::CTaskWrapper__lambda_1acd6cdd80cddfb63618e898b2901780___::_scalar_deleting_destructor_(
        _DWORD *a1,
        char a2)
{
  a1[3] = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x14000c890  push    rbx
0x14000c892  sub     rsp, 20h
0x14000c896  mov     dword ptr [rcx+0Ch], 0C0000001h
0x14000c89d  mov     rbx, rcx
0x14000c8a0  test    dl, 1
0x14000c8a3  jz      short loc_14000C8AF
0x14000c8a5  mov     edx, 28h ; '('; unsigned __int64
0x14000c8aa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000c8af  mov     rax, rbx
0x14000c8b2  add     rsp, 20h
0x14000c8b6  pop     rbx
0x14000c8b7  retn
```
