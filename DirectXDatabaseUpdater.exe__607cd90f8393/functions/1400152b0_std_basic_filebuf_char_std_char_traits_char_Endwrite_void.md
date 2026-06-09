# std::basic_filebuf<char,std::char_traits<char>>::_Endwrite(void)

- ea: `0x1400152b0`
- end: `0x140015391`
- name: `?_Endwrite@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAA_NXZ`
- size: `225`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140015530`
- `0x140015910`
- `0x1400159f0`

## callees

- `0x140002f40`
- `0x1400152b0`
- `0x1400155a4`
- `0x14001a010`

## import_xrefs

- `msvcp_win!?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x140015320`
- `msvcp_win!?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x140015320`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x140015379`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x140015379`

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
0x1400152b0  mov     [rsp+arg_8], rbx
0x1400152b5  push    rdi
0x1400152b6  sub     rsp, 60h
0x1400152ba  mov     rax, cs:__security_cookie
0x1400152c1  xor     rax, rsp
0x1400152c4  mov     [rsp+68h+var_10], rax
0x1400152c9  cmp     qword ptr [rcx+68h], 0
0x1400152ce  mov     rbx, rcx
0x1400152d1  jz      short loc_140015338
0x1400152d3  cmp     byte ptr [rcx+71h], 0
0x1400152d7  jz      short loc_140015338
0x1400152d9  mov     rax, [rcx]
0x1400152dc  or      edi, 0FFFFFFFFh
0x1400152df  mov     edx, edi
0x1400152e1  mov     rax, [rax+18h]
0x1400152e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400152ea  mov     edx, eax
0x1400152ec  mov     ecx, edi
0x1400152ee  call    ?eq_int_type@?$_Narrow_char_traits@DH@std@@SA_NHH@Z; std::_Narrow_char_traits<char,int>::eq_int_type(int,int)
0x1400152f3  test    al, al
0x1400152f5  jnz     loc_14001538D
0x1400152fb  mov     rcx, [rbx+68h]
0x1400152ff  lea     rax, [rsp+68h+var_38]
0x140015304  lea     rdx, [rbx+74h]
0x140015308  mov     [rsp+68h+var_48], rax
0x14001530d  lea     r9, [rsp+68h+var_10]
0x140015312  mov     [rsp+68h+var_38], 0
0x14001531b  lea     r8, [rsp+68h+var_30]
0x140015320  call    cs:__imp_?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z; std::codecvt<char,char,_Mbstatet>::unshift(_Mbstatet &,char *,char *,char * &)
0x140015326  test    eax, eax
0x140015328  jz      short loc_140015352
0x14001532a  sub     eax, 1
0x14001532d  jz      short loc_140015356
0x14001532f  cmp     eax, 2
0x140015332  jnz     short loc_14001538D
0x140015334  mov     byte ptr [rbx+71h], 0
0x140015338  mov     al, 1
0x14001533a  mov     rcx, [rsp+68h+var_10]
0x14001533f  xor     rcx, rsp; StackCookie
0x140015342  call    __security_check_cookie
0x140015347  mov     rbx, [rsp+68h+arg_8]
0x14001534c  add     rsp, 60h
0x140015350  pop     rdi
0x140015351  retn
0x140015352  mov     byte ptr [rbx+71h], 0
0x140015356  mov     rdi, [rsp+68h+var_38]
0x14001535b  lea     rax, [rsp+68h+var_30]
0x140015360  sub     rdi, rax
0x140015363  jz      short loc_140015384
0x140015365  mov     r9, [rbx+80h]
0x14001536c  lea     rcx, [rsp+68h+var_30]
0x140015371  mov     r8, rdi
0x140015374  mov     edx, 1
0x140015379  call    cs:__imp__o_fwrite
0x14001537f  cmp     rdi, rax
0x140015382  jnz     short loc_14001538D
0x140015384  cmp     byte ptr [rbx+71h], 0
0x140015388  setz    al
0x14001538b  jmp     short loc_14001533A
0x14001538d  xor     al, al
0x14001538f  jmp     short loc_14001533A
```
