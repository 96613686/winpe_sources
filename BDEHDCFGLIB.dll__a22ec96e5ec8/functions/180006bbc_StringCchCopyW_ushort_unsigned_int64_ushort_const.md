# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180006bbc`
- end: `0x180006c27`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180004170`
- `0x1800080f0`
- `0x18000a8e0`
- `0x18000ab70`
- `0x18000ad60`
- `0x18000ae70`
- `0x18000b094`
- `0x18000b2c0`
- `0x18000b590`

## callees

- `0x180006bbc`

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
0x180006bbc  xor     r10d, r10d
0x180006bbf  mov     r9, rcx
0x180006bc2  test    rdx, rdx
0x180006bc5  jz      short loc_180006C18
0x180006bc7  cmp     rdx, 7FFFFFFFh
0x180006bce  jbe     short loc_180006BD7
0x180006bd0  mov     eax, 80070057h
0x180006bd5  jmp     short loc_180006C22
0x180006bd7  mov     eax, 7FFFFFFEh
0x180006bdc  test    rax, rax
0x180006bdf  jz      short loc_180006BFF
0x180006be1  movzx   ecx, word ptr [r8]
0x180006be5  test    cx, cx
0x180006be8  jz      short loc_180006BFF
0x180006bea  mov     [r9], cx
0x180006bee  add     r8, 2
0x180006bf2  add     r9, 2
0x180006bf6  dec     rax
0x180006bf9  sub     rdx, 1
0x180006bfd  jnz     short loc_180006BDC
0x180006bff  test    rdx, rdx
0x180006c02  lea     rcx, [r9-2]
0x180006c06  cmovnz  rcx, r9
0x180006c0a  neg     rdx
0x180006c0d  sbb     eax, eax
0x180006c0f  not     eax
0x180006c11  and     eax, 8007007Ah
0x180006c16  jmp     short loc_180006C22
0x180006c18  mov     eax, 80070057h
0x180006c1d  test    rdx, rdx
0x180006c20  jz      short locret_180006C26
0x180006c22  mov     [rcx], r10w
0x180006c26  retn
```
