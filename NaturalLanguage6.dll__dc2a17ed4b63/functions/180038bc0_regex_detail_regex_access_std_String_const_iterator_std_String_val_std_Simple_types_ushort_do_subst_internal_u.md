# regex::detail::regex_access<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_do_subst_internal<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,regex::basic_subst_results<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,regex::detail::basic_rpattern_base_impl<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> const &,unsigned __int64,unsigned __int64)

- ea: `0x180038bc0`
- end: `0x180038ee0`
- name: `??$_do_subst_internal@GU?$char_traits@G@std@@V?$allocator@G@2@@?$regex_access@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@detail@regex@@SA_KAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU?$basic_subst_results@GU?$char_traits@G@std@@V?$allocator@G@2@@2@AEBV?$basic_rpattern_base_impl@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@12@_K3@Z`
- size: `800`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180063ab0`

## callees

- `0x180038bc0`
- `0x180038ee8`
- `0x180038f10`
- `0x18003b34c`
- `0x18003b3c0`
- `0x18003d5ec`
- `0x180064140`

## import_xrefs

- `msvcrt!towupper` at `0x180038e6f`
- `msvcrt!towupper` at `0x180038e6f`
- `msvcrt!towlower` at `0x180038e0d`
- `msvcrt!towlower` at `0x180038e53`
- `msvcrt!towlower` at `0x180038e0d`
- `msvcrt!towlower` at `0x180038e53`

## pseudocode

```c
__int64 __fastcall regex::detail::regex_access<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_do_subst_internal<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v5; // r10
  __int64 v6; // r8
  int v7; // r13d
  int v8; // edx
  char v9; // bl
  __int64 v10; // r15
  _QWORD *v11; // r14
  __int64 *v12; // rsi
  int v13; // eax
  _QWORD *v14; // r9
  int v15; // ebp
  __int64 v16; // r12
  __int64 v17; // rax
  int v18; // ecx
  int v19; // edi
  int v20; // ecx
  __int64 v21; // rdx
  _QWORD *v22; // rbx
  __int64 v23; // rax
  __int64 v24; // r12
  _QWORD *v25; // r12
  __int64 v26; // rbx
  __int64 v27; // rbx
  __int64 *v28; // rax
  __int64 v29; // rcx
  __int64 v30; // r12
  _QWORD *v31; // rcx
  char *v32; // r9
  _QWORD *v33; // rax
  wint_t *v34; // rbx
  wint_t *v35; // rdi
  _QWORD *v36; // rcx
  wint_t v37; // ax
  _QWORD *v38; // rcx
  _QWORD *v39; // rcx
  __int64 v41; // [rsp+20h] [rbp-78h]
  _QWORD *v42; // [rsp+30h] [rbp-68h]
  char v44; // [rsp+40h] [rbp-58h] BYREF
  char v45; // [rsp+48h] [rbp-50h] BYREF
  char v46; // [rsp+A0h] [rbp+8h]
  int v49; // [rsp+B8h] [rbp+20h]

  v5 = a3;
  v6 = a2;
  v7 = 0;
  v8 = 0;
  v9 = 1;
  v10 = a4;
  v11 = a1;
  v49 = 0;
  v46 = 1;
  if ( a1[3] >= 8u )
    a1 = (_QWORD *)*a1;
  v12 = *(__int64 **)(v5 + 80);
  v13 = a4 + a5;
  v14 = *(_QWORD **)(v5 + 72);
  v42 = v14;
  v15 = (_DWORD)a1 + 2 * v13;
  while ( 1 )
  {
    v12 = (__int64 *)*v12;
    if ( *(__int64 **)(v5 + 80) == v12 )
      break;
    v16 = 0;
    if ( v11[3] < 8u )
      LODWORD(v17) = (_DWORD)v11;
    else
      v17 = *v11;
    v18 = *((_DWORD *)v12 + 4);
    v19 = v17 + 2 * v10;
    if ( v18 )
    {
      v20 = v18 - 1;
      if ( !v20 )
      {
        v21 = v12[3];
        if ( v21 == -2 )
        {
          v25 = *(_QWORD **)(v6 + 72);
          if ( v25[3] >= 8u )
            v25 = (_QWORD *)*v25;
          v26 = regex::basic_match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::allocator<unsigned short>>::rlength(
                  v6,
                  0);
          v27 = regex::basic_match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::allocator<unsigned short>>::rstart(
                  a2,
                  0)
              + v26;
          v28 = *(__int64 **)(a2 + 72);
          v22 = (_QWORD *)((char *)v25 + 2 * v27);
          if ( (unsigned __int64)v28[3] < 8 )
            v29 = *(_QWORD *)(a2 + 72);
          else
            v29 = *v28;
          v24 = v29 + 2 * v28[2];
        }
        else
        {
          v22 = *(_QWORD **)(v6 + 72);
          if ( v21 == -1 )
          {
            if ( v22[3] >= 8u )
              v22 = (_QWORD *)*v22;
            v23 = regex::basic_match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::allocator<unsigned short>>::rstart(
                    v6,
                    0);
          }
          else
          {
            if ( v22[3] >= 8u )
              v22 = (_QWORD *)*v22;
            v22 = (_QWORD *)((char *)v22
                           + 2
                           * regex::basic_match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::allocator<unsigned short>>::rstart(
                               v6,
                               v21));
            v23 = regex::basic_match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::allocator<unsigned short>>::rlength(
                    a2,
                    v12[3]);
          }
          v24 = (__int64)v22 + 2 * v23;
        }
        if ( v46 )
          std::wstring::replace((_DWORD)v11, v19, v15, (_DWORD)v22, v24);
        else
          std::wstring::insert((_DWORD)v11, (unsigned int)&v44, v19, (_DWORD)v22, v24);
        v30 = v24 - (_QWORD)v22;
        goto LABEL_47;
      }
      if ( v20 != 1 )
        goto LABEL_48;
      switch ( *((_DWORD *)v12 + 6) )
      {
        case '(':
          v8 = -1;
LABEL_21:
          v49 = v8;
          break;
        case ')':
          v7 = -1;
          break;
        case '*':
          v8 = 1;
          goto LABEL_21;
        case '+':
          v7 = 1;
          break;
        case ',':
          v8 = 0;
          goto LABEL_21;
      }
    }
    else
    {
      if ( v14[3] < 8u )
        v31 = v14;
      else
        v31 = (_QWORD *)*v14;
      v32 = (char *)v31 + 2 * v12[3];
      v30 = 2 * v12[4];
      v41 = (__int64)&v32[v30];
      if ( v9 )
        std::wstring::replace((_DWORD)v11, v19, v15, (_DWORD)v32, v41);
      else
        std::wstring::insert((_DWORD)v11, (unsigned int)&v45, v19, (_DWORD)v32, v41);
LABEL_47:
      v8 = v49;
      v16 = v30 >> 1;
LABEL_48:
      v9 = 0;
      v46 = 0;
      if ( v8 )
      {
        if ( v11[3] < 8u )
          v33 = v11;
        else
          v33 = (_QWORD *)*v11;
        v34 = (wint_t *)v33 + v10;
        v35 = &v34[v16];
        if ( v8 == -1 )
        {
          regex::detail::regex_toupper<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
            (char *)v33 + 2 * v10,
            &v34[v16],
            v6);
        }
        else if ( v8 == 1 )
        {
          while ( v35 != v34 )
          {
            *v34 = towlower(*v34);
            ++v34;
          }
        }
        v9 = 0;
      }
      if ( v7 )
      {
        if ( v7 == -1 )
        {
          if ( v11[3] < 8u )
            v38 = v11;
          else
            v38 = (_QWORD *)*v11;
          v37 = towupper(*((_WORD *)v38 + v10));
        }
        else
        {
          if ( v11[3] < 8u )
            v36 = v11;
          else
            v36 = (_QWORD *)*v11;
          v37 = towlower(*((_WORD *)v36 + v10));
        }
        if ( v11[3] < 8u )
          v39 = v11;
        else
          v39 = (_QWORD *)*v11;
        *((_WORD *)v39 + v10) = v37;
        v7 = 0;
      }
      v8 = v49;
      v10 += v16;
      v6 = a2;
      v14 = v42;
      v5 = a3;
    }
  }
  if ( v9 )
    std::wstring::erase(v11, v10, a5);
  return v10 - a4;
}

