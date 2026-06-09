# CWinTaskHandler::Release(void)

- ea: `0x18002d720`
- end: `0x18002d74f`
- name: `?Release@CWinTaskHandler@@MEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(CWinTaskHandler *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18002d720`
- `0x180037010`

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
0x18002d720  push    rbx
0x18002d722  sub     rsp, 20h
0x18002d726  or      ebx, 0FFFFFFFFh
0x18002d729  lock xadd [rcx+20h], ebx
0x18002d72e  sub     ebx, 1
0x18002d731  jnz     short loc_18002D747
0x18002d733  test    rcx, rcx
0x18002d736  jz      short loc_18002D747
0x18002d738  mov     rdx, [rcx]
0x18002d73b  mov     rax, [rdx+38h]
0x18002d73f  lea     edx, [rbx+1]
0x18002d742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d747  mov     eax, ebx
0x18002d749  add     rsp, 20h
0x18002d74d  pop     rbx
0x18002d74e  retn
```
