# LanguageManager::_UninstallLanguageFeatures(std::shared_ptr<UninstallationRequest> const &)

- ea: `0x180033c54`
- end: `0x180034021`
- name: `?_UninstallLanguageFeatures@LanguageManager@@AEAAJAEBV?$shared_ptr@VUninstallationRequest@@@std@@@Z`
- size: `973`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180031810`

## callees

- `0x180003a00`
- `0x180009084`
- `0x180014ed0`
- `0x18001e2a4`
- `0x18001e3c0`
- `0x1800262f0`
- `0x180027818`
- `0x18002c068`
- `0x180033c54`
- `0x18006a010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180033ee9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180033f7a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180033fba`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180033ee9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180033f7a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180033fba`

## string_xrefs

- `0x180033e0e`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagemanager.cpp`
- `0x180033ed1`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagemanager.cpp`
- `0x180033f62`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall LanguageManager::_UninstallLanguageFeatures(__int64 a1, _QWORD ***a2)
{
  __int64 v4; // rdi
  __int64 v5; // r14
  int v6; // eax
  __int64 v7; // rbx
  __int128 *v8; // rcx
  __int64 v9; // rbx
  int v10; // eax
  unsigned int v11; // ebx
  _QWORD *v13; // rdx
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // eax
  int v17; // [rsp+20h] [rbp-B8h] BYREF
  __int128 v18; // [rsp+28h] [rbp-B0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-A0h]
  __int128 v20; // [rsp+40h] [rbp-98h] BYREF
  __int64 v21; // [rsp+50h] [rbp-88h]
  __int128 v22; // [rsp+58h] [rbp-80h] BYREF
  __int64 v23; // [rsp+68h] [rbp-70h]
  char *v24[4]; // [rsp+70h] [rbp-68h] BYREF
  int v25; // [rsp+90h] [rbp-48h]
  _QWORD v26[3]; // [rsp+98h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  std::vector<LanguageFeature>::vector<LanguageFeature>(v26, *a2 + 2);
  v22 = 0;
  v23 = 0;
  v20 = 0;
  v21 = 0;
  v18 = 0;
  v19 = 0;
  v4 = v26[0];
  v5 = v26[1];
  while ( v4 != v5 )
  {
    std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(
      (__int64)v24,
      v4);
    v6 = *(_DWORD *)(v4 + 32);
    v25 = v6;
    if ( v6 == 512 )
    {
      v7 = *((_QWORD *)&v20 + 1);
      if ( *((_QWORD *)&v20 + 1) != v21 )
      {
        std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(
          *((__int64 *)&v20 + 1),
          (__int64)v24);
        *(_DWORD *)(v7 + 32) = v25;
        *((_QWORD *)&v20 + 1) += 40LL;
        goto LABEL_15;
      }
      v8 = &v20;
LABEL_11:
      std::vector<LanguageFeature>::_Emplace_reallocate<LanguageFeature const &>(v8, v7, v24);
      goto LABEL_15;
    }
    if ( v6 == 1024 )
    {
      v7 = *((_QWORD *)&v18 + 1);
      if ( *((_QWORD *)&v18 + 1) != v19 )
      {
        std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(
          *((__int64 *)&v18 + 1),
          (__int64)v24);
        *(_DWORD *)(v7 + 32) = v25;
        *((_QWORD *)&v18 + 1) += 40LL;
        goto LABEL_15;
      }
      v8 = &v18;
      goto LABEL_11;
    }
    v9 = *((_QWORD *)&v22 + 1);
    if ( *((_QWORD *)&v22 + 1) == v23 )
    {
      std::vector<LanguageFeature>::_Emplace_reallocate<LanguageFeature const &>(&v22, *((_QWORD *)&v22 + 1), v24);
    }
    else
    {
      std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(
        *((__int64 *)&v22 + 1),
        (__int64)v24);
      *(_DWORD *)(v9 + 32) = v25;
      *((_QWORD *)&v22 + 1) += 40LL;
    }
LABEL_15:
    std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v24);
    v4 += 40;
  }
  if ( 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)&v22 + 1) - v22) >> 3) )
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)(a1 + 40) + 48LL))(*(_QWORD *)(a1 + 40), &v22);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x44B,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagemanager.cpp",
        (const char *)(unsigned int)v10,
        v17);
      std::vector<LanguageFeature>::_Tidy(&v18);
      std::vector<LanguageFeature>::_Tidy(&v20);
      std::vector<LanguageFeature>::_Tidy(&v22);
      std::vector<LanguageFeature>::_Tidy(v26);
      return v11;
    }
  }
  if ( *((_QWORD *)&v20 + 1) == (_QWORD)v20 && !(0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)&v18 + 1) - v18) >> 3)) )
  {
LABEL_35:
    std::vector<LanguageFeature>::_Tidy(&v18);
    std::vector<LanguageFeature>::_Tidy(&v20);
    std::vector<LanguageFeature>::_Tidy(&v22);
    std::vector<LanguageFeature>::_Tidy(v26);
    return 0;
  }
  v13 = **a2;
  if ( v13 )
    v13 = (_QWORD *)*v13;
  raii::ImpersonateLoggedOnUser(&v17, v13);
  if ( 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)&v20 + 1) - v20) >> 3) )
  {
    v14 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)(a1 + 48) + 32LL))(*(_QWORD *)(a1 + 48), &v20);
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x452,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagemanager.cpp",
        (const char *)(unsigned int)v14,
        v17);
      if ( (_BYTE)v17 )
        RevertToSelf();
      goto LABEL_27;
    }
  }
  if ( !(0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)&v18 + 1) - v18) >> 3))
    || (v16 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)(a1 + 48) + 32LL))(
                *(_QWORD *)(a1 + 48),
                &v18),
        v15 = v16,
        v16 >= 0) )
  {
    if ( (_BYTE)v17 )
      RevertToSelf();
    goto LABEL_35;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x456,
    (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagemanager.cpp",
    (const char *)(unsigned int)v16,
    v17);
  if ( (_BYTE)v17 )
    RevertToSelf();
LABEL_27:
  std::vector<LanguageFeature>::_Tidy(&v18);
  std::vector<LanguageFeature>::_Tidy(&v20);
  std::vector<LanguageFeature>::_Tidy(&v22);
  std::vector<LanguageFeature>::_Tidy(v26);
  return v15;
}

