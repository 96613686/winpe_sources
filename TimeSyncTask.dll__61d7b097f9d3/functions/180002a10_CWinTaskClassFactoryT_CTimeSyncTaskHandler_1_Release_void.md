# CWinTaskClassFactoryT<CTimeSyncTaskHandler,1>::Release(void)

- ea: `0x180002a10`
- end: `0x180002a3f`
- name: `?Release@?$CWinTaskClassFactoryT@VCTimeSyncTaskHandler@@$00@@UEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002a10`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CTimeSyncTaskHandler,1>::Release(volatile signed __int32 *a1)
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
0x180002a10  push    rbx
0x180002a12  sub     rsp, 20h
0x180002a16  or      ebx, 0FFFFFFFFh
0x180002a19  lock xadd [rcx+8], ebx
0x180002a1e  sub     ebx, 1
0x180002a21  jnz     short loc_180002A37
0x180002a23  test    rcx, rcx
0x180002a26  jz      short loc_180002A37
0x180002a28  mov     rdx, [rcx]
0x180002a2b  mov     rax, [rdx+28h]
0x180002a2f  lea     edx, [rbx+1]
0x180002a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a37  mov     eax, ebx
0x180002a39  add     rsp, 20h
0x180002a3d  pop     rbx
0x180002a3e  retn
```
