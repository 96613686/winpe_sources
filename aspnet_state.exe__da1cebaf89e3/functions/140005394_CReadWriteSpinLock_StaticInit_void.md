# CReadWriteSpinLock::StaticInit(void)

- ea: `0x140005394`
- end: `0x1400053b5`
- name: `?StaticInit@CReadWriteSpinLock@@SAHXZ`
- size: `33`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001070`

## callees

- `0x1400057b0`

## pseudocode

```c
__int64 CReadWriteSpinLock::StaticInit(void)
{
  bool v0; // zf
  __int64 result; // rax

  v0 = GetCurrentProcessCpuCount() == 1;
  result = 1;
  CReadWriteSpinLock::s_disableBusyWaiting = v0;
  return result;
}

```

## disassembly

```asm
0x140005394  sub     rsp, 28h
0x140005398  call    ?GetCurrentProcessCpuCount@@YAKXZ; GetCurrentProcessCpuCount(void)
0x14000539d  xor     ecx, ecx
0x14000539f  cmp     eax, 1
0x1400053a2  mov     eax, 1
0x1400053a7  setz    cl
0x1400053aa  mov     cs:?s_disableBusyWaiting@CReadWriteSpinLock@@0HA, ecx; int CReadWriteSpinLock::s_disableBusyWaiting
0x1400053b0  add     rsp, 28h
0x1400053b4  retn
```
