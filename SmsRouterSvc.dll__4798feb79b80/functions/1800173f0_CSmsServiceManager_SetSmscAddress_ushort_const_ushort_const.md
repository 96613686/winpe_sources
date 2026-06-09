# CSmsServiceManager::SetSmscAddress(ushort const *,ushort const *)

- ea: `0x1800173f0`
- end: `0x180017642`
- name: `?SetSmscAddress@CSmsServiceManager@@QEAAJPEBG0@Z`
- size: `594`
- prototype: `int(CSmsServiceManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000aac0`

## callees

- `0x180003a60`
- `0x1800069f0`
- `0x18000d388`
- `0x18000d8a8`
- `0x18000f018`
- `0x180014a64`
- `0x180014d20`
- `0x1800173f0`
- `0x180051420`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x18001748d`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x18001748d`
- `OLEAUT32!__imp_SysAllocString` at `0x18001745c`
- `OLEAUT32!__imp_SysAllocString` at `0x18001745c`
- `OLEAUT32!__imp_SysFreeString` at `0x180017571`
- `OLEAUT32!__imp_SysFreeString` at `0x180017571`
- `OLEAUT32!__imp_SysStringLen` at `0x180017475`
- `OLEAUT32!__imp_SysStringLen` at `0x180017482`
- `OLEAUT32!__imp_SysStringLen` at `0x180017475`
- `OLEAUT32!__imp_SysStringLen` at `0x180017482`

## string_xrefs

- `0x1800175c2`: `CSmsServiceManager::SetSmscAddress`
- `0x180017601`: `CSmsServiceManager::SetSmscAddress`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CSmsServiceManager::SetSmscAddress(
        CSmsServiceManager *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v5; // rbx
  char *v6; // r15
  OLECHAR *v7; // rax
  OLECHAR *v8; // rdi
  UINT v9; // eax
  unsigned __int64 v10; // r14
  unsigned __int64 v11; // r8
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // r13
  __int64 v15; // rsi
  char *v16; // rax
  __int64 v17; // rsi
  int v18; // eax
  unsigned int v19; // edi
  char *v21; // [rsp+30h] [rbp-49h]
  __int64 v23; // [rsp+60h] [rbp-19h] BYREF
  __int128 v24; // [rsp+70h] [rbp-9h] BYREF
  __int128 v25; // [rsp+80h] [rbp+7h]

  v5 = 0;
  if ( !a2 )
    goto LABEL_19;
  v6 = (char *)this + 40;
  (**((void (__fastcall ***)(char *))this + 5))((char *)this + 40);
  v7 = SysAllocString(a2);
  v8 = v7;
  if ( !v7 )
    ATL::AtlThrowImpl(-2147024882);
  if ( SysStringLen(v7) )
  {
    v9 = SysStringLen(v8);
    CharLowerBuffW(v8, v9);
  }
  v21 = (char *)this + 920;
  v24 = 0;
  v25 = 0;
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( v8[v11] );
  std::wstring::_Construct<1,unsigned short const *>((char **)&v24, v8, v11);
  v13 = stdext::hash_compare<std::wstring,std::less<std::wstring>>::operator()(v12, &v24);
  v14 = std::_Hash<stdext::_Hmap_traits<std::wstring,std::shared_ptr<CRegistration>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<CRegistration>>>,0>>::_Find_last<std::wstring>(
          (_QWORD *)this + 115,
          &v23,
          (const wchar_t *)&v24,
          v13)[1];
  if ( !v14 )
    v14 = *((_QWORD *)this + 116);
  v15 = *((_QWORD *)this + 116);
  std::wstring::~wstring((char **)&v24);
  if ( v14 != v15 )
  {
    v24 = 0;
    v25 = 0;
    do
      ++v10;
    while ( v8[v10] );
    std::wstring::_Construct<1,unsigned short const *>((char **)&v24, v8, v10);
    v16 = stdext::hash_map<std::wstring,ATL::CComPtr<ISmsDevice>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ATL::CComPtr<ISmsDevice>>>>::operator[](
            (__int64)v21,
            (__int64)&v24);
    v17 = *(_QWORD *)v16;
    if ( *(_QWORD *)v16 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v17 + 8LL))(*(_QWORD *)v16);
      v5 = v17;
    }
    std::wstring::~wstring((char **)&v24);
  }
  SysFreeString(v8);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
  if ( v5 )
  {
    v18 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v5 + 88LL))(v5, a3);
    v19 = v18;
    if ( v18 < 0 )
      LogSmsRouterError(
        "CSmsServiceManager::SetSmscAddress",
        0x22Bu,
        v18,
        "SetSmscAddress DeviceId: %S, Address: %S failed",
        a2,
        a3);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    return v19;
  }
  else
  {
LABEL_19:
    LogSmsRouterError(
      "CSmsServiceManager::SetSmscAddress",
      0x224u,
      -2147023728,
      "SmsDevice not found for DeviceId: %S",
      a2);
    return 2147943568LL;
  }
}

