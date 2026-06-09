# std::filesystem::path::operator/=(std::filesystem::path const &)

- ea: `0x180009508`
- end: `0x1800097d9`
- name: `??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z`
- size: `721`
- prototype: `std::filesystem *__fastcall(std::filesystem *Src, std::filesystem *this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180009208`

## callees

- `0x180007b54`
- `0x180007ea4`
- `0x18000826c`
- `0x180009508`
- `0x18000a9a4`
- `0x18000b394`
- `0x18000bb9c`
- `0x18000bda0`

## pseudocode

```c
std::filesystem *__fastcall std::filesystem::path::operator/=(std::filesystem *Src, std::filesystem *this)
{
  std::filesystem *v2; // rsi
  std::filesystem *v4; // rcx
  unsigned __int64 v5; // r11
  __int64 v6; // r8
  size_t v7; // r14
  __int64 v8; // rdx
  std::filesystem *v9; // r12
  const unsigned __int16 *root_name_end; // rax
  const unsigned __int16 *v11; // rcx
  std::filesystem *v12; // rbx
  unsigned __int64 v13; // rdx
  std::filesystem *v14; // r11
  const unsigned __int16 *v15; // rbx
  const unsigned __int16 *v16; // rbp
  const unsigned __int16 *v17; // r8
  std::filesystem *v18; // r11
  const unsigned __int16 *v19; // rax
  __int64 v20; // rcx
  const wchar_t *v21; // r11
  __int64 v22; // r14
  const unsigned __int16 *v23; // r13
  unsigned __int64 v24; // rax
  size_t v25; // r8
  std::filesystem *v26; // rbp
  __int64 v27; // rbx
  unsigned __int64 v28; // rbp
  std::filesystem *v29; // rax
  unsigned __int64 v30; // rcx
  std::filesystem *v31; // rax
  __int64 v32; // rcx
  unsigned __int64 v33; // rbx
  bool v34; // cc
  __int64 v35; // rbp
  std::filesystem *v36; // rsi
  unsigned __int64 v38; // [rsp+78h] [rbp+10h]
  unsigned __int64 v39; // [rsp+80h] [rbp+18h]
  const unsigned __int16 *v40; // [rsp+88h] [rbp+20h]

  v2 = this;
  if ( *((_QWORD *)this + 3) <= 7u )
    v4 = this;
  else
    v4 = *(std::filesystem **)this;
  v5 = *((_QWORD *)this + 2);
  v6 = 92;
  v7 = 2 * v5;
  v8 = (__int64)(2 * v5) >> 1;
  if ( v8 < 2 || (*(_DWORD *)v4 & 0xFFFFFFDF) - 3801153 >= 0x1A )
  {
    root_name_end = std::filesystem::_Find_root_name_end(
                      v4,
                      (const unsigned __int16 *const)((char *)v4 + v7),
                      (const unsigned __int16 *const)0x5C);
    if ( v11 == root_name_end )
      goto LABEL_9;
  }
  else if ( v8 < 3 || *((_WORD *)v4 + 2) != 92 && *((_WORD *)v4 + 2) != 47 )
  {
LABEL_9:
    if ( *((_QWORD *)Src + 3) <= 7u )
      v9 = Src;
    else
      v9 = *(std::filesystem **)Src;
    v40 = (const unsigned __int16 *)((char *)v9 + 2 * *((_QWORD *)Src + 2));
    if ( *((_QWORD *)v2 + 3) <= 7u )
      v14 = v2;
    else
      v14 = *(std::filesystem **)v2;
    v15 = (const unsigned __int16 *)((char *)v14 + v7);
    v16 = std::filesystem::_Find_root_name_end(
            v9,
            (const unsigned __int16 *const)v9 + *((_QWORD *)Src + 2),
            (const unsigned __int16 *const)v6);
    v19 = std::filesystem::_Find_root_name_end(v18, v15, v17);
    v22 = (char *)v16 - (char *)v9;
    v23 = v19;
    if ( v21 != v19 )
    {
      v24 = v19 - v21;
      v25 = v22 >> 1;
      v39 = v22 >> 1;
      v38 = v24;
      if ( v24 < v22 >> 1 )
        v25 = v24;
      if ( wmemcmp((const wchar_t *)v9, v21, v25) || v39 < v38 || v39 > v38 )
      {
        if ( Src == v2 )
          return Src;
        v13 = *((_QWORD *)v2 + 2);
        if ( *((_QWORD *)v2 + 3) > 7u )
          v2 = *(std::filesystem **)v2;
        if ( v13 <= *((_QWORD *)Src + 3) )
        {
          if ( *((_QWORD *)Src + 3) <= 7u )
            v26 = Src;
          else
            v26 = *(std::filesystem **)Src;
          v27 = 2 * v13;
          *((_QWORD *)Src + 2) = v13;
          memmove_0(v26, v2, 2 * v13);
          *(_WORD *)((char *)v26 + v27) = 0;
          return Src;
        }
LABEL_21:
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          Src,
          v13,
          v6,
          v2);
        return Src;
      }
    }
    if ( v23 != v15 && (*v23 == 92 || *v23 == 47) )
    {
      v28 = ((char *)v16 - (char *)v9) >> 1;
      if ( *((_QWORD *)Src + 2) < v28 )
        std::_String_val<std::_Simple_types<unsigned short>>::_Xran(v20, 92);
      *((_QWORD *)Src + 2) = v28;
      if ( *((_QWORD *)Src + 3) <= 7u )
        v29 = Src;
      else
        v29 = *(std::filesystem **)Src;
      *((_WORD *)v29 + v28) = 0;
      goto LABEL_59;
    }
    if ( v16 == v40 )
    {
      if ( (__int64)(v22 & 0xFFFFFFFFFFFFFFFEuLL) >= 6 )
        goto LABEL_53;
    }
    else if ( *(v40 - 1) != 92 && *(v40 - 1) != 47 )
    {
LABEL_53:
      v30 = *((_QWORD *)Src + 2);
      if ( v30 >= *((_QWORD *)Src + 3) )
      {
        std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Src);
      }
      else
      {
        *((_QWORD *)Src + 2) = v30 + 1;
        if ( *((_QWORD *)Src + 3) <= 7u )
          v31 = Src;
        else
          v31 = *(std::filesystem **)Src;
        *(_DWORD *)((char *)v31 + 2 * v30) = 92;
      }
    }
LABEL_59:
    v32 = *((_QWORD *)Src + 2);
    v33 = v15 - v23;
    if ( v33 > *((_QWORD *)Src + 3) - v32 )
    {
      std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
        Src,
        v33);
    }
    else
    {
      v34 = *((_QWORD *)Src + 3) <= 7u;
      v35 = v33 + v32;
      *((_QWORD *)Src + 2) = v33 + v32;
      if ( v34 )
        v36 = Src;
      else
        v36 = *(std::filesystem **)Src;
      memmove_0((char *)v36 + 2 * v32, v23, 2 * v33);
      *((_WORD *)v36 + v35) = 0;
    }
    return Src;
  }
  if ( Src == v2 )
    return Src;
  if ( *((_QWORD *)v2 + 3) > 7u )
    v2 = *(std::filesystem **)v2;
  if ( v5 > *((_QWORD *)Src + 3) )
  {
    v13 = v5;
    goto LABEL_21;
  }
  if ( *((_QWORD *)Src + 3) <= 7u )
    v12 = Src;
  else
    v12 = *(std::filesystem **)Src;
  *((_QWORD *)Src + 2) = v5;
  memmove_0(v12, v2, v7);
  *(_WORD *)((char *)v12 + v7) = 0;
  return Src;
}

```

