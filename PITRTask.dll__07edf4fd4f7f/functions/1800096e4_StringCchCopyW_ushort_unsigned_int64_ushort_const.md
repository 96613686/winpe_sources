# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800096e4`
- end: `0x18000974f`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fe60`

## callees

- `0x1800096e4`

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
0x1800096e4  xor     r10d, r10d
0x1800096e7  mov     r9, rcx
0x1800096ea  test    rdx, rdx
0x1800096ed  jz      short loc_180009740
0x1800096ef  cmp     rdx, 7FFFFFFFh
0x1800096f6  jbe     short loc_1800096FF
0x1800096f8  mov     eax, 80070057h
0x1800096fd  jmp     short loc_18000974A
0x1800096ff  mov     eax, 7FFFFFFEh
0x180009704  test    rax, rax
0x180009707  jz      short loc_180009727
0x180009709  movzx   ecx, word ptr [r8]
0x18000970d  test    cx, cx
0x180009710  jz      short loc_180009727
0x180009712  mov     [r9], cx
0x180009716  add     r8, 2
0x18000971a  add     r9, 2
0x18000971e  dec     rax
0x180009721  sub     rdx, 1
0x180009725  jnz     short loc_180009704
0x180009727  test    rdx, rdx
0x18000972a  lea     rcx, [r9-2]
0x18000972e  cmovnz  rcx, r9
0x180009732  neg     rdx
0x180009735  sbb     eax, eax
0x180009737  not     eax
0x180009739  and     eax, 8007007Ah
0x18000973e  jmp     short loc_18000974A
0x180009740  mov     eax, 80070057h
0x180009745  test    rdx, rdx
0x180009748  jz      short locret_18000974E
0x18000974a  mov     [rcx], r10w
0x18000974e  retn
```
