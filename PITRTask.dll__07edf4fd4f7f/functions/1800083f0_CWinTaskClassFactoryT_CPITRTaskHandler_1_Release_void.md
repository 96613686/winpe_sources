# CWinTaskClassFactoryT<CPITRTaskHandler,1>::Release(void)

- ea: `0x1800083f0`
- end: `0x18000841f`
- name: `?Release@?$CWinTaskClassFactoryT@VCPITRTaskHandler@@$00@@UEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x1800083f0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CPITRTaskHandler,1>::Release(volatile signed __int32 *a1)
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
0x1800083f0  push    rbx
0x1800083f2  sub     rsp, 20h
0x1800083f6  or      ebx, 0FFFFFFFFh
0x1800083f9  lock xadd [rcx+8], ebx
0x1800083fe  sub     ebx, 1
0x180008401  jnz     short loc_180008417
0x180008403  test    rcx, rcx
0x180008406  jz      short loc_180008417
0x180008408  mov     rdx, [rcx]
0x18000840b  mov     rax, [rdx+28h]
0x18000840f  lea     edx, [rbx+1]
0x180008412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008417  mov     eax, ebx
0x180008419  add     rsp, 20h
0x18000841d  pop     rbx
0x18000841e  retn
```
