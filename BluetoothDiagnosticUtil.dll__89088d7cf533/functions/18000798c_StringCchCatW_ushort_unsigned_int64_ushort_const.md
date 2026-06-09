# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000798c`
- end: `0x180007a36`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `170`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800063e0`
- `0x180007b2c`

## callees

- `0x18000798c`

## pseudocode

```c
__int64 __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // r10
  unsigned __int16 *v4; // rax
  unsigned int v5; // edx
  __int64 v6; // r11
  unsigned __int16 *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // r9
  unsigned __int16 *v10; // rcx

  v3 = 260;
  v4 = a1;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v3;
  }
  while ( v3 );
  v5 = v3 == 0 ? 0x80070057 : 0;
  v6 = (260 - v3) & -(__int64)(v3 != 0);
  if ( v3 )
  {
    v7 = &a1[v6];
    v8 = 2147483646;
    v9 = 260 - v6;
    if ( 260 != v6 )
    {
      do
      {
        if ( !v8 )
          break;
        if ( !*a3 )
          break;
        *v7++ = *a3++;
        --v8;
        --v9;
      }
      while ( v9 );
    }
    v10 = v7 - 1;
    if ( v9 )
      v10 = v7;
    v5 = v9 == 0 ? 0x8007007A : 0;
    *v10 = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x18000798c  mov     [rsp+arg_0], rbx
0x180007991  mov     [rsp+arg_8], rdi
0x180007996  mov     r9d, 104h
0x18000799c  mov     rbx, rcx
0x18000799f  mov     r10d, r9d
0x1800079a2  mov     rax, rcx
0x1800079a5  xor     edi, edi
0x1800079a7  cmp     [rax], di
0x1800079aa  jz      short loc_1800079B6
0x1800079ac  add     rax, 2
0x1800079b0  sub     r10, 1
0x1800079b4  jnz     short loc_1800079A7
0x1800079b6  mov     rax, r10
0x1800079b9  mov     rcx, r9
0x1800079bc  neg     rax
0x1800079bf  mov     rax, r10
0x1800079c2  sbb     edx, edx
0x1800079c4  sub     rcx, r10
0x1800079c7  not     edx
0x1800079c9  and     edx, 80070057h
0x1800079cf  neg     rax
0x1800079d2  sbb     r11, r11
0x1800079d5  and     r11, rcx
0x1800079d8  test    r10, r10
0x1800079db  jz      short loc_180007A28
0x1800079dd  lea     rax, [rbx+r11*2]
0x1800079e1  mov     ecx, 7FFFFFFEh
0x1800079e6  sub     r9, r11
0x1800079e9  jz      short loc_180007A0D
0x1800079eb  test    rcx, rcx
0x1800079ee  jz      short loc_180007A0D
0x1800079f0  movzx   edx, word ptr [r8]
0x1800079f4  test    dx, dx
0x1800079f7  jz      short loc_180007A0D
0x1800079f9  mov     [rax], dx
0x1800079fc  add     r8, 2
0x180007a00  add     rax, 2
0x180007a04  dec     rcx
0x180007a07  sub     r9, 1
0x180007a0b  jnz     short loc_1800079EB
0x180007a0d  test    r9, r9
0x180007a10  lea     rcx, [rax-2]
0x180007a14  cmovnz  rcx, rax
0x180007a18  neg     r9
0x180007a1b  sbb     edx, edx
0x180007a1d  not     edx
0x180007a1f  and     edx, 8007007Ah
0x180007a25  mov     [rcx], di
0x180007a28  mov     rbx, [rsp+arg_0]
0x180007a2d  mov     eax, edx
0x180007a2f  mov     rdi, [rsp+arg_8]
0x180007a34  retn
```
