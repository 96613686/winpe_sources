# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180005c60`
- end: `0x180005cd5`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `117`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800033a0`
- `0x180003eb0`
- `0x180005ce0`
- `0x180006730`
- `0x18000afd8`

## callees

- `0x180005c60`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  __int64 result; // rax
  __int64 v4; // rax
  unsigned __int16 *v5; // rax

  if ( !a2 )
    return 2147942487LL;
  if ( a2 <= 0x7FFFFFFF )
  {
    v4 = 2147483646;
    do
    {
      if ( !v4 )
        break;
      if ( !*a3 )
        break;
      *a1++ = *a3++;
      --v4;
      --a2;
    }
    while ( a2 );
    v5 = a1 - 1;
    if ( a2 )
      v5 = a1;
    *v5 = 0;
    result = 2147942522LL;
    if ( a2 )
      return 0;
  }
  else
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180005c60  test    rdx, rdx
0x180005c63  jz      short loc_180005CC3
0x180005c65  cmp     rdx, 7FFFFFFFh
0x180005c6c  jbe     short loc_180005C7B
0x180005c6e  xor     r8d, r8d
0x180005c71  mov     eax, 80070057h
0x180005c76  mov     [rcx], r8w
0x180005c7a  retn
0x180005c7b  mov     eax, 7FFFFFFEh
0x180005c80  test    rax, rax
0x180005c83  jz      short loc_180005CA4
0x180005c85  movzx   r9d, word ptr [r8]
0x180005c89  test    r9w, r9w
0x180005c8d  jz      short loc_180005CA4
0x180005c8f  mov     [rcx], r9w
0x180005c93  add     r8, 2
0x180005c97  add     rcx, 2
0x180005c9b  dec     rax
0x180005c9e  sub     rdx, 1
0x180005ca2  jnz     short loc_180005C80
0x180005ca4  test    rdx, rdx
0x180005ca7  lea     rax, [rcx-2]
0x180005cab  cmovnz  rax, rcx
0x180005caf  xor     r8d, r8d
0x180005cb2  test    rdx, rdx
0x180005cb5  mov     [rax], r8w
0x180005cb9  mov     eax, 8007007Ah
0x180005cbe  cmovnz  eax, r8d
0x180005cc2  retn
0x180005cc3  mov     eax, 80070057h
0x180005cc8  test    rdx, rdx
0x180005ccb  jz      short locret_180005CD4
0x180005ccd  xor     r8d, r8d
0x180005cd0  mov     [rcx], r8w
0x180005cd4  retn
```
