# CSmsServiceManager::OnSmsDeviceAdded(ISmsDevice *)

- ea: `0x1800162f0`
- end: `0x18001648b`
- name: `?OnSmsDeviceAdded@CSmsServiceManager@@UEAAJPEAUISmsDevice@@@Z`
- size: `411`
- prototype: `__int64 __fastcall(CSmsServiceManager *__hidden this, struct ISmsDevice *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003a60`
- `0x1800069f0`
- `0x18000d388`
- `0x180014a64`
- `0x1800162f0`
- `0x180051628`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x180016371`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x180016371`
- `OLEAUT32!__imp_SysFreeString` at `0x180016463`
- `OLEAUT32!__imp_SysFreeString` at `0x180016463`
- `OLEAUT32!__imp_SysStringLen` at `0x180016357`
- `OLEAUT32!__imp_SysStringLen` at `0x180016365`
- `OLEAUT32!__imp_SysStringLen` at `0x180016357`
- `OLEAUT32!__imp_SysStringLen` at `0x180016365`

## string_xrefs

- `0x180016403`: `CSmsServiceManager::OnSmsDeviceAdded`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSmsServiceManager::OnSmsDeviceAdded(void (__fastcall ***this)(char *), struct ISmsDevice *a2)
{
  UINT v4; // eax
  unsigned __int64 v5; // r8
  char *v6; // rax
  char *v7; // rdi
  BSTR pbstr[3]; // [rsp+30h] [rbp-40h] BYREF
  _OWORD v10[2]; // [rsp+48h] [rbp-28h] BYREF

  pbstr[0] = 0;
  (*(void (__fastcall **)(struct ISmsDevice *, BSTR *))(*(_QWORD *)a2 + 40LL))(a2, pbstr);
  pbstr[1] = (BSTR)&Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
  pbstr[2] = (BSTR)(this + 5);
  (*this[5])((char *)this + 40);
  if ( SysStringLen(pbstr[0]) )
  {
    v4 = SysStringLen(pbstr[0]);
    CharLowerBuffW(pbstr[0], v4);
  }
  memset(v10, 0, sizeof(v10));
  v5 = -1;
  do
    ++v5;
  while ( pbstr[0][v5] );
  std::wstring::_Construct<1,unsigned short const *>((char **)v10, pbstr[0], v5);
  v6 = stdext::hash_map<std::wstring,ATL::CComPtr<ISmsDevice>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ATL::CComPtr<ISmsDevice>>>>::operator[](
         (__int64)(this + 115),
         (__int64)v10);
  v7 = v6;
  if ( *(struct ISmsDevice **)v6 != a2 && v6 )
  {
    (*(void (__fastcall **)(struct ISmsDevice *))(*(_QWORD *)a2 + 8LL))(a2);
    if ( *(_QWORD *)v7 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v7 + 16LL))(*(_QWORD *)v7);
    *(_QWORD *)v7 = a2;
  }
  std::wstring::~wstring((char **)v10);
  LogSmsRouterInfo(
    "CSmsServiceManager::OnSmsDeviceAdded",
    0x27Du,
    "Adding DeviceId: %S, SmsDevice: 0x%08X",
    pbstr[0],
    (_DWORD)a2);
  this[5][1]((char *)this + 40);
  (*(void (__fastcall **)(struct ISmsDevice *, _QWORD))(*(_QWORD *)a2 + 128LL))(
    a2,
    (unsigned __int64)(this + 1) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
  (*(void (__fastcall **)(struct ISmsDevice *, unsigned __int64))(*(_QWORD *)a2 + 120LL))(
    a2,
    (unsigned __int64)(this + 2) & -(__int64)(this != 0));
  SysFreeString(pbstr[0]);
  return 0;
}