```

## disassembly

```asm
0x1800173f0  mov     [rsp-8+arg_18], rbx
0x1800173f5  push    rbp
0x1800173f6  push    rsi
0x1800173f7  push    rdi
0x1800173f8  push    r12
0x1800173fa  push    r13
0x1800173fc  push    r14
0x1800173fe  push    r15
0x180017400  lea     rbp, [rsp-27h]
0x180017405  sub     rsp, 0A0h
0x18001740c  mov     rax, cs:__security_cookie
0x180017413  xor     rax, rsp
0x180017416  mov     [rbp+57h+var_40], rax
0x18001741a  mov     [rbp+57h+var_90], r8
0x18001741e  mov     r12, rdx
0x180017421  mov     rsi, rcx
0x180017424  xor     r14d, r14d
0x180017427  mov     ebx, r14d
0x18001742a  mov     [rbp+57h+var_98], rbx
0x18001742e  test    rdx, rdx
0x180017431  jz      loc_1800175E8
0x180017437  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x18001743e  mov     [rbp+57h+var_80], rax
0x180017442  lea     r15, [rcx+28h]
0x180017446  mov     [rbp+57h+var_78], r15
0x18001744a  mov     rax, [r15]
0x18001744d  mov     rcx, r15
0x180017450  mov     rax, [rax]
0x180017453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017458  nop
0x180017459  mov     rcx, r12; psz
0x18001745c  call    cs:__imp_SysAllocString
0x180017462  mov     rdi, rax
0x180017465  mov     [rbp+57h+var_88], rax
0x180017469  test    rax, rax
0x18001746c  jz      loc_180017637
0x180017472  mov     rcx, rax; pbstr
0x180017475  call    cs:__imp_SysStringLen
0x18001747b  test    eax, eax
0x18001747d  jz      short loc_180017493
0x18001747f  mov     rcx, rdi; pbstr
0x180017482  call    cs:__imp_SysStringLen
0x180017488  mov     edx, eax; cchLength
0x18001748a  mov     rcx, rdi; lpsz
0x18001748d  call    cs:__imp_CharLowerBuffW
0x180017493  lea     r13, [rsi+398h]
0x18001749a  mov     [rbp+57h+var_A0], r13
0x18001749e  xorps   xmm0, xmm0
0x1800174a1  movups  [rbp+57h+var_60], xmm0
0x1800174a5  xorps   xmm1, xmm1
0x1800174a8  movdqu  [rbp+57h+var_50], xmm1
0x1800174ad  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800174b1  mov     r8, r14
0x1800174b4  xor     eax, eax
0x1800174b6  inc     r8
0x1800174b9  cmp     [rdi+r8*2], ax
0x1800174be  jnz     short loc_1800174B6
0x1800174c0  mov     rdx, rdi
0x1800174c3  lea     rcx, [rbp+57h+var_60]
0x1800174c7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800174cc  lea     rdx, [rbp+57h+var_60]
0x1800174d0  call    ??R?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@QEBA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_compare<std::wstring,std::less<std::wstring>>::operator()(std::wstring const &)
0x1800174d5  mov     r9, rax
0x1800174d8  lea     r8, [rbp+57h+var_60]
0x1800174dc  lea     rdx, [rbp+57h+var_70]
0x1800174e0  mov     rcx, r13
0x1800174e3  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCRegistration@@@2@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCRegistration@@@2@@std@@@2@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCRegistration@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<stdext::_Hmap_traits<std::wstring,std::shared_ptr<CRegistration>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<CRegistration>>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x1800174e8  mov     r13, [rax+8]
0x1800174ec  test    r13, r13
0x1800174ef  jnz     short loc_1800174F8
0x1800174f1  mov     r13, [rsi+3A0h]
0x1800174f8  mov     rsi, [rsi+3A0h]
0x1800174ff  lea     rcx, [rbp+57h+var_60]; void *
0x180017503  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017508  cmp     r13, rsi
0x18001750b  jz      short loc_18001756E
0x18001750d  xorps   xmm0, xmm0
0x180017510  movups  [rbp+57h+var_60], xmm0
0x180017514  xorps   xmm1, xmm1
0x180017517  movdqu  [rbp+57h+var_50], xmm1
0x18001751c  xor     r13d, r13d
0x18001751f  inc     r14
0x180017522  cmp     [rdi+r14*2], r13w
0x180017527  jnz     short loc_18001751F
0x180017529  mov     r8, r14
0x18001752c  mov     rdx, rdi
0x18001752f  lea     rcx, [rbp+57h+var_60]
0x180017533  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180017538  nop
0x180017539  lea     rdx, [rbp+57h+var_60]
0x18001753d  mov     rcx, [rbp+57h+var_A0]
0x180017541  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CComPtr@UISmsDevice@@@ATL@@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CComPtr@UISmsDevice@@@ATL@@@std@@@2@@stdext@@QEAAAEAV?$CComPtr@UISmsDevice@@@ATL@@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ATL::CComPtr<ISmsDevice>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ATL::CComPtr<ISmsDevice>>>>::operator[](std::wstring &&)
0x180017546  mov     rsi, [rax]
0x180017549  test    rsi, rsi
0x18001754c  jz      short loc_180017564
0x18001754e  mov     rax, [rsi]
0x180017551  mov     rcx, rsi
0x180017554  mov     rax, [rax+8]
0x180017558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001755d  mov     rbx, rsi
0x180017560  mov     [rbp+57h+var_98], rbx
0x180017564  lea     rcx, [rbp+57h+var_60]; void *
0x180017568  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001756d  nop
0x18001756e  mov     rcx, rdi; bstrString
0x180017571  call    cs:__imp_SysFreeString
0x180017577  nop
0x180017578  mov     rax, [r15]
0x18001757b  mov     rcx, r15
0x18001757e  mov     rax, [rax+8]
0x180017582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017587  nop
0x180017588  test    rbx, rbx
0x18001758b  jz      short loc_1800175E8
0x18001758d  mov     rax, [rbx]
0x180017590  mov     rsi, [rbp+57h+var_90]
0x180017594  mov     rdx, rsi
0x180017597  mov     rcx, rbx
0x18001759a  mov     rax, [rax+58h]
0x18001759e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175a3  mov     edi, eax
0x1800175a5  test    eax, eax
0x1800175a7  jns     short loc_1800175CF
0x1800175a9  mov     [rsp+0D0h+var_A8], rsi
0x1800175ae  mov     [rsp+0D0h+var_B0], r12
0x1800175b3  lea     r9, aSetsmscaddress_1; "SetSmscAddress DeviceId: %S, Address: %"...
0x1800175ba  mov     r8d, eax; int
0x1800175bd  mov     edx, 22Bh; unsigned int
0x1800175c2  lea     rcx, aCsmsserviceman_15; "CSmsServiceManager::SetSmscAddress"
0x1800175c9  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x1800175ce  nop
0x1800175cf  test    rbx, rbx
0x1800175d2  jz      short loc_1800175E4
0x1800175d4  mov     rax, [rbx]
0x1800175d7  mov     rcx, rbx
0x1800175da  mov     rax, [rax+10h]
0x1800175de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175e3  nop
0x1800175e4  mov     eax, edi
0x1800175e6  jmp     short loc_180017610
0x1800175e8  mov     [rsp+0D0h+var_B0], r12
0x1800175ed  lea     r9, aSmsdeviceNotFo; "SmsDevice not found for DeviceId: %S"
0x1800175f4  mov     ebx, 80070490h
0x1800175f9  mov     r8d, ebx; int
0x1800175fc  mov     edx, 224h; unsigned int
0x180017601  lea     rcx, aCsmsserviceman_15; "CSmsServiceManager::SetSmscAddress"
0x180017608  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18001760d  nop
0x18001760e  mov     eax, ebx
0x180017610  mov     rcx, [rbp+57h+var_40]
0x180017614  xor     rcx, rsp; StackCookie
0x180017617  call    __security_check_cookie
0x18001761c  mov     rbx, [rsp+0D0h+arg_18]
0x180017624  add     rsp, 0A0h
0x18001762b  pop     r15
0x18001762d  pop     r14
0x18001762f  pop     r13
0x180017631  pop     r12
0x180017633  pop     rdi
0x180017634  pop     rsi
0x180017635  pop     rbp
0x180017636  retn
0x180017637  mov     ecx, 8007000Eh; int
0x18001763c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
