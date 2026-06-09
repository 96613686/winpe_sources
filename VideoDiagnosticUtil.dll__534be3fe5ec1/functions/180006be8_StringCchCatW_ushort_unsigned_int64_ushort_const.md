# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180006be8`
- end: `0x180006c92`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `170`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003ad8`
- `0x1800070e4`

## callees

- `0x180006be8`

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
0x180006be8  mov     [rsp+arg_0], rbx
0x180006bed  mov     [rsp+arg_8], rdi
0x180006bf2  mov     r9d, 104h
0x180006bf8  mov     rbx, rcx
0x180006bfb  mov     r10d, r9d
0x180006bfe  mov     rax, rcx
0x180006c01  xor     edi, edi
0x180006c03  cmp     [rax], di
0x180006c06  jz      short loc_180006C12
0x180006c08  add     rax, 2
0x180006c0c  sub     r10, 1
0x180006c10  jnz     short loc_180006C03
0x180006c12  mov     rax, r10
0x180006c15  mov     rcx, r9
0x180006c18  neg     rax
0x180006c1b  mov     rax, r10
0x180006c1e  sbb     edx, edx
0x180006c20  sub     rcx, r10
0x180006c23  not     edx
0x180006c25  and     edx, 80070057h
0x180006c2b  neg     rax
0x180006c2e  sbb     r11, r11
0x180006c31  and     r11, rcx
0x180006c34  test    r10, r10
0x180006c37  jz      short loc_180006C84
0x180006c39  lea     rax, [rbx+r11*2]
0x180006c3d  mov     ecx, 7FFFFFFEh
0x180006c42  sub     r9, r11
0x180006c45  jz      short loc_180006C69
0x180006c47  test    rcx, rcx
0x180006c4a  jz      short loc_180006C69
0x180006c4c  movzx   edx, word ptr [r8]
0x180006c50  test    dx, dx
0x180006c53  jz      short loc_180006C69
0x180006c55  mov     [rax], dx
0x180006c58  add     r8, 2
0x180006c5c  add     rax, 2
0x180006c60  dec     rcx
0x180006c63  sub     r9, 1
0x180006c67  jnz     short loc_180006C47
0x180006c69  test    r9, r9
0x180006c6c  lea     rcx, [rax-2]
0x180006c70  cmovnz  rcx, rax
0x180006c74  neg     r9
0x180006c77  sbb     edx, edx
0x180006c79  not     edx
0x180006c7b  and     edx, 8007007Ah
0x180006c81  mov     [rcx], di
0x180006c84  mov     rbx, [rsp+arg_0]
0x180006c89  mov     eax, edx
0x180006c8b  mov     rdi, [rsp+arg_8]
0x180006c90  retn
```
