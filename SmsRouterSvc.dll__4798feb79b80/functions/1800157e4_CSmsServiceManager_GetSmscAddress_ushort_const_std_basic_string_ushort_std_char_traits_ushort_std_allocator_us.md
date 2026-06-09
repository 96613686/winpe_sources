# CSmsServiceManager::GetSmscAddress(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800157e4`
- end: `0x180015aa6`
- name: `?GetSmscAddress@CSmsServiceManager@@QEAAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `706`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a400`

## callees

- `0x180003a60`
- `0x18000498c`
- `0x18000659c`
- `0x1800069f0`
- `0x18000d388`
- `0x18000d8a8`
- `0x18000f018`
- `0x180014a64`
- `0x180014d20`
- `0x1800157e4`
- `0x180051420`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x180015885`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x180015885`
- `OLEAUT32!__imp_SysAllocString` at `0x180015854`
- `OLEAUT32!__imp_SysAllocString` at `0x180015854`
- `OLEAUT32!__imp_SysFreeString` at `0x180015975`
- `OLEAUT32!__imp_SysFreeString` at `0x180015a25`
- `OLEAUT32!__imp_SysFreeString` at `0x180015a6b`
- `OLEAUT32!__imp_SysFreeString` at `0x180015975`
- `OLEAUT32!__imp_SysFreeString` at `0x180015a25`
- `OLEAUT32!__imp_SysFreeString` at `0x180015a6b`
- `OLEAUT32!__imp_SysStringLen` at `0x18001586d`
- `OLEAUT32!__imp_SysStringLen` at `0x18001587a`
- `OLEAUT32!__imp_SysStringLen` at `0x18001586d`
- `OLEAUT32!__imp_SysStringLen` at `0x18001587a`

## string_xrefs

