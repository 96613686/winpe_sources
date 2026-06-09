# CWinTaskHandler::Release(void)

- ea: `0x18001abf0`
- end: `0x18001ac1f`
- name: `?Release@CWinTaskHandler@@MEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(CWinTaskHandler *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18001abf0`
- `0x18002a010`

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
0x18001abf0  push    rbx
0x18001abf2  sub     rsp, 20h
0x18001abf6  or      ebx, 0FFFFFFFFh
0x18001abf9  lock xadd [rcx+20h], ebx
0x18001abfe  sub     ebx, 1
0x18001ac01  jnz     short loc_18001AC17
0x18001ac03  test    rcx, rcx
0x18001ac06  jz      short loc_18001AC17
0x18001ac08  mov     rdx, [rcx]
0x18001ac0b  mov     rax, [rdx+38h]
0x18001ac0f  lea     edx, [rbx+1]
0x18001ac12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac17  mov     eax, ebx
0x18001ac19  add     rsp, 20h
0x18001ac1d  pop     rbx
0x18001ac1e  retn
```
