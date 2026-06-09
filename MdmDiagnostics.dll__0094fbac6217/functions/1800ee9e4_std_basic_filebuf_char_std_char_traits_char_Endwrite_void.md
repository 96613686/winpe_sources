# std::basic_filebuf<char,std::char_traits<char>>::_Endwrite(void)

- ea: `0x1800ee9e4`
- end: `0x1800eeac5`
- name: `?_Endwrite@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAA_NXZ`
- size: `225`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800efa40`
- `0x1800f19e0`
- `0x1800f1dd0`

## callees

- `0x180019000`
- `0x1800ee9e4`
- `0x1800f08b4`
- `0x180191010`

## import_xrefs

- `msvcp_win!?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x1800eea54`
- `msvcp_win!?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x1800eea54`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800eeaad`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800eeaad`

## pseudocode

```c
bool __fastcall std::filebuf::_Endwrite(__int64 a1)
{
  unsigned int v2; // eax
  __int64 v3; // rcx
  int v4; // eax
  int v5; // eax
  __int64 v7; // rdi
  _BYTE *v8; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v9[32]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v10; // [rsp+58h] [rbp-10h] BYREF

  if ( !*(_QWORD *)(a1 + 104) || !*(_BYTE *)(a1 + 113) )
    return 1;
  v2 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 24LL))(a1, 0xFFFFFFFFLL);
  if ( (unsigned __int8)std::_Narrow_char_traits<char,int>::eq_int_type(0xFFFFFFFFLL, v2) )
    return 0;
  v3 = *(_QWORD *)(a1 + 104);
  v8 = 0;
  v4 = std::codecvt<char,char,_Mbstatet>::unshift(v3, a1 + 116, v9, &v10, &v8);
  if ( v4 )
  {
    v5 = v4 - 1;
    if ( v5 )
    {
      if ( v5 == 2 )
      {
        *(_BYTE *)(a1 + 113) = 0;
        return 1;
      }
      return 0;
    }
  }
  else
  {
    *(_BYTE *)(a1 + 113) = 0;
  }
  if ( v8 == v9 )
    return *(_BYTE *)(a1 + 113) == 0;
  v7 = v8 - v9;
  if ( v7 == _o_fwrite(v9, 1, v8 - v9, *(_QWORD *)(a1 + 128)) )
    return *(_BYTE *)(a1 + 113) == 0;
  return 0;
}

```

## disassembly

```asm
0x1800ee9e4  mov     [rsp+arg_8], rbx
0x1800ee9e9  push    rdi
0x1800ee9ea  sub     rsp, 60h
0x1800ee9ee  mov     rax, cs:__security_cookie
0x1800ee9f5  xor     rax, rsp
0x1800ee9f8  mov     [rsp+68h+var_10], rax
0x1800ee9fd  cmp     qword ptr [rcx+68h], 0
0x1800eea02  mov     rbx, rcx
0x1800eea05  jz      short loc_1800EEA6C
0x1800eea07  cmp     byte ptr [rcx+71h], 0
0x1800eea0b  jz      short loc_1800EEA6C
0x1800eea0d  mov     rax, [rcx]
0x1800eea10  or      edi, 0FFFFFFFFh
0x1800eea13  mov     edx, edi
0x1800eea15  mov     rax, [rax+18h]
0x1800eea19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eea1e  mov     edx, eax
0x1800eea20  mov     ecx, edi
0x1800eea22  call    ?eq_int_type@?$_Narrow_char_traits@DH@std@@SA_NHH@Z; std::_Narrow_char_traits<char,int>::eq_int_type(int,int)
0x1800eea27  test    al, al
0x1800eea29  jnz     loc_1800EEAC1
0x1800eea2f  mov     rcx, [rbx+68h]
0x1800eea33  lea     rax, [rsp+68h+var_38]
0x1800eea38  lea     rdx, [rbx+74h]
0x1800eea3c  mov     [rsp+68h+var_48], rax
0x1800eea41  lea     r9, [rsp+68h+var_10]
0x1800eea46  mov     [rsp+68h+var_38], 0
0x1800eea4f  lea     r8, [rsp+68h+var_30]
0x1800eea54  call    cs:__imp_?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z; std::codecvt<char,char,_Mbstatet>::unshift(_Mbstatet &,char *,char *,char * &)
0x1800eea5a  test    eax, eax
0x1800eea5c  jz      short loc_1800EEA86
0x1800eea5e  sub     eax, 1
0x1800eea61  jz      short loc_1800EEA8A
0x1800eea63  cmp     eax, 2
0x1800eea66  jnz     short loc_1800EEAC1
0x1800eea68  mov     byte ptr [rbx+71h], 0
0x1800eea6c  mov     al, 1
0x1800eea6e  mov     rcx, [rsp+68h+var_10]
0x1800eea73  xor     rcx, rsp; StackCookie
0x1800eea76  call    __security_check_cookie
0x1800eea7b  mov     rbx, [rsp+68h+arg_8]
0x1800eea80  add     rsp, 60h
0x1800eea84  pop     rdi
0x1800eea85  retn
0x1800eea86  mov     byte ptr [rbx+71h], 0
0x1800eea8a  mov     rdi, [rsp+68h+var_38]
0x1800eea8f  lea     rax, [rsp+68h+var_30]
0x1800eea94  sub     rdi, rax
0x1800eea97  jz      short loc_1800EEAB8
0x1800eea99  mov     r9, [rbx+80h]
0x1800eeaa0  lea     rcx, [rsp+68h+var_30]
0x1800eeaa5  mov     r8, rdi
0x1800eeaa8  mov     edx, 1
0x1800eeaad  call    cs:__imp__o_fwrite
0x1800eeab3  cmp     rdi, rax
0x1800eeab6  jnz     short loc_1800EEAC1
0x1800eeab8  cmp     byte ptr [rbx+71h], 0
0x1800eeabc  setz    al
0x1800eeabf  jmp     short loc_1800EEA6E
0x1800eeac1  xor     al, al
0x1800eeac3  jmp     short loc_1800EEA6E
```
