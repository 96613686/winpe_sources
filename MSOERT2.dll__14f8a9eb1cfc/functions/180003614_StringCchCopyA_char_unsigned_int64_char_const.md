# StringCchCopyA(char *,unsigned __int64,char const *)

- ea: `0x180003614`
- end: `0x180003676`
- name: `?StringCchCopyA@@YAJPEAD_KPEBD@Z`
- size: `98`
- prototype: `__int64 __fastcall(char *, unsigned __int64, const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x18000367c`
- `0x180003f80`
- `0x1800056e0`
- `0x1800089d0`
- `0x1800095a8`
- `0x18000b390`
- `0x18000c330`
- `0x180012554`
- `0x180012650`

## callees

- `0x180003614`

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
0x180003614  test    rdx, rdx
0x180003617  jz      short loc_180003668
0x180003619  cmp     rdx, 7FFFFFFFh
0x180003620  jbe     short loc_180003629
0x180003622  mov     eax, 80070057h
0x180003627  jmp     short loc_180003672
0x180003629  mov     eax, 7FFFFFFEh
0x18000362e  test    rax, rax
0x180003631  jz      short loc_18000364D
0x180003633  mov     r9b, [r8]
0x180003636  test    r9b, r9b
0x180003639  jz      short loc_18000364D
0x18000363b  mov     [rcx], r9b
0x18000363e  inc     r8
0x180003641  inc     rcx
0x180003644  dec     rax
0x180003647  sub     rdx, 1
0x18000364b  jnz     short loc_18000362E
0x18000364d  test    rdx, rdx
0x180003650  lea     rax, [rcx-1]
0x180003654  cmovnz  rax, rcx
0x180003658  neg     rdx
0x18000365b  mov     byte ptr [rax], 0
0x18000365e  sbb     eax, eax
0x180003660  not     eax
0x180003662  and     eax, 8007007Ah
0x180003667  retn
0x180003668  mov     eax, 80070057h
0x18000366d  test    rdx, rdx
0x180003670  jz      short locret_180003675
0x180003672  mov     byte ptr [rcx], 0
0x180003675  retn
```
