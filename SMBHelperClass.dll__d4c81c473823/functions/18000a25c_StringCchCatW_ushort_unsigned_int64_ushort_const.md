# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000a25c`
- end: `0x18000a317`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `187`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000aa6c`
- `0x18000e3b8`
- `0x18000e49c`
- `0x18000e6a8`
- `0x18000eb74`

## callees

- `0x18000a25c`

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
0x18000a25c  mov     [rsp+arg_0], rbx
0x18000a261  mov     [rsp+arg_8], rdi
0x18000a266  lea     rax, [rdx-1]
0x18000a26a  mov     r10d, 7FFFFFFEh
0x18000a270  mov     r9, rdx
0x18000a273  mov     rbx, rcx
0x18000a276  cmp     rax, r10
0x18000a279  ja      loc_18000A305
0x18000a27f  mov     r11, rdx
0x18000a282  mov     rax, rcx
0x18000a285  xor     edi, edi
0x18000a287  cmp     [rax], di
0x18000a28a  jz      short loc_18000A296
0x18000a28c  add     rax, 2
0x18000a290  sub     r11, 1
0x18000a294  jnz     short loc_18000A287
0x18000a296  mov     rax, r11
0x18000a299  mov     rcx, r9
0x18000a29c  neg     rax
0x18000a29f  mov     rax, r11
0x18000a2a2  sbb     edx, edx
0x18000a2a4  sub     rcx, r11
0x18000a2a7  not     edx
0x18000a2a9  and     edx, 80070057h
0x18000a2af  neg     rax
0x18000a2b2  sbb     rax, rax
0x18000a2b5  and     rax, rcx
0x18000a2b8  test    r11, r11
0x18000a2bb  jz      short loc_18000A30A
0x18000a2bd  sub     r9, rax
0x18000a2c0  lea     rax, [rbx+rax*2]
0x18000a2c4  jz      short loc_18000A2E8
0x18000a2c6  test    r10, r10
0x18000a2c9  jz      short loc_18000A2E8
0x18000a2cb  movzx   ecx, word ptr [r8]
0x18000a2cf  test    cx, cx
0x18000a2d2  jz      short loc_18000A2E8
0x18000a2d4  mov     [rax], cx
0x18000a2d7  add     r8, 2
0x18000a2db  add     rax, 2
0x18000a2df  dec     r10
0x18000a2e2  sub     r9, 1
0x18000a2e6  jnz     short loc_18000A2C6
0x18000a2e8  test    r9, r9
0x18000a2eb  lea     rcx, [rax-2]
0x18000a2ef  cmovnz  rcx, rax
0x18000a2f3  neg     r9
0x18000a2f6  sbb     edx, edx
0x18000a2f8  not     edx
0x18000a2fa  and     edx, 8007007Ah
0x18000a300  mov     [rcx], di
0x18000a303  jmp     short loc_18000A30A
0x18000a305  mov     edx, 80070057h
0x18000a30a  mov     rbx, [rsp+arg_0]
0x18000a30f  mov     eax, edx
0x18000a311  mov     rdi, [rsp+arg_8]
0x18000a316  retn
```
