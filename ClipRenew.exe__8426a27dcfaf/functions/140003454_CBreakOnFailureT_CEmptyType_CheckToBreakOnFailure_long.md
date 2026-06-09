# CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)

- ea: `0x140003454`
- end: `0x14000346d`
- name: `?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z`
- size: `25`
- prototype: `__int64 __fastcall(int)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x140005524`
- `0x14000678c`
- `0x1400067f4`
- `0x140006924`
- `0x140006ab8`
- `0x1400077fc`
- `0x140007a34`
- `0x140007ae0`
- `0x140007dcc`
- `0x140011354`
- `0x1400113b0`
- `0x1400128a0`
- `0x140012938`
- `0x140012a38`

## callees

- `0x140003454`

## pseudocode

```c
__int64 __fastcall CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(int a1)
{
  __int64 result; // rax

  result = (unsigned int)CBreakOnFailureT<CEmptyType>::g_hResultToBreakOn;
  if ( CBreakOnFailureT<CEmptyType>::g_hResultToBreakOn
    && a1 < 0
    && (CBreakOnFailureT<CEmptyType>::g_hResultToBreakOn == a1 || CBreakOnFailureT<CEmptyType>::g_hResultToBreakOn == -1) )
  {
    __debugbreak();
  }
  return result;
}

```

## disassembly

```asm
0x140003454  mov     eax, cs:?g_hResultToBreakOn@?$CBreakOnFailureT@VCEmptyType@@@@0JA; long CBreakOnFailureT<CEmptyType>::g_hResultToBreakOn
0x14000345a  test    eax, eax
0x14000345c  jz      short locret_14000346C
0x14000345e  test    ecx, ecx
0x140003460  jns     short locret_14000346C
0x140003462  cmp     eax, ecx
0x140003464  jz      short loc_14000346B
0x140003466  cmp     eax, 0FFFFFFFFh
0x140003469  jnz     short locret_14000346C
0x14000346b  int     3; Trap to Debugger
0x14000346c  retn
```
