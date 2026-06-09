# CServerObject_RawFactory::GetProvider(_tag_WmiInternalContext,long,IWbemContext *,_GUID *,ushort const *,ushort const *,ushort const *,ushort const *,_GUID const &,void * *)

- ea: `0x14003d0c0`
- end: `0x14003d517`
- name: `?GetProvider@CServerObject_RawFactory@@UEAAJU_tag_WmiInternalContext@@JPEAUIWbemContext@@PEAU_GUID@@PEBG333AEBU4@PEAPEAX@Z`
- size: `1111`
- prototype: `__int64 __fastcall(__int64, void **, __int64, struct IWbemContext *, struct _GUID *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, __int64, __int64)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140001624`
- `0x1400018b0`
- `0x140001988`
- `0x140006c64`
- `0x140007698`
- `0x14000a530`
- `0x140014298`
- `0x14001d55c`
- `0x1400217c8`
- `0x1400234b8`
- `0x140024d4c`
- `0x140027a4c`
- `0x1400282c4`
- `0x140029c48`
- `0x14002ff78`
- `0x14002ffe4`
- `0x14003d0c0`
- `0x140048010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14003d154`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14003d473`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14003d154`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14003d473`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003d164`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003d164`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14003d137`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14003d137`
- `wbemcomn!GetMemLogObject` at `0x14003d3c9`
- `wbemcomn!GetMemLogObject` at `0x14003d4bb`
- `wbemcomn!GetMemLogObject` at `0x14003d3c9`
- `wbemcomn!GetMemLogObject` at `0x14003d4bb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003d3d5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003d4c6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003d3d5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003d4c6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14003d1a0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14003d1a0`

## pseudocode

```c
__int64 __fastcall CServerObject_RawFactory::GetProvider(
        __int64 a1,
        void **a2,
        __int64 a3,
        struct IWbemContext *a4,
        struct _GUID *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        unsigned __int16 *a9,
        __int64 a10,
        __int64 a11)
{
  void *v14; // r14
  HRESULT v15; // ebx
  unsigned __int16 *v16; // rsi
  struct IUnknown *v17; // rax
  volatile signed __int32 *v18; // rax
  CServerObject_ProviderRegistrationV1 *v19; // rdi
  CServerObject_ProviderRegistrationV1 *v20; // rcx
  unsigned __int64 v21; // rdx
  OLECHAR *v22; // r8
  unsigned int v23; // ecx
  unsigned int v24; // eax
  int v25; // eax
  __int64 v26; // r9
  int v27; // ecx
  int v28; // ecx
  int ApartmentInstanceProvider; // eax
  CServerObject_RawFactory *v30; // rcx
  CMemoryLog *MemLogObject; // rax
  _QWORD *v32; // rcx
  CMemoryLog *v33; // rax
  struct _GUID *v35; // [rsp+38h] [rbp-38h]
  struct IUnknown *v36; // [rsp+50h] [rbp-20h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-18h] BYREF
  struct IServerSecurity *v38; // [rsp+60h] [rbp-10h] BYREF
  struct IUnknown *ppInterface; // [rsp+68h] [rbp-8h] BYREF
  int v40; // [rsp+A8h] [rbp+38h] BYREF
  int v41; // [rsp+B0h] [rbp+40h]

  v41 = a3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a9);
  }
  v14 = *a2;
  v40 = 0;
  ppInterface = 0;
  v38 = 0;
  if ( !v14 )
    goto LABEL_10;
  if ( SetThreadToken(0, v14) )
  {
    v15 = ProviderSubSystem_Globals::BeginThreadImpersonation(&ppInterface, &v38, &v40);
    RevertToSelf();
  }
  else
  {
    v15 = -2147217405;
  }
  CloseHandle(v14);
  if ( v15 >= 0 )
  {
LABEL_10:
    v16 = a8;
    ppv = 0;
    if ( a8 )
    {
      v15 = CoCreateInstance(&CLSID_WbemDefPath, 0, 5u, &IID_IWbemPath, &ppv);
      if ( v15 < 0 )
        goto LABEL_54;
      v15 = (*(__int64 (__fastcall **)(LPVOID, __int64, unsigned __int16 *))(*(_QWORD *)ppv + 24LL))(ppv, 12, v16);
      if ( v15 < 0 )
        goto LABEL_54;
    }
    v17 = (struct IUnknown *)operator new(0x8E0u);
    v36 = v17;
    if ( !v17
      || (v18 = (volatile signed __int32 *)CServerObject_ProviderRegistrationV1::CServerObject_ProviderRegistrationV1((CServerObject_ProviderRegistrationV1 *)v17),
          (v19 = (CServerObject_ProviderRegistrationV1 *)v18) == 0) )
    {
      v15 = -2147217402;
      goto LABEL_54;
    }
    _InterlockedIncrement(v18);
    v15 = CServerObject_ProviderRegistrationV1::SetContext(
            (CServerObject_ProviderRegistrationV1 *)v18,
            a4,
            *(struct IWbemPath **)(a1 + 56),
            *(struct IWbemServices **)(a1 + 64));
    if ( v15 < 0 )
    {
LABEL_52:
      CServerObject_ProviderRegistrationV1::Release(v19);
LABEL_54:
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      if ( v14 )
      {
        ProviderSubSystem_Common_Globals::EndImpersonation(ppInterface, v38, v40);
        RevertToSelf();
      }
      goto LABEL_58;
    }
    CServerObject_ProviderRegistrationV1::EventProvider(v19);
    if ( (unsigned int)CServerObject_ProviderRegistrationV1::ObjectProvider(v20) )
    {
      if ( (_DWORD)v21 )
      {
        v23 = ProviderSubSystem_Globals::s_ObjectCacheTimeout;
        if ( ProviderSubSystem_Globals::s_ObjectCacheTimeout < ProviderSubSystem_Globals::s_EventCacheTimeout )
          v23 = ProviderSubSystem_Globals::s_EventCacheTimeout;
        *((_DWORD *)v19 + 434) = v23;
LABEL_25:
        v25 = CServerObject_ProviderRegistrationV1::Load(v19, v21, v22, a9);
        if ( v25 < 0 )
        {
          v15 = -2147217389;
          if ( v25 == -2147217406 )
            v15 = -2147217391;
          goto LABEL_52;
        }
        v26 = *((unsigned int *)v19 + 420);
        if ( ((_DWORD)v26 == 11 || (_DWORD)v26 == 8) && *((_DWORD *)v19 + 9) == 1 )
        {
          *((_DWORD *)v19 + 420) = 3;
          v26 = 3;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            35,
            WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids,
            v26,
            *((_DWORD *)v19 + 8));
        }
        v36 = 0;
        if ( *((_DWORD *)v19 + 420) != 3 && *((_DWORD *)v19 + 8) == 1 )
        {
          v27 = *((_DWORD *)v19 + 6);
          if ( !v27 )
          {
            ApartmentInstanceProvider = CServerObject_RawFactory::GetApartmentInstanceProvider(
                                          (CServerObject_RawFactory *)a1,
                                          v41,
                                          a4,
                                          a5,
                                          a6,
                                          a7,
                                          v16,
                                          &IID_IUnknown,
                                          (void **)&v36,
                                          v19);
            goto LABEL_42;
          }
          v28 = v27 - 1;
          if ( v28 && (unsigned int)(v28 - 1) >= 2 )
          {
            v15 = -2147217390;
            goto LABEL_52;
          }
        }
        ApartmentInstanceProvider = CServerObject_RawFactory::GetNonApartmentProvider(
                                      (CServerObject_RawFactory *)a1,
                                      v41,
                                      a4,
                                      a5,
                                      a6,
                                      a7,
                                      v16,
                                      v35,
                                      (void **)&v36,
                                      v19);
LABEL_42:
        v15 = ApartmentInstanceProvider;
        if ( ApartmentInstanceProvider >= 0 )
        {
          v15 = CServerObject_RawFactory::CheckInterfaceConformance(v30, v19, v36);
          if ( v15 < 0 )
          {
            MemLogObject = GetMemLogObject();
            CMemoryLog::Write(MemLogObject, -1);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_SD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                36,
                (unsigned int)WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids,
                (_DWORD)a9,
                v15);
            }
          }
          else
          {
            v15 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64))v36->lpVtbl->QueryInterface)(
                    v36,
                    a10,
                    a11);
          }
          ((void (__fastcall *)(struct IUnknown *))v36->lpVtbl->Release)(v36);
        }
        goto LABEL_52;
      }
      v24 = ProviderSubSystem_Globals::s_ObjectCacheTimeout;
    }
    else
    {
      if ( !(_DWORD)v21 )
        goto LABEL_25;
      v24 = ProviderSubSystem_Globals::s_EventCacheTimeout;
    }
    *((_DWORD *)v19 + 434) = v24;
    goto LABEL_25;
  }
