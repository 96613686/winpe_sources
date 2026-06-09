# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180008374`
- end: `0x180008430`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `188`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003dcc`
- `0x180008a0c`
- `0x180028ef0`
- `0x1800312c4`
- `0x180032688`
- `0x18003291c`

## callees

- `0x180008374`

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
0x180008374  mov     [rsp+arg_0], rbx
0x180008379  mov     [rsp+arg_8], rdi
0x18000837e  lea     rax, [rdx-1]
0x180008382  mov     r10d, 7FFFFFFEh
0x180008388  mov     r9, rdx
0x18000838b  mov     rbx, rcx
0x18000838e  cmp     rax, r10
0x180008391  ja      loc_18000841D
0x180008397  mov     r11, rdx
0x18000839a  mov     rax, rcx
0x18000839d  xor     edi, edi
0x18000839f  cmp     [rax], di
0x1800083a2  jz      short loc_1800083AE
0x1800083a4  add     rax, 2
0x1800083a8  sub     r11, 1
0x1800083ac  jnz     short loc_18000839F
0x1800083ae  mov     rax, r11
0x1800083b1  mov     rcx, r9
0x1800083b4  neg     rax
0x1800083b7  mov     rax, r11
0x1800083ba  sbb     edx, edx
0x1800083bc  sub     rcx, r11
0x1800083bf  not     edx
0x1800083c1  and     edx, 80070057h
0x1800083c7  neg     rax
0x1800083ca  sbb     rax, rax
0x1800083cd  and     rax, rcx
0x1800083d0  test    r11, r11
0x1800083d3  jz      short loc_180008422
0x1800083d5  sub     r9, rax
0x1800083d8  lea     rax, [rbx+rax*2]
0x1800083dc  jz      short loc_180008400
0x1800083de  test    r10, r10
0x1800083e1  jz      short loc_180008400
0x1800083e3  movzx   ecx, word ptr [r8]
0x1800083e7  test    cx, cx
0x1800083ea  jz      short loc_180008400
0x1800083ec  mov     [rax], cx
0x1800083ef  add     r8, 2
0x1800083f3  add     rax, 2
0x1800083f7  dec     r10
0x1800083fa  sub     r9, 1
0x1800083fe  jnz     short loc_1800083DE
0x180008400  test    r9, r9
0x180008403  lea     rcx, [rax-2]
0x180008407  cmovnz  rcx, rax
0x18000840b  neg     r9
0x18000840e  sbb     edx, edx
0x180008410  not     edx
0x180008412  and     edx, 8007007Ah
0x180008418  mov     [rcx], di
0x18000841b  jmp     short loc_180008422
0x18000841d  mov     edx, 80070057h
0x180008422  mov     rbx, [rsp+arg_0]
0x180008427  mov     eax, edx
0x180008429  mov     rdi, [rsp+arg_8]
0x18000842e  retn
```
