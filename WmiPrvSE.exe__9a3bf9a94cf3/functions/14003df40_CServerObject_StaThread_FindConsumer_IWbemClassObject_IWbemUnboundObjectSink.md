# CServerObject_StaThread::FindConsumer(IWbemClassObject *,IWbemUnboundObjectSink * *)

- ea: `0x14003df40`
- end: `0x14003e244`
- name: `?FindConsumer@CServerObject_StaThread@@UEAAJPEAUIWbemClassObject@@PEAPEAUIWbemUnboundObjectSink@@@Z`
- size: `772`
- prototype: `__int64 __fastcall(CServerObject_StaThread *__hidden this, struct IWbemClassObject *, struct IWbemUnboundObjectSink **)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400053dc`
- `0x1400054a0`
- `0x140005544`
- `0x1400058dc`
- `0x140006c64`
- `0x14000a530`
- `0x14001ca74`
- `0x1400234b8`
- `0x140035f94`
- `0x140038ab0`
- `0x14003df40`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14003e19f`
- `wbemcomn!GetMemLogObject` at `0x14003e1d9`
- `wbemcomn!GetMemLogObject` at `0x14003e19f`
- `wbemcomn!GetMemLogObject` at `0x14003e1d9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003e1aa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003e1e9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003e1aa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003e1e9`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14003e03b`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14003e03b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14003e015`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14003e05d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14003e015`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14003e05d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CServerObject_StaThread::FindConsumer(
        struct IUnknown **this,
        struct IWbemClassObject *a2,
        struct IWbemUnboundObjectSink **a3)
{
  int v6; // ebx
  int v7; // eax
  struct IUnknown *v8; // rdi
  unsigned int CurrentImpersonationLevel; // eax
  unsigned int v10; // edx
  LPVOID v11; // rax
  unsigned __int64 v12; // r14
  CInterceptor_IWbemSyncUnboundObjectSink *v13; // rdi
  int v14; // eax
  char *v15; // rcx
  bool v16; // zf
  void (__fastcall *v17)(char *); // rax
  CMemoryLog *MemLogObject; // rax
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r9
  CMemoryLog *v22; // rax
  __int64 v24; // [rsp+30h] [rbp-20h] BYREF
  struct IUnknown *v25; // [rsp+38h] [rbp-18h] BYREF
  struct IServerSecurity *v26; // [rsp+40h] [rbp-10h] BYREF
  struct IUnknown *ppInterface; // [rsp+48h] [rbp-8h] BYREF
  LPVOID v28; // [rsp+80h] [rbp+30h] BYREF
  int v29; // [rsp+98h] [rbp+48h] BYREF

