# std::filesystem::path::operator/=(std::filesystem::path const &)

- ea: `0x180011980`
- end: `0x180011b2a`
- name: `??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z`
- size: `426`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800116d8`

## callees

- `0x18000828c`
- `0x18000ef38`
- `0x18000efa8`
- `0x18001024c`
- `0x180011980`
- `0x1800155cc`
- `0x180015774`
- `0x180015890`
- `0x180015d28`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall std::filesystem::path::operator/=(__int64 a1, __int64 a2)
{
  std::filesystem *v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rsi
  std::filesystem *v7; // rcx
  const unsigned __int16 *v8; // r8
  __int64 v9; // r11
  std::filesystem *v10; // r13
  const unsigned __int16 *v11; // r15
  std::filesystem *v12; // r12
  __int64 v13; // r11
  const unsigned __int16 *v14; // rsi
  const unsigned __int16 *v15; // r8
  const unsigned __int16 *v16; // r8
  const unsigned __int16 *v17; // rax
  const unsigned __int16 *v18; // r11
  const unsigned __int16 *v19; // r14
  __int64 v20; // rbp
  __int64 v21; // rax
  __int64 v22; // r8
  const unsigned __int16 *root_name_end; // rax
  const unsigned __int16 *v24; // rcx
  const unsigned __int16 *v26; // [rsp+78h] [rbp+10h]

  v4 = (std::filesystem *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  v6 = *(_QWORD *)(v5 + 16);
  if ( !std::filesystem::_Has_drive_letter_prefix(
          v4,
          (const unsigned __int16 *const)v4 + v6,
          (const unsigned __int16 *const)v4 + v6) )
  {
    root_name_end = std::filesystem::_Find_root_name_end(v7, v8, v8);
    if ( v24 == root_name_end )
      goto LABEL_5;
LABEL_11:
    if ( a1 == a2 )
      return a1;
    v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    v22 = v6;
    goto LABEL_9;
  }
  if ( (__int64)(v9 & 0xFFFFFFFFFFFFFFFEuLL) >= 6 && (*((_WORD *)v7 + 2) == 92 || *((_WORD *)v7 + 2) == 47) )
    goto LABEL_11;
LABEL_5:
  v10 = (std::filesystem *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  v11 = (const unsigned __int16 *)((char *)v10 + 2 * *(_QWORD *)(a1 + 16));
  v12 = (std::filesystem *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  v14 = (const unsigned __int16 *)((char *)v12 + v13);
  v26 = std::filesystem::_Find_root_name_end(v10, v11, v15);
  v17 = std::filesystem::_Find_root_name_end(v12, v14, v16);
  v19 = v17;
  v20 = ((char *)v18 - (char *)v10) >> 1;
  if ( v12 == (std::filesystem *)v17 )
  {
LABEL_14:
    if ( v19 != v14 && (*v19 == 92 || *v19 == 47) )
    {
      if ( *(_QWORD *)(a1 + 16) < (unsigned __int64)v20 )
        std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
      *(_QWORD *)(a1 + 16) = v20;
      *(_WORD *)(std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1) + 2 * v20) = 0;
      goto LABEL_25;
    }
    if ( v18 == v11 )
    {
      if ( v20 < 3 )
        goto LABEL_25;
    }
    else if ( *(v11 - 1) == 92 || *(v11 - 1) == 47 )
    {
      goto LABEL_25;
    }
    std::wstring::push_back(a1, 92);
LABEL_25:
    std::wstring::_Append<unsigned short>(a1, v19, v14 - v19);
    return a1;
  }
  if ( !std::_Traits_compare<std::char_traits<unsigned short>>(
          (const wchar_t *)v10,
          ((char *)v18 - (char *)v10) >> 1,
          (const wchar_t *)v12,
          ((char *)v17 - (char *)v12) >> 1) )
  {
    v18 = v26;
    goto LABEL_14;
  }
  if ( a1 != a2 )
  {
    v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    v22 = *(_QWORD *)(a2 + 16);
LABEL_9:
    std::wstring::_Assign<unsigned short>(a1, v21, v22);
  }
  return a1;
}

```

## disassembly