```

## disassembly

```asm
0x180033c54  mov     r11, rsp
0x180033c57  mov     [r11+18h], rbx
0x180033c5b  mov     [r11+20h], rsi
0x180033c5f  push    rdi
0x180033c60  push    r14
0x180033c62  push    r15
0x180033c64  sub     rsp, 0C0h
0x180033c6b  mov     rax, cs:__security_cookie
0x180033c72  xor     rax, rsp
0x180033c75  mov     [rsp+0D8h+var_28], rax
0x180033c7d  mov     rsi, rdx
0x180033c80  mov     r15, rcx
0x180033c83  mov     rdx, [rdx]
0x180033c86  add     rdx, 10h
0x180033c8a  lea     rcx, [r11-40h]
0x180033c8e  call    ??0?$vector@ULanguageFeature@@V?$allocator@ULanguageFeature@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<LanguageFeature>::vector<LanguageFeature>(std::vector<LanguageFeature> const &)
0x180033c93  nop
0x180033c94  xorps   xmm0, xmm0
0x180033c97  movdqu  [rsp+0D8h+var_80], xmm0
0x180033c9d  mov     [rsp+0D8h+var_70], 0
0x180033ca6  movdqu  [rsp+0D8h+var_98], xmm0
0x180033cac  mov     [rsp+0D8h+var_88], 0
0x180033cb5  movdqu  [rsp+0D8h+var_B0], xmm0
0x180033cbb  mov     [rsp+0D8h+var_A0], 0
0x180033cc4  mov     rdi, [rsp+0D8h+var_40]
0x180033ccc  mov     r14, [rsp+0D8h+var_38]
0x180033cd4  cmp     rdi, r14
0x180033cd7  jz      loc_180033DC7
0x180033cdd  mov     rdx, rdi
0x180033ce0  lea     rcx, [rsp+0D8h+var_68]
0x180033ce5  call    ??0?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@AEBV01@@Z; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>> const &)
0x180033cea  mov     eax, [rdi+20h]
0x180033ced  mov     [rsp+0D8h+var_48], eax
0x180033cf4  cmp     eax, 200h
0x180033cf9  jnz     short loc_180033D30
0x180033cfb  mov     rbx, qword ptr [rsp+0D8h+var_98+8]
0x180033d00  cmp     rbx, [rsp+0D8h+var_88]
0x180033d05  jz      short loc_180033D29
0x180033d07  lea     rdx, [rsp+0D8h+var_68]
0x180033d0c  mov     rcx, rbx
0x180033d0f  call    ??0?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@AEBV01@@Z; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>> const &)
0x180033d14  mov     eax, [rsp+0D8h+var_48]
0x180033d1b  mov     [rbx+20h], eax
0x180033d1e  add     qword ptr [rsp+0D8h+var_98+8], 28h ; '('
0x180033d24  jmp     loc_180033DB4
0x180033d29  lea     rcx, [rsp+0D8h+var_98]
0x180033d2e  jmp     short loc_180033D67
0x180033d30  cmp     eax, 400h
0x180033d35  jnz     short loc_180033D76
0x180033d37  mov     rbx, qword ptr [rsp+0D8h+var_B0+8]
0x180033d3c  cmp     rbx, [rsp+0D8h+var_A0]
0x180033d41  jz      short loc_180033D62
0x180033d43  lea     rdx, [rsp+0D8h+var_68]
0x180033d48  mov     rcx, rbx
0x180033d4b  call    ??0?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@AEBV01@@Z; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>> const &)
0x180033d50  mov     eax, [rsp+0D8h+var_48]
0x180033d57  mov     [rbx+20h], eax
0x180033d5a  add     qword ptr [rsp+0D8h+var_B0+8], 28h ; '('
0x180033d60  jmp     short loc_180033DB4
0x180033d62  lea     rcx, [rsp+0D8h+var_B0]
0x180033d67  mov     rdx, rbx
0x180033d6a  lea     r8, [rsp+0D8h+var_68]
0x180033d6f  call    ??$_Emplace_reallocate@AEBULanguageFeature@@@?$vector@ULanguageFeature@@V?$allocator@ULanguageFeature@@@std@@@std@@AEAAPEAULanguageFeature@@QEAU2@AEBU2@@Z; std::vector<LanguageFeature>::_Emplace_reallocate<LanguageFeature const &>(LanguageFeature * const,LanguageFeature const &)
0x180033d74  jmp     short loc_180033DB4
0x180033d76  mov     rbx, qword ptr [rsp+0D8h+var_80+8]
0x180033d7b  cmp     rbx, [rsp+0D8h+var_70]
0x180033d80  jz      short loc_180033DA1
0x180033d82  lea     rdx, [rsp+0D8h+var_68]
0x180033d87  mov     rcx, rbx
0x180033d8a  call    ??0?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@AEBV01@@Z; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>> const &)
0x180033d8f  mov     eax, [rsp+0D8h+var_48]
0x180033d96  mov     [rbx+20h], eax
0x180033d99  add     qword ptr [rsp+0D8h+var_80+8], 28h ; '('
0x180033d9f  jmp     short loc_180033DB4
0x180033da1  lea     r8, [rsp+0D8h+var_68]
0x180033da6  mov     rdx, rbx
0x180033da9  lea     rcx, [rsp+0D8h+var_80]
0x180033dae  call    ??$_Emplace_reallocate@AEBULanguageFeature@@@?$vector@ULanguageFeature@@V?$allocator@ULanguageFeature@@@std@@@std@@AEAAPEAULanguageFeature@@QEAU2@AEBU2@@Z; std::vector<LanguageFeature>::_Emplace_reallocate<LanguageFeature const &>(LanguageFeature * const,LanguageFeature const &)
0x180033db3  nop
0x180033db4  lea     rcx, [rsp+0D8h+var_68]; void *
0x180033db9  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180033dbe  add     rdi, 28h ; '('
0x180033dc2  jmp     loc_180033CD4
0x180033dc7  mov     rax, qword ptr [rsp+0D8h+var_80+8]
0x180033dcc  sub     rax, qword ptr [rsp+0D8h+var_80]
0x180033dd1  sar     rax, 3
0x180033dd5  mov     rdi, 0CCCCCCCCCCCCCCCDh
0x180033ddf  imul    rax, rdi
0x180033de3  test    rax, rax
0x180033de6  jz      short loc_180033E55
0x180033de8  mov     rcx, [r15+28h]
0x180033dec  mov     rax, [rcx]
0x180033def  lea     rdx, [rsp+0D8h+var_80]
0x180033df4  mov     rax, [rax+30h]
0x180033df8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033dfd  mov     ebx, eax
0x180033dff  test    eax, eax
0x180033e01  jns     short loc_180033E55
0x180033e03  mov     rcx, [rsp+0D8h]; this
0x180033e0b  mov     r9d, eax; char *
0x180033e0e  lea     r8, aOnecoreBaseLan_4; "onecore\\base\\languageoverlay\\service"...
0x180033e15  mov     edx, 44Bh; void *
0x180033e1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033e1f  nop
0x180033e20  lea     rcx, [rsp+0D8h+var_B0]
0x180033e25  call    ?_Tidy@?$vector@ULanguageFeature@@V?$allocator@ULanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<LanguageFeature>::_Tidy(void)
0x180033e2a  nop
0x180033e2b  lea     rcx, [rsp+0D8h+var_98]
0x180033e30  call    ?_Tidy@?$vector@ULanguageFeature@@V?$allocator@ULanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<LanguageFeature>::_Tidy(void)
0x180033e35  nop
0x180033e36  lea     rcx, [rsp+0D8h+var_80]
0x180033e3b  call    ?_Tidy@?$vector@ULanguageFeature@@V?$allocator@ULanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<LanguageFeature>::_Tidy(void)
0x180033e40  nop
0x180033e41  lea     rcx, [rsp+0D8h+var_40]
0x180033e49  call    ?_Tidy@?$vector@ULanguageFeature@@V?$allocator@ULanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<LanguageFeature>::_Tidy(void)
0x180033e4e  mov     eax, ebx
0x180033e50  jmp     loc_180033FF7
0x180033e55  mov     rax, qword ptr [rsp+0D8h+var_98+8]
0x180033e5a  cmp     rax, qword ptr [rsp+0D8h+var_98]
0x180033e5f  jnz     short loc_180033E7C
0x180033e61  mov     rax, qword ptr [rsp+0D8h+var_B0+8]
0x180033e66  sub     rax, qword ptr [rsp+0D8h+var_B0]
0x180033e6b  sar     rax, 3
0x180033e6f  imul    rax, rdi
0x180033e73  test    rax, rax
0x180033e76  jz      loc_180033FC1
0x180033e7c  mov     rax, [rsi]
0x180033e7f  mov     rdx, [rax]
0x180033e82  test    rdx, rdx
0x180033e85  jz      short loc_180033E8A
0x180033e87  mov     rdx, [rdx]
0x180033e8a  lea     rcx, [rsp+0D8h+var_B8]
0x180033e8f  call    ?ImpersonateLoggedOnUser@raii@@YA?AV?$unique_call@P6AHXZ$1?RevertToSelf@@YAHXZ$00@wil@@PEAX@Z; raii::ImpersonateLoggedOnUser(void *)
0x180033e94  mov     rax, qword ptr [rsp+0D8h+var_98+8]
0x180033e99  sub     rax, qword ptr [rsp+0D8h+var_98]
0x180033e9e  sar     rax, 3
0x180033ea2  imul    rax, rdi
0x180033ea6  test    rax, rax
0x180033ea9  jz      short loc_180033F25
0x180033eab  mov     rcx, [r15+30h]
0x180033eaf  mov     rax, [rcx]
0x180033eb2  lea     rdx, [rsp+0D8h+var_98]
0x180033eb7  mov     rax, [rax+20h]
0x180033ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033ec0  mov     ebx, eax
0x180033ec2  test    eax, eax
0x180033ec4  jns     short loc_180033F25
0x180033ec6  mov     rcx, [rsp+0D8h]; this
0x180033ece  mov     r9d, eax; char *
0x180033ed1  lea     r8, aOnecoreBaseLan_4; "onecore\\base\\languageoverlay\\service"...
0x180033ed8  mov     edx, 452h; void *
0x180033edd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033ee2  cmp     byte ptr [rsp+0D8h+var_B8], 0
0x180033ee7  jz      short loc_180033EF0
0x180033ee9  call    cs:__imp_RevertToSelf
0x180033eef  nop
0x180033ef0  lea     rcx, [rsp+0D8h+var_B0]
0x180033ef5  call    ?_Tidy@?$vector@ULanguageFeature@@V?$allocator@ULanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<LanguageFeature>::_Tidy(void)
0x180033efa  nop
0x180033efb  lea     rcx, [rsp+0D8h+var_98]
0x180033f00  call    ?_Tidy@?$vector@ULanguageFeature@@V?$allocator@ULanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<LanguageFeature>::_Tidy(void)
0x180033f05  nop
0x180033f06  lea     rcx, [rsp+0D8h+var_80]
0x180033f0b  call    ?_Tidy@?$vector@ULanguageFeature@@V?$allocator@ULanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<LanguageFeature>::_Tidy(void)
0x180033f10  nop
0x180033f11  lea     rcx, [rsp+0D8h+var_40]
0x180033f19  call    ?_Tidy@?$vector@ULanguageFeature@@V?$allocator@ULanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<LanguageFeature>::_Tidy(void)
0x180033f1e  mov     eax, ebx
0x180033f20  jmp     loc_180033FF7
0x180033f25  mov     rax, qword ptr [rsp+0D8h+var_B0+8]
0x180033f2a  sub     rax, qword ptr [rsp+0D8h+var_B0]
0x180033f2f  sar     rax, 3
0x180033f33  imul    rax, rdi
0x180033f37  test    rax, rax
0x180033f3a  jz      short loc_180033FB3
0x180033f3c  mov     rcx, [r15+30h]
0x180033f40  mov     rax, [rcx]
0x180033f43  lea     rdx, [rsp+0D8h+var_B0]
0x180033f48  mov     rax, [rax+20h]
0x180033f4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f51  mov     ebx, eax
0x180033f53  test    eax, eax
0x180033f55  jns     short loc_180033FB3
0x180033f57  mov     rcx, [rsp+0D8h]; this
0x180033f5f  mov     r9d, eax; char *
0x180033f62  lea     r8, aOnecoreBaseLan_4; "onecore\\base\\languageoverlay\\service"...
0x180033f69  mov     edx, 456h; void *
0x180033f6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033f73  cmp     byte ptr [rsp+0D8h+var_B8], 0
0x180033f78  jz      short loc_180033F81
0x180033f7a  call    cs:__imp_RevertToSelf
0x180033f80  nop
0x180033f81  lea     rcx, [rsp+0D8h+var_B0]
0x180033f86  call    ?_Tidy@?$vector@ULanguageFeature@@V?$allocator@ULanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<LanguageFeature>::_Tidy(void)
0x180033f8b  nop
0x180033f8c  lea     rcx, [rsp+0D8h+var_98]
0x180033f91  call    ?_Tidy@?$vector@ULanguageFeature@@V?$allocator@ULanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<LanguageFeature>::_Tidy(void)
0x180033f96  nop
0x180033f97  lea     rcx, [rsp+0D8h+var_80]
0x180033f9c  call    ?_Tidy@?$vector@ULanguageFeature@@V?$allocator@ULanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<LanguageFeature>::_Tidy(void)
0x180033fa1  nop
0x180033fa2  lea     rcx, [rsp+0D8h+var_40]
0x180033faa  call    ?_Tidy@?$vector@ULanguageFeature@@V?$allocator@ULanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<LanguageFeature>::_Tidy(void)
0x180033faf  mov     eax, ebx
0x180033fb1  jmp     short loc_180033FF7
0x180033fb3  cmp     byte ptr [rsp+0D8h+var_B8], 0
0x180033fb8  jz      short loc_180033FC1
0x180033fba  call    cs:__imp_RevertToSelf
0x180033fc0  nop
0x180033fc1  lea     rcx, [rsp+0D8h+var_B0]
0x180033fc6  call    ?_Tidy@?$vector@ULanguageFeature@@V?$allocator@ULanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<LanguageFeature>::_Tidy(void)
0x180033fcb  nop
0x180033fcc  lea     rcx, [rsp+0D8h+var_98]
0x180033fd1  call    ?_Tidy@?$vector@ULanguageFeature@@V?$allocator@ULanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<LanguageFeature>::_Tidy(void)
0x180033fd6  nop
0x180033fd7  lea     rcx, [rsp+0D8h+var_80]
0x180033fdc  call    ?_Tidy@?$vector@ULanguageFeature@@V?$allocator@ULanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<LanguageFeature>::_Tidy(void)
0x180033fe1  nop
0x180033fe2  lea     rcx, [rsp+0D8h+var_40]
0x180033fea  call    ?_Tidy@?$vector@ULanguageFeature@@V?$allocator@ULanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<LanguageFeature>::_Tidy(void)
0x180033fef  xor     eax, eax
0x180033ff1  jmp     short loc_180033FF7
0x180033ff3  mov     eax, [rsp+0D8h+var_B4]
0x180033ff7  mov     rcx, [rsp+0D8h+var_28]
0x180033fff  xor     rcx, rsp; StackCookie
0x180034002  call    __security_check_cookie
0x180034007  lea     r11, [rsp+0D8h+var_18]
0x18003400f  mov     rbx, [r11+30h]
0x180034013  mov     rsi, [r11+38h]
0x180034017  mov     rsp, r11
0x18003401a  pop     r15
0x18003401c  pop     r14
0x18003401e  pop     rdi
0x18003401f  retn
```
