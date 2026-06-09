# CWinTaskHandler::Release(void)

- ea: `0x18000b730`
- end: `0x18000b75f`
- name: `?Release@CWinTaskHandler@@MEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(CWinTaskHandler *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000b730`
- `0x180012010`

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
0x18000b730  push    rbx
0x18000b732  sub     rsp, 20h
0x18000b736  or      ebx, 0FFFFFFFFh
0x18000b739  lock xadd [rcx+20h], ebx
0x18000b73e  sub     ebx, 1
0x18000b741  jnz     short loc_18000B757
0x18000b743  test    rcx, rcx
0x18000b746  jz      short loc_18000B757
0x18000b748  mov     rdx, [rcx]
0x18000b74b  mov     rax, [rdx+38h]
0x18000b74f  lea     edx, [rbx+1]
0x18000b752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b757  mov     eax, ebx
0x18000b759  add     rsp, 20h
0x18000b75d  pop     rbx
0x18000b75e  retn
```
