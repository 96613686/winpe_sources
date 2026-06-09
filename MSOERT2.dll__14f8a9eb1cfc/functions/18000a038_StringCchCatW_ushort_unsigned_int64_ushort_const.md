# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000a038`
- end: `0x18000a0f3`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `187`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ab80`
- `0x18000af00`

## callees

- `0x18000a038`

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
0x18000a038  mov     [rsp+arg_0], rbx
0x18000a03d  mov     [rsp+arg_8], rdi
0x18000a042  lea     rax, [rdx-1]
0x18000a046  mov     r10d, 7FFFFFFEh
0x18000a04c  mov     r9, rdx
0x18000a04f  mov     rbx, rcx
0x18000a052  cmp     rax, r10
0x18000a055  ja      loc_18000A0E1
0x18000a05b  mov     r11, rdx
0x18000a05e  mov     rax, rcx
0x18000a061  xor     edi, edi
0x18000a063  cmp     [rax], di
0x18000a066  jz      short loc_18000A072
0x18000a068  add     rax, 2
0x18000a06c  sub     r11, 1
0x18000a070  jnz     short loc_18000A063
0x18000a072  mov     rax, r11
0x18000a075  mov     rcx, r9
0x18000a078  neg     rax
0x18000a07b  mov     rax, r11
0x18000a07e  sbb     edx, edx
0x18000a080  sub     rcx, r11
0x18000a083  not     edx
0x18000a085  and     edx, 80070057h
0x18000a08b  neg     rax
0x18000a08e  sbb     rax, rax
0x18000a091  and     rax, rcx
0x18000a094  test    r11, r11
0x18000a097  jz      short loc_18000A0E6
0x18000a099  sub     r9, rax
0x18000a09c  lea     rax, [rbx+rax*2]
0x18000a0a0  jz      short loc_18000A0C4
0x18000a0a2  test    r10, r10
0x18000a0a5  jz      short loc_18000A0C4
0x18000a0a7  movzx   ecx, word ptr [r8]
0x18000a0ab  test    cx, cx
0x18000a0ae  jz      short loc_18000A0C4
0x18000a0b0  mov     [rax], cx
0x18000a0b3  add     r8, 2
0x18000a0b7  add     rax, 2
0x18000a0bb  dec     r10
0x18000a0be  sub     r9, 1
0x18000a0c2  jnz     short loc_18000A0A2
0x18000a0c4  test    r9, r9
0x18000a0c7  lea     rcx, [rax-2]
0x18000a0cb  cmovnz  rcx, rax
0x18000a0cf  neg     r9
0x18000a0d2  sbb     edx, edx
0x18000a0d4  not     edx
0x18000a0d6  and     edx, 8007007Ah
0x18000a0dc  mov     [rcx], di
0x18000a0df  jmp     short loc_18000A0E6
0x18000a0e1  mov     edx, 80070057h
0x18000a0e6  mov     rbx, [rsp+arg_0]
0x18000a0eb  mov     eax, edx
0x18000a0ed  mov     rdi, [rsp+arg_8]
0x18000a0f2  retn
```
