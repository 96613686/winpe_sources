# CWinTaskHandler::Release(void)

- ea: `0x180002a50`
- end: `0x180002a7f`
- name: `?Release@CWinTaskHandler@@MEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(CWinTaskHandler *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002a50`
- `0x180004010`

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
0x180002a50  push    rbx
0x180002a52  sub     rsp, 20h
0x180002a56  or      ebx, 0FFFFFFFFh
0x180002a59  lock xadd [rcx+20h], ebx
0x180002a5e  sub     ebx, 1
0x180002a61  jnz     short loc_180002A77
0x180002a63  test    rcx, rcx
0x180002a66  jz      short loc_180002A77
0x180002a68  mov     rdx, [rcx]
0x180002a6b  mov     rax, [rdx+38h]
0x180002a6f  lea     edx, [rbx+1]
0x180002a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a77  mov     eax, ebx
0x180002a79  add     rsp, 20h
0x180002a7d  pop     rbx
0x180002a7e  retn
```
