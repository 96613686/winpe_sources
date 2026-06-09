# std::basic_filebuf<char,std::char_traits<char>>::_Endwrite(void)

- ea: `0x180030020`
- end: `0x1800300f7`
- name: `?_Endwrite@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAA_NXZ`
- size: `215`
- prototype: `bool __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180030afc`
- `0x180033310`
- `0x1800333e0`

## callees

- `0x1800078b0`
- `0x180030020`
- `0x18005e010`

## import_xrefs

- `msvcp_win!?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x180030086`
- `msvcp_win!?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x180030086`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800300df`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800300df`

## pseudocode

```c
bool __fastcall std::filebuf::_Endwrite(__int64 a1)
{
  __int64 v2; // rcx
  int v3; // eax
  int v4; // eax
  __int64 v6; // rdi
  _BYTE *v7; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v8[32]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v9; // [rsp+58h] [rbp-10h] BYREF

  if ( !*(_QWORD *)(a1 + 104) || !*(_BYTE *)(a1 + 113) )
    return 1;
  if ( (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 24LL))(a1, 0xFFFFFFFFLL) == -1 )
    return 0;
  v2 = *(_QWORD *)(a1 + 104);
  v7 = 0;
  v3 = std::codecvt<char,char,_Mbstatet>::unshift(v2, a1 + 116, v8, &v9, &v7);
  if ( v3 )
  {
    v4 = v3 - 1;
    if ( v4 )
    {
      if ( v4 == 2 )
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
  if ( v7 == v8 )
    return *(_BYTE *)(a1 + 113) == 0;
  v6 = v7 - v8;
  if ( v6 == _o_fwrite(v8, 1, v7 - v8, *(_QWORD *)(a1 + 128)) )
    return *(_BYTE *)(a1 + 113) == 0;
  return 0;
}

```

## disassembly

```asm
0x180030020  mov     [rsp+arg_8], rbx
0x180030025  push    rdi
0x180030026  sub     rsp, 60h
0x18003002a  mov     rax, cs:__security_cookie
0x180030031  xor     rax, rsp
0x180030034  mov     [rsp+68h+var_10], rax
0x180030039  cmp     qword ptr [rcx+68h], 0
0x18003003e  mov     rbx, rcx
0x180030041  jz      short loc_18003009E
0x180030043  cmp     byte ptr [rcx+71h], 0
0x180030047  jz      short loc_18003009E
0x180030049  mov     rax, [rcx]
0x18003004c  or      edx, 0FFFFFFFFh
0x18003004f  mov     rax, [rax+18h]
0x180030053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030058  cmp     eax, 0FFFFFFFFh
0x18003005b  jz      loc_1800300F3
0x180030061  mov     rcx, [rbx+68h]
0x180030065  lea     rax, [rsp+68h+var_38]
0x18003006a  lea     rdx, [rbx+74h]
0x18003006e  mov     [rsp+68h+var_48], rax
0x180030073  lea     r9, [rsp+68h+var_10]
0x180030078  mov     [rsp+68h+var_38], 0
0x180030081  lea     r8, [rsp+68h+var_30]
0x180030086  call    cs:__imp_?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z; std::codecvt<char,char,_Mbstatet>::unshift(_Mbstatet &,char *,char *,char * &)
0x18003008c  test    eax, eax
0x18003008e  jz      short loc_1800300B8
0x180030090  sub     eax, 1
0x180030093  jz      short loc_1800300BC
0x180030095  cmp     eax, 2
0x180030098  jnz     short loc_1800300F3
0x18003009a  mov     byte ptr [rbx+71h], 0
0x18003009e  mov     al, 1
0x1800300a0  mov     rcx, [rsp+68h+var_10]
0x1800300a5  xor     rcx, rsp; StackCookie
0x1800300a8  call    __security_check_cookie
0x1800300ad  mov     rbx, [rsp+68h+arg_8]
0x1800300b2  add     rsp, 60h
0x1800300b6  pop     rdi
0x1800300b7  retn
0x1800300b8  mov     byte ptr [rbx+71h], 0
0x1800300bc  mov     rdi, [rsp+68h+var_38]
0x1800300c1  lea     rax, [rsp+68h+var_30]
0x1800300c6  sub     rdi, rax
0x1800300c9  jz      short loc_1800300EA
0x1800300cb  mov     r9, [rbx+80h]
0x1800300d2  lea     rcx, [rsp+68h+var_30]
0x1800300d7  mov     r8, rdi
0x1800300da  mov     edx, 1
0x1800300df  call    cs:__imp__o_fwrite
0x1800300e5  cmp     rdi, rax
0x1800300e8  jnz     short loc_1800300F3
0x1800300ea  cmp     byte ptr [rbx+71h], 0
0x1800300ee  setz    al
0x1800300f1  jmp     short loc_1800300A0
0x1800300f3  xor     al, al
0x1800300f5  jmp     short loc_1800300A0
```
