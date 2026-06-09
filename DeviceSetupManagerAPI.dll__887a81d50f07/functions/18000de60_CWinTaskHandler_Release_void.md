# CWinTaskHandler::Release(void)

- ea: `0x18000de60`
- end: `0x18000de8f`
- name: `?Release@CWinTaskHandler@@MEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(CWinTaskHandler *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000de60`
- `0x18000f010`

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
0x18000de60  push    rbx
0x18000de62  sub     rsp, 20h
0x18000de66  or      ebx, 0FFFFFFFFh
0x18000de69  lock xadd [rcx+20h], ebx
0x18000de6e  sub     ebx, 1
0x18000de71  jnz     short loc_18000DE87
0x18000de73  test    rcx, rcx
0x18000de76  jz      short loc_18000DE87
0x18000de78  mov     rdx, [rcx]
0x18000de7b  mov     rax, [rdx+38h]
0x18000de7f  lea     edx, [rbx+1]
0x18000de82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de87  mov     eax, ebx
0x18000de89  add     rsp, 20h
0x18000de8d  pop     rbx
0x18000de8e  retn
```
