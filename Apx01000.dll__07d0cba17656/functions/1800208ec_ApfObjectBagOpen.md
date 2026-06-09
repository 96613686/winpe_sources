# ApfObjectBagOpen

- ea: `0x1800208ec`
- end: `0x180020b6c`
- name: `ApfObjectBagOpen`
- size: `640`
- prototype: `__int64 __fastcall(Apx::ApfVerify **, Apx::ApfVerify *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180017ba4`

## callees

- `0x18000a12c`
- `0x18000a154`
- `0x18000a1b4`
- `0x18000a8e8`
- `0x18000aea8`
- `0x18000d210`
- `0x1800203ac`
- `0x1800208ec`

## string_xrefs

- `0x180020941`: `Config`

## pseudocode

```c
__int64 __fastcall ApfObjectBagOpen(Apx::ApfVerify **a1, Apx::ApfVerify *this, const unsigned __int16 *a3)
{
  struct Apx::ApfObjectBag *v5; // rsi
  int IsNotNull; // ebx
  const unsigned __int16 *v7; // r8
  const unsigned __int16 *v8; // rdx
  _QWORD *v9; // rcx
  unsigned int v10; // eax
  Apx::ApfVerify *v11; // rcx
  __int64 v12; // rdx
  Apx::ApfVerify *v13; // rax
  struct Apx::ApfObjectBag *v15; // [rsp+70h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_7d1103ce0f2130c34abf2862b3df7f94_Traceguids);
  }
  v15 = 0;
  v5 = 0;
  IsNotNull = Apx::ApfVerify::IsNotNull((Apx::ApfVerify *)a1, L"Config", a3);
  if ( IsNotNull < 0 )
    goto LABEL_41;
  IsNotNull = Apx::ApfVerify::IsNotNull(this, L"ObjectBag", v7);
  if ( IsNotNull < 0 )
    goto LABEL_41;
  *(_QWORD *)this = 0;
  if ( *(_DWORD *)a1 == 48 )
  {
    v10 = *((_DWORD *)a1 + 1);
    if ( (v10 & 0xFFFFFFF0) != 0 )
    {
      IsNotNull = -2147024809;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return (unsigned int)IsNotNull;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_42;
      WPP_SF_DDd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_7d1103ce0f2130c34abf2862b3df7f94_Traceguids, v10, 15);
      goto LABEL_41;
    }
    v11 = a1[2];
    if ( !v11 || (IsNotNull = Apx::ApfVerify::ValidateString(v11, v8), IsNotNull >= 0) )
    {
      if ( (*((_BYTE *)a1 + 4) & 8) != 0 )
      {
        IsNotNull = -2147024809;
        if ( a1[3] )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            return (unsigned int)IsNotNull;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_42;
          v12 = 15;
        }
        else
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            return (unsigned int)IsNotNull;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_42;
          v12 = 13;
        }
        WPP_SF_d(v9[2], v12, WPP_7d1103ce0f2130c34abf2862b3df7f94_Traceguids);
        goto LABEL_41;
      }
      v13 = a1[2];
      if ( v13 && *(_WORD *)v13 )
      {
        IsNotNull = Apx::ApfObjectBag::_CreateAndInitialize((struct Apx::_APF_OBJECTBAG_CONFIG *)a1, &v15);
        if ( IsNotNull >= 0 )
        {
          IsNotNull = 0;
          *(_QWORD *)this = ~(unsigned __int64)v15;
          goto LABEL_41;
        }
        v5 = v15;
      }
      else
      {
        IsNotNull = -2147024809;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return (unsigned int)IsNotNull;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_42;
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_7d1103ce0f2130c34abf2862b3df7f94_Traceguids);
      }
      if ( v5 )
        imp_ApxObjectDelete(0, (Apx::ApfVerify *)~(unsigned __int64)v5);
    }
LABEL_41:
    v9 = WPP_GLOBAL_Control;
    goto LABEL_42;
  }
  IsNotNull = -2147024809;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return (unsigned int)IsNotNull;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_DDd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_7d1103ce0f2130c34abf2862b3df7f94_Traceguids,
      48,
      *(_DWORD *)a1);
    goto LABEL_41;
  }
LABEL_42:
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 && *((_BYTE *)v9 + 25) >= 5u )
    WPP_SF_(v9[2], 16, WPP_7d1103ce0f2130c34abf2862b3df7f94_Traceguids);
  return (unsigned int)IsNotNull;
}

```

## disassembly

