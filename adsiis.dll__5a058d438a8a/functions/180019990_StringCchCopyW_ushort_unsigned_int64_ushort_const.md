# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180019990`
- end: `0x1800199fb`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800198b4`
- `0x180019a04`
- `0x180019a80`
- `0x18001a290`
- `0x18001a578`
- `0x18001c580`

## callees

- `0x180019990`

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
0x180019990  xor     r10d, r10d
0x180019993  mov     r9, rcx
0x180019996  test    rdx, rdx
0x180019999  jz      short loc_1800199EC
0x18001999b  cmp     rdx, 7FFFFFFFh
0x1800199a2  jbe     short loc_1800199AB
0x1800199a4  mov     eax, 80070057h
0x1800199a9  jmp     short loc_1800199F6
0x1800199ab  mov     eax, 7FFFFFFEh
0x1800199b0  test    rax, rax
0x1800199b3  jz      short loc_1800199D3
0x1800199b5  movzx   ecx, word ptr [r8]
0x1800199b9  test    cx, cx
0x1800199bc  jz      short loc_1800199D3
0x1800199be  mov     [r9], cx
0x1800199c2  add     r8, 2
0x1800199c6  add     r9, 2
0x1800199ca  dec     rax
0x1800199cd  sub     rdx, 1
0x1800199d1  jnz     short loc_1800199B0
0x1800199d3  test    rdx, rdx
0x1800199d6  lea     rcx, [r9-2]
0x1800199da  cmovnz  rcx, r9
0x1800199de  neg     rdx
0x1800199e1  sbb     eax, eax
0x1800199e3  not     eax
0x1800199e5  and     eax, 8007007Ah
0x1800199ea  jmp     short loc_1800199F6
0x1800199ec  mov     eax, 80070057h
0x1800199f1  test    rdx, rdx
0x1800199f4  jz      short locret_1800199FA
0x1800199f6  mov     [rcx], r10w
0x1800199fa  retn
```
