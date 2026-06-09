# web::json::details::JSON_Parser<wchar_t>::handle_unescape_char(web::json::details::JSON_Parser<wchar_t>::Token &)

- ea: `0x18002eeb0`
- end: `0x18002f19d`
- name: `?handle_unescape_char@?$JSON_Parser@_W@details@json@web@@IEAA_NAEAUToken@1234@@Z`
- size: `749`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18002e600`
- `0x18002eda0`

## callees

- `0x180028b6c`
- `0x18002eeb0`
- `0x180031b14`
- `0x180042426`
- `0x180047a30`

## pseudocode

```c
char __fastcall web::json::details::JSON_Parser<wchar_t>::handle_unescape_char(
        __int64 (__fastcall ***a1)(_QWORD),
        __int64 a2)
{
  __int16 v4; // ax
  __int16 v5; // bp
  int v6; // edi
  __int64 v7; // r15
  struct __crt_locale_pointers *v8; // rax
  __int16 v9; // cx
  int v10; // edx
  _QWORD *v11; // rcx
  unsigned __int64 v12; // rdx
  bool v13; // cc
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // rdx
  unsigned __int64 v21; // rdx
  unsigned __int64 v22; // rdx

  *(_BYTE *)(a2 + 56) = 1;
  v4 = (**a1)(a1);
  switch ( v4 )
  {
    case '"':
      v11 = (_QWORD *)(a2 + 8);
      v22 = *(_QWORD *)(a2 + 24);
      if ( v22 < *(_QWORD *)(a2 + 32) )
      {
        v13 = *(_QWORD *)(a2 + 32) <= 7u;
        *(_QWORD *)(a2 + 24) = v22 + 1;
        if ( !v13 )
          v11 = (_QWORD *)*v11;
        *(_DWORD *)((char *)v11 + 2 * v22) = 34;
        return 1;
      }
      goto LABEL_21;
    case '/':
      v11 = (_QWORD *)(a2 + 8);
      v21 = *(_QWORD *)(a2 + 24);
      if ( v21 < *(_QWORD *)(a2 + 32) )
      {
        v13 = *(_QWORD *)(a2 + 32) <= 7u;
        *(_QWORD *)(a2 + 24) = v21 + 1;
        if ( !v13 )
          v11 = (_QWORD *)*v11;
        *(_DWORD *)((char *)v11 + 2 * v21) = 47;
        return 1;
      }
      goto LABEL_21;
    case '\\':
      v11 = (_QWORD *)(a2 + 8);
      v20 = *(_QWORD *)(a2 + 24);
      if ( v20 < *(_QWORD *)(a2 + 32) )
      {
        v13 = *(_QWORD *)(a2 + 32) <= 7u;
        *(_QWORD *)(a2 + 24) = v20 + 1;
        if ( !v13 )
          v11 = (_QWORD *)*v11;
        *(_DWORD *)((char *)v11 + 2 * v20) = 92;
        return 1;
      }
      goto LABEL_21;
    case 'b':
      v11 = (_QWORD *)(a2 + 8);
      v19 = *(_QWORD *)(a2 + 24);
      if ( v19 < *(_QWORD *)(a2 + 32) )
      {
        v13 = *(_QWORD *)(a2 + 32) <= 7u;
        *(_QWORD *)(a2 + 24) = v19 + 1;
        if ( !v13 )
          v11 = (_QWORD *)*v11;
        *(_DWORD *)((char *)v11 + 2 * v19) = 8;
        return 1;
      }
      goto LABEL_21;
    case 'f':
      v11 = (_QWORD *)(a2 + 8);
      v18 = *(_QWORD *)(a2 + 24);
      if ( v18 < *(_QWORD *)(a2 + 32) )
      {
        v13 = *(_QWORD *)(a2 + 32) <= 7u;
        *(_QWORD *)(a2 + 24) = v18 + 1;
        if ( !v13 )
          v11 = (_QWORD *)*v11;
        *(_DWORD *)((char *)v11 + 2 * v18) = 12;
        return 1;
      }
      goto LABEL_21;
    case 'n':
      v11 = (_QWORD *)(a2 + 8);
      v17 = *(_QWORD *)(a2 + 24);
      if ( v17 < *(_QWORD *)(a2 + 32) )
      {
        v13 = *(_QWORD *)(a2 + 32) <= 7u;
        *(_QWORD *)(a2 + 24) = v17 + 1;
        if ( !v13 )
          v11 = (_QWORD *)*v11;
        *(_DWORD *)((char *)v11 + 2 * v17) = 10;
        return 1;
      }
      goto LABEL_21;
    case 'r':
      v11 = (_QWORD *)(a2 + 8);
      v16 = *(_QWORD *)(a2 + 24);
      if ( v16 < *(_QWORD *)(a2 + 32) )
      {
        v13 = *(_QWORD *)(a2 + 32) <= 7u;
        *(_QWORD *)(a2 + 24) = v16 + 1;
        if ( !v13 )
          v11 = (_QWORD *)*v11;
        *(_DWORD *)((char *)v11 + 2 * v16) = 13;
        return 1;
      }
      goto LABEL_21;
    case 't':
      v11 = (_QWORD *)(a2 + 8);
      v15 = *(_QWORD *)(a2 + 24);
      if ( v15 < *(_QWORD *)(a2 + 32) )
      {
        v13 = *(_QWORD *)(a2 + 32) <= 7u;
        *(_QWORD *)(a2 + 24) = v15 + 1;
        if ( !v13 )
          v11 = (_QWORD *)*v11;
        *(_DWORD *)((char *)v11 + 2 * v15) = 9;
        return 1;
      }
LABEL_21:
      std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(v11);
      return 1;
    case 'u':
      v5 = 0;
      v6 = 12;
      while ( 1 )
      {
        v7 = (unsigned __int16)(**a1)(a1);
        if ( (unsigned int)v7 > 0x7F )
          break;
        v8 = utility::details::scoped_c_thread_locale::c_locale();
        v9 = v8 ? *(_WORD *)(*(_QWORD *)v8->locinfo + 2LL * (int)v7) : *(_WORD *)(2LL * (int)v7 + o___pctype_func_0());
        if ( (v9 & 0x80) == 0 )
          break;
        v10 = *((char *)_hexval + v7) << v6;
        v6 -= 4;
        v5 |= v10;
        if ( v6 <= -4 )
        {
          v11 = (_QWORD *)(a2 + 8);
          v12 = *(_QWORD *)(a2 + 24);
          if ( v12 >= *(_QWORD *)(a2 + 32) )
            goto LABEL_21;
          v13 = *(_QWORD *)(a2 + 32) <= 7u;
          *(_QWORD *)(a2 + 24) = v12 + 1;
          if ( !v13 )
            v11 = (_QWORD *)*v11;
          *((_WORD *)v11 + v12) = v5;
          *((_WORD *)v11 + v12 + 1) = 0;
          return 1;
        }
      }
      break;
  }
  return 0;
}

