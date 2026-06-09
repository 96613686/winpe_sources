# mp3decClose

- ea: `0x18000e244`
- end: `0x18000e25d`
- name: `mp3decClose`
- size: `25`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a1d0`
- `0x18000be78`
- `0x18000d8d0`

## callees

- `0x18000e264`

## pseudocode

```c
__int64 __fastcall mp3decClose(void *a1)
{
  return DeleteHandle(a1) == 0 ? 0xC0000003 : 0;
}

```

## disassembly

```asm
0x18000e244  sub     rsp, 28h
0x18000e248  call    DeleteHandle
0x18000e24d  neg     al
0x18000e24f  sbb     eax, eax
0x18000e251  not     eax
0x18000e253  and     eax, 0C0000003h
0x18000e258  add     rsp, 28h
0x18000e25c  retn
```
