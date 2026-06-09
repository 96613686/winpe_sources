# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180005e24`
- end: `0x180005e8f`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180006e2c`
- `0x180007818`
- `0x18000fa60`
- `0x180010ae4`

## callees

- `0x180005e24`

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
0x180005e24  xor     r10d, r10d
0x180005e27  mov     r9, rcx
0x180005e2a  test    rdx, rdx
0x180005e2d  jz      short loc_180005E80
0x180005e2f  cmp     rdx, 7FFFFFFFh
0x180005e36  jbe     short loc_180005E3F
0x180005e38  mov     eax, 80070057h
0x180005e3d  jmp     short loc_180005E8A
0x180005e3f  mov     eax, 7FFFFFFEh
0x180005e44  test    rax, rax
0x180005e47  jz      short loc_180005E67
0x180005e49  movzx   ecx, word ptr [r8]
0x180005e4d  test    cx, cx
0x180005e50  jz      short loc_180005E67
0x180005e52  mov     [r9], cx
0x180005e56  add     r8, 2
0x180005e5a  add     r9, 2
0x180005e5e  dec     rax
0x180005e61  sub     rdx, 1
0x180005e65  jnz     short loc_180005E44
0x180005e67  test    rdx, rdx
0x180005e6a  lea     rcx, [r9-2]
0x180005e6e  cmovnz  rcx, r9
0x180005e72  neg     rdx
0x180005e75  sbb     eax, eax
0x180005e77  not     eax
0x180005e79  and     eax, 8007007Ah
0x180005e7e  jmp     short loc_180005E8A
0x180005e80  mov     eax, 80070057h
0x180005e85  test    rdx, rdx
0x180005e88  jz      short locret_180005E8E
0x180005e8a  mov     [rcx], r10w
0x180005e8e  retn
```
