# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180006584`
- end: `0x18000663f`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `187`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003c90`
- `0x180009280`
- `0x18000c150`
- `0x18000cb58`

## callees

- `0x180006584`

## pseudocode

```c
__int64 __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // r10
  __int64 v5; // r11
  unsigned __int16 *v6; // rax
  unsigned int v7; // edx
  __int64 v8; // rax
  __int64 v9; // r9
  unsigned __int16 *i; // rax
  unsigned __int16 *v11; // rcx

  v3 = 2147483646;
  if ( (unsigned __int64)(a2 - 1) > 0x7FFFFFFE )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    v5 = a2;
    v6 = a1;
    do
    {
      if ( !*v6 )
        break;
      ++v6;
      --v5;
    }
    while ( v5 );
    v7 = v5 == 0 ? 0x80070057 : 0;
    v8 = (a2 - v5) & -(__int64)(v5 != 0);
    if ( v5 )
    {
      v9 = a2 - v8;
      for ( i = &a1[v8]; v9; --v9 )
      {
        if ( !v3 )
          break;
        if ( !*a3 )
          break;
        *i++ = *a3++;
        --v3;
      }
      v11 = i - 1;
      if ( v9 )
        v11 = i;
      v7 = v9 == 0 ? 0x8007007A : 0;
      *v11 = 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180006584  mov     [rsp+arg_0], rbx
0x180006589  mov     [rsp+arg_8], rdi
0x18000658e  lea     rax, [rdx-1]
0x180006592  mov     r10d, 7FFFFFFEh
0x180006598  mov     r9, rdx
0x18000659b  mov     rbx, rcx
0x18000659e  cmp     rax, r10
0x1800065a1  ja      loc_180006638
0x1800065a7  mov     r11, rdx
0x1800065aa  mov     rax, rcx
0x1800065ad  xor     edi, edi
0x1800065af  cmp     [rax], di
0x1800065b2  jz      short loc_1800065BE
0x1800065b4  add     rax, 2
0x1800065b8  sub     r11, 1
0x1800065bc  jnz     short loc_1800065AF
0x1800065be  mov     rax, r11
0x1800065c1  mov     rcx, r9
0x1800065c4  neg     rax
0x1800065c7  mov     rax, r11
0x1800065ca  sbb     edx, edx
0x1800065cc  sub     rcx, r11
0x1800065cf  not     edx
0x1800065d1  and     edx, 80070057h
0x1800065d7  neg     rax
0x1800065da  sbb     rax, rax
0x1800065dd  and     rax, rcx
0x1800065e0  test    r11, r11
0x1800065e3  jz      short loc_18000662B
0x1800065e5  sub     r9, rax
0x1800065e8  lea     rax, [rbx+rax*2]
0x1800065ec  jz      short loc_180006610
0x1800065ee  test    r10, r10
0x1800065f1  jz      short loc_180006610
0x1800065f3  movzx   ecx, word ptr [r8]
0x1800065f7  test    cx, cx
0x1800065fa  jz      short loc_180006610
0x1800065fc  mov     [rax], cx
0x1800065ff  add     r8, 2
0x180006603  add     rax, 2
0x180006607  dec     r10
0x18000660a  sub     r9, 1
0x18000660e  jnz     short loc_1800065EE
0x180006610  test    r9, r9
0x180006613  lea     rcx, [rax-2]
0x180006617  cmovnz  rcx, rax
0x18000661b  neg     r9
0x18000661e  sbb     edx, edx
0x180006620  not     edx
0x180006622  and     edx, 8007007Ah
0x180006628  mov     [rcx], di
0x18000662b  mov     rbx, [rsp+arg_0]
0x180006630  mov     eax, edx
0x180006632  mov     rdi, [rsp+arg_8]
0x180006637  retn
0x180006638  mov     edx, 80070057h
0x18000663d  jmp     short loc_18000662B
```
