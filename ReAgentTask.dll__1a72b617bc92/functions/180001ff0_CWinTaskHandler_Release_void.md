# CWinTaskHandler::Release(void)

- ea: `0x180001ff0`
- end: `0x18000201f`
- name: `?Release@CWinTaskHandler@@MEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(CWinTaskHandler *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180001ff0`
- `0x180003010`

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
0x180001ff0  push    rbx
0x180001ff2  sub     rsp, 20h
0x180001ff6  or      ebx, 0FFFFFFFFh
0x180001ff9  lock xadd [rcx+20h], ebx
0x180001ffe  sub     ebx, 1
0x180002001  jnz     short loc_180002017
0x180002003  test    rcx, rcx
0x180002006  jz      short loc_180002017
0x180002008  mov     rdx, [rcx]
0x18000200b  mov     rax, [rdx+38h]
0x18000200f  lea     edx, [rbx+1]
0x180002012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002017  mov     eax, ebx
0x180002019  add     rsp, 20h
0x18000201d  pop     rbx
0x18000201e  retn
```
