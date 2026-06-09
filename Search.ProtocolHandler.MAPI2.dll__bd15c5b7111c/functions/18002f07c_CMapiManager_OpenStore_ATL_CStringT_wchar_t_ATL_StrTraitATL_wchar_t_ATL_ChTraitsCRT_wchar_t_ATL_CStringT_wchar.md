# CMapiManager::OpenStore(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &,CMapiStore * *)

- ea: `0x18002f07c`
- end: `0x18002f1ea`
- name: `?OpenStore@CMapiManager@@QEAAJAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@0PEAPEAVCMapiStore@@@Z`
- size: `366`
- prototype: `__int64 __fastcall(CMapiManager *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015970`

## callees

- `0x180004c20`
- `0x18000ad14`
- `0x18000fd58`
- `0x1800113ac`
- `0x18002d048`
- `0x18002d270`
- `0x18002dd9c`
- `0x18002dffc`
- `0x18002e7a4`
- `0x18002e890`
- `0x18002f07c`
- `0x1800361f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f0bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f0bb`

## string_xrefs

- `0x18002f1a1`: `OpenStore() failed since we got MAPI_E_FAILEDONEPROVIDER probably because MAPI can't get the address book`
- `0x18002f1b9`: `OpenStore() failed. Returning MAPI_E_NOT_FOUND`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMapiManager::OpenStore(
        CMapiManager *this,
        const wchar_t **a2,
        const wchar_t **a3,
        struct CMapiStore **a4)
{
  const wchar_t *v9; // r8
  const wchar_t *v10; // r9
  const wchar_t *v11; // rdx
  int Session; // ebx
  _QWORD *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  const wchar_t *v16; // r9
  _QWORD *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // [rsp+20h] [rbp-10h] BYREF
  struct _RTL_CRITICAL_SECTION *v20; // [rsp+28h] [rbp-8h] BYREF
  struct CMapiSession *v21; // [rsp+68h] [rbp+38h] BYREF

  if ( !a4 )
    return 2147942487LL;
  *a4 = 0;
  v20 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v11 = *a2;
  if ( *((_DWORD *)*a2 - 4) )
  {
    v21 = 0;
    Session = CMapiManager::GetSession(this, v11, v9, &v21);
    if ( Session >= 0 )
      Session = CMapiSession::OpenStore((struct _RTL_CRITICAL_SECTION *)v21, *a3, a4);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v21);
  }
  else
  {
    v19 = 0;
    v13 = TPointer<ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>>::operator&(
            &v19,
            (__int64)v11,
            (__int64)v9,
            v10);
    Session = CMapiManager::GetOpenProfiles(this, v13);
    if ( Session >= 0 )
    {
      v14 = v19;
      if ( v19 )
        CMapiManager::FindStore(this, v19, a3, a4);
    }
    if ( !*a4 )
    {
      v21 = 0;
      v17 = TPointer<ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>>::operator&(
              &v21,
              v14,
              v15,
              v16);
      Session = CMapiManager::GetAllProfiles(v18, v17);
      if ( Session >= 0 && v21 )
        Session = CMapiManager::FindStore(this, (__int64)v21, a3, a4);
      TPointer<ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>>::~TPointer<ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>>(&v21);
    }
    TPointer<ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>>::~TPointer<ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>>(&v19);
  }
  if ( !*a4 )
  {
    if ( Session == -2147221219 )
    {
      Session = -2147216890;
      CLogger::Info(
        -2147216890,
        L"OpenStore() failed since we got MAPI_E_FAILEDONEPROVIDER probably because MAPI can't get the address book");
    }
    else if ( Session != -2147216890 )
    {
      CLogger::Error((unsigned int)Session, L"OpenStore() failed. Returning MAPI_E_NOT_FOUND");
      Session = -2147221233;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v20);
  return (unsigned int)Session;
}

