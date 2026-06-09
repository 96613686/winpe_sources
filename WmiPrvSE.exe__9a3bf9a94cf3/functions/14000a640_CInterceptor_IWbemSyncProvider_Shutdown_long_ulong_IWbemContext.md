# CInterceptor_IWbemSyncProvider::Shutdown(long,ulong,IWbemContext *)

- ea: `0x14000a640`
- end: `0x14000aa5b`
- name: `?Shutdown@CInterceptor_IWbemSyncProvider@@UEAAJJKPEAUIWbemContext@@@Z`
- size: `1051`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *__hidden this, int, unsigned int, struct IWbemContext *)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1400053dc`
- `0x1400054a0`
- `0x1400055e4`
- `0x1400058dc`
- `0x140006c64`
- `0x14000a0f0`
- `0x14000a530`
- `0x14000a640`
- `0x14000aa70`
- `0x14001ca74`
- `0x1400234b8`
- `0x140023d78`
- `0x14002fe24`
- `0x14004612c`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14000aa45`
- `wbemcomn!GetMemLogObject` at `0x14000aa45`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000aa50`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000aa50`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000a8b2`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000a9b9`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000a8b2`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000a9b9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000a8ff`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000a9df`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000a8ff`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000a9df`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::Shutdown(
        CInterceptor_IWbemSyncProvider *this,
        unsigned int a2,
        unsigned int a3,
        struct IWbemContext *a4)
{
  unsigned int v6; // r14d
  __int64 (__fastcall ***v8)(_QWORD, GUID *, struct IUnknown **); // rcx
  int v9; // edi
  HRESULT v10; // ebx
  __int64 (__fastcall ***v11)(_QWORD, GUID *, struct IUnknown **); // rcx
  struct IUnknown *v12; // rdi
  __int64 v13; // rax
  _QWORD *v14; // r15
  __int64 v16; // rcx
  __int64 v17; // r14
  __int64 v18; // rsi
  int Proxy; // eax
  unsigned __int16 *v20; // rdx
  unsigned __int16 *v21; // r8
  unsigned __int16 *v22; // r9
  struct IUnknown *v23; // r14
  unsigned int CurrentImpersonationLevel; // eax
  unsigned int v25; // edx
  unsigned int v26; // edi
  __int64 v27; // rcx
  CMemoryLog *MemLogObject; // rax
  unsigned int v29; // [rsp+20h] [rbp-40h]
  unsigned int v30; // [rsp+28h] [rbp-38h]
  unsigned int v31; // [rsp+30h] [rbp-30h]
  struct IUnknown *v32; // [rsp+40h] [rbp-20h] BYREF
  struct IUnknown *v33; // [rsp+48h] [rbp-18h] BYREF
  struct IServerSecurity *v34; // [rsp+50h] [rbp-10h] BYREF
  struct IUnknown *ppInterface; // [rsp+58h] [rbp-8h] BYREF
  __int64 v36; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int v37; // [rsp+A8h] [rbp+48h]
  unsigned int v38; // [rsp+B0h] [rbp+50h]

  v38 = a3;
  v37 = a2;
  v6 = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v30 = (unsigned int)a4;
    WPP_SF_dlq(*((_QWORD *)WPP_GLOBAL_Control + 2), 184, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, a2, a3);
  }
  v8 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IUnknown **))*((_QWORD *)this + 23);
  v9 = 0;
  v32 = 0;
  v10 = 0;
  if ( v8 )
  {
    v10 = (**v8)(v8, &IID_IWbemShutdown, &v32);
    if ( v10 >= 0 )
    {
      LODWORD(v36) = 0;
      ppInterface = 0;
      v34 = 0;
      v10 = ProviderSubSystem_Common_Globals::BeginImpersonation(&ppInterface, &v34, (int *)&v36, 0);
      if ( v10 < 0 )
      {
LABEL_35:
        ((void (__fastcall *)(struct IUnknown *))v32->lpVtbl->Release)(v32);
        goto LABEL_5;
      }
      v33 = 0;
      Proxy = ProviderSubSystem_Common_Globals::GetProxy(
                (CInterceptor_IWbemSyncProvider *)((char *)this + 304),
                0x15u,
                &IID_IWbemShutdown,
                v32,
                &v33);
      if ( Proxy < 0 )
      {
        if ( Proxy != -2147217406 )
        {
          v10 = -2147217398;
          goto LABEL_34;
        }
LABEL_33:
        v10 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, _QWORD, struct IWbemContext *))v32->lpVtbl[1].QueryInterface)(
                v32,
                v6,
                a3,
                a4);
        CoRevertToSelf();
LABEL_34:
        ProviderSubSystem_Common_Globals::EndImpersonation(ppInterface, v34, v36);
        goto LABEL_35;
      }
      v10 = CoImpersonateClient();
      if ( v10 < 0 )
      {
        v10 = -2147217405;
      }
      else
      {
        if ( (unsigned int)ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel() - 3 > 1 )
          v10 = SetInterfaceSecurity(v33, v20, v21, v22, v29, v30, v31);
        v9 = 1;
        if ( v10 >= 0 )
        {
LABEL_32:
          if ( v10 != -2147217406 )
          {
            if ( v10 >= 0 )
            {
              v23 = v33;
              CurrentImpersonationLevel = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
              v10 = ProviderSubSystem_Common_Globals::SetCloaking(v23, v25, CurrentImpersonationLevel);
              if ( v10 >= 0 )
              {
                v10 = CoImpersonateClient();
                if ( v10 >= 0 )
                {
                  v10 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, _QWORD, struct IWbemContext *))v23->lpVtbl[1].QueryInterface)(
                          v23,
                          v37,
                          a3,
                          a4);
                  CoRevertToSelf();
                }
              }
              ProviderSubSystem_Common_Globals::RevertProxyState(
                (CInterceptor_IWbemSyncProvider *)((char *)this + 304),
                0x15u,
                v33,
                v9);
              v6 = v37;
            }
            goto LABEL_34;
          }
          goto LABEL_33;
        }
      }
      ProviderSubSystem_Common_Globals::RevertProxyState(
        (CInterceptor_IWbemSyncProvider *)((char *)this + 304),
        0x15u,
        v33,
        v9);
      goto LABEL_32;
    }
  }
LABEL_5:
  v11 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IUnknown **))*((_QWORD *)this + 35);
  if ( v11 )
  {
    v32 = 0;
    v10 = (**v11)(v11, &IID_IWbemShutdown, &v32);
    if ( v10 >= 0 )
    {
      v10 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, _QWORD, struct IWbemContext *))v32->lpVtbl[1].QueryInterface)(
              v32,
              v6,
              a3,
              a4);
      ((void (__fastcall *)(struct IUnknown *))v32->lpVtbl->Release)(v32);
    }
  }
  v12 = (struct IUnknown *)((char *)this + 96);
  v13 = *((_QWORD *)this + 12);
  ppInterface = (struct IUnknown *)((char *)this + 96);
  (*(void (__fastcall **)(char *))(v13 + 48))((char *)this + 96);
  v14 = operator new(saturated_mul(*((unsigned int *)this + 42), 8u));
  if ( v14 )
  {
    v16 = *((_QWORD *)this + 20);
    if ( v16 )
    {
      while ( *(_QWORD *)(v16 + 8) )
        v16 = *(_QWORD *)(v16 + 8);
    }
    v36 = v16;
    v17 = 0;
    while ( v16 )
    {
      v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64))(v16 + 40))(
              *(_QWORD *)(v16 + 40),
              &IID_IWbemShutdown,
              (__int64)&v14[v17]);
      WmiAvlTree<void *,WmiContainerController<void *>::WmiContainerElement *>::Iterator::Increment(&v36);
      v16 = v36;
      v17 = (unsigned int)(v17 + 1);
    }
    ((void (__fastcall *)(char *))v12->lpVtbl[2].AddRef)((char *)this + 96);
    v18 = 0;
    if ( (_DWORD)v17 )
    {
      v26 = v38;
      do
      {
        v27 = v14[v18];
        if ( v27 )
        {
          v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, struct IWbemContext *))(*(_QWORD *)v27 + 24LL))(
                  v27,
                  v37,
                  v26,
                  a4);
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v14[v18] + 16LL))(v14[v18]);
        }
        v18 = (unsigned int)(v18 + 1);
      }
      while ( (unsigned int)v18 < (unsigned int)v17 );
      v12 = ppInterface;
    }
    operator delete(v14);
  }
  else
  {
    ((void (__fastcall *)(char *))v12->lpVtbl[2].AddRef)((char *)this + 96);
    v10 = -2147217402;
  }
  WmiContainerController<void *>::Shutdown(v12);
  if ( v10 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v10);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      185,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (unsigned int)v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14000a640  mov     [rsp-38h+arg_18], rbx
0x14000a645  mov     [rsp-38h+arg_10], r8d
0x14000a64a  mov     [rsp-38h+arg_8], edx
0x14000a64e  push    rbp
0x14000a64f  push    rsi
0x14000a650  push    rdi
0x14000a651  push    r12
0x14000a653  push    r13
0x14000a655  push    r14
0x14000a657  push    r15
0x14000a659  mov     rbp, rsp
0x14000a65c  sub     rsp, 60h
0x14000a660  mov     r13, r9
0x14000a663  mov     r12d, r8d
0x14000a666  mov     r14d, edx
0x14000a669  mov     rsi, rcx
0x14000a66c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a673  lea     rax, WPP_GLOBAL_Control
0x14000a67a  cmp     rcx, rax
0x14000a67d  jz      short loc_14000A689
0x14000a67f  test    byte ptr [rcx+1Ch], 4
0x14000a683  jnz     loc_14000A956
0x14000a689  mov     rcx, [rsi+0B8h]
0x14000a690  xor     edi, edi
0x14000a692  mov     [rbp+var_20], rdi
0x14000a696  mov     ebx, edi
0x14000a698  test    rcx, rcx
0x14000a69b  jz      short loc_14000A6BD
0x14000a69d  mov     rax, [rcx]
0x14000a6a0  lea     r8, [rbp+var_20]
0x14000a6a4  lea     rdx, IID_IWbemShutdown
0x14000a6ab  mov     rax, [rax]
0x14000a6ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a6b3  mov     ebx, eax
0x14000a6b5  test    eax, eax
0x14000a6b7  jns     loc_14000A859
0x14000a6bd  mov     rcx, [rsi+118h]
0x14000a6c4  test    rcx, rcx
0x14000a6c7  jnz     loc_14000A762
0x14000a6cd  lea     rdi, [rsi+60h]
0x14000a6d1  mov     rax, [rdi]
0x14000a6d4  mov     rcx, rdi
0x14000a6d7  mov     [rbp+ppInterface], rdi
0x14000a6db  mov     rax, [rax+30h]
0x14000a6df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a6e4  mov     ecx, [rsi+0A8h]
0x14000a6ea  mov     eax, 8
0x14000a6ef  mul     rcx
0x14000a6f2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000a6f9  cmovb   rax, rcx
0x14000a6fd  mov     rcx, rax; dwBytes
0x14000a700  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000a705  mov     r15, rax
0x14000a708  test    rax, rax
0x14000a70b  jnz     loc_14000A7DF
0x14000a711  mov     rax, [rdi]
0x14000a714  mov     rcx, rdi
0x14000a717  mov     rax, [rax+38h]
0x14000a71b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a720  mov     ebx, 80041006h
0x14000a725  mov     rcx, rdi
0x14000a728  call    ?Shutdown@?$WmiContainerController@PEAX@@UEAA?AW4WmiStatusCode@@XZ; WmiContainerController<void *>::Shutdown(void)
0x14000a72d  test    ebx, ebx
0x14000a72f  js      loc_14000AA45
0x14000a735  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a73c  lea     rax, WPP_GLOBAL_Control
0x14000a743  cmp     rcx, rax
0x14000a746  jnz     short loc_14000A7B6
0x14000a748  mov     eax, ebx
0x14000a74a  mov     rbx, [rsp+60h+arg_18]
0x14000a752  add     rsp, 60h
0x14000a756  pop     r15
0x14000a758  pop     r14
0x14000a75a  pop     r13
0x14000a75c  pop     r12
0x14000a75e  pop     rdi
0x14000a75f  pop     rsi
0x14000a760  pop     rbp
0x14000a761  retn
0x14000a762  mov     [rbp+var_20], rdi
0x14000a766  lea     r8, [rbp+var_20]
0x14000a76a  mov     rax, [rcx]
0x14000a76d  lea     rdx, IID_IWbemShutdown
0x14000a774  mov     rax, [rax]
0x14000a777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a77c  mov     ebx, eax
0x14000a77e  test    eax, eax
0x14000a780  js      loc_14000A6CD
0x14000a786  mov     rcx, [rbp+var_20]
0x14000a78a  mov     r9, r13
0x14000a78d  mov     r8d, r12d
0x14000a790  mov     edx, r14d
0x14000a793  mov     rax, [rcx]
0x14000a796  mov     rax, [rax+18h]
0x14000a79a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a79f  mov     rcx, [rbp+var_20]
0x14000a7a3  mov     ebx, eax
0x14000a7a5  mov     rax, [rcx]
0x14000a7a8  mov     rax, [rax+10h]
0x14000a7ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a7b1  jmp     loc_14000A6CD
0x14000a7b6  test    byte ptr [rcx+1Ch], 4
0x14000a7ba  jz      short loc_14000A748
0x14000a7bc  cmp     byte ptr [rcx+19h], 2
0x14000a7c0  jb      short loc_14000A748
0x14000a7c2  mov     rcx, [rcx+10h]
0x14000a7c6  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14000a7cd  mov     edx, 0B9h
0x14000a7d2  mov     r9d, ebx
0x14000a7d5  call    WPP_SF_d
0x14000a7da  jmp     loc_14000A748
0x14000a7df  mov     rcx, [rsi+0A0h]
0x14000a7e6  test    rcx, rcx
0x14000a7e9  jz      short loc_14000A7F8
0x14000a7eb  jmp     short loc_14000A7F1
0x14000a7ed  mov     rcx, [rcx+8]
0x14000a7f1  cmp     qword ptr [rcx+8], 0
0x14000a7f6  jnz     short loc_14000A7ED
0x14000a7f8  mov     [rbp+arg_0], rcx
0x14000a7fc  xor     r14d, r14d
0x14000a7ff  test    rcx, rcx
0x14000a802  jnz     short loc_14000A82B
0x14000a804  mov     rax, [rdi]
0x14000a807  mov     rcx, rdi
0x14000a80a  mov     rax, [rax+38h]
0x14000a80e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a813  xor     esi, esi
0x14000a815  test    r14d, r14d
0x14000a818  jnz     loc_14000AA02
0x14000a81e  mov     rcx, r15; lpMem
0x14000a821  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000a826  jmp     loc_14000A725
0x14000a82b  mov     rcx, [rcx+28h]
0x14000a82f  lea     r8, [r15+r14*8]
0x14000a833  mov     rdx, [rcx]
0x14000a836  mov     rax, [rdx]
0x14000a839  lea     rdx, IID_IWbemShutdown
0x14000a840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a845  lea     rcx, [rbp+arg_0]
0x14000a849  mov     ebx, eax
0x14000a84b  call    ?Increment@Iterator@?$WmiAvlTree@PEAXPEAVWmiContainerElement@?$WmiContainerController@PEAX@@@@QEAAAEAV12@XZ; WmiAvlTree<void *,WmiContainerController<void *>::WmiContainerElement *>::Iterator::Increment(void)
0x14000a850  mov     rcx, [rbp+arg_0]
0x14000a854  inc     r14d
0x14000a857  jmp     short loc_14000A7FF
0x14000a859  xor     r9d, r9d; unsigned int *
0x14000a85c  mov     dword ptr [rbp+arg_0], edi
0x14000a85f  lea     r8, [rbp+arg_0]; int *
0x14000a863  mov     [rbp+ppInterface], rdi
0x14000a867  lea     rdx, [rbp+var_10]; struct IServerSecurity **
0x14000a86b  mov     [rbp+var_10], rdi
0x14000a86f  lea     rcx, [rbp+ppInterface]; ppInterface
0x14000a873  call    ?BeginImpersonation@ProviderSubSystem_Common_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAHPEAK@Z; ProviderSubSystem_Common_Globals::BeginImpersonation(IUnknown * &,IServerSecurity * &,int &,ulong *)
0x14000a878  mov     ebx, eax
0x14000a87a  test    eax, eax
0x14000a87c  js      loc_14000A918
0x14000a882  mov     r9, [rbp+var_20]; struct IUnknown *
0x14000a886  lea     rax, [rbp+var_18]
0x14000a88a  lea     r15, [rsi+130h]
0x14000a891  mov     [rbp+var_18], rdi
0x14000a895  mov     rcx, r15; struct ProxyContainer *
0x14000a898  mov     [rsp+60h+var_40], rax; unsigned int
0x14000a89d  lea     r8, IID_IWbemShutdown; struct _GUID *
0x14000a8a4  mov     edx, 15h; unsigned int
0x14000a8a9  call    ?GetProxy@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KAEBU_GUID@@PEAUIUnknown@@AEAPEAU4@@Z; ProviderSubSystem_Common_Globals::GetProxy(ProxyContainer &,ulong,_GUID const &,IUnknown *,IUnknown * &)
0x14000a8ae  test    eax, eax
0x14000a8b0  js      short loc_14000A92D
0x14000a8b2  call    cs:__imp_CoImpersonateClient
0x14000a8b8  mov     ebx, eax
0x14000a8ba  test    eax, eax
0x14000a8bc  js      short loc_14000A93B
0x14000a8be  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x14000a8c3  add     eax, 0FFFFFFFDh
0x14000a8c6  cmp     eax, 1
0x14000a8c9  ja      loc_14000A987
0x14000a8cf  mov     edi, 1
0x14000a8d4  test    ebx, ebx
0x14000a8d6  js      short loc_14000A940
0x14000a8d8  cmp     ebx, 80041002h
0x14000a8de  jnz     loc_14000A997
0x14000a8e4  mov     rcx, [rbp+var_20]
0x14000a8e8  mov     r9, r13
0x14000a8eb  mov     r8d, r12d
0x14000a8ee  mov     edx, r14d
0x14000a8f1  mov     rax, [rcx]
0x14000a8f4  mov     rax, [rax+18h]
0x14000a8f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a8fd  mov     ebx, eax
0x14000a8ff  call    cs:__imp_CoRevertToSelf
0x14000a905  mov     r8d, dword ptr [rbp+arg_0]; int
0x14000a909  mov     rdx, [rbp+var_10]; struct IServerSecurity *
0x14000a90d  mov     rcx, [rbp+ppInterface]; struct IUnknown *
0x14000a911  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x14000a916  xor     edi, edi
0x14000a918  mov     rcx, [rbp+var_20]
0x14000a91c  mov     rax, [rcx]
0x14000a91f  mov     rax, [rax+10h]
0x14000a923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a928  jmp     loc_14000A6BD
0x14000a92d  cmp     eax, 80041002h
0x14000a932  jz      short loc_14000A8E4
0x14000a934  mov     ebx, 8004100Ah
0x14000a939  jmp     short loc_14000A905
0x14000a93b  mov     ebx, 80041003h
0x14000a940  mov     r8, [rbp+var_18]; struct IUnknown *
0x14000a944  mov     r9d, edi; int
0x14000a947  mov     edx, 15h; unsigned int
0x14000a94c  mov     rcx, r15; struct ProxyContainer *
0x14000a94f  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x14000a954  jmp     short loc_14000A8D8
0x14000a956  cmp     byte ptr [rcx+19h], 5
0x14000a95a  jb      loc_14000A689
0x14000a960  mov     rcx, [rcx+10h]
0x14000a964  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14000a96b  mov     edx, 0B8h
0x14000a970  mov     [rsp+60h+var_38], r13
0x14000a975  mov     r9d, r14d
0x14000a978  mov     dword ptr [rsp+60h+var_40], r12d
0x14000a97d  call    WPP_SF_dlq
0x14000a982  jmp     loc_14000A689
0x14000a987  mov     rcx, [rbp+var_18]; struct IUnknown *
0x14000a98b  call    ?SetInterfaceSecurity@@YAJPEAUIUnknown@@PEAG11KKK@Z; SetInterfaceSecurity(IUnknown *,ushort *,ushort *,ushort *,ulong,ulong,ulong)
0x14000a990  mov     ebx, eax
0x14000a992  jmp     loc_14000A8CF
0x14000a997  test    ebx, ebx
0x14000a999  js      loc_14000A905
0x14000a99f  mov     r14, [rbp+var_18]
0x14000a9a3  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x14000a9a8  mov     r8d, eax; unsigned int
0x14000a9ab  mov     rcx, r14; struct IUnknown *
0x14000a9ae  call    ?SetCloaking@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@KK@Z; ProviderSubSystem_Common_Globals::SetCloaking(IUnknown *,ulong,ulong)
0x14000a9b3  mov     ebx, eax
0x14000a9b5  test    eax, eax
0x14000a9b7  js      short loc_14000A9E5
0x14000a9b9  call    cs:__imp_CoImpersonateClient
0x14000a9bf  mov     ebx, eax
0x14000a9c1  test    eax, eax
0x14000a9c3  js      short loc_14000A9E5
0x14000a9c5  mov     rax, [r14]
0x14000a9c8  mov     r9, r13
0x14000a9cb  mov     edx, [rbp+arg_8]
0x14000a9ce  mov     r8d, r12d
0x14000a9d1  mov     rcx, r14
0x14000a9d4  mov     rax, [rax+18h]
0x14000a9d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a9dd  mov     ebx, eax
0x14000a9df  call    cs:__imp_CoRevertToSelf
0x14000a9e5  mov     r8, [rbp+var_18]; struct IUnknown *
0x14000a9e9  mov     r9d, edi; int
0x14000a9ec  mov     edx, 15h; unsigned int
0x14000a9f1  mov     rcx, r15; struct ProxyContainer *
0x14000a9f4  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x14000a9f9  mov     r14d, [rbp+arg_8]
0x14000a9fd  jmp     loc_14000A905
0x14000aa02  mov     edi, [rbp+arg_10]
0x14000aa05  mov     rcx, [r15+rsi*8]
0x14000aa09  test    rcx, rcx
0x14000aa0c  jz      short loc_14000AA35
0x14000aa0e  mov     rax, [rcx]
0x14000aa11  mov     r9, r13
0x14000aa14  mov     edx, [rbp+arg_8]
0x14000aa17  mov     r8d, edi
0x14000aa1a  mov     rax, [rax+18h]
0x14000aa1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa23  mov     rcx, [r15+rsi*8]
0x14000aa27  mov     ebx, eax
0x14000aa29  mov     rax, [rcx]
0x14000aa2c  mov     rax, [rax+10h]
0x14000aa30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa35  inc     esi
0x14000aa37  cmp     esi, r14d
0x14000aa3a  jb      short loc_14000AA05
0x14000aa3c  mov     rdi, [rbp+ppInterface]
0x14000aa40  jmp     loc_14000A81E
0x14000aa45  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14000aa4b  mov     rcx, rax
0x14000aa4e  mov     edx, ebx
0x14000aa50  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14000aa56  jmp     loc_14000A735
```
