# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800068c0`
- end: `0x18000692b`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005d80`
- `0x18001639c`

## callees

- `0x1800068c0`

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
0x1800068c0  xor     r10d, r10d
0x1800068c3  mov     r9, rcx
0x1800068c6  test    rdx, rdx
0x1800068c9  jz      short loc_18000691C
0x1800068cb  cmp     rdx, 7FFFFFFFh
0x1800068d2  jbe     short loc_1800068DB
0x1800068d4  mov     eax, 80070057h
0x1800068d9  jmp     short loc_180006926
0x1800068db  mov     eax, 7FFFFFFEh
0x1800068e0  test    rax, rax
0x1800068e3  jz      short loc_180006903
0x1800068e5  movzx   ecx, word ptr [r8]
0x1800068e9  test    cx, cx
0x1800068ec  jz      short loc_180006903
0x1800068ee  mov     [r9], cx
0x1800068f2  add     r8, 2
0x1800068f6  add     r9, 2
0x1800068fa  dec     rax
0x1800068fd  sub     rdx, 1
0x180006901  jnz     short loc_1800068E0
0x180006903  test    rdx, rdx
0x180006906  lea     rcx, [r9-2]
0x18000690a  cmovnz  rcx, r9
0x18000690e  neg     rdx
0x180006911  sbb     eax, eax
0x180006913  not     eax
0x180006915  and     eax, 8007007Ah
0x18000691a  jmp     short loc_180006926
0x18000691c  mov     eax, 80070057h
0x180006921  test    rdx, rdx
0x180006924  jz      short locret_18000692A
0x180006926  mov     [rcx], r10w
0x18000692a  retn
```
