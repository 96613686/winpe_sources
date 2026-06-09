# LanguagePacksUninstaller::GetFeaturesToUninstall(std::vector<CbsLanguageFeature,std::allocator<CbsLanguageFeature>> &)

- ea: `0x180024198`
- end: `0x180024382`
- name: `?GetFeaturesToUninstall@LanguagePacksUninstaller@@QEAAXAEAV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@Z`
- size: `490`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180013e1c`
- `0x180014788`

## callees

- `0x180003520`
- `0x180005d68`
- `0x180006380`
- `0x18000a7fc`
- `0x18000cef4`
- `0x1800118f4`
- `0x1800214f4`
- `0x180021590`
- `0x180024198`
- `0x180024388`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002428b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002428b`
- `ext-ms-win-resources-languageoverlay-l1-1-4!GetUnusedLanguagesToCleanup` at `0x1800241e5`
- `ext-ms-win-resources-languageoverlay-l1-1-4!GetUnusedLanguagesToCleanup` at `0x1800241e5`

## string_xrefs

- `0x18002436f`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\languagepacksuninstaller.cpp`

## pseudocode

```c
void __fastcall LanguagePacksUninstaller::GetFeaturesToUninstall(__int64 a1, __int64 a2)
{
  __int64 *v4; // r15
  int UnusedLanguagesToCleanup; // eax
  const char *v6; // r9
  struct CbsLanguageFeature *v7; // r12
  struct CbsLanguageFeature *v8; // rax
  __int64 v9; // rsi
  __int64 v10; // rax
  char **v11; // rax
  char **v12; // r13
  char **v13; // rdx
  char **v14; // rcx
  int v15; // ebx
  int v16; // [rsp+20h] [rbp-148h]
  __int64 i; // [rsp+20h] [rbp-148h]
  struct CbsLanguageFeature *v18; // [rsp+28h] [rbp-140h]
  char v19[32]; // [rsp+38h] [rbp-130h] BYREF
  struct CbsLanguageFeature *v20; // [rsp+58h] [rbp-110h] BYREF
  struct CbsLanguageFeature *v21; // [rsp+60h] [rbp-108h]
  char *v22[4]; // [rsp+70h] [rbp-F8h] BYREF
  char *v23; // [rsp+90h] [rbp-D8h] BYREF
  char v24[24]; // [rsp+D8h] [rbp-90h] BYREF
  char v25[24]; // [rsp+F0h] [rbp-78h] BYREF
  char *v26[5]; // [rsp+108h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  if ( *(_DWORD *)a1 == 1 )
  {
    v4 = (__int64 *)(a1 + 208);
    UnusedLanguagesToCleanup = GetUnusedLanguagesToCleanup(
                                 lambda_211c643b6b024d0b479b7030a2e65962_::_lambda_invoker_cdecl_,
                                 a1 + 208);
    try
    {
      if ( UnusedLanguagesToCleanup < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x22,
          (int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagepacksuninstaller.cpp",
          (const char *)(unsigned int)UnusedLanguagesToCleanup,
          v16);
      if ( *v4 != v4[1] )
      {
        CbsLanguageSession::InstalledLanguageFeaturesOfType(a1 + 8, &v20);
        v7 = v20;
        v8 = v21;
        v18 = v21;
        while ( v7 != v8 )
        {
          CbsLanguageFeature::CbsLanguageFeature((CbsLanguageFeature *)v22, v7);
          v9 = *v4;
          v10 = *(_QWORD *)(a1 + 216);
          for ( i = v10; v9 != v10; v10 = i )
          {
            v11 = (char **)std::wstring::wstring((__int64)v19, v9);
            v12 = v11;
            v13 = v26;
            if ( v26[3] > (char *)7 )
              v13 = (char **)v26[0];
            v14 = (unsigned __int64)v11[3] <= 7 ? v11 : (char **)*v11;
            v15 = _o__wcsicmp(v14, v13);
            std::wstring::~wstring(v12);
            if ( !v15 )
              break;
            v9 += 32;
          }
          if ( v9 != *(_QWORD *)(a1 + 216) )
          {
            if ( *(_QWORD *)(a2 + 8) == *(_QWORD *)(a2 + 16) )
            {
              std::vector<CbsLanguageFeature>::_Emplace_reallocate<CbsLanguageFeature const &>(a2, *(_QWORD *)(a2 + 8));
            }
            else
            {
              CbsLanguageFeature::CbsLanguageFeature(
                *(CbsLanguageFeature **)(a2 + 8),
                (const struct CbsLanguageFeature *)v22);
              *(_QWORD *)(a2 + 8) += 192LL;
            }
          }
          std::wstring::~wstring(v26);
          std::vector<std::wstring>::_Tidy((__int64)v25);
          std::vector<std::wstring>::_Tidy((__int64)v24);
          std::wstring::~wstring(&v23);
          std::wstring::~wstring(v22);
          v7 = (struct CbsLanguageFeature *)((char *)v7 + 192);
          v8 = v18;
        }
        std::vector<CbsLanguageFeature>::_Tidy((__int64)&v20);
      }
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagepacksuninstaller.cpp",
        v6);
    }
  }
}

