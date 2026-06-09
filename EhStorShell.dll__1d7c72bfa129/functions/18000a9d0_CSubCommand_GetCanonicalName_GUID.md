# CSubCommand::GetCanonicalName(_GUID *)

- ea: `0x18000a9d0`
- end: `0x18000a9de`
- name: `?GetCanonicalName@CSubCommand@@UEAAJPEAU_GUID@@@Z`
- size: `14`
- prototype: `__int64 __fastcall(CSubCommand *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CSubCommand::GetCanonicalName(CSubCommand *this, struct _GUID *a2)
{
  __int64 result; // rax

  result = 0;
  *a2 = (struct _GUID)xmmword_18000EBD0;
  return result;
}

```

## disassembly

```asm
0x18000a9d0  movups  xmm0, cs:xmmword_18000EBD0
0x18000a9d7  xor     eax, eax
0x18000a9d9  movdqu  xmmword ptr [rdx], xmm0
0x18000a9dd  retn
```
