# StreamFindSample

- ea: `0x1800152e4`
- end: `0x1800153cc`
- name: `StreamFindSample`
- size: `232`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180009a70`
- `0x18000acf0`
- `0x18000b0f0`
- `0x18000b368`

## callees

- `0x180014a68`
- `0x1800152e4`

## pseudocode

```c
__int64 __fastcall StreamFindSample(__int64 a1, signed int a2, __int16 a3)
{
  signed int v3; // r9d
  int v4; // ebx
  int v5; // eax
  __int64 result; // rax

  v3 = *(_DWORD *)(a1 + 28);
  if ( a2 < v3 || a2 >= *(_DWORD *)(a1 + 32) )
    return 4294967196LL;
  v4 = a3 & 0xF000;
  if ( (a3 & 0xF000) == 0 )
  {
    v5 = a3 & 0xF0;
    switch ( v5 )
    {
      case 16:
        if ( *(_DWORD *)(a1 + 48) != *(_DWORD *)(a1 + 44) )
          return SearchIndex((struct STREAMINDEX *)a1);
        break;
      case 32:
        if ( *(_DWORD *)(a1 + 56) )
          return SearchIndex((struct STREAMINDEX *)a1);
        break;
      case 64:
        if ( *(_DWORD *)(a1 + 52) == v4 )
        {
          if ( (a3 & 1) == 0 || a2 <= v3 )
            return (unsigned int)v3;
          return 4294967196LL;
        }
        return SearchIndex((struct STREAMINDEX *)a1);
    }
    return (unsigned int)a2;
  }
  if ( (unsigned int)SearchIndex((struct STREAMINDEX *)a1) == -100 )
    return 4294967196LL;
  switch ( v4 )
  {
    case 4096:
      return 0;
    case 8192:
      return 8;
    case 12288:
      return 0;
  }
  result = 0;
  if ( v4 != 0x4000 )
    return 4294967196LL;
  return result;
}

```

## disassembly

```asm
0x1800152e4  mov     [rsp+arg_0], rbx
0x1800152e9  push    rdi
0x1800152ea  sub     rsp, 40h
0x1800152ee  mov     r9d, [rcx+1Ch]
0x1800152f2  mov     edi, 0FFFFFF9Ch
0x1800152f7  cmp     edx, r9d
0x1800152fa  jl      loc_1800153BF
0x180015300  cmp     edx, [rcx+20h]
0x180015303  jge     loc_1800153BF
0x180015309  mov     ebx, r8d
0x18001530c  and     ebx, 0F000h
0x180015312  jnz     short loc_180015360
0x180015314  mov     eax, r8d
0x180015317  and     eax, 0F0h
0x18001531c  cmp     eax, 10h
0x18001531f  jz      short loc_180015354
0x180015321  cmp     eax, 20h ; ' '
0x180015324  jz      short loc_180015344
0x180015326  cmp     eax, 40h ; '@'
0x180015329  jnz     short loc_18001535C
0x18001532b  cmp     [rcx+34h], ebx
0x18001532e  jnz     short loc_18001534A
0x180015330  test    r8b, 1
0x180015334  jz      short loc_18001533F
0x180015336  cmp     edx, r9d
0x180015339  jg      loc_1800153BF
0x18001533f  mov     eax, r9d
0x180015342  jmp     short loc_1800153C1
0x180015344  cmp     dword ptr [rcx+38h], 0
0x180015348  jz      short loc_18001535C
0x18001534a  xor     r9d, r9d
0x18001534d  call    SearchIndex
0x180015352  jmp     short loc_1800153C1
0x180015354  mov     eax, [rcx+2Ch]
0x180015357  cmp     [rcx+30h], eax
0x18001535a  jnz     short loc_18001534A
0x18001535c  mov     eax, edx
0x18001535e  jmp     short loc_1800153C1
0x180015360  xor     eax, eax
0x180015362  lea     r9, [rsp+48h+var_28]
0x180015367  xorps   xmm0, xmm0
0x18001536a  mov     [rsp+48h+var_18], eax
0x18001536e  movups  [rsp+48h+var_28], xmm0
0x180015373  call    SearchIndex
0x180015378  cmp     eax, edi
0x18001537a  jz      short loc_1800153BF
0x18001537c  cmp     ebx, 1000h
0x180015382  jz      short loc_1800153B9
0x180015384  cmp     ebx, 2000h
0x18001538a  jz      short loc_1800153A9
0x18001538c  cmp     ebx, 3000h
0x180015392  jz      short loc_1800153A3
0x180015394  mov     eax, dword ptr [rsp+48h+var_28]
0x180015398  cmp     ebx, 4000h
0x18001539e  cmovnz  eax, edi
0x1800153a1  jmp     short loc_1800153C1
0x1800153a3  mov     eax, dword ptr [rsp+48h+var_28+8]
0x1800153a7  jmp     short loc_1800153C1
0x1800153a9  mov     eax, dword ptr [rsp+48h+var_28+0Ch]
0x1800153ad  cmp     eax, 7FFFFFF7h
0x1800153b2  jg      short loc_1800153BF
0x1800153b4  add     eax, 8
0x1800153b7  jmp     short loc_1800153C1
0x1800153b9  mov     eax, [rsp+48h+var_18]
0x1800153bd  jmp     short loc_1800153C1
0x1800153bf  mov     eax, edi
0x1800153c1  mov     rbx, [rsp+48h+arg_0]
0x1800153c6  add     rsp, 40h
0x1800153ca  pop     rdi
0x1800153cb  retn
```
