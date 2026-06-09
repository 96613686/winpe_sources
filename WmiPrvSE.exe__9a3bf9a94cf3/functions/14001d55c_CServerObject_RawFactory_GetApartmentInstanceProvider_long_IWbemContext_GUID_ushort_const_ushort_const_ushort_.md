# CServerObject_RawFactory::GetApartmentInstanceProvider(long,IWbemContext *,_GUID *,ushort const *,ushort const *,ushort const *,_GUID const &,void * *,CServerObject_ProviderRegistrationV1 &)

- ea: `0x14001d55c`
- end: `0x14001dd9a`
- name: `?GetApartmentInstanceProvider@CServerObject_RawFactory@@QEAAJJPEAUIWbemContext@@PEAU_GUID@@PEBG22AEBU3@PEAPEAXAEAVCServerObject_ProviderRegistrationV1@@@Z`
- size: `2110`
- prototype: `int(CServerObject_RawFactory *__hidden this, int, struct IWbemContext *, struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, void **, struct CServerObject_ProviderRegistrationV1 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x14003d0c0`

## callees

- `0x140006d34`
- `0x140006d5c`
- `0x1400085ec`
- `0x14000a0f0`
- `0x14000a530`
- `0x14001d55c`
- `0x14001dda0`
- `0x14001de20`
- `0x14001df64`
- `0x14001e00c`
- `0x14001e268`
- `0x14001e6e4`
- `0x14001e774`
- `0x14001e9d4`
- `0x14001ebc4`
- `0x14001eec0`
- `0x1400234b8`
- `0x140046430`
- `0x140048010`

## import_xrefs

