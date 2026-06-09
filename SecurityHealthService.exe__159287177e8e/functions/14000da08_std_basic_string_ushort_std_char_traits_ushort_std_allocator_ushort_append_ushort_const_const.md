# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::append(ushort const * const)

- ea: `0x14000da08`
- end: `0x14000da87`
- name: `?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z`
- size: `127`
- prototype: `void **__fastcall(void **Src, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000d15c`

## callees

- `0x14000ce04`
- `0x14000da08`
- `0x1400121ec`

## string_xrefs

- `0x14000da50`: `\MsMpLics.dll`

## pseudocode

```c
void **__fastcall std::wstring::append(void **Src, __int64 a2, __int64 a3, __int64 a4)
{
  void **v4; // rbx
  void *v5; // rcx
  bool v6; // cc
  __int64 v7; // rsi
  _WORD *v8; // rdi

  v4 = Src;
  v5 = Src[2];
  if ( (unsigned __int64)((_BYTE *)v4[3] - (_BYTE *)v5) < 0xD )
    return std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
             v4,
             0xDu,
             a3,
             a4,
             13);
  v6 = (unsigned __int64)v4[3] <= 7;
  v7 = (__int64)v5 + 13;
  v4[2] = (char *)v5 + 13;
  if ( v6 )
    v8 = v4;
  else
    v8 = *v4;
  memmove_0(&v8[(_QWORD)v5], L"\\MsMpLics.dll", 0x1Au);
  v8[v7] = 0;
  return v4;
}

```

## disassembly

```asm
0x14000da08  mov     [rsp+arg_0], rbx
0x14000da0d  mov     [rsp+arg_8], rsi
0x14000da12  push    rdi
0x14000da13  sub     rsp, 30h
0x14000da17  mov     rbx, rcx
0x14000da1a  mov     edx, 0Dh
0x14000da1f  mov     rcx, [rcx+10h]
0x14000da23  mov     rax, [rbx+18h]
0x14000da27  sub     rax, rcx
0x14000da2a  cmp     rax, rdx
0x14000da2d  jb      short loc_14000DA64
0x14000da2f  cmp     qword ptr [rbx+18h], 7
0x14000da34  lea     rsi, [rcx+0Dh]
0x14000da38  mov     [rbx+10h], rsi
0x14000da3c  jbe     short loc_14000DA43
0x14000da3e  mov     rdi, [rbx]
0x14000da41  jmp     short loc_14000DA46
0x14000da43  mov     rdi, rbx
0x14000da46  lea     rcx, [rdi+rcx*2]; void *
0x14000da4a  mov     r8d, 1Ah; Size
0x14000da50  lea     rdx, aMsmplicsDll_0; "\\MsMpLics.dll"
0x14000da57  call    memmove_0
0x14000da5c  xor     eax, eax
0x14000da5e  mov     [rdi+rsi*2], ax
0x14000da62  jmp     short loc_14000DA74
0x14000da64  mov     rcx, rbx; Src
0x14000da67  mov     [rsp+38h+var_18], rdx; __int64
0x14000da6c  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x14000da71  mov     rbx, rax
0x14000da74  mov     rsi, [rsp+38h+arg_8]
0x14000da79  mov     rax, rbx
0x14000da7c  mov     rbx, [rsp+38h+arg_0]
0x14000da81  add     rsp, 30h
0x14000da85  pop     rdi
0x14000da86  retn
```
