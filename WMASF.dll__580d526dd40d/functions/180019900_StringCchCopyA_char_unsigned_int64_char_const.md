# StringCchCopyA(char *,unsigned __int64,char const *)

- ea: `0x180019900`
- end: `0x180019962`
- name: `?StringCchCopyA@@YAJPEAD_KPEBD@Z`
- size: `98`
- prototype: `__int64 __fastcall(char *, unsigned __int64, const char *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180018d00`
- `0x180018e00`
- `0x180018fa0`
- `0x180019460`
- `0x180019520`
- `0x180019690`
- `0x180019970`
- `0x180037a20`

## callees

- `0x180019900`

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
0x180019900  test    rdx, rdx
0x180019903  jz      short loc_180019954
0x180019905  cmp     rdx, 7FFFFFFFh
0x18001990c  jbe     short loc_180019915
0x18001990e  mov     eax, 80070057h
0x180019913  jmp     short loc_18001995E
0x180019915  mov     eax, 7FFFFFFEh
0x18001991a  test    rax, rax
0x18001991d  jz      short loc_180019939
0x18001991f  mov     r9b, [r8]
0x180019922  test    r9b, r9b
0x180019925  jz      short loc_180019939
0x180019927  mov     [rcx], r9b
0x18001992a  inc     r8
0x18001992d  inc     rcx
0x180019930  dec     rax
0x180019933  sub     rdx, 1
0x180019937  jnz     short loc_18001991A
0x180019939  test    rdx, rdx
0x18001993c  lea     rax, [rcx-1]
0x180019940  cmovnz  rax, rcx
0x180019944  neg     rdx
0x180019947  mov     byte ptr [rax], 0
0x18001994a  sbb     eax, eax
0x18001994c  not     eax
0x18001994e  and     eax, 8007007Ah
0x180019953  retn
0x180019954  mov     eax, 80070057h
0x180019959  test    rdx, rdx
0x18001995c  jz      short locret_180019961
0x18001995e  mov     byte ptr [rcx], 0
0x180019961  retn
```