- `NCObjAPI!WmiSetAndCommitObject` at `0x14001d77e`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14001dd74`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14001d77e`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14001dd74`
- `wbemcomn!GetMemLogObject` at `0x14001dd84`
- `wbemcomn!GetMemLogObject` at `0x14001dd84`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001dd8f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001dd8f`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14001d9a9`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14001d9a9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x14001dce4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x14001dce4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CServerObject_RawFactory::GetApartmentInstanceProvider(
        CServerObject_RawFactory *this,
        int a2,
        struct IWbemContext *a3,
        struct _GUID *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        unsigned __int16 *a7,
        const struct _GUID *a8,
        void **a9,
        struct CServerObject_ProviderRegistrationV1 *a10)
{
  const GUID *v10; // r14
  CServerObject_StaThread *v12; // rax
  CServerObject_StaThread *v13; // rsi
  HRESULT ApartmentInstanceProvider; // ebx
  CServerObject_ProviderInitSink *v15; // rax
  struct _SECURITY_DESCRIPTOR *v16; // rdx
  __int64 v17; // r13
  CServerObject_RawFactory *v18; // rcx
  CServerObject_ProviderInitSink *v20; // rax
  CServerObject_ProviderInitSink *v21; // r13
  CInterceptor_IWbemProviderInitSink *v22; // rax
  CInterceptor_IWbemProviderInitSink *inited; // r12
  CServerObject_StaThread *v24; // rax
  struct IWbemServices *v25; // r14
  CInterceptor_IWbemSyncProvider *v26; // rax
  CInterceptor_IWbemSyncProvider *v27; // r15
  bool v28; // zf
  void (*v29)(void); // rax
  CServerObject_ProviderInitSink *v30; // rax
  struct _SECURITY_DESCRIPTOR *v31; // rdx
  CServerObject_ProviderInitSink *v32; // rax
  CServerObject_ProviderInitSink *v33; // r14
  CInterceptor_IWbemProviderInitSink *v34; // rax
  CInterceptor_IWbemProviderInitSink *v35; // r12
  CMemoryLog *MemLogObject; // rax
  CServerObject_StaThread *v38; // [rsp+88h] [rbp-78h] BYREF
  CInterceptor_IWbemProviderInitSink *v39; // [rsp+90h] [rbp-70h] BYREF
  int v40[2]; // [rsp+98h] [rbp-68h] BYREF
  void *lpMem; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v42; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v43; // [rsp+B0h] [rbp-50h]
  unsigned __int64 v44; // [rsp+B8h] [rbp-48h]
  struct IWbemContext *v45; // [rsp+C0h] [rbp-40h]
  __int64 v46; // [rsp+C8h] [rbp-38h] BYREF
  struct IWbemServices *v47; // [rsp+D0h] [rbp-30h]
  void **v48; // [rsp+D8h] [rbp-28h]
  CServerObject_ProviderInitSink *v49; // [rsp+E0h] [rbp-20h]
  GUID pguid; // [rsp+E8h] [rbp-18h] BYREF
  OLECHAR sz[80]; // [rsp+100h] [rbp+0h] BYREF

  v10 = a4;
  v45 = a3;
  v40[0] = a2;
  v44 = (unsigned __int64)a5;
  v43 = (unsigned __int64)a6;
  v42 = a7;
  v48 = a9;
  lpMem = 0;
  if ( (int)ProviderSubSystem_Common_Globals::GetNamespacePath(
              *((struct IWbemPath **)this + 7),
              (unsigned __int16 **)&lpMem) < 0 )
  {
    ApartmentInstanceProvider = -2147217402;
LABEL_74:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, ApartmentInstanceProvider);
    goto LABEL_17;
  }
  v12 = (CServerObject_StaThread *)operator new(0x280u);
  v38 = v12;
  if ( v12 )
    v13 = CServerObject_StaThread::CServerObject_StaThread(v12, *((struct WmiAllocator **)this + 3), a10);
  else
    v13 = 0;
  if ( v13 )
  {
    (*(void (__fastcall **)(CServerObject_StaThread *))(*(_QWORD *)v13 + 8LL))(v13);
    ApartmentInstanceProvider = CServerObject_StaThread::SetProviderName(v13, *((unsigned __int16 **)a10 + 221));
    if ( ApartmentInstanceProvider >= 0 )
    {
      LODWORD(v39) = -1;
      if ( (unsigned int)WmiThread<unsigned long>::Initialize((char *)v13 + 64, &v39) )
      {
        ApartmentInstanceProvider = -2147217402;
      }
      else
      {
        v46 = 0;
        ApartmentInstanceProvider = (**(__int64 (__fastcall ***)(CServerObject_StaThread *, GUID *, __int64 *))v13)(
                                      v13,
                                      &IID_IWbemProviderInit,
                                      &v46);
        if ( ApartmentInstanceProvider >= 0 )
        {
          v15 = (CServerObject_ProviderInitSink *)operator new(0x28u);
          v38 = v15;
          if ( v15 && (v20 = CServerObject_ProviderInitSink::CServerObject_ProviderInitSink(v15, v16), (v21 = v20) != 0) )
          {
            (*(void (__fastcall **)(CServerObject_ProviderInitSink *))(*(_QWORD *)v20 + 8LL))(v20);
            ApartmentInstanceProvider = CServerObject_ProviderInitSink::SinkInitialize(v21, 0);
            if ( ApartmentInstanceProvider >= 0 )
            {
              v22 = (CInterceptor_IWbemProviderInitSink *)operator new(0x20u);
              v38 = v22;
              if ( v22 )
                inited = CInterceptor_IWbemProviderInitSink::CInterceptor_IWbemProviderInitSink(
                           v22,
                           (struct IWbemProviderInitSink *)v21);
              else
                inited = 0;
              v39 = inited;
              if ( inited )
              {
                (*(void (__fastcall **)(CInterceptor_IWbemProviderInitSink *))(*(_QWORD *)inited + 8LL))(inited);
                ApartmentInstanceProvider = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, CInterceptor_IWbemProviderInitSink *))(*(_QWORD *)v46 + 24LL))(
                                              v46,
                                              0,
                                              0,
                                              0,
                                              0,
                                              0,
                                              0,
                                              inited);
                if ( ApartmentInstanceProvider >= 0 )
                {
                  CServerObject_ProviderInitSink::Wait(v21, *((_DWORD *)a10 + 430));
                  ApartmentInstanceProvider = *((_DWORD *)v21 + 6);
                  if ( ApartmentInstanceProvider >= 0 )
                  {
                    v24 = (CServerObject_StaThread *)operator new(0x78u);
                    v38 = v24;
                    if ( v24 )
                      v25 = (struct IWbemServices *)CInterceptor_IWbemServices_Interceptor::CInterceptor_IWbemServices_Interceptor(
                                                      (__int64)v24,
                                                      *((_QWORD *)this + 3),
                                                      *((_QWORD *)this + 9));
                    else
                      v25 = 0;
                    v47 = v25;
                    if ( v25 )
                    {
                      ((void (__fastcall *)(struct IWbemServices *))v25->lpVtbl->AddRef)(v25);
                      ApartmentInstanceProvider = CServerObject_StaThread::GetApartmentInstanceProvider(
                                                    v13,
                                                    a4,
                                                    (const unsigned __int16 *)(v44
                                                                             & -(__int64)(*((_DWORD *)a10 + 414) != 0)),
                                                    (const unsigned __int16 *)(v43
                                                                             & -(__int64)(*((_DWORD *)a10 + 415) != 0)),
                                                    *((const unsigned __int16 **)this + 6),
                                                    *((struct IWbemPath **)this + 7),
                                                    v25,
                                                    v40[0],
                                                    v45,
                                                    v42,
                                                    a10);
                      if ( ApartmentInstanceProvider >= 0 )
                      {
                        v42 = 0;
                        ApartmentInstanceProvider = (**(__int64 (__fastcall ***)(CServerObject_StaThread *, GUID *, unsigned __int16 **))v13)(
                                                      v13,
                                                      &IID_IUnknown,
                                                      &v42);
                        if ( ApartmentInstanceProvider >= 0 )
                        {
                          pguid = 0;
                          ApartmentInstanceProvider = CoCreateGuid(&pguid);
                          if ( ApartmentInstanceProvider >= 0 )
                          {
                            v26 = (CInterceptor_IWbemSyncProvider *)operator new(0x368u);
                            v38 = v26;
                            if ( v26 )
                              v27 = CInterceptor_IWbemSyncProvider::CInterceptor_IWbemSyncProvider(
                                      v26,
                                      *((struct WmiAllocator **)this + 3),
                                      (__int64)v42,
                                      (__int64)v25,
                                      ProviderSubSystem_Globals::s_SyncProviderController,
                                      v45,
                                      (__int64)a10,
                                      (__int64)&pguid);
                            else
                              v27 = 0;
                            if ( v27 )
                            {
                              (*(void (__fastcall **)(CInterceptor_IWbemSyncProvider *))(*(_QWORD *)v27 + 8LL))(v27);
                              v38 = 0;
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)ProviderSubSystem_Globals::s_SyncProviderController
                                                              + 48LL))(ProviderSubSystem_Globals::s_SyncProviderController);
                              v28 = (*(unsigned int (__fastcall **)(__int64, __int64, CServerObject_StaThread **))(*(_QWORD *)ProviderSubSystem_Globals::s_SyncProviderController + 64LL))(
                                      ProviderSubSystem_Globals::s_SyncProviderController,
                                      (__int64)v27 + 176,
                                      &v38) == 0;
                              v29 = *(void (**)(void))(*(_QWORD *)ProviderSubSystem_Globals::s_SyncProviderController
                                                     + 56LL);
                              if ( v28 )
                              {
                                v29();
                                *(_QWORD *)v40 = 0;
                                ApartmentInstanceProvider = (**(__int64 (__fastcall ***)(CInterceptor_IWbemSyncProvider *, GUID *, int *))v27)(
                                                              v27,
                                                              &IID__IWmiProviderInitialize,
                                                              v40);
                                if ( ApartmentInstanceProvider >= 0 )
                                {
                                  v30 = (CServerObject_ProviderInitSink *)operator new(0x28u);
                                  v49 = v30;
                                  if ( v30
                                    && (v32 = CServerObject_ProviderInitSink::CServerObject_ProviderInitSink(v30, v31),
                                        (v33 = v32) != 0) )
                                  {
                                    (*(void (__fastcall **)(CServerObject_ProviderInitSink *))(*(_QWORD *)v32 + 8LL))(v32);
                                    ApartmentInstanceProvider = CServerObject_ProviderInitSink::SinkInitialize(v33, 0);
                                    if ( ApartmentInstanceProvider >= 0 )
                                    {
                                      v34 = (CInterceptor_IWbemProviderInitSink *)operator new(0x20u);
                                      v49 = v34;
                                      if ( v34 )
                                        v35 = CInterceptor_IWbemProviderInitSink::CInterceptor_IWbemProviderInitSink(
                                                v34,
                                                (struct IWbemProviderInitSink *)v33);
                                      else
                                        v35 = 0;
                                      if ( v35 )
                                      {
                                        (*(void (__fastcall **)(CInterceptor_IWbemProviderInitSink *))(*(_QWORD *)v35 + 8LL))(v35);
                                        ApartmentInstanceProvider = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IWbemContext *, struct _GUID *, unsigned __int64, unsigned __int64, void *, _QWORD, _QWORD, CInterceptor_IWbemProviderInitSink *))(**(_QWORD **)v40 + 24LL))(
                                                                      *(_QWORD *)v40,
                                                                      0,
                                                                      v45,
                                                                      a4,
                                                                      v44 & -(__int64)(*((_DWORD *)a10 + 414) != 0),
                                                                      v43 & -(__int64)(*((_DWORD *)a10 + 415) != 0),
                                                                      lpMem,
                                                                      0,
                                                                      0,
                                                                      v35);
                                        if ( ApartmentInstanceProvider >= 0 )
                                        {
                                          CServerObject_ProviderInitSink::Wait(v33, *((_DWORD *)a10 + 430));
                                          ApartmentInstanceProvider = *((_DWORD *)v33 + 6);
                                          if ( ApartmentInstanceProvider >= 0 )
                                            ApartmentInstanceProvider = (**(__int64 (__fastcall ***)(CInterceptor_IWbemSyncProvider *, GUID *, void **))v27)(
                                                                          v27,
                                                                          &IID_IUnknown,
                                                                          v48);
                                        }
                                        (*(void (__fastcall **)(CInterceptor_IWbemProviderInitSink *))(*(_QWORD *)v35 + 16LL))(v35);
                                      }
                                      else
                                      {
                                        ApartmentInstanceProvider = -2147217402;
                                      }
                                      inited = v39;
                                    }
                                    (*(void (__fastcall **)(CServerObject_ProviderInitSink *))(*(_QWORD *)v33 + 16LL))(v33);
                                  }
                                  else
                                  {
                                    ApartmentInstanceProvider = -2147217402;
                                  }
                                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v40 + 16LL))(*(_QWORD *)v40);
                                  v25 = v47;
                                }
                              }
                              else
                              {
                                v29();
                                ApartmentInstanceProvider = -2147217402;
                              }
                              CInterceptor_IWbemSyncProvider::SetInitialized(v27, ApartmentInstanceProvider);
                              (*(void (__fastcall **)(CInterceptor_IWbemSyncProvider *))(*(_QWORD *)v27 + 16LL))(v27);
                            }
                            else
                            {
                              ApartmentInstanceProvider = -2147217402;
                            }
                          }
                          (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v42 + 16LL))(v42);
                        }
                      }
                      ((void (__fastcall *)(struct IWbemServices *))v25->lpVtbl->Release)(v25);
                    }
                    else
                    {
                      ApartmentInstanceProvider = -2147217402;
                    }
                    v10 = a4;
                  }
                }
                (*(void (__fastcall **)(CInterceptor_IWbemProviderInitSink *))(*(_QWORD *)inited + 16LL))(inited);
              }
              else
              {
                ApartmentInstanceProvider = -2147217402;
              }
            }
            (*(void (__fastcall **)(CServerObject_ProviderInitSink *))(*(_QWORD *)v21 + 16LL))(v21);
          }
          else
          {
            ApartmentInstanceProvider = -2147217402;
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
        }
      }
    }
    (*(void (__fastcall **)(CServerObject_StaThread *))(*(_QWORD *)v13 + 16LL))(v13);
  }
  else
  {
    ApartmentInstanceProvider = -2147217402;
  }
  if ( v10 )
    StringFromGUID2(v10, sz, 78);
  v17 = *((_QWORD *)a10 + 6);
  if ( ApartmentInstanceProvider < 0 )
    WmiSetAndCommitObject(
      qword_140061378,
      1,
      lpMem,
      *((_QWORD *)a10 + 8),
      v44,
      v43,
      (unsigned __int64)sz & -(__int64)(a4 != 0),
      v17);
  else
    WmiSetAndCommitObject(
      qword_140061370,
      1,
      lpMem,
      *((_QWORD *)a10 + 8),
      v44,
      v43,
      (unsigned __int64)sz & -(__int64)(a4 != 0),
      v17);
  CServerObject_RawFactory::ReportProviderStartedEvent(v18, ApartmentInstanceProvider, a10);
  operator delete(lpMem);
  if ( ApartmentInstanceProvider < 0 )
    goto LABEL_74;
LABEL_17:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids,
      (unsigned int)ApartmentInstanceProvider);
  }
  return (unsigned int)ApartmentInstanceProvider;
}

```

