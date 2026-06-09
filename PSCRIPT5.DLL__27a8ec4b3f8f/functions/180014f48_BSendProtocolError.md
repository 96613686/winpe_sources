# BSendProtocolError

- ea: `0x180014f48`
- end: `0x180014f87`
- name: `BSendProtocolError`
- size: `63`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014058`
- `0x180014154`
- `0x180014d7c`
- `0x1800153f0`

## callees

- `0x180014f48`
- `0x1800166c0`

## pseudocode

```c
_BOOL8 __fastcall BSendProtocolError(__int64 a1)
{
  __int16 v1; // ax
  int v3; // edx

  v1 = *(_WORD *)(a1 + 166);
  if ( v1 == 2 )
  {
    v3 = 6;
LABEL_5:
    PSProcsetSend((_DWORD *)a1, v3);
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
0x180014f48  push    rbx
0x180014f4a  sub     rsp, 20h
0x180014f4e  movzx   eax, word ptr [rcx+0A6h]
0x180014f55  mov     rbx, rcx
0x180014f58  cmp     ax, 2
0x180014f5c  jnz     short loc_180014F65
0x180014f5e  mov     edx, 6
0x180014f63  jmp     short loc_180014F70
0x180014f65  cmp     ax, 10h
0x180014f69  jnz     short loc_180014F75
0x180014f6b  mov     edx, 7
0x180014f70  call    PSProcsetSend
0x180014f75  xor     eax, eax
0x180014f77  cmp     [rbx+0D70h], eax
0x180014f7d  setz    al
0x180014f80  add     rsp, 20h
0x180014f84  pop     rbx
0x180014f85  retn
```
