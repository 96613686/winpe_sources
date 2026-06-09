# imp_ApxMuteCreate

- ea: `0x18001c400`
- end: `0x18001c7a4`
- name: `imp_ApxMuteCreate`
- size: `932`
- prototype: `__int64 __fastcall(Apx::ApfVerify *this, Apx::ApfVerify *, struct _APX_MUTE_CONFIG *, Apx::ApfVerify *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x18000a12c`
- `0x18000a154`
- `0x18000a1b4`
- `0x18000a820`
- `0x18000a8e8`
- `0x18000a948`
- `0x18000ae48`
- `0x18000be74`
- `0x18000d210`
- `0x18001bf50`
- `0x18001c400`

## string_xrefs

- `0x18001c4a9`: `Config`

## pseudocode

```c
__int64 __fastcall imp_ApxMuteCreate(
        Apx::ApfVerify *this,
        Apx::ApfVerify *a2,
        struct _APX_MUTE_CONFIG *a3,
        Apx::ApfVerify *a4)
{
  struct Apx::ApfMute *v8; // rsi
  Apx::ApfVerify *v9; // rcx
  int IsNull; // ebx
  struct APX_CLIENT_GLOBALS__ *v11; // rdx
  const unsigned __int16 *v12; // r8
  const unsigned __int16 *v13; // r8
  const unsigned __int16 *v14; // r8
  _QWORD *v15; // rcx
  unsigned int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rdx
  struct Apx::ApfMute *v20; // [rsp+30h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ef16463b4e5c3f467a4309089a5279ae_Traceguids);
  }
  v8 = 0;
  v20 = 0;
  IsNull = Apx::ApfVerify::IsNull(this, L"Globals", (const unsigned __int16 *)a3);
  if ( IsNull < 0 )
    goto LABEL_59;
  IsNull = Apx::ApfVerify::IsApxInitialized(v9);
  if ( IsNull < 0 )
    goto LABEL_59;
  IsNull = Apx::ApfVerify::ValidateClientBindings(this, v11);
  if ( IsNull < 0 )
    goto LABEL_59;
  IsNull = Apx::ApfVerify::IsNull(a2, L"Attributes", v12);
  if ( IsNull < 0 )
    goto LABEL_59;
  IsNull = Apx::ApfVerify::IsNotNull(a3, L"Config", v13);
  if ( IsNull < 0 )
    goto LABEL_59;
  IsNull = Apx::ApfVerify::IsNotNull(a4, L"Mute", v14);
  if ( IsNull < 0 )
    goto LABEL_59;
  *(_QWORD *)a4 = 0;
  if ( *(_DWORD *)a3 == 32 )
  {
    v16 = *((_DWORD *)a3 + 4);
    if ( v16 )
    {
      IsNull = -2147024809;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return (unsigned int)IsNull;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_60;
      WPP_SF_DDd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ef16463b4e5c3f467a4309089a5279ae_Traceguids, v16, 0);
      goto LABEL_59;
    }
    v17 = *((_QWORD *)a3 + 3);
    if ( !v17 )
    {
      IsNull = -2147024809;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return (unsigned int)IsNull;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_60;
      v18 = 13;
LABEL_27:
      WPP_SF_d(v15[2], v18, WPP_ef16463b4e5c3f467a4309089a5279ae_Traceguids);
LABEL_59:
      v15 = WPP_GLOBAL_Control;
      goto LABEL_60;
    }
    if ( *(_DWORD *)v17 != 24 )
    {
      IsNull = -2147024809;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return (unsigned int)IsNull;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_60;
      WPP_SF_DDd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_ef16463b4e5c3f467a4309089a5279ae_Traceguids,
        24,
        *(_DWORD *)v17);
      goto LABEL_59;
    }
    if ( *(_QWORD *)(v17 + 16) && *(_QWORD *)(v17 + 8) )
    {
      if ( *((_DWORD *)a3 + 1) != -1 )
      {
        IsNull = -2147024809;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return (unsigned int)IsNull;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_60;
        v18 = 16;
        goto LABEL_27;
      }
      if ( !*((_DWORD *)a3 + 5) )
      {
        IsNull = -2147024809;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return (unsigned int)IsNull;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_60;
        v18 = 17;
        goto LABEL_27;
      }
      if ( *((_DWORD *)a3 + 5) > 0xFFFFu )
      {
        IsNull = -2147024809;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return (unsigned int)IsNull;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_60;
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_ef16463b4e5c3f467a4309089a5279ae_Traceguids);
        goto LABEL_59;
      }
      IsNull = Apx::ApfMute::_CreateAndInitialize(a3, &v20);
      if ( IsNull >= 0 )
      {
        IsNull = 0;
        *(_QWORD *)a4 = ~(unsigned __int64)v20;
        goto LABEL_59;
      }
      v8 = v20;
    }
    else
    {
      IsNull = -2147024809;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return (unsigned int)IsNull;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_60;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_ef16463b4e5c3f467a4309089a5279ae_Traceguids);
    }
    if ( v8 )
      imp_ApxObjectDelete(0, (Apx::ApfVerify *)~(unsigned __int64)v8);
    goto LABEL_59;
  }
  IsNull = -2147024809;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return (unsigned int)IsNull;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_DDd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_ef16463b4e5c3f467a4309089a5279ae_Traceguids,
      32,
      *(_DWORD *)a3);
    goto LABEL_59;
  }
LABEL_60:
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) >= 5u )
    WPP_SF_(v15[2], 19, WPP_ef16463b4e5c3f467a4309089a5279ae_Traceguids);
  return (unsigned int)IsNull;
}

```

