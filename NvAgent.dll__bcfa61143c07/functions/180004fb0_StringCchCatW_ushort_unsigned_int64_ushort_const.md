# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180004fb0`
- end: `0x180005059`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800030bc`
- `0x18000513c`

## callees

- `0x180004fb0`

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
0x180004fb0  mov     [rsp+arg_0], rbx
0x180004fb5  mov     [rsp+arg_8], rdi
0x180004fba  mov     r9d, 104h
0x180004fc0  mov     rbx, rcx
0x180004fc3  mov     r10d, r9d
0x180004fc6  mov     rax, rcx
0x180004fc9  xor     edi, edi
0x180004fcb  cmp     [rax], di
0x180004fce  jz      short loc_180004FDA
0x180004fd0  add     rax, 2
0x180004fd4  sub     r10, 1
0x180004fd8  jnz     short loc_180004FCB
0x180004fda  mov     rax, r10
0x180004fdd  mov     rcx, r9
0x180004fe0  neg     rax
0x180004fe3  mov     rax, r10
0x180004fe6  sbb     edx, edx
0x180004fe8  sub     rcx, r10
0x180004feb  not     edx
0x180004fed  and     edx, 80070057h
0x180004ff3  neg     rax
0x180004ff6  sbb     r11, r11
0x180004ff9  and     r11, rcx
0x180004ffc  test    r10, r10
0x180004fff  jz      short loc_18000504C
0x180005001  lea     rax, [rbx+r11*2]
0x180005005  mov     ecx, 7FFFFFFEh
0x18000500a  sub     r9, r11
0x18000500d  jz      short loc_180005031
0x18000500f  test    rcx, rcx
0x180005012  jz      short loc_180005031
0x180005014  movzx   edx, word ptr [r8]
0x180005018  test    dx, dx
0x18000501b  jz      short loc_180005031
0x18000501d  mov     [rax], dx
0x180005020  add     r8, 2
0x180005024  add     rax, 2
0x180005028  dec     rcx
0x18000502b  sub     r9, 1
0x18000502f  jnz     short loc_18000500F
0x180005031  test    r9, r9
0x180005034  lea     rcx, [rax-2]
0x180005038  cmovnz  rcx, rax
0x18000503c  neg     r9
0x18000503f  sbb     edx, edx
0x180005041  not     edx
0x180005043  and     edx, 8007007Ah
0x180005049  mov     [rcx], di
0x18000504c  mov     rbx, [rsp+arg_0]
0x180005051  mov     eax, edx
0x180005053  mov     rdi, [rsp+arg_8]
0x180005058  retn
```
