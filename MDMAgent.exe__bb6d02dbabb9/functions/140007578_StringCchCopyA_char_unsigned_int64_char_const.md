# StringCchCopyA(char *,unsigned __int64,char const *)

- ea: `0x140007578`
- end: `0x1400075db`
- name: `?StringCchCopyA@@YAJPEAD_KPEBD@Z`
- size: `99`
- prototype: `__int64 __fastcall(char *, unsigned __int64, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140005950`
- `0x140018d74`

## callees

- `0x140007578`

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
0x140007578  test    rdx, rdx
0x14000757b  jz      short loc_1400075CD
0x14000757d  cmp     rdx, 7FFFFFFFh
0x140007584  jbe     short loc_14000758D
0x140007586  mov     eax, 80070057h
0x14000758b  jmp     short loc_1400075D7
0x14000758d  mov     eax, 7FFFFFFEh
0x140007592  test    rax, rax
0x140007595  jz      short loc_1400075B1
0x140007597  mov     r9b, [r8]
0x14000759a  test    r9b, r9b
0x14000759d  jz      short loc_1400075B1
0x14000759f  mov     [rcx], r9b
0x1400075a2  inc     r8
0x1400075a5  inc     rcx
0x1400075a8  dec     rax
0x1400075ab  sub     rdx, 1
0x1400075af  jnz     short loc_140007592
0x1400075b1  test    rdx, rdx
0x1400075b4  lea     rax, [rcx-1]
0x1400075b8  cmovnz  rax, rcx
0x1400075bc  neg     rdx
0x1400075bf  mov     byte ptr [rax], 0
0x1400075c2  sbb     eax, eax
0x1400075c4  not     eax
0x1400075c6  and     eax, 8007007Ah
0x1400075cb  retn
0x1400075cd  mov     eax, 80070057h
0x1400075d2  test    rdx, rdx
0x1400075d5  jz      short locret_1400075DA
0x1400075d7  mov     byte ptr [rcx], 0
0x1400075da  retn
```
