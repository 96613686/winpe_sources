# CWinTaskClassFactoryT<CPlutonTasksHandler,1>::Release(void)

- ea: `0x180006fd0`
- end: `0x180006fff`
- name: `?Release@?$CWinTaskClassFactoryT@VCPlutonTasksHandler@@$00@@UEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180006fd0`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CPlutonTasksHandler,1>::Release(volatile signed __int32 *a1)
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
0x180006fd0  push    rbx
0x180006fd2  sub     rsp, 20h
0x180006fd6  or      ebx, 0FFFFFFFFh
0x180006fd9  lock xadd [rcx+8], ebx
0x180006fde  sub     ebx, 1
0x180006fe1  jnz     short loc_180006FF7
0x180006fe3  test    rcx, rcx
0x180006fe6  jz      short loc_180006FF7
0x180006fe8  mov     rdx, [rcx]
0x180006feb  mov     rax, [rdx+28h]
0x180006fef  lea     edx, [rbx+1]
0x180006ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ff7  mov     eax, ebx
0x180006ff9  add     rsp, 20h
0x180006ffd  pop     rbx
0x180006ffe  retn
```
