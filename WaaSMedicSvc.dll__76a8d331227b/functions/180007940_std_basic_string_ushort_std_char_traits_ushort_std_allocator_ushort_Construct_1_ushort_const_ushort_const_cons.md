# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)

- ea: `0x180007940`
- end: `0x1800079ed`
- name: `??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z`
- size: `173`
- prototype: `__int64 __fastcall(_QWORD *, const void *, unsigned __int64)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x18000865c`
- `0x180009d10`
- `0x180009e98`
- `0x180009fc8`
- `0x18000aa84`
- `0x18000b4e8`

## callees

- `0x1800077d8`
- `0x180007940`
- `0x18000b37c`
- `0x18000bd94`

## pseudocode

```c
__int64 __fastcall std::wstring::_Construct<1,unsigned short const *>(_QWORD *a1, const void *a2, unsigned __int64 a3)
{
  __int64 v3; // rax
  __int64 v7; // rbx
  __int64 result; // rax
  unsigned __int64 v9; // rcx
  _QWORD *v10; // rax
  __int64 v11; // rcx
  _QWORD *v12; // rdi
  size_t v13; // rbx
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF

  v3 = 0x7FFFFFFFFFFFFFFELL;
  if ( a3 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( a3 > 7 )
  {
    v9 = a3 | 7;
    if ( (a3 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      v3 = a3 | 7;
      if ( v9 < 0xA )
        v3 = 10;
    }
    v14 = v3;
    v10 = std::wstring::_Allocate_for_capacity<0>(v9, &v14);
    v11 = v14;
    a1[2] = a3;
    v12 = v10;
    a1[3] = v11;
    v13 = 2 * a3;
    *a1 = v10;
    memcpy_0(v10, a2, v13);
    result = 0;
    *(_WORD *)((char *)v12 + v13) = 0;
  }
  else
  {
    a1[2] = a3;
    v7 = 2 * a3;
    a1[3] = 7;
    memcpy_0(a1, a2, 2 * a3);
    result = 0;
    *(_WORD *)((char *)a1 + v7) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180007940  push    rbx
0x180007942  push    rbp
0x180007943  push    rsi
0x180007944  push    rdi
0x180007945  sub     rsp, 28h
0x180007949  mov     rax, 7FFFFFFFFFFFFFFEh
0x180007953  mov     rbx, r8
0x180007956  mov     rbp, rdx
0x180007959  mov     rsi, rcx
0x18000795c  cmp     r8, rax
0x18000795f  ja      loc_1800079E7
0x180007965  cmp     rbx, 7
0x180007969  ja      short loc_18000798A
0x18000796b  mov     [rcx+10h], rbx
0x18000796f  add     rbx, rbx
0x180007972  mov     r8, rbx; Size
0x180007975  mov     qword ptr [rcx+18h], 7
0x18000797d  call    memcpy_0
0x180007982  xor     eax, eax
0x180007984  mov     [rbx+rsi], ax
0x180007988  jmp     short loc_1800079DE
0x18000798a  mov     rcx, rbx
0x18000798d  or      rcx, 7
0x180007991  cmp     rcx, rax
0x180007994  ja      short loc_1800079A5
0x180007996  mov     edx, 0Ah
0x18000799b  mov     rax, rcx
0x18000799e  cmp     rcx, rdx
0x1800079a1  cmovb   rax, rdx
0x1800079a5  lea     rdx, [rsp+48h+arg_0]
0x1800079aa  mov     [rsp+48h+arg_0], rax
0x1800079af  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x1800079b4  mov     rcx, [rsp+48h+arg_0]
0x1800079b9  mov     rdx, rbp; Src
0x1800079bc  mov     [rsi+10h], rbx
0x1800079c0  mov     rdi, rax
0x1800079c3  mov     [rsi+18h], rcx
0x1800079c7  add     rbx, rbx
0x1800079ca  mov     rcx, rax; void *
0x1800079cd  mov     [rsi], rax
0x1800079d0  mov     r8, rbx; Size
0x1800079d3  call    memcpy_0
0x1800079d8  xor     eax, eax
0x1800079da  mov     [rbx+rdi], ax
0x1800079de  add     rsp, 28h
0x1800079e2  pop     rdi
0x1800079e3  pop     rsi
0x1800079e4  pop     rbp
0x1800079e5  pop     rbx
0x1800079e6  retn
0x1800079e7  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
