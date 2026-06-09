# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140004c14`
- end: `0x140004cd0`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `188`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140004638`
- `0x14000505c`

## callees

- `0x140004c14`

## pseudocode

```c
__int64 __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, char *a3)
{
  __int64 v4; // r9
  unsigned __int16 *v5; // rax
  __int64 v6; // r8
  __int64 result; // rax
  unsigned __int16 *v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rax
  char *v11; // r11
  unsigned __int16 v12; // r8
  unsigned __int16 *v13; // rax

  v4 = a2;
  if ( (unsigned __int64)(a2 - 1) > 0x7FFFFFFE )
    return 2147942487LL;
  v5 = a1;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --a2;
  }
  while ( a2 );
  v6 = (v4 - a2) & -(__int64)(a2 != 0);
  result = a2 == 0 ? 0x80070057 : 0;
  if ( a2 )
  {
    v8 = &a1[v6];
    v9 = v4 - v6;
    if ( v4 != v6 )
    {
      v10 = 2147483646;
      v11 = (char *)(a3 - (char *)v8);
      do
      {
        if ( !v10 )
          break;
        v12 = *(unsigned __int16 *)((char *)v8 + (_QWORD)v11);
        if ( !v12 )
          break;
        *v8 = v12;
        --v10;
        ++v8;
        --v9;
      }
      while ( v9 );
    }
    v13 = v8 - 1;
    if ( v9 )
      v13 = v8;
    *v13 = 0;
    return v9 == 0 ? 0x8007007A : 0;
  }
  return result;
}

```

## disassembly

```asm
0x140004c14  mov     [rsp+arg_0], rbx
0x140004c19  lea     rax, [rdx-1]
0x140004c1d  mov     r11, r8
0x140004c20  mov     r9, rdx
0x140004c23  mov     r10, rcx
0x140004c26  cmp     rax, 7FFFFFFEh
0x140004c2c  ja      loc_140004CC5
0x140004c32  mov     rax, rcx
0x140004c35  xor     ebx, ebx
0x140004c37  cmp     [rax], bx
0x140004c3a  jz      short loc_140004C46
0x140004c3c  add     rax, 2
0x140004c40  sub     rdx, 1
0x140004c44  jnz     short loc_140004C37
0x140004c46  mov     rcx, r9
0x140004c49  mov     rax, rdx
0x140004c4c  sub     rcx, rdx
0x140004c4f  neg     rax
0x140004c52  mov     rax, rdx
0x140004c55  sbb     r8, r8
0x140004c58  and     r8, rcx
0x140004c5b  neg     rax
0x140004c5e  sbb     eax, eax
0x140004c60  not     eax
0x140004c62  and     eax, 80070057h
0x140004c67  test    rdx, rdx
0x140004c6a  jz      short loc_140004CCA
0x140004c6c  mov     rcx, r9
0x140004c6f  lea     rdx, [r10+r8*2]
0x140004c73  sub     rcx, r8
0x140004c76  jz      short loc_140004CA9
0x140004c78  sub     r8, r9
0x140004c7b  lea     rax, [rcx+7FFFFFFEh]
0x140004c82  add     rax, r8
0x140004c85  sub     r11, rdx
0x140004c88  test    rax, rax
0x140004c8b  jz      short loc_140004CA9
0x140004c8d  movzx   r8d, word ptr [r11+rdx]
0x140004c92  test    r8w, r8w
0x140004c96  jz      short loc_140004CA9
0x140004c98  mov     [rdx], r8w
0x140004c9c  dec     rax
0x140004c9f  add     rdx, 2
0x140004ca3  sub     rcx, 1
0x140004ca7  jnz     short loc_140004C88
0x140004ca9  test    rcx, rcx
0x140004cac  lea     rax, [rdx-2]
0x140004cb0  cmovnz  rax, rdx
0x140004cb4  neg     rcx
0x140004cb7  mov     [rax], bx
0x140004cba  sbb     eax, eax
0x140004cbc  not     eax
0x140004cbe  and     eax, 8007007Ah
0x140004cc3  jmp     short loc_140004CCA
0x140004cc5  mov     eax, 80070057h
0x140004cca  mov     rbx, [rsp+arg_0]
0x140004ccf  retn
```