- `0x1800159c6`: `CSmsServiceManager::GetSmscAddress`
- `0x180015a5a`: `CSmsServiceManager::GetSmscAddress`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CSmsServiceManager::GetSmscAddress(__int64 a1, const OLECHAR *a2, __int64 a3)
{
  __int64 v6; // rdi
  __int64 v7; // r12
  OLECHAR *v8; // rax
  OLECHAR *v9; // rbx
  UINT v10; // eax
  unsigned __int64 v11; // r14
  unsigned __int64 v12; // r8
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rsi
  unsigned __int64 v16; // r8
  char *v17; // rax
  __int64 v18; // rsi
  int v19; // eax
  __int64 v20; // r8
  unsigned int v21; // r12d
  void *v22; // r9
  char *v23; // rsi
  void *Src; // [rsp+30h] [rbp-49h] BYREF
  __int64 v26; // [rsp+38h] [rbp-41h] BYREF
  __int64 v27; // [rsp+48h] [rbp-31h]
  __int64 v28; // [rsp+50h] [rbp-29h]
  OLECHAR *v29; // [rsp+58h] [rbp-21h]
  void **v30; // [rsp+60h] [rbp-19h]
  __int64 v31; // [rsp+68h] [rbp-11h]
  __int128 v32; // [rsp+70h] [rbp-9h] BYREF
  __int128 v33; // [rsp+80h] [rbp+7h]

  v6 = 0;
  v28 = 0;
  Src = 0;
  if ( !a2 )
    goto LABEL_27;
  v30 = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
  v7 = a1 + 40;
  v31 = a1 + 40;
  (**(void (__fastcall ***)(__int64))(a1 + 40))(a1 + 40);
  v8 = SysAllocString(a2);
  v9 = v8;
  v29 = v8;
  if ( !v8 )
    ATL::AtlThrowImpl(-2147024882);
  if ( SysStringLen(v8) )
  {
    v10 = SysStringLen(v9);
    CharLowerBuffW(v9, v10);
  }
  v27 = a1 + 920;
  v32 = 0;
  v33 = 0;
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( v9[v12] );
  std::wstring::_Construct<1,unsigned short const *>((char **)&v32, v9, v12);
  v14 = stdext::hash_compare<std::wstring,std::less<std::wstring>>::operator()(v13, &v32);
  v26 = std::_Hash<stdext::_Hmap_traits<std::wstring,std::shared_ptr<CRegistration>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<CRegistration>>>,0>>::_Find_last<std::wstring>(
          (_QWORD *)(a1 + 920),
          &v26,
          (const wchar_t *)&v32,
          v14)[1];
  if ( !v26 )
    v26 = *(_QWORD *)(a1 + 928);
  v15 = *(_QWORD *)(a1 + 928);
  std::wstring::~wstring((char **)&v32);
  if ( v26 != v15 )
  {
    v32 = 0;
    v33 = 0;
    v16 = -1;
    do
      ++v16;
    while ( v9[v16] );
    std::wstring::_Construct<1,unsigned short const *>((char **)&v32, v9, v16);
    v17 = stdext::hash_map<std::wstring,ATL::CComPtr<ISmsDevice>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ATL::CComPtr<ISmsDevice>>>>::operator[](
            v27,
            (__int64)&v32);
    v18 = *(_QWORD *)v17;
    if ( *(_QWORD *)v17 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v18 + 8LL))(*(_QWORD *)v17);
      v6 = v18;
      v28 = v18;
    }
    std::wstring::~wstring((char **)&v32);
  }
  SysFreeString(v9);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  if ( v6 )
  {
    v19 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v6 + 80LL))(v6, &Src);
    v21 = v19;
    if ( v19 >= 0 )
    {
      v22 = Src;
      do
        ++v11;
      while ( *((_WORD *)Src + v11) );
      if ( v11 > *(_QWORD *)(a3 + 24) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          (char **)a3,
          v11,
          v20,
          Src);
      }
      else
      {
        if ( *(_QWORD *)(a3 + 24) <= 7u )
          v23 = (char *)a3;
        else
          v23 = *(char **)a3;
        *(_QWORD *)(a3 + 16) = v11;
        memmove_0(v23, v22, 2 * v11);
        *(_WORD *)&v23[2 * v11] = 0;
      }
    }
    else
    {
      LogSmsRouterError("CSmsServiceManager::GetSmscAddress", 0x24Cu, v19, "GetSmscNumber DeviceId: %S failed", a2);
    }
    SysFreeString((BSTR)Src);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    return v21;
  }
  else
  {
LABEL_27:
    LogSmsRouterError(
      "CSmsServiceManager::GetSmscAddress",
      0x245u,
      -2147023728,
      "SmsDevice not found for DeviceId: %S",
      a2);
    SysFreeString((BSTR)Src);
    return 2147943568LL;
  }
}

