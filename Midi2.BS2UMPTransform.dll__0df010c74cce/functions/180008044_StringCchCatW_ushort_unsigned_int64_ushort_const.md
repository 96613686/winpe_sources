# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180008044`
- end: `0x1800080ed`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004850`
- `0x1800081ac`

## callees

- `0x180008044`

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
0x180008044  mov     [rsp+arg_0], rbx
0x180008049  mov     [rsp+arg_8], rdi
0x18000804e  mov     r9d, 104h
0x180008054  mov     rbx, rcx
0x180008057  mov     r10d, r9d
0x18000805a  mov     rax, rcx
0x18000805d  xor     edi, edi
0x18000805f  cmp     [rax], di
0x180008062  jz      short loc_18000806E
0x180008064  add     rax, 2
0x180008068  sub     r10, 1
0x18000806c  jnz     short loc_18000805F
0x18000806e  mov     rax, r10
0x180008071  mov     rcx, r9
0x180008074  neg     rax
0x180008077  mov     rax, r10
0x18000807a  sbb     edx, edx
0x18000807c  sub     rcx, r10
0x18000807f  not     edx
0x180008081  and     edx, 80070057h
0x180008087  neg     rax
0x18000808a  sbb     r11, r11
0x18000808d  and     r11, rcx
0x180008090  test    r10, r10
0x180008093  jz      short loc_1800080E0
0x180008095  lea     rax, [rbx+r11*2]
0x180008099  mov     ecx, 7FFFFFFEh
0x18000809e  sub     r9, r11
0x1800080a1  jz      short loc_1800080C5
0x1800080a3  test    rcx, rcx
0x1800080a6  jz      short loc_1800080C5
0x1800080a8  movzx   edx, word ptr [r8]
0x1800080ac  test    dx, dx
0x1800080af  jz      short loc_1800080C5
0x1800080b1  mov     [rax], dx
0x1800080b4  add     r8, 2
0x1800080b8  add     rax, 2
0x1800080bc  dec     rcx
0x1800080bf  sub     r9, 1
0x1800080c3  jnz     short loc_1800080A3
0x1800080c5  test    r9, r9
0x1800080c8  lea     rcx, [rax-2]
0x1800080cc  cmovnz  rcx, rax
0x1800080d0  neg     r9
0x1800080d3  sbb     edx, edx
0x1800080d5  not     edx
0x1800080d7  and     edx, 8007007Ah
0x1800080dd  mov     [rcx], di
0x1800080e0  mov     rbx, [rsp+arg_0]
0x1800080e5  mov     eax, edx
0x1800080e7  mov     rdi, [rsp+arg_8]
0x1800080ec  retn
```
