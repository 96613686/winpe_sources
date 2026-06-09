# CServerObject_StaThread::ValidateSubscription(IWbemClassObject *)

- ea: `0x14003ebd0`
- end: `0x14003ed9d`
- name: `?ValidateSubscription@CServerObject_StaThread@@UEAAJPEAUIWbemClassObject@@@Z`
- size: `461`
- prototype: `__int64 __fastcall(CServerObject_StaThread *__hidden this, struct IWbemClassObject *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400053dc`
- `0x1400054a0`
- `0x140005544`
- `0x1400058dc`
- `0x140006c64`
- `0x14001ca74`
- `0x1400234b8`
- `0x14003ebd0`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14003ed06`
- `wbemcomn!GetMemLogObject` at `0x14003ed40`
- `wbemcomn!GetMemLogObject` at `0x14003ed06`
- `wbemcomn!GetMemLogObject` at `0x14003ed40`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003ed11`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003ed50`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003ed11`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003ed50`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14003ecb1`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14003ecb1`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14003ec8b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14003eccf`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14003ec8b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14003eccf`

## pseudocode

```c
__int64 __fastcall CServerObject_StaThread::ValidateSubscription(
        CServerObject_StaThread *this,
        struct IWbemClassObject *a2)
{
  int v4; // ebx
  struct IUnknown *v5; // r9
  struct ProxyContainer *v6; // r14
  int v7; // eax
  struct IUnknown *v8; // rdi
  unsigned int CurrentImpersonationLevel; // eax
  unsigned int v10; // edx
  CMemoryLog *MemLogObject; // rax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  CMemoryLog *v15; // rax
  struct IServerSecurity *v17; // [rsp+30h] [rbp-10h] BYREF
  struct IUnknown *ppInterface; // [rsp+38h] [rbp-8h] BYREF
  int v19; // [rsp+70h] [rbp+30h] BYREF
  int v20; // [rsp+80h] [rbp+40h] BYREF
  struct IUnknown *v21; // [rsp+88h] [rbp+48h] BYREF

