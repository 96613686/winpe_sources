# CRemMdmObj::RemoveModem(ushort *,ulong)

- ea: `0x180005970`
- end: `0x18000597b`
- name: `?RemoveModem@CRemMdmObj@@UEAAJPEAGK@Z`
- size: `11`
- prototype: `__int64 __fastcall(CRemMdmObj *this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001f94`

## pseudocode

```c
__int64 __fastcall CRemMdmObj::RemoveModem(CRemMdmObj *this, unsigned __int16 *a2)
{
  return RemMdmByID(a2);
}

```

## disassembly

```asm
0x180005970  mov     rcx, rdx; lpString2
0x180005973  mov     edx, r8d
0x180005976  jmp     RemMdmByID
```
