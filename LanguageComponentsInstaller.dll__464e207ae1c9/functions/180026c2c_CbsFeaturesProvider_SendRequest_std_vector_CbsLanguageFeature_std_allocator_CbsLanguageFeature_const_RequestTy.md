# CbsFeaturesProvider::SendRequest(std::vector<CbsLanguageFeature,std::allocator<CbsLanguageFeature>> const &,RequestType,ICbsUIHandler *,ulong)

- ea: `0x180026c2c`
- end: `0x180026f35`
- name: `?SendRequest@CbsFeaturesProvider@@YAJAEBV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@W4RequestType@@PEAUICbsUIHandler@@K@Z`
- size: `777`
- prototype: `__int64 __fastcall(__int64 *, int, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180025d20`
- `0x180026020`

## callees

- `0x180003520`
- `0x180005d68`
- `0x180006380`
- `0x1800092a4`
- `0x180009c94`
- `0x18000e978`
- `0x180018574`
- `0x180021b6c`
- `0x180026c2c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180026d7c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180026d7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026ead`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026edb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026ead`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026edb`
- `ext-ms-win-ole32-bindctx-l1-1-0!CoGetObject` at `0x180026ded`
- `ext-ms-win-ole32-bindctx-l1-1-0!CoGetObject` at `0x180026ded`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetForegroundWindow` at `0x180026d4d`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetForegroundWindow` at `0x180026d4d`

## string_xrefs

- `0x180026e03`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\languagefeaturesprovider.cpp`
- `0x180026e92`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\languagefeaturesprovider.cpp`

## pseudocode

```c
__int64 __fastcall CbsFeaturesProvider::SendRequest(__int64 *a1, int a2, __int64 a3, unsigned int a4)
{
  __int64 v5; // rbx
  __int64 v6; // rdi
  int v7; // esi
  char v8; // r14
  __int64 v9; // rax
  __int64 v10; // rdx
  __int128 *p_Src; // rcx
  HWND ForegroundWindow; // rdi
  HRESULT Object; // ebx
  void *v14; // rcx
  int v15; // edx
  __int64 v16; // rax
  __int128 *v17; // r9
  int v18; // eax
  void *v19; // rcx
  void *v20; // rcx
  int v22; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+20h] [rbp-E0h]
  BIND_OPTS pBindOptions[3]; // [rsp+48h] [rbp-B8h] BYREF
  void *ppv; // [rsp+78h] [rbp-88h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-80h]
  __int128 Src; // [rsp+88h] [rbp-78h] BYREF
  __int64 v29; // [rsp+98h] [rbp-68h]
  unsigned __int64 v30; // [rsp+A0h] [rbp-60h]
  OLECHAR sz[56]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR pszName[304]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3C8h] [rbp+2C8h]

  v5 = a1[1];
  v6 = *a1;
  Src = 0;
  v29 = 0;
  v30 = 7;
  LOWORD(Src) = 0;
  v7 = 2;
  v8 = 1;
  while ( v6 != v5 )
  {
    v9 = CbsFeature::Identity(v6);
    std::wstring::wstring(pBindOptions, v9);
    v7 |= 4u;
    if ( *(_QWORD *)&pBindOptions[1].cbStruct )
    {
      if ( !v8 )
      {
        v10 = v29;
        if ( v30 == v29 )
        {
          std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(
            &Src,
            59);
        }
        else
        {
          ++v29;
          p_Src = &Src;
          if ( v30 > 7 )
            p_Src = (__int128 *)Src;
          *(_DWORD *)((char *)p_Src + 2 * v10) = 59;
        }
      }
      std::wstring::append(&Src);
      v8 = 0;
    }
    std::wstring::~wstring(pBindOptions);
    v6 += 192;
  }
  ppv = 0;
  ForegroundWindow = GetForegroundWindow();
  memset(pBindOptions, 0, sizeof(pBindOptions));
  ppv = 0;
  if ( !StringFromGUID2(&GUID_c6b167ea_db3e_4659_badc_d1ccc00efe9c, sz, 50) )
  {
    Object = -2147024882;
    goto LABEL_16;
  }
  Object = StringCchPrintfW(pszName, 0x12Cu, L"Elevation:Administrator!new:%s", sz);
  if ( Object < 0
    || (*(_OWORD *)&pBindOptions[0].grfFlags = 0,
        *(_OWORD *)&pBindOptions[1].grfMode = 0,
        pBindOptions[0].cbStruct = 48,
        *(_QWORD *)&pBindOptions[2].grfMode = ForegroundWindow,
        pBindOptions[1].grfFlags = 4,
        Object = CoGetObject(pszName, pBindOptions, &GUID_fe3ccccc_f5b9_4b61_86b8_697908ad690f, &ppv),
        Object < 0) )
  {
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagefeaturesprovider.cpp",
      (const char *)(unsigned int)Object,
      v22);
    v14 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v14 + 16LL))(v14);
    }
    goto LABEL_32;
  }
  v15 = 0;
  pv = 0;
  v16 = *(_QWORD *)ppv;
  pv = 0;
  v17 = &Src;
  if ( v30 > 7 )
    v17 = (__int128 *)Src;
  LOBYTE(v15) = a2 == 1;
  v23 = v15;
  v18 = (*(__int64 (__fastcall **)(void *, const wchar_t *, _QWORD, __int128 *))(v16 + 32))(
          ppv,
          L"LanguageFeaturesOnDemand",
          a4,
          v17);
  Object = v18;
  if ( v18 >= 0 )
  {
    if ( pv )
      CoTaskMemFree(pv);
    v20 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 16LL))(v20);
    }
    Object = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagefeaturesprovider.cpp",
      (const char *)(unsigned int)v18,
      v23);
    if ( pv )
      CoTaskMemFree(pv);
    v19 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v19 + 16LL))(v19);
    }
  }
LABEL_32:
  std::wstring::~wstring(&Src);
  return (unsigned int)Object;
}

```

