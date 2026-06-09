# CWinTaskClassFactoryT<CWofTasksHandler,1>::Release(void)

- ea: `0x180003620`
- end: `0x18000364f`
- name: `?Release@?$CWinTaskClassFactoryT@VCWofTasksHandler@@$00@@UEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180003620`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CWofTasksHandler,1>::Release(volatile signed __int32 *a1)
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
0x180003620  push    rbx
0x180003622  sub     rsp, 20h
0x180003626  or      ebx, 0FFFFFFFFh
0x180003629  lock xadd [rcx+8], ebx
0x18000362e  sub     ebx, 1
0x180003631  jnz     short loc_180003647
0x180003633  test    rcx, rcx
0x180003636  jz      short loc_180003647
0x180003638  mov     rdx, [rcx]
0x18000363b  mov     rax, [rdx+28h]
0x18000363f  lea     edx, [rbx+1]
0x180003642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003647  mov     eax, ebx
0x180003649  add     rsp, 20h
0x18000364d  pop     rbx
0x18000364e  retn
```
