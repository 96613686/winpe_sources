# SessionFrameDecoder::SetSWPowerLevel(ulong)

- ea: `0x1800129e4`
- end: `0x1800129ff`
- name: `?SetSWPowerLevel@SessionFrameDecoder@@QEAAJK@Z`
- size: `27`
- prototype: `__int64 __fastcall(SessionFrameDecoder *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180012580`
- `0x180012e50`
- `0x1800149ac`
- `0x18002a450`

## callees

- `0x1800129e4`

## pseudocode

```c
__int64 __fastcall SessionFrameDecoder::SetSWPowerLevel(SessionFrameDecoder *this, unsigned int a2)
{
  __int64 v2; // rax

  v2 = *((_QWORD *)this + 2);
  if ( !v2 )
    return 0xFFFFFFFFLL;
  if ( a2 <= 0x64 )
    *(_DWORD *)(v2 + 6560) = a2;
  return 0;
}

```

## disassembly

```asm
0x1800129e4  mov     rax, [rcx+10h]
0x1800129e8  test    rax, rax
0x1800129eb  jz      short loc_1800129FB
0x1800129ed  cmp     edx, 64h ; 'd'
0x1800129f0  ja      short loc_1800129F8
0x1800129f2  mov     [rax+19A0h], edx
0x1800129f8  xor     eax, eax
0x1800129fa  retn
0x1800129fb  or      eax, 0FFFFFFFFh
0x1800129fe  retn
```
