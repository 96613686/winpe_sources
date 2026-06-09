# Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>::`vector deleting destructor'(uint)

- ea: `0x180009d70`
- end: `0x180009dc5`
- name: `??_E?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@UEAAPEAXI@Z`
- size: `85`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800022c0`
- `0x180009d70`
- `0x180011010`

## pseudocode

```c
_QWORD *__fastcall Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>::`vector deleting destructor'(
        _QWORD *a1,
        char a2)
{
  __int64 v4; // rcx

  v4 = a1[2];
  if ( v4 )
  {
    a1[2] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  *((_DWORD *)a1 + 3) = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(a1, (const struct std::nothrow_t *)0x18);
  return a1;
}

```

## disassembly

```asm
0x180009d70  mov     [rsp+arg_0], rbx
0x180009d75  push    rdi
0x180009d76  sub     rsp, 20h
0x180009d7a  mov     edi, edx
0x180009d7c  mov     rbx, rcx
0x180009d7f  mov     rcx, [rcx+10h]
0x180009d83  test    rcx, rcx
0x180009d86  jz      short loc_180009D9D
0x180009d88  mov     qword ptr [rbx+10h], 0
0x180009d90  mov     rax, [rcx]
0x180009d93  mov     rax, [rax+10h]
0x180009d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d9c  nop
0x180009d9d  mov     dword ptr [rbx+0Ch], 0C0000001h
0x180009da4  test    dil, 1
0x180009da8  jz      short loc_180009DB7
0x180009daa  mov     edx, 18h; struct std::nothrow_t *
0x180009daf  mov     rcx, rbx; void *
0x180009db2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009db7  mov     rax, rbx
0x180009dba  mov     rbx, [rsp+28h+arg_0]
0x180009dbf  add     rsp, 20h
0x180009dc3  pop     rdi
0x180009dc4  retn
```
