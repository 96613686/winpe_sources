# StringCchCopyA(char *,unsigned __int64,char const *)

- ea: `0x1400072bc`
- end: `0x14000731e`
- name: `?StringCchCopyA@@YAJPEAD_KPEBD@Z`
- size: `98`
- prototype: `__int64 __fastcall(char *, unsigned __int64, char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400057a0`
- `0x140018060`

## callees

- `0x1400072bc`

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
0x1400072bc  test    rdx, rdx
0x1400072bf  jz      short loc_140007310
0x1400072c1  cmp     rdx, 7FFFFFFFh
0x1400072c8  jbe     short loc_1400072D1
0x1400072ca  mov     eax, 80070057h
0x1400072cf  jmp     short loc_14000731A
0x1400072d1  mov     eax, 7FFFFFFEh
0x1400072d6  test    rax, rax
0x1400072d9  jz      short loc_1400072F5
0x1400072db  mov     r9b, [r8]
0x1400072de  test    r9b, r9b
0x1400072e1  jz      short loc_1400072F5
0x1400072e3  mov     [rcx], r9b
0x1400072e6  inc     r8
0x1400072e9  inc     rcx
0x1400072ec  dec     rax
0x1400072ef  sub     rdx, 1
0x1400072f3  jnz     short loc_1400072D6
0x1400072f5  test    rdx, rdx
0x1400072f8  lea     rax, [rcx-1]
0x1400072fc  cmovnz  rax, rcx
0x140007300  neg     rdx
0x140007303  mov     byte ptr [rax], 0
0x140007306  sbb     eax, eax
0x140007308  not     eax
0x14000730a  and     eax, 8007007Ah
0x14000730f  retn
0x140007310  mov     eax, 80070057h
0x140007315  test    rdx, rdx
0x140007318  jz      short locret_14000731D
0x14000731a  mov     byte ptr [rcx], 0
0x14000731d  retn
```
