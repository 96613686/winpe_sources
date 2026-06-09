# CWinTaskClassFactoryT<CDrvRecoveryOnRebootHandler,1>::Release(void)

- ea: `0x18000de20`
- end: `0x18000de4f`
- name: `?Release@?$CWinTaskClassFactoryT@VCDrvRecoveryOnRebootHandler@@$00@@UEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000de20`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CDrvRecoveryOnRebootHandler,1>::Release(volatile signed __int32 *a1)
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
0x18000de20  push    rbx
0x18000de22  sub     rsp, 20h
0x18000de26  or      ebx, 0FFFFFFFFh
0x18000de29  lock xadd [rcx+8], ebx
0x18000de2e  sub     ebx, 1
0x18000de31  jnz     short loc_18000DE47
0x18000de33  test    rcx, rcx
0x18000de36  jz      short loc_18000DE47
0x18000de38  mov     rdx, [rcx]
0x18000de3b  mov     rax, [rdx+28h]
0x18000de3f  lea     edx, [rbx+1]
0x18000de42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de47  mov     eax, ebx
0x18000de49  add     rsp, 20h
0x18000de4d  pop     rbx
0x18000de4e  retn
```
