# CWinTaskClassFactoryT<CEcoScoreTaskHandler,1>::Release(void)

- ea: `0x180005980`
- end: `0x1800059af`
- name: `?Release@?$CWinTaskClassFactoryT@VCEcoScoreTaskHandler@@$00@@UEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180005980`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CEcoScoreTaskHandler,1>::Release(volatile signed __int32 *a1)
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
0x180005980  push    rbx
0x180005982  sub     rsp, 20h
0x180005986  or      ebx, 0FFFFFFFFh
0x180005989  lock xadd [rcx+8], ebx
0x18000598e  sub     ebx, 1
0x180005991  jnz     short loc_1800059A7
0x180005993  test    rcx, rcx
0x180005996  jz      short loc_1800059A7
0x180005998  mov     rdx, [rcx]
0x18000599b  mov     rax, [rdx+28h]
0x18000599f  lea     edx, [rbx+1]
0x1800059a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059a7  mov     eax, ebx
0x1800059a9  add     rsp, 20h
0x1800059ad  pop     rbx
0x1800059ae  retn
```
