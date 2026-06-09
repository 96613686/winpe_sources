# ATL::AtlHresultFromWin32(ulong)

- ea: `0x140002db0`
- end: `0x140002dc0`
- name: `?AtlHresultFromWin32@ATL@@YAJK@Z`
- size: `16`
- prototype: `__int64 __fastcall(int)`
- caller_count: `80`
- callee_count: `1`
- tags: ``

## callers

- `0x140003e38`
- `0x1400052f0`
- `0x140005db4`
- `0x140006720`
- `0x140007c90`
- `0x14000860c`
- `0x140008fe4`
- `0x1400094f8`
- `0x14000acac`
- `0x14000aea8`
- `0x14000b0d0`
- `0x14000c8f8`
- `0x14000e6c0`
- `0x140012040`
- `0x14001250c`
- `0x140014fe4`
- `0x1400164c8`
- `0x140016d18`
- `0x14001742c`
- `0x1400188e8`
- `0x140019e70`
- `0x14001a270`
- `0x14001b328`
- `0x14001c094`
- `0x14001cb24`
- `0x14001d058`
- `0x14001da7c`
- `0x14001dbf0`
- `0x14001e2e0`
- `0x14001effc`
- `0x14001f874`
- `0x14001fca0`
- `0x140020390`
- `0x1400211a4`
- `0x140021a28`
- `0x140022878`
- `0x1400237c8`
- `0x140024b60`
- `0x140026e90`
- `0x140027908`
- `0x1400280bc`
- `0x140028848`
- `0x140028e7c`
- `0x140029268`
- `0x140029840`
- `0x140029f6c`
- `0x14002b15c`
- `0x14002beec`
- `0x14002c60c`
- `0x14002d960`

## callees

- `0x140002db0`

## pseudocode

```c
__int64 __fastcall ATL::AtlHresultFromWin32(int a1)
{
  if ( a1 > 0 )
    return (unsigned __int16)a1 | 0x80070000;
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x140002db0  test    ecx, ecx
0x140002db2  jle     short loc_140002DBD
0x140002db4  movzx   ecx, cx
0x140002db7  or      ecx, 80070000h
0x140002dbd  mov     eax, ecx
0x140002dbf  retn
```