```

## disassembly

```asm
0x18002eeb0  mov     [rsp+arg_10], rbx
0x18002eeb5  mov     [rsp+arg_18], rbp
0x18002eeba  push    rsi
0x18002eebb  push    rdi
0x18002eebc  push    r12
0x18002eebe  push    r14
0x18002eec0  push    r15
0x18002eec2  sub     rsp, 20h
0x18002eec6  mov     byte ptr [rdx+38h], 1
0x18002eeca  mov     rsi, rdx
0x18002eecd  mov     rax, [rcx]
0x18002eed0  mov     r12, rcx
0x18002eed3  mov     rax, [rax]
0x18002eed6  call    _guard_dispatch_icall
0x18002eedb  movzx   r8d, ax
0x18002eedf  mov     r9d, 22h ; '"'
0x18002eee5  sub     r8d, r9d
0x18002eee8  jz      loc_18002F170
0x18002eeee  lea     r10d, [r9-15h]
0x18002eef2  sub     r8d, r10d
0x18002eef5  jz      loc_18002F139
0x18002eefb  sub     r8d, 2Dh ; '-'
0x18002eeff  jz      loc_18002F102
0x18002ef05  sub     r8d, 6
0x18002ef09  jz      loc_18002F0CB
0x18002ef0f  sub     r8d, 4
0x18002ef13  jz      loc_18002F094
0x18002ef19  sub     r8d, 8
0x18002ef1d  jz      loc_18002F05D
0x18002ef23  sub     r8d, 4
0x18002ef27  jz      loc_18002F032
0x18002ef2d  sub     r8d, 2
0x18002ef31  jz      loc_18002F001
0x18002ef37  cmp     r8d, 1
0x18002ef3b  jnz     loc_18002EFFD
0x18002ef41  xor     ebx, ebx
0x18002ef43  mov     ebp, ebx
0x18002ef45  lea     edi, [rbx+0Ch]
0x18002ef48  mov     rax, [r12]
0x18002ef4c  mov     rcx, r12
0x18002ef4f  mov     rax, [rax]
0x18002ef52  call    _guard_dispatch_icall
0x18002ef57  movzx   r15d, ax
0x18002ef5b  cmp     r15d, 7Fh
0x18002ef5f  ja      loc_18002EFFD
0x18002ef65  call    ?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ; utility::details::scoped_c_thread_locale::c_locale(void)
0x18002ef6a  movsxd  r14, r15d
0x18002ef6d  add     r14, r14
0x18002ef70  test    rax, rax
0x18002ef73  jnz     short loc_18002EF81
0x18002ef75  call    _o___pctype_func_0
0x18002ef7a  movzx   ecx, word ptr [r14+rax]
0x18002ef7f  jmp     short loc_18002EF8C
0x18002ef81  mov     rax, [rax]
0x18002ef84  mov     rcx, [rax]
0x18002ef87  movzx   ecx, word ptr [rcx+r14]
0x18002ef8c  and     ecx, 80h
0x18002ef92  test    ecx, ecx
0x18002ef94  jz      short loc_18002EFFD
0x18002ef96  lea     rcx, ?_hexval@@3V?$array@C$0IA@@std@@A; std::array<signed char,128> _hexval
0x18002ef9d  movsx   edx, byte ptr [r15+rcx]
0x18002efa2  mov     ecx, edi
0x18002efa4  shl     edx, cl
0x18002efa6  sub     edi, 4
0x18002efa9  or      ebp, edx
0x18002efab  cmp     edi, 0FFFFFFFCh
0x18002efae  jg      short loc_18002EF48
0x18002efb0  lea     rcx, [rsi+8]; Src
0x18002efb4  mov     rdx, [rcx+10h]
0x18002efb8  cmp     rdx, [rcx+18h]
0x18002efbc  jnb     short loc_18002EFDB
0x18002efbe  cmp     qword ptr [rcx+18h], 7
0x18002efc3  lea     rax, [rdx+1]
0x18002efc7  mov     [rcx+10h], rax
0x18002efcb  jbe     short loc_18002EFD0
0x18002efcd  mov     rcx, [rcx]
0x18002efd0  mov     [rcx+rdx*2], bp
0x18002efd4  mov     [rcx+rdx*2+2], bx
0x18002efd9  jmp     short loc_18002EFE4
0x18002efdb  movzx   r9d, bp
0x18002efdf  call    ??$_Reallocate_grow_by@V_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@Z; std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(unsigned __int64,_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t)
0x18002efe4  mov     al, 1
0x18002efe6  mov     rbx, [rsp+48h+arg_10]
0x18002efeb  mov     rbp, [rsp+48h+arg_18]
0x18002eff0  add     rsp, 20h
0x18002eff4  pop     r15
0x18002eff6  pop     r14
0x18002eff8  pop     r12
0x18002effa  pop     rdi
0x18002effb  pop     rsi
0x18002effc  retn
0x18002effd  xor     al, al
0x18002efff  jmp     short loc_18002EFE6
0x18002f001  lea     rcx, [rsi+8]
0x18002f005  mov     rdx, [rcx+10h]
0x18002f009  cmp     rdx, [rcx+18h]
0x18002f00d  jnb     short loc_18002F02A
0x18002f00f  cmp     qword ptr [rcx+18h], 7
0x18002f014  lea     rax, [rdx+1]
0x18002f018  mov     [rcx+10h], rax
0x18002f01c  jbe     short loc_18002F021
0x18002f01e  mov     rcx, [rcx]
0x18002f021  mov     dword ptr [rcx+rdx*2], 9
0x18002f028  jmp     short loc_18002EFE4
0x18002f02a  mov     r9d, 9
0x18002f030  jmp     short loc_18002EFDF
0x18002f032  lea     rcx, [rsi+8]
0x18002f036  mov     rdx, [rcx+10h]
0x18002f03a  cmp     rdx, [rcx+18h]
0x18002f03e  jnb     short loc_18002F058
0x18002f040  cmp     qword ptr [rcx+18h], 7
0x18002f045  lea     rax, [rdx+1]
0x18002f049  mov     [rcx+10h], rax
0x18002f04d  jbe     short loc_18002F052
0x18002f04f  mov     rcx, [rcx]
0x18002f052  mov     [rcx+rdx*2], r10d
0x18002f056  jmp     short loc_18002EFE4
0x18002f058  mov     r9d, r10d
0x18002f05b  jmp     short loc_18002EFDF
0x18002f05d  lea     rcx, [rsi+8]
0x18002f061  mov     rdx, [rcx+10h]
0x18002f065  cmp     rdx, [rcx+18h]
0x18002f069  jnb     short loc_18002F089
0x18002f06b  cmp     qword ptr [rcx+18h], 7
0x18002f070  lea     rax, [rdx+1]
0x18002f074  mov     [rcx+10h], rax
0x18002f078  jbe     short loc_18002F07D
0x18002f07a  mov     rcx, [rcx]
0x18002f07d  mov     dword ptr [rcx+rdx*2], 0Ah
0x18002f084  jmp     loc_18002EFE4
0x18002f089  mov     r9d, 0Ah
0x18002f08f  jmp     loc_18002EFDF
0x18002f094  lea     rcx, [rsi+8]
0x18002f098  mov     rdx, [rcx+10h]
0x18002f09c  cmp     rdx, [rcx+18h]
0x18002f0a0  jnb     short loc_18002F0C0
0x18002f0a2  cmp     qword ptr [rcx+18h], 7
0x18002f0a7  lea     rax, [rdx+1]
0x18002f0ab  mov     [rcx+10h], rax
0x18002f0af  jbe     short loc_18002F0B4
0x18002f0b1  mov     rcx, [rcx]
0x18002f0b4  mov     dword ptr [rcx+rdx*2], 0Ch
0x18002f0bb  jmp     loc_18002EFE4
0x18002f0c0  mov     r9d, 0Ch
0x18002f0c6  jmp     loc_18002EFDF
0x18002f0cb  lea     rcx, [rsi+8]
0x18002f0cf  mov     rdx, [rcx+10h]
0x18002f0d3  cmp     rdx, [rcx+18h]
0x18002f0d7  jnb     short loc_18002F0F7
0x18002f0d9  cmp     qword ptr [rcx+18h], 7
0x18002f0de  lea     rax, [rdx+1]
0x18002f0e2  mov     [rcx+10h], rax
0x18002f0e6  jbe     short loc_18002F0EB
0x18002f0e8  mov     rcx, [rcx]
0x18002f0eb  mov     dword ptr [rcx+rdx*2], 8
0x18002f0f2  jmp     loc_18002EFE4
0x18002f0f7  mov     r9d, 8
0x18002f0fd  jmp     loc_18002EFDF
0x18002f102  lea     rcx, [rsi+8]
0x18002f106  mov     rdx, [rcx+10h]
0x18002f10a  cmp     rdx, [rcx+18h]
0x18002f10e  jnb     short loc_18002F12E
0x18002f110  cmp     qword ptr [rcx+18h], 7
0x18002f115  lea     rax, [rdx+1]
0x18002f119  mov     [rcx+10h], rax
0x18002f11d  jbe     short loc_18002F122
0x18002f11f  mov     rcx, [rcx]
0x18002f122  mov     dword ptr [rcx+rdx*2], 5Ch ; '\'
0x18002f129  jmp     loc_18002EFE4
0x18002f12e  mov     r9d, 5Ch ; '\'
0x18002f134  jmp     loc_18002EFDF
0x18002f139  lea     rcx, [rsi+8]
0x18002f13d  mov     rdx, [rcx+10h]
0x18002f141  cmp     rdx, [rcx+18h]
0x18002f145  jnb     short loc_18002F165
0x18002f147  cmp     qword ptr [rcx+18h], 7
0x18002f14c  lea     rax, [rdx+1]
0x18002f150  mov     [rcx+10h], rax
0x18002f154  jbe     short loc_18002F159
0x18002f156  mov     rcx, [rcx]
0x18002f159  mov     dword ptr [rcx+rdx*2], 2Fh ; '/'
0x18002f160  jmp     loc_18002EFE4
0x18002f165  mov     r9d, 2Fh ; '/'
0x18002f16b  jmp     loc_18002EFDF
0x18002f170  lea     rcx, [rsi+8]
0x18002f174  mov     rdx, [rcx+10h]
0x18002f178  cmp     rdx, [rcx+18h]
0x18002f17c  jnb     loc_18002EFDF
0x18002f182  cmp     qword ptr [rcx+18h], 7
0x18002f187  lea     rax, [rdx+1]
0x18002f18b  mov     [rcx+10h], rax
0x18002f18f  jbe     short loc_18002F194
0x18002f191  mov     rcx, [rcx]
0x18002f194  mov     [rcx+rdx*2], r9d
0x18002f198  jmp     loc_18002EFE4
```
