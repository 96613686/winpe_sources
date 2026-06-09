# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800050dc`
- end: `0x180005185`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003afc`
- `0x180005218`

## callees

- `0x1800050dc`

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
0x1800050dc  mov     [rsp+arg_0], rbx
0x1800050e1  mov     [rsp+arg_8], rdi
0x1800050e6  mov     r9d, 104h
0x1800050ec  mov     rbx, rcx
0x1800050ef  mov     r10d, r9d
0x1800050f2  mov     rax, rcx
0x1800050f5  xor     edi, edi
0x1800050f7  cmp     [rax], di
0x1800050fa  jz      short loc_180005106
0x1800050fc  add     rax, 2
0x180005100  sub     r10, 1
0x180005104  jnz     short loc_1800050F7
0x180005106  mov     rax, r10
0x180005109  mov     rcx, r9
0x18000510c  neg     rax
0x18000510f  mov     rax, r10
0x180005112  sbb     edx, edx
0x180005114  sub     rcx, r10
0x180005117  not     edx
0x180005119  and     edx, 80070057h
0x18000511f  neg     rax
0x180005122  sbb     r11, r11
0x180005125  and     r11, rcx
0x180005128  test    r10, r10
0x18000512b  jz      short loc_180005178
0x18000512d  lea     rax, [rbx+r11*2]
0x180005131  mov     ecx, 7FFFFFFEh
0x180005136  sub     r9, r11
0x180005139  jz      short loc_18000515D
0x18000513b  test    rcx, rcx
0x18000513e  jz      short loc_18000515D
0x180005140  movzx   edx, word ptr [r8]
0x180005144  test    dx, dx
0x180005147  jz      short loc_18000515D
0x180005149  mov     [rax], dx
0x18000514c  add     r8, 2
0x180005150  add     rax, 2
0x180005154  dec     rcx
0x180005157  sub     r9, 1
0x18000515b  jnz     short loc_18000513B
0x18000515d  test    r9, r9
0x180005160  lea     rcx, [rax-2]
0x180005164  cmovnz  rcx, rax
0x180005168  neg     r9
0x18000516b  sbb     edx, edx
0x18000516d  not     edx
0x18000516f  and     edx, 8007007Ah
0x180005175  mov     [rcx], di
0x180005178  mov     rbx, [rsp+arg_0]
0x18000517d  mov     eax, edx
0x18000517f  mov     rdi, [rsp+arg_8]
0x180005184  retn
```
