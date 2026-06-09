# HexDecodeNibble(ushort,uchar &)

- ea: `0x1800046c0`
- end: `0x1800046e7`
- name: `?HexDecodeNibble@@YA_NGAEAE@Z`
- size: `39`
- prototype: `bool __fastcall(__int16, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004160`
- `0x1800044c0`

## callees

- `0x1800046c0`

## pseudocode

```c
bool __fastcall HexDecodeNibble(__int16 a1, unsigned __int8 *a2)
{
  bool result; // al
  unsigned __int16 v3; // cx

  if ( (unsigned __int16)(a1 - 48) >= 0xAu )
  {
    v3 = (a1 | 0x20) - 97;
    if ( v3 >= 6u )
    {
      return 0;
    }
    else
    {
      result = 1;
      *a2 = v3 + 10;
    }
  }
  else
  {
    *a2 = a1 - 48;
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x1800046c0  lea     eax, [rcx-30h]
0x1800046c3  cmp     ax, 0Ah
0x1800046c7  jnb     short loc_1800046CE
0x1800046c9  mov     [rdx], al
0x1800046cb  mov     al, 1
0x1800046cd  retn
0x1800046ce  or      cx, 20h
0x1800046d2  sub     cx, 61h ; 'a'
0x1800046d6  cmp     cx, 6
0x1800046da  jnb     short loc_1800046E4
0x1800046dc  add     cl, 0Ah
0x1800046df  mov     al, 1
0x1800046e1  mov     [rdx], cl
0x1800046e3  retn
0x1800046e4  xor     al, al
0x1800046e6  retn
```
