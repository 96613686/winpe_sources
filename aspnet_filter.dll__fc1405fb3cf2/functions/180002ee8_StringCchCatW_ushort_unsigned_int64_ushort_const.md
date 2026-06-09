# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180002ee8`
- end: `0x180002fa4`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `188`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800022a0`

## callees

- `0x180002ee8`

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
0x180002ee8  mov     [rsp+arg_0], rbx
0x180002eed  lea     rax, [rdx-1]
0x180002ef1  mov     r11, r8
0x180002ef4  mov     r9, rdx
0x180002ef7  mov     r10, rcx
0x180002efa  cmp     rax, 7FFFFFFEh
0x180002f00  ja      loc_180002F99
0x180002f06  mov     rax, rcx
0x180002f09  xor     ebx, ebx
0x180002f0b  cmp     [rax], bx
0x180002f0e  jz      short loc_180002F1A
0x180002f10  add     rax, 2
0x180002f14  sub     rdx, 1
0x180002f18  jnz     short loc_180002F0B
0x180002f1a  mov     rcx, r9
0x180002f1d  mov     rax, rdx
0x180002f20  sub     rcx, rdx
0x180002f23  neg     rax
0x180002f26  mov     rax, rdx
0x180002f29  sbb     r8, r8
0x180002f2c  and     r8, rcx
0x180002f2f  neg     rax
0x180002f32  sbb     eax, eax
0x180002f34  not     eax
0x180002f36  and     eax, 80070057h
0x180002f3b  test    rdx, rdx
0x180002f3e  jz      short loc_180002F9E
0x180002f40  mov     rcx, r9
0x180002f43  lea     rdx, [r10+r8*2]
0x180002f47  sub     rcx, r8
0x180002f4a  jz      short loc_180002F7D
0x180002f4c  sub     r8, r9
0x180002f4f  lea     rax, [rcx+7FFFFFFEh]
0x180002f56  add     rax, r8
0x180002f59  sub     r11, rdx
0x180002f5c  test    rax, rax
0x180002f5f  jz      short loc_180002F7D
0x180002f61  movzx   r8d, word ptr [r11+rdx]
0x180002f66  test    r8w, r8w
0x180002f6a  jz      short loc_180002F7D
0x180002f6c  mov     [rdx], r8w
0x180002f70  dec     rax
0x180002f73  add     rdx, 2
0x180002f77  sub     rcx, 1
0x180002f7b  jnz     short loc_180002F5C
0x180002f7d  test    rcx, rcx
0x180002f80  lea     rax, [rdx-2]
0x180002f84  cmovnz  rax, rdx
0x180002f88  neg     rcx
0x180002f8b  mov     [rax], bx
0x180002f8e  sbb     eax, eax
0x180002f90  not     eax
0x180002f92  and     eax, 8007007Ah
0x180002f97  jmp     short loc_180002F9E
0x180002f99  mov     eax, 80070057h
0x180002f9e  mov     rbx, [rsp+arg_0]
0x180002fa3  retn
```
