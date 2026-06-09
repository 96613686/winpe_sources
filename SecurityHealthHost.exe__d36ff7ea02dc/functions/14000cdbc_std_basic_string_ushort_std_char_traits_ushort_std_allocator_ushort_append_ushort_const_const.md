# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::append(ushort const * const)

- ea: `0x14000cdbc`
- end: `0x14000ce3b`
- name: `?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z`
- size: `127`
- prototype: `void **__fastcall(void **Src, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000c688`

## callees

- `0x14000c4a0`
- `0x14000cdbc`
- `0x14000fa8c`

## string_xrefs

- `0x14000ce04`: `\MsMpLics.dll`

## pseudocode

```c
void **__fastcall std::wstring::append(void **Src, __int64 a2, __int64 a3)
{
  void **v3; // rbx
  void *v4; // rcx
  bool v5; // cc
  __int64 v6; // rsi
  _WORD *v7; // rdi

  v3 = Src;
  v4 = Src[2];
  if ( (unsigned __int64)((_BYTE *)v3[3] - (_BYTE *)v4) < 0xD )
    return std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
             v3,
             0xDu,
             a3);
  v5 = (unsigned __int64)v3[3] <= 7;
  v6 = (__int64)v4 + 13;
  v3[2] = (char *)v4 + 13;
  if ( v5 )
    v7 = v3;
  else
    v7 = *v3;
  memmove_0(&v7[(_QWORD)v4], L"\\MsMpLics.dll", 0x1Au);
  v7[v6] = 0;
  return v3;
}

```

## disassembly

```asm
0x14000cdbc  mov     [rsp+arg_0], rbx
0x14000cdc1  mov     [rsp+arg_8], rsi
0x14000cdc6  push    rdi
0x14000cdc7  sub     rsp, 30h
0x14000cdcb  mov     rbx, rcx
0x14000cdce  mov     edx, 0Dh
0x14000cdd3  mov     rcx, [rcx+10h]
0x14000cdd7  mov     rax, [rbx+18h]
0x14000cddb  sub     rax, rcx
0x14000cdde  cmp     rax, rdx
0x14000cde1  jb      short loc_14000CE18
0x14000cde3  cmp     qword ptr [rbx+18h], 7
0x14000cde8  lea     rsi, [rcx+0Dh]
0x14000cdec  mov     [rbx+10h], rsi
0x14000cdf0  jbe     short loc_14000CDF7
0x14000cdf2  mov     rdi, [rbx]
0x14000cdf5  jmp     short loc_14000CDFA
0x14000cdf7  mov     rdi, rbx
0x14000cdfa  lea     rcx, [rdi+rcx*2]; void *
0x14000cdfe  mov     r8d, 1Ah; Size
0x14000ce04  lea     rdx, aMsmplicsDll_0; "\\MsMpLics.dll"
0x14000ce0b  call    memmove_0
0x14000ce10  xor     eax, eax
0x14000ce12  mov     [rdi+rsi*2], ax
0x14000ce16  jmp     short loc_14000CE28
0x14000ce18  mov     rcx, rbx; Src
0x14000ce1b  mov     [rsp+38h+var_18], rdx; __int64
0x14000ce20  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x14000ce25  mov     rbx, rax
0x14000ce28  mov     rsi, [rsp+38h+arg_8]
0x14000ce2d  mov     rax, rbx
0x14000ce30  mov     rbx, [rsp+38h+arg_0]
0x14000ce35  add     rsp, 30h
0x14000ce39  pop     rdi
0x14000ce3a  retn
```
