# CWinTaskHandler::Release(void)

- ea: `0x180008570`
- end: `0x18000859f`
- name: `?Release@CWinTaskHandler@@MEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(CWinTaskHandler *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180008570`
- `0x18000d010`

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
0x180008570  push    rbx
0x180008572  sub     rsp, 20h
0x180008576  or      ebx, 0FFFFFFFFh
0x180008579  lock xadd [rcx+20h], ebx
0x18000857e  sub     ebx, 1
0x180008581  jnz     short loc_180008597
0x180008583  test    rcx, rcx
0x180008586  jz      short loc_180008597
0x180008588  mov     rdx, [rcx]
0x18000858b  mov     rax, [rdx+38h]
0x18000858f  lea     edx, [rbx+1]
0x180008592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008597  mov     eax, ebx
0x180008599  add     rsp, 20h
0x18000859d  pop     rbx
0x18000859e  retn
```
