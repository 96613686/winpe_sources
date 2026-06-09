# CWinTaskClassFactoryT<CDeferredChargingTaskHandler,1>::Release(void)

- ea: `0x18002d430`
- end: `0x18002d45f`
- name: `?Release@?$CWinTaskClassFactoryT@VCDeferredChargingTaskHandler@@$00@@UEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18002d430`
- `0x180037010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CDeferredChargingTaskHandler,1>::Release(volatile signed __int32 *a1)
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
0x18002d430  push    rbx
0x18002d432  sub     rsp, 20h
0x18002d436  or      ebx, 0FFFFFFFFh
0x18002d439  lock xadd [rcx+8], ebx
0x18002d43e  sub     ebx, 1
0x18002d441  jnz     short loc_18002D457
0x18002d443  test    rcx, rcx
0x18002d446  jz      short loc_18002D457
0x18002d448  mov     rdx, [rcx]
0x18002d44b  mov     rax, [rdx+28h]
0x18002d44f  lea     edx, [rbx+1]
0x18002d452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d457  mov     eax, ebx
0x18002d459  add     rsp, 20h
0x18002d45d  pop     rbx
0x18002d45e  retn
```
