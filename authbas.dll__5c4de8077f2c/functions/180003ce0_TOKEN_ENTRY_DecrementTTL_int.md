# TOKEN_ENTRY::DecrementTTL(int *)

- ea: `0x180003ce0`
- end: `0x180003cf3`
- name: `?DecrementTTL@TOKEN_ENTRY@@UEAAXPEAH@Z`
- size: `19`
- prototype: `void __fastcall(TOKEN_ENTRY *__hidden this, int *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall TOKEN_ENTRY::DecrementTTL(TOKEN_ENTRY *this, int *a2)
{
  *a2 = _InterlockedAdd((volatile signed __int32 *)this + 64, 0xFFFFFFFF) == 0;
}

```

## disassembly

```asm
0x180003ce0  lock add dword ptr [rcx+100h], 0FFFFFFFFh
0x180003ce8  mov     ecx, 0
0x180003ced  setz    cl
0x180003cf0  mov     [rdx], ecx
0x180003cf2  retn
```
