# av_codec_is_encoder

- ea: `0x180012050`
- end: `0x180012066`
- name: `av_codec_is_encoder`
- size: `22`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180004010`
- `0x1800050a4`
- `0x1800097f0`
- `0x180009880`

## callees

- `0x180012050`

## pseudocode

```c
_BOOL8 __fastcall av_codec_is_encoder(__int64 a1)
{
  _BOOL8 result; // rax

  result = 0;
  if ( a1 )
    return (*(_DWORD *)(a1 + 96) & 0x4000000) == 0;
  return result;
}

```

## disassembly

```asm
0x180012050  xor     eax, eax
0x180012052  test    rcx, rcx
0x180012055  jz      short locret_180012065
0x180012057  test    dword ptr [rcx+60h], 4000000h
0x18001205e  jnz     short locret_180012065
0x180012060  mov     eax, 1
0x180012065  retn
```