  if ( *((_QWORD *)this + 59) )
  {
    v20 = 0;
    ppInterface = 0;
    v17 = 0;
    v4 = ProviderSubSystem_Common_Globals::BeginImpersonation(&ppInterface, &v17, &v20, 0);
    if ( v4 < 0 )
      goto LABEL_12;
    v5 = (struct IUnknown *)*((_QWORD *)this + 59);
    v6 = (CServerObject_StaThread *)((char *)this + 528);
    v19 = 0;
    v21 = 0;
    v7 = ProviderSubSystem_Common_Globals::SetProxyState(
           (CServerObject_StaThread *)((char *)this + 528),
           5u,
           &IID_IWbemEventConsumerProviderEx,
           v5,
           &v21,
           &v19);
    v4 = v7;
    if ( v7 == -2147217406 )
    {
      v4 = (*(__int64 (__fastcall **)(_QWORD, struct IWbemClassObject *))(**((_QWORD **)this + 59) + 32LL))(
             *((_QWORD *)this + 59),
             a2);
      CoRevertToSelf();
    }
    else if ( v7 >= 0 )
    {
      v8 = v21;
      CurrentImpersonationLevel = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
      v4 = ProviderSubSystem_Common_Globals::SetCloaking(v8, v10, CurrentImpersonationLevel);
      if ( v4 >= 0 )
      {
        if ( CoImpersonateClient() < 0 )
        {
          v4 = -2147217405;
        }
        else
        {
          v4 = ((__int64 (__fastcall *)(struct IUnknown *, struct IWbemClassObject *))v8->lpVtbl[1].AddRef)(v8, a2);
          CoRevertToSelf();
        }
      }
      ProviderSubSystem_Common_Globals::RevertProxyState(v6, 5u, v21, v19);
    }
    ProviderSubSystem_Common_Globals::EndImpersonation(ppInterface, v17, v20);
    if ( v4 < 0 )
    {
LABEL_12:
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v4);
    }
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 49;
      v14 = (unsigned int)v4;
LABEL_21:
      WPP_SF_d(v12[2], v13, WPP_d3ea76c96a8339db06b7a6ae92e79012_Traceguids, v14);
    }
  }
  else
  {
    v15 = GetMemLogObject();
    v4 = -2147217372;
    CMemoryLog::Write(v15, -2147217372);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 50;
      v14 = 2147749924LL;
      goto LABEL_21;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14003ebd0  push    rbp
0x14003ebd2  push    rbx
0x14003ebd3  push    rsi
0x14003ebd4  push    rdi
0x14003ebd5  push    r14
0x14003ebd7  mov     rbp, rsp
0x14003ebda  sub     rsp, 40h
0x14003ebde  cmp     qword ptr [rcx+1D8h], 0
0x14003ebe6  mov     rsi, rdx
0x14003ebe9  mov     rdi, rcx
0x14003ebec  jz      loc_14003ED40
0x14003ebf2  xor     r9d, r9d; unsigned int *
0x14003ebf5  mov     [rbp+arg_10], 0
0x14003ebfc  lea     r8, [rbp+arg_10]; int *
0x14003ec00  mov     [rbp+ppInterface], 0
0x14003ec08  lea     rdx, [rbp+var_10]; struct IServerSecurity **
0x14003ec0c  mov     [rbp+var_10], 0
0x14003ec14  lea     rcx, [rbp+ppInterface]; ppInterface
0x14003ec18  call    ?BeginImpersonation@ProviderSubSystem_Common_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAHPEAK@Z; ProviderSubSystem_Common_Globals::BeginImpersonation(IUnknown * &,IServerSecurity * &,int &,ulong *)
0x14003ec1d  mov     ebx, eax
0x14003ec1f  test    eax, eax
0x14003ec21  js      loc_14003ED06
0x14003ec27  mov     r9, [rdi+1D8h]; struct IUnknown *
0x14003ec2e  lea     rax, [rbp+arg_0]
0x14003ec32  mov     [rsp+40h+var_18], rax; int *
0x14003ec37  lea     r14, [rdi+210h]
0x14003ec3e  lea     rax, [rbp+arg_18]
0x14003ec42  mov     [rbp+arg_0], 0
0x14003ec49  lea     r8, IID_IWbemEventConsumerProviderEx; struct _GUID *
0x14003ec50  mov     [rsp+40h+var_20], rax; struct IUnknown **
0x14003ec55  mov     edx, 5; unsigned int
0x14003ec5a  mov     [rbp+arg_18], 0
0x14003ec62  mov     rcx, r14; struct ProxyContainer *
0x14003ec65  call    ?SetProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KAEBU_GUID@@PEAUIUnknown@@AEAPEAU4@AEAH@Z; ProviderSubSystem_Common_Globals::SetProxyState(ProxyContainer &,ulong,_GUID const &,IUnknown *,IUnknown * &,int &)
0x14003ec6a  mov     ebx, eax
0x14003ec6c  cmp     eax, 80041002h
0x14003ec71  jnz     short loc_14003EC93
0x14003ec73  mov     rcx, [rdi+1D8h]
0x14003ec7a  mov     rdx, rsi
0x14003ec7d  mov     rax, [rcx]
0x14003ec80  mov     rax, [rax+20h]
0x14003ec84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ec89  mov     ebx, eax
0x14003ec8b  call    cs:__imp_CoRevertToSelf
0x14003ec91  jmp     short loc_14003ECF1
0x14003ec93  test    eax, eax
0x14003ec95  js      short loc_14003ECF1
0x14003ec97  mov     rdi, [rbp+arg_18]
0x14003ec9b  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x14003eca0  mov     r8d, eax; unsigned int
0x14003eca3  mov     rcx, rdi; struct IUnknown *
0x14003eca6  call    ?SetCloaking@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@KK@Z; ProviderSubSystem_Common_Globals::SetCloaking(IUnknown *,ulong,ulong)
0x14003ecab  mov     ebx, eax
0x14003ecad  test    eax, eax
0x14003ecaf  js      short loc_14003ECDC
0x14003ecb1  call    cs:__imp_CoImpersonateClient
0x14003ecb7  test    eax, eax
0x14003ecb9  js      short loc_14003ECD7
0x14003ecbb  mov     rax, [rdi]
0x14003ecbe  mov     rdx, rsi
0x14003ecc1  mov     rcx, rdi
0x14003ecc4  mov     rax, [rax+20h]
0x14003ecc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003eccd  mov     ebx, eax
0x14003eccf  call    cs:__imp_CoRevertToSelf
0x14003ecd5  jmp     short loc_14003ECDC
0x14003ecd7  mov     ebx, 80041003h
0x14003ecdc  mov     r9d, [rbp+arg_0]; int
0x14003ece0  mov     edx, 5; unsigned int
0x14003ece5  mov     r8, [rbp+arg_18]; struct IUnknown *
0x14003ece9  mov     rcx, r14; struct ProxyContainer *
0x14003ecec  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x14003ecf1  mov     r8d, [rbp+arg_10]; int
0x14003ecf5  mov     rdx, [rbp+var_10]; struct IServerSecurity *
0x14003ecf9  mov     rcx, [rbp+ppInterface]; struct IUnknown *
0x14003ecfd  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x14003ed02  test    ebx, ebx
0x14003ed04  jns     short loc_14003ED17
0x14003ed06  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003ed0c  mov     rcx, rax
0x14003ed0f  mov     edx, ebx
0x14003ed11  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14003ed17  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ed1e  lea     rax, WPP_GLOBAL_Control
0x14003ed25  cmp     rcx, rax
0x14003ed28  jz      short loc_14003ED90
0x14003ed2a  test    byte ptr [rcx+1Ch], 4
0x14003ed2e  jz      short loc_14003ED90
0x14003ed30  cmp     byte ptr [rcx+19h], 2
0x14003ed34  jb      short loc_14003ED90
0x14003ed36  mov     edx, 31h ; '1'
0x14003ed3b  mov     r9d, ebx
0x14003ed3e  jmp     short loc_14003ED80
0x14003ed40  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003ed46  mov     ebx, 80041024h
0x14003ed4b  mov     rcx, rax
0x14003ed4e  mov     edx, ebx
0x14003ed50  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14003ed56  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ed5d  lea     rax, WPP_GLOBAL_Control
0x14003ed64  cmp     rcx, rax
0x14003ed67  jz      short loc_14003ED90
0x14003ed69  test    byte ptr [rcx+1Ch], 4
0x14003ed6d  jz      short loc_14003ED90
0x14003ed6f  cmp     byte ptr [rcx+19h], 2
0x14003ed73  jb      short loc_14003ED90
0x14003ed75  mov     edx, 32h ; '2'
0x14003ed7a  mov     r9d, 80041024h
0x14003ed80  mov     rcx, [rcx+10h]
0x14003ed84  lea     r8, WPP_d3ea76c96a8339db06b7a6ae92e79012_Traceguids
0x14003ed8b  call    WPP_SF_d
0x14003ed90  mov     eax, ebx
0x14003ed92  add     rsp, 40h
0x14003ed96  pop     r14
0x14003ed98  pop     rdi
0x14003ed99  pop     rsi
0x14003ed9a  pop     rbx
0x14003ed9b  pop     rbp
0x14003ed9c  retn
```
