# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1400051c0`
- end: `0x14000527b`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `187`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400030f8`
- `0x14000535c`

## callees

- `0x1400051c0`

## pseudocode

```c
__int64 __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // r10
  __int64 v5; // r11
  unsigned __int16 *v6; // rax
  unsigned int v7; // edx
  __int64 v8; // rax
  __int64 v9; // r9
  unsigned __int16 *i; // rax
  unsigned __int16 *v11; // rcx

  v3 = 2147483646;
  if ( (unsigned __int64)(a2 - 1) > 0x7FFFFFFE )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    v5 = a2;
    v6 = a1;
    do
    {
      if ( !*v6 )
        break;
      ++v6;
      --v5;
    }
    while ( v5 );
    v7 = v5 == 0 ? 0x80070057 : 0;
    v8 = (a2 - v5) & -(__int64)(v5 != 0);
    if ( v5 )
    {
      v9 = a2 - v8;
      for ( i = &a1[v8]; v9; --v9 )
      {
        if ( !v3 )
          break;
        if ( !*a3 )
          break;
        *i++ = *a3++;
        --v3;
      }
      v11 = i - 1;
      if ( v9 )
        v11 = i;
      v7 = v9 == 0 ? 0x8007007A : 0;
      *v11 = 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1400051c0  mov     [rsp+arg_0], rbx
0x1400051c5  mov     [rsp+arg_8], rdi
0x1400051ca  lea     rax, [rdx-1]
0x1400051ce  mov     r10d, 7FFFFFFEh
0x1400051d4  mov     r9, rdx
0x1400051d7  mov     rbx, rcx
0x1400051da  cmp     rax, r10
0x1400051dd  ja      loc_140005269
0x1400051e3  mov     r11, rdx
0x1400051e6  mov     rax, rcx
0x1400051e9  xor     edi, edi
0x1400051eb  cmp     [rax], di
0x1400051ee  jz      short loc_1400051FA
0x1400051f0  add     rax, 2
0x1400051f4  sub     r11, 1
0x1400051f8  jnz     short loc_1400051EB
0x1400051fa  mov     rax, r11
0x1400051fd  mov     rcx, r9
0x140005200  neg     rax
0x140005203  mov     rax, r11
0x140005206  sbb     edx, edx
0x140005208  sub     rcx, r11
0x14000520b  not     edx
0x14000520d  and     edx, 80070057h
0x140005213  neg     rax
0x140005216  sbb     rax, rax
0x140005219  and     rax, rcx
0x14000521c  test    r11, r11
0x14000521f  jz      short loc_14000526E
0x140005221  sub     r9, rax
0x140005224  lea     rax, [rbx+rax*2]
0x140005228  jz      short loc_14000524C
0x14000522a  test    r10, r10
0x14000522d  jz      short loc_14000524C
0x14000522f  movzx   ecx, word ptr [r8]
0x140005233  test    cx, cx
0x140005236  jz      short loc_14000524C
0x140005238  mov     [rax], cx
0x14000523b  add     r8, 2
0x14000523f  add     rax, 2
0x140005243  dec     r10
0x140005246  sub     r9, 1
0x14000524a  jnz     short loc_14000522A
0x14000524c  test    r9, r9
0x14000524f  lea     rcx, [rax-2]
0x140005253  cmovnz  rcx, rax
0x140005257  neg     r9
0x14000525a  sbb     edx, edx
0x14000525c  not     edx
0x14000525e  and     edx, 8007007Ah
0x140005264  mov     [rcx], di
0x140005267  jmp     short loc_14000526E
0x140005269  mov     edx, 80070057h
0x14000526e  mov     rbx, [rsp+arg_0]
0x140005273  mov     eax, edx
0x140005275  mov     rdi, [rsp+arg_8]
0x14000527a  retn
```