```asm
0x180011980  push    rbx
0x180011982  push    rbp
0x180011983  push    rsi
0x180011984  push    rdi
0x180011985  push    r12
0x180011987  push    r13
0x180011989  push    r14
0x18001198b  push    r15
0x18001198d  sub     rsp, 28h
0x180011991  mov     rbx, rcx
0x180011994  mov     rdi, rdx
0x180011997  mov     rcx, rdx
0x18001199a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001199f  mov     rsi, [rdx+10h]
0x1800119a3  mov     rcx, rax; this
0x1800119a6  lea     r11, [rsi+rsi]
0x1800119aa  lea     r8, [r11+rax]; unsigned __int16 *
0x1800119ae  mov     rdx, r8; unsigned __int16 *
0x1800119b1  call    ?_Has_drive_letter_prefix@filesystem@std@@YA_NQEBG0@Z; std::filesystem::_Has_drive_letter_prefix(ushort const * const,ushort const * const)
0x1800119b6  mov     edx, 5Ch ; '\'
0x1800119bb  test    al, al
0x1800119bd  jz      loc_180011A7D
0x1800119c3  mov     rax, r11
0x1800119c6  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800119ca  cmp     rax, 6
0x1800119ce  jl      short loc_1800119E5
0x1800119d0  cmp     [rcx+4], dx
0x1800119d4  jz      loc_180011A8E
0x1800119da  cmp     word ptr [rcx+4], 2Fh ; '/'
0x1800119df  jz      loc_180011A8E
0x1800119e5  mov     rcx, rbx
0x1800119e8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800119ed  mov     rcx, [rbx+10h]
0x1800119f1  mov     r13, rax
0x1800119f4  lea     r15, ds:0[rcx*2]
0x1800119fc  mov     rcx, rdi
0x1800119ff  add     r15, rax
0x180011a02  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180011a07  mov     rdx, r15; unsigned __int16 *
0x180011a0a  mov     rcx, r13; this
0x180011a0d  mov     r12, rax
0x180011a10  lea     rsi, [r11+rax]
0x180011a14  call    ?_Find_root_name_end@filesystem@std@@YAPEBGQEBG0@Z; std::filesystem::_Find_root_name_end(ushort const * const,ushort const * const)
0x180011a19  mov     rdx, rsi; unsigned __int16 *
0x180011a1c  mov     [rsp+68h+arg_8], rax
0x180011a21  mov     rcx, r12; this
0x180011a24  mov     r11, rax
0x180011a27  call    ?_Find_root_name_end@filesystem@std@@YAPEBGQEBG0@Z; std::filesystem::_Find_root_name_end(ushort const * const,ushort const * const)
0x180011a2c  mov     rbp, r11
0x180011a2f  mov     r14, rax
0x180011a32  sub     rbp, r13
0x180011a35  sar     rbp, 1
0x180011a38  cmp     r12, rax
0x180011a3b  jz      short loc_180011AA5
0x180011a3d  mov     r9, rax
0x180011a40  mov     r8, r12
0x180011a43  sub     r9, r12
0x180011a46  mov     rdx, rbp
0x180011a49  sar     r9, 1
0x180011a4c  mov     rcx, r13
0x180011a4f  call    ??$_Traits_compare@U?$char_traits@G@std@@@std@@YAHQEBG_K01@Z; std::_Traits_compare<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180011a54  test    eax, eax
0x180011a56  jz      short loc_180011AA0
0x180011a58  cmp     rbx, rdi
0x180011a5b  jz      loc_180011B10
0x180011a61  mov     rcx, rdi
0x180011a64  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180011a69  mov     r8, [rdi+10h]
0x180011a6d  mov     rdx, rax
0x180011a70  mov     rcx, rbx
0x180011a73  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180011a78  jmp     loc_180011B10
0x180011a7d  mov     rdx, r8; unsigned __int16 *
0x180011a80  call    ?_Find_root_name_end@filesystem@std@@YAPEBGQEBG0@Z; std::filesystem::_Find_root_name_end(ushort const * const,ushort const * const)
0x180011a85  cmp     rcx, rax
0x180011a88  jz      loc_1800119E5
0x180011a8e  cmp     rbx, rdi
0x180011a91  jz      short loc_180011B10
0x180011a93  mov     rcx, rdi
0x180011a96  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180011a9b  mov     r8, rsi
0x180011a9e  jmp     short loc_180011A6D
0x180011aa0  mov     r11, [rsp+68h+arg_8]
0x180011aa5  mov     eax, 5Ch ; '\'
0x180011aaa  cmp     r14, rsi
0x180011aad  jz      short loc_180011AD6
0x180011aaf  cmp     [r14], ax
0x180011ab3  jz      short loc_180011ABC
0x180011ab5  cmp     word ptr [r14], 2Fh ; '/'
0x180011aba  jnz     short loc_180011AD6
0x180011abc  cmp     [rbx+10h], rbp
0x180011ac0  jb      short loc_180011B24
0x180011ac2  mov     rcx, rbx
0x180011ac5  mov     [rbx+10h], rbp
0x180011ac9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180011ace  xor     ecx, ecx
0x180011ad0  mov     [rax+rbp*2], cx
0x180011ad4  jmp     short loc_180011AFC
0x180011ad6  cmp     r11, r15
0x180011ad9  jnz     short loc_180011AE3
0x180011adb  cmp     rbp, 3
0x180011adf  jge     short loc_180011AF2
0x180011ae1  jmp     short loc_180011AFC
0x180011ae3  cmp     [r15-2], ax
0x180011ae8  jz      short loc_180011AFC
0x180011aea  cmp     word ptr [r15-2], 2Fh ; '/'
0x180011af0  jz      short loc_180011AFC
0x180011af2  mov     edx, eax
0x180011af4  mov     rcx, rbx
0x180011af7  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x180011afc  sub     rsi, r14
0x180011aff  mov     rdx, r14
0x180011b02  sar     rsi, 1
0x180011b05  mov     rcx, rbx
0x180011b08  mov     r8, rsi
0x180011b0b  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180011b10  mov     rax, rbx
0x180011b13  add     rsp, 28h
0x180011b17  pop     r15
0x180011b19  pop     r14
0x180011b1b  pop     r13
0x180011b1d  pop     r12
0x180011b1f  pop     rdi
0x180011b20  pop     rsi
0x180011b21  pop     rbp
0x180011b22  pop     rbx
0x180011b23  retn
0x180011b24  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
```
