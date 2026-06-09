# Log_HREvent_0

- ea: `0x1800044dc`
- end: `0x1800044f2`
- name: `Log_HREvent_0`
- size: `22`
- prototype: `void __fastcall(__int64, int, char *, __int64)`
- caller_count: `19`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003090`
- `0x180003774`
- `0x180003928`
- `0x180004500`
- `0x180004880`
- `0x180004984`
- `0x180004ad8`
- `0x180004ba0`
- `0x180004c48`
- `0x180004ea0`
- `0x180005030`
- `0x1800051cc`
- `0x180007c48`
- `0x180007d50`
- `0x1800080c8`
- `0x180008168`
- `0x1800088dc`
- `0x180008e54`
- `0x180009120`

## callees

- `0x180006858`
- `0x1800068a8`

## pseudocode

```c
void __fastcall Log_HREvent_0(__int64 a1, int a2, char *a3, __int64 a4)
{
  if ( a2 )
    EventWriteCommsErrorPropagateEvent(a1, a3, (unsigned int)a4, a4);
  else
    EventWriteCommsErrorOriginateEvent(a1, a3, (unsigned int)a4, a4);
}

```

## disassembly

```asm
0x1800044dc  mov     rax, r8
0x1800044df  test    edx, edx
0x1800044e1  mov     rdx, rax; char *
0x1800044e4  mov     r8d, r9d; unsigned int
0x1800044e7  jnz     ?EventWriteCommsErrorPropagateEvent@@YAXJQEBDK@Z; EventWriteCommsErrorPropagateEvent(long,char const * const,ulong)
0x1800044ed  jmp     ?EventWriteCommsErrorOriginateEvent@@YAXJQEBDK@Z; EventWriteCommsErrorOriginateEvent(long,char const * const,ulong)
```
