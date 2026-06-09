# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180006e20`
- end: `0x180006ec9`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003a54`
- `0x180006f5c`

## callees

- `0x180006e20`

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
0x180006e20  mov     [rsp+arg_0], rbx
0x180006e25  mov     [rsp+arg_8], rdi
0x180006e2a  mov     r9d, 104h
0x180006e30  mov     rbx, rcx
0x180006e33  mov     r10d, r9d
0x180006e36  mov     rax, rcx
0x180006e39  xor     edi, edi
0x180006e3b  cmp     [rax], di
0x180006e3e  jz      short loc_180006E4A
0x180006e40  add     rax, 2
0x180006e44  sub     r10, 1
0x180006e48  jnz     short loc_180006E3B
0x180006e4a  mov     rax, r10
0x180006e4d  mov     rcx, r9
0x180006e50  neg     rax
0x180006e53  mov     rax, r10
0x180006e56  sbb     edx, edx
0x180006e58  sub     rcx, r10
0x180006e5b  not     edx
0x180006e5d  and     edx, 80070057h
0x180006e63  neg     rax
0x180006e66  sbb     r11, r11
0x180006e69  and     r11, rcx
0x180006e6c  test    r10, r10
0x180006e6f  jz      short loc_180006EBC
0x180006e71  lea     rax, [rbx+r11*2]
0x180006e75  mov     ecx, 7FFFFFFEh
0x180006e7a  sub     r9, r11
0x180006e7d  jz      short loc_180006EA1
0x180006e7f  test    rcx, rcx
0x180006e82  jz      short loc_180006EA1
0x180006e84  movzx   edx, word ptr [r8]
0x180006e88  test    dx, dx
0x180006e8b  jz      short loc_180006EA1
0x180006e8d  mov     [rax], dx
0x180006e90  add     r8, 2
0x180006e94  add     rax, 2
0x180006e98  dec     rcx
0x180006e9b  sub     r9, 1
0x180006e9f  jnz     short loc_180006E7F
0x180006ea1  test    r9, r9
0x180006ea4  lea     rcx, [rax-2]
0x180006ea8  cmovnz  rcx, rax
0x180006eac  neg     r9
0x180006eaf  sbb     edx, edx
0x180006eb1  not     edx
0x180006eb3  and     edx, 8007007Ah
0x180006eb9  mov     [rcx], di
0x180006ebc  mov     rbx, [rsp+arg_0]
0x180006ec1  mov     eax, edx
0x180006ec3  mov     rdi, [rsp+arg_8]
0x180006ec8  retn
```
