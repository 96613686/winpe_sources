# CWinTaskClassFactoryT<CReAgentTaskHandler,1>::Release(void)

- ea: `0x180001fb0`
- end: `0x180001fdf`
- name: `?Release@?$CWinTaskClassFactoryT@VCReAgentTaskHandler@@$00@@UEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180001fb0`
- `0x180003010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CReAgentTaskHandler,1>::Release(volatile signed __int32 *a1)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement(a1 + 2);
  if ( !v1 && a1 )
    (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)a1 + 40LL))(a1, 1);
  return v1;
}

```

## disassembly

```asm
0x180001fb0  push    rbx
0x180001fb2  sub     rsp, 20h
0x180001fb6  or      ebx, 0FFFFFFFFh
0x180001fb9  lock xadd [rcx+8], ebx
0x180001fbe  sub     ebx, 1
0x180001fc1  jnz     short loc_180001FD7
0x180001fc3  test    rcx, rcx
0x180001fc6  jz      short loc_180001FD7
0x180001fc8  mov     rdx, [rcx]
0x180001fcb  mov     rax, [rdx+28h]
0x180001fcf  lea     edx, [rbx+1]
0x180001fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fd7  mov     eax, ebx
0x180001fd9  add     rsp, 20h
0x180001fdd  pop     rbx
0x180001fde  retn
```
