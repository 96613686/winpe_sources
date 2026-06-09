# CMapiSupport::GetMatchingRule(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSupport::ProviderRuleT &)

- ea: `0x180031594`
- end: `0x180031819`
- name: `?GetMatchingRule@CMapiSupport@@CAJV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@00AEAUProviderRuleT@1@@Z`
- size: `645`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180031c4c`

## callees

- `0x18000bf84`
- `0x18000c8a0`
- `0x18000e658`
- `0x18000e684`
- `0x18000e6e0`
- `0x18000ee70`
- `0x180011884`
- `0x180023a30`
- `0x1800302ac`
- `0x180030324`
- `0x180030a10`
- `0x180031594`
- `0x1800318c4`

## string_xrefs

- `0x1800315f2`: `Software\Microsoft\Windows Search\Gather\Windows\SystemIndex\Protocols\Mapi\ProviderRules\`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CMapiSupport::GetMatchingRule(
        const void **a1,
        _QWORD *a2,
        _QWORD *a3,
        struct CMapiSupport::ProviderRuleT *a4)
{
  _QWORD *v7; // rax
  __int64 v8; // r13
  _QWORD *v9; // rax
  unsigned int v10; // r12d
  int ProviderRule; // r14d
  int v12; // edi
  unsigned int v13; // esi
  __int64 v14; // rax
  __int64 v15; // rax
  _QWORD *v16; // rax
  __int64 v17; // rbx
  _QWORD *v18; // rax
  __int64 v19; // rax
  _QWORD *v20; // rax
  __int64 v21; // rbx
  _QWORD *v22; // rax
  __int64 v23; // rax
  LPCWSTR lpSubKey; // [rsp+28h] [rbp-49h] BYREF
  __int64 v26; // [rsp+30h] [rbp-41h] BYREF
  __int64 v27; // [rsp+38h] [rbp-39h] BYREF
  __int64 v28; // [rsp+40h] [rbp-31h]
  _QWORD v29[3]; // [rsp+50h] [rbp-21h] BYREF
  __int64 v30; // [rsp+68h] [rbp-9h] BYREF
  __int64 v31; // [rsp+70h] [rbp-1h] BYREF
  __int64 v32; // [rsp+78h] [rbp+7h] BYREF
  __int64 v33; // [rsp+80h] [rbp+Fh] BYREF
  __int64 v34; // [rsp+88h] [rbp+17h] BYREF
  _QWORD v35[7]; // [rsp+90h] [rbp+1Fh] BYREF

  v7 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
         &lpSubKey,
         a2);
  v8 = CMapiSupport::ConvertToIntVersion(v7);
  v9 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
         &lpSubKey,
         a3);
  v28 = CMapiSupport::ConvertToIntVersion(v9);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    (__int64)&v27,
    L"Software\\Microsoft\\Windows Search\\Gather\\Windows\\SystemIndex\\Protocols\\Mapi\\ProviderRules\\");
  ATL::CSimpleStringT<wchar_t,0>::Append(&v27, *a1, *((unsigned int *)*a1 - 4));
  v10 = 0;
  ProviderRule = 0;
  v12 = 0;
  v13 = 1;
  while ( !ProviderRule )
  {
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)&v26);
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Format(&v26, L"%d", v10);
    v14 = ATL::operator+(&v31, &v27, L"\\");
    v15 = ATL::operator+(&v30, v14, L"Rule");
    ATL::operator+(&lpSubKey, v15, &v26);
    ATL::CStringData::Release((ATL::CStringData *)(v30 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v31 - 24));
    memset(v29, 0, sizeof(v29));
    ProviderRule = ATL::CRegKey::Open((ATL::CRegKey *)v29, HKEY_CURRENT_USER, lpSubKey, 0x20019u);
    if ( !ProviderRule )
    {
      ProviderRule = CMapiSupport::GetProviderRule((struct ATL::CRegKey *)v29, a4);
      if ( !ProviderRule )
      {
        v16 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
                &v32,
                (_QWORD *)a4 + 2);
        v17 = CMapiSupport::ConvertToIntVersion(v16);
        v18 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
                &v33,
                (_QWORD *)a4 + 3);
        v19 = CMapiSupport::ConvertToIntVersion(v18);
        if ( !v19 )
          v19 = 0x7FFFFFFFFFFFFFFFLL;
        if ( v8 >= v17 && v8 < v19 )
        {
          v20 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
                  &v34,
                  a4);
          v21 = CMapiSupport::ConvertToIntVersion(v20);
          v22 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
                  v35,
                  (_QWORD *)a4 + 1);
          v23 = CMapiSupport::ConvertToIntVersion(v22);
          if ( !v23 )
            v23 = 0x7FFFFFFFFFFFFFFFLL;
          if ( v28 >= v21 && v28 < v23 )
            v12 = 1;
        }
      }
      ATL::CRegKey::Close((ATL::CRegKey *)v29);
    }
    ++v10;
    ATL::CRegKey::Close((ATL::CRegKey *)v29);
    ATL::CStringData::Release((ATL::CStringData *)(lpSubKey - 12));
    ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
    if ( v12 )
    {
      v13 = 0;
      break;
    }
  }
  ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
  ATL::CStringData::Release((ATL::CStringData *)((char *)*a1 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(*a2 - 24LL));
  ATL::CStringData::Release((ATL::CStringData *)(*a3 - 24LL));
  return v13;
}

```

