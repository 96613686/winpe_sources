# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180005200`
- end: `0x1800052a9`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800032d8`
- `0x18000536c`

## callees

- `0x180005200`

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
0x180005200  mov     [rsp+arg_0], rbx
0x180005205  mov     [rsp+arg_8], rdi
0x18000520a  mov     r9d, 104h
0x180005210  mov     rbx, rcx
0x180005213  mov     r10d, r9d
0x180005216  mov     rax, rcx
0x180005219  xor     edi, edi
0x18000521b  cmp     [rax], di
0x18000521e  jz      short loc_18000522A
0x180005220  add     rax, 2
0x180005224  sub     r10, 1
0x180005228  jnz     short loc_18000521B
0x18000522a  mov     rax, r10
0x18000522d  mov     rcx, r9
0x180005230  neg     rax
0x180005233  mov     rax, r10
0x180005236  sbb     edx, edx
0x180005238  sub     rcx, r10
0x18000523b  not     edx
0x18000523d  and     edx, 80070057h
0x180005243  neg     rax
0x180005246  sbb     r11, r11
0x180005249  and     r11, rcx
0x18000524c  test    r10, r10
0x18000524f  jz      short loc_18000529C
0x180005251  lea     rax, [rbx+r11*2]
0x180005255  mov     ecx, 7FFFFFFEh
0x18000525a  sub     r9, r11
0x18000525d  jz      short loc_180005281
0x18000525f  test    rcx, rcx
0x180005262  jz      short loc_180005281
0x180005264  movzx   edx, word ptr [r8]
0x180005268  test    dx, dx
0x18000526b  jz      short loc_180005281
0x18000526d  mov     [rax], dx
0x180005270  add     r8, 2
0x180005274  add     rax, 2
0x180005278  dec     rcx
0x18000527b  sub     r9, 1
0x18000527f  jnz     short loc_18000525F
0x180005281  test    r9, r9
0x180005284  lea     rcx, [rax-2]
0x180005288  cmovnz  rcx, rax
0x18000528c  neg     r9
0x18000528f  sbb     edx, edx
0x180005291  not     edx
0x180005293  and     edx, 8007007Ah
0x180005299  mov     [rcx], di
0x18000529c  mov     rbx, [rsp+arg_0]
0x1800052a1  mov     eax, edx
0x1800052a3  mov     rdi, [rsp+arg_8]
0x1800052a8  retn
```
