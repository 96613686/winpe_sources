# VersionCompare(ushort const *,ushort const *)

- ea: `0x180019068`
- end: `0x18001916d`
- name: `?VersionCompare@@YA?AW4VersionCompareResult@@PEBG0@Z`
- size: `261`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018ac4`
- `0x180018b8c`

## callees

- `0x180018a50`
- `0x180019068`

## pseudocode

```c
__int64 __fastcall VersionCompare(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  signed __int64 v2; // r8
  const unsigned __int16 *v5; // rax
  int v6; // edx
  int v7; // ecx
  bool v8; // cf
  bool v9; // cc
  unsigned int v11; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v12; // [rsp+34h] [rbp-1Ch] BYREF
  unsigned int v13; // [rsp+38h] [rbp-18h] BYREF
  unsigned int v14; // [rsp+3Ch] [rbp-14h] BYREF
  unsigned int v15; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v16[3]; // [rsp+44h] [rbp-Ch] BYREF
  unsigned int v17; // [rsp+70h] [rbp+20h] BYREF
  unsigned int v18; // [rsp+78h] [rbp+28h] BYREF

  v13 = 0;
  v2 = (char *)a2 - (char *)a1;
  v14 = 0;
  v17 = 0;
  v18 = 0;
  v5 = a1;
  v11 = 0;
  v12 = 0;
  v15 = 0;
  v16[0] = 0;
  do
  {
    v6 = *(const unsigned __int16 *)((char *)v5 + v2);
    v7 = *v5 - v6;
    if ( v7 )
      break;
    ++v5;
  }
  while ( v6 );
  if ( !v7 )
    return 0;
  if ( (unsigned int)GetVersionElements(a1, &v13, &v17, &v11, &v15) == 4
    && (unsigned int)GetVersionElements(a2, &v14, &v18, &v12, v16) == 4 )
  {
    v8 = v13 < v14;
    v9 = v13 <= v14;
    if ( v13 == v14 )
    {
      if ( v17 == v18 && v11 == v12 )
        return v16[0] < v15 ? 2 : 0;
      v8 = v13 < v14;
      v9 = v13 <= v14;
    }
    if ( !v8 )
    {
      if ( !v9 )
        return 4;
      if ( v17 >= v18 )
      {
        if ( v17 <= v18 )
        {
          if ( v11 >= v12 )
          {
            if ( v11 <= v12 )
              return v16[0] < v15 ? 2 : 0;
            return 4;
          }
          return 3;
        }
        return 4;
      }
    }
    return 3;
  }
  return 1;
}

```

## disassembly

```asm
0x180019068  mov     [rsp-8+arg_0], rbx
0x18001906d  push    rbp
0x18001906e  mov     rbp, rsp
0x180019071  sub     rsp, 50h
0x180019075  xor     r9d, r9d
0x180019078  mov     r8, rdx
0x18001907b  mov     [rbp+var_18], r9d
0x18001907f  sub     r8, rcx
0x180019082  mov     [rbp+var_14], r9d
0x180019086  mov     rbx, rdx
0x180019089  mov     [rbp+arg_10], r9d
0x18001908d  mov     r10, rcx
0x180019090  mov     [rbp+arg_18], r9d
0x180019094  mov     rax, rcx
0x180019097  mov     [rbp+var_20], r9d
0x18001909b  mov     [rbp+var_1C], r9d
0x18001909f  mov     [rbp+var_10], r9d
0x1800190a3  mov     [rbp+var_C], r9d
0x1800190a7  movzx   ecx, word ptr [rax]
0x1800190aa  movzx   edx, word ptr [rax+r8]
0x1800190af  sub     ecx, edx
0x1800190b1  jnz     short loc_1800190BB
0x1800190b3  add     rax, 2
0x1800190b7  test    edx, edx
0x1800190b9  jnz     short loc_1800190A7
0x1800190bb  test    ecx, ecx
0x1800190bd  jz      loc_180019160
0x1800190c3  lea     rax, [rbp+var_10]
0x1800190c7  mov     rcx, r10; unsigned __int16 *
0x1800190ca  lea     r9, [rbp+var_20]; unsigned int *
0x1800190ce  mov     [rsp+50h+var_30], rax; unsigned int *
0x1800190d3  lea     r8, [rbp+arg_10]; unsigned int *
0x1800190d7  lea     rdx, [rbp+var_18]; unsigned int *
0x1800190db  call    ?GetVersionElements@@YAHPEBGAEAK111@Z; GetVersionElements(ushort const *,ulong &,ulong &,ulong &,ulong &)
0x1800190e0  cmp     eax, 4
0x1800190e3  jnz     short loc_180019159
0x1800190e5  lea     rax, [rbp+var_C]
0x1800190e9  mov     rcx, rbx; unsigned __int16 *
0x1800190ec  lea     r9, [rbp+var_1C]; unsigned int *
0x1800190f0  mov     [rsp+50h+var_30], rax; unsigned int *
0x1800190f5  lea     r8, [rbp+arg_18]; unsigned int *
0x1800190f9  lea     rdx, [rbp+var_14]; unsigned int *
0x1800190fd  call    ?GetVersionElements@@YAHPEBGAEAK111@Z; GetVersionElements(ushort const *,ulong &,ulong &,ulong &,ulong &)
0x180019102  cmp     eax, 4
0x180019105  jnz     short loc_180019159
0x180019107  mov     r9d, [rbp+var_18]
0x18001910b  mov     r10d, [rbp+var_14]
0x18001910f  mov     edx, [rbp+arg_10]
0x180019112  mov     r8d, [rbp+arg_18]
0x180019116  mov     eax, [rbp+var_20]
0x180019119  mov     ecx, [rbp+var_1C]
0x18001911c  cmp     r9d, r10d
0x18001911f  jnz     short loc_18001912D
0x180019121  cmp     edx, r8d
0x180019124  jnz     short loc_18001912A
0x180019126  cmp     eax, ecx
0x180019128  jz      short loc_18001913E
0x18001912a  cmp     r9d, r10d
0x18001912d  jb      short loc_180019152
0x18001912f  ja      short loc_18001914B
0x180019131  cmp     edx, r8d
0x180019134  jb      short loc_180019152
0x180019136  ja      short loc_18001914B
0x180019138  cmp     eax, ecx
0x18001913a  jb      short loc_180019152
0x18001913c  ja      short loc_18001914B
0x18001913e  mov     eax, [rbp+var_10]
0x180019141  cmp     [rbp+var_C], eax
0x180019144  sbb     eax, eax
0x180019146  and     eax, 2
0x180019149  jmp     short loc_180019162
0x18001914b  mov     eax, 4
0x180019150  jmp     short loc_180019162
0x180019152  mov     eax, 3
0x180019157  jmp     short loc_180019162
0x180019159  mov     eax, 1
0x18001915e  jmp     short loc_180019162
0x180019160  xor     eax, eax
0x180019162  mov     rbx, [rsp+50h+arg_0]
0x180019167  add     rsp, 50h
0x18001916b  pop     rbp
0x18001916c  retn
```