## disassembly

```asm
0x180031594  mov     rax, rsp
0x180031597  mov     [rax+20h], rbx
0x18003159b  mov     [rax+18h], r8
0x18003159f  mov     [rax+10h], rdx
0x1800315a3  mov     [rax+8], rcx
0x1800315a7  push    rbp
0x1800315a8  push    rsi
0x1800315a9  push    rdi
0x1800315aa  push    r12
0x1800315ac  push    r13
0x1800315ae  push    r14
0x1800315b0  push    r15
0x1800315b2  lea     rbp, [rax-5Fh]
0x1800315b6  sub     rsp, 90h
0x1800315bd  mov     r15, r9
0x1800315c0  mov     rbx, r8
0x1800315c3  mov     rdi, rcx
0x1800315c6  lea     rcx, [rbp+57h+lpSubKey]
0x1800315ca  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x1800315cf  mov     rcx, rax
0x1800315d2  call    ?ConvertToIntVersion@CMapiSupport@@SA_JV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiSupport::ConvertToIntVersion(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>)
0x1800315d7  mov     r13, rax
0x1800315da  mov     rdx, rbx
0x1800315dd  lea     rcx, [rbp+57h+lpSubKey]
0x1800315e1  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x1800315e6  mov     rcx, rax
0x1800315e9  call    ?ConvertToIntVersion@CMapiSupport@@SA_JV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiSupport::ConvertToIntVersion(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>)
0x1800315ee  mov     [rbp+57h+var_88], rax
0x1800315f2  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows Search\\Ga"...
0x1800315f9  lea     rcx, [rbp+57h+var_90]
0x1800315fd  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@PEB_W@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(wchar_t const *)
0x180031602  nop
0x180031603  mov     rdx, [rdi]
0x180031606  mov     r8d, [rdx-10h]
0x18003160a  lea     rcx, [rbp+57h+var_90]
0x18003160e  call    ?Append@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::Append(wchar_t const *,int)
0x180031613  xor     r12d, r12d
0x180031616  xor     r14d, r14d
0x180031619  xor     edi, edi
0x18003161b  lea     esi, [rdi+1]
0x18003161e  test    r14d, r14d
0x180031621  jnz     loc_1800317BC
0x180031627  lea     rcx, [rbp+57h+var_98]
0x18003162b  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180031630  nop
0x180031631  mov     r8d, r12d
0x180031634  lea     rdx, aD; "%d"
0x18003163b  lea     rcx, [rbp+57h+var_98]
0x18003163f  call    ?Format@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAXPEB_WZZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Format(wchar_t const *,...)
0x180031644  lea     r8, asc_1800444B8; "\\"
0x18003164b  lea     rdx, [rbp+57h+var_90]
0x18003164f  lea     rcx, [rbp+57h+var_58]
0x180031653  call    ??HATL@@YA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@0@AEBV10@PEB_W@Z; ATL::operator+(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &,wchar_t const *)
0x180031658  nop
0x180031659  lea     r8, aRule; "Rule"
0x180031660  mov     rdx, rax
0x180031663  lea     rcx, [rbp+57h+var_60]
0x180031667  call    ??HATL@@YA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@0@AEBV10@PEB_W@Z; ATL::operator+(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &,wchar_t const *)
0x18003166c  nop
0x18003166d  lea     r8, [rbp+57h+var_98]
0x180031671  mov     rdx, rax
0x180031674  lea     rcx, [rbp+57h+lpSubKey]
0x180031678  call    ??HATL@@YA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@0@AEBV10@0@Z; ATL::operator+(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x18003167d  nop
0x18003167e  mov     rcx, [rbp+57h+var_60]
0x180031682  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180031686  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003168b  nop
0x18003168c  mov     rcx, [rbp+57h+var_58]
0x180031690  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180031694  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180031699  mov     [rbp+57h+var_78], 0
0x1800316a1  mov     [rbp+57h+var_70], 0
0x1800316a9  mov     [rbp+57h+var_68], 0
0x1800316b1  mov     r9d, 20019h; unsigned int
0x1800316b7  mov     r8, [rbp+57h+lpSubKey]; lpSubKey
0x1800316bb  mov     rdx, 0FFFFFFFF80000001h; hKey
0x1800316c2  lea     rcx, [rbp+57h+var_78]; this
0x1800316c6  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x1800316cb  mov     r14d, eax
0x1800316ce  test    eax, eax
0x1800316d0  jnz     loc_18003178A
0x1800316d6  mov     rdx, r15; struct CMapiSupport::ProviderRuleT *
0x1800316d9  lea     rcx, [rbp+57h+var_78]; this
0x1800316dd  call    ?GetProviderRule@CMapiSupport@@CAJAEAVCRegKey@ATL@@AEAUProviderRuleT@1@@Z; CMapiSupport::GetProviderRule(ATL::CRegKey &,CMapiSupport::ProviderRuleT &)
0x1800316e2  mov     r14d, eax
0x1800316e5  test    eax, eax
0x1800316e7  jnz     loc_180031781
0x1800316ed  lea     rdx, [r15+10h]
0x1800316f1  lea     rcx, [rbp+57h+var_50]
0x1800316f5  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x1800316fa  mov     rcx, rax
0x1800316fd  call    ?ConvertToIntVersion@CMapiSupport@@SA_JV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiSupport::ConvertToIntVersion(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>)
0x180031702  mov     rbx, rax
0x180031705  lea     rdx, [r15+18h]
0x180031709  lea     rcx, [rbp+57h+var_48]
0x18003170d  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x180031712  mov     rcx, rax
0x180031715  call    ?ConvertToIntVersion@CMapiSupport@@SA_JV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiSupport::ConvertToIntVersion(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>)
0x18003171a  test    rax, rax
0x18003171d  mov     rcx, 7FFFFFFFFFFFFFFFh
0x180031727  cmovz   rax, rcx
0x18003172b  cmp     r13, rbx
0x18003172e  jl      short loc_180031781
0x180031730  cmp     r13, rax
0x180031733  jge     short loc_180031781
0x180031735  mov     rdx, r15
0x180031738  lea     rcx, [rbp+57h+var_40]
0x18003173c  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x180031741  mov     rcx, rax
0x180031744  call    ?ConvertToIntVersion@CMapiSupport@@SA_JV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiSupport::ConvertToIntVersion(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>)
0x180031749  mov     rbx, rax
0x18003174c  lea     rdx, [r15+8]
0x180031750  lea     rcx, [rbp+57h+var_38]
0x180031754  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x180031759  mov     rcx, rax
0x18003175c  call    ?ConvertToIntVersion@CMapiSupport@@SA_JV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiSupport::ConvertToIntVersion(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>)
0x180031761  test    rax, rax
0x180031764  mov     rcx, 7FFFFFFFFFFFFFFFh
0x18003176e  cmovz   rax, rcx
0x180031772  mov     rcx, [rbp+57h+var_88]
0x180031776  cmp     rcx, rbx
0x180031779  jl      short loc_180031781
0x18003177b  cmp     rcx, rax
0x18003177e  cmovl   edi, esi
0x180031781  lea     rcx, [rbp+57h+var_78]; this
0x180031785  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003178a  add     r12d, esi
0x18003178d  lea     rcx, [rbp+57h+var_78]; this
0x180031791  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180031796  nop
0x180031797  mov     rcx, [rbp+57h+lpSubKey]
0x18003179b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18003179f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800317a4  nop
0x1800317a5  mov     rcx, [rbp+57h+var_98]
0x1800317a9  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800317ad  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800317b2  test    edi, edi
0x1800317b4  jz      loc_18003161E
0x1800317ba  xor     esi, esi
0x1800317bc  mov     rcx, [rbp+57h+var_90]
0x1800317c0  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800317c4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800317c9  nop
0x1800317ca  mov     rcx, [rbp+57h+arg_0]
0x1800317ce  mov     rcx, [rcx]
0x1800317d1  sub     rcx, 18h; this
0x1800317d5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800317da  nop
0x1800317db  mov     rcx, [rbp+57h+arg_8]
0x1800317df  mov     rcx, [rcx]
0x1800317e2  sub     rcx, 18h; this
0x1800317e6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800317eb  nop
0x1800317ec  mov     rcx, [rbp+57h+arg_10]
0x1800317f0  mov     rcx, [rcx]
0x1800317f3  sub     rcx, 18h; this
0x1800317f7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800317fc  mov     eax, esi
0x1800317fe  mov     rbx, [rsp+0C0h+arg_18]
0x180031806  add     rsp, 90h
0x18003180d  pop     r15
0x18003180f  pop     r14
0x180031811  pop     r13
0x180031813  pop     r12
0x180031815  pop     rdi
0x180031816  pop     rsi
0x180031817  pop     rbp
0x180031818  retn
```
