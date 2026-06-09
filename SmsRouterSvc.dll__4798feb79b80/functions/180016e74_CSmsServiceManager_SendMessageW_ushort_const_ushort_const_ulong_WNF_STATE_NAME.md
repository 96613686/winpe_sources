# CSmsServiceManager::SendMessageW(ushort const *,ushort const *,ulong *,_WNF_STATE_NAME *)

- ea: `0x180016e74`
- end: `0x1800173e9`
- name: `?SendMessageW@CSmsServiceManager@@QEAAJPEBG0PEAKPEAU_WNF_STATE_NAME@@@Z`
- size: `1397`
- prototype: `int(CSmsServiceManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int *, struct _WNF_STATE_NAME *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a950`

## callees

- `0x180003a60`
- `0x180003a90`
- `0x180003f50`
- `0x1800069f0`
- `0x18000d388`
- `0x18000d8a8`
- `0x18000f018`
- `0x180013fd8`
- `0x180014a64`
- `0x180014d20`
- `0x180015aac`
- `0x180016e74`
- `0x180018210`
- `0x180018334`
- `0x1800267f8`
- `0x180051420`
- `0x180051628`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x180016f60`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x180016f60`
- `OLEAUT32!__imp_SysAllocString` at `0x180016f2f`
- `OLEAUT32!__imp_SysAllocString` at `0x180016f2f`
- `OLEAUT32!__imp_SysFreeString` at `0x180017040`
- `OLEAUT32!__imp_SysFreeString` at `0x180017040`
- `OLEAUT32!__imp_SysStringLen` at `0x180016f48`
- `OLEAUT32!__imp_SysStringLen` at `0x180016f55`
- `OLEAUT32!__imp_SysStringLen` at `0x180016f48`
- `OLEAUT32!__imp_SysStringLen` at `0x180016f55`
- `ntdll!NtDeleteWnfStateName` at `0x180017310`
- `ntdll!NtDeleteWnfStateName` at `0x180017310`

## string_xrefs

- `0x18001709e`: `CSmsServiceManager::SendMessageW`
- `0x18001716c`: `CSmsServiceManager::SendMessageW`
- `0x180017254`: `CSmsServiceManager::SendMessageW`
- `0x1800172ce`: `CSmsServiceManager::SendMessageW`
- `0x180017245`: `CSmsRpcUtils::CreateWNFStateName`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CSmsServiceManager::SendMessageW(
        CSmsServiceManager *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int *a4,
        struct _WNF_STATE_NAME *a5)
{
  const unsigned __int16 *v5; // r12
  const OLECHAR *v6; // rsi
  char *v8; // r15
  __int64 v9; // rbx
  _QWORD *v10; // rdi
  __int64 v11; // rax
  OLECHAR *v12; // rax
  OLECHAR *v13; // rdi
  UINT v14; // eax
  char v15; // r12
  unsigned __int64 v16; // rsi
  unsigned __int64 v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  char *v21; // rax
  __int64 v22; // rsi
  __int64 v23; // rax
  const char *v24; // rcx
  int XmlDocument; // edi
  int v27; // r13d
  unsigned int v28; // esi
  char *v29; // r14
  __int64 v30; // rdi
  void *v31; // rax
  void *v32; // rcx
  __int64 v33; // rax
  int WNFStateName; // eax
  struct IXMLDOMDocument *v35; // rdi
  int v36; // eax
  unsigned int v37; // r12d
  __int64 v38; // rax
  __int64 v39; // rax
  const unsigned __int16 *v40; // [rsp+30h] [rbp-71h] BYREF
  struct IXMLDOMDocument *v41; // [rsp+38h] [rbp-69h] BYREF
  const wchar_t *v42; // [rsp+40h] [rbp-61h]
  __int64 v43; // [rsp+48h] [rbp-59h]
  _QWORD v44[2]; // [rsp+50h] [rbp-51h] BYREF
  unsigned int *v45; // [rsp+60h] [rbp-41h]
  struct _WNF_STATE_NAME *v46; // [rsp+68h] [rbp-39h]
  _QWORD v47[3]; // [rsp+70h] [rbp-31h] BYREF
  __int128 v48; // [rsp+88h] [rbp-19h] BYREF
  __int64 v49; // [rsp+98h] [rbp-9h]
  __int64 v50; // [rsp+A0h] [rbp-1h]

