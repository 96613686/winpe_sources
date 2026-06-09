# KdcGetSidFromAltSecId(_UNICODE_STRING &,void * *)

- ea: `0x180053900`
- end: `0x180053aaf`
- name: `?KdcGetSidFromAltSecId@@YAJAEAU_UNICODE_STRING@@PEAPEAX@Z`
- size: `431`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800560a4`

## callees

- `0x18000e9e8`
- `0x1800101c4`
- `0x180053900`
- `0x18005654c`
- `0x180056670`
- `0x180077d78`
- `0x18007d950`
- `0x18007dc20`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180053a50`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180053a50`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall KdcGetSidFromAltSecId(struct _UNICODE_STRING *a1, void **a2)
{
  _WORD *v3; // rsi
  _WORD *v4; // rbx
  PWSTR Buffer; // rdx
  __int64 v6; // rax
  unsigned int v7; // ebx
  __int128 v9; // [rsp+20h] [rbp-48h] BYREF
  __int128 *v10; // [rsp+30h] [rbp-38h]
  char v11; // [rsp+38h] [rbp-30h]
  _WORD *v12; // [rsp+40h] [rbp-28h] BYREF
  _WORD *v13; // [rsp+48h] [rbp-20h]
  _WORD v14[12]; // [rsp+50h] [rbp-18h] BYREF

  v3 = v14;
  v12 = v14;
  v4 = v14;
  v13 = v14;
  v14[0] = 0;
  Buffer = a1->Buffer;
  if ( Buffer && (a1->Length & 1) == 0 )
  {
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
      &v12,
      Buffer,
      (unsigned __int64)a1->Length >> 1);
    v4 = v13;
    v3 = v12;
  }
  v9 = 0;
  v10 = &v9;
  v11 = 1;
  v6 = utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::find(&v12);
  if ( v6 == -1 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids);
    v7 = -1073741275;
  }
  else
  {
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
      &v12,
      &v3[v6 + 5],
      v4 - &v3[v6 + 5]);
    if ( (unsigned int)WStringToUnicodeString(&v12, &v9) )
    {
      if ( (int)KerbConvertStringToSid(&v9, a2) >= 0 )
      {
        if ( IsValidSid(*a2) )
        {
          v7 = 0;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids);
          }
          v7 = -1073741704;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids);
        }
        v7 = -1073741811;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids);
      v7 = -1073741801;
    }
  }
  KerbFreeString(&v9);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((void **)&v12);
  return v7;
}

```

## disassembly

