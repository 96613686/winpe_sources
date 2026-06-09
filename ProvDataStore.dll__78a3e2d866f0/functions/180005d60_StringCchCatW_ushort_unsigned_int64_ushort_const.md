# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180005d60`
- end: `0x180005e1b`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `187`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003a9c`
- `0x18000608c`
- `0x180007fa4`

## callees

- `0x180005d60`

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
0x180005d60  mov     [rsp+arg_0], rbx
0x180005d65  mov     [rsp+arg_8], rdi
0x180005d6a  lea     rax, [rdx-1]
0x180005d6e  mov     r10d, 7FFFFFFEh
0x180005d74  mov     r9, rdx
0x180005d77  mov     rbx, rcx
0x180005d7a  cmp     rax, r10
0x180005d7d  ja      loc_180005E09
0x180005d83  mov     r11, rdx
0x180005d86  mov     rax, rcx
0x180005d89  xor     edi, edi
0x180005d8b  cmp     [rax], di
0x180005d8e  jz      short loc_180005D9A
0x180005d90  add     rax, 2
0x180005d94  sub     r11, 1
0x180005d98  jnz     short loc_180005D8B
0x180005d9a  mov     rax, r11
0x180005d9d  mov     rcx, r9
0x180005da0  neg     rax
0x180005da3  mov     rax, r11
0x180005da6  sbb     edx, edx
0x180005da8  sub     rcx, r11
0x180005dab  not     edx
0x180005dad  and     edx, 80070057h
0x180005db3  neg     rax
0x180005db6  sbb     rax, rax
0x180005db9  and     rax, rcx
0x180005dbc  test    r11, r11
0x180005dbf  jz      short loc_180005E0E
0x180005dc1  sub     r9, rax
0x180005dc4  lea     rax, [rbx+rax*2]
0x180005dc8  jz      short loc_180005DEC
0x180005dca  test    r10, r10
0x180005dcd  jz      short loc_180005DEC
0x180005dcf  movzx   ecx, word ptr [r8]
0x180005dd3  test    cx, cx
0x180005dd6  jz      short loc_180005DEC
0x180005dd8  mov     [rax], cx
0x180005ddb  add     r8, 2
0x180005ddf  add     rax, 2
0x180005de3  dec     r10
0x180005de6  sub     r9, 1
0x180005dea  jnz     short loc_180005DCA
0x180005dec  test    r9, r9
0x180005def  lea     rcx, [rax-2]
0x180005df3  cmovnz  rcx, rax
0x180005df7  neg     r9
0x180005dfa  sbb     edx, edx
0x180005dfc  not     edx
0x180005dfe  and     edx, 8007007Ah
0x180005e04  mov     [rcx], di
0x180005e07  jmp     short loc_180005E0E
0x180005e09  mov     edx, 80070057h
0x180005e0e  mov     rbx, [rsp+arg_0]
0x180005e13  mov     eax, edx
0x180005e15  mov     rdi, [rsp+arg_8]
0x180005e1a  retn
```
