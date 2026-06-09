# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180006fac`
- end: `0x180007017`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b49c`
- `0x18001d310`

## callees

- `0x180006fac`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // r9
  __int64 result; // rax
  __int64 v5; // rax

  v3 = a1;
  if ( !a2 )
    return 2147942487LL;
  if ( a2 <= 0x7FFFFFFF )
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*a3 )
        break;
      *v3++ = *a3++;
      --v5;
      --a2;
    }
    while ( a2 );
    a1 = v3 - 1;
    if ( a2 )
      a1 = v3;
    result = a2 == 0 ? 0x8007007A : 0;
  }
  else
  {
    result = 2147942487LL;
  }
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x180006fac  xor     r10d, r10d
0x180006faf  mov     r9, rcx
0x180006fb2  test    rdx, rdx
0x180006fb5  jz      short loc_180007008
0x180006fb7  cmp     rdx, 7FFFFFFFh
0x180006fbe  jbe     short loc_180006FC7
0x180006fc0  mov     eax, 80070057h
0x180006fc5  jmp     short loc_180007012
0x180006fc7  mov     eax, 7FFFFFFEh
0x180006fcc  test    rax, rax
0x180006fcf  jz      short loc_180006FEF
0x180006fd1  movzx   ecx, word ptr [r8]
0x180006fd5  test    cx, cx
0x180006fd8  jz      short loc_180006FEF
0x180006fda  mov     [r9], cx
0x180006fde  add     r8, 2
0x180006fe2  add     r9, 2
0x180006fe6  dec     rax
0x180006fe9  sub     rdx, 1
0x180006fed  jnz     short loc_180006FCC
0x180006fef  test    rdx, rdx
0x180006ff2  lea     rcx, [r9-2]
0x180006ff6  cmovnz  rcx, r9
0x180006ffa  neg     rdx
0x180006ffd  sbb     eax, eax
0x180006fff  not     eax
0x180007001  and     eax, 8007007Ah
0x180007006  jmp     short loc_180007012
0x180007008  mov     eax, 80070057h
0x18000700d  test    rdx, rdx
0x180007010  jz      short locret_180007016
0x180007012  mov     [rcx], r10w
0x180007016  retn
```