  if ( this[58] )
  {
    v24 = 0;
    v29 = 0;
    ppInterface = 0;
    v26 = 0;
    v6 = ProviderSubSystem_Common_Globals::BeginImpersonation(&ppInterface, &v26, &v29, 0);
    if ( v6 >= 0 )
    {
      LODWORD(v28) = 0;
      v25 = 0;
      v7 = ProviderSubSystem_Common_Globals::SetProxyState(
             (struct ProxyContainer *)(this + 66),
             4u,
             &IID_IWbemEventConsumerProvider,
             this[58],
             &v25,
             (int *)&v28);
      v6 = v7;
      if ( v7 == -2147217406 )
      {
        v6 = ((__int64 (__fastcall *)(struct IUnknown *, struct IWbemClassObject *, __int64 *))this[58]->lpVtbl[1].QueryInterface)(
               this[58],
               a2,
               &v24);
        CoRevertToSelf();
      }
      else if ( v7 >= 0 )
      {
        v8 = v25;
        CurrentImpersonationLevel = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
        v6 = ProviderSubSystem_Common_Globals::SetCloaking(v8, v10, CurrentImpersonationLevel);
        if ( v6 >= 0 )
        {
          if ( CoImpersonateClient() < 0 )
          {
            v6 = -2147217405;
          }
          else
          {
            v6 = ((__int64 (__fastcall *)(struct IUnknown *, struct IWbemClassObject *, __int64 *))v8->lpVtbl[1].QueryInterface)(
                   v8,
                   a2,
                   &v24);
            CoRevertToSelf();
          }
        }
        ProviderSubSystem_Common_Globals::RevertProxyState((struct ProxyContainer *)(this + 66), 4u, v25, (int)v28);
      }
      ProviderSubSystem_Common_Globals::EndImpersonation(ppInterface, v26, v29);
      if ( v6 >= 0 && a3 )
      {
        v11 = operator new(0xC0u);
        v28 = v11;
        v12 = (unsigned __int64)(this + 34);
        v13 = v11
            ? (CInterceptor_IWbemSyncUnboundObjectSink *)CInterceptor_IWbemSyncUnboundObjectSink::CInterceptor_IWbemSyncUnboundObjectSink(
                                                           v11,
                                                           this[45],
                                                           v24,
                                                           v12 & -(__int64)(this != (struct IUnknown **)32),
                                                           this[64])
            : 0LL;
        if ( v13 )
        {
          (*(void (__fastcall **)(CInterceptor_IWbemSyncUnboundObjectSink *))(*(_QWORD *)v13 + 8LL))(v13);
          v6 = CInterceptor_IWbemSyncUnboundObjectSink::Initialize(v13);
          if ( v6 >= 0 )
          {
            v28 = 0;
            (*(void (__fastcall **)(char *))(*(_QWORD *)v12 + 48LL))((char *)this + 272);
            v14 = (*(__int64 (__fastcall **)(char *, __int64, LPVOID *))(*(_QWORD *)v12 + 64LL))(
                    (char *)this + 272,
                    (__int64)v13 + 32,
                    &v28);
            v15 = (char *)(this + 34);
            v16 = v14 == 0;
            v17 = *(void (__fastcall **)(char *))(*(_QWORD *)v12 + 56LL);
            if ( v16 )
            {
              v17(v15);
              *a3 = (struct IWbemUnboundObjectSink *)v13;
              (*(void (__fastcall **)(CInterceptor_IWbemSyncUnboundObjectSink *))(*(_QWORD *)v13 + 8LL))(v13);
            }
            else
            {
              v17(v15);
              v6 = -2147217402;
            }
          }
          (*(void (__fastcall **)(CInterceptor_IWbemSyncUnboundObjectSink *))(*(_QWORD *)v13 + 16LL))(v13);
        }
      }
    }
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v6 < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v6);
    }
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v20 = 47;
      v21 = (unsigned int)v6;
