# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180009110`
- end: `0x1800091b9`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800060e0`
- `0x1800094c8`

## callees

- `0x180009110`

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
0x180009110  mov     [rsp+arg_0], rbx
0x180009115  mov     [rsp+arg_8], rdi
0x18000911a  mov     r9d, 104h
0x180009120  mov     rbx, rcx
0x180009123  mov     r10d, r9d
0x180009126  mov     rax, rcx
0x180009129  xor     edi, edi
0x18000912b  cmp     [rax], di
0x18000912e  jz      short loc_18000913A
0x180009130  add     rax, 2
0x180009134  sub     r10, 1
0x180009138  jnz     short loc_18000912B
0x18000913a  mov     rax, r10
0x18000913d  mov     rcx, r9
0x180009140  neg     rax
0x180009143  mov     rax, r10
0x180009146  sbb     edx, edx
0x180009148  sub     rcx, r10
0x18000914b  not     edx
0x18000914d  and     edx, 80070057h
0x180009153  neg     rax
0x180009156  sbb     r11, r11
0x180009159  and     r11, rcx
0x18000915c  test    r10, r10
0x18000915f  jz      short loc_1800091AC
0x180009161  lea     rax, [rbx+r11*2]
0x180009165  mov     ecx, 7FFFFFFEh
0x18000916a  sub     r9, r11
0x18000916d  jz      short loc_180009191
0x18000916f  test    rcx, rcx
0x180009172  jz      short loc_180009191
0x180009174  movzx   edx, word ptr [r8]
0x180009178  test    dx, dx
0x18000917b  jz      short loc_180009191
0x18000917d  mov     [rax], dx
0x180009180  add     r8, 2
0x180009184  add     rax, 2
0x180009188  dec     rcx
0x18000918b  sub     r9, 1
0x18000918f  jnz     short loc_18000916F
0x180009191  test    r9, r9
0x180009194  lea     rcx, [rax-2]
0x180009198  cmovnz  rcx, rax
0x18000919c  neg     r9
0x18000919f  sbb     edx, edx
0x1800091a1  not     edx
0x1800091a3  and     edx, 8007007Ah
0x1800091a9  mov     [rcx], di
0x1800091ac  mov     rbx, [rsp+arg_0]
0x1800091b1  mov     eax, edx
0x1800091b3  mov     rdi, [rsp+arg_8]
0x1800091b8  retn
```
