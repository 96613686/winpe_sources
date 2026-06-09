# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)

- ea: `0x180005954`
- end: `0x180005a0b`
- name: `??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z`
- size: `183`
- prototype: `__int64 __fastcall(__int64, const void *, unsigned __int64)`
- caller_count: `23`
- callee_count: `4`
- tags: ``

## callers

- `0x180002320`
- `0x180007594`
- `0x18000afac`
- `0x18000c32c`
- `0x180010768`
- `0x180011534`
- `0x180011d10`
- `0x1800140e0`
- `0x180014508`
- `0x180014788`
- `0x180016ae0`
- `0x180017328`
- `0x180017e84`
- `0x180018234`
- `0x180019168`
- `0x18001b728`
- `0x18001f49c`
- `0x180022a60`
- `0x180023f40`
- `0x180024388`
- `0x180024b28`
- `0x18002502c`
- `0x180025c30`

## callees

- `0x180004100`
- `0x1800058dc`
- `0x180005954`
- `0x18000a844`

## pseudocode

```c
__int64 __fastcall std::wstring::_Construct<1,unsigned short const *>(__int64 a1, const void *a2, unsigned __int64 a3)
{
  __int64 v5; // rdx
  _QWORD *v6; // rsi
  __int64 v7; // rbx
  __int64 result; // rax
  _QWORD *v9; // rax
  __int64 v10; // rcx
  _QWORD *v11; // rdi
  size_t v12; // rbx
  __int64 v13[5]; // [rsp+20h] [rbp-28h] BYREF

  v5 = 0x7FFFFFFFFFFFFFFELL;
  v6 = (_QWORD *)a1;
  if ( a3 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( a3 > 7 )
  {
    if ( (a3 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      a1 = 10;
      v5 = a3 | 7;
      if ( (a3 | 7) < 0xA )
        v5 = 10;
    }
    v13[0] = v5;
    v9 = std::wstring::_Allocate_for_capacity<0>(a1, v13);
    v10 = v13[0];
    v6[2] = a3;
    v11 = v9;
    v6[3] = v10;
    v12 = 2 * a3;
    *v6 = v9;
    memcpy_0(v9, a2, v12);
    result = 0;
    *(_WORD *)((char *)v11 + v12) = 0;
  }
  else
  {
    *(_QWORD *)(a1 + 16) = a3;
    v7 = 2 * a3;
    *(_QWORD *)(a1 + 24) = 7;
    memcpy_0((void *)a1, a2, 2 * a3);
    result = 0;
    *(_WORD *)((char *)v6 + v7) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180005954  mov     [rsp+arg_18], rbx
0x180005959  push    rbp
0x18000595a  push    rsi
0x18000595b  push    rdi
0x18000595c  sub     rsp, 30h
0x180005960  mov     rbp, rdx
0x180005963  mov     rbx, r8
0x180005966  mov     rdx, 7FFFFFFFFFFFFFFEh
0x180005970  mov     rsi, rcx
0x180005973  cmp     r8, rdx
0x180005976  ja      loc_180005A05
0x18000597c  cmp     rbx, 7
0x180005980  ja      short loc_1800059A4
0x180005982  mov     [rcx+10h], rbx
0x180005986  mov     rdx, rbp; Src
0x180005989  add     rbx, rbx
0x18000598c  mov     qword ptr [rcx+18h], 7
0x180005994  mov     r8, rbx; Size
0x180005997  call    memcpy_0
0x18000599c  xor     eax, eax
0x18000599e  mov     [rbx+rsi], ax
0x1800059a2  jmp     short loc_1800059F8
0x1800059a4  mov     rax, rbx
0x1800059a7  or      rax, 7
0x1800059ab  cmp     rax, rdx
0x1800059ae  ja      short loc_1800059BF
0x1800059b0  mov     ecx, 0Ah
0x1800059b5  mov     rdx, rax
0x1800059b8  cmp     rax, rcx
0x1800059bb  cmovb   rdx, rcx
0x1800059bf  mov     [rsp+48h+var_28], rdx
0x1800059c4  lea     rdx, [rsp+48h+var_28]
0x1800059c9  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x1800059ce  mov     rcx, [rsp+48h+var_28]
0x1800059d3  mov     rdx, rbp; Src
0x1800059d6  mov     [rsi+10h], rbx
0x1800059da  mov     rdi, rax
0x1800059dd  mov     [rsi+18h], rcx
0x1800059e1  add     rbx, rbx
0x1800059e4  mov     rcx, rax; void *
0x1800059e7  mov     [rsi], rax
0x1800059ea  mov     r8, rbx; Size
0x1800059ed  call    memcpy_0
0x1800059f2  xor     eax, eax
0x1800059f4  mov     [rbx+rdi], ax
0x1800059f8  mov     rbx, [rsp+48h+arg_18]
0x1800059fd  add     rsp, 30h
0x180005a01  pop     rdi
0x180005a02  pop     rsi
0x180005a03  pop     rbp
0x180005a04  retn
0x180005a05  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
