# StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x180006210`
- end: `0x180006292`
- name: `?StringCchCopyNW@@YAJPEAG_KPEBG1@Z`
- size: `130`
- prototype: `__int64 __fastcall(char *, __int64, char *, unsigned __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800062a4`
- `0x18000829c`
- `0x180011364`
- `0x180025824`

## callees

- `0x180006210`

## pseudocode

```c
__int64 __fastcall StringCchCopyNW(char *a1, __int64 a2, char *a3, unsigned __int64 a4)
{
  int v4; // r10d
  __int64 v5; // r9
  signed __int64 v6; // r8
  unsigned __int16 v7; // ax

  v4 = 0;
  if ( (unsigned __int64)(a2 - 1) > 0x7FFFFFFE )
    v4 = -2147024809;
  if ( v4 >= 0 )
  {
    if ( a4 <= 0x7FFFFFFE )
    {
      v4 = 0;
      if ( !a2 )
        goto LABEL_12;
      v5 = a4 - a2;
      v6 = a3 - a1;
      do
      {
        if ( !(v5 + a2) )
          break;
        v7 = *(_WORD *)&a1[v6];
        if ( !v7 )
          break;
        *(_WORD *)a1 = v7;
        a1 += 2;
        --a2;
      }
      while ( a2 );
      if ( !a2 )
      {
LABEL_12:
        a1 -= 2;
        v4 = -2147024774;
      }
    }
    else
    {
      v4 = -2147024809;
    }
    goto LABEL_14;
  }
  if ( a2 )
LABEL_14:
    *(_WORD *)a1 = 0;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180006210  mov     [rsp+arg_0], rbx
0x180006215  xor     r11d, r11d
0x180006218  lea     rax, [rdx-1]
0x18000621c  cmp     rax, 7FFFFFFEh
0x180006222  mov     r10d, r11d
0x180006225  mov     ebx, 80070057h
0x18000622a  cmova   r10d, ebx
0x18000622e  test    r10d, r10d
0x180006231  js      short loc_180006280
0x180006233  cmp     r9, 7FFFFFFEh
0x18000623a  jbe     short loc_180006241
0x18000623c  mov     r10d, ebx
0x18000623f  jmp     short loc_180006285
0x180006241  mov     r10d, r11d
0x180006244  test    rdx, rdx
0x180006247  jz      short loc_180006274
0x180006249  sub     r9, rdx
0x18000624c  sub     r8, rcx
0x18000624f  lea     rax, [r9+rdx]
0x180006253  test    rax, rax
0x180006256  jz      short loc_18000626F
0x180006258  movzx   eax, word ptr [r8+rcx]
0x18000625d  test    ax, ax
0x180006260  jz      short loc_18000626F
0x180006262  mov     [rcx], ax
0x180006265  add     rcx, 2
0x180006269  sub     rdx, 1
0x18000626d  jnz     short loc_18000624F
0x18000626f  test    rdx, rdx
0x180006272  jnz     short loc_180006285
0x180006274  sub     rcx, 2
0x180006278  mov     r10d, 8007007Ah
0x18000627e  jmp     short loc_180006285
0x180006280  test    rdx, rdx
0x180006283  jz      short loc_180006289
0x180006285  mov     [rcx], r11w
0x180006289  mov     rbx, [rsp+arg_0]
0x18000628e  mov     eax, r10d
0x180006291  retn
```
