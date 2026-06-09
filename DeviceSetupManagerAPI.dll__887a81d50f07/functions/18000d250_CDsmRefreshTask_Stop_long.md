# CDsmRefreshTask::Stop(long *)

- ea: `0x18000d250`
- end: `0x18000d259`
- name: `?Stop@CDsmRefreshTask@@UEAAJPEAJ@Z`
- size: `9`
- prototype: `__int64 __fastcall(CDsmRefreshTask *__hidden this, int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
__int64 __fastcall CDsmRefreshTask::Stop(CDsmRefreshTask *this, int *a2)
{
  *a2 = 0;
  return 0;
}

```

## disassembly

```asm
0x18000d250  mov     dword ptr [rdx], 0
0x18000d256  xor     eax, eax
0x18000d258  retn
```
