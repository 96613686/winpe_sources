# CWinTaskClassFactoryT<PrinterCleanupTask,1>::Release(void)

- ea: `0x180004bc0`
- end: `0x180004bef`
- name: `?Release@?$CWinTaskClassFactoryT@VPrinterCleanupTask@@$00@@UEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180004bc0`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<PrinterCleanupTask,1>::Release(volatile signed __int32 *a1)
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
0x180004bc0  push    rbx
0x180004bc2  sub     rsp, 20h
0x180004bc6  or      ebx, 0FFFFFFFFh
0x180004bc9  lock xadd [rcx+8], ebx
0x180004bce  sub     ebx, 1
0x180004bd1  jnz     short loc_180004BE7
0x180004bd3  test    rcx, rcx
0x180004bd6  jz      short loc_180004BE7
0x180004bd8  mov     rdx, [rcx]
0x180004bdb  mov     rax, [rdx+28h]
0x180004bdf  lea     edx, [rbx+1]
0x180004be2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004be7  mov     eax, ebx
0x180004be9  add     rsp, 20h
0x180004bed  pop     rbx
0x180004bee  retn
```
