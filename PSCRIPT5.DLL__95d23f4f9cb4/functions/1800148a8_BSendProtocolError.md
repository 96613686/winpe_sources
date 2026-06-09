# BSendProtocolError

- ea: `0x1800148a8`
- end: `0x1800148e6`
- name: `BSendProtocolError`
- size: `62`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800139e8`
- `0x180013ae4`
- `0x1800146dc`
- `0x180014d48`

## callees

- `0x1800148a8`
- `0x180015f84`

## pseudocode

```c
_BOOL8 __fastcall BSendProtocolError(__int64 a1)
{
  __int16 v1; // ax
  __int64 v3; // rdx

  v1 = *(_WORD *)(a1 + 166);
  if ( v1 == 2 )
  {
    v3 = 6;
LABEL_5:
    PSProcsetSend(a1, v3);
    return *(_DWORD *)(a1 + 3440) == 0;
  }
  if ( v1 == 16 )
  {
    v3 = 7;
    goto LABEL_5;
  }
  return *(_DWORD *)(a1 + 3440) == 0;
}

```

## disassembly

```asm
0x1800148a8  push    rbx
0x1800148aa  sub     rsp, 20h
0x1800148ae  movzx   eax, word ptr [rcx+0A6h]
0x1800148b5  mov     rbx, rcx
0x1800148b8  cmp     ax, 2
0x1800148bc  jnz     short loc_1800148C5
0x1800148be  mov     edx, 6
0x1800148c3  jmp     short loc_1800148D0
0x1800148c5  cmp     ax, 10h
0x1800148c9  jnz     short loc_1800148D5
0x1800148cb  mov     edx, 7
0x1800148d0  call    PSProcsetSend
0x1800148d5  xor     eax, eax
0x1800148d7  cmp     [rbx+0D70h], eax
0x1800148dd  setz    al
0x1800148e0  add     rsp, 20h
0x1800148e4  pop     rbx
0x1800148e5  retn
```
