# imp_ApxJackCreate

- ea: `0x180025310`
- end: `0x1800255fa`
- name: `imp_ApxJackCreate`
- size: `746`
- prototype: `__int64 __fastcall(Apx::ApfVerify *this, Apx::ApfVerify *, struct _APX_JACK_CONFIG *, Apx::ApfVerify *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0x18000a12c`
- `0x18000a154`
- `0x18000a1b4`
- `0x18000a820`
- `0x18000a8e8`
- `0x18000a948`
- `0x18000ae48`
- `0x18000d210`
- `0x180025130`
- `0x180025310`

## string_xrefs

- `0x1800253be`: `Config`

## pseudocode

```c
__int64 __fastcall imp_ApxJackCreate(
        Apx::ApfVerify *this,
        Apx::ApfVerify *a2,
        struct _APX_JACK_CONFIG *a3,
        Apx::ApfVerify *a4)
{
  Apx::ApfVerify *v8; // rcx
  int IsNull; // ebx
  struct APX_CLIENT_GLOBALS__ *v10; // rdx
  const unsigned __int16 *v11; // r8
  const unsigned __int16 *v12; // r8
  const unsigned __int16 *v13; // r8
  _QWORD *v14; // rcx
  unsigned int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rax
  struct Apx::ApfJack *v19; // [rsp+30h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_e67c265a27cd31bd325b8c3a7ff5f216_Traceguids);
  }
  v19 = 0;
  IsNull = Apx::ApfVerify::IsNull(this, L"Globals", (const unsigned __int16 *)a3);
  if ( IsNull < 0 )
    goto LABEL_48;
  IsNull = Apx::ApfVerify::IsApxInitialized(v8);
  if ( IsNull < 0 )
    goto LABEL_48;
  IsNull = Apx::ApfVerify::ValidateClientBindings(this, v10);
  if ( IsNull < 0 )
    goto LABEL_48;
  IsNull = Apx::ApfVerify::IsNull(a2, L"Attributes", v11);
  if ( IsNull < 0 )
    goto LABEL_48;
  IsNull = Apx::ApfVerify::IsNotNull(a3, L"Config", v12);
  if ( IsNull < 0 )
    goto LABEL_48;
  IsNull = Apx::ApfVerify::IsNotNull(a4, L"Jack", v13);
  if ( IsNull < 0 )
    goto LABEL_48;
  *(_QWORD *)a4 = 0;
  if ( *(_DWORD *)a3 == 48 )
  {
    v15 = *((_DWORD *)a3 + 2);
    if ( (v15 & 0xFFFFFFFE) != 0 )
    {
      IsNull = -2147024809;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return (unsigned int)IsNull;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_49;
      WPP_SF_DDd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_e67c265a27cd31bd325b8c3a7ff5f216_Traceguids, v15, 1);
      goto LABEL_48;
    }
    if ( *((_DWORD *)a3 + 1) != -1 )
    {
      IsNull = -2147024809;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return (unsigned int)IsNull;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_49;
      v16 = 13;
LABEL_27:
      WPP_SF_d(v14[2], v16, WPP_e67c265a27cd31bd325b8c3a7ff5f216_Traceguids);
LABEL_48:
      v14 = WPP_GLOBAL_Control;
      goto LABEL_49;
    }
    if ( (v15 & 1) != 0 )
    {
      v17 = *((_QWORD *)a3 + 2);
      if ( !v17 )
      {
        IsNull = -2147024809;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return (unsigned int)IsNull;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_49;
        v16 = 14;
        goto LABEL_27;
      }
      if ( *(_DWORD *)v17 != 16 )
      {
        IsNull = -2147024809;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return (unsigned int)IsNull;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_49;
        WPP_SF_DDd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          WPP_e67c265a27cd31bd325b8c3a7ff5f216_Traceguids,
          16,
          *(_DWORD *)v17);
        goto LABEL_48;
      }
      if ( !*(_QWORD *)(v17 + 8) )
      {
        IsNull = -2147024809;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return (unsigned int)IsNull;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_49;
        v16 = 16;
        goto LABEL_27;
      }
    }
    IsNull = Apx::ApfJack::_CreateAndInitialize(a3, &v19);
    if ( IsNull < 0 )
    {
      if ( v19 )
        imp_ApxObjectDelete(0, (Apx::ApfVerify *)~(unsigned __int64)v19);
    }
    else
    {
      IsNull = 0;
      *(_QWORD *)a4 = ~(unsigned __int64)v19;
    }
    goto LABEL_48;
  }
  IsNull = -2147024809;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return (unsigned int)IsNull;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_DDd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_e67c265a27cd31bd325b8c3a7ff5f216_Traceguids,
      48,
      *(_DWORD *)a3);
    goto LABEL_48;
  }
LABEL_49:
  if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 5u )
    WPP_SF_(v14[2], 17, WPP_e67c265a27cd31bd325b8c3a7ff5f216_Traceguids);
  return (unsigned int)IsNull;
}

```

## disassembly