LABEL_34:
      WPP_SF_d(v19[2], v20, WPP_d3ea76c96a8339db06b7a6ae92e79012_Traceguids, v21);
    }
  }
  else
  {
    v22 = GetMemLogObject();
    v6 = -2147217372;
    CMemoryLog::Write(v22, -2147217372);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v20 = 48;
      v21 = 2147749924LL;
      goto LABEL_34;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14003df40  mov     [rsp-28h+arg_8], rbx
0x14003df45  mov     [rsp-28h+arg_10], rsi
0x14003df4a  push    rbp
0x14003df4b  push    rdi
0x14003df4c  push    r12
0x14003df4e  push    r14
0x14003df50  push    r15
0x14003df52  mov     rbp, rsp
0x14003df55  sub     rsp, 50h
0x14003df59  mov     r12, r8
0x14003df5c  mov     r15, rdx
0x14003df5f  mov     rsi, rcx
0x14003df62  cmp     qword ptr [rcx+1D0h], 0
0x14003df6a  jz      loc_14003E1D9
0x14003df70  mov     [rbp+var_20], 0
0x14003df78  mov     [rbp+arg_18], 0
0x14003df7f  mov     [rbp+ppInterface], 0
0x14003df87  mov     [rbp+var_10], 0
0x14003df8f  xor     r9d, r9d; unsigned int *
0x14003df92  lea     r8, [rbp+arg_18]; int *
0x14003df96  lea     rdx, [rbp+var_10]; struct IServerSecurity **
0x14003df9a  lea     rcx, [rbp+ppInterface]; ppInterface
0x14003df9e  call    ?BeginImpersonation@ProviderSubSystem_Common_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAHPEAK@Z; ProviderSubSystem_Common_Globals::BeginImpersonation(IUnknown * &,IServerSecurity * &,int &,ulong *)
0x14003dfa3  mov     ebx, eax
0x14003dfa5  test    eax, eax
0x14003dfa7  js      loc_14003E186
0x14003dfad  mov     dword ptr [rbp+arg_0], 0
0x14003dfb4  mov     [rbp+var_18], 0
0x14003dfbc  lea     r14, [rsi+210h]
0x14003dfc3  lea     rax, [rbp+arg_0]
0x14003dfc7  mov     [rsp+50h+var_28], rax; int *
0x14003dfcc  lea     rax, [rbp+var_18]
0x14003dfd0  mov     [rsp+50h+var_30], rax; struct IUnknown **
0x14003dfd5  mov     r9, [rsi+1D0h]; struct IUnknown *
0x14003dfdc  lea     r8, IID_IWbemEventConsumerProvider; struct _GUID *
0x14003dfe3  mov     edx, 4; unsigned int
0x14003dfe8  mov     rcx, r14; struct ProxyContainer *
0x14003dfeb  call    ?SetProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KAEBU_GUID@@PEAUIUnknown@@AEAPEAU4@AEAH@Z; ProviderSubSystem_Common_Globals::SetProxyState(ProxyContainer &,ulong,_GUID const &,IUnknown *,IUnknown * &,int &)
0x14003dff0  mov     ebx, eax
0x14003dff2  cmp     eax, 80041002h
0x14003dff7  jnz     short loc_14003E01D
0x14003dff9  mov     rcx, [rsi+1D0h]
0x14003e000  mov     rax, [rcx]
0x14003e003  lea     r8, [rbp+var_20]
0x14003e007  mov     rdx, r15
0x14003e00a  mov     rax, [rax+18h]
0x14003e00e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e013  mov     ebx, eax
0x14003e015  call    cs:__imp_CoRevertToSelf
0x14003e01b  jmp     short loc_14003E07F
0x14003e01d  test    eax, eax
0x14003e01f  js      short loc_14003E07F
0x14003e021  mov     rdi, [rbp+var_18]
0x14003e025  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x14003e02a  mov     r8d, eax; unsigned int
0x14003e02d  mov     rcx, rdi; struct IUnknown *
0x14003e030  call    ?SetCloaking@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@KK@Z; ProviderSubSystem_Common_Globals::SetCloaking(IUnknown *,ulong,ulong)
0x14003e035  mov     ebx, eax
0x14003e037  test    eax, eax
0x14003e039  js      short loc_14003E06A
0x14003e03b  call    cs:__imp_CoImpersonateClient
0x14003e041  test    eax, eax
0x14003e043  js      short loc_14003E065
0x14003e045  mov     rax, [rdi]
0x14003e048  lea     r8, [rbp+var_20]
0x14003e04c  mov     rdx, r15
0x14003e04f  mov     rcx, rdi
0x14003e052  mov     rax, [rax+18h]
0x14003e056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e05b  mov     ebx, eax
0x14003e05d  call    cs:__imp_CoRevertToSelf
0x14003e063  jmp     short loc_14003E06A
0x14003e065  mov     ebx, 80041003h
0x14003e06a  mov     r9d, dword ptr [rbp+arg_0]; int
0x14003e06e  mov     r8, [rbp+var_18]; struct IUnknown *
0x14003e072  mov     edx, 4; unsigned int
0x14003e077  mov     rcx, r14; struct ProxyContainer *
0x14003e07a  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x14003e07f  mov     r8d, [rbp+arg_18]; int
0x14003e083  mov     rdx, [rbp+var_10]; struct IServerSecurity *
0x14003e087  mov     rcx, [rbp+ppInterface]; struct IUnknown *
0x14003e08b  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x14003e090  test    ebx, ebx
0x14003e092  js      loc_14003E186
0x14003e098  test    r12, r12
0x14003e09b  jz      loc_14003E186
0x14003e0a1  mov     ecx, 0C0h; dwBytes
0x14003e0a6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003e0ab  mov     [rbp+arg_0], rax
0x14003e0af  lea     r14, [rsi+110h]
0x14003e0b6  test    rax, rax
0x14003e0b9  jz      short loc_14003E0EC
0x14003e0bb  lea     rcx, [rsi-20h]
0x14003e0bf  neg     rcx
0x14003e0c2  sbb     r9, r9
0x14003e0c5  and     r9, r14
0x14003e0c8  mov     rcx, [rsi+200h]
0x14003e0cf  mov     [rsp+50h+var_30], rcx
0x14003e0d4  mov     r8, [rbp+var_20]
0x14003e0d8  mov     rdx, [rsi+168h]
0x14003e0df  mov     rcx, rax
0x14003e0e2  call    ??0CInterceptor_IWbemSyncUnboundObjectSink@@QEAA@AEAVWmiAllocator@@PEAUIUnknown@@PEAV?$WmiContainerController@PEAX@@AEAVCServerObject_ProviderRegistrationV1@@@Z; CInterceptor_IWbemSyncUnboundObjectSink::CInterceptor_IWbemSyncUnboundObjectSink(WmiAllocator &,IUnknown *,WmiContainerController<void *> *,CServerObject_ProviderRegistrationV1 &)
0x14003e0e7  mov     rdi, rax
0x14003e0ea  jmp     short loc_14003E0EE
0x14003e0ec  xor     edi, edi
0x14003e0ee  test    rdi, rdi
0x14003e0f1  jz      loc_14003E186
0x14003e0f7  mov     rax, [rdi]
0x14003e0fa  mov     rcx, rdi
0x14003e0fd  mov     rax, [rax+8]
0x14003e101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e106  mov     rcx, rdi; this
0x14003e109  call    ?Initialize@CInterceptor_IWbemSyncUnboundObjectSink@@QEAAJXZ; CInterceptor_IWbemSyncUnboundObjectSink::Initialize(void)
0x14003e10e  mov     ebx, eax
0x14003e110  test    eax, eax
0x14003e112  js      short loc_14003E177
0x14003e114  mov     [rbp+arg_0], 0
0x14003e11c  mov     rax, [r14]
0x14003e11f  mov     rcx, r14
0x14003e122  mov     rax, [rax+30h]
0x14003e126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e12b  mov     rax, [r14]
0x14003e12e  lea     rdx, [rdi+20h]
0x14003e132  lea     r8, [rbp+arg_0]
0x14003e136  mov     rcx, r14
0x14003e139  mov     rax, [rax+40h]
0x14003e13d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e142  mov     rdx, [r14]
0x14003e145  mov     r8, [rdx+38h]
0x14003e149  mov     rcx, r14
0x14003e14c  test    eax, eax
0x14003e14e  mov     rax, r8
0x14003e151  jnz     short loc_14003E16D
0x14003e153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e158  mov     [r12], rdi
0x14003e15c  mov     rax, [rdi]
0x14003e15f  mov     rcx, rdi
0x14003e162  mov     rax, [rax+8]
0x14003e166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e16b  jmp     short loc_14003E177
0x14003e16d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e172  mov     ebx, 80041006h
0x14003e177  mov     rax, [rdi]
0x14003e17a  mov     rcx, rdi
0x14003e17d  mov     rax, [rax+10h]
0x14003e181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e186  mov     rcx, [rbp+var_20]
0x14003e18a  test    rcx, rcx
0x14003e18d  jz      short loc_14003E19B
0x14003e18f  mov     rax, [rcx]
0x14003e192  mov     rax, [rax+10h]
0x14003e196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e19b  test    ebx, ebx
0x14003e19d  jns     short loc_14003E1B0
0x14003e19f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003e1a5  mov     edx, ebx
0x14003e1a7  mov     rcx, rax
0x14003e1aa  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14003e1b0  lea     rax, WPP_GLOBAL_Control
0x14003e1b7  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e1be  cmp     rcx, rax
0x14003e1c1  jz      short loc_14003E229
0x14003e1c3  test    byte ptr [rcx+1Ch], 4
0x14003e1c7  jz      short loc_14003E229
0x14003e1c9  cmp     byte ptr [rcx+19h], 2
0x14003e1cd  jb      short loc_14003E229
0x14003e1cf  mov     edx, 2Fh ; '/'
0x14003e1d4  mov     r9d, ebx
0x14003e1d7  jmp     short loc_14003E219
0x14003e1d9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003e1df  mov     ebx, 80041024h
0x14003e1e4  mov     edx, ebx
0x14003e1e6  mov     rcx, rax
0x14003e1e9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14003e1ef  lea     rax, WPP_GLOBAL_Control
0x14003e1f6  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e1fd  cmp     rcx, rax
0x14003e200  jz      short loc_14003E229
0x14003e202  test    byte ptr [rcx+1Ch], 4
0x14003e206  jz      short loc_14003E229
0x14003e208  cmp     byte ptr [rcx+19h], 2
0x14003e20c  jb      short loc_14003E229
0x14003e20e  mov     edx, 30h ; '0'
0x14003e213  mov     r9d, 80041024h
0x14003e219  lea     r8, WPP_d3ea76c96a8339db06b7a6ae92e79012_Traceguids
0x14003e220  mov     rcx, [rcx+10h]
0x14003e224  call    WPP_SF_d
0x14003e229  mov     eax, ebx
0x14003e22b  lea     r11, [rsp+50h+var_s0]
0x14003e230  mov     rbx, [r11+38h]
0x14003e234  mov     rsi, [r11+40h]
0x14003e238  mov     rsp, r11
0x14003e23b  pop     r15
0x14003e23d  pop     r14
0x14003e23f  pop     r12
0x14003e241  pop     rdi
0x14003e242  pop     rbp
0x14003e243  retn
```
