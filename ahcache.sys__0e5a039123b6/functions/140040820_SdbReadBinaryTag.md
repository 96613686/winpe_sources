# SdbReadBinaryTag

- ea: `0x140040820`
- end: `0x1400408c0`
- name: `SdbReadBinaryTag`
- size: `160`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x140002d38`
- `0x14002dc6c`
- `0x14002fd64`
- `0x140040730`
- `0x140040c08`

## callees

- `0x14003e1f0`
- `0x14003e364`
- `0x14003ea80`
- `0x140040820`

## string_xrefs

- `0x140040881`: `SdbReadBinaryTag`
- `0x1400408ad`: `SdbReadBinaryTag`
- `0x1400408a0`: `Error reading buffer`

## pseudocode

```c
__int64 __fastcall SdbReadBinaryTag(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  unsigned int v6; // ebx
  unsigned __int16 TagFromTagID; // ax

  v6 = a2;
  if ( (SdbGetTagFromTagID(a1, a2) & 0xF000) == 0x9000 )
  {
    if ( (unsigned int)SdbpReadTagData(a1, v6, a3, a4) )
      return 1;
    AslLogCallPrintf(1, "SdbReadBinaryTag", 1010, "Error reading buffer");
  }
  else
  {
    TagFromTagID = SdbGetTagFromTagID(a1, v6);
    AslLogCallPrintf(1, "SdbReadBinaryTag", 1005, "TagID 0x%08X, Tag %04X not BINARY type", v6, TagFromTagID);
  }
  return 0;
}

```

## disassembly

```asm
0x140040820  push    rbx
0x140040822  push    rbp
0x140040823  push    rsi
0x140040824  push    rdi
0x140040825  sub     rsp, 38h
0x140040829  mov     esi, r9d
0x14004082c  mov     rbp, r8
0x14004082f  mov     ebx, edx
0x140040831  mov     rdi, rcx
0x140040834  call    SdbGetTagFromTagID
0x140040839  mov     ecx, 0F000h
0x14004083e  mov     edx, ebx
0x140040840  and     ax, cx
0x140040843  mov     ecx, 9000h
0x140040848  cmp     ax, cx
0x14004084b  mov     rcx, rdi
0x14004084e  jnz     short loc_14004086E
0x140040850  mov     r9d, esi
0x140040853  mov     r8, rbp
0x140040856  call    SdbpReadTagData
0x14004085b  test    eax, eax
0x14004085d  jz      short loc_1400408A0
0x14004085f  mov     eax, 1
0x140040864  add     rsp, 38h
0x140040868  pop     rdi
0x140040869  pop     rsi
0x14004086a  pop     rbp
0x14004086b  pop     rbx
0x14004086c  retn
0x14004086e  call    SdbGetTagFromTagID
0x140040873  movzx   eax, ax
0x140040876  lea     r9, aTagid0x08xTag0_0; "TagID 0x%08X, Tag %04X not BINARY type"
0x14004087d  mov     [rsp+58h+var_30], eax
0x140040881  lea     rdx, aSdbreadbinaryt_0; "SdbReadBinaryTag"
0x140040888  mov     r8d, 3EDh
0x14004088e  mov     [rsp+58h+var_38], ebx
0x140040892  mov     ecx, 1
0x140040897  call    AslLogCallPrintf
0x14004089c  xor     eax, eax
0x14004089e  jmp     short loc_140040864
0x1400408a0  lea     r9, aErrorReadingBu; "Error reading buffer"
0x1400408a7  mov     r8d, 3F2h
0x1400408ad  lea     rdx, aSdbreadbinaryt_0; "SdbReadBinaryTag"
0x1400408b4  mov     ecx, 1
0x1400408b9  call    AslLogCallPrintf
0x1400408be  jmp     short loc_14004089C
```
