# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140004cd0`
- end: `0x140004d39`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `105`
- prototype: `__int64 __fastcall(char *, __int64, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140004638`

## callees

- `0x140004cd0`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(char *a1, __int64 a2, char *a3)
{
  __int64 v3; // r9
  signed __int64 v4; // r10
  unsigned __int16 v5; // ax
  unsigned __int16 *v6; // rax
  __int64 result; // rax

  if ( (unsigned __int64)(a2 - 1) > 0x7FFFFFFE )
  {
    result = 2147942487LL;
    if ( a2 )
      *(_WORD *)a1 = 0;
  }
  else
  {
    v3 = 2147483646 - a2;
    v4 = a3 - a1;
    do
    {
      if ( !(v3 + a2) )
        break;
      v5 = *(_WORD *)&a1[v4];
      if ( !v5 )
        break;
      *(_WORD *)a1 = v5;
      a1 += 2;
      --a2;
    }
    while ( a2 );
    v6 = (unsigned __int16 *)(a1 - 2);
    if ( a2 )
      v6 = (unsigned __int16 *)a1;
    *v6 = 0;
    return a2 == 0 ? 0x8007007A : 0;
  }
  return result;
}

```

## disassembly

```asm
0x140004cd0  lea     rax, [rdx-1]
0x140004cd4  mov     r9d, 7FFFFFFEh
0x140004cda  mov     r10, r8
0x140004cdd  cmp     rax, r9
0x140004ce0  ja      short loc_140004D27
0x140004ce2  sub     r9, rdx
0x140004ce5  sub     r10, rcx
0x140004ce8  xor     r8d, r8d
0x140004ceb  lea     rax, [r9+rdx]
0x140004cef  test    rax, rax
0x140004cf2  jz      short loc_140004D0B
0x140004cf4  movzx   eax, word ptr [r10+rcx]
0x140004cf9  test    ax, ax
0x140004cfc  jz      short loc_140004D0B
0x140004cfe  mov     [rcx], ax
0x140004d01  add     rcx, 2
0x140004d05  sub     rdx, 1
0x140004d09  jnz     short loc_140004CEB
0x140004d0b  test    rdx, rdx
0x140004d0e  lea     rax, [rcx-2]
0x140004d12  cmovnz  rax, rcx
0x140004d16  neg     rdx
0x140004d19  mov     [rax], r8w
0x140004d1d  sbb     eax, eax
0x140004d1f  not     eax
0x140004d21  and     eax, 8007007Ah
0x140004d26  retn
0x140004d27  xor     r8d, r8d
0x140004d2a  mov     eax, 80070057h
0x140004d2f  test    rdx, rdx
0x140004d32  jz      short locret_140004D38
0x140004d34  mov     [rcx], r8w
0x140004d38  retn
```
