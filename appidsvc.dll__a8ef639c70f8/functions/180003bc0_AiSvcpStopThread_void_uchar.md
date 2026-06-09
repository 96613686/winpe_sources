# AiSvcpStopThread(void *,uchar)

- ea: `0x180003bc0`
- end: `0x180003bc7`
- name: `?AiSvcpStopThread@@YAXPEAXE@Z`
- size: `7`
- prototype: `void __fastcall(void *, unsigned __int8)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002d5c`

## pseudocode

```c
void __fastcall AiSvcpStopThread(void *a1)
{
  AiSvcpCleanup(0);
}

```

## disassembly

```asm
0x180003bc0  xor     ecx, ecx; unsigned int
0x180003bc2  jmp     ?AiSvcpCleanup@@YAXK@Z; AiSvcpCleanup(ulong)
```