  v45 = a4;
  v5 = a3;
  v40 = a3;
  v6 = a2;
  v42 = a2;
  v46 = a5;
  v47[1] = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
  v8 = (char *)this + 40;
  v47[2] = (char *)this + 40;
  (**((void (__fastcall ***)(char *))this + 5))((char *)this + 40);
  v9 = 0;
  v43 = 0;
  v41 = 0;
  if ( v6 )
  {
    v12 = SysAllocString(v6);
    v13 = v12;
    v47[0] = v12;
    if ( !v12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( SysStringLen(v12) )
    {
      v14 = SysStringLen(v13);
      CharLowerBuffW(v13, v14);
    }
    v48 = 0;
    v15 = 0;
    v49 = 0;
    v50 = 0;
    v16 = -1;
    v17 = -1;
    do
      ++v17;
    while ( v13[v17] );
    std::wstring::_Construct<1,unsigned short const *>((char **)&v48, v13, v17);
    v19 = stdext::hash_compare<std::wstring,std::less<std::wstring>>::operator()(v18, &v48);
    v20 = std::_Hash<stdext::_Hmap_traits<std::wstring,std::shared_ptr<CRegistration>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<CRegistration>>>,0>>::_Find_last<std::wstring>(
            (_QWORD *)this + 115,
            v44,
            (const wchar_t *)&v48,
            v19)[1];
    if ( v20 && v20 != *((_QWORD *)this + 116) )
      v15 = 1;
    std::wstring::~wstring((char **)&v48);
    if ( v15 )
    {
      v48 = 0;
      v49 = 0;
      v50 = 0;
      do
        ++v16;
      while ( v13[v16] );
      std::wstring::_Construct<1,unsigned short const *>((char **)&v48, v13, v16);
      v21 = stdext::hash_map<std::wstring,ATL::CComPtr<ISmsDevice>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ATL::CComPtr<ISmsDevice>>>>::operator[](
              (__int64)this + 920,
              (__int64)&v48);
      v22 = *(_QWORD *)v21;
      if ( *(_QWORD *)v21 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v22 + 8LL))(*(_QWORD *)v21);
        v9 = v22;
        v43 = v22;
      }
      std::wstring::~wstring((char **)&v48);
    }
    SysFreeString(v13);
    v10 = (_QWORD *)((char *)this + 936);
    v6 = v42;
    v5 = v40;
  }
  else
  {
    v10 = (_QWORD *)((char *)this + 936);
    if ( !*((_QWORD *)this + 117) )
      goto LABEL_24;
    v11 = *((_QWORD *)this + 116);
    v9 = *(_QWORD *)(*(_QWORD *)v11 + 48LL);
    if ( !v9 )
    {
LABEL_21:
      if ( *v10 )
      {
        v23 = *((_QWORD *)this + 116);
        v24 = (const char *)(*(_QWORD *)v23 + 16LL);
        if ( *(_QWORD *)(*(_QWORD *)v23 + 40LL) > 7u )
          v24 = *(const char **)v24;
        goto LABEL_25;
      }
LABEL_24:
      v24 = (const char *)L"(NULL)";
LABEL_25:
      LogSmsRouterError(
        "CSmsServiceManager::SendMessageW",
        0x1A2u,
        -2147023728,
        "SmsDevice %s not found, default smsdevice is %s",
        (const char *)v6,
        v24);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v8 + 8LL))(v8);
      return 2147943568LL;
    }
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v9 + 8LL))(*(_QWORD *)(*(_QWORD *)v11 + 48LL));
    v43 = v9;
  }
  if ( !v9 )
    goto LABEL_21;
  XmlDocument = Windows::Sms::Common::CSmsUtil::GetXmlDocument(v5, &v41);
  if ( XmlDocument >= 0 )
  {
    v27 = *((_DWORD *)this + 22);
    if ( !v27 )
    {
      v27 = 1;
      *((_DWORD *)this + 22) = 1;
    }
    v28 = v27;
    while ( 1 )
    {
      if ( v28 )
      {
        LODWORD(v40) = v28;
        if ( *(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned long,unsigned long,stdext::hash_compare<unsigned long,std::less<unsigned long>>,std::allocator<std::pair<unsigned long const,unsigned long>>,0>>::find(
                          (char *)this + 856,
                          v47,
                          &v40) == *((_QWORD *)this + 108) )
          break;
      }
      *((_DWORD *)this + 22) = ++v28;
      if ( v28 == v27 )
      {
        XmlDocument = -2147467259;
        LogSmsRouterError("CSmsServiceManager::SendMessageW", 0x1B4u, -2147467259, "GetNextMessageContextId");
        if ( v41 )
          ((void (__fastcall *)(struct IXMLDOMDocument *))v41->lpVtbl->Release)(v41);
LABEL_38:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        (*(void (__fastcall **)(char *))(*(_QWORD *)v8 + 8LL))(v8);
        return (unsigned int)XmlDocument;
      }
    }
    *((_DWORD *)this + 22) = v28 + 1;
    v29 = (char *)this + 856;
    LODWORD(v40) = v28;
    v30 = *(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned long,std::unique_ptr<SendMessageContext>,stdext::hash_compare<unsigned long,std::less<unsigned long>>,std::allocator<std::pair<unsigned long const,std::unique_ptr<SendMessageContext>>>,0>>::_Try_emplace<unsigned long,>(
                       (__int64)v29,
                       (__int64)v44,
                       (unsigned int *)&v40);
    v31 = operator new(8u);
    v32 = *(void **)(v30 + 24);
    *(_QWORD *)(v30 + 24) = v31;
    if ( v32 )
      operator delete(v32);
    LODWORD(v40) = v28;
    v33 = std::_Hash<stdext::_Hmap_traits<unsigned long,std::unique_ptr<SendMessageContext>,stdext::hash_compare<unsigned long,std::less<unsigned long>>,std::allocator<std::pair<unsigned long const,std::unique_ptr<SendMessageContext>>>,0>>::_Try_emplace<unsigned long,>(
            (__int64)v29,
            (__int64)v44,
            (unsigned int *)&v40);
    WNFStateName = CSmsRpcUtils::CreateWNFStateName(*(_QWORD *)(*(_QWORD *)v33 + 24LL), 0);
    XmlDocument = WNFStateName;
    if ( WNFStateName < 0 )
    {
      LogSmsRouterError("CSmsServiceManager::SendMessageW", 0x1BCu, WNFStateName, "CSmsRpcUtils::CreateWNFStateName");
      LODWORD(v40) = v28;
      std::_Hash<stdext::_Hmap_traits<unsigned long,std::unique_ptr<SendMessageContext>,stdext::hash_compare<unsigned long,std::less<unsigned long>>,std::allocator<std::pair<unsigned long const,std::unique_ptr<SendMessageContext>>>,0>>::erase(
        v29,
        &v40);
      if ( v41 )
        ((void (__fastcall *)(struct IXMLDOMDocument *))v41->lpVtbl->Release)(v41);
      goto LABEL_38;
    }
    v35 = v41;
    v36 = (*(__int64 (__fastcall **)(__int64, struct IXMLDOMDocument *, _QWORD))(*(_QWORD *)v9 + 144LL))(v9, v41, v28);
    v37 = v36;
    if ( v36 >= 0 )
    {
      LogSmsRouterInfo(
        "CSmsServiceManager::SendMessageW",
        0x1CAu,
        "SendMessage on SmsDeviceId: %S with ContextId %lu",
        v42,
        v28);
      *v45 = v28;
      LODWORD(v40) = v28;
      v39 = std::_Hash<stdext::_Hmap_traits<unsigned long,std::unique_ptr<SendMessageContext>,stdext::hash_compare<unsigned long,std::less<unsigned long>>,std::allocator<std::pair<unsigned long const,std::unique_ptr<SendMessageContext>>>,0>>::_Try_emplace<unsigned long,>(
              (__int64)v29,
              (__int64)v44,
              (unsigned int *)&v40);
      *v46 = **(struct _WNF_STATE_NAME **)(*(_QWORD *)v39 + 24LL);
      if ( v35 )
        ((void (__fastcall *)(struct IXMLDOMDocument *))v35->lpVtbl->Release)(v35);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v8 + 8LL))(v8);
      return 0;
    }
    else
    {
      LogSmsRouterError("CSmsServiceManager::SendMessageW", 0x1C4u, v36, "SendMessage for SmsDeviceId: %S failed", v42);
      LODWORD(v40) = v28;
      v38 = std::_Hash<stdext::_Hmap_traits<unsigned long,std::unique_ptr<SendMessageContext>,stdext::hash_compare<unsigned long,std::less<unsigned long>>,std::allocator<std::pair<unsigned long const,std::unique_ptr<SendMessageContext>>>,0>>::_Try_emplace<unsigned long,>(
              (__int64)v29,
              (__int64)v44,
              (unsigned int *)&v40);
      NtDeleteWnfStateName(*(_QWORD *)(*(_QWORD *)v38 + 24LL));
      LODWORD(v40) = v28;
      std::_Hash<stdext::_Hmap_traits<unsigned long,std::unique_ptr<SendMessageContext>,stdext::hash_compare<unsigned long,std::less<unsigned long>>,std::allocator<std::pair<unsigned long const,std::unique_ptr<SendMessageContext>>>,0>>::erase(
        v29,
        &v40);
      if ( v35 )
        ((void (__fastcall *)(struct IXMLDOMDocument *))v35->lpVtbl->Release)(v35);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v8 + 8LL))(v8);
      return v37;
    }
  }
  else
  {
    if ( v41 )
      ((void (__fastcall *)(struct IXMLDOMDocument *))v41->lpVtbl->Release)(v41);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v8 + 8LL))(v8);
    return (unsigned int)XmlDocument;
  }
}

