# CWinTaskHandler::Release(void)

- ea: `0x180003660`
- end: `0x18000368f`
- name: `?Release@CWinTaskHandler@@MEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(CWinTaskHandler *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180003660`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::Release(CWinTaskHandler *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 8);
  if ( !v1 && this )
    (*(void (__fastcall **)(CWinTaskHandler *, __int64))(*(_QWORD *)this + 56LL))(this, 1);
  return v1;
}

```

## disassembly

```asm
0x180003660  push    rbx
0x180003662  sub     rsp, 20h
0x180003666  or      ebx, 0FFFFFFFFh
0x180003669  lock xadd [rcx+20h], ebx
0x18000366e  sub     ebx, 1
0x180003671  jnz     short loc_180003687
0x180003673  test    rcx, rcx
0x180003676  jz      short loc_180003687
0x180003678  mov     rdx, [rcx]
0x18000367b  mov     rax, [rdx+38h]
0x18000367f  lea     edx, [rbx+1]
0x180003682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003687  mov     eax, ebx
0x180003689  add     rsp, 20h
0x18000368d  pop     rbx
0x18000368e  retn
```
