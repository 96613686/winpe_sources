# CWinTaskClassFactoryT<SetupRecoveryTaskHandler,1>::Release(void)

- ea: `0x180008300`
- end: `0x18000832f`
- name: `?Release@?$CWinTaskClassFactoryT@VSetupRecoveryTaskHandler@@$00@@UEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x180008300`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<SetupRecoveryTaskHandler,1>::Release(volatile signed __int32 *a1)
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
0x180008300  push    rbx
0x180008302  sub     rsp, 20h
0x180008306  or      ebx, 0FFFFFFFFh
0x180008309  lock xadd [rcx+8], ebx
0x18000830e  sub     ebx, 1
0x180008311  jnz     short loc_180008327
0x180008313  test    rcx, rcx
0x180008316  jz      short loc_180008327
0x180008318  mov     rdx, [rcx]
0x18000831b  mov     rax, [rdx+28h]
0x18000831f  lea     edx, [rbx+1]
0x180008322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008327  mov     eax, ebx
0x180008329  add     rsp, 20h
0x18000832d  pop     rbx
0x18000832e  retn
```