## disassembly

```asm
0x180026c2c  mov     [rsp-8+arg_0], rbx
0x180026c31  push    rbp
0x180026c32  push    rsi
0x180026c33  push    rdi
0x180026c34  push    r12
0x180026c36  push    r13
0x180026c38  push    r14
0x180026c3a  push    r15
0x180026c3c  lea     rbp, [rsp-290h]
0x180026c44  sub     rsp, 390h
0x180026c4b  mov     rax, cs:__security_cookie
0x180026c52  xor     rax, rsp
0x180026c55  mov     [rbp+2C0h+var_40], rax
0x180026c5c  mov     [rsp+3C0h+var_37C], r9d
0x180026c61  mov     r12, r8
0x180026c64  mov     r15d, edx
0x180026c67  mov     [rsp+3C0h+var_380], 0
0x180026c6f  mov     rbx, [rcx+8]
0x180026c73  mov     rdi, [rcx]
0x180026c76  xorps   xmm0, xmm0
0x180026c79  movups  [rbp+2C0h+Src], xmm0
0x180026c7d  mov     [rbp+2C0h+var_328], 0
0x180026c85  mov     [rbp+2C0h+var_320], 7
0x180026c8d  xor     eax, eax
0x180026c8f  mov     word ptr [rbp+2C0h+Src], ax
0x180026c93  lea     esi, [rax+2]
0x180026c96  mov     [rsp+3C0h+var_380], esi
0x180026c9a  mov     r14b, 1
0x180026c9d  lea     r13d, [rax+3Bh]
0x180026ca1  mov     rax, rdi
0x180026ca4  cmp     rax, rbx
0x180026ca7  jz      loc_180026D46
0x180026cad  mov     rcx, rdi
0x180026cb0  call    ?Identity@CbsFeature@@QEBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CbsFeature::Identity(void)
0x180026cb5  mov     rdx, rax
0x180026cb8  lea     rcx, [rsp+3C0h+pBindOptions]
0x180026cbd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180026cc2  or      esi, 4
0x180026cc5  mov     [rsp+3C0h+var_380], esi
0x180026cc9  cmp     qword ptr [rsp+3C0h+var_368], 0
0x180026ccf  jz      short loc_180026D30
0x180026cd1  test    r14b, r14b
0x180026cd4  jnz     short loc_180026D1F
0x180026cd6  mov     rdx, [rbp+2C0h+var_328]
0x180026cda  mov     rax, [rbp+2C0h+var_320]
0x180026cde  sub     rax, rdx
0x180026ce1  mov     ecx, 1
0x180026ce6  cmp     rax, rcx
0x180026ce9  jb      short loc_180026D0A
0x180026ceb  lea     rax, [rdx+1]
0x180026cef  mov     [rbp+2C0h+var_328], rax
0x180026cf3  lea     rcx, [rbp+2C0h+Src]
0x180026cf7  cmp     [rbp+2C0h+var_320], 7
0x180026cfc  cmova   rcx, qword ptr [rbp+2C0h+Src]
0x180026d01  mov     dword ptr [rcx+rdx*2], 3Bh ; ';'
0x180026d08  jmp     short loc_180026D1F
0x180026d0a  mov     [rsp+3C0h+var_3A0], r13w; __int16
0x180026d10  mov     r9, rcx
0x180026d13  mov     rdx, rcx
0x180026d16  lea     rcx, [rbp+2C0h+Src]; Src
0x180026d1a  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x180026d1f  lea     rdx, [rsp+3C0h+pBindOptions]
0x180026d24  lea     rcx, [rbp+2C0h+Src]; Src
0x180026d28  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180026d2d  xor     r14b, r14b
0x180026d30  lea     rcx, [rsp+3C0h+pBindOptions]; void *
0x180026d35  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180026d3a  add     rdi, 0C0h
0x180026d41  jmp     loc_180026CA1
0x180026d46  xor     esi, esi
0x180026d48  mov     [rsp+3C0h+ppv], rsi
0x180026d4d  call    cs:__imp_GetForegroundWindow
0x180026d53  mov     rdi, rax
0x180026d56  xorps   xmm0, xmm0
0x180026d59  movups  xmmword ptr [rsp+3C0h+pBindOptions.cbStruct], xmm0
0x180026d5e  movups  [rsp+3C0h+var_368], xmm0
0x180026d63  movups  [rsp+3C0h+var_358], xmm0
0x180026d68  mov     [rsp+3C0h+ppv], rsi
0x180026d6d  lea     r8d, [rsi+32h]; cchMax
0x180026d71  lea     rdx, [rbp+2C0h+sz]; lpsz
0x180026d75  lea     rcx, _GUID_c6b167ea_db3e_4659_badc_d1ccc00efe9c; rguid
0x180026d7c  call    cs:__imp_StringFromGUID2
0x180026d82  test    eax, eax
0x180026d84  mov     r13d, [rsp+3C0h+var_37C]
0x180026d89  jnz     short loc_180026D92
0x180026d8b  mov     ebx, 8007000Eh
0x180026d90  jmp     short loc_180026DF9
0x180026d92  lea     r9, [rbp+2C0h+sz]
0x180026d96  lea     r8, aElevationAdmin; "Elevation:Administrator!new:%s"
0x180026d9d  mov     edx, 12Ch; unsigned __int64
0x180026da2  lea     rcx, [rbp+2C0h+pszName]; unsigned __int16 *
0x180026da6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026dab  mov     ebx, eax
0x180026dad  test    eax, eax
0x180026daf  js      short loc_180026DF9
0x180026db1  xorps   xmm0, xmm0
0x180026db4  movdqu  xmmword ptr [rsp+3C0h+pBindOptions.grfFlags], xmm0
0x180026dba  xorps   xmm1, xmm1
0x180026dbd  movdqu  [rsp+3C0h+var_368+8], xmm1
0x180026dc3  mov     [rsp+3C0h+pBindOptions.cbStruct], 30h ; '0'
0x180026dcb  mov     qword ptr [rsp+3C0h+var_358+8], rdi
0x180026dd0  mov     dword ptr [rsp+3C0h+var_368+4], 4
0x180026dd8  lea     r9, [rsp+3C0h+ppv]; ppv
0x180026ddd  lea     r8, _GUID_fe3ccccc_f5b9_4b61_86b8_697908ad690f; riid
0x180026de4  lea     rdx, [rsp+3C0h+pBindOptions]; pBindOptions
0x180026de9  lea     rcx, [rbp+2C0h+pszName]; pszName
0x180026ded  call    cs:__imp_CoGetObject
0x180026df3  mov     ebx, eax
0x180026df5  test    eax, eax
0x180026df7  jns     short loc_180026E36
0x180026df9  mov     rcx, [rbp+2C8h]; this
0x180026e00  mov     r9d, ebx; char *
0x180026e03  lea     r8, aOnecoreShellCp_3; "onecore\\shell\\cpls\\internationalsett"...
0x180026e0a  mov     edx, 1Dh; void *
0x180026e0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026e14  nop
0x180026e15  mov     rcx, [rsp+3C0h+ppv]
0x180026e1a  test    rcx, rcx
0x180026e1d  jz      short loc_180026E31
0x180026e1f  mov     [rsp+3C0h+ppv], rsi
0x180026e24  mov     rax, [rcx]
0x180026e27  mov     rax, [rax+10h]
0x180026e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e30  nop
0x180026e31  jmp     loc_180026F00
0x180026e36  mov     edx, esi
0x180026e38  cmp     r15d, 1
0x180026e3c  setz    dl
0x180026e3f  mov     [rbp+2C0h+pv], rsi
0x180026e43  mov     rcx, [rsp+3C0h+ppv]
0x180026e48  mov     rax, [rcx]
0x180026e4b  mov     [rbp+2C0h+pv], rsi
0x180026e4f  lea     r9, [rbp+2C0h+Src]
0x180026e53  cmp     [rbp+2C0h+var_320], 7
0x180026e58  cmova   r9, qword ptr [rbp+2C0h+Src]
0x180026e5d  lea     r8, [rbp+2C0h+pv]
0x180026e61  mov     [rsp+3C0h+var_390], r8
0x180026e66  mov     [rsp+3C0h+var_398], r12
0x180026e6b  mov     dword ptr [rsp+3C0h+var_3A0], edx; int
0x180026e6f  mov     r8d, r13d
0x180026e72  lea     rdx, aLanguagefeatur; "LanguageFeaturesOnDemand"
0x180026e79  mov     rax, [rax+20h]
0x180026e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e82  mov     ebx, eax
0x180026e84  test    eax, eax
0x180026e86  jns     short loc_180026ED2
0x180026e88  mov     rcx, [rbp+2C8h]; this
0x180026e8f  mov     r9d, eax; char *
0x180026e92  lea     r8, aOnecoreShellCp_3; "onecore\\shell\\cpls\\internationalsett"...
0x180026e99  mov     edx, 27h ; '''; void *
0x180026e9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026ea3  nop
0x180026ea4  mov     rcx, [rbp+2C0h+pv]; pv
0x180026ea8  test    rcx, rcx
0x180026eab  jz      short loc_180026EB4
0x180026ead  call    cs:__imp_CoTaskMemFree
0x180026eb3  nop
0x180026eb4  mov     rcx, [rsp+3C0h+ppv]
0x180026eb9  test    rcx, rcx
0x180026ebc  jz      short loc_180026ED0
0x180026ebe  mov     [rsp+3C0h+ppv], rsi
0x180026ec3  mov     rax, [rcx]
0x180026ec6  mov     rax, [rax+10h]
0x180026eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ecf  nop
0x180026ed0  jmp     short loc_180026F00
0x180026ed2  mov     rcx, [rbp+2C0h+pv]; pv
0x180026ed6  test    rcx, rcx
0x180026ed9  jz      short loc_180026EE2
0x180026edb  call    cs:__imp_CoTaskMemFree
0x180026ee1  nop
0x180026ee2  mov     rcx, [rsp+3C0h+ppv]
0x180026ee7  test    rcx, rcx
0x180026eea  jz      short loc_180026EFE
0x180026eec  mov     [rsp+3C0h+ppv], rsi
0x180026ef1  mov     rax, [rcx]
0x180026ef4  mov     rax, [rax+10h]
0x180026ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026efd  nop
0x180026efe  mov     ebx, esi
0x180026f00  lea     rcx, [rbp+2C0h+Src]; void *
0x180026f04  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180026f09  mov     eax, ebx
0x180026f0b  mov     rcx, [rbp+2C0h+var_40]
0x180026f12  xor     rcx, rsp; StackCookie
0x180026f15  call    __security_check_cookie
0x180026f1a  mov     rbx, [rsp+3C0h+arg_0]
0x180026f22  add     rsp, 390h
0x180026f29  pop     r15
0x180026f2b  pop     r14
0x180026f2d  pop     r13
0x180026f2f  pop     r12
0x180026f31  pop     rdi
0x180026f32  pop     rsi
0x180026f33  pop     rbp
0x180026f34  retn
```
