# CShutdownPopupCommand::get_ID(uint *)

- ea: `0x140009070`
- end: `0x140009078`
- name: `?get_ID@CShutdownPopupCommand@@UEAAJPEAI@Z`
- size: `8`
- prototype: `__int64 __fastcall(CShutdownPopupCommand *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CShutdownPopupCommand::get_ID(CShutdownPopupCommand *this, unsigned int *a2)
{
  *a2 = *((_DWORD *)this + 10);
  return 0;
}

```

## disassembly

```asm
0x140009070  mov     eax, [rcx+28h]
0x140009073  mov     [rdx], eax
0x140009075  xor     eax, eax
0x140009077  retn
```