## disassembly

```asm
0x18001c400  push    rbx
0x18001c402  push    rbp
0x18001c403  push    rsi
0x18001c404  push    rdi
0x18001c405  push    r13
0x18001c407  push    r14
0x18001c409  push    r15
0x18001c40b  sub     rsp, 40h
0x18001c40f  mov     r14, r9
0x18001c412  mov     rdi, r8
0x18001c415  mov     r15, rdx
0x18001c418  mov     rbp, rcx
0x18001c41b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c422  lea     r13, WPP_GLOBAL_Control
0x18001c429  cmp     rcx, r13
0x18001c42c  jz      short loc_18001C44F
0x18001c42e  test    byte ptr [rcx+1Ch], 1
0x18001c432  jz      short loc_18001C44F
0x18001c434  cmp     byte ptr [rcx+19h], 5
0x18001c438  jb      short loc_18001C44F
0x18001c43a  mov     rcx, [rcx+10h]
0x18001c43e  lea     r8, WPP_ef16463b4e5c3f467a4309089a5279ae_Traceguids
0x18001c445  mov     edx, 0Ah
0x18001c44a  call    WPP_SF_
0x18001c44f  xor     esi, esi
0x18001c451  lea     rdx, aGlobals; "Globals"
0x18001c458  mov     rcx, rbp; this
0x18001c45b  mov     [rsp+78h+var_48], rsi
0x18001c460  call    ?IsNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNull(void const *,ushort const *)
0x18001c465  mov     ebx, eax
0x18001c467  test    eax, eax
0x18001c469  js      loc_18001C766
0x18001c46f  call    ?IsApxInitialized@ApfVerify@Apx@@YAJXZ; Apx::ApfVerify::IsApxInitialized(void)
0x18001c474  mov     ebx, eax
0x18001c476  test    eax, eax
0x18001c478  js      loc_18001C766
0x18001c47e  mov     rcx, rbp; this
0x18001c481  call    ?ValidateClientBindings@ApfVerify@Apx@@YAJPEAUAPX_CLIENT_GLOBALS__@@@Z; Apx::ApfVerify::ValidateClientBindings(APX_CLIENT_GLOBALS__ *)
0x18001c486  mov     ebx, eax
0x18001c488  test    eax, eax
0x18001c48a  js      loc_18001C766
0x18001c490  lea     rdx, aAttributes; "Attributes"
0x18001c497  mov     rcx, r15; this
0x18001c49a  call    ?IsNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNull(void const *,ushort const *)
0x18001c49f  mov     ebx, eax
0x18001c4a1  test    eax, eax
0x18001c4a3  js      loc_18001C766
0x18001c4a9  lea     rdx, aConfig_0; "Config"
0x18001c4b0  mov     rcx, rdi; this
0x18001c4b3  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x18001c4b8  mov     ebx, eax
0x18001c4ba  test    eax, eax
0x18001c4bc  js      loc_18001C766
0x18001c4c2  lea     rdx, aMute; "Mute"
0x18001c4c9  mov     rcx, r14; this
0x18001c4cc  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x18001c4d1  mov     ebx, eax
0x18001c4d3  test    eax, eax
0x18001c4d5  js      loc_18001C766
0x18001c4db  mov     [r14], rsi
0x18001c4de  mov     eax, [rdi]
0x18001c4e0  cmp     eax, 20h ; ' '
0x18001c4e3  jz      short loc_18001C52E
0x18001c4e5  mov     ebx, 80070057h
0x18001c4ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c4f1  cmp     rcx, r13
0x18001c4f4  jz      loc_18001C793
0x18001c4fa  test    byte ptr [rcx+1Ch], 40h
0x18001c4fe  jz      loc_18001C76D
0x18001c504  cmp     byte ptr [rcx+19h], 2
0x18001c508  jb      loc_18001C76D
0x18001c50e  lea     edx, [rsi+0Bh]
0x18001c511  mov     [rsp+78h+var_58], eax
0x18001c515  lea     r9d, [rsi+20h]
0x18001c519  mov     rcx, [rcx+10h]
0x18001c51d  lea     r8, WPP_ef16463b4e5c3f467a4309089a5279ae_Traceguids
0x18001c524  call    WPP_SF_DDd
0x18001c529  jmp     loc_18001C766
0x18001c52e  mov     eax, [rdi+10h]
0x18001c531  test    eax, eax
0x18001c533  jz      short loc_18001C57F
0x18001c535  mov     ebx, 80070057h
0x18001c53a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c541  cmp     rcx, r13
0x18001c544  jz      loc_18001C793
0x18001c54a  test    byte ptr [rcx+1Ch], 40h
0x18001c54e  jz      loc_18001C76D
0x18001c554  cmp     byte ptr [rcx+19h], 2
0x18001c558  jb      loc_18001C76D
0x18001c55e  mov     rcx, [rcx+10h]
0x18001c562  lea     r8, WPP_ef16463b4e5c3f467a4309089a5279ae_Traceguids
0x18001c569  mov     edx, 0Ch
0x18001c56e  mov     [rsp+78h+var_58], esi
0x18001c572  mov     r9d, eax
0x18001c575  call    WPP_SF_DDd
0x18001c57a  jmp     loc_18001C766
0x18001c57f  mov     rax, [rdi+18h]
0x18001c583  test    rax, rax
0x18001c586  jnz     short loc_18001C5CD
0x18001c588  mov     r9d, 80070057h
0x18001c58e  mov     ebx, r9d
0x18001c591  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c598  cmp     rcx, r13
0x18001c59b  jz      loc_18001C793
0x18001c5a1  test    byte ptr [rcx+1Ch], 40h
0x18001c5a5  jz      loc_18001C76D
0x18001c5ab  cmp     byte ptr [rcx+19h], 2
0x18001c5af  jb      loc_18001C76D
0x18001c5b5  lea     edx, [rax+0Dh]
0x18001c5b8  mov     rcx, [rcx+10h]
0x18001c5bc  lea     r8, WPP_ef16463b4e5c3f467a4309089a5279ae_Traceguids
0x18001c5c3  call    WPP_SF_d
0x18001c5c8  jmp     loc_18001C766
0x18001c5cd  mov     r8d, [rax]
0x18001c5d0  cmp     r8d, 18h
0x18001c5d4  jz      short loc_18001C612
0x18001c5d6  mov     ebx, 80070057h
0x18001c5db  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c5e2  cmp     rcx, r13
0x18001c5e5  jz      loc_18001C793
0x18001c5eb  test    byte ptr [rcx+1Ch], 40h
0x18001c5ef  jz      loc_18001C76D
0x18001c5f5  cmp     byte ptr [rcx+19h], 2
0x18001c5f9  jb      loc_18001C76D
0x18001c5ff  mov     edx, 0Eh
0x18001c604  mov     [rsp+78h+var_58], r8d
0x18001c609  lea     r9d, [rdx+0Ah]
0x18001c60d  jmp     loc_18001C519
0x18001c612  cmp     [rax+10h], rsi
0x18001c616  jz      loc_18001C71E
0x18001c61c  cmp     [rax+8], rsi
0x18001c620  jz      loc_18001C71E
0x18001c626  cmp     dword ptr [rdi+4], 0FFFFFFFFh
0x18001c62a  jz      short loc_18001C663
0x18001c62c  mov     r9d, 80070057h
0x18001c632  mov     ebx, r9d
0x18001c635  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c63c  cmp     rcx, r13
0x18001c63f  jz      loc_18001C793
0x18001c645  test    byte ptr [rcx+1Ch], 40h
0x18001c649  jz      loc_18001C76D
0x18001c64f  cmp     byte ptr [rcx+19h], 2
0x18001c653  jb      loc_18001C76D
0x18001c659  mov     edx, 10h
0x18001c65e  jmp     loc_18001C5B8
0x18001c663  cmp     [rdi+14h], esi
0x18001c666  jnz     short loc_18001C69F
0x18001c668  mov     r9d, 80070057h
0x18001c66e  mov     ebx, r9d
0x18001c671  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c678  cmp     rcx, r13
0x18001c67b  jz      loc_18001C793
0x18001c681  test    byte ptr [rcx+1Ch], 40h
0x18001c685  jz      loc_18001C76D
0x18001c68b  cmp     byte ptr [rcx+19h], 2
0x18001c68f  jb      loc_18001C76D
0x18001c695  mov     edx, 11h
0x18001c69a  jmp     loc_18001C5B8
0x18001c69f  mov     eax, 0FFFFh
0x18001c6a4  cmp     [rdi+14h], eax
0x18001c6a7  jbe     short loc_18001C6F5
0x18001c6a9  mov     r9d, 80070057h
0x18001c6af  mov     ebx, r9d
0x18001c6b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c6b9  cmp     rcx, r13
0x18001c6bc  jz      loc_18001C793
0x18001c6c2  test    byte ptr [rcx+1Ch], 40h
0x18001c6c6  jz      loc_18001C76D
0x18001c6cc  cmp     byte ptr [rcx+19h], 2
0x18001c6d0  jb      loc_18001C76D
0x18001c6d6  mov     rcx, [rcx+10h]
0x18001c6da  lea     r8, WPP_ef16463b4e5c3f467a4309089a5279ae_Traceguids
0x18001c6e1  mov     [rsp+78h+var_58], r9d
0x18001c6e6  mov     edx, 12h
0x18001c6eb  mov     r9d, eax
0x18001c6ee  call    WPP_SF_dd
0x18001c6f3  jmp     short loc_18001C766
0x18001c6f5  lea     rdx, [rsp+78h+var_48]; struct Apx::ApfMute **
0x18001c6fa  mov     rcx, rdi; struct _APX_MUTE_CONFIG *
0x18001c6fd  call    ?_CreateAndInitialize@ApfMute@Apx@@SAJPEAU_APX_MUTE_CONFIG@@PEAPEAV12@@Z; Apx::ApfMute::_CreateAndInitialize(_APX_MUTE_CONFIG *,Apx::ApfMute * *)
0x18001c702  mov     ebx, eax
0x18001c704  test    eax, eax
0x18001c706  js      short loc_18001C717
0x18001c708  mov     rax, [rsp+78h+var_48]
0x18001c70d  xor     ebx, ebx
0x18001c70f  not     rax
0x18001c712  mov     [r14], rax
0x18001c715  jmp     short loc_18001C766
0x18001c717  mov     rsi, [rsp+78h+var_48]
0x18001c71c  jmp     short loc_18001C754
0x18001c71e  mov     r9d, 80070057h
0x18001c724  mov     ebx, r9d
0x18001c727  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c72e  cmp     rcx, r13
0x18001c731  jz      short loc_18001C793
0x18001c733  test    byte ptr [rcx+1Ch], 40h
0x18001c737  jz      short loc_18001C76D
0x18001c739  cmp     byte ptr [rcx+19h], 2
0x18001c73d  jb      short loc_18001C76D
0x18001c73f  mov     rcx, [rcx+10h]
0x18001c743  lea     r8, WPP_ef16463b4e5c3f467a4309089a5279ae_Traceguids
0x18001c74a  mov     edx, 0Fh
0x18001c74f  call    WPP_SF_d
0x18001c754  test    rsi, rsi
0x18001c757  jz      short loc_18001C766
0x18001c759  not     rsi
0x18001c75c  xor     ecx, ecx; this
0x18001c75e  mov     rdx, rsi; Apx::ApfVerify *
0x18001c761  call    imp_ApxObjectDelete
0x18001c766  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c76d  cmp     rcx, r13
0x18001c770  jz      short loc_18001C793
0x18001c772  test    byte ptr [rcx+1Ch], 1
0x18001c776  jz      short loc_18001C793
0x18001c778  cmp     byte ptr [rcx+19h], 5
0x18001c77c  jb      short loc_18001C793
0x18001c77e  mov     rcx, [rcx+10h]
0x18001c782  lea     r8, WPP_ef16463b4e5c3f467a4309089a5279ae_Traceguids
0x18001c789  mov     edx, 13h
0x18001c78e  call    WPP_SF_
0x18001c793  mov     eax, ebx
0x18001c795  add     rsp, 40h
0x18001c799  pop     r15
0x18001c79b  pop     r14
0x18001c79d  pop     r13
0x18001c79f  pop     rdi
0x18001c7a0  pop     rsi
0x18001c7a1  pop     rbp
0x18001c7a2  pop     rbx
0x18001c7a3  retn
```