```asm
0x1800208ec  mov     [rsp+arg_0], rbx
0x1800208f1  mov     [rsp+arg_8], rbp
0x1800208f6  push    rsi
0x1800208f7  push    rdi
0x1800208f8  push    r12
0x1800208fa  push    r14
0x1800208fc  push    r15
0x1800208fe  sub     rsp, 30h
0x180020902  mov     r14, rdx
0x180020905  mov     rdi, rcx
0x180020908  mov     rcx, cs:WPP_GLOBAL_Control
0x18002090f  lea     r15, WPP_GLOBAL_Control
0x180020916  lea     r12, WPP_7d1103ce0f2130c34abf2862b3df7f94_Traceguids
0x18002091d  cmp     rcx, r15
0x180020920  jz      short loc_18002093F
0x180020922  test    byte ptr [rcx+1Ch], 1
0x180020926  jz      short loc_18002093F
0x180020928  cmp     byte ptr [rcx+19h], 5
0x18002092c  jb      short loc_18002093F
0x18002092e  mov     rcx, [rcx+10h]
0x180020932  mov     edx, 0Ah
0x180020937  mov     r8, r12
0x18002093a  call    WPP_SF_
0x18002093f  xor     ebp, ebp
0x180020941  lea     rdx, aConfig_0; "Config"
0x180020948  mov     rcx, rdi; this
0x18002094b  mov     [rsp+58h+arg_10], rbp
0x180020950  mov     esi, ebp
0x180020952  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x180020957  mov     ebx, eax
0x180020959  test    eax, eax
0x18002095b  js      loc_180020B2A
0x180020961  lea     rdx, aObjectbag; "ObjectBag"
0x180020968  mov     rcx, r14; this
0x18002096b  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x180020970  mov     ebx, eax
0x180020972  test    eax, eax
0x180020974  js      loc_180020B2A
0x18002097a  mov     [r14], rbp
0x18002097d  mov     eax, [rdi]
0x18002097f  cmp     eax, 30h ; '0'
0x180020982  jz      short loc_1800209C9
0x180020984  mov     ebx, 80070057h
0x180020989  mov     rcx, cs:WPP_GLOBAL_Control
0x180020990  cmp     rcx, r15
0x180020993  jz      loc_180020B53
0x180020999  test    byte ptr [rcx+1Ch], 40h
0x18002099d  jz      loc_180020B31
0x1800209a3  cmp     byte ptr [rcx+19h], 2
0x1800209a7  jb      loc_180020B31
0x1800209ad  mov     rcx, [rcx+10h]
0x1800209b1  lea     edx, [rbp+0Bh]
0x1800209b4  lea     r9d, [rbp+30h]
0x1800209b8  mov     [rsp+58h+var_38], eax
0x1800209bc  mov     r8, r12
0x1800209bf  call    WPP_SF_DDd
0x1800209c4  jmp     loc_180020B2A
0x1800209c9  mov     eax, [rdi+4]
0x1800209cc  test    eax, 0FFFFFFF0h
0x1800209d1  jz      short loc_180020A1D
0x1800209d3  mov     ebx, 80070057h
0x1800209d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800209df  cmp     rcx, r15
0x1800209e2  jz      loc_180020B53
0x1800209e8  test    byte ptr [rcx+1Ch], 40h
0x1800209ec  jz      loc_180020B31
0x1800209f2  cmp     byte ptr [rcx+19h], 2
0x1800209f6  jb      loc_180020B31
0x1800209fc  mov     rcx, [rcx+10h]
0x180020a00  mov     edx, 0Ch
0x180020a05  mov     r9d, eax
0x180020a08  mov     [rsp+58h+var_38], 0Fh
0x180020a10  mov     r8, r12
0x180020a13  call    WPP_SF_DDd
0x180020a18  jmp     loc_180020B2A
0x180020a1d  mov     rcx, [rdi+10h]; this
0x180020a21  test    rcx, rcx
0x180020a24  jz      short loc_180020A35
0x180020a26  call    ?ValidateString@ApfVerify@Apx@@YAJPEBG@Z; Apx::ApfVerify::ValidateString(ushort const *)
0x180020a2b  mov     ebx, eax
0x180020a2d  test    eax, eax
0x180020a2f  js      loc_180020B2A
0x180020a35  test    byte ptr [rdi+4], 8
0x180020a39  jz      short loc_180020AAF
0x180020a3b  mov     r9d, 80070057h
0x180020a41  mov     ebx, r9d
0x180020a44  cmp     [rdi+18h], rbp
0x180020a48  jnz     short loc_180020A84
0x180020a4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180020a51  cmp     rcx, r15
0x180020a54  jz      loc_180020B53
0x180020a5a  test    byte ptr [rcx+1Ch], 40h
0x180020a5e  jz      loc_180020B31
0x180020a64  cmp     byte ptr [rcx+19h], 2
0x180020a68  jb      loc_180020B31
0x180020a6e  mov     edx, 0Dh
0x180020a73  mov     rcx, [rcx+10h]
0x180020a77  mov     r8, r12
0x180020a7a  call    WPP_SF_d
0x180020a7f  jmp     loc_180020B2A
0x180020a84  mov     rcx, cs:WPP_GLOBAL_Control
0x180020a8b  cmp     rcx, r15
0x180020a8e  jz      loc_180020B53
0x180020a94  test    byte ptr [rcx+1Ch], 40h
0x180020a98  jz      loc_180020B31
0x180020a9e  cmp     byte ptr [rcx+19h], 2
0x180020aa2  jb      loc_180020B31
0x180020aa8  mov     edx, 0Fh
0x180020aad  jmp     short loc_180020A73
0x180020aaf  mov     rax, [rdi+10h]
0x180020ab3  test    rax, rax
0x180020ab6  jz      short loc_180020AE6
0x180020ab8  cmp     [rax], bp
0x180020abb  jz      short loc_180020AE6
0x180020abd  lea     rdx, [rsp+58h+arg_10]; struct Apx::ApfObjectBag **
0x180020ac2  mov     rcx, rdi; struct Apx::_APF_OBJECTBAG_CONFIG *
0x180020ac5  call    ?_CreateAndInitialize@ApfObjectBag@Apx@@SAJPEAU_APF_OBJECTBAG_CONFIG@2@PEAPEAV12@@Z; Apx::ApfObjectBag::_CreateAndInitialize(Apx::_APF_OBJECTBAG_CONFIG *,Apx::ApfObjectBag * *)
0x180020aca  mov     ebx, eax
0x180020acc  test    eax, eax
0x180020ace  js      short loc_180020ADF
0x180020ad0  mov     rax, [rsp+58h+arg_10]
0x180020ad5  mov     ebx, ebp
0x180020ad7  not     rax
0x180020ada  mov     [r14], rax
0x180020add  jmp     short loc_180020B2A
0x180020adf  mov     rsi, [rsp+58h+arg_10]
0x180020ae4  jmp     short loc_180020B18
0x180020ae6  mov     r9d, 80070057h
0x180020aec  mov     ebx, r9d
0x180020aef  mov     rcx, cs:WPP_GLOBAL_Control
0x180020af6  cmp     rcx, r15
0x180020af9  jz      short loc_180020B53
0x180020afb  test    byte ptr [rcx+1Ch], 40h
0x180020aff  jz      short loc_180020B31
0x180020b01  cmp     byte ptr [rcx+19h], 2
0x180020b05  jb      short loc_180020B31
0x180020b07  mov     rcx, [rcx+10h]
0x180020b0b  mov     edx, 0Eh
0x180020b10  mov     r8, r12
0x180020b13  call    WPP_SF_d
0x180020b18  test    rsi, rsi
0x180020b1b  jz      short loc_180020B2A
0x180020b1d  not     rsi
0x180020b20  xor     ecx, ecx; this
0x180020b22  mov     rdx, rsi; Apx::ApfVerify *
0x180020b25  call    imp_ApxObjectDelete
0x180020b2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b31  cmp     rcx, r15
0x180020b34  jz      short loc_180020B53
0x180020b36  test    byte ptr [rcx+1Ch], 1
0x180020b3a  jz      short loc_180020B53
0x180020b3c  cmp     byte ptr [rcx+19h], 5
0x180020b40  jb      short loc_180020B53
0x180020b42  mov     rcx, [rcx+10h]
0x180020b46  mov     edx, 10h
0x180020b4b  mov     r8, r12
0x180020b4e  call    WPP_SF_
0x180020b53  mov     rbp, [rsp+58h+arg_8]
0x180020b58  mov     eax, ebx
0x180020b5a  mov     rbx, [rsp+58h+arg_0]
0x180020b5f  add     rsp, 30h
0x180020b63  pop     r15
0x180020b65  pop     r14
0x180020b67  pop     r12
0x180020b69  pop     rdi
0x180020b6a  pop     rsi
0x180020b6b  retn
```
