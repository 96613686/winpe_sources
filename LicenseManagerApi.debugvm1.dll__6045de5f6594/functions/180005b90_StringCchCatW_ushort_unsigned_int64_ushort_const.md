# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180005b90`
- end: `0x180005c4b`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `187`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003b10`
- `0x180005d2c`
- `0x180006ddc`

## callees

- `0x180005b90`

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
0x180005b90  mov     [rsp+arg_0], rbx
0x180005b95  mov     [rsp+arg_8], rdi
0x180005b9a  lea     rax, [rdx-1]
0x180005b9e  mov     r10d, 7FFFFFFEh
0x180005ba4  mov     r9, rdx
0x180005ba7  mov     rbx, rcx
0x180005baa  cmp     rax, r10
0x180005bad  ja      loc_180005C39
0x180005bb3  mov     r11, rdx
0x180005bb6  mov     rax, rcx
0x180005bb9  xor     edi, edi
0x180005bbb  cmp     [rax], di
0x180005bbe  jz      short loc_180005BCA
0x180005bc0  add     rax, 2
0x180005bc4  sub     r11, 1
0x180005bc8  jnz     short loc_180005BBB
0x180005bca  mov     rax, r11
0x180005bcd  mov     rcx, r9
0x180005bd0  neg     rax
0x180005bd3  mov     rax, r11
0x180005bd6  sbb     edx, edx
0x180005bd8  sub     rcx, r11
0x180005bdb  not     edx
0x180005bdd  and     edx, 80070057h
0x180005be3  neg     rax
0x180005be6  sbb     rax, rax
0x180005be9  and     rax, rcx
0x180005bec  test    r11, r11
0x180005bef  jz      short loc_180005C3E
0x180005bf1  sub     r9, rax
0x180005bf4  lea     rax, [rbx+rax*2]
0x180005bf8  jz      short loc_180005C1C
0x180005bfa  test    r10, r10
0x180005bfd  jz      short loc_180005C1C
0x180005bff  movzx   ecx, word ptr [r8]
0x180005c03  test    cx, cx
0x180005c06  jz      short loc_180005C1C
0x180005c08  mov     [rax], cx
0x180005c0b  add     r8, 2
0x180005c0f  add     rax, 2
0x180005c13  dec     r10
0x180005c16  sub     r9, 1
0x180005c1a  jnz     short loc_180005BFA
0x180005c1c  test    r9, r9
0x180005c1f  lea     rcx, [rax-2]
0x180005c23  cmovnz  rcx, rax
0x180005c27  neg     r9
0x180005c2a  sbb     edx, edx
0x180005c2c  not     edx
0x180005c2e  and     edx, 8007007Ah
0x180005c34  mov     [rcx], di
0x180005c37  jmp     short loc_180005C3E
0x180005c39  mov     edx, 80070057h
0x180005c3e  mov     rbx, [rsp+arg_0]
0x180005c43  mov     eax, edx
0x180005c45  mov     rdi, [rsp+arg_8]
0x180005c4a  retn
```
