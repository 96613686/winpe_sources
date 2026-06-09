# CSmsServiceManager::OnSmsDeviceRemoved(ISmsDevice *)

- ea: `0x1800164a0`
- end: `0x180016747`
- name: `?OnSmsDeviceRemoved@CSmsServiceManager@@UEAAJPEAUISmsDevice@@@Z`
- size: `679`
- prototype: `__int64 __fastcall(CSmsServiceManager *__hidden this, struct ISmsDevice *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180003a60`
- `0x180003f50`
- `0x1800069f0`
- `0x18000d388`
- `0x18000d8a8`
- `0x18000f018`
- `0x1800164a0`
- `0x180051420`
- `0x180051628`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x180016529`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x180016529`
- `OLEAUT32!__imp_SysFreeString` at `0x180016718`
- `OLEAUT32!__imp_SysFreeString` at `0x180016718`
- `OLEAUT32!__imp_SysStringLen` at `0x18001650f`
- `OLEAUT32!__imp_SysStringLen` at `0x18001651d`
- `OLEAUT32!__imp_SysStringLen` at `0x18001650f`
- `OLEAUT32!__imp_SysStringLen` at `0x18001651d`

## string_xrefs

- `0x18001659e`: `CSmsServiceManager::OnSmsDeviceRemoved`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSmsServiceManager::OnSmsDeviceRemoved(CSmsServiceManager *this, struct ISmsDevice *a2)
{
  char *v4; // r12
  UINT v5; // eax
  _QWORD *v6; // rsi
  unsigned __int64 v7; // r8
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rcx
  bool v11; // bl
  unsigned int v12; // ebx
  unsigned __int64 v13; // r8
  __int64 v14; // rcx
  __int64 v15; // r15
  char **v16; // rbx
  __int64 v17; // rcx
  __int64 v18; // rdx
  char *v19; // rax
  char *v20; // rcx
  char *v21; // rcx
  BSTR pbstr[3]; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v24[2]; // [rsp+48h] [rbp-38h] BYREF
  __int128 v25; // [rsp+58h] [rbp-28h] BYREF
  __int64 v26; // [rsp+68h] [rbp-18h]
  __int64 v27; // [rsp+70h] [rbp-10h]

  pbstr[0] = 0;
  (*(void (__fastcall **)(struct ISmsDevice *, BSTR *))(*(_QWORD *)a2 + 40LL))(a2, pbstr);
  pbstr[1] = (BSTR)&Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
  v4 = (char *)this + 40;
  pbstr[2] = (BSTR)((char *)this + 40);
  (**((void (__fastcall ***)(char *))this + 5))((char *)this + 40);
  if ( SysStringLen(pbstr[0]) )
  {
    v5 = SysStringLen(pbstr[0]);
    CharLowerBuffW(pbstr[0], v5);
  }
  v6 = (_QWORD *)((char *)this + 920);
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v7 = -1;
  do
    ++v7;
  while ( pbstr[0][v7] );
  std::wstring::_Construct<1,unsigned short const *>((char **)&v25, pbstr[0], v7);
  v9 = stdext::hash_compare<std::wstring,std::less<std::wstring>>::operator()(v8, &v25);
  v10 = std::_Hash<stdext::_Hmap_traits<std::wstring,std::shared_ptr<CRegistration>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<CRegistration>>>,0>>::_Find_last<std::wstring>(
          v6,
          v24,
          (const wchar_t *)&v25,
          v9)[1];
  v11 = !v10 || v10 == v6[1];
  std::wstring::~wstring((char **)&v25);
  if ( v11 )
  {
    v12 = -2147023728;
    LogSmsRouterError(
      "CSmsServiceManager::OnSmsDeviceRemoved",
      0x293u,
      -2147023728,
      "m_InstanceIdMap not found for DeviceId: %S, SmsDevice: 0x%08X",
      pbstr[0],
      (_DWORD)a2);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
  }
  else
  {
    LogSmsRouterInfo(
      "CSmsServiceManager::OnSmsDeviceRemoved",
      0x296u,
      "Removing DeviceId: %S, SmsDevice: 0x%08X",
      pbstr[0],
      (_DWORD)a2);
    v25 = 0;
    v26 = 0;
    v27 = 0;
    v13 = -1;
    do
      ++v13;
    while ( pbstr[0][v13] );
    std::wstring::_Construct<1,unsigned short const *>((char **)&v25, pbstr[0], v13);
    v15 = stdext::hash_compare<std::wstring,std::less<std::wstring>>::operator()(v14, &v25);
    v16 = (char **)std::_Hash<stdext::_Hmap_traits<std::wstring,std::shared_ptr<CRegistration>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<CRegistration>>>,0>>::_Find_last<std::wstring>(
                     v6,
                     v24,
                     (const wchar_t *)&v25,
                     v15)[1];
    if ( v16 )
    {
      v17 = 2 * (v15 & v6[6]);
      v18 = v6[3];
      if ( *(char ***)(v18 + 16 * (v15 & v6[6]) + 8) == v16 )
      {
        if ( *(char ***)(v18 + 16 * (v15 & v6[6])) == v16 )
        {
          v19 = (char *)v6[1];
          *(_QWORD *)(v18 + 16 * (v15 & v6[6])) = v19;
        }
        else
        {
          v19 = v16[1];
        }
        *(_QWORD *)(v18 + 8 * v17 + 8) = v19;
      }
      else if ( *(char ***)(v18 + 16 * (v15 & v6[6])) == v16 )
      {
        *(_QWORD *)(v18 + 16 * (v15 & v6[6])) = *v16;
      }
      v20 = *v16;
      --v6[2];
      *(_QWORD *)v16[1] = v20;
      *((_QWORD *)v20 + 1) = v16[1];
      v21 = v16[6];
      if ( v21 )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v21 + 16LL))(v21);
      std::wstring::~wstring(v16 + 2);
      operator delete(v16);
    }
    std::wstring::~wstring((char **)&v25);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
    (*(void (__fastcall **)(struct ISmsDevice *, _QWORD))(*(_QWORD *)a2 + 128LL))(a2, 0);
    (*(void (__fastcall **)(struct ISmsDevice *, _QWORD))(*(_QWORD *)a2 + 120LL))(a2, 0);
    v12 = 0;
  }
  SysFreeString(pbstr[0]);
  return v12;
}