```asm
0x180025310  push    rbx
0x180025312  push    rbp
0x180025313  push    rsi
0x180025314  push    rdi
0x180025315  push    r12
0x180025317  push    r13
0x180025319  push    r14
0x18002531b  sub     rsp, 40h
0x18002531f  mov     rsi, r9
0x180025322  mov     rdi, r8
0x180025325  mov     r14, rdx
0x180025328  mov     rbp, rcx
0x18002532b  mov     rcx, cs:WPP_GLOBAL_Control
0x180025332  lea     r12, WPP_GLOBAL_Control
0x180025339  lea     r13, WPP_e67c265a27cd31bd325b8c3a7ff5f216_Traceguids
0x180025340  cmp     rcx, r12
0x180025343  jz      short loc_180025362
0x180025345  test    byte ptr [rcx+1Ch], 1
0x180025349  jz      short loc_180025362
0x18002534b  cmp     byte ptr [rcx+19h], 5
0x18002534f  jb      short loc_180025362
0x180025351  mov     rcx, [rcx+10h]
0x180025355  mov     edx, 0Ah
0x18002535a  mov     r8, r13
0x18002535d  call    WPP_SF_
0x180025362  lea     rdx, aGlobals; "Globals"
0x180025369  mov     [rsp+78h+var_48], 0
0x180025372  mov     rcx, rbp; this
0x180025375  call    ?IsNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNull(void const *,ushort const *)
0x18002537a  mov     ebx, eax
0x18002537c  test    eax, eax
0x18002537e  js      loc_1800255C0
0x180025384  call    ?IsApxInitialized@ApfVerify@Apx@@YAJXZ; Apx::ApfVerify::IsApxInitialized(void)
0x180025389  mov     ebx, eax
0x18002538b  test    eax, eax
0x18002538d  js      loc_1800255C0
0x180025393  mov     rcx, rbp; this
0x180025396  call    ?ValidateClientBindings@ApfVerify@Apx@@YAJPEAUAPX_CLIENT_GLOBALS__@@@Z; Apx::ApfVerify::ValidateClientBindings(APX_CLIENT_GLOBALS__ *)
0x18002539b  mov     ebx, eax
0x18002539d  test    eax, eax
0x18002539f  js      loc_1800255C0
0x1800253a5  lea     rdx, aAttributes; "Attributes"
0x1800253ac  mov     rcx, r14; this
0x1800253af  call    ?IsNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNull(void const *,ushort const *)
0x1800253b4  mov     ebx, eax
0x1800253b6  test    eax, eax
0x1800253b8  js      loc_1800255C0
0x1800253be  lea     rdx, aConfig_0; "Config"
0x1800253c5  mov     rcx, rdi; this
0x1800253c8  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x1800253cd  mov     ebx, eax
0x1800253cf  test    eax, eax
0x1800253d1  js      loc_1800255C0
0x1800253d7  lea     rdx, aJack; "Jack"
0x1800253de  mov     rcx, rsi; this
0x1800253e1  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x1800253e6  mov     ebx, eax
0x1800253e8  test    eax, eax
0x1800253ea  js      loc_1800255C0
0x1800253f0  mov     qword ptr [rsi], 0
0x1800253f7  mov     r9d, 30h ; '0'
0x1800253fd  mov     eax, [rdi]
0x1800253ff  cmp     eax, r9d
0x180025402  jz      short loc_180025446
0x180025404  mov     ebx, 80070057h
0x180025409  mov     rcx, cs:WPP_GLOBAL_Control
0x180025410  cmp     rcx, r12
0x180025413  jz      loc_1800255E9
0x180025419  test    byte ptr [rcx+1Ch], 40h
0x18002541d  jz      loc_1800255C7
0x180025423  cmp     byte ptr [rcx+19h], 2
0x180025427  jb      loc_1800255C7
0x18002542d  lea     edx, [r9-25h]
0x180025431  mov     [rsp+78h+var_58], eax
0x180025435  mov     rcx, [rcx+10h]
0x180025439  mov     r8, r13
0x18002543c  call    WPP_SF_DDd
0x180025441  jmp     loc_1800255C0
0x180025446  mov     eax, [rdi+8]
0x180025449  test    eax, 0FFFFFFFEh
0x18002544e  jz      short loc_18002549A
0x180025450  mov     ebx, 80070057h
0x180025455  mov     rcx, cs:WPP_GLOBAL_Control
0x18002545c  cmp     rcx, r12
0x18002545f  jz      loc_1800255E9
0x180025465  test    byte ptr [rcx+1Ch], 40h
0x180025469  jz      loc_1800255C7
0x18002546f  cmp     byte ptr [rcx+19h], 2
0x180025473  jb      loc_1800255C7
0x180025479  mov     rcx, [rcx+10h]
0x18002547d  mov     edx, 0Ch
0x180025482  mov     r9d, eax
0x180025485  mov     [rsp+78h+var_58], 1
0x18002548d  mov     r8, r13
0x180025490  call    WPP_SF_DDd
0x180025495  jmp     loc_1800255C0
0x18002549a  cmp     dword ptr [rdi+4], 0FFFFFFFFh
0x18002549e  jz      short loc_1800254E2
0x1800254a0  mov     ebx, 80070057h
0x1800254a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800254ac  cmp     rcx, r12
0x1800254af  jz      loc_1800255E9
0x1800254b5  test    byte ptr [rcx+1Ch], 40h
0x1800254b9  jz      loc_1800255C7
0x1800254bf  cmp     byte ptr [rcx+19h], 2
0x1800254c3  jb      loc_1800255C7
0x1800254c9  mov     edx, 0Dh
0x1800254ce  mov     rcx, [rcx+10h]
0x1800254d2  mov     r9d, ebx
0x1800254d5  mov     r8, r13
0x1800254d8  call    WPP_SF_d
0x1800254dd  jmp     loc_1800255C0
0x1800254e2  test    al, 1
0x1800254e4  jz      loc_18002558A
0x1800254ea  mov     rax, [rdi+10h]
0x1800254ee  test    rax, rax
0x1800254f1  jnz     short loc_180025521
0x1800254f3  mov     ebx, 80070057h
0x1800254f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800254ff  cmp     rcx, r12
0x180025502  jz      loc_1800255E9
0x180025508  test    byte ptr [rcx+1Ch], 40h
0x18002550c  jz      loc_1800255C7
0x180025512  cmp     byte ptr [rcx+19h], 2
0x180025516  jb      loc_1800255C7
0x18002551c  lea     edx, [rax+0Eh]
0x18002551f  jmp     short loc_1800254CE
0x180025521  mov     r8d, [rax]
0x180025524  mov     r9d, 10h
0x18002552a  cmp     r8d, r9d
0x18002552d  jz      short loc_18002555E
0x18002552f  mov     ebx, 80070057h
0x180025534  mov     rcx, cs:WPP_GLOBAL_Control
0x18002553b  cmp     rcx, r12
0x18002553e  jz      loc_1800255E9
0x180025544  test    byte ptr [rcx+1Ch], 40h
0x180025548  jz      short loc_1800255C7
0x18002554a  cmp     byte ptr [rcx+19h], 2
0x18002554e  jb      short loc_1800255C7
0x180025550  lea     edx, [r9-1]
0x180025554  mov     [rsp+78h+var_58], r8d
0x180025559  jmp     loc_180025435
0x18002555e  cmp     qword ptr [rax+8], 0
0x180025563  jnz     short loc_18002558A
0x180025565  mov     ebx, 80070057h
0x18002556a  mov     rcx, cs:WPP_GLOBAL_Control
0x180025571  cmp     rcx, r12
0x180025574  jz      short loc_1800255E9
0x180025576  test    byte ptr [rcx+1Ch], 40h
0x18002557a  jz      short loc_1800255C7
0x18002557c  cmp     byte ptr [rcx+19h], 2
0x180025580  jb      short loc_1800255C7
0x180025582  mov     edx, r9d
0x180025585  jmp     loc_1800254CE
0x18002558a  lea     rdx, [rsp+78h+var_48]; struct Apx::ApfJack **
0x18002558f  mov     rcx, rdi; struct _APX_JACK_CONFIG *
0x180025592  call    ?_CreateAndInitialize@ApfJack@Apx@@SAJPEAU_APX_JACK_CONFIG@@PEAPEAV12@@Z; Apx::ApfJack::_CreateAndInitialize(_APX_JACK_CONFIG *,Apx::ApfJack * *)
0x180025597  mov     ebx, eax
0x180025599  test    eax, eax
0x18002559b  js      short loc_1800255AC
0x18002559d  mov     rax, [rsp+78h+var_48]
0x1800255a2  xor     ebx, ebx
0x1800255a4  not     rax
0x1800255a7  mov     [rsi], rax
0x1800255aa  jmp     short loc_1800255C0
0x1800255ac  mov     rdx, [rsp+78h+var_48]
0x1800255b1  test    rdx, rdx
0x1800255b4  jz      short loc_1800255C0
0x1800255b6  not     rdx; Apx::ApfVerify *
0x1800255b9  xor     ecx, ecx; this
0x1800255bb  call    imp_ApxObjectDelete
0x1800255c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800255c7  cmp     rcx, r12
0x1800255ca  jz      short loc_1800255E9
0x1800255cc  test    byte ptr [rcx+1Ch], 1
0x1800255d0  jz      short loc_1800255E9
0x1800255d2  cmp     byte ptr [rcx+19h], 5
0x1800255d6  jb      short loc_1800255E9
0x1800255d8  mov     rcx, [rcx+10h]
0x1800255dc  mov     edx, 11h
0x1800255e1  mov     r8, r13
0x1800255e4  call    WPP_SF_
0x1800255e9  mov     eax, ebx
0x1800255eb  add     rsp, 40h
0x1800255ef  pop     r14
0x1800255f1  pop     r13
0x1800255f3  pop     r12
0x1800255f5  pop     rdi
0x1800255f6  pop     rsi
0x1800255f7  pop     rbp
0x1800255f8  pop     rbx
0x1800255f9  retn
```