```asm
0x180053900  push    rbp
0x180053902  push    rbx
0x180053903  push    rsi
0x180053904  push    rdi
0x180053905  mov     rbp, rsp
0x180053908  sub     rsp, 68h
0x18005390c  mov     rdi, rdx
0x18005390f  lea     rsi, [rbp+var_18]
0x180053913  mov     [rbp+var_28], rsi
0x180053917  lea     rbx, [rbp+var_18]
0x18005391b  mov     [rbp+var_20], rbx
0x18005391f  xor     eax, eax
0x180053921  mov     [rbp+var_18], ax
0x180053925  mov     rdx, [rcx+8]
0x180053929  test    rdx, rdx
0x18005392c  jz      short loc_18005394B
0x18005392e  test    byte ptr [rcx], 1
0x180053931  jnz     short loc_18005394B
0x180053933  movzx   r8d, word ptr [rcx]
0x180053937  shr     r8, 1
0x18005393a  lea     rcx, [rbp+var_28]
0x18005393e  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180053943  mov     rbx, [rbp+var_20]
0x180053947  mov     rsi, [rbp+var_28]
0x18005394b  xorps   xmm0, xmm0
0x18005394e  movups  [rbp+var_48], xmm0
0x180053952  lea     rax, [rbp+var_48]
0x180053956  mov     [rbp+var_38], rax
0x18005395a  mov     [rbp+var_30], 1
0x18005395e  lea     rcx, [rbp+var_28]
0x180053962  call    ?find@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEBA_KPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::find(ushort const *,unsigned __int64)
0x180053967  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005396b  jnz     short loc_1800539A5
0x18005396d  lea     rax, WPP_GLOBAL_Control
0x180053974  mov     rcx, cs:WPP_GLOBAL_Control
0x18005397b  cmp     rcx, rax
0x18005397e  jz      short loc_18005399B
0x180053980  test    byte ptr [rcx+1Ch], 1
0x180053984  jz      short loc_18005399B
0x180053986  mov     edx, 22h ; '"'
0x18005398b  lea     r8, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids
0x180053992  mov     rcx, [rcx+10h]
0x180053996  call    WPP_SF_
0x18005399b  mov     ebx, 0C0000225h
0x1800539a0  jmp     loc_180053A91
0x1800539a5  add     rax, 5
0x1800539a9  lea     rdx, [rsi+rax*2]
0x1800539ad  sub     rbx, rdx
0x1800539b0  sar     rbx, 1
0x1800539b3  mov     r8, rbx
0x1800539b6  lea     rcx, [rbp+var_28]
0x1800539ba  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800539bf  lea     rdx, [rbp+var_48]
0x1800539c3  lea     rcx, [rbp+var_28]
0x1800539c7  call    ?WStringToUnicodeString@@YAHAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAU_UNICODE_STRING@@@Z; WStringToUnicodeString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &,_UNICODE_STRING *)
0x1800539cc  test    eax, eax
0x1800539ce  jnz     short loc_180053A08
0x1800539d0  lea     rax, WPP_GLOBAL_Control
0x1800539d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800539de  cmp     rcx, rax
0x1800539e1  jz      short loc_1800539FE
0x1800539e3  test    byte ptr [rcx+1Ch], 1
0x1800539e7  jz      short loc_1800539FE
0x1800539e9  mov     edx, 23h ; '#'
0x1800539ee  lea     r8, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids
0x1800539f5  mov     rcx, [rcx+10h]
0x1800539f9  call    WPP_SF_
0x1800539fe  mov     ebx, 0C0000017h
0x180053a03  jmp     loc_180053A91
0x180053a08  mov     rdx, rdi
0x180053a0b  lea     rcx, [rbp+var_48]
0x180053a0f  call    KerbConvertStringToSid
0x180053a14  test    eax, eax
0x180053a16  jns     short loc_180053A4D
0x180053a18  lea     rax, WPP_GLOBAL_Control
0x180053a1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180053a26  cmp     rcx, rax
0x180053a29  jz      short loc_180053A46
0x180053a2b  test    byte ptr [rcx+1Ch], 1
0x180053a2f  jz      short loc_180053A46
0x180053a31  mov     edx, 24h ; '$'
0x180053a36  lea     r8, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids
0x180053a3d  mov     rcx, [rcx+10h]
0x180053a41  call    WPP_SF_
0x180053a46  mov     ebx, 0C000000Dh
0x180053a4b  jmp     short loc_180053A91
0x180053a4d  mov     rcx, [rdi]; pSid
0x180053a50  call    cs:__imp_IsValidSid
0x180053a56  test    eax, eax
0x180053a58  jnz     short loc_180053A8F
0x180053a5a  lea     rax, WPP_GLOBAL_Control
0x180053a61  mov     rcx, cs:WPP_GLOBAL_Control
0x180053a68  cmp     rcx, rax
0x180053a6b  jz      short loc_180053A88
0x180053a6d  test    byte ptr [rcx+1Ch], 1
0x180053a71  jz      short loc_180053A88
0x180053a73  mov     edx, 25h ; '%'
0x180053a78  lea     r8, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids
0x180053a7f  mov     rcx, [rcx+10h]
0x180053a83  call    WPP_SF_
0x180053a88  mov     ebx, 0C0000078h
0x180053a8d  jmp     short loc_180053A91
0x180053a8f  xor     ebx, ebx
0x180053a91  lea     rcx, [rbp+var_48]
0x180053a95  call    KerbFreeString
0x180053a9a  nop
0x180053a9b  lea     rcx, [rbp+var_28]
0x180053a9f  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180053aa4  mov     eax, ebx
0x180053aa6  add     rsp, 68h
0x180053aaa  pop     rdi
0x180053aab  pop     rsi
0x180053aac  pop     rbx
0x180053aad  pop     rbp
0x180053aae  retn
```
