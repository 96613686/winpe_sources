# InternalNeedReboot(ulong,ushort)

- ea: `0x1800080c8`
- end: `0x1800080e7`
- name: `?InternalNeedReboot@@YAHKG@Z`
- size: `31`
- prototype: `_BOOL8 __fastcall(int, unsigned __int16)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180002450`
- `0x180004880`
- `0x180009c14`
- `0x18000bc50`
- `0x18000bdb0`

## callees

- `0x1800080f0`

## pseudocode

```c
_BOOL8 __fastcall InternalNeedReboot(int a1, unsigned __int16 a2)
{
  return a1 != InternalNeedRebootInit(a2);
}

```

## disassembly

```asm
0x1800080c8  push    rbx
0x1800080ca  sub     rsp, 20h
0x1800080ce  mov     ebx, ecx
0x1800080d0  movzx   ecx, dx; unsigned __int16
0x1800080d3  call    ?InternalNeedRebootInit@@YAKG@Z; InternalNeedRebootInit(ushort)
0x1800080d8  xor     edx, edx
0x1800080da  cmp     ebx, eax
0x1800080dc  setnz   dl
0x1800080df  mov     eax, edx
0x1800080e1  add     rsp, 20h
0x1800080e5  pop     rbx
0x1800080e6  retn
```
