# RtlStringCbCopyA

- ea: `0x180004d64`
- end: `0x180004dad`
- name: `RtlStringCbCopyA`
- size: `73`
- prototype: `__int64 __fastcall(_BYTE *, __int64, _BYTE *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004950`
- `0x180004c40`

## callees

- `0x180004d64`

## pseudocode

```c
__int64 __fastcall RtlStringCbCopyA(_BYTE *a1, __int64 a2, _BYTE *a3)
{
  __int64 v4; // rax
  __int64 v5; // rdx
  _BYTE *v6; // rcx
  __int64 result; // rax

  v4 = 2147483646;
  v5 = 64;
  do
  {
    if ( !v4 )
      break;
    if ( !*a3 )
      break;
    *a1++ = *a3++;
    --v4;
    --v5;
  }
  while ( v5 );
  v6 = a1 - 1;
  result = v5 == 0 ? 0x80000005 : 0;
  if ( v5 )
    v6 = a1;
  *v6 = 0;
  return result;
}

```

## disassembly

```asm
0x180004d64  mov     r9, rcx
0x180004d67  mov     eax, 7FFFFFFEh
0x180004d6c  mov     edx, 40h ; '@'
0x180004d71  test    rax, rax
0x180004d74  jz      short loc_180004D8F
0x180004d76  mov     cl, [r8]
0x180004d79  test    cl, cl
0x180004d7b  jz      short loc_180004D8F
0x180004d7d  mov     [r9], cl
0x180004d80  inc     r8
0x180004d83  inc     r9
0x180004d86  dec     rax
0x180004d89  sub     rdx, 1
0x180004d8d  jnz     short loc_180004D71
0x180004d8f  mov     rax, rdx
0x180004d92  lea     rcx, [r9-1]
0x180004d96  neg     rax
0x180004d99  sbb     eax, eax
0x180004d9b  not     eax
0x180004d9d  and     eax, 80000005h
0x180004da2  test    rdx, rdx
0x180004da5  cmovnz  rcx, r9
0x180004da9  mov     byte ptr [rcx], 0
0x180004dac  retn
```