```

## disassembly

```asm
0x1800162f0  mov     [rsp-28h+arg_10], rbx
0x1800162f5  push    rbp
0x1800162f6  push    rsi
0x1800162f7  push    rdi
0x1800162f8  push    r14
0x1800162fa  push    r15
0x1800162fc  mov     rbp, rsp
0x1800162ff  sub     rsp, 70h
0x180016303  mov     rax, cs:__security_cookie
0x18001630a  xor     rax, rsp
0x18001630d  mov     [rbp+var_8], rax
0x180016311  mov     rbx, rdx
0x180016314  mov     rsi, rcx
0x180016317  xor     r15d, r15d
0x18001631a  mov     [rbp+pbstr], r15
0x18001631e  mov     rax, [rdx]
0x180016321  lea     rdx, [rbp+pbstr]
0x180016325  mov     rcx, rbx
0x180016328  mov     rax, [rax+28h]
0x18001632c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016331  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x180016338  mov     [rbp+var_38], rax
0x18001633c  lea     r14, [rsi+28h]
0x180016340  mov     [rbp+var_30], r14
0x180016344  mov     rax, [r14]
0x180016347  mov     rcx, r14
0x18001634a  mov     rax, [rax]
0x18001634d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016352  nop
0x180016353  mov     rcx, [rbp+pbstr]; pbstr
0x180016357  call    cs:__imp_SysStringLen
0x18001635d  test    eax, eax
0x18001635f  jz      short loc_180016377
0x180016361  mov     rcx, [rbp+pbstr]; pbstr
0x180016365  call    cs:__imp_SysStringLen
0x18001636b  mov     edx, eax; cchLength
0x18001636d  mov     rcx, [rbp+pbstr]; lpsz
0x180016371  call    cs:__imp_CharLowerBuffW
0x180016377  mov     rdx, [rbp+pbstr]
0x18001637b  xorps   xmm0, xmm0
0x18001637e  movups  [rbp+var_28], xmm0
0x180016382  xorps   xmm1, xmm1
0x180016385  movdqu  [rbp+var_18], xmm1
0x18001638a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001638e  inc     r8
0x180016391  cmp     [rdx+r8*2], r15w
0x180016396  jnz     short loc_18001638E
0x180016398  lea     rcx, [rbp+var_28]
0x18001639c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800163a1  nop
0x1800163a2  lea     rcx, [rsi+398h]
0x1800163a9  lea     rdx, [rbp+var_28]
0x1800163ad  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CComPtr@UISmsDevice@@@ATL@@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CComPtr@UISmsDevice@@@ATL@@@std@@@2@@stdext@@QEAAAEAV?$CComPtr@UISmsDevice@@@ATL@@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ATL::CComPtr<ISmsDevice>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ATL::CComPtr<ISmsDevice>>>>::operator[](std::wstring &&)
0x1800163b2  mov     rdi, rax
0x1800163b5  cmp     [rax], rbx
0x1800163b8  jz      short loc_1800163E5
0x1800163ba  test    rax, rax
0x1800163bd  jz      short loc_1800163E5
0x1800163bf  mov     rcx, [rbx]
0x1800163c2  mov     rax, [rcx+8]
0x1800163c6  mov     rcx, rbx
0x1800163c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163ce  mov     rcx, [rdi]
0x1800163d1  test    rcx, rcx
0x1800163d4  jz      short loc_1800163E2
0x1800163d6  mov     rax, [rcx]
0x1800163d9  mov     rax, [rax+10h]
0x1800163dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163e2  mov     [rdi], rbx
0x1800163e5  lea     rcx, [rbp+var_28]; void *
0x1800163e9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800163ee  mov     [rsp+70h+var_50], rbx
0x1800163f3  mov     r9, [rbp+pbstr]
0x1800163f7  lea     r8, aAddingDeviceid; "Adding DeviceId: %S, SmsDevice: 0x%08X"
0x1800163fe  mov     edx, 27Dh; unsigned int
0x180016403  lea     rcx, aCsmsserviceman_11; "CSmsServiceManager::OnSmsDeviceAdded"
0x18001640a  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18001640f  nop
0x180016410  mov     rax, [r14]
0x180016413  mov     rcx, r14
0x180016416  mov     rax, [rax+8]
0x18001641a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001641f  nop
0x180016420  mov     r8, [rbx]
0x180016423  mov     rax, rsi
0x180016426  lea     rcx, [rsi+8]
0x18001642a  neg     rax
0x18001642d  sbb     rdx, rdx
0x180016430  and     rdx, rcx
0x180016433  mov     rcx, rbx
0x180016436  mov     rax, [r8+80h]
0x18001643d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016442  mov     r8, [rbx]
0x180016445  lea     rax, [rsi+10h]
0x180016449  neg     rsi
0x18001644c  sbb     rdx, rdx
0x18001644f  and     rdx, rax
0x180016452  mov     rcx, rbx
0x180016455  mov     rax, [r8+78h]
0x180016459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001645e  nop
0x18001645f  mov     rcx, [rbp+pbstr]; bstrString
0x180016463  call    cs:__imp_SysFreeString
0x180016469  xor     eax, eax
0x18001646b  mov     rcx, [rbp+var_8]
0x18001646f  xor     rcx, rsp; StackCookie
0x180016472  call    __security_check_cookie
0x180016477  mov     rbx, [rsp+70h+arg_10]
0x18001647f  add     rsp, 70h
0x180016483  pop     r15
0x180016485  pop     r14
0x180016487  pop     rdi
0x180016488  pop     rsi
0x180016489  pop     rbp
0x18001648a  retn
```