LABEL_58:
  v32 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      37,
      WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids,
      (unsigned int)v15);
    v32 = WPP_GLOBAL_Control;
  }
  if ( v15 < 0 )
  {
    v33 = GetMemLogObject();
    CMemoryLog::Write(v33, v15);
    v32 = WPP_GLOBAL_Control;
  }
  if ( v32 != &WPP_GLOBAL_Control && (*((_BYTE *)v32 + 28) & 4) != 0 && *((_BYTE *)v32 + 25) >= 2u )
    WPP_SF_d(v32[2], 38, WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids, (unsigned int)v15);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x14003d0c0  mov     [rsp-28h+arg_0], rbx
0x14003d0c5  mov     [rsp-28h+arg_18], rsi
0x14003d0ca  mov     [rsp-28h+arg_10], r8d
0x14003d0cf  push    rbp
0x14003d0d0  push    rdi
0x14003d0d1  push    r12
0x14003d0d3  push    r14
0x14003d0d5  push    r15
0x14003d0d7  mov     rbp, rsp
0x14003d0da  sub     rsp, 70h
0x14003d0de  mov     r12, r9
0x14003d0e1  mov     rbx, rdx
0x14003d0e4  mov     r15, rcx
0x14003d0e7  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d0ee  lea     rax, WPP_GLOBAL_Control
0x14003d0f5  cmp     rcx, rax
0x14003d0f8  jz      short loc_14003D113
0x14003d0fa  test    byte ptr [rcx+1Ch], 4
0x14003d0fe  jz      short loc_14003D113
0x14003d100  cmp     byte ptr [rcx+19h], 5
0x14003d104  jb      short loc_14003D113
0x14003d106  mov     r9, [rbp+arg_40]
0x14003d10a  mov     rcx, [rcx+10h]
0x14003d10e  call    WPP_SF_S
0x14003d113  mov     r14, [rbx]
0x14003d116  mov     [rbp+arg_8], 0
0x14003d11d  mov     [rbp+ppInterface], 0
0x14003d125  mov     [rbp+var_10], 0
0x14003d12d  test    r14, r14
0x14003d130  jz      short loc_14003D172
0x14003d132  mov     rdx, r14; Token
0x14003d135  xor     ecx, ecx; Thread
0x14003d137  call    cs:__imp_SetThreadToken
0x14003d13d  test    eax, eax
0x14003d13f  jz      short loc_14003D15C
0x14003d141  lea     r8, [rbp+arg_8]; int *
0x14003d145  lea     rdx, [rbp+var_10]; struct IServerSecurity **
0x14003d149  lea     rcx, [rbp+ppInterface]; ppInterface
0x14003d14d  call    ?BeginThreadImpersonation@ProviderSubSystem_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAH@Z; ProviderSubSystem_Globals::BeginThreadImpersonation(IUnknown * &,IServerSecurity * &,int &)
0x14003d152  mov     ebx, eax
0x14003d154  call    cs:__imp_RevertToSelf
0x14003d15a  jmp     short loc_14003D161
0x14003d15c  mov     ebx, 80041003h
0x14003d161  mov     rcx, r14; hObject
0x14003d164  call    cs:__imp_CloseHandle
0x14003d16a  test    ebx, ebx
0x14003d16c  js      loc_14003D479
0x14003d172  mov     rsi, [rbp+arg_38]
0x14003d176  mov     [rbp+var_18], 0
0x14003d17e  test    rsi, rsi
0x14003d181  jz      short loc_14003D1D2
0x14003d183  xor     edx, edx; pUnkOuter
0x14003d185  lea     rax, [rbp+var_18]
0x14003d189  lea     r9, IID_IWbemPath; riid
0x14003d190  mov     [rsp+70h+ppv], rax; ppv
0x14003d195  lea     rcx, CLSID_WbemDefPath; rclsid
0x14003d19c  lea     r8d, [rdx+5]; dwClsContext
0x14003d1a0  call    cs:__imp_CoCreateInstance
0x14003d1a6  mov     ebx, eax
0x14003d1a8  test    eax, eax
0x14003d1aa  js      loc_14003D448
0x14003d1b0  mov     rcx, [rbp+var_18]
0x14003d1b4  mov     r8, rsi
0x14003d1b7  mov     edx, 0Ch
0x14003d1bc  mov     rax, [rcx]
0x14003d1bf  mov     rax, [rax+18h]
0x14003d1c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d1c8  mov     ebx, eax
0x14003d1ca  test    eax, eax
0x14003d1cc  js      loc_14003D448
0x14003d1d2  mov     ecx, 8E0h; dwBytes
0x14003d1d7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003d1dc  mov     [rbp+var_20], rax
0x14003d1e0  test    rax, rax
0x14003d1e3  jz      loc_14003D443
0x14003d1e9  mov     rcx, rax; this
0x14003d1ec  call    ??0CServerObject_ProviderRegistrationV1@@QEAA@XZ; CServerObject_ProviderRegistrationV1::CServerObject_ProviderRegistrationV1(void)
0x14003d1f1  mov     rdi, rax
0x14003d1f4  test    rax, rax
0x14003d1f7  jz      loc_14003D443
0x14003d1fd  lock inc dword ptr [rax]
0x14003d200  mov     r9, [r15+40h]; struct IWbemServices *
0x14003d204  mov     rdx, r12; struct IWbemContext *
0x14003d207  mov     r8, [r15+38h]; struct IWbemPath *
0x14003d20b  mov     rcx, rax; this
0x14003d20e  call    ?SetContext@CServerObject_ProviderRegistrationV1@@QEAAJPEAUIWbemContext@@PEAUIWbemPath@@PEAUIWbemServices@@@Z; CServerObject_ProviderRegistrationV1::SetContext(IWbemContext *,IWbemPath *,IWbemServices *)
0x14003d213  mov     ebx, eax
0x14003d215  test    eax, eax
0x14003d217  js      loc_14003D439
0x14003d21d  mov     rcx, rdi; this
0x14003d220  call    ?EventProvider@CServerObject_ProviderRegistrationV1@@QEAAHXZ; CServerObject_ProviderRegistrationV1::EventProvider(void)
0x14003d225  mov     edx, eax
0x14003d227  call    ?ObjectProvider@CServerObject_ProviderRegistrationV1@@QEAAHXZ; CServerObject_ProviderRegistrationV1::ObjectProvider(void)
0x14003d22c  test    eax, eax
0x14003d22e  jz      short loc_14003D257
0x14003d230  test    edx, edx
0x14003d232  jz      short loc_14003D24F
0x14003d234  mov     ecx, cs:?s_ObjectCacheTimeout@ProviderSubSystem_Globals@@2KA; ulong ProviderSubSystem_Globals::s_ObjectCacheTimeout
0x14003d23a  cmp     ecx, cs:?s_EventCacheTimeout@ProviderSubSystem_Globals@@2KA; ulong ProviderSubSystem_Globals::s_EventCacheTimeout
0x14003d240  cmovb   ecx, cs:?s_EventCacheTimeout@ProviderSubSystem_Globals@@2KA; ulong ProviderSubSystem_Globals::s_EventCacheTimeout
0x14003d247  mov     [rdi+6C8h], ecx
0x14003d24d  jmp     short loc_14003D267
0x14003d24f  mov     eax, cs:?s_ObjectCacheTimeout@ProviderSubSystem_Globals@@2KA; ulong ProviderSubSystem_Globals::s_ObjectCacheTimeout
0x14003d255  jmp     short loc_14003D261
0x14003d257  test    edx, edx
0x14003d259  jz      short loc_14003D267
0x14003d25b  mov     eax, cs:?s_EventCacheTimeout@ProviderSubSystem_Globals@@2KA; ulong ProviderSubSystem_Globals::s_EventCacheTimeout
0x14003d261  mov     [rdi+6C8h], eax
0x14003d267  mov     r9, [rbp+arg_40]; unsigned __int16 *
0x14003d26b  mov     rcx, rdi; this
0x14003d26e  call    ?Load@CServerObject_ProviderRegistrationV1@@QEAAJ_KPEAUIWbemPath@@PEBG@Z; CServerObject_ProviderRegistrationV1::Load(unsigned __int64,IWbemPath *,ushort const *)
0x14003d273  test    eax, eax
0x14003d275  js      loc_14003D429
0x14003d27b  mov     r9d, [rdi+690h]
0x14003d282  mov     ebx, 3
0x14003d287  cmp     r9d, 0Bh
0x14003d28b  jz      short loc_14003D293
0x14003d28d  cmp     r9d, 8
0x14003d291  jnz     short loc_14003D2A2
0x14003d293  cmp     dword ptr [rdi+24h], 1
0x14003d297  jnz     short loc_14003D2A2
0x14003d299  mov     [rdi+690h], ebx
0x14003d29f  mov     r9d, ebx
0x14003d2a2  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d2a9  lea     rax, WPP_GLOBAL_Control
0x14003d2b0  cmp     rcx, rax
0x14003d2b3  jz      short loc_14003D2DD
0x14003d2b5  test    byte ptr [rcx+1Ch], 4
0x14003d2b9  jz      short loc_14003D2DD
0x14003d2bb  cmp     byte ptr [rcx+19h], 5
0x14003d2bf  jb      short loc_14003D2DD
0x14003d2c1  mov     eax, [rdi+20h]
0x14003d2c4  lea     r8, WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids
0x14003d2cb  mov     rcx, [rcx+10h]
0x14003d2cf  mov     edx, 23h ; '#'
0x14003d2d4  mov     dword ptr [rsp+70h+ppv], eax
0x14003d2d8  call    WPP_SF_dd
0x14003d2dd  mov     [rbp+var_20], 0
0x14003d2e5  cmp     [rdi+690h], ebx
0x14003d2eb  jz      short loc_14003D358
0x14003d2ed  cmp     dword ptr [rdi+20h], 1
0x14003d2f1  jnz     short loc_14003D358
0x14003d2f3  mov     ecx, [rdi+18h]
0x14003d2f6  test    ecx, ecx
0x14003d2f8  jz      short loc_14003D313
0x14003d2fa  sub     ecx, 1
0x14003d2fd  jz      short loc_14003D358
0x14003d2ff  sub     ecx, 1
0x14003d302  jz      short loc_14003D358
0x14003d304  cmp     ecx, 1
0x14003d307  jz      short loc_14003D358
0x14003d309  mov     ebx, 80041012h
0x14003d30e  jmp     loc_14003D439
0x14003d313  mov     r9, [rbp+arg_20]; struct _GUID *
0x14003d317  lea     rax, [rbp+var_20]
0x14003d31b  mov     edx, [rbp+arg_10]; int
0x14003d31e  mov     r8, r12; struct IWbemContext *
0x14003d321  mov     [rsp+70h+var_28], rdi; struct CServerObject_ProviderRegistrationV1 *
0x14003d326  mov     rcx, r15; this
0x14003d329  mov     [rsp+70h+var_30], rax; void **
0x14003d32e  lea     rax, IID_IUnknown
0x14003d335  mov     [rsp+70h+var_38], rax; struct _GUID *
0x14003d33a  mov     rax, [rbp+arg_30]
0x14003d33e  mov     [rsp+70h+var_40], rsi; unsigned __int16 *
0x14003d343  mov     [rsp+70h+var_48], rax; unsigned __int16 *
0x14003d348  mov     rax, [rbp+arg_28]
0x14003d34c  mov     [rsp+70h+ppv], rax; unsigned __int16 *
0x14003d351  call    ?GetApartmentInstanceProvider@CServerObject_RawFactory@@QEAAJJPEAUIWbemContext@@PEAU_GUID@@PEBG22AEBU3@PEAPEAXAEAVCServerObject_ProviderRegistrationV1@@@Z; CServerObject_RawFactory::GetApartmentInstanceProvider(long,IWbemContext *,_GUID *,ushort const *,ushort const *,ushort const *,_GUID const &,void * *,CServerObject_ProviderRegistrationV1 &)
0x14003d356  jmp     short loc_14003D38F
0x14003d358  mov     r9, [rbp+arg_20]; struct _GUID *
0x14003d35c  lea     rax, [rbp+var_20]
0x14003d360  mov     edx, [rbp+arg_10]; int
0x14003d363  mov     r8, r12; struct IWbemContext *
0x14003d366  mov     [rsp+70h+var_28], rdi; struct CServerObject_ProviderRegistrationV1 *
0x14003d36b  mov     rcx, r15; this
0x14003d36e  mov     [rsp+70h+var_30], rax; void **
0x14003d373  mov     rax, [rbp+arg_30]
0x14003d377  mov     [rsp+70h+var_40], rsi; unsigned __int16 *
0x14003d37c  mov     [rsp+70h+var_48], rax; unsigned __int16 *
0x14003d381  mov     rax, [rbp+arg_28]
0x14003d385  mov     [rsp+70h+ppv], rax; unsigned __int16 *
0x14003d38a  call    ?GetNonApartmentProvider@CServerObject_RawFactory@@QEAAJJPEAUIWbemContext@@PEAU_GUID@@PEBG22AEBU3@PEAPEAXAEAVCServerObject_ProviderRegistrationV1@@@Z; CServerObject_RawFactory::GetNonApartmentProvider(long,IWbemContext *,_GUID *,ushort const *,ushort const *,ushort const *,_GUID const &,void * *,CServerObject_ProviderRegistrationV1 &)
0x14003d38f  mov     ebx, eax
0x14003d391  test    eax, eax
0x14003d393  js      loc_14003D439
0x14003d399  mov     r8, [rbp+var_20]; struct IUnknown *
0x14003d39d  mov     rdx, rdi; struct CServerObject_ProviderRegistrationV1 *
0x14003d3a0  call    ?CheckInterfaceConformance@CServerObject_RawFactory@@QEAAJAEAVCServerObject_ProviderRegistrationV1@@PEAUIUnknown@@@Z; CServerObject_RawFactory::CheckInterfaceConformance(CServerObject_ProviderRegistrationV1 &,IUnknown *)
0x14003d3a5  mov     ebx, eax
0x14003d3a7  test    eax, eax
0x14003d3a9  js      short loc_14003D3C9
0x14003d3ab  mov     rcx, [rbp+var_20]
0x14003d3af  mov     r8, [rbp+arg_50]
0x14003d3b6  mov     rdx, [rbp+arg_48]
0x14003d3ba  mov     rax, [rcx]
0x14003d3bd  mov     rax, [rax]
0x14003d3c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d3c5  mov     ebx, eax
0x14003d3c7  jmp     short loc_14003D417
0x14003d3c9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003d3cf  mov     rcx, rax
0x14003d3d2  or      edx, 0FFFFFFFFh
0x14003d3d5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14003d3db  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d3e2  lea     rax, WPP_GLOBAL_Control
0x14003d3e9  cmp     rcx, rax
0x14003d3ec  jz      short loc_14003D417
0x14003d3ee  test    byte ptr [rcx+1Ch], 4
0x14003d3f2  jz      short loc_14003D417
0x14003d3f4  cmp     byte ptr [rcx+19h], 2
0x14003d3f8  jb      short loc_14003D417
0x14003d3fa  mov     r9, [rbp+arg_40]
0x14003d3fe  lea     r8, WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids
0x14003d405  mov     rcx, [rcx+10h]
0x14003d409  mov     edx, 24h ; '$'
0x14003d40e  mov     dword ptr [rsp+70h+ppv], ebx
0x14003d412  call    WPP_SF_SD
0x14003d417  mov     rcx, [rbp+var_20]
0x14003d41b  mov     rax, [rcx]
0x14003d41e  mov     rax, [rax+10h]
0x14003d422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d427  jmp     short loc_14003D439
0x14003d429  mov     ebx, 80041013h
0x14003d42e  cmp     eax, 80041002h
0x14003d433  lea     ecx, [rbx-2]
0x14003d436  cmovz   ebx, ecx
0x14003d439  mov     rcx, rdi; this
0x14003d43c  call    ?Release@CServerObject_ProviderRegistrationV1@@QEAAKXZ; CServerObject_ProviderRegistrationV1::Release(void)
0x14003d441  jmp     short loc_14003D448
0x14003d443  mov     ebx, 80041006h
0x14003d448  mov     rcx, [rbp+var_18]
0x14003d44c  test    rcx, rcx
0x14003d44f  jz      short loc_14003D45D
0x14003d451  mov     rax, [rcx]
0x14003d454  mov     rax, [rax+10h]
0x14003d458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d45d  test    r14, r14
0x14003d460  jz      short loc_14003D479
0x14003d462  mov     r8d, [rbp+arg_8]; int
0x14003d466  mov     rdx, [rbp+var_10]; struct IServerSecurity *
0x14003d46a  mov     rcx, [rbp+ppInterface]; struct IUnknown *
0x14003d46e  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x14003d473  call    cs:__imp_RevertToSelf
0x14003d479  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d480  lea     rdi, WPP_GLOBAL_Control
0x14003d487  cmp     rcx, rdi
0x14003d48a  jz      short loc_14003D4B7
0x14003d48c  test    byte ptr [rcx+1Ch], 4
0x14003d490  jz      short loc_14003D4B7
0x14003d492  cmp     byte ptr [rcx+19h], 5
0x14003d496  jb      short loc_14003D4B7
0x14003d498  mov     rcx, [rcx+10h]
0x14003d49c  lea     r8, WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids
0x14003d4a3  mov     edx, 25h ; '%'
0x14003d4a8  mov     r9d, ebx
0x14003d4ab  call    WPP_SF_d
0x14003d4b0  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d4b7  test    ebx, ebx
0x14003d4b9  jns     short loc_14003D4D3
0x14003d4bb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003d4c1  mov     rcx, rax
0x14003d4c4  mov     edx, ebx
0x14003d4c6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14003d4cc  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d4d3  cmp     rcx, rdi
0x14003d4d6  jz      short loc_14003D4FC
0x14003d4d8  test    byte ptr [rcx+1Ch], 4
0x14003d4dc  jz      short loc_14003D4FC
0x14003d4de  cmp     byte ptr [rcx+19h], 2
0x14003d4e2  jb      short loc_14003D4FC
0x14003d4e4  mov     rcx, [rcx+10h]
0x14003d4e8  lea     r8, WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids
0x14003d4ef  mov     edx, 26h ; '&'
0x14003d4f4  mov     r9d, ebx
0x14003d4f7  call    WPP_SF_d
0x14003d4fc  lea     r11, [rsp+70h+var_s0]
0x14003d501  mov     eax, ebx
0x14003d503  mov     rbx, [r11+30h]
0x14003d507  mov     rsi, [r11+48h]
0x14003d50b  mov     rsp, r11
0x14003d50e  pop     r15
0x14003d510  pop     r14
0x14003d512  pop     r12
0x14003d514  pop     rdi
0x14003d515  pop     rbp
0x14003d516  retn
```