## disassembly

```asm
0x180009508  mov     [rsp+arg_0], rbx
0x18000950d  push    rbp
0x18000950e  push    rsi
0x18000950f  push    rdi
0x180009510  push    r12
0x180009512  push    r13
0x180009514  push    r14
0x180009516  push    r15
0x180009518  sub     rsp, 30h
0x18000951c  cmp     qword ptr [rdx+18h], 7
0x180009521  mov     rsi, rdx
0x180009524  mov     rdi, rcx
0x180009527  jbe     short loc_18000952E
0x180009529  mov     rcx, [rdx]
0x18000952c  jmp     short loc_180009531
0x18000952e  mov     rcx, rsi; this
0x180009531  mov     r11, [rdx+10h]
0x180009535  mov     r8d, 5Ch ; '\'; unsigned __int16 *
0x18000953b  lea     r14, [r11+r11]
0x18000953f  mov     rdx, r14
0x180009542  sar     rdx, 1
0x180009545  cmp     rdx, 2
0x180009549  jl      short loc_18000957A
0x18000954b  mov     eax, [rcx]
0x18000954d  and     eax, 0FFFFFFDFh
0x180009550  sub     eax, 3A0041h
0x180009555  cmp     eax, 1Ah
0x180009558  jnb     short loc_18000957A
0x18000955a  cmp     rdx, 3
0x18000955e  jl      short loc_18000956E
0x180009560  cmp     [rcx+4], r8w
0x180009565  jz      short loc_180009588
0x180009567  cmp     word ptr [rcx+4], 2Fh ; '/'
0x18000956c  jz      short loc_180009588
0x18000956e  cmp     qword ptr [rdi+18h], 7
0x180009573  jbe     short loc_1800095E2
0x180009575  mov     r12, [rdi]
0x180009578  jmp     short loc_1800095E5
0x18000957a  lea     rdx, [r14+rcx]; unsigned __int16 *
0x18000957e  call    ?_Find_root_name_end@filesystem@std@@YAPEBGQEBG0@Z; std::filesystem::_Find_root_name_end(ushort const * const,ushort const * const)
0x180009583  cmp     rcx, rax
0x180009586  jz      short loc_18000956E
0x180009588  cmp     rdi, rsi
0x18000958b  jz      loc_1800097BB
0x180009591  cmp     qword ptr [rsi+18h], 7
0x180009596  jbe     short loc_18000959B
0x180009598  mov     rsi, [rsi]
0x18000959b  cmp     r11, [rdi+18h]
0x18000959f  ja      short loc_1800095CF
0x1800095a1  cmp     qword ptr [rdi+18h], 7
0x1800095a6  jbe     short loc_1800095AD
0x1800095a8  mov     rbx, [rdi]
0x1800095ab  jmp     short loc_1800095B0
0x1800095ad  mov     rbx, rdi
0x1800095b0  mov     r8, r14; Size
0x1800095b3  mov     [rdi+10h], r11
0x1800095b7  mov     rdx, rsi; Src
0x1800095ba  mov     rcx, rbx; void *
0x1800095bd  call    memmove_0
0x1800095c2  xor     r15d, r15d
0x1800095c5  mov     [r14+rbx], r15w
0x1800095ca  jmp     loc_1800097BB
0x1800095cf  mov     rdx, r11
0x1800095d2  mov     r9, rsi
0x1800095d5  mov     rcx, rdi
0x1800095d8  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800095dd  jmp     loc_1800097BB
0x1800095e2  mov     r12, rdi
0x1800095e5  cmp     qword ptr [rsi+18h], 7
0x1800095ea  mov     rax, [rdi+10h]
0x1800095ee  lea     rdx, [r12+rax*2]; unsigned __int16 *
0x1800095f2  mov     [rsp+68h+arg_18], rdx
0x1800095fa  jbe     short loc_180009601
0x1800095fc  mov     r11, [rsi]
0x1800095ff  jmp     short loc_180009604
0x180009601  mov     r11, rsi
0x180009604  mov     rcx, r12; this
0x180009607  lea     rbx, [r14+r11]
0x18000960b  call    ?_Find_root_name_end@filesystem@std@@YAPEBGQEBG0@Z; std::filesystem::_Find_root_name_end(ushort const * const,ushort const * const)
0x180009610  mov     rdx, rbx; unsigned __int16 *
0x180009613  mov     rcx, r11; this
0x180009616  mov     rbp, rax
0x180009619  call    ?_Find_root_name_end@filesystem@std@@YAPEBGQEBG0@Z; std::filesystem::_Find_root_name_end(ushort const * const,ushort const * const)
0x18000961e  mov     r14, rbp
0x180009621  xor     r15d, r15d
0x180009624  sub     r14, r12
0x180009627  mov     r13, rax
0x18000962a  cmp     r11, rax
0x18000962d  jz      loc_1800096C6
0x180009633  sub     rax, r11
0x180009636  mov     rcx, r14
0x180009639  sar     rcx, 1
0x18000963c  mov     rdx, r11; S2
0x18000963f  sar     rax, 1
0x180009642  mov     r8, rcx
0x180009645  cmp     rax, rcx
0x180009648  mov     [rsp+68h+arg_10], rcx
0x180009650  mov     rcx, r12; S1
0x180009653  mov     [rsp+68h+arg_8], rax
0x180009658  cmovb   r8, rax; N
0x18000965c  call    wmemcmp
0x180009661  test    eax, eax
0x180009663  jnz     short loc_180009676
0x180009665  mov     rax, [rsp+68h+arg_8]
0x18000966a  cmp     [rsp+68h+arg_10], rax
0x180009672  jb      short loc_180009676
0x180009674  jbe     short loc_1800096C6
0x180009676  cmp     rdi, rsi
0x180009679  jz      loc_1800097BB
0x18000967f  cmp     qword ptr [rsi+18h], 7
0x180009684  mov     rdx, [rsi+10h]
0x180009688  jbe     short loc_18000968D
0x18000968a  mov     rsi, [rsi]
0x18000968d  cmp     rdx, [rdi+18h]
0x180009691  ja      loc_1800095D2
0x180009697  cmp     qword ptr [rdi+18h], 7
0x18000969c  jbe     short loc_1800096A3
0x18000969e  mov     rbp, [rdi]
0x1800096a1  jmp     short loc_1800096A6
0x1800096a3  mov     rbp, rdi
0x1800096a6  lea     rbx, [rdx+rdx]
0x1800096aa  mov     [rdi+10h], rdx
0x1800096ae  mov     r8, rbx; Size
0x1800096b1  mov     rdx, rsi; Src
0x1800096b4  mov     rcx, rbp; void *
0x1800096b7  call    memmove_0
0x1800096bc  mov     [rbx+rbp], r15w
0x1800096c1  jmp     loc_1800097BB
0x1800096c6  mov     edx, 5Ch ; '\'
0x1800096cb  cmp     r13, rbx
0x1800096ce  jz      short loc_180009709
0x1800096d0  cmp     [r13+0], dx
0x1800096d5  jz      short loc_1800096DF
0x1800096d7  cmp     word ptr [r13+0], 2Fh ; '/'
0x1800096dd  jnz     short loc_180009709
0x1800096df  sub     rbp, r12
0x1800096e2  sar     rbp, 1
0x1800096e5  cmp     [rdi+10h], rbp
0x1800096e9  jb      loc_1800097D3
0x1800096ef  mov     [rdi+10h], rbp
0x1800096f3  cmp     qword ptr [rdi+18h], 7
0x1800096f8  jbe     short loc_1800096FF
0x1800096fa  mov     rax, [rdi]
0x1800096fd  jmp     short loc_180009702
0x1800096ff  mov     rax, rdi
0x180009702  mov     [rax+rbp*2], r15w
0x180009707  jmp     short loc_180009764
0x180009709  mov     rax, [rsp+68h+arg_18]
0x180009711  cmp     rbp, rax
0x180009714  jnz     short loc_180009722
0x180009716  and     r14, 0FFFFFFFFFFFFFFFEh
0x18000971a  cmp     r14, 6
0x18000971e  jl      short loc_180009764
0x180009720  jmp     short loc_18000972F
0x180009722  cmp     [rax-2], dx
0x180009726  jz      short loc_180009764
0x180009728  cmp     word ptr [rax-2], 2Fh ; '/'
0x18000972d  jz      short loc_180009764
0x18000972f  mov     rcx, [rdi+10h]
0x180009733  cmp     rcx, [rdi+18h]
0x180009737  jnb     short loc_180009759
0x180009739  lea     rax, [rcx+1]
0x18000973d  mov     [rdi+10h], rax
0x180009741  cmp     qword ptr [rdi+18h], 7
0x180009746  jbe     short loc_18000974D
0x180009748  mov     rax, [rdi]
0x18000974b  jmp     short loc_180009750
0x18000974d  mov     rax, rdi
0x180009750  mov     dword ptr [rax+rcx*2], 5Ch ; '\'
0x180009757  jmp     short loc_180009764
0x180009759  mov     r9d, edx
0x18000975c  mov     rcx, rdi; Src
0x18000975f  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x180009764  mov     rcx, [rdi+10h]
0x180009768  sub     rbx, r13
0x18000976b  mov     rax, [rdi+18h]
0x18000976f  sar     rbx, 1
0x180009772  sub     rax, rcx
0x180009775  cmp     rbx, rax
0x180009778  ja      short loc_1800097A8
0x18000977a  cmp     qword ptr [rdi+18h], 7
0x18000977f  lea     rbp, [rbx+rcx]
0x180009783  mov     [rdi+10h], rbp
0x180009787  jbe     short loc_18000978E
0x180009789  mov     rsi, [rdi]
0x18000978c  jmp     short loc_180009791
0x18000978e  mov     rsi, rdi
0x180009791  lea     r8, [rbx+rbx]; Size
0x180009795  mov     rdx, r13; Src
0x180009798  lea     rcx, [rsi+rcx*2]; void *
0x18000979c  call    memmove_0
0x1800097a1  mov     [rsi+rbp*2], r15w
0x1800097a6  jmp     short loc_1800097BB
0x1800097a8  mov     r9, r13
0x1800097ab  mov     [rsp+68h+var_48], rbx; __int64
0x1800097b0  mov     rdx, rbx
0x1800097b3  mov     rcx, rdi; Src
0x1800097b6  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x1800097bb  mov     rbx, [rsp+68h+arg_0]
0x1800097c0  mov     rax, rdi
0x1800097c3  add     rsp, 30h
0x1800097c7  pop     r15
0x1800097c9  pop     r14
0x1800097cb  pop     r13
0x1800097cd  pop     r12
0x1800097cf  pop     rdi
0x1800097d0  pop     rsi
0x1800097d1  pop     rbp
0x1800097d2  retn
0x1800097d3  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
```
