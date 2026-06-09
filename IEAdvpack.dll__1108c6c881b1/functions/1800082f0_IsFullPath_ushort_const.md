# IsFullPath(ushort const *)

- ea: `0x1800082f0`
- end: `0x180008327`
- name: `?IsFullPath@@YAHPEBG@Z`
- size: `55`
- prototype: `_BOOL8 __fastcall(const unsigned __int16 *)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x18000521c`
- `0x1800056d0`
- `0x1800063c4`
- `0x180009c14`
- `0x18000b240`
- `0x18000cc80`
- `0x18000e060`
- `0x18000f7b0`
- `0x180010050`
- `0x1800104c0`
- `0x1800108a0`
- `0x180010ac0`

## callees

- `0x1800082f0`

## pseudocode

```c
_BOOL8 __fastcall IsFullPath(const unsigned __int16 *a1)
{
  unsigned __int64 v1; // rax

  if ( !a1 )
    return 0;
  v1 = -1;
  do
    ++v1;
  while ( a1[v1] );
  return v1 >= 3 && (a1[1] == 58 || *a1 == 92 && a1[1] == 92);
}

```

## disassembly

```asm
0x1800082f0  xor     edx, edx
0x1800082f2  test    rcx, rcx
0x1800082f5  jz      short loc_180008324
0x1800082f7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800082fb  inc     rax
0x1800082fe  cmp     [rcx+rax*2], dx
0x180008302  jnz     short loc_1800082FB
0x180008304  cmp     rax, 3
0x180008308  jb      short loc_180008324
0x18000830a  cmp     word ptr [rcx+2], 3Ah ; ':'
0x18000830f  jz      short loc_18000831E
0x180008311  cmp     word ptr [rcx], 5Ch ; '\'
0x180008315  jnz     short loc_180008324
0x180008317  cmp     word ptr [rcx+2], 5Ch ; '\'
0x18000831c  jnz     short loc_180008324
0x18000831e  mov     eax, 1
0x180008323  retn
0x180008324  xor     eax, eax
0x180008326  retn
```