```

## disassembly

```asm
0x1800164a0  mov     [rsp-38h+arg_10], rbx
0x1800164a5  push    rbp
0x1800164a6  push    rsi
0x1800164a7  push    rdi
0x1800164a8  push    r12
0x1800164aa  push    r13
0x1800164ac  push    r14
0x1800164ae  push    r15
0x1800164b0  mov     rbp, rsp
0x1800164b3  sub     rsp, 80h
0x1800164ba  mov     rax, cs:__security_cookie
0x1800164c1  xor     rax, rsp
0x1800164c4  mov     [rbp+var_8], rax
0x1800164c8  mov     r14, rdx
0x1800164cb  mov     rsi, rcx
0x1800164ce  xor     r13d, r13d
0x1800164d1  mov     [rbp+pbstr], r13
0x1800164d5  mov     rax, [rdx]
0x1800164d8  lea     rdx, [rbp+pbstr]
0x1800164dc  mov     rcx, r14
0x1800164df  mov     rax, [rax+28h]
0x1800164e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164e8  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x1800164ef  mov     [rbp+var_48], rax
0x1800164f3  lea     r12, [rsi+28h]
0x1800164f7  mov     [rbp+var_40], r12
0x1800164fb  mov     rax, [r12]
0x1800164ff  mov     rcx, r12
0x180016502  mov     rax, [rax]
0x180016505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001650a  nop
0x18001650b  mov     rcx, [rbp+pbstr]; pbstr
0x18001650f  call    cs:__imp_SysStringLen
0x180016515  test    eax, eax
0x180016517  jz      short loc_18001652F
0x180016519  mov     rcx, [rbp+pbstr]; pbstr
0x18001651d  call    cs:__imp_SysStringLen
0x180016523  mov     edx, eax; cchLength
0x180016525  mov     rcx, [rbp+pbstr]; lpsz
0x180016529  call    cs:__imp_CharLowerBuffW
0x18001652f  add     rsi, 398h
0x180016536  mov     rdx, [rbp+pbstr]
0x18001653a  xorps   xmm0, xmm0
0x18001653d  movups  [rbp+var_28], xmm0
0x180016541  mov     [rbp+var_18], r13
0x180016545  mov     [rbp+var_10], r13
0x180016549  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001654d  mov     r8, r15
0x180016550  inc     r8
0x180016553  cmp     [rdx+r8*2], r13w
0x180016558  jnz     short loc_180016550
0x18001655a  lea     rcx, [rbp+var_28]
0x18001655e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180016563  lea     rdx, [rbp+var_28]
0x180016567  call    ??R?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@QEBA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_compare<std::wstring,std::less<std::wstring>>::operator()(std::wstring const &)
0x18001656c  mov     r9, rax
0x18001656f  lea     r8, [rbp+var_28]
0x180016573  lea     rdx, [rbp+var_38]
0x180016577  mov     rcx, rsi
0x18001657a  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCRegistration@@@2@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCRegistration@@@2@@std@@@2@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCRegistration@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<stdext::_Hmap_traits<std::wstring,std::shared_ptr<CRegistration>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<CRegistration>>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x18001657f  mov     rcx, [rax+8]
0x180016583  test    rcx, rcx
0x180016586  jz      short loc_18001658E
0x180016588  cmp     rcx, [rsi+8]
0x18001658c  jnz     short loc_180016592
0x18001658e  mov     bl, 1
0x180016590  jmp     short loc_180016595
0x180016592  mov     bl, r13b
0x180016595  lea     rcx, [rbp+var_28]; void *
0x180016599  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001659e  lea     rcx, aCsmsserviceman_4; "CSmsServiceManager::OnSmsDeviceRemoved"
0x1800165a5  test    bl, bl
0x1800165a7  jz      short loc_1800165E7
0x1800165a9  mov     [rsp+80h+var_58], r14
0x1800165ae  mov     rax, [rbp+pbstr]
0x1800165b2  mov     [rsp+80h+var_60], rax
0x1800165b7  lea     r9, aMInstanceidmap; "m_InstanceIdMap not found for DeviceId:"...
0x1800165be  mov     ebx, 80070490h
0x1800165c3  mov     r8d, ebx; int
0x1800165c6  mov     edx, 293h; unsigned int
0x1800165cb  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x1800165d0  nop
0x1800165d1  mov     rax, [r12]
0x1800165d5  mov     rcx, r12
0x1800165d8  mov     rax, [rax+8]
0x1800165dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165e1  nop
0x1800165e2  jmp     loc_180016714
0x1800165e7  mov     [rsp+80h+var_60], r14
0x1800165ec  mov     r9, [rbp+pbstr]
0x1800165f0  lea     r8, aRemovingDevice; "Removing DeviceId: %S, SmsDevice: 0x%08"...
0x1800165f7  mov     edx, 296h; unsigned int
0x1800165fc  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180016601  mov     rdx, [rbp+pbstr]
0x180016605  xorps   xmm0, xmm0
0x180016608  movups  [rbp+var_28], xmm0
0x18001660c  mov     [rbp+var_18], r13
0x180016610  mov     [rbp+var_10], r13
0x180016614  mov     r8, r15
0x180016617  inc     r8
0x18001661a  cmp     [rdx+r8*2], r13w
0x18001661f  jnz     short loc_180016617
0x180016621  lea     rcx, [rbp+var_28]
0x180016625  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001662a  lea     rdx, [rbp+var_28]
0x18001662e  call    ??R?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@QEBA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_compare<std::wstring,std::less<std::wstring>>::operator()(std::wstring const &)
0x180016633  mov     r15, rax
0x180016636  mov     r9, rax
0x180016639  lea     r8, [rbp+var_28]
0x18001663d  lea     rdx, [rbp+var_38]
0x180016641  mov     rcx, rsi
0x180016644  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCRegistration@@@2@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCRegistration@@@2@@std@@@2@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCRegistration@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<stdext::_Hmap_traits<std::wstring,std::shared_ptr<CRegistration>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<CRegistration>>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x180016649  mov     rbx, [rax+8]
0x18001664d  test    rbx, rbx
0x180016650  jz      short loc_1800166D1
0x180016652  mov     rcx, [rsi+30h]
0x180016656  and     rcx, r15
0x180016659  add     rcx, rcx
0x18001665c  mov     rdx, [rsi+18h]
0x180016660  cmp     [rdx+rcx*8+8], rbx
0x180016665  jnz     short loc_180016682
0x180016667  cmp     [rdx+rcx*8], rbx
0x18001666b  jnz     short loc_180016677
0x18001666d  mov     rax, [rsi+8]
0x180016671  mov     [rdx+rcx*8], rax
0x180016675  jmp     short loc_18001667B
0x180016677  mov     rax, [rbx+8]
0x18001667b  mov     [rdx+rcx*8+8], rax
0x180016680  jmp     short loc_18001668F
0x180016682  cmp     [rdx+rcx*8], rbx
0x180016686  jnz     short loc_18001668F
0x180016688  mov     rax, [rbx]
0x18001668b  mov     [rdx+rcx*8], rax
0x18001668f  mov     rcx, [rbx]
0x180016692  dec     qword ptr [rsi+10h]
0x180016696  mov     rax, [rbx+8]
0x18001669a  mov     [rax], rcx
0x18001669d  mov     rax, [rbx+8]
0x1800166a1  mov     [rcx+8], rax
0x1800166a5  mov     rcx, [rbx+30h]
0x1800166a9  test    rcx, rcx
0x1800166ac  jz      short loc_1800166BB
0x1800166ae  mov     rax, [rcx]
0x1800166b1  mov     rax, [rax+10h]
0x1800166b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166ba  nop
0x1800166bb  lea     rcx, [rbx+10h]; void *
0x1800166bf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800166c4  mov     edx, 38h ; '8'
0x1800166c9  mov     rcx, rbx; Block
0x1800166cc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800166d1  lea     rcx, [rbp+var_28]; void *
0x1800166d5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800166da  nop
0x1800166db  mov     rax, [r12]
0x1800166df  mov     rcx, r12
0x1800166e2  mov     rax, [rax+8]
0x1800166e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166eb  nop
0x1800166ec  mov     rax, [r14]
0x1800166ef  xor     edx, edx
0x1800166f1  mov     rcx, r14
0x1800166f4  mov     rax, [rax+80h]
0x1800166fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016700  mov     rax, [r14]
0x180016703  xor     edx, edx
0x180016705  mov     rcx, r14
0x180016708  mov     rax, [rax+78h]
0x18001670c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016711  mov     ebx, r13d
0x180016714  mov     rcx, [rbp+pbstr]; bstrString
0x180016718  call    cs:__imp_SysFreeString
0x18001671e  mov     eax, ebx
0x180016720  mov     rcx, [rbp+var_8]
0x180016724  xor     rcx, rsp; StackCookie
0x180016727  call    __security_check_cookie
0x18001672c  mov     rbx, [rsp+80h+arg_10]
0x180016734  add     rsp, 80h
0x18001673b  pop     r15
0x18001673d  pop     r14
0x18001673f  pop     r13
0x180016741  pop     r12
0x180016743  pop     rdi
0x180016744  pop     rsi
0x180016745  pop     rbp
0x180016746  retn
```
