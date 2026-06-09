# CInterceptor_IWbemSyncProvider::Begin_Interface_Events(bool,IUnknown *,_GUID const &,ulong,int &,IUnknown * &,IServerSecurity * &,int &,IUnknown * &,int &,IUnknown * &)

- ea: `0x14001c6d8`
- end: `0x14001ca6c`
- name: `?Begin_Interface_Events@CInterceptor_IWbemSyncProvider@@AEAAJ_NPEAUIUnknown@@AEBU_GUID@@KAEAHAEAPEAU2@AEAPEAUIServerSecurity@@3434@Z`
- size: `916`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *this, char, struct IUnknown *, struct _GUID *, unsigned int, int *, struct IUnknown **ppOldObject, struct IServerSecurity **, int *, struct IUnknown **, int *, struct IUnknown **)`
- caller_count: `8`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001b484`
- `0x14001b75c`
- `0x14001ba40`
- `0x14001c138`
- `0x14001c418`
- `0x140038b20`
- `0x140038fa4`
- `0x14003be80`

## callees

- `0x1400053dc`
- `0x1400054a0`
- `0x140005544`
- `0x1400058dc`
- `0x140006c64`
- `0x14001c6d8`
- `0x14001ca74`
- `0x1400234b8`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14001c7c9`
- `wbemcomn!GetMemLogObject` at `0x14001c7c9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001c7d4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001c7d4`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x14001c74e`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x14001c74e`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x14001c987`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x14001c987`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14001c84b`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14001c84b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14001c85f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14001c85f`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::Begin_Interface_Events(
        CInterceptor_IWbemSyncProvider *this,
        char a2,
        struct IUnknown *a3,
        struct _GUID *a4,
        unsigned int a5,
        int *a6,
        struct IUnknown **ppOldObject,
        struct IServerSecurity **a8,
        int *a9,
        struct IUnknown **a10,
        int *a11,
        struct IUnknown **a12)
{
  int *v12; // r13
  struct IUnknown **v13; // rbp
  int *v15; // r15
  CInterceptor_IWbemSyncProvider *v16; // r12
  struct IUnknown **v17; // rsi
  struct IServerSecurity **v18; // r14
  HRESULT v19; // ebx
  int v20; // eax
  CMemoryLog *MemLogObject; // rax
  unsigned int v23; // r12d
  int v24; // eax
  struct IUnknown **v25; // rbx
  unsigned int CurrentImpersonationLevel; // eax
  unsigned int v27; // edx
  struct IUnknown **v28; // rbx
  unsigned int v29; // eax
  unsigned int v30; // edx
  unsigned int v32; // [rsp+78h] [rbp+10h] BYREF
  struct _GUID *v33; // [rsp+88h] [rbp+20h]

  v33 = a4;
  v12 = a11;
  v13 = a12;
  v15 = a6;
  v16 = this;
  v17 = ppOldObject;
  v18 = a8;
  *a11 = 0;
  *v13 = 0;
  *v15 = 0;
  *v17 = 0;
  *v18 = 0;
  if ( a2 )
  {
    v32 = 0;
    v19 = ProviderSubSystem_Common_Globals::BeginImpersonation(v17, v18, v15, &v32);
    if ( v19 >= 0 )
    {
      v24 = ProviderSubSystem_Common_Globals::SetProxyState(
              (CInterceptor_IWbemSyncProvider *)((char *)v16 + 440),
              a5,
              v33,
              a3,
              v13,
              v12);
      v19 = v24;
      if ( v24 == -2147217406 )
      {
        *a10 = a3;
        *a9 = 0;
        return 2147749890LL;
      }
      if ( v24 >= 0 )
      {
        v25 = a10;
        *a9 = 1;
        *v25 = *v13;
        CurrentImpersonationLevel = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
        v19 = ProviderSubSystem_Common_Globals::SetCloaking(*v25, v27, CurrentImpersonationLevel);
        if ( v19 >= 0 )
          goto LABEL_12;
        ProviderSubSystem_Common_Globals::RevertProxyState(
          (CInterceptor_IWbemSyncProvider *)((char *)v16 + 440),
          a5,
          *v13,
          *v12);
        if ( v19 == -2147217406 )
          return 2147749890LL;
      }
      ProviderSubSystem_Common_Globals::EndImpersonation(*v17, *v18, *v15);
    }
  }
  else
  {
    a11 = 0;
    if ( CoGetCallContext(&IID_IUnknown, (void **)&a11) >= 0 )
    {
      v23 = 3;
      v19 = CoImpersonateClient();
      if ( v19 >= 0 )
      {
        v23 = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
        CoRevertToSelf();
      }
      (*(void (__fastcall **)(int *))(*(_QWORD *)a11 + 16LL))(a11);
      if ( v19 < 0 )
        goto LABEL_12;
      if ( v23 == 2 )
      {
        v19 = CoSwitchCallContext(0, v17);
        if ( v19 >= 0 )
        {
          v19 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IServerSecurity **))(*v17)->lpVtbl->QueryInterface)(
                  *v17,
                  &IID_IServerSecurity,
                  v18);
          if ( v19 >= 0 )
            *v15 = ((__int64 (__fastcall *)(struct IServerSecurity *))(*v18)->lpVtbl->IsImpersonating)(*v18);
        }
        *a10 = a3;
        *a9 = 0;
        goto LABEL_12;
      }
      v16 = this;
    }
    v32 = 0;
    v19 = ProviderSubSystem_Common_Globals::BeginImpersonation(v17, v18, v15, &v32);
    if ( v19 >= 0 )
    {
      v20 = ProviderSubSystem_Common_Globals::SetProxyState(
              (CInterceptor_IWbemSyncProvider *)((char *)v16 + 440),
              a5,
              v33,
              a3,
              v13,
              v12);
      v19 = v20;
      if ( v20 == -2147217406 )
      {
        v19 = 0;
        *a10 = a3;
        *a9 = 0;
        goto LABEL_8;
      }
      if ( v20 < 0 )
      {
LABEL_6:
        ProviderSubSystem_Common_Globals::EndImpersonation(*v17, *v18, *v15);
LABEL_7:
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, v19);
        goto LABEL_8;
      }
      v28 = a10;
      *a9 = 1;
      *v28 = *v13;
      v29 = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
      v19 = ProviderSubSystem_Common_Globals::SetCloaking(*v28, v30, v29);
      if ( v19 < 0 )
      {
        ProviderSubSystem_Common_Globals::RevertProxyState(
          (CInterceptor_IWbemSyncProvider *)((char *)v16 + 440),
          a5,
          *v13,
          *v12);
        if ( v19 != -2147217406 )
          goto LABEL_6;
        return 2147749890LL;
      }
    }
  }
LABEL_12:
  if ( v19 == -2147217406 )
    return 2147749890LL;
  if ( v19 < 0 )
    goto LABEL_7;
LABEL_8:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      73,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (unsigned int)v19);
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x14001c6d8  mov     rax, rsp
0x14001c6db  mov     [rax+18h], rbx
0x14001c6df  mov     [rax+20h], r9
0x14001c6e3  mov     [rax+8], rcx
0x14001c6e7  push    rbp
0x14001c6e8  push    rsi
0x14001c6e9  push    rdi
0x14001c6ea  push    r12
0x14001c6ec  push    r13
0x14001c6ee  push    r14
0x14001c6f0  push    r15
0x14001c6f2  sub     rsp, 30h
0x14001c6f6  mov     r13, [rsp+68h+arg_50]
0x14001c6fe  xor     ebx, ebx
0x14001c700  mov     rbp, [rsp+68h+arg_58]
0x14001c708  mov     rdi, r8
0x14001c70b  mov     r15, [rsp+68h+arg_28]
0x14001c713  mov     r12, rcx
0x14001c716  mov     rsi, [rsp+68h+ppOldObject]
0x14001c71e  mov     r14, [rsp+68h+arg_38]
0x14001c726  mov     [r13+0], ebx
0x14001c72a  mov     [rbp+0], rbx
0x14001c72e  mov     [r15], ebx
0x14001c731  mov     [rsi], rbx
0x14001c734  mov     [r14], rbx
0x14001c737  test    dl, dl
0x14001c739  jnz     loc_14001C7FB
0x14001c73f  lea     rdx, [rax+58h]; ppInterface
0x14001c743  mov     [rax+58h], rbx
0x14001c747  lea     rcx, IID_IUnknown; riid
0x14001c74e  call    cs:__imp_CoGetCallContext
0x14001c754  test    eax, eax
0x14001c756  jns     loc_14001C845
0x14001c75c  lea     r9, [rsp+68h+arg_8]; unsigned int *
0x14001c761  mov     [rsp+68h+arg_8], ebx
0x14001c765  mov     r8, r15; int *
0x14001c768  mov     rdx, r14; struct IServerSecurity **
0x14001c76b  mov     rcx, rsi; ppInterface
0x14001c76e  call    ?BeginImpersonation@ProviderSubSystem_Common_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAHPEAK@Z; ProviderSubSystem_Common_Globals::BeginImpersonation(IUnknown * &,IServerSecurity * &,int &,ulong *)
0x14001c773  mov     ebx, eax
0x14001c775  test    eax, eax
0x14001c777  js      loc_14001C81C
0x14001c77d  mov     r8, [rsp+68h+arg_18]; struct _GUID *
0x14001c785  lea     rcx, [r12+1B8h]; struct ProxyContainer *
0x14001c78d  mov     edx, [rsp+68h+arg_20]; unsigned int
0x14001c794  mov     r9, rdi; struct IUnknown *
0x14001c797  mov     [rsp+68h+var_40], r13; int *
0x14001c79c  mov     [rsp+68h+var_48], rbp; struct IUnknown **
0x14001c7a1  call    ?SetProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KAEBU_GUID@@PEAUIUnknown@@AEAPEAU4@AEAH@Z; ProviderSubSystem_Common_Globals::SetProxyState(ProxyContainer &,ulong,_GUID const &,IUnknown *,IUnknown * &,int &)
0x14001c7a6  mov     ebx, eax
0x14001c7a8  cmp     eax, 80041002h
0x14001c7ad  jz      loc_14001C893
0x14001c7b3  test    eax, eax
0x14001c7b5  jns     loc_14001C9E1
0x14001c7bb  mov     r8d, [r15]; int
0x14001c7be  mov     rdx, [r14]; struct IServerSecurity *
0x14001c7c1  mov     rcx, [rsi]; struct IUnknown *
0x14001c7c4  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x14001c7c9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14001c7cf  mov     rcx, rax
0x14001c7d2  mov     edx, ebx
0x14001c7d4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14001c7da  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c7e1  lea     rax, WPP_GLOBAL_Control
0x14001c7e8  cmp     rcx, rax
0x14001c7eb  jz      short loc_14001C7F7
0x14001c7ed  test    byte ptr [rcx+1Ch], 4
0x14001c7f1  jnz     loc_14001CA45
0x14001c7f7  mov     eax, ebx
0x14001c7f9  jmp     short loc_14001C82D
0x14001c7fb  lea     r9, [rsp+68h+arg_8]; unsigned int *
0x14001c800  mov     [rsp+68h+arg_8], ebx
0x14001c804  mov     r8, r15; int *
0x14001c807  mov     rdx, r14; struct IServerSecurity **
0x14001c80a  mov     rcx, rsi; ppInterface
0x14001c80d  call    ?BeginImpersonation@ProviderSubSystem_Common_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAHPEAK@Z; ProviderSubSystem_Common_Globals::BeginImpersonation(IUnknown * &,IServerSecurity * &,int &,ulong *)
0x14001c812  mov     ebx, eax
0x14001c814  test    eax, eax
0x14001c816  jns     loc_14001C8BC
0x14001c81c  cmp     ebx, 80041002h
0x14001c822  jnz     loc_14001C8AF
0x14001c828  mov     eax, 80041002h
0x14001c82d  mov     rbx, [rsp+68h+arg_10]
0x14001c835  add     rsp, 30h
0x14001c839  pop     r15
0x14001c83b  pop     r14
0x14001c83d  pop     r13
0x14001c83f  pop     r12
0x14001c841  pop     rdi
0x14001c842  pop     rsi
0x14001c843  pop     rbp
0x14001c844  retn
0x14001c845  mov     r12d, 3
0x14001c84b  call    cs:__imp_CoImpersonateClient
0x14001c851  mov     ebx, eax
0x14001c853  test    eax, eax
0x14001c855  js      short loc_14001C865
0x14001c857  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x14001c85c  mov     r12d, eax
0x14001c85f  call    cs:__imp_CoRevertToSelf
0x14001c865  mov     rcx, [rsp+68h+arg_50]
0x14001c86d  mov     rax, [rcx]
0x14001c870  mov     rax, [rax+10h]
0x14001c874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c879  test    ebx, ebx
0x14001c87b  js      short loc_14001C81C
0x14001c87d  cmp     r12d, 2
0x14001c881  jz      loc_14001C982
0x14001c887  mov     r12, [rsp+68h+arg_0]
0x14001c88c  xor     ebx, ebx
0x14001c88e  jmp     loc_14001C75C
0x14001c893  mov     rax, [rsp+68h+arg_48]
0x14001c89b  xor     ebx, ebx
0x14001c89d  mov     [rax], rdi
0x14001c8a0  mov     rax, [rsp+68h+arg_40]
0x14001c8a8  mov     [rax], ebx
0x14001c8aa  jmp     loc_14001C7DA
0x14001c8af  test    ebx, ebx
0x14001c8b1  jns     loc_14001C7DA
0x14001c8b7  jmp     loc_14001C7C9
0x14001c8bc  mov     r8, [rsp+68h+arg_18]; struct _GUID *
0x14001c8c4  lea     rcx, [r12+1B8h]; struct ProxyContainer *
0x14001c8cc  mov     edx, [rsp+68h+arg_20]; unsigned int
0x14001c8d3  mov     r9, rdi; struct IUnknown *
0x14001c8d6  mov     [rsp+68h+var_40], r13; int *
0x14001c8db  mov     [rsp+68h+var_48], rbp; struct IUnknown **
0x14001c8e0  call    ?SetProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KAEBU_GUID@@PEAUIUnknown@@AEAPEAU4@AEAH@Z; ProviderSubSystem_Common_Globals::SetProxyState(ProxyContainer &,ulong,_GUID const &,IUnknown *,IUnknown * &,int &)
0x14001c8e5  mov     ebx, eax
0x14001c8e7  cmp     eax, 80041002h
0x14001c8ec  jnz     short loc_14001C90C
0x14001c8ee  mov     rax, [rsp+68h+arg_48]
0x14001c8f6  mov     [rax], rdi
0x14001c8f9  mov     rax, [rsp+68h+arg_40]
0x14001c901  mov     dword ptr [rax], 0
0x14001c907  jmp     loc_14001C828
0x14001c90c  test    eax, eax
0x14001c90e  js      short loc_14001C96F
0x14001c910  mov     rax, [rsp+68h+arg_40]
0x14001c918  mov     rbx, [rsp+68h+arg_48]
0x14001c920  mov     dword ptr [rax], 1
0x14001c926  mov     rax, [rbp+0]
0x14001c92a  mov     [rbx], rax
0x14001c92d  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x14001c932  mov     rcx, [rbx]; struct IUnknown *
0x14001c935  mov     r8d, eax; unsigned int
0x14001c938  call    ?SetCloaking@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@KK@Z; ProviderSubSystem_Common_Globals::SetCloaking(IUnknown *,ulong,ulong)
0x14001c93d  mov     ebx, eax
0x14001c93f  test    eax, eax
0x14001c941  jns     loc_14001C81C
0x14001c947  mov     r9d, [r13+0]; int
0x14001c94b  lea     rcx, [r12+1B8h]; struct ProxyContainer *
0x14001c953  mov     r8, [rbp+0]; struct IUnknown *
0x14001c957  mov     edx, [rsp+68h+arg_20]; unsigned int
0x14001c95e  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x14001c963  cmp     ebx, 80041002h
0x14001c969  jz      loc_14001C828
0x14001c96f  mov     r8d, [r15]; int
0x14001c972  mov     rdx, [r14]; struct IServerSecurity *
0x14001c975  mov     rcx, [rsi]; struct IUnknown *
0x14001c978  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x14001c97d  jmp     loc_14001C81C
0x14001c982  mov     rdx, rsi; ppOldObject
0x14001c985  xor     ecx, ecx; pNewObject
0x14001c987  call    cs:__imp_CoSwitchCallContext
0x14001c98d  mov     ebx, eax
0x14001c98f  test    eax, eax
0x14001c991  js      short loc_14001C9C3
0x14001c993  mov     rcx, [rsi]
0x14001c996  lea     rdx, IID_IServerSecurity
0x14001c99d  mov     r8, r14
0x14001c9a0  mov     rax, [rcx]
0x14001c9a3  mov     rax, [rax]
0x14001c9a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c9ab  mov     ebx, eax
0x14001c9ad  test    eax, eax
0x14001c9af  js      short loc_14001C9C3
0x14001c9b1  mov     rcx, [r14]
0x14001c9b4  mov     rax, [rcx]
0x14001c9b7  mov     rax, [rax+30h]
0x14001c9bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c9c0  mov     [r15], eax
0x14001c9c3  mov     rax, [rsp+68h+arg_48]
0x14001c9cb  mov     [rax], rdi
0x14001c9ce  mov     rax, [rsp+68h+arg_40]
0x14001c9d6  mov     dword ptr [rax], 0
0x14001c9dc  jmp     loc_14001C81C
0x14001c9e1  mov     rax, [rsp+68h+arg_40]
0x14001c9e9  mov     rbx, [rsp+68h+arg_48]
0x14001c9f1  mov     dword ptr [rax], 1
0x14001c9f7  mov     rax, [rbp+0]
0x14001c9fb  mov     [rbx], rax
0x14001c9fe  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x14001ca03  mov     rcx, [rbx]; struct IUnknown *
0x14001ca06  mov     r8d, eax; unsigned int
0x14001ca09  call    ?SetCloaking@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@KK@Z; ProviderSubSystem_Common_Globals::SetCloaking(IUnknown *,ulong,ulong)
0x14001ca0e  mov     ebx, eax
0x14001ca10  test    eax, eax
0x14001ca12  jns     loc_14001C81C
0x14001ca18  mov     r9d, [r13+0]; int
0x14001ca1c  lea     rcx, [r12+1B8h]; struct ProxyContainer *
0x14001ca24  mov     r8, [rbp+0]; struct IUnknown *
0x14001ca28  mov     edx, [rsp+68h+arg_20]; unsigned int
0x14001ca2f  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x14001ca34  cmp     ebx, 80041002h
0x14001ca3a  jz      loc_14001C828
0x14001ca40  jmp     loc_14001C7BB
0x14001ca45  cmp     byte ptr [rcx+19h], 2
0x14001ca49  jb      loc_14001C7F7
0x14001ca4f  mov     rcx, [rcx+10h]
0x14001ca53  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14001ca5a  mov     edx, 49h ; 'I'
0x14001ca5f  mov     r9d, ebx
0x14001ca62  call    WPP_SF_d
0x14001ca67  jmp     loc_14001C7F7
```
