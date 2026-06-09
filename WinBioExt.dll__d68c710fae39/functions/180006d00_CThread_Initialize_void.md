# CThread::Initialize(void)

- ea: `0x180006d00`
- end: `0x180006d12`
- name: `?Initialize@CThread@@SAJXZ`
- size: `18`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006edc`

## pseudocode

```c
__int64 CThread::Initialize(void)
{
  CThread::thread_list(0);
  return 0;
}

```

## disassembly

```asm
0x180006d00  sub     rsp, 28h
0x180006d04  xor     ecx, ecx
0x180006d06  call    ?thread_list@CThread@@CAJPEAV?$locked_pointer@V?$list@PEAVCThread@@V?$allocator@PEAVCThread@@@std@@@std@@@@@Z
0x180006d0b  xor     eax, eax
0x180006d0d  add     rsp, 28h
0x180006d11  retn
```
