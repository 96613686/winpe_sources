# CSubCommand::GetState(IShellItemArray *,int,ulong *)

- ea: `0x180008950`
- end: `0x18000895a`
- name: `?GetState@CSubCommand@@UEAAJPEAUIShellItemArray@@HPEAK@Z`
- size: `10`
- prototype: `__int64 __fastcall(CSubCommand *this, struct IShellItemArray *, __int64, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CSubCommand::GetState(CSubCommand *this, struct IShellItemArray *a2, __int64 a3, unsigned int *a4)
{
  *a4 = 0;
  return 0;
}

```

## disassembly

```asm
0x180008950  mov     dword ptr [r9], 0
0x180008957  xor     eax, eax
0x180008959  retn
```
