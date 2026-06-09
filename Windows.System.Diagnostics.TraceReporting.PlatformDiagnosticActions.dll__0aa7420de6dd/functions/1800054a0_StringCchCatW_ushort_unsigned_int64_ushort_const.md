# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800054a0`
- end: `0x180005549`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800033e8`
- `0x18000560c`

## callees

- `0x1800054a0`

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
0x1800054a0  mov     [rsp+arg_0], rbx
0x1800054a5  mov     [rsp+arg_8], rdi
0x1800054aa  mov     r9d, 104h
0x1800054b0  mov     rbx, rcx
0x1800054b3  mov     r10d, r9d
0x1800054b6  mov     rax, rcx
0x1800054b9  xor     edi, edi
0x1800054bb  cmp     [rax], di
0x1800054be  jz      short loc_1800054CA
0x1800054c0  add     rax, 2
0x1800054c4  sub     r10, 1
0x1800054c8  jnz     short loc_1800054BB
0x1800054ca  mov     rax, r10
0x1800054cd  mov     rcx, r9
0x1800054d0  neg     rax
0x1800054d3  mov     rax, r10
0x1800054d6  sbb     edx, edx
0x1800054d8  sub     rcx, r10
0x1800054db  not     edx
0x1800054dd  and     edx, 80070057h
0x1800054e3  neg     rax
0x1800054e6  sbb     r11, r11
0x1800054e9  and     r11, rcx
0x1800054ec  test    r10, r10
0x1800054ef  jz      short loc_18000553C
0x1800054f1  lea     rax, [rbx+r11*2]
0x1800054f5  mov     ecx, 7FFFFFFEh
0x1800054fa  sub     r9, r11
0x1800054fd  jz      short loc_180005521
0x1800054ff  test    rcx, rcx
0x180005502  jz      short loc_180005521
0x180005504  movzx   edx, word ptr [r8]
0x180005508  test    dx, dx
0x18000550b  jz      short loc_180005521
0x18000550d  mov     [rax], dx
0x180005510  add     r8, 2
0x180005514  add     rax, 2
0x180005518  dec     rcx
0x18000551b  sub     r9, 1
0x18000551f  jnz     short loc_1800054FF
0x180005521  test    r9, r9
0x180005524  lea     rcx, [rax-2]
0x180005528  cmovnz  rcx, rax
0x18000552c  neg     r9
0x18000552f  sbb     edx, edx
0x180005531  not     edx
0x180005533  and     edx, 8007007Ah
0x180005539  mov     [rcx], di
0x18000553c  mov     rbx, [rsp+arg_0]
0x180005541  mov     eax, edx
0x180005543  mov     rdi, [rsp+arg_8]
0x180005548  retn
```
