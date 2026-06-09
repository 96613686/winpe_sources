# CWinTaskHandler::Release(void)

- ea: `0x180005d40`
- end: `0x180005d6f`
- name: `?Release@CWinTaskHandler@@MEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(CWinTaskHandler *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180005d40`
- `0x180015010`

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
0x180005d40  push    rbx
0x180005d42  sub     rsp, 20h
0x180005d46  or      ebx, 0FFFFFFFFh
0x180005d49  lock xadd [rcx+20h], ebx
0x180005d4e  sub     ebx, 1
0x180005d51  jnz     short loc_180005D67
0x180005d53  test    rcx, rcx
0x180005d56  jz      short loc_180005D67
0x180005d58  mov     rdx, [rcx]
0x180005d5b  mov     rax, [rdx+38h]
0x180005d5f  lea     edx, [rbx+1]
0x180005d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d67  mov     eax, ebx
0x180005d69  add     rsp, 20h
0x180005d6d  pop     rbx
0x180005d6e  retn
```
