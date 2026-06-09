# CSubCommand::GetFlags(ulong *)

- ea: `0x18000aa10`
- end: `0x18000aa19`
- name: `?GetFlags@CSubCommand@@UEAAJPEAK@Z`
- size: `9`
- prototype: `__int64 __fastcall(CSubCommand *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CSubCommand::GetFlags(CSubCommand *this, unsigned int *a2)
{
  *a2 = 0;
  return 0;
}

```

## disassembly

```asm
0x18000aa10  mov     dword ptr [rdx], 0
0x18000aa16  xor     eax, eax
0x18000aa18  retn
```
