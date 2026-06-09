# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140006e74`
- end: `0x140006f1d`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400040e4`
- `0x140007104`

## callees

- `0x140006e74`

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
0x140006e74  mov     [rsp+arg_0], rbx
0x140006e79  mov     [rsp+arg_8], rdi
0x140006e7e  mov     r9d, 104h
0x140006e84  mov     rbx, rcx
0x140006e87  mov     r10d, r9d
0x140006e8a  mov     rax, rcx
0x140006e8d  xor     edi, edi
0x140006e8f  cmp     [rax], di
0x140006e92  jz      short loc_140006E9E
0x140006e94  add     rax, 2
0x140006e98  sub     r10, 1
0x140006e9c  jnz     short loc_140006E8F
0x140006e9e  mov     rax, r10
0x140006ea1  mov     rcx, r9
0x140006ea4  neg     rax
0x140006ea7  mov     rax, r10
0x140006eaa  sbb     edx, edx
0x140006eac  sub     rcx, r10
0x140006eaf  not     edx
0x140006eb1  and     edx, 80070057h
0x140006eb7  neg     rax
0x140006eba  sbb     r11, r11
0x140006ebd  and     r11, rcx
0x140006ec0  test    r10, r10
0x140006ec3  jz      short loc_140006F10
0x140006ec5  lea     rax, [rbx+r11*2]
0x140006ec9  mov     ecx, 7FFFFFFEh
0x140006ece  sub     r9, r11
0x140006ed1  jz      short loc_140006EF5
0x140006ed3  test    rcx, rcx
0x140006ed6  jz      short loc_140006EF5
0x140006ed8  movzx   edx, word ptr [r8]
0x140006edc  test    dx, dx
0x140006edf  jz      short loc_140006EF5
0x140006ee1  mov     [rax], dx
0x140006ee4  add     r8, 2
0x140006ee8  add     rax, 2
0x140006eec  dec     rcx
0x140006eef  sub     r9, 1
0x140006ef3  jnz     short loc_140006ED3
0x140006ef5  test    r9, r9
0x140006ef8  lea     rcx, [rax-2]
0x140006efc  cmovnz  rcx, rax
0x140006f00  neg     r9
0x140006f03  sbb     edx, edx
0x140006f05  not     edx
0x140006f07  and     edx, 8007007Ah
0x140006f0d  mov     [rcx], di
0x140006f10  mov     rbx, [rsp+arg_0]
0x140006f15  mov     eax, edx
0x140006f17  mov     rdi, [rsp+arg_8]
0x140006f1c  retn
```
