# StringCchCopyA(char *,unsigned __int64,char const *)

- ea: `0x180011d50`
- end: `0x180011db2`
- name: `?StringCchCopyA@@YAJPEAD_KPEBD@Z`
- size: `98`
- prototype: `__int64 __fastcall(char *, unsigned __int64, char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180011cb8`
- `0x180011dc0`
- `0x1800198f8`

## callees

- `0x180011d50`

## pseudocode

```c
__int64 __fastcall StringCchCopyA(char *a1, unsigned __int64 a2, char *a3)
{
  __int64 result; // rax
  __int64 v4; // rax
  char *v5; // rax

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
    return a2 == 0 ? 0x8007007A : 0;
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
0x180011d50  test    rdx, rdx
0x180011d53  jz      short loc_180011DA4
0x180011d55  cmp     rdx, 7FFFFFFFh
0x180011d5c  jbe     short loc_180011D65
0x180011d5e  mov     eax, 80070057h
0x180011d63  jmp     short loc_180011DAE
0x180011d65  mov     eax, 7FFFFFFEh
0x180011d6a  test    rax, rax
0x180011d6d  jz      short loc_180011D89
0x180011d6f  mov     r9b, [r8]
0x180011d72  test    r9b, r9b
0x180011d75  jz      short loc_180011D89
0x180011d77  mov     [rcx], r9b
0x180011d7a  inc     r8
0x180011d7d  inc     rcx
0x180011d80  dec     rax
0x180011d83  sub     rdx, 1
0x180011d87  jnz     short loc_180011D6A
0x180011d89  test    rdx, rdx
0x180011d8c  lea     rax, [rcx-1]
0x180011d90  cmovnz  rax, rcx
0x180011d94  neg     rdx
0x180011d97  mov     byte ptr [rax], 0
0x180011d9a  sbb     eax, eax
0x180011d9c  not     eax
0x180011d9e  and     eax, 8007007Ah
0x180011da3  retn
0x180011da4  mov     eax, 80070057h
0x180011da9  test    rdx, rdx
0x180011dac  jz      short locret_180011DB1
0x180011dae  mov     byte ptr [rcx], 0
0x180011db1  retn
```
