# CServerObject_StaThread::InitializeProvider(_GUID *,ushort const *,ushort const *,ushort const *,IWbemPath *,IWbemServices *,long,IWbemContext *,ushort const *,CServerObject_ProviderRegistrationV1 &)

- ea: `0x14001cbf4`
- end: `0x14001d556`
- name: `?InitializeProvider@CServerObject_StaThread@@QEAAJPEAU_GUID@@PEBG11PEAUIWbemPath@@PEAUIWbemServices@@JPEAUIWbemContext@@1AEAVCServerObject_ProviderRegistrationV1@@@Z`
- size: `2402`
- prototype: `int(CServerObject_StaThread *__hidden this, struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct IWbemPath *, struct IWbemServices *, int, struct IWbemContext *, const unsigned __int16 *, struct CServerObject_ProviderRegistrationV1 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14001e268`

## callees

- `0x1400053dc`
- `0x1400058dc`
- `0x140005984`
- `0x140006c64`
- `0x140006d34`
- `0x140006d5c`
- `0x140006eec`
- `0x14000a530`
- `0x14001b698`
- `0x14001ca74`
- `0x14001cbf4`
- `0x14001e00c`
- `0x14001ebc4`
- `0x1400234b8`
- `0x14004612c`
- `0x140046430`
- `0x140048010`

## import_xrefs

