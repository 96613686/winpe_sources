# CSmsServiceManager::GetDeviceStatusEvent(ushort const *,_WNF_STATE_NAME *)

- ea: `0x180015014`
- end: `0x1800152a4`
- name: `?GetDeviceStatusEvent@CSmsServiceManager@@QEAAJPEBGPEAU_WNF_STATE_NAME@@@Z`
- size: `656`
- prototype: `int(CSmsServiceManager *__hidden this, const unsigned __int16 *, struct _WNF_STATE_NAME *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a350`

## callees

- `0x180003a60`
- `0x1800069f0`
- `0x18000d388`
- `0x18000d8a8`
- `0x18000f018`
- `0x180014a64`
- `0x180014d20`
- `0x180015014`
- `0x180051420`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x1800150b1`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x1800150b1`
- `OLEAUT32!__imp_SysAllocString` at `0x180015080`
- `OLEAUT32!__imp_SysAllocString` at `0x180015080`
- `OLEAUT32!__imp_SysFreeString` at `0x1800151c8`
- `OLEAUT32!__imp_SysFreeString` at `0x180015200`
- `OLEAUT32!__imp_SysFreeString` at `0x180015233`
- `OLEAUT32!__imp_SysFreeString` at `0x1800151c8`
- `OLEAUT32!__imp_SysFreeString` at `0x180015200`
- `OLEAUT32!__imp_SysFreeString` at `0x180015233`
- `OLEAUT32!__imp_SysStringLen` at `0x180015099`
- `OLEAUT32!__imp_SysStringLen` at `0x1800150a6`
- `OLEAUT32!__imp_SysStringLen` at `0x180015099`
- `OLEAUT32!__imp_SysStringLen` at `0x1800150a6`

## string_xrefs