```

## disassembly

```asm
0x18002f07c  mov     [rsp-18h+arg_0], rbx
0x18002f081  mov     [rsp-18h+arg_8], rsi
0x18002f086  push    rbp
0x18002f087  push    rdi
0x18002f088  push    r14
0x18002f08a  mov     rbp, rsp
0x18002f08d  sub     rsp, 30h
0x18002f091  mov     rdi, r9
0x18002f094  mov     r14, r8
0x18002f097  mov     rbx, rdx
0x18002f09a  mov     rsi, rcx
0x18002f09d  test    r9, r9
0x18002f0a0  jnz     short loc_18002F0AC
0x18002f0a2  mov     eax, 80070057h
0x18002f0a7  jmp     loc_18002F1D7
0x18002f0ac  mov     qword ptr [r9], 0
0x18002f0b3  add     rcx, 58h ; 'X'; lpCriticalSection
0x18002f0b7  mov     [rbp+var_8], rcx
0x18002f0bb  call    cs:__imp_EnterCriticalSection
0x18002f0c1  nop
0x18002f0c2  mov     rdx, [rbx]; wchar_t *
0x18002f0c5  cmp     dword ptr [rdx-10h], 0
0x18002f0c9  jz      short loc_18002F104
0x18002f0cb  mov     [rbp+arg_18], 0
0x18002f0d3  lea     r9, [rbp+arg_18]; struct CMapiSession **
0x18002f0d7  mov     rcx, rsi; this
0x18002f0da  call    ?GetSession@CMapiManager@@QEAAJPEB_W0PEAPEAVCMapiSession@@@Z; CMapiManager::GetSession(wchar_t const *,wchar_t const *,CMapiSession * *)
0x18002f0df  mov     ebx, eax
0x18002f0e1  test    eax, eax
0x18002f0e3  js      short loc_18002F0F6
0x18002f0e5  mov     r8, rdi; struct CMapiStore **
0x18002f0e8  mov     rdx, [r14]; wchar_t *
0x18002f0eb  mov     rcx, [rbp+arg_18]; this
0x18002f0ef  call    ?OpenStore@CMapiSession@@QEAAJPEB_WPEAPEAVCMapiStore@@H@Z; CMapiSession::OpenStore(wchar_t const *,CMapiStore * *,int)
0x18002f0f4  mov     ebx, eax
0x18002f0f6  lea     rcx, [rbp+arg_18]
0x18002f0fa  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002f0ff  jmp     loc_18002F18E
0x18002f104  mov     [rbp+var_10], 0
0x18002f10c  lea     rcx, [rbp+var_10]
0x18002f110  call    ??I?$TPointer@V?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@@@QEAAPEAPEAV?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@XZ; TPointer<ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>>::operator&(void)
0x18002f115  mov     rdx, rax
0x18002f118  mov     rcx, rsi
0x18002f11b  call    ?GetOpenProfiles@CMapiManager@@QEAAJPEAPEAV?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z; CMapiManager::GetOpenProfiles(ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>> * *)
0x18002f120  mov     ebx, eax
0x18002f122  test    eax, eax
0x18002f124  js      short loc_18002F13D
0x18002f126  mov     rdx, [rbp+var_10]
0x18002f12a  test    rdx, rdx
0x18002f12d  jz      short loc_18002F13D
0x18002f12f  mov     r9, rdi
0x18002f132  mov     r8, r14
0x18002f135  mov     rcx, rsi; this
0x18002f138  call    ?FindStore@CMapiManager@@AEAAJAEAV?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@AEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@3@PEAPEAVCMapiStore@@@Z; CMapiManager::FindStore(ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>> &,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &,CMapiStore * *)
0x18002f13d  cmp     qword ptr [rdi], 0
0x18002f141  jnz     short loc_18002F185
0x18002f143  mov     [rbp+arg_18], 0
0x18002f14b  lea     rcx, [rbp+arg_18]
0x18002f14f  call    ??I?$TPointer@V?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@@@QEAAPEAPEAV?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@XZ; TPointer<ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>>::operator&(void)
0x18002f154  mov     rdx, rax
0x18002f157  call    ?GetAllProfiles@CMapiManager@@QEAAJPEAPEAV?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z; CMapiManager::GetAllProfiles(ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>> * *)
0x18002f15c  mov     ebx, eax
0x18002f15e  test    eax, eax
0x18002f160  js      short loc_18002F17B
0x18002f162  mov     rdx, [rbp+arg_18]
0x18002f166  test    rdx, rdx
0x18002f169  jz      short loc_18002F17B
0x18002f16b  mov     r9, rdi
0x18002f16e  mov     r8, r14
0x18002f171  mov     rcx, rsi; this
0x18002f174  call    ?FindStore@CMapiManager@@AEAAJAEAV?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@AEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@3@PEAPEAVCMapiStore@@@Z; CMapiManager::FindStore(ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>> &,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &,CMapiStore * *)
0x18002f179  mov     ebx, eax
0x18002f17b  lea     rcx, [rbp+arg_18]
0x18002f17f  call    ??1?$TPointer@V?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@@@QEAA@XZ; TPointer<ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>>::~TPointer<ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>>(void)
0x18002f184  nop
0x18002f185  lea     rcx, [rbp+var_10]
0x18002f189  call    ??1?$TPointer@V?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@@@QEAA@XZ; TPointer<ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>>::~TPointer<ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>>(void)
0x18002f18e  cmp     qword ptr [rdi], 0
0x18002f192  jnz     short loc_18002F1CC
0x18002f194  cmp     ebx, 8004011Dh
0x18002f19a  jnz     short loc_18002F1B1
0x18002f19c  mov     ebx, 80041206h
0x18002f1a1  lea     rdx, aOpenstoreFaile_0; "OpenStore() failed since we got MAPI_E_"...
0x18002f1a8  mov     ecx, ebx; int
0x18002f1aa  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x18002f1af  jmp     short loc_18002F1CC
0x18002f1b1  cmp     ebx, 80041206h
0x18002f1b7  jz      short loc_18002F1CC
0x18002f1b9  lea     rdx, aOpenstoreFaile; "OpenStore() failed. Returning MAPI_E_NO"...
0x18002f1c0  mov     ecx, ebx; int
0x18002f1c2  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x18002f1c7  mov     ebx, 8004010Fh
0x18002f1cc  lea     rcx, [rbp+var_8]
0x18002f1d0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002f1d5  mov     eax, ebx
0x18002f1d7  mov     rbx, [rsp+30h+arg_0]
0x18002f1dc  mov     rsi, [rsp+30h+arg_8]
0x18002f1e1  add     rsp, 30h
0x18002f1e5  pop     r14
0x18002f1e7  pop     rdi
0x18002f1e8  pop     rbp
0x18002f1e9  retn
```