- `NCObjAPI!WmiSetAndCommitObject` at `0x14001cf9a`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14001d08f`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14001d475`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14001d4d4`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14001cf9a`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14001d08f`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14001d475`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14001d4d4`
- `wbemcomn!GetMemLogObject` at `0x14001d286`
- `wbemcomn!GetMemLogObject` at `0x14001d286`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001d291`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001d291`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x14001d150`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x14001d150`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14001cff0`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14001d0ba`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14001d21c`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14001d39a`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14001cff0`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14001d0ba`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14001d21c`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14001d39a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14001cf28`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14001d11d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14001d240`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14001d36d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14001d3eb`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14001cf28`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14001d11d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14001d240`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14001d36d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14001d3eb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CServerObject_StaThread::InitializeProvider(
        CServerObject_StaThread *this,
        struct _GUID *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        struct IWbemPath *a6,
        struct IWbemServices *a7,
        int a8,
        struct IWbemContext *a9,
        const unsigned __int16 *a10,
        struct CServerObject_ProviderRegistrationV1 *a11)
{
  int v13; // r15d
  HRESULT v14; // ebx
  int v15; // eax
  int v16; // r12d
  struct IServerSecurity *v18; // rax
  struct _SECURITY_DESCRIPTOR *v19; // rdx
  struct IServerSecurity *v20; // rax
  struct _SECURITY_DESCRIPTOR *v21; // rdx
  CServerObject_ProviderInitSink *inited; // rax
  CServerObject_ProviderInitSink *v23; // rsi
  struct IServerSecurity *v24; // rax
  CInterceptor_IWbemProviderInitSink *v25; // r14
  CServerObject_ProviderInitSink *v26; // rax
  CServerObject_ProviderInitSink *v27; // rsi
  struct IServerSecurity *v28; // rax
  CInterceptor_IWbemProviderInitSink *v29; // r14
  int Proxy; // eax
  _DWORD *v31; // r15
  _DWORD *v32; // r12
  unsigned __int16 *v33; // rdx
  unsigned __int16 *v34; // r8
  unsigned __int16 *v35; // r9
  struct IUnknown *v36; // r12
  unsigned int v37; // eax
  unsigned int v38; // edx
  int v39; // eax
  int v40; // eax
  struct IUnknown *v41; // rsi
  unsigned int CurrentImpersonationLevel; // eax
  unsigned int v43; // edx
  CMemoryLog *MemLogObject; // rax
  int v45; // eax
  _DWORD *v46; // r15
  struct IUnknown *v47; // r15
  unsigned int v48; // eax
  unsigned int v49; // edx
  unsigned int v50; // [rsp+20h] [rbp-E0h]
  unsigned int v51; // [rsp+28h] [rbp-D8h]
  unsigned int v52; // [rsp+30h] [rbp-D0h]
  int v53; // [rsp+38h] [rbp-C8h]
  int v54; // [rsp+50h] [rbp-B0h] BYREF
  struct IServerSecurity *v55; // [rsp+58h] [rbp-A8h] BYREF
  struct IUnknown *v56; // [rsp+60h] [rbp-A0h] BYREF
  struct IUnknown *v57; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v58; // [rsp+70h] [rbp-90h]
  const unsigned __int16 *v59; // [rsp+78h] [rbp-88h]
  struct IUnknown *ppInterface; // [rsp+80h] [rbp-80h] BYREF
  struct IUnknown *v61; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v62; // [rsp+90h] [rbp-70h]
  struct IWbemContext *v63; // [rsp+98h] [rbp-68h]
  struct IWbemServices *v64; // [rsp+A0h] [rbp-60h]
  OLECHAR sz[80]; // [rsp+B0h] [rbp-50h] BYREF

  v58 = (unsigned __int64)a4;
  v62 = (unsigned __int64)a3;
  v59 = a5;
  v64 = a7;
  v63 = a9;
  v13 = 0;
  v14 = 0;
  if ( a2 )
    StringFromGUID2(a2, sz, 78);
  if ( *((_DWORD *)a11 + 544) )
  {
    v57 = 0;
    v39 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, struct IUnknown **))this + 60))(
            *((_QWORD *)this + 60),
            &IID_IWbemProviderIdentity,
            &v57);
    if ( v39 < 0 )
    {
      if ( v39 != -2147467262 )
      {
        v14 = v39;
LABEL_68:
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, v14);
        goto LABEL_10;
      }
    }
    else
    {
      v54 = 0;
      v55 = 0;
      ppInterface = 0;
      v14 = ProviderSubSystem_Common_Globals::BeginImpersonation(
              (struct IUnknown **)&v55,
              (struct IServerSecurity **)&ppInterface,
              &v54,
              0);
      if ( v14 >= 0 )
      {
        LODWORD(v56) = 0;
        v61 = 0;
        v40 = ProviderSubSystem_Common_Globals::SetProxyState(&IID_IWbemProviderIdentity, v57, &v61, (int *)&v56);
        v14 = v40;
        if ( v40 == -2147217406 )
        {
          v14 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, _QWORD))v57->lpVtbl[1].QueryInterface)(
                  v57,
                  0,
                  *((_QWORD *)a11 + 226));
        }
        else if ( v40 >= 0 )
        {
          v41 = v61;
          CurrentImpersonationLevel = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
          v14 = ProviderSubSystem_Common_Globals::SetCloaking(v41, v43, CurrentImpersonationLevel);
          if ( v14 >= 0 )
          {
            if ( CoImpersonateClient() < 0 )
            {
              v14 = -2147217405;
            }
            else
            {
              v14 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, _QWORD))v41->lpVtbl[1].QueryInterface)(
                      v41,
                      0,
                      *((_QWORD *)a11 + 226));
              CoRevertToSelf();
            }
          }
          ProviderSubSystem_Common_Globals::RevertProxyState(v61, (int)v56);
        }
        ProviderSubSystem_Common_Globals::EndImpersonation(
          (struct IUnknown *)v55,
          (struct IServerSecurity *)ppInterface,
          v54);
      }
      ((void (__fastcall *)(struct IUnknown *))v57->lpVtbl->Release)(v57);
      if ( v14 < 0 )
        goto LABEL_68;
    }
  }
  v57 = 0;
  v15 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, struct IUnknown **))this + 60))(
          *((_QWORD *)this + 60),
          &IID_IWbemProviderInit,
          &v57);
  v16 = v15;
  if ( v15 >= 0 )
  {
    if ( !*((_DWORD *)a11 + 414) || !*((_DWORD *)a11 + 413) )
      goto LABEL_6;
    v20 = (struct IServerSecurity *)operator new(0x28u);
    v55 = v20;
    if ( !v20
      || (inited = CServerObject_ProviderInitSink::CServerObject_ProviderInitSink(
                     (CServerObject_ProviderInitSink *)v20,
                     v21),
          (v23 = inited) == 0) )
    {
      v14 = -2147217402;
      goto LABEL_6;
    }
    (*(void (__fastcall **)(CServerObject_ProviderInitSink *))(*(_QWORD *)inited + 8LL))(inited);
    v14 = CServerObject_ProviderInitSink::SinkInitialize(v23, *((struct _SECURITY_DESCRIPTOR **)a11 + 230));
    if ( v14 < 0 )
    {
LABEL_89:
      (*(void (__fastcall **)(CServerObject_ProviderInitSink *))(*(_QWORD *)v23 + 16LL))(v23);
      goto LABEL_6;
    }
    v24 = (struct IServerSecurity *)operator new(0x20u);
    v55 = v24;
    if ( v24 )
      v25 = CInterceptor_IWbemProviderInitSink::CInterceptor_IWbemProviderInitSink(
              (CInterceptor_IWbemProviderInitSink *)v24,
              (struct IWbemProviderInitSink *)v23);
    else
      v25 = 0;
    if ( !v25 )
    {
      v14 = -2147217402;
      goto LABEL_89;
    }
    (*(void (__fastcall **)(CInterceptor_IWbemProviderInitSink *))(*(_QWORD *)v25 + 8LL))(v25);
    LODWORD(v56) = 0;
    ppInterface = 0;
    v55 = 0;
    v14 = ProviderSubSystem_Common_Globals::BeginImpersonation(&ppInterface, &v55, (int *)&v56, 0);
    if ( v14 < 0 )
    {
LABEL_87:
      (*(void (__fastcall **)(CInterceptor_IWbemProviderInitSink *))(*(_QWORD *)v25 + 16LL))(v25);
      goto LABEL_89;
    }
    v54 = 0;
    v61 = 0;
    v45 = ProviderSubSystem_Common_Globals::SetProxyState(&IID_IWbemProviderInit, v57, &v61, &v54);
    v14 = v45;
    if ( v45 == -2147217406 )
    {
      v46 = (_DWORD *)((char *)a11 + 1660);
      v53 = (int)v25;
      v14 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, _QWORD, const unsigned __int16 *, unsigned __int64, struct IWbemServices *, struct IWbemContext *))v57->lpVtbl[1].QueryInterface)(
              v57,
              0,
              0,
              v59,
              v58 & -(__int64)(*((_DWORD *)a11 + 415) != 0),
              v64,
              v63);
      CoRevertToSelf();
    }
    else
    {
      if ( v45 < 0 )
        goto LABEL_85;
      v47 = v61;
      v48 = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
      v14 = ProviderSubSystem_Common_Globals::SetCloaking(v47, v49, v48);
      if ( v14 >= 0 )
      {
        if ( CoImpersonateClient() < 0 )
        {
          v14 = -2147217405;
        }
        else
        {
          v53 = (int)v25;
          v14 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, _QWORD, const unsigned __int16 *, unsigned __int64, struct IWbemServices *, struct IWbemContext *))v47->lpVtbl[1].QueryInterface)(
                  v47,
                  0,
                  0,
                  v59,
                  v58 & -(__int64)(*((_DWORD *)a11 + 415) != 0),
                  v64,
                  v63);
          CoRevertToSelf();
        }
      }
      ProviderSubSystem_Common_Globals::RevertProxyState(v61, v54);
      v46 = (_DWORD *)((char *)a11 + 1660);
    }
    if ( v14 >= 0 )
    {
      CServerObject_ProviderInitSink::Wait(v23, *((_DWORD *)a11 + 430));
      v14 = *((_DWORD *)v23 + 6);
      if ( v14 >= 0 )
      {
        WmiSetAndCommitObject(
          qword_140061388,
          1,
          v59,
          *((_QWORD *)a11 + 8),
          v62 & -(__int64)(*((_DWORD *)a11 + 414) != 0),
          v58 & -(__int64)(*v46 != 0),
          (unsigned __int64)sz & -(__int64)(a2 != 0),
          v53);
LABEL_86:
        ProviderSubSystem_Common_Globals::EndImpersonation(ppInterface, v55, (int)v56);
        v13 = 0;
        goto LABEL_87;
      }
    }
LABEL_85:
    WmiSetAndCommitObject(
      qword_140061380,
      1,
      v59,
      *((_QWORD *)a11 + 8),
      v62 & -(__int64)(*((_DWORD *)a11 + 414) != 0),
      v58 & -(__int64)(*((_DWORD *)a11 + 415) != 0),
      (unsigned __int64)sz & -(__int64)(a2 != 0),
      v14);
    v14 = -2147217389;
    goto LABEL_86;
  }
  if ( v15 != -2147467262 )
  {
    v14 = v15;
    goto LABEL_7;
  }
LABEL_6:
  if ( v14 >= 0 && v16 != -2147467262 )
  {
    v18 = (struct IServerSecurity *)operator new(0x28u);
    v55 = v18;
    if ( !v18
      || (v26 = CServerObject_ProviderInitSink::CServerObject_ProviderInitSink(
                  (CServerObject_ProviderInitSink *)v18,
                  v19),
          (v27 = v26) == 0) )
    {
      v14 = -2147217402;
      goto LABEL_7;
    }
    (*(void (__fastcall **)(CServerObject_ProviderInitSink *))(*(_QWORD *)v26 + 8LL))(v26);
    v14 = CServerObject_ProviderInitSink::SinkInitialize(v27, *((struct _SECURITY_DESCRIPTOR **)a11 + 230));
    if ( v14 < 0 )
      goto LABEL_40;
    v28 = (struct IServerSecurity *)operator new(0x20u);
    v55 = v28;
    if ( v28 )
      v29 = CInterceptor_IWbemProviderInitSink::CInterceptor_IWbemProviderInitSink(
              (CInterceptor_IWbemProviderInitSink *)v28,
              (struct IWbemProviderInitSink *)v27);
    else
      v29 = 0;
    if ( !v29 )
    {
      v14 = -2147217402;
      goto LABEL_40;
    }
    (*(void (__fastcall **)(CInterceptor_IWbemProviderInitSink *))(*(_QWORD *)v29 + 8LL))(v29);
    v54 = 0;
    ppInterface = 0;
    v55 = 0;
    v14 = ProviderSubSystem_Common_Globals::BeginImpersonation(&ppInterface, &v55, &v54, 0);
    if ( v14 < 0 )
    {
LABEL_38:
      (*(void (__fastcall **)(CInterceptor_IWbemProviderInitSink *))(*(_QWORD *)v29 + 16LL))(v29);
LABEL_40:
      (*(void (__fastcall **)(CServerObject_ProviderInitSink *))(*(_QWORD *)v27 + 16LL))(v27);
      goto LABEL_7;
    }
    v56 = 0;
    Proxy = ProviderSubSystem_Common_Globals::GetProxy(&IID_IWbemProviderInit, v57, &v56);
    if ( Proxy < 0 )
    {
      if ( Proxy != -2147217406 )
      {
        v14 = -2147217398;
        goto LABEL_51;
      }
      goto LABEL_33;
    }
    v14 = CoImpersonateClient();
    if ( v14 < 0 )
    {
      v14 = -2147217405;
    }
    else
    {
      if ( ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel() - 3 > 1 )
        v14 = SetInterfaceSecurity(v56, v33, v34, v35, v50, v51, v52);
      v13 = 1;
      if ( v14 >= 0 )
      {
LABEL_49:
        if ( v14 != -2147217406 )
        {
          if ( v14 < 0 )
            goto LABEL_51;
          v36 = v56;
          v37 = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
          v14 = ProviderSubSystem_Common_Globals::SetCloaking(v36, v38, v37);
          if ( v14 >= 0 )
          {
            if ( CoImpersonateClient() < 0 )
            {
              v14 = -2147217405;
            }
            else
            {
              v53 = (int)v29;
              v14 = ((__int64 (__fastcall *)(struct IUnknown *, unsigned __int64, _QWORD, const unsigned __int16 *, unsigned __int64, struct IWbemServices *, struct IWbemContext *))v36->lpVtbl[1].QueryInterface)(
                      v36,
                      v62 & -(__int64)(*((_DWORD *)a11 + 414) != 0),
                      0,
                      v59,
                      v58 & -(__int64)(*((_DWORD *)a11 + 415) != 0),
                      v64,
                      v63);
              CoRevertToSelf();
            }
          }
          ProviderSubSystem_Common_Globals::RevertProxyState(v56, v13);
          v31 = (_DWORD *)((char *)a11 + 1660);
          v32 = (_DWORD *)((char *)a11 + 1656);
LABEL_34:
          if ( v14 >= 0 )
          {
            CServerObject_ProviderInitSink::Wait(v27, *((_DWORD *)a11 + 430));
            v14 = *((_DWORD *)v27 + 6);
            if ( v14 >= 0 )
            {
              WmiSetAndCommitObject(
                qword_140061388,
                1,
                v59,
                *((_QWORD *)a11 + 8),
                v62 & -(__int64)(*v32 != 0),
                v58 & -(__int64)(*v31 != 0),
                (unsigned __int64)sz & -(__int64)(a2 != 0),
                v53);
LABEL_37:
              ProviderSubSystem_Common_Globals::EndImpersonation(ppInterface, v55, v54);
              goto LABEL_38;
            }
          }
LABEL_51:
          WmiSetAndCommitObject(
            qword_140061380,
            1,
            v59,
            *((_QWORD *)a11 + 8),
            v62 & -(__int64)(*((_DWORD *)a11 + 414) != 0),
            v58 & -(__int64)(*((_DWORD *)a11 + 415) != 0),
            (unsigned __int64)sz & -(__int64)(a2 != 0),
            v14);
          v14 = -2147217389;
          goto LABEL_37;
        }
LABEL_33:
        v31 = (_DWORD *)((char *)a11 + 1660);
        v32 = (_DWORD *)((char *)a11 + 1656);
        v53 = (int)v29;
        v14 = ((__int64 (__fastcall *)(struct IUnknown *, unsigned __int64, _QWORD, const unsigned __int16 *, unsigned __int64, struct IWbemServices *, struct IWbemContext *))v57->lpVtbl[1].QueryInterface)(
                v57,
                v62 & -(__int64)(*((_DWORD *)a11 + 414) != 0),
                0,
                v59,
                v58 & -(__int64)(*((_DWORD *)a11 + 415) != 0),
                v64,
                v63);
        CoRevertToSelf();
        goto LABEL_34;
      }
    }
    ProviderSubSystem_Common_Globals::RevertProxyState(v56, v13);
    goto LABEL_49;
  }
LABEL_7:
  if ( v57 )
    ((void (__fastcall *)(struct IUnknown *))v57->lpVtbl->Release)(v57);
  if ( v14 < 0 )
    goto LABEL_68;
LABEL_10:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      WPP_d3ea76c96a8339db06b7a6ae92e79012_Traceguids,
      (unsigned int)v14);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14001cbf4  push    rbp
0x14001cbf6  push    rbx
0x14001cbf7  push    rsi
0x14001cbf8  push    rdi
0x14001cbf9  push    r12
0x14001cbfb  push    r13
0x14001cbfd  push    r14
0x14001cbff  push    r15
0x14001cc01  lea     rbp, [rsp-68h]
0x14001cc06  sub     rsp, 168h
0x14001cc0d  mov     rax, cs:__security_cookie
0x14001cc14  xor     rax, rsp
0x14001cc17  mov     [rbp+0A0h+var_50], rax
0x14001cc1b  mov     [rsp+1A0h+var_130], r9
0x14001cc20  mov     [rbp+0A0h+var_110], r8
0x14001cc24  mov     r13, rdx
0x14001cc27  mov     r14, rcx
0x14001cc2a  mov     rax, [rbp+0A0h+arg_20]
0x14001cc31  mov     [rsp+1A0h+var_128], rax
0x14001cc36  mov     rax, [rbp+0A0h+arg_30]
0x14001cc3d  mov     [rbp+0A0h+var_100], rax
0x14001cc41  mov     rax, [rbp+0A0h+arg_40]
0x14001cc48  mov     [rbp+0A0h+var_108], rax
0x14001cc4c  mov     rdi, [rbp+0A0h+arg_50]
0x14001cc53  xor     r15d, r15d
0x14001cc56  mov     ebx, r15d
0x14001cc59  test    rdx, rdx
0x14001cc5c  jnz     loc_14001D143
0x14001cc62  cmp     [rdi+880h], r15d
0x14001cc69  jnz     loc_14001D15B
0x14001cc6f  mov     [rsp+1A0h+var_138], r15
0x14001cc74  mov     rcx, [r14+1E0h]
0x14001cc7b  mov     rax, [rcx]
0x14001cc7e  lea     r8, [rsp+1A0h+var_138]
0x14001cc83  lea     rdx, IID_IWbemProviderInit
0x14001cc8a  mov     rax, [rax]
0x14001cc8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001cc92  mov     r12d, eax
0x14001cc95  test    eax, eax
0x14001cc97  jns     loc_14001CD23
0x14001cc9d  cmp     eax, 80004002h
0x14001cca2  jnz     loc_14001D529
0x14001cca8  test    ebx, ebx
0x14001ccaa  jns     short loc_14001CCFB
0x14001ccac  mov     rcx, [rsp+1A0h+var_138]
0x14001ccb1  test    rcx, rcx
0x14001ccb4  jnz     loc_14001CDBC
0x14001ccba  test    ebx, ebx
0x14001ccbc  js      loc_14001D286
0x14001ccc2  lea     rax, WPP_GLOBAL_Control
0x14001ccc9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ccd0  cmp     rcx, rax
0x14001ccd3  jnz     loc_14001CDCD
0x14001ccd9  mov     eax, ebx
0x14001ccdb  mov     rcx, [rbp+0A0h+var_50]
0x14001ccdf  xor     rcx, rsp; StackCookie
0x14001cce2  call    __security_check_cookie
0x14001cce7  add     rsp, 168h
0x14001ccee  pop     r15
0x14001ccf0  pop     r14
0x14001ccf2  pop     r13
0x14001ccf4  pop     r12
0x14001ccf6  pop     rdi
0x14001ccf7  pop     rsi
0x14001ccf8  pop     rbx
0x14001ccf9  pop     rbp
0x14001ccfa  retn
0x14001ccfb  cmp     r12d, 80004002h
0x14001cd02  jz      short loc_14001CCAC
0x14001cd04  mov     ecx, 28h ; '('; dwBytes
0x14001cd09  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001cd0e  mov     [rsp+1A0h+var_148], rax
0x14001cd13  test    rax, rax
0x14001cd16  jnz     loc_14001CDFE
0x14001cd1c  mov     ebx, 80041006h
0x14001cd21  jmp     short loc_14001CCAC
0x14001cd23  cmp     [rdi+678h], r15d
0x14001cd2a  jz      loc_14001CCA8
0x14001cd30  cmp     [rdi+674h], r15d
0x14001cd37  jz      loc_14001CCA8
0x14001cd3d  mov     ecx, 28h ; '('; dwBytes
0x14001cd42  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001cd47  mov     [rsp+1A0h+var_148], rax
0x14001cd4c  test    rax, rax
0x14001cd4f  jz      loc_14001D51F
0x14001cd55  mov     rcx, rax; this
0x14001cd58  call    ??0CServerObject_ProviderInitSink@@QEAA@PEAU_SECURITY_DESCRIPTOR@@@Z; CServerObject_ProviderInitSink::CServerObject_ProviderInitSink(_SECURITY_DESCRIPTOR *)
0x14001cd5d  mov     rsi, rax
0x14001cd60  test    rax, rax
0x14001cd63  jz      loc_14001D51F
0x14001cd69  mov     rax, [rax]
0x14001cd6c  mov     rcx, rsi
0x14001cd6f  mov     rax, [rax+8]
0x14001cd73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001cd78  mov     rdx, [rdi+730h]; struct _SECURITY_DESCRIPTOR *
0x14001cd7f  mov     rcx, rsi; this
0x14001cd82  call    ?SinkInitialize@CServerObject_ProviderInitSink@@QEAAJPEAU_SECURITY_DESCRIPTOR@@@Z; CServerObject_ProviderInitSink::SinkInitialize(_SECURITY_DESCRIPTOR *)
0x14001cd87  mov     ebx, eax
0x14001cd89  test    eax, eax
0x14001cd8b  js      loc_14001D50B
0x14001cd91  mov     ecx, 20h ; ' '; dwBytes
0x14001cd96  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001cd9b  mov     [rsp+1A0h+var_148], rax
0x14001cda0  test    rax, rax
0x14001cda3  jz      loc_14001D2AB
0x14001cda9  mov     rdx, rsi; struct IWbemProviderInitSink *
0x14001cdac  mov     rcx, rax; this
0x14001cdaf  call    ??0CInterceptor_IWbemProviderInitSink@@QEAA@PEAUIWbemProviderInitSink@@@Z; CInterceptor_IWbemProviderInitSink::CInterceptor_IWbemProviderInitSink(IWbemProviderInitSink *)
0x14001cdb4  mov     r14, rax
0x14001cdb7  jmp     loc_14001D2AE
0x14001cdbc  mov     rax, [rcx]
0x14001cdbf  mov     rax, [rax+10h]
0x14001cdc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001cdc8  jmp     loc_14001CCBA
0x14001cdcd  test    byte ptr [rcx+1Ch], 4
0x14001cdd1  jz      loc_14001CCD9
0x14001cdd7  cmp     byte ptr [rcx+19h], 2
0x14001cddb  jb      loc_14001CCD9
0x14001cde1  mov     edx, 11h
0x14001cde6  mov     r9d, ebx
0x14001cde9  lea     r8, WPP_d3ea76c96a8339db06b7a6ae92e79012_Traceguids
0x14001cdf0  mov     rcx, [rcx+10h]
0x14001cdf4  call    WPP_SF_d
0x14001cdf9  jmp     loc_14001CCD9
0x14001cdfe  mov     rcx, rax; this
0x14001ce01  call    ??0CServerObject_ProviderInitSink@@QEAA@PEAU_SECURITY_DESCRIPTOR@@@Z; CServerObject_ProviderInitSink::CServerObject_ProviderInitSink(_SECURITY_DESCRIPTOR *)
0x14001ce06  mov     rsi, rax
0x14001ce09  test    rax, rax
0x14001ce0c  jz      loc_14001CD1C
0x14001ce12  mov     rdx, [rax]
0x14001ce15  mov     rcx, rax
0x14001ce18  mov     rax, [rdx+8]
0x14001ce1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ce21  mov     rdx, [rdi+730h]; struct _SECURITY_DESCRIPTOR *
0x14001ce28  mov     rcx, rsi; this
0x14001ce2b  call    ?SinkInitialize@CServerObject_ProviderInitSink@@QEAAJPEAU_SECURITY_DESCRIPTOR@@@Z; CServerObject_ProviderInitSink::SinkInitialize(_SECURITY_DESCRIPTOR *)
0x14001ce30  mov     ebx, eax
0x14001ce32  test    eax, eax
0x14001ce34  js      loc_14001CFC9
0x14001ce3a  mov     ecx, 20h ; ' '; dwBytes
0x14001ce3f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001ce44  mov     [rsp+1A0h+var_148], rax
0x14001ce49  test    rax, rax
0x14001ce4c  jnz     loc_14001CFDD
0x14001ce52  mov     r14, r15
0x14001ce55  test    r14, r14
0x14001ce58  jz      loc_14001CFC4
0x14001ce5e  mov     rax, [r14]
0x14001ce61  mov     rcx, r14
0x14001ce64  mov     rax, [rax+8]
0x14001ce68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ce6d  mov     [rsp+1A0h+var_150], r15d
0x14001ce72  mov     [rbp+0A0h+ppInterface], r15
0x14001ce76  mov     [rsp+1A0h+var_148], r15
0x14001ce7b  xor     r9d, r9d; unsigned int *
0x14001ce7e  lea     r8, [rsp+1A0h+var_150]; int *
0x14001ce83  lea     rdx, [rsp+1A0h+var_148]; struct IServerSecurity **
0x14001ce88  lea     rcx, [rbp+0A0h+ppInterface]; ppInterface
0x14001ce8c  call    ?BeginImpersonation@ProviderSubSystem_Common_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAHPEAK@Z; ProviderSubSystem_Common_Globals::BeginImpersonation(IUnknown * &,IServerSecurity * &,int &,ulong *)
0x14001ce91  mov     ebx, eax
0x14001ce93  test    eax, eax
0x14001ce95  js      loc_14001CFB3
0x14001ce9b  mov     [rsp+1A0h+var_140], r15
0x14001cea0  lea     r8, [rsp+1A0h+var_140]; struct IUnknown **
0x14001cea5  mov     rdx, [rsp+1A0h+var_138]; struct IUnknown *
0x14001ceaa  lea     rcx, IID_IWbemProviderInit; struct _GUID *
0x14001ceb1  call    ?GetProxy@ProviderSubSystem_Common_Globals@@SAJAEBU_GUID@@PEAUIUnknown@@AEAPEAU3@@Z; ProviderSubSystem_Common_Globals::GetProxy(_GUID const &,IUnknown *,IUnknown * &)
0x14001ceb6  test    eax, eax
0x14001ceb8  jns     loc_14001CFF0
0x14001cebe  cmp     eax, 80041002h
0x14001cec3  jnz     loc_14001D54C
0x14001cec9  lea     r15, [rdi+67Ch]
0x14001ced0  lea     r12, [rdi+678h]
0x14001ced7  mov     rcx, [rsp+1A0h+var_138]
0x14001cedc  mov     r8, [rcx]
0x14001cedf  mov     eax, [r15]
0x14001cee2  neg     eax
0x14001cee4  sbb     r9, r9
0x14001cee7  and     r9, [rsp+1A0h+var_130]
0x14001ceec  mov     eax, [r12]
0x14001cef0  neg     eax
0x14001cef2  sbb     rdx, rdx
0x14001cef5  and     rdx, [rbp+0A0h+var_110]
0x14001cef9  mov     rax, [r8+18h]
0x14001cefd  mov     qword ptr [rsp+1A0h+var_168], r14
0x14001cf02  mov     r8, [rbp+0A0h+var_108]
0x14001cf06  mov     [rsp+1A0h+var_170], r8
0x14001cf0b  mov     r8, [rbp+0A0h+var_100]
0x14001cf0f  mov     [rsp+1A0h+var_178], r8
0x14001cf14  mov     [rsp+1A0h+var_180], r9
0x14001cf19  mov     r9, [rsp+1A0h+var_128]
0x14001cf1e  xor     r8d, r8d
0x14001cf21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001cf26  mov     ebx, eax
0x14001cf28  call    cs:__imp_CoRevertToSelf
0x14001cf2e  test    ebx, ebx
0x14001cf30  js      loc_14001D03B
0x14001cf36  mov     edx, [rdi+6B8h]; unsigned int
0x14001cf3c  mov     rcx, rsi; this
0x14001cf3f  call    ?Wait@CServerObject_ProviderInitSink@@QEAAXK@Z; CServerObject_ProviderInitSink::Wait(ulong)
0x14001cf44  mov     ebx, [rsi+18h]
0x14001cf47  test    ebx, ebx
0x14001cf49  js      loc_14001D03B
0x14001cf4f  neg     r13
0x14001cf52  sbb     r11, r11
0x14001cf55  lea     rax, [rbp+0A0h+sz]
0x14001cf59  and     r11, rax
0x14001cf5c  mov     eax, [r15]
0x14001cf5f  neg     eax
0x14001cf61  sbb     r10, r10
0x14001cf64  and     r10, [rsp+1A0h+var_130]
0x14001cf69  mov     eax, [r12]
0x14001cf6d  neg     eax
0x14001cf6f  sbb     rcx, rcx
0x14001cf72  and     rcx, [rbp+0A0h+var_110]
0x14001cf76  mov     [rsp+1A0h+var_170], r11
0x14001cf7b  mov     [rsp+1A0h+var_178], r10
0x14001cf80  mov     [rsp+1A0h+var_180], rcx
0x14001cf85  mov     r9, [rdi+40h]
0x14001cf89  mov     r8, [rsp+1A0h+var_128]
0x14001cf8e  mov     edx, 1
0x14001cf93  mov     rcx, cs:qword_140061388
0x14001cf9a  call    cs:__imp_WmiSetAndCommitObject
0x14001cfa0  mov     r8d, [rsp+1A0h+var_150]; int
0x14001cfa5  mov     rdx, [rsp+1A0h+var_148]; struct IServerSecurity *
0x14001cfaa  mov     rcx, [rbp+0A0h+ppInterface]; struct IUnknown *
0x14001cfae  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x14001cfb3  mov     rax, [r14]
0x14001cfb6  mov     rcx, r14
0x14001cfb9  mov     rax, [rax+10h]
0x14001cfbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001cfc2  jmp     short loc_14001CFC9
0x14001cfc4  mov     ebx, 80041006h
0x14001cfc9  mov     rax, [rsi]
0x14001cfcc  mov     rcx, rsi
0x14001cfcf  mov     rax, [rax+10h]
0x14001cfd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001cfd8  jmp     loc_14001CCAC
0x14001cfdd  mov     rdx, rsi; struct IWbemProviderInitSink *
0x14001cfe0  mov     rcx, rax; this
0x14001cfe3  call    ??0CInterceptor_IWbemProviderInitSink@@QEAA@PEAUIWbemProviderInitSink@@@Z; CInterceptor_IWbemProviderInitSink::CInterceptor_IWbemProviderInitSink(IWbemProviderInitSink *)
0x14001cfe8  mov     r14, rax
0x14001cfeb  jmp     loc_14001CE55
0x14001cff0  call    cs:__imp_CoImpersonateClient
0x14001cff6  mov     ebx, eax
0x14001cff8  test    eax, eax
0x14001cffa  js      short loc_14001D019
0x14001cffc  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x14001d001  add     eax, 0FFFFFFFDh
0x14001d004  cmp     eax, 1
0x14001d007  ja      loc_14001D531
0x14001d00d  mov     r15d, 1
0x14001d013  test    ebx, ebx
0x14001d015  js      short loc_14001D01E
0x14001d017  jmp     short loc_14001D02B
0x14001d019  mov     ebx, 80041003h
0x14001d01e  mov     edx, r15d; int
0x14001d021  mov     rcx, [rsp+1A0h+var_140]; struct IUnknown *
0x14001d026  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(IUnknown *,int)
0x14001d02b  cmp     ebx, 80041002h
0x14001d031  jz      loc_14001CEC9
0x14001d037  test    ebx, ebx
0x14001d039  jns     short loc_14001D09F
0x14001d03b  neg     r13
0x14001d03e  sbb     r8, r8
0x14001d041  lea     rax, [rbp+0A0h+sz]
0x14001d045  and     r8, rax
0x14001d048  mov     eax, [rdi+67Ch]
0x14001d04e  neg     eax
0x14001d050  sbb     rdx, rdx
0x14001d053  and     rdx, [rsp+1A0h+var_130]
0x14001d058  mov     eax, [rdi+678h]
0x14001d05e  neg     eax
0x14001d060  sbb     rcx, rcx
0x14001d063  and     rcx, [rbp+0A0h+var_110]
0x14001d067  mov     [rsp+1A0h+var_168], ebx
0x14001d06b  mov     [rsp+1A0h+var_170], r8
0x14001d070  mov     [rsp+1A0h+var_178], rdx
0x14001d075  mov     [rsp+1A0h+var_180], rcx
0x14001d07a  mov     r9, [rdi+40h]
0x14001d07e  mov     r8, [rsp+1A0h+var_128]
0x14001d083  mov     edx, 1
0x14001d088  mov     rcx, cs:qword_140061380
0x14001d08f  call    cs:__imp_WmiSetAndCommitObject
0x14001d095  mov     ebx, 80041013h
0x14001d09a  jmp     loc_14001CFA0
0x14001d09f  mov     r12, [rsp+1A0h+var_140]
0x14001d0a4  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x14001d0a9  mov     r8d, eax; unsigned int
0x14001d0ac  mov     rcx, r12; struct IUnknown *
0x14001d0af  call    ?SetCloaking@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@KK@Z; ProviderSubSystem_Common_Globals::SetCloaking(IUnknown *,ulong,ulong)
0x14001d0b4  mov     ebx, eax
0x14001d0b6  test    eax, eax
0x14001d0b8  js      short loc_14001D123
0x14001d0ba  call    cs:__imp_CoImpersonateClient
0x14001d0c0  test    eax, eax
0x14001d0c2  js      loc_14001D542
0x14001d0c8  mov     r8, [r12]
0x14001d0cc  mov     eax, [rdi+67Ch]
0x14001d0d2  neg     eax
  ... truncated ...
```