```

## disassembly

```asm
0x180024198  mov     [rsp+arg_10], rbx
0x18002419d  mov     [rsp+arg_18], rsi
0x1800241a2  push    rdi
0x1800241a3  push    r12
0x1800241a5  push    r13
0x1800241a7  push    r14
0x1800241a9  push    r15
0x1800241ab  sub     rsp, 140h
0x1800241b2  mov     rax, cs:__security_cookie
0x1800241b9  xor     rax, rsp
0x1800241bc  mov     [rsp+168h+var_38], rax
0x1800241c4  mov     r14, rdx
0x1800241c7  mov     rdi, rcx
0x1800241ca  cmp     dword ptr [rcx], 1
0x1800241cd  jz      short loc_1800241D4
0x1800241cf  jmp     loc_18002433F
0x1800241d4  lea     r15, [rcx+0D0h]
0x1800241db  mov     rdx, r15
0x1800241de  lea     rcx, _lambda_211c643b6b024d0b479b7030a2e65962____lambda_invoker_cdecl_
0x1800241e5  call    cs:__imp_GetUnusedLanguagesToCleanup
0x1800241eb  mov     rcx, [rsp+168h]; this
0x1800241f3  test    eax, eax
0x1800241f5  js      loc_18002436C
0x1800241fb  mov     rax, [r15+8]
0x1800241ff  cmp     [r15], rax
0x180024202  jnz     short loc_180024209
0x180024204  jmp     loc_18002433F
0x180024209  lea     rcx, [rdi+8]
0x18002420d  lea     rdx, [rsp+168h+var_110]
0x180024212  call    ?InstalledLanguageFeaturesOfType@CbsLanguageSession@@QEBA?AV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@W4PayloadType@@_N@Z; CbsLanguageSession::InstalledLanguageFeaturesOfType(PayloadType,bool)
0x180024217  nop
0x180024218  mov     r12, [rsp+168h+var_110]
0x18002421d  mov     rax, [rsp+168h+var_108]
0x180024222  mov     [rsp+168h+var_140], rax
0x180024227  cmp     r12, rax
0x18002422a  jz      loc_180024334
0x180024230  mov     rdx, r12; struct CbsLanguageFeature *
0x180024233  lea     rcx, [rsp+168h+var_F8]; this
0x180024238  call    ??0CbsLanguageFeature@@QEAA@AEBV0@@Z; CbsLanguageFeature::CbsLanguageFeature(CbsLanguageFeature const &)
0x18002423d  nop
0x18002423e  mov     rsi, [r15]
0x180024241  mov     rax, [rdi+0D8h]
0x180024248  mov     [rsp+168h+var_148], rax
0x18002424d  cmp     rsi, rax
0x180024250  jz      short loc_1800242AA
0x180024252  mov     rdx, rsi
0x180024255  lea     rcx, [rsp+168h+var_130]
0x18002425a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002425f  mov     r13, rax
0x180024262  lea     rdx, [rsp+168h+var_60]
0x18002426a  cmp     [rsp+168h+var_48], 7
0x180024273  cmova   rdx, [rsp+168h+var_60]
0x18002427c  cmp     qword ptr [rax+18h], 7
0x180024281  jbe     short loc_180024288
0x180024283  mov     rcx, [rax]
0x180024286  jmp     short loc_18002428B
0x180024288  mov     rcx, r13
0x18002428b  call    cs:__imp__o__wcsicmp
0x180024291  mov     ebx, eax
0x180024293  mov     rcx, r13; void *
0x180024296  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002429b  test    ebx, ebx
0x18002429d  jz      short loc_1800242AA
0x18002429f  add     rsi, 20h ; ' '
0x1800242a3  mov     rax, [rsp+168h+var_148]
0x1800242a8  jmp     short loc_18002424D
0x1800242aa  cmp     rsi, [rdi+0D8h]
0x1800242b1  jz      short loc_1800242E5
0x1800242b3  mov     rax, [r14+8]
0x1800242b7  cmp     rax, [r14+10h]
0x1800242bb  jz      short loc_1800242D4
0x1800242bd  lea     rdx, [rsp+168h+var_F8]; struct CbsLanguageFeature *
0x1800242c2  mov     rcx, rax; this
0x1800242c5  call    ??0CbsLanguageFeature@@QEAA@AEBV0@@Z; CbsLanguageFeature::CbsLanguageFeature(CbsLanguageFeature const &)
0x1800242ca  add     qword ptr [r14+8], 0C0h
0x1800242d2  jmp     short loc_1800242E5
0x1800242d4  lea     r8, [rsp+168h+var_F8]
0x1800242d9  mov     rdx, rax
0x1800242dc  mov     rcx, r14
0x1800242df  call    ??$_Emplace_reallocate@AEBVCbsLanguageFeature@@@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAPEAVCbsLanguageFeature@@QEAV2@AEBV2@@Z; std::vector<CbsLanguageFeature>::_Emplace_reallocate<CbsLanguageFeature const &>(CbsLanguageFeature * const,CbsLanguageFeature const &)
0x1800242e4  nop
0x1800242e5  lea     rcx, [rsp+168h+var_60]; void *
0x1800242ed  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800242f2  lea     rcx, [rsp+168h+var_78]
0x1800242fa  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800242ff  lea     rcx, [rsp+168h+var_90]
0x180024307  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18002430c  lea     rcx, [rsp+168h+var_D8]; void *
0x180024314  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180024319  lea     rcx, [rsp+168h+var_F8]; void *
0x18002431e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180024323  add     r12, 0C0h
0x18002432a  mov     rax, [rsp+168h+var_140]
0x18002432f  jmp     loc_180024227
0x180024334  lea     rcx, [rsp+168h+var_110]
0x180024339  call    ?_Tidy@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<CbsLanguageFeature>::_Tidy(void)
0x18002433e  nop
0x18002433f  mov     rcx, [rsp+168h+var_38]
0x180024347  xor     rcx, rsp; StackCookie
0x18002434a  call    __security_check_cookie
0x18002434f  lea     r11, [rsp+168h+var_28]
0x180024357  mov     rbx, [r11+40h]
0x18002435b  mov     rsi, [r11+48h]
0x18002435f  mov     rsp, r11
0x180024362  pop     r15
0x180024364  pop     r14
0x180024366  pop     r13
0x180024368  pop     r12
0x18002436a  pop     rdi
0x18002436b  retn
0x18002436c  mov     r9d, eax; char *
0x18002436f  lea     r8, aOnecoreShellCp_2; "onecore\\shell\\cpls\\internationalsett"...
0x180024376  mov     edx, 22h ; '"'; void *
0x18002437b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
