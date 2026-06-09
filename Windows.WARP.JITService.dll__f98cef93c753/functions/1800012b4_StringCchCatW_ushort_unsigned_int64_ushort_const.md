# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800012b4`
- end: `0x18000135d`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003280`
- `0x180003490`

## callees

- `0x1800012b4`

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
0x1800012b4  mov     [rsp+arg_0], rbx
0x1800012b9  mov     [rsp+arg_8], rdi
0x1800012be  mov     r9d, 104h
0x1800012c4  mov     rbx, rcx
0x1800012c7  mov     r10d, r9d
0x1800012ca  mov     rax, rcx
0x1800012cd  xor     edi, edi
0x1800012cf  cmp     [rax], di
0x1800012d2  jz      short loc_1800012DE
0x1800012d4  add     rax, 2
0x1800012d8  sub     r10, 1
0x1800012dc  jnz     short loc_1800012CF
0x1800012de  mov     rax, r10
0x1800012e1  mov     rcx, r9
0x1800012e4  neg     rax
0x1800012e7  mov     rax, r10
0x1800012ea  sbb     edx, edx
0x1800012ec  sub     rcx, r10
0x1800012ef  not     edx
0x1800012f1  and     edx, 80070057h
0x1800012f7  neg     rax
0x1800012fa  sbb     r11, r11
0x1800012fd  and     r11, rcx
0x180001300  test    r10, r10
0x180001303  jz      short loc_180001350
0x180001305  lea     rax, [rbx+r11*2]
0x180001309  mov     ecx, 7FFFFFFEh
0x18000130e  sub     r9, r11
0x180001311  jz      short loc_180001335
0x180001313  test    rcx, rcx
0x180001316  jz      short loc_180001335
0x180001318  movzx   edx, word ptr [r8]
0x18000131c  test    dx, dx
0x18000131f  jz      short loc_180001335
0x180001321  mov     [rax], dx
0x180001324  add     r8, 2
0x180001328  add     rax, 2
0x18000132c  dec     rcx
0x18000132f  sub     r9, 1
0x180001333  jnz     short loc_180001313
0x180001335  test    r9, r9
0x180001338  lea     rcx, [rax-2]
0x18000133c  cmovnz  rcx, rax
0x180001340  neg     r9
0x180001343  sbb     edx, edx
0x180001345  not     edx
0x180001347  and     edx, 8007007Ah
0x18000134d  mov     [rcx], di
0x180001350  mov     rbx, [rsp+arg_0]
0x180001355  mov     eax, edx
0x180001357  mov     rdi, [rsp+arg_8]
0x18000135c  retn
```
