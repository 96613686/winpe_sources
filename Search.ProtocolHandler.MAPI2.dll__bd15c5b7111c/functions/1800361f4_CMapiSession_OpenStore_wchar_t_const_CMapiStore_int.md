# CMapiSession::OpenStore(wchar_t const *,CMapiStore * *,int)

- ea: `0x1800361f4`
- end: `0x180036646`
- name: `?OpenStore@CMapiSession@@QEAAJPEB_WPEAPEAVCMapiStore@@H@Z`
- size: `1106`
- prototype: `__int64 __fastcall(CMapiSession *__hidden this, const wchar_t *, struct CMapiStore **, int)`
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x18002dd9c`
- `0x18002f07c`

## callees

- `0x180002300`
- `0x18000ad14`
- `0x18000e684`
- `0x18000e6e0`
- `0x1800113ac`
- `0x180011884`
- `0x18002bc3c`
- `0x180034578`
- `0x18003583c`
- `0x180035af8`
- `0x180035e68`
- `0x1800361f4`
- `0x18003664c`
- `0x180036b6c`
- `0x180036f0c`
- `0x180036f80`
- `0x1800377b0`
- `0x18003f010`

## import_xrefs

- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_FreeProws` at `0x1800365b6`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_FreeProws` at `0x1800365b6`

## string_xrefs

- `0x1800362da`: `OpenStore() because the store is disabled in classic mode (online or offline)`
- `0x1800362f8`: `OpenStore() because the store is disabled in classic mode (online or offline)`
- `0x1800365cf`: `CMapiSession::OpenStore at least one instance of the store was found but was unavailable`
- `0x180036518`: `OpenStore() will fail because Exchange online is disabled`
- `0x180036569`: `CMapiSession::OpenStore Found delegate store but it not available`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CMapiSession::OpenStore(
        struct _RTL_CRITICAL_SECTION *this,
        const wchar_t *a2,
        struct CMapiStore **a3)
{
  int v5; // r13d
  __int64 CachedStore; // rax
  int v8; // ebx
  struct CMapiStore *v9; // rax
  unsigned int v10; // edi
  __int64 v11; // rdx
  int v12; // r12d
  __int64 v13; // rax
  LPSPropValue lpProps; // r13
  __int64 v15; // rdx
  int v16; // ecx
  unsigned __int16 *v17; // [rsp+30h] [rbp-99h] BYREF
  unsigned int v18; // [rsp+38h] [rbp-91h] BYREF
  int v19; // [rsp+3Ch] [rbp-8Dh]
  __int64 v20; // [rsp+40h] [rbp-89h] BYREF
  LPSRowSet lpRows; // [rsp+48h] [rbp-81h] BYREF
  __int64 v22; // [rsp+50h] [rbp-79h] BYREF
  __int64 v23; // [rsp+58h] [rbp-71h] BYREF
  LPBYTE lpb; // [rsp+60h] [rbp-69h]
  unsigned int v25[12]; // [rsp+70h] [rbp-59h] BYREF
  int v26; // [rsp+A0h] [rbp-29h]
  int DebugInfo_high; // [rsp+A8h] [rbp-21h]
  unsigned __int16 *v28; // [rsp+C0h] [rbp-9h] BYREF
  _DWORD v29[4]; // [rsp+D0h] [rbp+7h] BYREF

  v5 = 0;
  if ( !this->LockSemaphore )
    return 2147500037LL;
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    (__int64)&v17,
    a2);
  CachedStore = CMapiSession::FindCachedStore(this, &v17);
  *a3 = (struct CMapiStore *)CachedStore;
  if ( CachedStore )
  {
    if ( *(_QWORD *)(CachedStore + 48) || !*(_DWORD *)(CachedStore + 128) )
    {
      if ( *(_DWORD *)(CachedStore + 116) )
      {
        *a3 = 0;
        v10 = -2147216890;
        CLogger::Info(-2147216890, L"OpenStore() because the store is disabled in classic mode (online or offline)");
      }
      else
      {
        v10 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)CachedStore + 8LL))(CachedStore);
      }
LABEL_15:
      ATL::CStringData::Release((ATL::CStringData *)(v17 - 12));
      return v10;
    }
    *a3 = 0;
  }
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)&v23);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)&v22);
  v8 = CMapiStore::LookupHash(&v17, &v23, &v22);
  if ( v8 )
  {
    if ( !(unsigned int)CMapiSession::OpenAllStores((CMapiSession *)this) )
    {
      v9 = (struct CMapiStore *)CMapiSession::FindCachedStore(this, &v17);
      *a3 = v9;
      if ( v9 )
      {
        if ( *((_DWORD *)v9 + 29) )
        {
          *a3 = 0;
          v10 = -2147216890;
          CLogger::Info(-2147216890, L"OpenStore() because the store is disabled in classic mode (online or offline)");
        }
        else
        {
          v10 = 0;
          (*(void (__fastcall **)(struct CMapiStore *))(*(_QWORD *)v9 + 8LL))(v9);
        }
        ATL::CStringData::Release((ATL::CStringData *)(v22 - 24));
        ATL::CStringData::Release((ATL::CStringData *)(v23 - 24));
        goto LABEL_15;
      }
    }
    if ( v8 >= 0 )
      v8 = -2147467259;
  }
  else
  {
    v29[0] = 2;
    v29[1] = 268370178;
    v29[2] = 873726210;
    v20 = 0;
    v8 = (*(__int64 (__fastcall **)(HANDLE, _QWORD, __int64 *))(*(_QWORD *)this->LockSemaphore + 32LL))(
           this->LockSemaphore,
           0,
           &v20);
    if ( v8 >= 0 )
      v8 = (*(__int64 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)v20 + 56LL))(v20, v29, 2);
    v11 = 0;
    v18 = 0;
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v20 + 72LL))(v20, 0, &v18);
      v11 = v18;
      if ( v18 > 0x64 )
      {
        v11 = 100;
        v18 = 100;
      }
    }
    lpRows = 0;
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, LPSRowSet *))(*(_QWORD *)v20 + 152LL))(
             v20,
             v11,
             0,
             &lpRows);
      if ( v8 >= 0 )
      {
        v12 = 0;
        v13 = 0;
        while ( 1 )
        {
          v19 = v13;
          if ( (unsigned int)v13 >= lpRows->cRows )
            break;
          lpProps = lpRows->aRow[v13].lpProps;
          if ( lpProps[1].ulPropTag == 873726210 )
            lpb = lpProps[1].Value.bin.lpb;
          else
            lpb = 0;
          if ( lpProps->ulPropTag == 268370178 )
          {
            CStoreEntryId::CStoreEntryId((CStoreEntryId *)v25);
            DebugInfo_high = HIDWORD(this[4].DebugInfo);
            v8 = CStoreEntryId::InitializeWithHint(
                   (unsigned int)v25,
                   this->LockSemaphore,
                   (_DWORD)lpb,
                   (_DWORD)lpProps,
                   (__int64)&v17);
            if ( v8 < 0 )
            {
              v8 = 0;
            }
            else if ( v26
                   || !(unsigned int)ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Compare(
                                       &v28,
                                       (__int64)v17) )
            {
              v5 = 1;
              CMapiSession::ReleaseStore(this, &v17);
              v8 = CMapiSession::OpenStoreInternal((__int64)this, v25, a3, 0, 0);
              if ( v8 )
              {
                if ( v8 >= 0 )
                  v8 = -2147467259;
              }
              else
              {
                v15 = (__int64)*a3;
                if ( *((_DWORD *)*a3 + 29) )
                {
                  *a3 = 0;
                  v8 = -2147216890;
                  CLogger::Info(-2147216890, L"OpenStore() will fail because Exchange online is disabled");
                }
                else
                {
                  if ( !v26
                    || v15
                    && !(unsigned int)ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Compare(
                                        &v17,
                                        *(_QWORD *)(v15 + 40)) )
                  {
                    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 8LL))(*a3);
LABEL_53:
                    CStoreEntryId::~CStoreEntryId((CStoreEntryId *)v25);
                    break;
                  }
                  v8 = -2147467259;
                  *a3 = 0;
                }
              }
              if ( !v26 )
                goto LABEL_53;
              if ( (unsigned int)IsSoftError(v8) )
              {
                CLogger::Info(v16, L"CMapiSession::OpenStore Found delegate store but it not available");
                v12 = v8;
              }
            }
            CStoreEntryId::~CStoreEntryId((CStoreEntryId *)v25);
          }
          v13 = (unsigned int)(v19 + 1);
          v5 = 0;
        }
        if ( lpRows )
        {
          FreeProws(lpRows);
          lpRows = 0;
        }
        if ( !v5 )
        {
          if ( v12 >= 0 )
          {
            v8 = -2147221233;
          }
          else
          {
            CLogger::Info(
              v12,
              L"CMapiSession::OpenStore at least one instance of the store was found but was unavailable");
            v8 = v12;
          }
        }
      }
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
  }
  ATL::CStringData::Release((ATL::CStringData *)(v22 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v23 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v17 - 12));
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800361f4  mov     [rsp-8+arg_18], rbx
0x1800361f9  push    rbp
0x1800361fa  push    rsi
0x1800361fb  push    rdi
0x1800361fc  push    r12
0x1800361fe  push    r13
0x180036200  push    r14
0x180036202  push    r15
0x180036204  lea     rbp, [rsp-27h]
0x180036209  sub     rsp, 0F0h
0x180036210  mov     rax, cs:__security_cookie
0x180036217  xor     rax, rsp
0x18003621a  mov     [rbp+57h+var_40], rax
0x18003621e  mov     rsi, r8
0x180036221  mov     r15, rcx
0x180036224  xor     r13d, r13d
0x180036227  cmp     [rcx+18h], r13
0x18003622b  jnz     short loc_180036237
0x18003622d  mov     eax, 80004005h
0x180036232  jmp     loc_18003661F
0x180036237  lea     rcx, [rsp+120h+var_F0]
0x18003623c  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@PEB_W@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(wchar_t const *)
0x180036241  nop
0x180036242  lea     rdx, [rsp+120h+var_F0]
0x180036247  mov     rcx, r15
0x18003624a  call    ?FindCachedStore@CMapiSession@@AEAAPEAVCMapiStore@@AEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiSession::FindCachedStore(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x18003624f  mov     rcx, rax
0x180036252  mov     [rsi], rax
0x180036255  test    rax, rax
0x180036258  jz      short loc_180036270
0x18003625a  cmp     [rax+30h], r13
0x18003625e  jnz     loc_1800362EA
0x180036264  cmp     [rax+80h], r13d
0x18003626b  jz      short loc_1800362EA
0x18003626d  mov     [rsi], r13
0x180036270  lea     rcx, [rbp+57h+var_C8]
0x180036274  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180036279  nop
0x18003627a  lea     rcx, [rbp+57h+var_D0]
0x18003627e  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180036283  nop
0x180036284  lea     r8, [rbp+57h+var_D0]
0x180036288  lea     rdx, [rbp+57h+var_C8]
0x18003628c  lea     rcx, [rsp+120h+var_F0]
0x180036291  call    ?LookupHash@CMapiStore@@SAJAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@00@Z; CMapiStore::LookupHash(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x180036296  mov     ebx, eax
0x180036298  test    eax, eax
0x18003629a  jz      loc_18003636B
0x1800362a0  mov     rcx, r15; this
0x1800362a3  call    ?OpenAllStores@CMapiSession@@QEAAJXZ; CMapiSession::OpenAllStores(void)
0x1800362a8  test    eax, eax
0x1800362aa  jnz     loc_18003635A
0x1800362b0  lea     rdx, [rsp+120h+var_F0]
0x1800362b5  mov     rcx, r15
0x1800362b8  call    ?FindCachedStore@CMapiSession@@AEAAPEAVCMapiStore@@AEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiSession::FindCachedStore(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x1800362bd  mov     rcx, rax
0x1800362c0  mov     [rsi], rax
0x1800362c3  test    rax, rax
0x1800362c6  jz      loc_18003635A
0x1800362cc  cmp     [rax+74h], r13d
0x1800362d0  jz      short loc_18003632D
0x1800362d2  mov     [rsi], r13
0x1800362d5  mov     edi, 80041206h
0x1800362da  lea     rdx, aOpenstoreBecau; "OpenStore() because the store is disabl"...
0x1800362e1  mov     ecx, edi; int
0x1800362e3  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x1800362e8  jmp     short loc_18003633D
0x1800362ea  cmp     [rax+74h], r13d
0x1800362ee  jz      short loc_180036308
0x1800362f0  mov     [rsi], r13
0x1800362f3  mov     edi, 80041206h
0x1800362f8  lea     rdx, aOpenstoreBecau; "OpenStore() because the store is disabl"...
0x1800362ff  mov     ecx, edi; int
0x180036301  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x180036306  jmp     short loc_180036318
0x180036308  mov     edi, r13d
0x18003630b  mov     rax, [rax]
0x18003630e  mov     rax, [rax+8]
0x180036312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036317  nop
0x180036318  mov     rcx, [rsp+120h+var_F0]
0x18003631d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180036321  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180036326  mov     eax, edi
0x180036328  jmp     loc_18003661F
0x18003632d  mov     edi, r13d
0x180036330  mov     rax, [rax]
0x180036333  mov     rax, [rax+8]
0x180036337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003633c  nop
0x18003633d  mov     rcx, [rbp+57h+var_D0]
0x180036341  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180036345  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003634a  nop
0x18003634b  mov     rcx, [rbp+57h+var_C8]
0x18003634f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180036353  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180036358  jmp     short loc_180036318
0x18003635a  mov     r14d, 80004005h
0x180036360  test    ebx, ebx
0x180036362  cmovns  ebx, r14d
0x180036366  jmp     loc_1800365F3
0x18003636b  mov     edi, 2
0x180036370  mov     [rbp+57h+var_50], edi
0x180036373  mov     [rbp+57h+var_4C], 0FFF0102h
0x18003637a  mov     [rbp+57h+var_48], 34140102h
0x180036381  mov     [rsp+120h+var_E0], r13
0x180036386  mov     rcx, [r15+18h]
0x18003638a  mov     rax, [rcx]
0x18003638d  lea     r8, [rsp+120h+var_E0]
0x180036392  xor     edx, edx
0x180036394  mov     rax, [rax+20h]
0x180036398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003639d  mov     ebx, eax
0x18003639f  test    eax, eax
0x1800363a1  js      short loc_1800363BD
0x1800363a3  mov     rcx, [rsp+120h+var_E0]
0x1800363a8  mov     rax, [rcx]
0x1800363ab  mov     r8d, edi
0x1800363ae  lea     rdx, [rbp+57h+var_50]
0x1800363b2  mov     rax, [rax+38h]
0x1800363b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800363bb  mov     ebx, eax
0x1800363bd  mov     edx, r13d
0x1800363c0  mov     [rsp+120h+var_E8], edx
0x1800363c4  test    ebx, ebx
0x1800363c6  js      short loc_1800363F2
0x1800363c8  mov     rcx, [rsp+120h+var_E0]
0x1800363cd  mov     rax, [rcx]
0x1800363d0  lea     r8, [rsp+120h+var_E8]
0x1800363d5  mov     rax, [rax+48h]
0x1800363d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800363de  mov     ebx, eax
0x1800363e0  mov     edx, [rsp+120h+var_E8]
0x1800363e4  cmp     edx, 64h ; 'd'
0x1800363e7  jbe     short loc_1800363F2
0x1800363e9  mov     edx, 64h ; 'd'
0x1800363ee  mov     [rsp+120h+var_E8], edx
0x1800363f2  mov     [rsp+120h+lpRows], r13
0x1800363f7  test    ebx, ebx
0x1800363f9  js      loc_1800365E8
0x1800363ff  mov     rcx, [rsp+120h+var_E0]
0x180036404  mov     rax, [rcx]
0x180036407  lea     r9, [rsp+120h+lpRows]
0x18003640c  xor     r8d, r8d
0x18003640f  mov     rax, [rax+98h]
0x180036416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003641b  mov     ebx, eax
0x18003641d  test    eax, eax
0x18003641f  js      loc_1800365E8
0x180036425  mov     r12d, r13d
0x180036428  mov     eax, r13d
0x18003642b  mov     edi, 80041206h
0x180036430  mov     r14d, 80004005h
0x180036436  mov     [rsp+120h+var_E4], eax
0x18003643a  mov     rcx, [rsp+120h+lpRows]
0x18003643f  cmp     eax, [rcx]
0x180036441  jnb     loc_1800365AC
0x180036447  inc     rax
0x18003644a  add     rax, rax
0x18003644d  mov     r13, [rcx+rax*8]
0x180036451  cmp     dword ptr [r13+18h], 34140102h
0x180036459  jnz     short loc_180036465
0x18003645b  mov     rax, [r13+28h]
0x18003645f  mov     [rbp+57h+var_C0], rax
0x180036463  jmp     short loc_18003646D
0x180036465  mov     [rbp+57h+var_C0], 0
0x18003646d  cmp     dword ptr [r13+0], 0FFF0102h
0x180036475  jnz     loc_180036585
0x18003647b  lea     rcx, [rbp+57h+var_B0]; this
0x18003647f  call    ??0CStoreEntryId@@QEAA@XZ; CStoreEntryId::CStoreEntryId(void)
0x180036484  nop
0x180036485  mov     eax, [r15+0A4h]
0x18003648c  mov     [rbp+57h+var_78], eax
0x18003648f  lea     rax, [rsp+120h+var_F0]
0x180036494  mov     [rsp+120h+var_100], rax
0x180036499  mov     r9, r13
0x18003649c  mov     r8, [rbp+57h+var_C0]
0x1800364a0  mov     rdx, [r15+18h]
0x1800364a4  lea     rcx, [rbp+57h+var_B0]
0x1800364a8  call    ?InitializeWithHint@CStoreEntryId@@QEAAJPEAUIMAPISession@@PEAU_MAPIUID@@PEAU_SPropValue@@AEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CStoreEntryId::InitializeWithHint(IMAPISession *,_MAPIUID *,_SPropValue *,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x1800364ad  mov     ebx, eax
0x1800364af  test    eax, eax
0x1800364b1  js      loc_18003657A
0x1800364b7  cmp     [rbp+57h+var_80], 0
0x1800364bb  jnz     short loc_1800364D4
0x1800364bd  mov     rdx, [rsp+120h+var_F0]
0x1800364c2  lea     rcx, [rbp+57h+var_60]
0x1800364c6  call    ?Compare@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEBAHPEB_W@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Compare(wchar_t const *)
0x1800364cb  nop
0x1800364cc  test    eax, eax
0x1800364ce  jnz     loc_18003657C
0x1800364d4  mov     r13d, 1
0x1800364da  lea     rdx, [rsp+120h+var_F0]
0x1800364df  mov     rcx, r15
0x1800364e2  call    ?ReleaseStore@CMapiSession@@QEAAJAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiSession::ReleaseStore(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x1800364e7  mov     dword ptr [rsp+120h+var_100], 0
0x1800364ef  xor     r9d, r9d
0x1800364f2  mov     r8, rsi
0x1800364f5  lea     rdx, [rbp+57h+var_B0]
0x1800364f9  mov     rcx, r15
0x1800364fc  call    ?OpenStoreInternal@CMapiSession@@AEAAJAEAVCStoreEntryId@@PEAPEAVCMapiStore@@PEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@H@Z; CMapiSession::OpenStoreInternal(CStoreEntryId &,CMapiStore * *,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> *,int)
0x180036501  mov     ebx, eax
0x180036503  test    eax, eax
0x180036505  jnz     short loc_180036552
0x180036507  mov     rdx, [rsi]
0x18003650a  cmp     [rdx+74h], eax
0x18003650d  jz      short loc_180036528
0x18003650f  mov     qword ptr [rsi], 0
0x180036516  mov     ebx, edi
0x180036518  lea     rdx, aOpenstoreWillF; "OpenStore() will fail because Exchange "...
0x18003651f  mov     ecx, edi; int
0x180036521  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x180036526  jmp     short loc_180036558
0x180036528  cmp     [rbp+57h+var_80], 0
0x18003652c  jz      short loc_180036593
0x18003652e  test    rdx, rdx
0x180036531  jz      short loc_180036546
0x180036533  mov     rdx, [rdx+28h]
0x180036537  lea     rcx, [rsp+120h+var_F0]
0x18003653c  call    ?Compare@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEBAHPEB_W@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Compare(wchar_t const *)
0x180036541  nop
0x180036542  test    eax, eax
0x180036544  jz      short loc_180036593
0x180036546  mov     ebx, r14d
0x180036549  mov     qword ptr [rsi], 0
0x180036550  jmp     short loc_180036558
0x180036552  test    ebx, ebx
0x180036554  cmovns  ebx, r14d
0x180036558  cmp     [rbp+57h+var_80], 0
0x18003655c  jz      short loc_1800365A3
0x18003655e  mov     ecx, ebx; int
0x180036560  call    ?IsSoftError@@YAHJ@Z; IsSoftError(long)
0x180036565  test    eax, eax
0x180036567  jz      short loc_18003657C
0x180036569  lea     rdx, aCmapisessionOp_1; "CMapiSession::OpenStore Found delegate "...
0x180036570  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x180036575  mov     r12d, ebx
0x180036578  jmp     short loc_18003657C
0x18003657a  xor     ebx, ebx
0x18003657c  lea     rcx, [rbp+57h+var_B0]; this
0x180036580  call    ??1CStoreEntryId@@QEAA@XZ; CStoreEntryId::~CStoreEntryId(void)
0x180036585  mov     eax, [rsp+120h+var_E4]
0x180036589  inc     eax
0x18003658b  xor     r13d, r13d
0x18003658e  jmp     loc_180036436
0x180036593  mov     rcx, [rsi]
0x180036596  mov     rax, [rcx]
0x180036599  mov     rax, [rax+8]
0x18003659d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800365a2  nop
0x1800365a3  lea     rcx, [rbp+57h+var_B0]; this
0x1800365a7  call    ??1CStoreEntryId@@QEAA@XZ; CStoreEntryId::~CStoreEntryId(void)
0x1800365ac  mov     rcx, [rsp+120h+lpRows]; lpRows
0x1800365b1  test    rcx, rcx
0x1800365b4  jz      short loc_1800365C5
0x1800365b6  call    cs:__imp_FreeProws
0x1800365bc  mov     [rsp+120h+lpRows], 0
0x1800365c5  test    r13d, r13d
0x1800365c8  jnz     short loc_1800365E8
0x1800365ca  test    r12d, r12d
0x1800365cd  jns     short loc_1800365E3
0x1800365cf  lea     rdx, aCmapisessionOp_0; "CMapiSession::OpenStore at least one in"...
0x1800365d6  mov     ecx, r12d; int
0x1800365d9  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x1800365de  mov     ebx, r12d
0x1800365e1  jmp     short loc_1800365E8
0x1800365e3  mov     ebx, 8004010Fh
0x1800365e8  lea     rcx, [rsp+120h+var_E0]
0x1800365ed  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800365f2  nop
0x1800365f3  mov     rcx, [rbp+57h+var_D0]
0x1800365f7  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800365fb  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180036600  nop
0x180036601  mov     rcx, [rbp+57h+var_C8]
0x180036605  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180036609  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003660e  nop
0x18003660f  mov     rcx, [rsp+120h+var_F0]
0x180036614  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180036618  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003661d  mov     eax, ebx
0x18003661f  mov     rcx, [rbp+57h+var_40]
0x180036623  xor     rcx, rsp; StackCookie
0x180036626  call    __security_check_cookie
0x18003662b  mov     rbx, [rsp+120h+arg_18]
0x180036633  add     rsp, 0F0h
0x18003663a  pop     r15
0x18003663c  pop     r14
0x18003663e  pop     r13
0x180036640  pop     r12
0x180036642  pop     rdi
0x180036643  pop     rsi
0x180036644  pop     rbp
0x180036645  retn
```
