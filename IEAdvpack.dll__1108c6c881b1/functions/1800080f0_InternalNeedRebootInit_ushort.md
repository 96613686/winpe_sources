# InternalNeedRebootInit(ushort)

- ea: `0x1800080f0`
- end: `0x180008130`
- name: `?InternalNeedRebootInit@@YAKG@Z`
- size: `64`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180002450`
- `0x180004880`
- `0x1800080c8`
- `0x18000bc80`
- `0x18000bdb0`

## callees

- `0x180006994`
- `0x180006a5c`
- `0x1800078d8`
- `0x1800080f0`

## pseudocode

```c
__int64 __fastcall InternalNeedRebootInit(const unsigned __int16 *a1)
{
  unsigned int v1; // r8d
  const unsigned __int16 *v2; // rdx

  v1 = 0;
  if ( !(_WORD)a1 )
    return (unsigned int)GetWininitSize();
  if ( (unsigned __int16)a1 == 1 )
    return (unsigned int)GetNumberOfValues(a1);
  v2 = (const unsigned __int16 *)((unsigned int)(unsigned __int16)a1 - 2);
  if ( (unsigned __int16)a1 == 2 )
    return (unsigned int)GetRegValueSize(a1, v2);
  v2 = (const unsigned __int16 *)((unsigned int)(unsigned __int16)a1 - 3);
  if ( (unsigned int)v2 <= 1 )
    return (unsigned int)GetRegValueSize(a1, v2);
  return v1;
}

```

## disassembly

```asm
0x1800080f0  sub     rsp, 28h
0x1800080f4  xor     r8d, r8d
0x1800080f7  movzx   edx, cx
0x1800080fa  test    edx, edx
0x1800080fc  jz      short loc_180008120
0x1800080fe  sub     edx, 1
0x180008101  jz      short loc_180008119
0x180008103  sub     edx, 1
0x180008106  jz      short loc_180008112
0x180008108  sub     edx, 1; unsigned __int16 *
0x18000810b  jz      short loc_180008112
0x18000810d  cmp     edx, 1
0x180008110  jnz     short loc_180008128
0x180008112  call    ?GetRegValueSize@@YAKPEBG0@Z; GetRegValueSize(ushort const *,ushort const *)
0x180008117  jmp     short loc_180008125
0x180008119  call    ?GetNumberOfValues@@YAKPEBG@Z; GetNumberOfValues(ushort const *)
0x18000811e  jmp     short loc_180008125
0x180008120  call    ?GetWininitSize@@YAKXZ; GetWininitSize(void)
0x180008125  mov     r8d, eax
0x180008128  mov     eax, r8d
0x18000812b  add     rsp, 28h
0x18000812f  retn
```
