# CCommandHandler::GetFlags(ulong *)

- ea: `0x18000aa00`
- end: `0x18000aa09`
- name: `?GetFlags@CCommandHandler@@UEAAJPEAK@Z`
- size: `9`
- prototype: `__int64 __fastcall(CCommandHandler *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## pseudocode

```c
__int64 __fastcall CCommandHandler::GetFlags(CCommandHandler *this, unsigned int *a2)
{
  *a2 = 3;
  return 0;
}

```

## disassembly

```asm
0x18000aa00  mov     dword ptr [rdx], 3
0x18000aa06  xor     eax, eax
0x18000aa08  retn
```
