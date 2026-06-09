# CWinTaskHandler::Release(void)

- ea: `0x180007010`
- end: `0x18000703f`
- name: `?Release@CWinTaskHandler@@MEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(CWinTaskHandler *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180007010`
- `0x18000a010`

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
0x180007010  push    rbx
0x180007012  sub     rsp, 20h
0x180007016  or      ebx, 0FFFFFFFFh
0x180007019  lock xadd [rcx+20h], ebx
0x18000701e  sub     ebx, 1
0x180007021  jnz     short loc_180007037
0x180007023  test    rcx, rcx
0x180007026  jz      short loc_180007037
0x180007028  mov     rdx, [rcx]
0x18000702b  mov     rax, [rdx+38h]
0x18000702f  lea     edx, [rbx+1]
0x180007032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007037  mov     eax, ebx
0x180007039  add     rsp, 20h
0x18000703d  pop     rbx
0x18000703e  retn
```