```

## disassembly

```asm
0x1800157e4  mov     [rsp-8+arg_18], rbx
0x1800157e9  push    rbp
0x1800157ea  push    rsi
0x1800157eb  push    rdi
0x1800157ec  push    r12
0x1800157ee  push    r13
0x1800157f0  push    r14
0x1800157f2  push    r15
0x1800157f4  lea     rbp, [rsp-27h]
0x1800157f9  sub     rsp, 0A0h
0x180015800  mov     rax, cs:__security_cookie
0x180015807  xor     rax, rsp
0x18001580a  mov     [rbp+57h+var_40], rax
0x18001580e  mov     r15, r8
0x180015811  mov     r13, rdx
0x180015814  mov     rsi, rcx
0x180015817  xor     r14d, r14d
0x18001581a  mov     edi, r14d
0x18001581d  mov     [rbp+57h+var_80], r14
0x180015821  mov     [rbp+57h+Src], r14
0x180015825  test    rdx, rdx
0x180015828  jz      loc_180015A41
0x18001582e  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x180015835  mov     [rbp+57h+var_70], rax
0x180015839  lea     r12, [rcx+28h]
0x18001583d  mov     [rbp+57h+var_68], r12
0x180015841  mov     rax, [r12]
0x180015845  mov     rcx, r12
0x180015848  mov     rax, [rax]
0x18001584b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015850  nop
0x180015851  mov     rcx, r13; psz
0x180015854  call    cs:__imp_SysAllocString
0x18001585a  mov     rbx, rax
0x18001585d  mov     [rbp+57h+var_78], rax
0x180015861  test    rax, rax
0x180015864  jz      loc_180015A9B
0x18001586a  mov     rcx, rax; pbstr
0x18001586d  call    cs:__imp_SysStringLen
0x180015873  test    eax, eax
0x180015875  jz      short loc_18001588B
0x180015877  mov     rcx, rbx; pbstr
0x18001587a  call    cs:__imp_SysStringLen
0x180015880  mov     edx, eax; cchLength
0x180015882  mov     rcx, rbx; lpsz
0x180015885  call    cs:__imp_CharLowerBuffW
0x18001588b  lea     rax, [rsi+398h]
0x180015892  mov     [rbp+57h+var_88], rax
0x180015896  xorps   xmm0, xmm0
0x180015899  movups  [rbp+57h+var_60], xmm0
0x18001589d  xorps   xmm1, xmm1
0x1800158a0  movdqu  [rbp+57h+var_50], xmm1
0x1800158a5  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800158a9  mov     r8, r14
0x1800158ac  xor     eax, eax
0x1800158ae  inc     r8
0x1800158b1  cmp     [rbx+r8*2], ax
0x1800158b6  jnz     short loc_1800158AE
0x1800158b8  mov     rdx, rbx
0x1800158bb  lea     rcx, [rbp+57h+var_60]
0x1800158bf  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800158c4  lea     rdx, [rbp+57h+var_60]
0x1800158c8  call    ??R?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@QEBA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_compare<std::wstring,std::less<std::wstring>>::operator()(std::wstring const &)
0x1800158cd  mov     r9, rax
0x1800158d0  lea     r8, [rbp+57h+var_60]
0x1800158d4  lea     rdx, [rbp+57h+var_98]
0x1800158d8  lea     rcx, [rsi+398h]
0x1800158df  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCRegistration@@@2@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCRegistration@@@2@@std@@@2@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCRegistration@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<stdext::_Hmap_traits<std::wstring,std::shared_ptr<CRegistration>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<CRegistration>>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x1800158e4  mov     rax, [rax+8]
0x1800158e8  mov     [rbp+57h+var_98], rax
0x1800158ec  test    rax, rax
0x1800158ef  jnz     short loc_1800158FC
0x1800158f1  mov     rax, [rsi+3A0h]
0x1800158f8  mov     [rbp+57h+var_98], rax
0x1800158fc  mov     rsi, [rsi+3A0h]
0x180015903  lea     rcx, [rbp+57h+var_60]; void *
0x180015907  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001590c  cmp     [rbp+57h+var_98], rsi
0x180015910  jz      short loc_180015972
0x180015912  xorps   xmm0, xmm0
0x180015915  movups  [rbp+57h+var_60], xmm0
0x180015919  xorps   xmm1, xmm1
0x18001591c  movdqu  [rbp+57h+var_50], xmm1
0x180015921  mov     r8, r14
0x180015924  xor     eax, eax
0x180015926  inc     r8
0x180015929  cmp     [rbx+r8*2], ax
0x18001592e  jnz     short loc_180015926
0x180015930  mov     rdx, rbx
0x180015933  lea     rcx, [rbp+57h+var_60]
0x180015937  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001593c  nop
0x18001593d  lea     rdx, [rbp+57h+var_60]
0x180015941  mov     rcx, [rbp+57h+var_88]
0x180015945  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CComPtr@UISmsDevice@@@ATL@@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CComPtr@UISmsDevice@@@ATL@@@std@@@2@@stdext@@QEAAAEAV?$CComPtr@UISmsDevice@@@ATL@@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_map<std::wstring,ATL::CComPtr<ISmsDevice>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,ATL::CComPtr<ISmsDevice>>>>::operator[](std::wstring &&)
0x18001594a  mov     rsi, [rax]
0x18001594d  test    rsi, rsi
0x180015950  jz      short loc_180015968
0x180015952  mov     rax, [rsi]
0x180015955  mov     rcx, rsi
0x180015958  mov     rax, [rax+8]
0x18001595c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015961  mov     rdi, rsi
0x180015964  mov     [rbp+57h+var_80], rsi
0x180015968  lea     rcx, [rbp+57h+var_60]; void *
0x18001596c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015971  nop
0x180015972  mov     rcx, rbx; bstrString
0x180015975  call    cs:__imp_SysFreeString
0x18001597b  nop
0x18001597c  mov     rax, [r12]
0x180015980  mov     rcx, r12
0x180015983  mov     rax, [rax+8]
0x180015987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001598c  nop
0x18001598d  xor     ebx, ebx
0x18001598f  test    rdi, rdi
0x180015992  jz      loc_180015A41
0x180015998  mov     rax, [rdi]
0x18001599b  lea     rdx, [rbp+57h+Src]
0x18001599f  mov     rcx, rdi
0x1800159a2  mov     rax, [rax+50h]
0x1800159a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159ab  mov     r12d, eax
0x1800159ae  test    eax, eax
0x1800159b0  jns     short loc_1800159D4
0x1800159b2  mov     [rsp+0D0h+var_B0], r13
0x1800159b7  lea     r9, aGetsmscnumberD; "GetSmscNumber DeviceId: %S failed"
0x1800159be  mov     r8d, eax; int
0x1800159c1  mov     edx, 24Ch; unsigned int
0x1800159c6  lea     rcx, aCsmsserviceman_2; "CSmsServiceManager::GetSmscAddress"
0x1800159cd  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x1800159d2  jmp     short loc_180015A21
0x1800159d4  mov     r9, [rbp+57h+Src]
0x1800159d8  inc     r14
0x1800159db  cmp     [r9+r14*2], bx
0x1800159e0  jnz     short loc_1800159D8
0x1800159e2  cmp     r14, [r15+18h]
0x1800159e6  ja      short loc_180015A15
0x1800159e8  cmp     qword ptr [r15+18h], 7
0x1800159ed  jbe     short loc_1800159F4
0x1800159ef  mov     rsi, [r15]
0x1800159f2  jmp     short loc_1800159F7
0x1800159f4  mov     rsi, r15
0x1800159f7  mov     [r15+10h], r14
0x1800159fb  lea     rbx, [r14+r14]
0x1800159ff  mov     r8, rbx; Size
0x180015a02  mov     rdx, r9; Src
0x180015a05  mov     rcx, rsi; void *
0x180015a08  call    memmove_0
0x180015a0d  xor     eax, eax
0x180015a0f  mov     [rbx+rsi], ax
0x180015a13  jmp     short loc_180015A21
0x180015a15  mov     rdx, r14
0x180015a18  mov     rcx, r15
0x180015a1b  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180015a20  nop
0x180015a21  mov     rcx, [rbp+57h+Src]; bstrString
0x180015a25  call    cs:__imp_SysFreeString
0x180015a2b  nop
0x180015a2c  mov     rax, [rdi]
0x180015a2f  mov     rcx, rdi
0x180015a32  mov     rax, [rax+10h]
0x180015a36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a3b  nop
0x180015a3c  mov     eax, r12d
0x180015a3f  jmp     short loc_180015A74
0x180015a41  mov     [rsp+0D0h+var_B0], r13
0x180015a46  lea     r9, aSmsdeviceNotFo; "SmsDevice not found for DeviceId: %S"
0x180015a4d  mov     ebx, 80070490h
0x180015a52  mov     r8d, ebx; int
0x180015a55  mov     edx, 245h; unsigned int
0x180015a5a  lea     rcx, aCsmsserviceman_2; "CSmsServiceManager::GetSmscAddress"
0x180015a61  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180015a66  nop
0x180015a67  mov     rcx, [rbp+57h+Src]; bstrString
0x180015a6b  call    cs:__imp_SysFreeString
0x180015a71  nop
0x180015a72  mov     eax, ebx
0x180015a74  mov     rcx, [rbp+57h+var_40]
0x180015a78  xor     rcx, rsp; StackCookie
0x180015a7b  call    __security_check_cookie
0x180015a80  mov     rbx, [rsp+0D0h+arg_18]
0x180015a88  add     rsp, 0A0h
0x180015a8f  pop     r15
0x180015a91  pop     r14
0x180015a93  pop     r13
0x180015a95  pop     r12
0x180015a97  pop     rdi
0x180015a98  pop     rsi
0x180015a99  pop     rbp
0x180015a9a  retn
0x180015a9b  mov     ecx, 8007000Eh; int
0x180015aa0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