```

## disassembly

```asm
0x180038bc0  mov     [rsp+arg_10], r8
0x180038bc5  mov     [rsp+arg_8], rdx
0x180038bca  push    rbx
0x180038bcb  push    rbp
0x180038bcc  push    rsi
0x180038bcd  push    rdi
0x180038bce  push    r12
0x180038bd0  push    r13
0x180038bd2  push    r14
0x180038bd4  push    r15
0x180038bd6  sub     rsp, 58h
0x180038bda  mov     r10, r8
0x180038bdd  mov     [rsp+98h+var_60], r9
0x180038be2  mov     r8, rdx
0x180038be5  xor     r13d, r13d
0x180038be8  xor     edx, edx
0x180038bea  mov     bl, 1
0x180038bec  cmp     qword ptr [rcx+18h], 8
0x180038bf1  mov     r15, r9
0x180038bf4  mov     r14, rcx
0x180038bf7  mov     [rsp+98h+arg_18], edx
0x180038bfe  mov     [rsp+98h+arg_0], bl
0x180038c05  jb      short loc_180038C0A
0x180038c07  mov     rcx, [rcx]
0x180038c0a  mov     rax, [rsp+98h+arg_20]
0x180038c12  mov     rsi, [r10+50h]
0x180038c16  add     rax, r9
0x180038c19  mov     r9, [r10+48h]
0x180038c1d  mov     [rsp+98h+var_68], r9
0x180038c22  lea     rbp, [rcx+rax*2]
0x180038c26  mov     rsi, [rsi]
0x180038c29  cmp     [r10+50h], rsi
0x180038c2d  jz      loc_180038EB0
0x180038c33  xor     r12d, r12d
0x180038c36  cmp     qword ptr [r14+18h], 8
0x180038c3b  jb      short loc_180038C42
0x180038c3d  mov     rax, [r14]
0x180038c40  jmp     short loc_180038C45
0x180038c42  mov     rax, r14
0x180038c45  mov     ecx, [rsi+10h]
0x180038c48  lea     rdi, [rax+r15*2]
0x180038c4c  test    ecx, ecx
0x180038c4e  jz      loc_180038D84
0x180038c54  sub     ecx, 1
0x180038c57  jz      short loc_180038CA3
0x180038c59  cmp     ecx, 1
0x180038c5c  jnz     loc_180038DD7
0x180038c62  mov     ecx, [rsi+18h]
0x180038c65  sub     ecx, 28h ; '('
0x180038c68  jz      short loc_180038C97
0x180038c6a  sub     ecx, 1
0x180038c6d  jz      short loc_180038C91
0x180038c6f  sub     ecx, 1
0x180038c72  jz      short loc_180038C8A
0x180038c74  sub     ecx, 1
0x180038c77  jz      short loc_180038C82
0x180038c79  cmp     ecx, 1
0x180038c7c  jnz     short loc_180038C26
0x180038c7e  xor     edx, edx
0x180038c80  jmp     short loc_180038C9A
0x180038c82  mov     r13d, 1
0x180038c88  jmp     short loc_180038C26
0x180038c8a  mov     edx, 1
0x180038c8f  jmp     short loc_180038C9A
0x180038c91  or      r13d, 0FFFFFFFFh
0x180038c95  jmp     short loc_180038C26
0x180038c97  or      edx, 0FFFFFFFFh
0x180038c9a  mov     [rsp+98h+arg_18], edx
0x180038ca1  jmp     short loc_180038C26
0x180038ca3  mov     rdx, [rsi+18h]
0x180038ca7  cmp     rdx, 0FFFFFFFFFFFFFFFEh
0x180038cab  jz      short loc_180038CFA
0x180038cad  mov     rbx, [r8+48h]
0x180038cb1  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180038cb5  jz      short loc_180038CE0
0x180038cb7  cmp     qword ptr [rbx+18h], 8
0x180038cbc  jb      short loc_180038CC1
0x180038cbe  mov     rbx, [rbx]
0x180038cc1  mov     rcx, r8
0x180038cc4  call    ?rstart@?$basic_match_results@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$allocator@G@2@@regex@@QEBA_K_K@Z; regex::basic_match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::allocator<ushort>>::rstart(unsigned __int64)
0x180038cc9  mov     rdx, [rsi+18h]
0x180038ccd  mov     rcx, [rsp+98h+arg_8]
0x180038cd5  lea     rbx, [rbx+rax*2]
0x180038cd9  call    ?rlength@?$basic_match_results@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$allocator@G@2@@regex@@QEBA_K_K@Z; regex::basic_match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::allocator<ushort>>::rlength(unsigned __int64)
0x180038cde  jmp     short loc_180038CF4
0x180038ce0  cmp     qword ptr [rbx+18h], 8
0x180038ce5  jb      short loc_180038CEA
0x180038ce7  mov     rbx, [rbx]
0x180038cea  xor     edx, edx
0x180038cec  mov     rcx, r8
0x180038cef  call    ?rstart@?$basic_match_results@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$allocator@G@2@@regex@@QEBA_K_K@Z; regex::basic_match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::allocator<ushort>>::rstart(unsigned __int64)
0x180038cf4  lea     r12, [rbx+rax*2]
0x180038cf8  jmp     short loc_180038D50
0x180038cfa  mov     r12, [r8+48h]
0x180038cfe  cmp     qword ptr [r12+18h], 8
0x180038d04  jb      short loc_180038D0A
0x180038d06  mov     r12, [r12]
0x180038d0a  xor     edx, edx
0x180038d0c  mov     rcx, r8
0x180038d0f  call    ?rlength@?$basic_match_results@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$allocator@G@2@@regex@@QEBA_K_K@Z; regex::basic_match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::allocator<ushort>>::rlength(unsigned __int64)
0x180038d14  mov     rcx, [rsp+98h+arg_8]
0x180038d1c  xor     edx, edx
0x180038d1e  mov     rbx, rax
0x180038d21  call    ?rstart@?$basic_match_results@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$allocator@G@2@@regex@@QEBA_K_K@Z; regex::basic_match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::allocator<ushort>>::rstart(unsigned __int64)
0x180038d26  add     rbx, rax
0x180038d29  mov     rax, [rsp+98h+arg_8]
0x180038d31  mov     rax, [rax+48h]
0x180038d35  lea     rbx, [r12+rbx*2]
0x180038d39  cmp     qword ptr [rax+18h], 8
0x180038d3e  jb      short loc_180038D45
0x180038d40  mov     rcx, [rax]
0x180038d43  jmp     short loc_180038D48
0x180038d45  mov     rcx, rax
0x180038d48  mov     rax, [rax+10h]
0x180038d4c  lea     r12, [rcx+rax*2]
0x180038d50  cmp     [rsp+98h+arg_0], 0
0x180038d58  mov     r9, rbx
0x180038d5b  mov     [rsp+98h+var_78], r12
0x180038d60  mov     rcx, r14
0x180038d63  jz      short loc_180038D72
0x180038d65  mov     r8, rbp
0x180038d68  mov     rdx, rdi
0x180038d6b  call    ?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@000@Z; std::wstring::replace(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>)
0x180038d70  jmp     short loc_180038D7F
0x180038d72  mov     r8, rdi
0x180038d75  lea     rdx, [rsp+98h+var_58]
0x180038d7a  call    ?insert@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@00@Z; std::wstring::insert(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>)
0x180038d7f  sub     r12, rbx
0x180038d82  jmp     short loc_180038DCD
0x180038d84  cmp     qword ptr [r9+18h], 8
0x180038d89  jb      short loc_180038D90
0x180038d8b  mov     rcx, [r9]
0x180038d8e  jmp     short loc_180038D93
0x180038d90  mov     rcx, r9
0x180038d93  mov     rax, [rsi+18h]
0x180038d97  lea     r9, [rcx+rax*2]
0x180038d9b  mov     rax, [rsi+20h]
0x180038d9f  mov     rcx, r14
0x180038da2  lea     r12, [rax+rax]
0x180038da6  lea     rax, [r12+r9]
0x180038daa  mov     [rsp+98h+var_78], rax
0x180038daf  test    bl, bl
0x180038db1  jz      short loc_180038DC0
0x180038db3  mov     r8, rbp
0x180038db6  mov     rdx, rdi
0x180038db9  call    ?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@000@Z; std::wstring::replace(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>)
0x180038dbe  jmp     short loc_180038DCD
0x180038dc0  mov     r8, rdi
0x180038dc3  lea     rdx, [rsp+98h+var_50]
0x180038dc8  call    ?insert@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@00@Z; std::wstring::insert(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>)
0x180038dcd  mov     edx, [rsp+98h+arg_18]
0x180038dd4  sar     r12, 1
0x180038dd7  xor     bl, bl
0x180038dd9  mov     [rsp+98h+arg_0], bl
0x180038de0  test    edx, edx
0x180038de2  jz      short loc_180038E2E
0x180038de4  cmp     qword ptr [r14+18h], 8
0x180038de9  jb      short loc_180038DF0
0x180038deb  mov     rax, [r14]
0x180038dee  jmp     short loc_180038DF3
0x180038df0  mov     rax, r14
0x180038df3  lea     rbx, [rax+r15*2]
0x180038df7  lea     rdi, [rbx+r12*2]
0x180038dfb  cmp     edx, 0FFFFFFFFh
0x180038dfe  jz      short loc_180038E1C
0x180038e00  cmp     edx, 1
0x180038e03  jnz     short loc_180038E27
0x180038e05  cmp     rdi, rbx
0x180038e08  jz      short loc_180038E27
0x180038e0a  movzx   ecx, word ptr [rbx]; C
0x180038e0d  call    cs:__imp_towlower
0x180038e13  mov     [rbx], ax
0x180038e16  add     rbx, 2
0x180038e1a  jmp     short loc_180038E05
0x180038e1c  mov     rdx, rdi
0x180038e1f  mov     rcx, rbx
0x180038e22  call    ??$regex_toupper@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@@detail@regex@@YAXV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@3@@Z; regex::detail::regex_toupper<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>)
0x180038e27  mov     bl, [rsp+98h+arg_0]
0x180038e2e  test    r13d, r13d
0x180038e31  jz      short loc_180038E8C
0x180038e33  cmp     r13d, 0FFFFFFFFh
0x180038e37  jz      short loc_180038E5B
0x180038e39  cmp     r13d, 1
0x180038e3d  jnz     short loc_180038E89
0x180038e3f  cmp     qword ptr [r14+18h], 8
0x180038e44  jb      short loc_180038E4B
0x180038e46  mov     rcx, [r14]
0x180038e49  jmp     short loc_180038E4E
0x180038e4b  mov     rcx, r14
0x180038e4e  movzx   ecx, word ptr [rcx+r15*2]; C
0x180038e53  call    cs:__imp_towlower
0x180038e59  jmp     short loc_180038E75
0x180038e5b  cmp     qword ptr [r14+18h], 8
0x180038e60  jb      short loc_180038E67
0x180038e62  mov     rcx, [r14]
0x180038e65  jmp     short loc_180038E6A
0x180038e67  mov     rcx, r14
0x180038e6a  movzx   ecx, word ptr [rcx+r15*2]; C
0x180038e6f  call    cs:__imp_towupper
0x180038e75  cmp     qword ptr [r14+18h], 8
0x180038e7a  jb      short loc_180038E81
0x180038e7c  mov     rcx, [r14]
0x180038e7f  jmp     short loc_180038E84
0x180038e81  mov     rcx, r14
0x180038e84  mov     [rcx+r15*2], ax
0x180038e89  xor     r13d, r13d
0x180038e8c  mov     edx, [rsp+98h+arg_18]
0x180038e93  add     r15, r12
0x180038e96  mov     r8, [rsp+98h+arg_8]
0x180038e9e  mov     r9, [rsp+98h+var_68]
0x180038ea3  mov     r10, [rsp+98h+arg_10]
0x180038eab  jmp     loc_180038C26
0x180038eb0  test    bl, bl
0x180038eb2  jz      short loc_180038EC7
0x180038eb4  mov     r8, [rsp+98h+arg_20]
0x180038ebc  mov     rdx, r15
0x180038ebf  mov     rcx, r14
0x180038ec2  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x180038ec7  sub     r15, [rsp+98h+var_60]
0x180038ecc  mov     rax, r15
0x180038ecf  add     rsp, 58h
0x180038ed3  pop     r15
0x180038ed5  pop     r14
0x180038ed7  pop     r13
0x180038ed9  pop     r12
0x180038edb  pop     rdi
0x180038edc  pop     rsi
0x180038edd  pop     rbp
0x180038ede  pop     rbx
0x180038edf  retn
```
