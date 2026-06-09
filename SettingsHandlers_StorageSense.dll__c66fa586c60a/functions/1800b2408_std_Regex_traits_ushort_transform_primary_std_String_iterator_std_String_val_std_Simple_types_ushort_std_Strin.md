# std::_Regex_traits<ushort>::transform_primary<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>)

- ea: `0x1800b2408`
- end: `0x1800b2570`
- name: `??$transform_primary@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@?$_Regex_traits@G@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@1@0@Z`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800b1a30`

## callees

- `0x180006e50`
- `0x180009608`
- `0x180014840`
- `0x180023578`
- `0x180023928`
- `0x180024eac`
- `0x1800b2408`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1800b2485`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1800b2499`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1800b2485`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1800b2499`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1800b2471`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1800b2471`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Regex_traits<unsigned short>::transform_primary<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v7; // r14
  __int64 v8; // rbp
  unsigned __int64 v9; // rbx
  __int64 v10; // r14
  void *v11; // rax
  unsigned __int64 v12; // rax
  __int128 v14; // [rsp+40h] [rbp-48h] BYREF
  __int128 v15; // [rsp+50h] [rbp-38h]

  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 7;
  *(_WORD *)a2 = 0;
  if ( a3 != a4 )
  {
    v7 = *a1;
    v8 = __RTtypeid(*a1) + 8;
    if ( !(unsigned int)__std_type_info_compare(v8, &qword_180170FF0)
      || !(unsigned int)__std_type_info_compare(v8, &qword_180171580) )
    {
      v14 = 0;
      v15 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v14, a3, (a4 - a3) >> 1);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v14);
      v9 = v15;
      if ( *(_QWORD *)(a2 + 16) < (unsigned __int64)v15 )
      {
        v10 = v7 + 16;
        while ( 1 )
        {
          std::wstring::resize(a2, v9);
          std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
          v11 = (void *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
          v12 = _std_regex_transform_primary_wchar_t(v11, v10);
          v9 = v12;
          if ( v12 == -1 )
            break;
          if ( *(_QWORD *)(a2 + 16) >= v12 )
            goto LABEL_10;
        }
        v9 = 0;
      }
LABEL_10:
      std::wstring::resize(a2, v9);
      std::wstring::_Tidy_deallocate(&v14);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1800b2408  mov     [rsp+arg_10], rbx
0x1800b240d  mov     [rsp+arg_18], rbp
0x1800b2412  push    rsi
0x1800b2413  push    rdi
0x1800b2414  push    r14
0x1800b2416  sub     rsp, 70h
0x1800b241a  mov     rax, cs:__security_cookie
0x1800b2421  xor     rax, rsp
0x1800b2424  mov     [rsp+88h+var_28], rax
0x1800b2429  mov     rbx, r9
0x1800b242c  mov     rdi, r8
0x1800b242f  mov     rsi, rdx
0x1800b2432  mov     [rsp+88h+var_50], rdx
0x1800b2437  mov     [rsp+88h+var_58], 0
0x1800b243f  xorps   xmm0, xmm0
0x1800b2442  movups  xmmword ptr [rdx], xmm0
0x1800b2445  mov     qword ptr [rdx+10h], 0
0x1800b244d  mov     qword ptr [rdx+18h], 7
0x1800b2455  xor     eax, eax
0x1800b2457  mov     [rdx], ax
0x1800b245a  mov     [rsp+88h+var_58], 1
0x1800b2462  cmp     r8, r9
0x1800b2465  jz      loc_1800B254A
0x1800b246b  mov     r14, [rcx]
0x1800b246e  mov     rcx, r14
0x1800b2471  call    cs:__imp___RTtypeid
0x1800b2477  lea     rbp, [rax+8]
0x1800b247b  lea     rdx, qword_180170FF0
0x1800b2482  mov     rcx, rbp
0x1800b2485  call    cs:__imp___std_type_info_compare
0x1800b248b  test    eax, eax
0x1800b248d  jz      short loc_1800B24A7
0x1800b248f  lea     rdx, qword_180171580
0x1800b2496  mov     rcx, rbp
0x1800b2499  call    cs:__imp___std_type_info_compare
0x1800b249f  test    eax, eax
0x1800b24a1  jnz     loc_1800B254A
0x1800b24a7  xorps   xmm0, xmm0
0x1800b24aa  movups  [rsp+88h+var_48], xmm0
0x1800b24af  xorps   xmm1, xmm1
0x1800b24b2  movdqu  [rsp+88h+var_38], xmm1
0x1800b24b8  sub     rbx, rdi
0x1800b24bb  sar     rbx, 1
0x1800b24be  mov     r8, rbx
0x1800b24c1  mov     rdx, rdi
0x1800b24c4  lea     rcx, [rsp+88h+var_48]
0x1800b24c9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800b24ce  nop
0x1800b24cf  lea     rcx, [rsp+88h+var_48]
0x1800b24d4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b24d9  mov     rdi, rax
0x1800b24dc  mov     rbx, qword ptr [rsp+88h+var_38]
0x1800b24e1  lea     rbp, [rax+rbx*2]
0x1800b24e5  cmp     [rsi+10h], rbx
0x1800b24e9  jnb     short loc_1800B2534
0x1800b24eb  add     r14, 10h
0x1800b24ef  mov     rdx, rbx
0x1800b24f2  mov     rcx, rsi
0x1800b24f5  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800b24fa  mov     rcx, rsi
0x1800b24fd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b2502  lea     rdx, [rax+rbx*2]
0x1800b2506  mov     rcx, rsi
0x1800b2509  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b250e  mov     [rsp+88h+var_68], r14; __int64
0x1800b2513  mov     r9, rbp
0x1800b2516  mov     r8, rdi
0x1800b2519  mov     rcx, rax; void *
0x1800b251c  call    __std_regex_transform_primary_wchar_t
0x1800b2521  mov     rbx, rax
0x1800b2524  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b2528  jz      short loc_1800B2532
0x1800b252a  cmp     [rsi+10h], rax
0x1800b252e  jb      short loc_1800B24EF
0x1800b2530  jmp     short loc_1800B2534
0x1800b2532  xor     ebx, ebx
0x1800b2534  mov     rdx, rbx
0x1800b2537  mov     rcx, rsi
0x1800b253a  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800b253f  nop
0x1800b2540  lea     rcx, [rsp+88h+var_48]
0x1800b2545  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b254a  mov     rax, rsi
0x1800b254d  mov     rcx, [rsp+88h+var_28]
0x1800b2552  xor     rcx, rsp; StackCookie
0x1800b2555  call    __security_check_cookie
0x1800b255a  lea     r11, [rsp+88h+var_18]
0x1800b255f  mov     rbx, [r11+30h]
0x1800b2563  mov     rbp, [r11+38h]
0x1800b2567  mov     rsp, r11
0x1800b256a  pop     r14
0x1800b256c  pop     rdi
0x1800b256d  pop     rsi
0x1800b256e  retn
```
