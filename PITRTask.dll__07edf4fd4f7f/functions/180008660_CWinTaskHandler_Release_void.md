# CWinTaskHandler::Release(void)

- ea: `0x180008660`
- end: `0x18000868f`
- name: `?Release@CWinTaskHandler@@MEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(CWinTaskHandler *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180008660`
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
0x180008660  push    rbx
0x180008662  sub     rsp, 20h
0x180008666  or      ebx, 0FFFFFFFFh
0x180008669  lock xadd [rcx+20h], ebx
0x18000866e  sub     ebx, 1
0x180008671  jnz     short loc_180008687
0x180008673  test    rcx, rcx
0x180008676  jz      short loc_180008687
0x180008678  mov     rdx, [rcx]
0x18000867b  mov     rax, [rdx+38h]
0x18000867f  lea     edx, [rbx+1]
0x180008682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008687  mov     eax, ebx
0x180008689  add     rsp, 20h
0x18000868d  pop     rbx
0x18000868e  retn
```
