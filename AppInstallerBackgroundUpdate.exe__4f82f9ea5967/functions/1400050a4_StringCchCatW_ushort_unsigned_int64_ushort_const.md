# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1400050a4`
- end: `0x14000514d`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400030e8`
- `0x14000521c`

## callees

- `0x1400050a4`

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
0x1400050a4  mov     [rsp+arg_0], rbx
0x1400050a9  mov     [rsp+arg_8], rdi
0x1400050ae  mov     r9d, 104h
0x1400050b4  mov     rbx, rcx
0x1400050b7  mov     r10d, r9d
0x1400050ba  mov     rax, rcx
0x1400050bd  xor     edi, edi
0x1400050bf  cmp     [rax], di
0x1400050c2  jz      short loc_1400050CE
0x1400050c4  add     rax, 2
0x1400050c8  sub     r10, 1
0x1400050cc  jnz     short loc_1400050BF
0x1400050ce  mov     rax, r10
0x1400050d1  mov     rcx, r9
0x1400050d4  neg     rax
0x1400050d7  mov     rax, r10
0x1400050da  sbb     edx, edx
0x1400050dc  sub     rcx, r10
0x1400050df  not     edx
0x1400050e1  and     edx, 80070057h
0x1400050e7  neg     rax
0x1400050ea  sbb     r11, r11
0x1400050ed  and     r11, rcx
0x1400050f0  test    r10, r10
0x1400050f3  jz      short loc_140005140
0x1400050f5  lea     rax, [rbx+r11*2]
0x1400050f9  mov     ecx, 7FFFFFFEh
0x1400050fe  sub     r9, r11
0x140005101  jz      short loc_140005125
0x140005103  test    rcx, rcx
0x140005106  jz      short loc_140005125
0x140005108  movzx   edx, word ptr [r8]
0x14000510c  test    dx, dx
0x14000510f  jz      short loc_140005125
0x140005111  mov     [rax], dx
0x140005114  add     r8, 2
0x140005118  add     rax, 2
0x14000511c  dec     rcx
0x14000511f  sub     r9, 1
0x140005123  jnz     short loc_140005103
0x140005125  test    r9, r9
0x140005128  lea     rcx, [rax-2]
0x14000512c  cmovnz  rcx, rax
0x140005130  neg     r9
0x140005133  sbb     edx, edx
0x140005135  not     edx
0x140005137  and     edx, 8007007Ah
0x14000513d  mov     [rcx], di
0x140005140  mov     rbx, [rsp+arg_0]
0x140005145  mov     eax, edx
0x140005147  mov     rdi, [rsp+arg_8]
0x14000514c  retn
```
