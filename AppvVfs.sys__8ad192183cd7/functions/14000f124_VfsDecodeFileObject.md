# VfsDecodeFileObject

- ea: `0x14000f124`
- end: `0x14000f180`
- name: `VfsDecodeFileObject`
- size: `92`
- prototype: `char __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `22`
- callee_count: `1`
- tags: ``

## callers

- `0x1400010e0`
- `0x1400011c0`
- `0x140001380`
- `0x140001530`
- `0x140001690`
- `0x1400017e0`
- `0x140003c00`
- `0x14000414c`
- `0x140005c50`
- `0x140007c7c`
- `0x14000a3c0`
- `0x14000a5a0`
- `0x14000aa90`
- `0x14000ab10`
- `0x14000aca0`
- `0x14000ad00`
- `0x14000ad70`
- `0x14000ade0`
- `0x14000ae70`
- `0x14000c100`
- `0x14000c1b4`
- `0x14000f058`

## callees

- `0x14000f124`

## pseudocode

```c
char __fastcall VfsDecodeFileObject(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  char result; // al
  _WORD *v4; // r9
  _WORD *v5; // r10

  result = 0;
  if ( a1 )
  {
    v4 = *(_WORD **)(a1 + 24);
    if ( v4 )
    {
      if ( *v4 == 5766 )
      {
        v5 = *(_WORD **)(a1 + 32);
        if ( v5 )
        {
          if ( *v5 == 5767 )
          {
            if ( a2 )
              *a2 = v4;
            if ( a3 )
              *a3 = *(_QWORD *)(a1 + 32);
            return 1;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000f124  sub     rsp, 18h
0x14000f128  xor     al, al
0x14000f12a  mov     [rsp+18h+var_18], al
0x14000f12d  test    rcx, rcx
0x14000f130  jz      short loc_14000F17A
0x14000f132  mov     r9, [rcx+18h]
0x14000f136  test    r9, r9
0x14000f139  jz      short loc_14000F17A
0x14000f13b  mov     r10d, 1686h
0x14000f141  cmp     [r9], r10w
0x14000f145  jnz     short loc_14000F175
0x14000f147  mov     r10, [rcx+20h]
0x14000f14b  test    r10, r10
0x14000f14e  jz      short loc_14000F175
0x14000f150  mov     r11d, 1687h
0x14000f156  cmp     [r10], r11w
0x14000f15a  jnz     short loc_14000F175
0x14000f15c  test    rdx, rdx
0x14000f15f  jz      short loc_14000F164
0x14000f161  mov     [rdx], r9
0x14000f164  test    r8, r8
0x14000f167  jz      short loc_14000F170
0x14000f169  mov     rax, [rcx+20h]
0x14000f16d  mov     [r8], rax
0x14000f170  mov     al, 1
0x14000f172  mov     [rsp+18h+var_18], al
0x14000f175  jmp     short loc_14000F17A
0x14000f177  mov     al, [rsp+18h+var_18]
0x14000f17a  add     rsp, 18h
0x14000f17e  retn
```