- `0x1800151b8`: `CSmsServiceManager::GetDeviceStatusEvent`
- `0x180015263`: `CSmsServiceManager::GetDeviceStatusEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CSmsServiceManager::GetDeviceStatusEvent(
        CSmsServiceManager *this,
        const unsigned __int16 *a2,
        struct _WNF_STATE_NAME *a3)
{
  __int64 v5; // rdi
  char *v6; // r14
  OLECHAR *v7; // rax
  OLECHAR *v8; // rbx
  UINT v9; // eax
  unsigned __int64 v10; // r15
  unsigned __int64 v11; // r8
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // r13
  __int64 v15; // rsi
  char *v16; // rax
  __int64 v17; // rsi
  char *v19; // [rsp+30h] [rbp-49h]
  __int64 v21; // [rsp+60h] [rbp-19h] BYREF
  __int128 v22; // [rsp+70h] [rbp-9h] BYREF
  __int128 v23; // [rsp+80h] [rbp+7h]

  v5 = 0;
  if ( !a2 )
    goto LABEL_20;
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
  v19 = (char *)this + 920;
  v22 = 0;
  v23 = 0;
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( v8[v11] );
  std::wstring::_Construct<1,unsigned short const *>((char **)&v22, v8, v11);
  v13 = stdext::hash_compare<std::wstring,std::less<std::wstring>>::operator()(v12, &v22);
  v14 = std::_Hash<stdext::_Hmap_traits<std::wstring,std::shared_ptr<CRegistration>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<CRegistration>>>,0>>::_Find_last<std::wstring>(
          (_QWORD *)this + 115,
          &v21,
          (const wchar_t *)&v22,
          v13)[1];
  if ( !v14 )
    v14 = *((_QWORD *)this + 116);
  v15 = *((_QWORD *)this + 116);
  std::wstring::~wstring((char **)&v22);
  if ( v14 == v15 )
  {
    SysFreeString(v8);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
LABEL_20:
    LogSmsRouterError(
      "CSmsServiceManager::GetDeviceStatusEvent",
      0x26Fu,
      -2147023728,
      "SmsDevice not found for DeviceId: %S",
      a2);
    return 2147943568LL;
  }
  v22 = 0;
  v23 = 0;
  do
    ++v10;
  while ( v8[v10] );
  std::wstring::_Construct<1,unsigned short const *>((char **)&v22, v8, v10);
  v16 = stdext::hash_map<std::wstring,ATL::CComPtr<ISmsDevice>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ATL::CComPtr<ISmsDevice>>>>::operator[](
          (__int64)v19,
          (__int64)&v22);
  v17 = *(_QWORD *)v16;
  if ( *(_QWORD *)v16 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v17 + 8LL))(*(_QWORD *)v16);
    v5 = v17;
  }
  std::wstring::~wstring((char **)&v22);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64, struct _WNF_STATE_NAME *))(*(_QWORD *)v5 + 136LL))(v5, a3);
    SysFreeString(v8);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    return 0;
  }
  else
  {
    LogSmsRouterError(
      "CSmsServiceManager::GetDeviceStatusEvent",
      0x266u,
      -2147418113,
      "DeviceId: %S, SmsDevice: 0x%08X",
      a2,
      0);
    SysFreeString(v8);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x180015014  mov     [rsp-8+arg_18], rbx
0x180015019  push    rbp
0x18001501a  push    rsi
0x18001501b  push    rdi
0x18001501c  push    r12
0x18001501e  push    r13
0x180015020  push    r14
0x180015022  push    r15
0x180015024  lea     rbp, [rsp-27h]
0x180015029  sub     rsp, 0A0h
0x180015030  mov     rax, cs:__security_cookie
0x180015037  xor     rax, rsp
0x18001503a  mov     [rbp+57h+var_40], rax
0x18001503e  mov     [rbp+57h+var_90], r8
0x180015042  mov     r12, rdx
0x180015045  mov     rsi, rcx
0x180015048  xor     r15d, r15d
0x18001504b  mov     edi, r15d
0x18001504e  mov     [rbp+57h+var_98], r15
0x180015052  test    rdx, rdx
0x180015055  jz      loc_18001524A
0x18001505b  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x180015062  mov     [rbp+57h+var_80], rax
0x180015066  lea     r14, [rcx+28h]
0x18001506a  mov     [rbp+57h+var_78], r14
0x18001506e  mov     rax, [r14]
0x180015071  mov     rcx, r14
0x180015074  mov     rax, [rax]
0x180015077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001507c  nop
0x18001507d  mov     rcx, r12; psz
0x180015080  call    cs:__imp_SysAllocString
0x180015086  mov     rbx, rax
0x180015089  mov     [rbp+57h+var_88], rax
0x18001508d  test    rax, rax
0x180015090  jz      loc_180015299
0x180015096  mov     rcx, rax; pbstr
0x180015099  call    cs:__imp_SysStringLen
0x18001509f  test    eax, eax
0x1800150a1  jz      short loc_1800150B7
0x1800150a3  mov     rcx, rbx; pbstr
0x1800150a6  call    cs:__imp_SysStringLen
0x1800150ac  mov     edx, eax; cchLength
0x1800150ae  mov     rcx, rbx; lpsz
0x1800150b1  call    cs:__imp_CharLowerBuffW
0x1800150b7  lea     r13, [rsi+398h]
0x1800150be  mov     [rbp+57h+var_A0], r13
0x1800150c2  xorps   xmm0, xmm0
0x1800150c5  movups  [rbp+57h+var_60], xmm0
0x1800150c9  xorps   xmm1, xmm1
0x1800150cc  movdqu  [rbp+57h+var_50], xmm1
0x1800150d1  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800150d5  mov     r8, r15
0x1800150d8  xor     eax, eax
0x1800150da  inc     r8
0x1800150dd  cmp     [rbx+r8*2], ax
0x1800150e2  jnz     short loc_1800150DA
0x1800150e4  mov     rdx, rbx
0x1800150e7  lea     rcx, [rbp+57h+var_60]
0x1800150eb  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800150f0  lea     rdx, [rbp+57h+var_60]
0x1800150f4  call    ??R?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@QEBA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_compare<std::wstring,std::less<std::wstring>>::operator()(std::wstring const &)
0x1800150f9  mov     r9, rax
0x1800150fc  lea     r8, [rbp+57h+var_60]
0x180015100  lea     rdx, [rbp+57h+var_70]
0x180015104  mov     rcx, r13
0x180015107  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCRegistration@@@2@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCRegistration@@@2@@std@@@2@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCRegistration@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<stdext::_Hmap_traits<std::wstring,std::shared_ptr<CRegistration>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<CRegistration>>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x18001510c  mov     r13, [rax+8]
0x180015110  test    r13, r13
0x180015113  jnz     short loc_18001511C
0x180015115  mov     r13, [rsi+3A0h]
0x18001511c  mov     rsi, [rsi+3A0h]
0x180015123  lea     rcx, [rbp+57h+var_60]; void *
0x180015127  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001512c  cmp     r13, rsi
0x18001512f  jz      loc_180015230
0x180015135  xorps   xmm0, xmm0
0x180015138  movups  [rbp+57h+var_60], xmm0
0x18001513c  xorps   xmm1, xmm1
0x18001513f  movdqu  [rbp+57h+var_50], xmm1
0x180015144  xor     r13d, r13d
0x180015147  inc     r15
0x18001514a  cmp     [rbx+r15*2], r13w
0x18001514f  jnz     short loc_180015147
0x180015151  mov     r8, r15
0x180015154  mov     rdx, rbx
0x180015157  lea     rcx, [rbp+57h+var_60]
0x18001515b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180015160  nop
0x180015161  lea     rdx, [rbp+57h+var_60]
0x180015165  mov     rcx, [rbp+57h+var_A0]
0x180015169  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CComPtr@UISmsDevice@@@ATL@@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CComPtr@UISmsDevice@@@ATL@@@std@@@2@@stdext@@QEAAAEAV?$CComPtr@UISmsDevice@@@ATL@@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ATL::CComPtr<ISmsDevice>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ATL::CComPtr<ISmsDevice>>>>::operator[](std::wstring &&)
0x18001516e  mov     rsi, [rax]
0x180015171  test    rsi, rsi
0x180015174  jz      short loc_18001518C
0x180015176  mov     rax, [rsi]
0x180015179  mov     rcx, rsi
0x18001517c  mov     rax, [rax+8]
0x180015180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015185  mov     rdi, rsi
0x180015188  mov     [rbp+57h+var_98], rsi
0x18001518c  lea     rcx, [rbp+57h+var_60]; void *
0x180015190  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015195  test    rdi, rdi
0x180015198  jnz     short loc_1800151E6
0x18001519a  mov     [rsp+0D0h+var_A8], r13
0x18001519f  mov     [rsp+0D0h+var_B0], r12
0x1800151a4  lea     r9, aDeviceidSSmsde; "DeviceId: %S, SmsDevice: 0x%08X"
0x1800151ab  mov     edi, 8000FFFFh
0x1800151b0  mov     r8d, edi; int
0x1800151b3  mov     edx, 266h; unsigned int
0x1800151b8  lea     rcx, aCsmsserviceman_1; "CSmsServiceManager::GetDeviceStatusEven"...
0x1800151bf  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x1800151c4  nop
0x1800151c5  mov     rcx, rbx; bstrString
0x1800151c8  call    cs:__imp_SysFreeString
0x1800151ce  nop
0x1800151cf  mov     rdx, [r14]
0x1800151d2  mov     rcx, r14
0x1800151d5  mov     rax, [rdx+8]
0x1800151d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151de  nop
0x1800151df  mov     eax, edi
0x1800151e1  jmp     loc_180015272
0x1800151e6  mov     rax, [rdi]
0x1800151e9  mov     rdx, [rbp+57h+var_90]
0x1800151ed  mov     rcx, rdi
0x1800151f0  mov     rax, [rax+88h]
0x1800151f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151fc  nop
0x1800151fd  mov     rcx, rbx; bstrString
0x180015200  call    cs:__imp_SysFreeString
0x180015206  nop
0x180015207  mov     rax, [r14]
0x18001520a  mov     rcx, r14
0x18001520d  mov     rax, [rax+8]
0x180015211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015216  nop
0x180015217  test    rdi, rdi
0x18001521a  jz      short loc_18001522C
0x18001521c  mov     rax, [rdi]
0x18001521f  mov     rcx, rdi
0x180015222  mov     rax, [rax+10h]
0x180015226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001522b  nop
0x18001522c  xor     eax, eax
0x18001522e  jmp     short loc_180015272
0x180015230  mov     rcx, rbx; bstrString
0x180015233  call    cs:__imp_SysFreeString
0x180015239  nop
0x18001523a  mov     rax, [r14]
0x18001523d  mov     rcx, r14
0x180015240  mov     rax, [rax+8]
0x180015244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015249  nop
0x18001524a  mov     [rsp+0D0h+var_B0], r12
0x18001524f  lea     r9, aSmsdeviceNotFo; "SmsDevice not found for DeviceId: %S"
0x180015256  mov     ebx, 80070490h
0x18001525b  mov     r8d, ebx; int
0x18001525e  mov     edx, 26Fh; unsigned int
0x180015263  lea     rcx, aCsmsserviceman_1; "CSmsServiceManager::GetDeviceStatusEven"...
0x18001526a  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18001526f  nop
0x180015270  mov     eax, ebx
0x180015272  mov     rcx, [rbp+57h+var_40]
0x180015276  xor     rcx, rsp; StackCookie
0x180015279  call    __security_check_cookie
0x18001527e  mov     rbx, [rsp+0D0h+arg_18]
0x180015286  add     rsp, 0A0h
0x18001528d  pop     r15
0x18001528f  pop     r14
0x180015291  pop     r13
0x180015293  pop     r12
0x180015295  pop     rdi
0x180015296  pop     rsi
0x180015297  pop     rbp
0x180015298  retn
0x180015299  mov     ecx, 8007000Eh; int
0x18001529e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
