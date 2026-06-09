# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800093d0`
- end: `0x180009479`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004140`
- `0x1800098dc`

## callees

- `0x1800093d0`

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
0x1800093d0  mov     [rsp+arg_0], rbx
0x1800093d5  mov     [rsp+arg_8], rdi
0x1800093da  mov     r9d, 104h
0x1800093e0  mov     rbx, rcx
0x1800093e3  mov     r10d, r9d
0x1800093e6  mov     rax, rcx
0x1800093e9  xor     edi, edi
0x1800093eb  cmp     [rax], di
0x1800093ee  jz      short loc_1800093FA
0x1800093f0  add     rax, 2
0x1800093f4  sub     r10, 1
0x1800093f8  jnz     short loc_1800093EB
0x1800093fa  mov     rax, r10
0x1800093fd  mov     rcx, r9
0x180009400  neg     rax
0x180009403  mov     rax, r10
0x180009406  sbb     edx, edx
0x180009408  sub     rcx, r10
0x18000940b  not     edx
0x18000940d  and     edx, 80070057h
0x180009413  neg     rax
0x180009416  sbb     r11, r11
0x180009419  and     r11, rcx
0x18000941c  test    r10, r10
0x18000941f  jz      short loc_18000946C
0x180009421  lea     rax, [rbx+r11*2]
0x180009425  mov     ecx, 7FFFFFFEh
0x18000942a  sub     r9, r11
0x18000942d  jz      short loc_180009451
0x18000942f  test    rcx, rcx
0x180009432  jz      short loc_180009451
0x180009434  movzx   edx, word ptr [r8]
0x180009438  test    dx, dx
0x18000943b  jz      short loc_180009451
0x18000943d  mov     [rax], dx
0x180009440  add     r8, 2
0x180009444  add     rax, 2
0x180009448  dec     rcx
0x18000944b  sub     r9, 1
0x18000944f  jnz     short loc_18000942F
0x180009451  test    r9, r9
0x180009454  lea     rcx, [rax-2]
0x180009458  cmovnz  rcx, rax
0x18000945c  neg     r9
0x18000945f  sbb     edx, edx
0x180009461  not     edx
0x180009463  and     edx, 8007007Ah
0x180009469  mov     [rcx], di
0x18000946c  mov     rbx, [rsp+arg_0]
0x180009471  mov     eax, edx
0x180009473  mov     rdi, [rsp+arg_8]
0x180009478  retn
```
