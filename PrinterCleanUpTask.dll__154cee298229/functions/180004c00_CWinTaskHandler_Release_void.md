# CWinTaskHandler::Release(void)

- ea: `0x180004c00`
- end: `0x180004c2f`
- name: `?Release@CWinTaskHandler@@MEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(CWinTaskHandler *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180004c00`
- `0x180018010`

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
0x180004c00  push    rbx
0x180004c02  sub     rsp, 20h
0x180004c06  or      ebx, 0FFFFFFFFh
0x180004c09  lock xadd [rcx+20h], ebx
0x180004c0e  sub     ebx, 1
0x180004c11  jnz     short loc_180004C27
0x180004c13  test    rcx, rcx
0x180004c16  jz      short loc_180004C27
0x180004c18  mov     rdx, [rcx]
0x180004c1b  mov     rax, [rdx+38h]
0x180004c1f  lea     edx, [rbx+1]
0x180004c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c27  mov     eax, ebx
0x180004c29  add     rsp, 20h
0x180004c2d  pop     rbx
0x180004c2e  retn
```
