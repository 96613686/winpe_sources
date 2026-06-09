# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1400053b0`
- end: `0x140005459`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400035e0`
- `0x1400054ec`

## callees

- `0x1400053b0`

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
0x1400053b0  mov     [rsp+arg_0], rbx
0x1400053b5  mov     [rsp+arg_8], rdi
0x1400053ba  mov     r9d, 104h
0x1400053c0  mov     rbx, rcx
0x1400053c3  mov     r10d, r9d
0x1400053c6  mov     rax, rcx
0x1400053c9  xor     edi, edi
0x1400053cb  cmp     [rax], di
0x1400053ce  jz      short loc_1400053DA
0x1400053d0  add     rax, 2
0x1400053d4  sub     r10, 1
0x1400053d8  jnz     short loc_1400053CB
0x1400053da  mov     rax, r10
0x1400053dd  mov     rcx, r9
0x1400053e0  neg     rax
0x1400053e3  mov     rax, r10
0x1400053e6  sbb     edx, edx
0x1400053e8  sub     rcx, r10
0x1400053eb  not     edx
0x1400053ed  and     edx, 80070057h
0x1400053f3  neg     rax
0x1400053f6  sbb     r11, r11
0x1400053f9  and     r11, rcx
0x1400053fc  test    r10, r10
0x1400053ff  jz      short loc_14000544C
0x140005401  lea     rax, [rbx+r11*2]
0x140005405  mov     ecx, 7FFFFFFEh
0x14000540a  sub     r9, r11
0x14000540d  jz      short loc_140005431
0x14000540f  test    rcx, rcx
0x140005412  jz      short loc_140005431
0x140005414  movzx   edx, word ptr [r8]
0x140005418  test    dx, dx
0x14000541b  jz      short loc_140005431
0x14000541d  mov     [rax], dx
0x140005420  add     r8, 2
0x140005424  add     rax, 2
0x140005428  dec     rcx
0x14000542b  sub     r9, 1
0x14000542f  jnz     short loc_14000540F
0x140005431  test    r9, r9
0x140005434  lea     rcx, [rax-2]
0x140005438  cmovnz  rcx, rax
0x14000543c  neg     r9
0x14000543f  sbb     edx, edx
0x140005441  not     edx
0x140005443  and     edx, 8007007Ah
0x140005449  mov     [rcx], di
0x14000544c  mov     rbx, [rsp+arg_0]
0x140005451  mov     eax, edx
0x140005453  mov     rdi, [rsp+arg_8]
0x140005458  retn
```