```

## disassembly

```asm
0x180016e74  push    rbp
0x180016e76  push    rbx
0x180016e77  push    rsi
0x180016e78  push    rdi
0x180016e79  push    r12
0x180016e7b  push    r13
0x180016e7d  push    r14
0x180016e7f  push    r15
0x180016e81  lea     rbp, [rsp-17h]
0x180016e86  sub     rsp, 0B8h
0x180016e8d  mov     rax, cs:__security_cookie
0x180016e94  xor     rax, rsp
0x180016e97  mov     [rbp+4Fh+var_48], rax
0x180016e9b  mov     [rbp+4Fh+var_90], r9
0x180016e9f  mov     r12, r8
0x180016ea2  mov     [rbp+4Fh+var_C0], r8
0x180016ea6  mov     rsi, rdx
0x180016ea9  mov     [rbp+4Fh+var_B0], rdx
0x180016ead  mov     r14, rcx
0x180016eb0  mov     rax, [rbp+4Fh+arg_20]
0x180016eb4  mov     [rbp+4Fh+var_88], rax
0x180016eb8  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x180016ebf  mov     [rbp+4Fh+var_78], rax
0x180016ec3  lea     r15, [rcx+28h]
0x180016ec7  mov     [rbp+4Fh+var_70], r15
0x180016ecb  mov     rax, [r15]
0x180016ece  mov     rcx, r15
0x180016ed1  mov     rax, [rax]
0x180016ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ed9  nop
0x180016eda  xor     r13d, r13d
0x180016edd  mov     ebx, r13d
0x180016ee0  mov     [rbp+4Fh+var_A8], rbx
0x180016ee4  mov     [rbp+4Fh+var_B8], r13
0x180016ee8  test    rsi, rsi
0x180016eeb  jnz     short loc_180016F2C
0x180016eed  lea     rdi, [r14+3A8h]
0x180016ef4  cmp     [rdi], r13
0x180016ef7  jz      loc_180017079
0x180016efd  mov     rax, [r14+3A0h]
0x180016f04  mov     rbx, [rax]
0x180016f07  mov     rbx, [rbx+30h]
0x180016f0b  test    rbx, rbx
0x180016f0e  jz      loc_18001705A
0x180016f14  mov     rax, [rbx]
0x180016f17  mov     rcx, rbx
0x180016f1a  mov     rax, [rax+8]
0x180016f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f23  mov     [rbp+4Fh+var_A8], rbx
0x180016f27  jmp     loc_180017055
0x180016f2c  mov     rcx, rsi; psz
0x180016f2f  call    cs:__imp_SysAllocString
0x180016f35  mov     rdi, rax
0x180016f38  mov     [rbp+4Fh+var_80], rax
0x180016f3c  test    rax, rax
0x180016f3f  jz      loc_1800173DE
0x180016f45  mov     rcx, rax; pbstr
0x180016f48  call    cs:__imp_SysStringLen
0x180016f4e  test    eax, eax
0x180016f50  jz      short loc_180016F66
0x180016f52  mov     rcx, rdi; pbstr
0x180016f55  call    cs:__imp_SysStringLen
0x180016f5b  mov     edx, eax; cchLength
0x180016f5d  mov     rcx, rdi; lpsz
0x180016f60  call    cs:__imp_CharLowerBuffW
0x180016f66  lea     r13, [r14+398h]
0x180016f6d  xorps   xmm0, xmm0
0x180016f70  movups  [rbp+4Fh+var_68], xmm0
0x180016f74  xor     r12d, r12d
0x180016f77  mov     [rbp+4Fh+var_58], r12
0x180016f7b  mov     [rbp+4Fh+var_50], r12
0x180016f7f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180016f83  mov     r8, rsi
0x180016f86  inc     r8
0x180016f89  cmp     [rdi+r8*2], r12w
0x180016f8e  jnz     short loc_180016F86
0x180016f90  mov     rdx, rdi
0x180016f93  lea     rcx, [rbp+4Fh+var_68]
0x180016f97  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180016f9c  lea     rdx, [rbp+4Fh+var_68]
0x180016fa0  call    ??R?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@QEBA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_compare<std::wstring,std::less<std::wstring>>::operator()(std::wstring const &)
0x180016fa5  mov     r9, rax
0x180016fa8  lea     r8, [rbp+4Fh+var_68]
0x180016fac  lea     rdx, [rbp+4Fh+var_A0]
0x180016fb0  mov     rcx, r13
0x180016fb3  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCRegistration@@@2@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCRegistration@@@2@@std@@@2@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCRegistration@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<stdext::_Hmap_traits<std::wstring,std::shared_ptr<CRegistration>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<CRegistration>>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x180016fb8  mov     rcx, [rax+8]
0x180016fbc  test    rcx, rcx
0x180016fbf  jz      short loc_180016FCA
0x180016fc1  cmp     rcx, [r13+8]
0x180016fc5  jz      short loc_180016FCA
0x180016fc7  mov     r12b, 1
0x180016fca  lea     rcx, [rbp+4Fh+var_68]; void *
0x180016fce  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016fd3  xor     eax, eax
0x180016fd5  test    r12b, r12b
0x180016fd8  jz      short loc_18001703A
0x180016fda  xorps   xmm0, xmm0
0x180016fdd  movups  [rbp+4Fh+var_68], xmm0
0x180016fe1  mov     [rbp+4Fh+var_58], rax
0x180016fe5  mov     [rbp+4Fh+var_50], rax
0x180016fe9  inc     rsi
0x180016fec  cmp     [rdi+rsi*2], ax
0x180016ff0  jnz     short loc_180016FE9
0x180016ff2  mov     r8, rsi
0x180016ff5  mov     rdx, rdi
0x180016ff8  lea     rcx, [rbp+4Fh+var_68]
0x180016ffc  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180017001  nop
0x180017002  lea     rdx, [rbp+4Fh+var_68]
0x180017006  mov     rcx, r13
0x180017009  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CComPtr@UISmsDevice@@@ATL@@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CComPtr@UISmsDevice@@@ATL@@@std@@@2@@stdext@@QEAAAEAV?$CComPtr@UISmsDevice@@@ATL@@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ATL::CComPtr<ISmsDevice>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ATL::CComPtr<ISmsDevice>>>>::operator[](std::wstring &&)
0x18001700e  mov     rsi, [rax]
0x180017011  xor     r13d, r13d
0x180017014  test    rsi, rsi
0x180017017  jz      short loc_18001702F
0x180017019  mov     rax, [rsi]
0x18001701c  mov     rcx, rsi
0x18001701f  mov     rax, [rax+8]
0x180017023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017028  mov     rbx, rsi
0x18001702b  mov     [rbp+4Fh+var_A8], rbx
0x18001702f  lea     rcx, [rbp+4Fh+var_68]; void *
0x180017033  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017038  jmp     short loc_18001703D
0x18001703a  xor     r13d, r13d
0x18001703d  mov     rcx, rdi; bstrString
0x180017040  call    cs:__imp_SysFreeString
0x180017046  lea     rdi, [r14+3A8h]
0x18001704d  mov     rsi, [rbp+4Fh+var_B0]
0x180017051  mov     r12, [rbp+4Fh+var_C0]
0x180017055  test    rbx, rbx
0x180017058  jnz     short loc_1800170C2
0x18001705a  cmp     [rdi], r13
0x18001705d  jbe     short loc_180017079
0x18001705f  mov     rax, [r14+3A0h]
0x180017066  mov     rcx, [rax]
0x180017069  add     rcx, 10h
0x18001706d  cmp     qword ptr [rcx+18h], 7
0x180017072  jbe     short loc_180017080
0x180017074  mov     rcx, [rcx]
0x180017077  jmp     short loc_180017080
0x180017079  lea     rcx, aNull; "(NULL)"
0x180017080  mov     [rsp+0F0h+var_C8], rcx
0x180017085  mov     [rsp+0F0h+var_D0], rsi
0x18001708a  lea     r9, aSmsdeviceSNotF; "SmsDevice %s not found, default smsdevi"...
0x180017091  mov     ebx, 80070490h
0x180017096  mov     r8d, ebx; int
0x180017099  mov     edx, 1A2h; unsigned int
0x18001709e  lea     rcx, aCsmsserviceman_8; "CSmsServiceManager::SendMessageW"
0x1800170a5  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x1800170aa  nop
0x1800170ab  mov     rdx, [r15]
0x1800170ae  mov     rcx, r15
0x1800170b1  mov     rax, [rdx+8]
0x1800170b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170ba  nop
0x1800170bb  mov     eax, ebx
0x1800170bd  jmp     loc_1800171B1
0x1800170c2  lea     rdx, [rbp+4Fh+var_B8]; struct IXMLDOMDocument **
0x1800170c6  mov     rcx, r12; unsigned __int16 *
0x1800170c9  call    ?GetXmlDocument@CSmsUtil@Common@Sms@Windows@@SAJPEBGPEAPEAUIXMLDOMDocument@@@Z; Windows::Sms::Common::CSmsUtil::GetXmlDocument(ushort const *,IXMLDOMDocument * *)
0x1800170ce  mov     edi, eax
0x1800170d0  test    eax, eax
0x1800170d2  jns     short loc_18001710F
0x1800170d4  mov     rcx, [rbp+4Fh+var_B8]
0x1800170d8  test    rcx, rcx
0x1800170db  jz      short loc_1800170EA
0x1800170dd  mov     rdx, [rcx]
0x1800170e0  mov     rax, [rdx+10h]
0x1800170e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170e9  nop
0x1800170ea  mov     rax, [rbx]
0x1800170ed  mov     rcx, rbx
0x1800170f0  mov     rax, [rax+10h]
0x1800170f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170f9  nop
0x1800170fa  mov     rax, [r15]
0x1800170fd  mov     rcx, r15
0x180017100  mov     rax, [rax+8]
0x180017104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017109  nop
0x18001710a  jmp     loc_1800171AF
0x18001710f  mov     r13d, [r14+58h]
0x180017113  test    r13d, r13d
0x180017116  jnz     short loc_18001711F
0x180017118  inc     r13d
0x18001711b  mov     [r14+58h], r13d
0x18001711f  mov     esi, r13d
0x180017122  test    esi, esi
0x180017124  jz      short loc_18001714D
0x180017126  lea     rdi, [r14+358h]
0x18001712d  mov     dword ptr [rbp+4Fh+var_C0], esi
0x180017130  lea     r8, [rbp+4Fh+var_C0]
0x180017134  lea     rdx, [rbp+4Fh+var_80]
0x180017138  mov     rcx, rdi
0x18001713b  call    ?find@?$_Hash@V?$_Hmap_traits@KKV?$hash_compare@KU?$less@K@std@@@stdext@@V?$allocator@U?$pair@$$CBKK@std@@@std@@$0A@@stdext@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKK@std@@@std@@@std@@@2@AEBK@Z; std::_Hash<stdext::_Hmap_traits<ulong,ulong,stdext::hash_compare<ulong,std::less<ulong>>,std::allocator<std::pair<ulong const,ulong>>,0>>::find(ulong const &)
0x180017140  mov     rcx, [rdi+8]
0x180017144  cmp     [rax], rcx
0x180017147  jz      loc_1800171D1
0x18001714d  inc     esi
0x18001714f  mov     [r14+58h], esi
0x180017153  cmp     esi, r13d
0x180017156  jnz     short loc_180017122
0x180017158  lea     r9, aGetnextmessage_1; "GetNextMessageContextId"
0x18001715f  mov     edi, 80004005h
0x180017164  mov     r8d, edi; int
0x180017167  mov     edx, 1B4h; unsigned int
0x18001716c  lea     rcx, aCsmsserviceman_8; "CSmsServiceManager::SendMessageW"
0x180017173  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180017178  nop
0x180017179  mov     rcx, [rbp+4Fh+var_B8]
0x18001717d  test    rcx, rcx
0x180017180  jz      short loc_18001718F
0x180017182  mov     rax, [rcx]
0x180017185  mov     rax, [rax+10h]
0x180017189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001718e  nop
0x18001718f  mov     rax, [rbx]
0x180017192  mov     rcx, rbx
0x180017195  mov     rax, [rax+10h]
0x180017199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001719e  nop
0x18001719f  mov     rcx, [r15]
0x1800171a2  mov     rax, [rcx+8]
0x1800171a6  mov     rcx, r15
0x1800171a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171ae  nop
0x1800171af  mov     eax, edi
0x1800171b1  mov     rcx, [rbp+4Fh+var_48]
0x1800171b5  xor     rcx, rsp; StackCookie
0x1800171b8  call    __security_check_cookie
0x1800171bd  add     rsp, 0B8h
0x1800171c4  pop     r15
0x1800171c6  pop     r14
0x1800171c8  pop     r13
0x1800171ca  pop     r12
0x1800171cc  pop     rdi
0x1800171cd  pop     rsi
0x1800171ce  pop     rbx
0x1800171cf  pop     rbp
0x1800171d0  retn
0x1800171d1  lea     eax, [rsi+1]
0x1800171d4  mov     [r14+58h], eax
0x1800171d8  add     r14, 358h
0x1800171df  mov     dword ptr [rbp+4Fh+var_C0], esi
0x1800171e2  lea     r8, [rbp+4Fh+var_C0]
0x1800171e6  lea     rdx, [rbp+4Fh+var_A0]
0x1800171ea  mov     rcx, r14
0x1800171ed  call    ??$_Try_emplace@K$$V@?$_Hash@V?$_Hmap_traits@KV?$unique_ptr@USendMessageContext@@U?$default_delete@USendMessageContext@@@std@@@std@@V?$hash_compare@KU?$less@K@std@@@stdext@@V?$allocator@U?$pair@$$CBKV?$unique_ptr@USendMessageContext@@U?$default_delete@USendMessageContext@@@std@@@std@@@std@@@2@$0A@@stdext@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBKV?$unique_ptr@USendMessageContext@@U?$default_delete@USendMessageContext@@@std@@@std@@@std@@PEAX@std@@_N@1@$$QEAK@Z; std::_Hash<stdext::_Hmap_traits<ulong,std::unique_ptr<SendMessageContext>,stdext::hash_compare<ulong,std::less<ulong>>,std::allocator<std::pair<ulong const,std::unique_ptr<SendMessageContext>>>,0>>::_Try_emplace<ulong,>(ulong &&)
0x1800171f2  mov     rdi, [rax]
0x1800171f5  mov     r13d, 8
0x1800171fb  mov     ecx, r13d; Size
0x1800171fe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017203  mov     rcx, [rdi+18h]; Block
0x180017207  mov     [rdi+18h], rax
0x18001720b  test    rcx, rcx
0x18001720e  jz      short loc_180017218
0x180017210  mov     edx, r13d
0x180017213  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017218  mov     dword ptr [rbp+4Fh+var_C0], esi
0x18001721b  lea     r8, [rbp+4Fh+var_C0]
0x18001721f  lea     rdx, [rbp+4Fh+var_A0]
0x180017223  mov     rcx, r14
0x180017226  call    ??$_Try_emplace@K$$V@?$_Hash@V?$_Hmap_traits@KV?$unique_ptr@USendMessageContext@@U?$default_delete@USendMessageContext@@@std@@@std@@V?$hash_compare@KU?$less@K@std@@@stdext@@V?$allocator@U?$pair@$$CBKV?$unique_ptr@USendMessageContext@@U?$default_delete@USendMessageContext@@@std@@@std@@@std@@@2@$0A@@stdext@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBKV?$unique_ptr@USendMessageContext@@U?$default_delete@USendMessageContext@@@std@@@std@@@std@@PEAX@std@@_N@1@$$QEAK@Z; std::_Hash<stdext::_Hmap_traits<ulong,std::unique_ptr<SendMessageContext>,stdext::hash_compare<ulong,std::less<ulong>>,std::allocator<std::pair<ulong const,std::unique_ptr<SendMessageContext>>>,0>>::_Try_emplace<ulong,>(ulong &&)
0x18001722b  mov     rcx, [rax]
0x18001722e  xor     edx, edx
0x180017230  mov     r8d, 4B0h
0x180017236  mov     rcx, [rcx+18h]
0x18001723a  call    ?CreateWNFStateName@CSmsRpcUtils@@SAJPEAU_WNF_STATE_NAME@@PEBGKW4_WNF_STATE_NAME_LIFETIME@@@Z; CSmsRpcUtils::CreateWNFStateName(_WNF_STATE_NAME *,ushort const *,ulong,_WNF_STATE_NAME_LIFETIME)
0x18001723f  mov     edi, eax
0x180017241  test    eax, eax
0x180017243  jns     short loc_1800172AB
0x180017245  lea     r9, aCsmsrpcutilsCr; "CSmsRpcUtils::CreateWNFStateName"
0x18001724c  mov     r8d, eax; int
0x18001724f  mov     edx, 1BCh; unsigned int
0x180017254  lea     rcx, aCsmsserviceman_8; "CSmsServiceManager::SendMessageW"
0x18001725b  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180017260  mov     dword ptr [rbp+4Fh+var_C0], esi
0x180017263  lea     rdx, [rbp+4Fh+var_C0]
0x180017267  mov     rcx, r14
0x18001726a  call    ?erase@?$_Hash@V?$_Hmap_traits@KV?$unique_ptr@USendMessageContext@@U?$default_delete@USendMessageContext@@@std@@@std@@V?$hash_compare@KU?$less@K@std@@@stdext@@V?$allocator@U?$pair@$$CBKV?$unique_ptr@USendMessageContext@@U?$default_delete@USendMessageContext@@@std@@@std@@@std@@@2@$0A@@stdext@@@std@@QEAA_KAEBK@Z; std::_Hash<stdext::_Hmap_traits<ulong,std::unique_ptr<SendMessageContext>,stdext::hash_compare<ulong,std::less<ulong>>,std::allocator<std::pair<ulong const,std::unique_ptr<SendMessageContext>>>,0>>::erase(ulong const &)
0x18001726f  nop
0x180017270  mov     rcx, [rbp+4Fh+var_B8]
0x180017274  test    rcx, rcx
0x180017277  jz      short loc_180017286
0x180017279  mov     rax, [rcx]
0x18001727c  mov     rax, [rax+10h]
0x180017280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017285  nop
0x180017286  mov     rax, [rbx]
0x180017289  mov     rcx, rbx
0x18001728c  mov     rax, [rax+10h]
0x180017290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017295  nop
0x180017296  mov     rax, [r15]
0x180017299  mov     rcx, r15
0x18001729c  mov     rax, [rax+8]
0x1800172a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172a5  nop
  ... truncated ...
```