## disassembly

```asm
0x14001d55c  push    rbp
0x14001d55e  push    rbx
0x14001d55f  push    rsi
0x14001d560  push    rdi
0x14001d561  push    r12
0x14001d563  push    r13
0x14001d565  push    r14
0x14001d567  push    r15
0x14001d569  lea     rbp, [rsp-0B8h]
0x14001d571  sub     rsp, 1B8h
0x14001d578  mov     rax, cs:__security_cookie
0x14001d57f  xor     rax, rsp
0x14001d582  mov     [rbp+0F0h+var_50], rax
0x14001d589  mov     r14, r9
0x14001d58c  mov     [rbp+0F0h+var_170], r9
0x14001d590  mov     [rbp+0F0h+var_130], r8
0x14001d594  mov     [rbp+0F0h+var_158], edx
0x14001d597  mov     r15, rcx
0x14001d59a  mov     rax, [rbp+0F0h+arg_20]
0x14001d5a1  mov     [rbp+0F0h+var_138], rax
0x14001d5a5  mov     rax, [rbp+0F0h+arg_28]
0x14001d5ac  mov     [rbp+0F0h+var_140], rax
0x14001d5b0  mov     rax, [rbp+0F0h+arg_30]
0x14001d5b7  mov     [rbp+0F0h+var_148], rax
0x14001d5bb  mov     rax, [rbp+0F0h+arg_40]
0x14001d5c2  mov     [rbp+0F0h+var_118], rax
0x14001d5c6  mov     rdi, [rbp+0F0h+arg_48]
0x14001d5cd  mov     [rbp+0F0h+lpMem], 0
0x14001d5d5  lea     rdx, [rbp+0F0h+lpMem]; unsigned __int16 **
0x14001d5d9  mov     rcx, [rcx+38h]; struct IWbemPath *
0x14001d5dd  call    ?GetNamespacePath@ProviderSubSystem_Common_Globals@@SAJPEAUIWbemPath@@AEAPEAG@Z; ProviderSubSystem_Common_Globals::GetNamespacePath(IWbemPath *,ushort * &)
0x14001d5e2  test    eax, eax
0x14001d5e4  js      loc_14001DD7F
0x14001d5ea  mov     ecx, 280h; dwBytes
0x14001d5ef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001d5f4  mov     [rbp+0F0h+var_168], rax
0x14001d5f8  test    rax, rax
0x14001d5fb  jz      loc_14001D7D7
0x14001d601  mov     r8, rdi; struct CServerObject_ProviderRegistrationV1 *
0x14001d604  mov     rdx, [r15+18h]; struct WmiAllocator *
0x14001d608  mov     rcx, rax; this
0x14001d60b  call    ??0CServerObject_StaThread@@QEAA@AEAVWmiAllocator@@AEAVCServerObject_ProviderRegistrationV1@@@Z; CServerObject_StaThread::CServerObject_StaThread(WmiAllocator &,CServerObject_ProviderRegistrationV1 &)
0x14001d610  mov     rsi, rax
0x14001d613  test    rsi, rsi
0x14001d616  jz      loc_14001DCCD
0x14001d61c  mov     rax, [rsi]
0x14001d61f  mov     rcx, rsi
0x14001d622  mov     rax, [rax+8]
0x14001d626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d62b  mov     rdx, [rdi+6E8h]; unsigned __int16 *
0x14001d632  mov     rcx, rsi; this
0x14001d635  call    ?SetProviderName@CServerObject_StaThread@@QEAAJPEAG@Z; CServerObject_StaThread::SetProviderName(ushort *)
0x14001d63a  mov     ebx, eax
0x14001d63c  test    eax, eax
0x14001d63e  js      short loc_14001D6AF
0x14001d640  mov     dword ptr [rbp+0F0h+var_160], 0FFFFFFFFh
0x14001d647  lea     rcx, [rsi+40h]
0x14001d64b  lea     rdx, [rbp+0F0h+var_160]
0x14001d64f  call    ?Initialize@?$WmiThread@K@@UEAA?AW4WmiStatusCode@@AEBK@Z; WmiThread<ulong>::Initialize(ulong const &)
0x14001d654  test    eax, eax
0x14001d656  jnz     loc_14001DCC3
0x14001d65c  mov     [rbp+0F0h+var_128], 0
0x14001d664  mov     rax, [rsi]
0x14001d667  lea     r8, [rbp+0F0h+var_128]
0x14001d66b  lea     rdx, IID_IWbemProviderInit
0x14001d672  mov     rcx, rsi
0x14001d675  mov     rax, [rax]
0x14001d678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d67d  mov     ebx, eax
0x14001d67f  test    eax, eax
0x14001d681  js      short loc_14001D6AF
0x14001d683  mov     ecx, 28h ; '('; dwBytes
0x14001d688  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001d68d  mov     [rbp+0F0h+var_168], rax
0x14001d691  test    rax, rax
0x14001d694  jnz     loc_14001D804
0x14001d69a  mov     ebx, 80041006h
0x14001d69f  mov     rcx, [rbp+0F0h+var_128]
0x14001d6a3  mov     rax, [rcx]
0x14001d6a6  mov     rax, [rax+10h]
0x14001d6aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d6af  mov     rax, [rsi]
0x14001d6b2  mov     rcx, rsi
0x14001d6b5  mov     rax, [rax+10h]
0x14001d6b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d6be  test    r14, r14
0x14001d6c1  jnz     loc_14001DCD7
0x14001d6c7  mov     r14d, [rdi+1Ch]
0x14001d6cb  mov     r15d, [rdi+18h]
0x14001d6cf  mov     ecx, [rdi+24h]
0x14001d6d2  lea     r11, [rdi+250h]
0x14001d6d9  lea     rsi, [rdi+48h]
0x14001d6dd  lea     r12, [rdi+458h]
0x14001d6e4  mov     r9d, [rdi+20h]
0x14001d6e8  mov     r13, [rdi+30h]
0x14001d6ec  xor     eax, eax
0x14001d6ee  lea     r10d, [rax+1]
0x14001d6f2  test    ebx, ebx
0x14001d6f4  js      loc_14001DCEF
0x14001d6fa  cmp     ecx, r10d
0x14001d6fd  cmovnz  r11, rax
0x14001d701  cmp     r9d, r10d
0x14001d704  cmovnz  rsi, rax
0x14001d708  xor     r8d, r8d
0x14001d70b  cmp     ecx, r10d
0x14001d70e  setnz   r8b
0x14001d712  sub     r8d, r10d
0x14001d715  xor     ecx, ecx
0x14001d717  cmp     r9d, r10d
0x14001d71a  setnz   cl
0x14001d71d  sub     ecx, r10d
0x14001d720  neg     [rbp+0F0h+var_170]
0x14001d724  sbb     rax, rax
0x14001d727  lea     rdx, [rbp+0F0h+sz]
0x14001d72b  and     rax, rdx
0x14001d72e  mov     [rsp+1F0h+var_180], r14d
0x14001d733  mov     [rsp+1F0h+var_188], r15d
0x14001d738  mov     [rsp+1F0h+var_190], r11
0x14001d73d  mov     [rsp+1F0h+var_198], rsi
0x14001d742  mov     dword ptr [rsp+1F0h+var_1A0], r8d
0x14001d747  mov     dword ptr [rsp+1F0h+var_1A8], ecx
0x14001d74b  mov     [rsp+1F0h+var_1B0], r12
0x14001d750  mov     [rsp+1F0h+var_1B8], r13
0x14001d755  mov     [rsp+1F0h+var_1C0], rax
0x14001d75a  mov     rax, [rbp+0F0h+var_140]
0x14001d75e  mov     [rsp+1F0h+var_1C8], rax
0x14001d763  mov     rax, [rbp+0F0h+var_138]
0x14001d767  mov     [rsp+1F0h+var_1D0], rax
0x14001d76c  mov     r9, [rdi+40h]
0x14001d770  mov     r8, [rbp+0F0h+lpMem]
0x14001d774  mov     edx, r10d
0x14001d777  mov     rcx, cs:qword_140061370
0x14001d77e  call    cs:__imp_WmiSetAndCommitObject
0x14001d784  mov     r8, rdi; struct CServerObject_ProviderRegistrationV1 *
0x14001d787  mov     edx, ebx; int
0x14001d789  call    ?ReportProviderStartedEvent@CServerObject_RawFactory@@AEAAXJAEAVCServerObject_ProviderRegistrationV1@@@Z; CServerObject_RawFactory::ReportProviderStartedEvent(long,CServerObject_ProviderRegistrationV1 &)
0x14001d78e  mov     rcx, [rbp+0F0h+lpMem]; lpMem
0x14001d792  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001d797  test    ebx, ebx
0x14001d799  js      loc_14001DD84
0x14001d79f  lea     rax, WPP_GLOBAL_Control
0x14001d7a6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d7ad  cmp     rcx, rax
0x14001d7b0  jnz     short loc_14001D7DE
0x14001d7b2  mov     eax, ebx
0x14001d7b4  mov     rcx, [rbp+0F0h+var_50]
0x14001d7bb  xor     rcx, rsp; StackCookie
0x14001d7be  call    __security_check_cookie
0x14001d7c3  add     rsp, 1B8h
0x14001d7ca  pop     r15
0x14001d7cc  pop     r14
0x14001d7ce  pop     r13
0x14001d7d0  pop     r12
0x14001d7d2  pop     rdi
0x14001d7d3  pop     rsi
0x14001d7d4  pop     rbx
0x14001d7d5  pop     rbp
0x14001d7d6  retn
0x14001d7d7  xor     esi, esi
0x14001d7d9  jmp     loc_14001D613
0x14001d7de  test    byte ptr [rcx+1Ch], 4
0x14001d7e2  jz      short loc_14001D7B2
0x14001d7e4  cmp     byte ptr [rcx+19h], 2
0x14001d7e8  jb      short loc_14001D7B2
0x14001d7ea  mov     edx, 10h
0x14001d7ef  mov     r9d, ebx
0x14001d7f2  lea     r8, WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids
0x14001d7f9  mov     rcx, [rcx+10h]
0x14001d7fd  call    WPP_SF_d
0x14001d802  jmp     short loc_14001D7B2
0x14001d804  mov     rcx, rax; this
0x14001d807  call    ??0CServerObject_ProviderInitSink@@QEAA@PEAU_SECURITY_DESCRIPTOR@@@Z; CServerObject_ProviderInitSink::CServerObject_ProviderInitSink(_SECURITY_DESCRIPTOR *)
0x14001d80c  mov     r13, rax
0x14001d80f  test    rax, rax
0x14001d812  jz      loc_14001D69A
0x14001d818  mov     rcx, [rax]
0x14001d81b  mov     rax, [rcx+8]
0x14001d81f  mov     rcx, r13
0x14001d822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d827  xor     edx, edx; struct _SECURITY_DESCRIPTOR *
0x14001d829  mov     rcx, r13; this
0x14001d82c  call    ?SinkInitialize@CServerObject_ProviderInitSink@@QEAAJPEAU_SECURITY_DESCRIPTOR@@@Z; CServerObject_ProviderInitSink::SinkInitialize(_SECURITY_DESCRIPTOR *)
0x14001d831  mov     ebx, eax
0x14001d833  test    eax, eax
0x14001d835  js      loc_14001DAE0
0x14001d83b  mov     ecx, 20h ; ' '; dwBytes
0x14001d840  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001d845  mov     [rbp+0F0h+var_168], rax
0x14001d849  test    rax, rax
0x14001d84c  jnz     loc_14001DABD
0x14001d852  xor     r12d, r12d
0x14001d855  mov     [rbp+0F0h+var_160], r12
0x14001d859  xor     ebx, ebx
0x14001d85b  test    r12, r12
0x14001d85e  jz      loc_14001DCB9
0x14001d864  mov     rax, [r12]
0x14001d868  mov     rcx, r12
0x14001d86b  mov     rax, [rax+8]
0x14001d86f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d874  mov     rcx, [rbp+0F0h+var_128]
0x14001d878  mov     rax, [rcx]
0x14001d87b  mov     [rsp+1F0h+var_1B8], r12
0x14001d880  mov     [rsp+1F0h+var_1C0], rbx
0x14001d885  mov     [rsp+1F0h+var_1C8], rbx
0x14001d88a  mov     [rsp+1F0h+var_1D0], rbx
0x14001d88f  xor     r9d, r9d
0x14001d892  xor     r8d, r8d
0x14001d895  xor     edx, edx
0x14001d897  mov     rax, [rax+18h]
0x14001d89b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d8a0  mov     ebx, eax
0x14001d8a2  test    eax, eax
0x14001d8a4  js      loc_14001DAD0
0x14001d8aa  mov     edx, [rdi+6B8h]; unsigned int
0x14001d8b0  mov     rcx, r13; this
0x14001d8b3  call    ?Wait@CServerObject_ProviderInitSink@@QEAAXK@Z; CServerObject_ProviderInitSink::Wait(ulong)
0x14001d8b8  mov     ebx, [r13+18h]
0x14001d8bc  test    ebx, ebx
0x14001d8be  js      loc_14001DAD0
0x14001d8c4  mov     ecx, 78h ; 'x'; dwBytes
0x14001d8c9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001d8ce  mov     [rbp+0F0h+var_168], rax
0x14001d8d2  test    rax, rax
0x14001d8d5  jz      loc_14001DC6F
0x14001d8db  mov     r8, [r15+48h]
0x14001d8df  mov     rdx, [r15+18h]
0x14001d8e3  mov     rcx, rax
0x14001d8e6  call    ??0CInterceptor_IWbemServices_Interceptor@@QEAA@AEAVWmiAllocator@@PEAUIWbemServices@@W4Enum_ThreadingModel@@@Z; CInterceptor_IWbemServices_Interceptor::CInterceptor_IWbemServices_Interceptor(WmiAllocator &,IWbemServices *,Enum_ThreadingModel)
0x14001d8eb  mov     r14, rax
0x14001d8ee  mov     [rbp+0F0h+var_120], r14
0x14001d8f2  test    r14, r14
0x14001d8f5  jz      loc_14001DC86
0x14001d8fb  mov     rax, [r14]
0x14001d8fe  mov     rcx, r14
0x14001d901  mov     rax, [rax+8]
0x14001d905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d90a  mov     eax, [rdi+67Ch]
0x14001d910  neg     eax
0x14001d912  sbb     r9, r9
0x14001d915  and     r9, [rbp+0F0h+var_140]; unsigned __int16 *
0x14001d919  mov     eax, [rdi+678h]
0x14001d91f  neg     eax
0x14001d921  sbb     r8, r8
0x14001d924  and     r8, [rbp+0F0h+var_138]; unsigned __int16 *
0x14001d928  mov     [rsp+1F0h+var_1A0], rdi; struct CServerObject_ProviderRegistrationV1 *
0x14001d92d  mov     rax, [rbp+0F0h+var_148]
0x14001d931  mov     [rsp+1F0h+var_1A8], rax; unsigned __int16 *
0x14001d936  mov     rax, [rbp+0F0h+var_130]
0x14001d93a  mov     [rsp+1F0h+var_1B0], rax; struct IWbemContext *
0x14001d93f  mov     eax, [rbp+0F0h+var_158]
0x14001d942  mov     dword ptr [rsp+1F0h+var_1B8], eax; int
0x14001d946  mov     [rsp+1F0h+var_1C0], r14; struct IWbemServices *
0x14001d94b  mov     rax, [r15+38h]
0x14001d94f  mov     [rsp+1F0h+var_1C8], rax; struct IWbemPath *
0x14001d954  mov     rax, [r15+30h]
0x14001d958  mov     [rsp+1F0h+var_1D0], rax; unsigned __int16 *
0x14001d95d  mov     rdx, [rbp+0F0h+var_170]; struct _GUID *
0x14001d961  mov     rcx, rsi; this
0x14001d964  call    ?GetApartmentInstanceProvider@CServerObject_StaThread@@QEAAJPEAU_GUID@@PEBG11PEAUIWbemPath@@PEAUIWbemServices@@JPEAUIWbemContext@@1AEAVCServerObject_ProviderRegistrationV1@@@Z; CServerObject_StaThread::GetApartmentInstanceProvider(_GUID *,ushort const *,ushort const *,ushort const *,IWbemPath *,IWbemServices *,long,IWbemContext *,ushort const *,CServerObject_ProviderRegistrationV1 &)
0x14001d969  mov     ebx, eax
0x14001d96b  test    eax, eax
0x14001d96d  js      loc_14001DC57
0x14001d973  mov     [rbp+0F0h+var_148], 0
0x14001d97b  mov     rax, [rsi]
0x14001d97e  lea     r8, [rbp+0F0h+var_148]
0x14001d982  lea     rdx, IID_IUnknown
0x14001d989  mov     rcx, rsi
0x14001d98c  mov     rax, [rax]
0x14001d98f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d994  mov     ebx, eax
0x14001d996  test    eax, eax
0x14001d998  js      loc_14001DC57
0x14001d99e  xorps   xmm0, xmm0
0x14001d9a1  movups  xmmword ptr [rbp+0F0h+pguid.Data1], xmm0
0x14001d9a5  lea     rcx, [rbp+0F0h+pguid]; pguid
0x14001d9a9  call    cs:__imp_CoCreateGuid
0x14001d9af  mov     ebx, eax
0x14001d9b1  test    eax, eax
0x14001d9b3  js      loc_14001DC47
0x14001d9b9  mov     ecx, 368h; dwBytes
0x14001d9be  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001d9c3  mov     [rbp+0F0h+var_168], rax
0x14001d9c7  test    rax, rax
0x14001d9ca  jz      loc_14001DC7E
0x14001d9d0  mov     rcx, cs:?s_SyncProviderController@ProviderSubSystem_Globals@@2PEAV?$WmiContainerController@U_GUID@@@@EA; WmiContainerController<_GUID> * ProviderSubSystem_Globals::s_SyncProviderController
0x14001d9d7  lea     rdx, [rbp+0F0h+pguid]
0x14001d9db  mov     [rsp+1F0h+var_1B8], rdx; __int64
0x14001d9e0  mov     [rsp+1F0h+var_1C0], rdi; __int64
0x14001d9e5  mov     rdx, [rbp+0F0h+var_130]
0x14001d9e9  mov     [rsp+1F0h+var_1C8], rdx; __int64
0x14001d9ee  mov     [rsp+1F0h+var_1D0], rcx; __int64
0x14001d9f3  mov     r9, r14
0x14001d9f6  mov     r8, [rbp+0F0h+var_148]
0x14001d9fa  mov     rdx, [r15+18h]
0x14001d9fe  mov     rcx, rax; this
0x14001da01  call    ??0CInterceptor_IWbemSyncProvider@@QEAA@AEAVWmiAllocator@@PEAUIUnknown@@PEAUIWbemServices@@PEAV?$WmiContainerController@U_GUID@@@@PEAUIWbemContext@@AEAVCServerObject_ProviderRegistrationV1@@AEAU_GUID@@@Z; CInterceptor_IWbemSyncProvider::CInterceptor_IWbemSyncProvider(WmiAllocator &,IUnknown *,IWbemServices *,WmiContainerController<_GUID> *,IWbemContext *,CServerObject_ProviderRegistrationV1 &,_GUID &)
0x14001da06  mov     r15, rax
0x14001da09  test    r15, r15
0x14001da0c  jz      loc_14001DC77
0x14001da12  mov     rax, [r15]
  ... truncated ...
```
