# CInterceptor_IWbemSyncUnboundObjectSink::Begin_Interface_Consumer(bool,IUnknown *,_GUID const &,ulong,int &,IUnknown * &,IServerSecurity * &,int &,IUnknown * &,int &,IUnknown * &)

- ea: `0x140036450`
- end: `0x140036791`
- name: `?Begin_Interface_Consumer@CInterceptor_IWbemSyncUnboundObjectSink@@IEAAJ_NPEAUIUnknown@@AEBU_GUID@@KAEAHAEAPEAU2@AEAPEAUIServerSecurity@@3434@Z`
- size: `833`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncUnboundObjectSink *this, char, struct IUnknown *, struct _GUID *, unsigned int, int *, struct IUnknown **ppOldObject, struct IServerSecurity **, int *, struct IUnknown **, int *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140038e00`

## callees

- `0x1400053dc`
- `0x1400054a0`
- `0x140005544`
- `0x1400058dc`
- `0x140006c64`
- `0x14001ca74`
- `0x1400234b8`
- `0x140036450`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14003672f`
- `wbemcomn!GetMemLogObject` at `0x14003672f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003673a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003673a`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1400365a8`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1400365a8`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1400365f9`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1400365f9`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1400365bc`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1400365bc`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400365d0`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400365d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInterceptor_IWbemSyncUnboundObjectSink::Begin_Interface_Consumer(
        CInterceptor_IWbemSyncUnboundObjectSink *this,
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
  CInterceptor_IWbemSyncUnboundObjectSink *v16; // r12
  struct IUnknown **v17; // rsi
  struct IServerSecurity **v18; // r14
  HRESULT v19; // ebx
  int v20; // eax
  struct IUnknown **v21; // rbx
  unsigned int v22; // eax
  unsigned int v23; // edx
  unsigned int CurrentImpersonationLevel; // r12d
  int v26; // eax
  struct IUnknown **v27; // rbx
  unsigned int v28; // eax
  unsigned int v29; // edx
  CMemoryLog *MemLogObject; // rax
  unsigned int v32; // [rsp+78h] [rbp+10h] BYREF
  void *ppInterface; // [rsp+88h] [rbp+20h] BYREF

  ppInterface = a4;
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
  if ( !a2 )
  {
    ppInterface = 0;
    if ( CoGetCallContext(&IID_IUnknown, &ppInterface) >= 0 )
    {
      CurrentImpersonationLevel = 3;
      v19 = CoImpersonateClient();
      if ( v19 >= 0 )
      {
        CurrentImpersonationLevel = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
        CoRevertToSelf();
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 16LL))(ppInterface);
      if ( v19 < 0 )
        goto LABEL_9;
      if ( CurrentImpersonationLevel == 2 )
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
        goto LABEL_9;
      }
      v16 = this;
    }
    v32 = 0;
    v19 = ProviderSubSystem_Common_Globals::BeginImpersonation(v17, v18, v15, &v32);
    if ( v19 < 0 )
      goto LABEL_9;
    v26 = ProviderSubSystem_Common_Globals::SetProxyState(
            (CInterceptor_IWbemSyncUnboundObjectSink *)((char *)v16 + 112),
            0,
            &IID_IWbemUnboundObjectSink,
            a3,
            v13,
            v12);
    v19 = v26;
    if ( v26 == -2147217406 )
    {
      v19 = 0;
      *a10 = a3;
      *a9 = 0;
      goto LABEL_30;
    }
    if ( v26 >= 0 )
    {
      v27 = a10;
      *a9 = 1;
      *v27 = *v13;
      v28 = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
      v19 = ProviderSubSystem_Common_Globals::SetCloaking(*v27, v29, v28);
      if ( v19 >= 0 )
        goto LABEL_9;
      ProviderSubSystem_Common_Globals::RevertProxyState(
        (CInterceptor_IWbemSyncUnboundObjectSink *)((char *)v16 + 112),
        0,
        *v13,
        *v12);
      if ( v19 == -2147217406 )
        return 2147749890LL;
    }
    ProviderSubSystem_Common_Globals::EndImpersonation(*v17, *v18, *v15);
LABEL_29:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v19);
    goto LABEL_30;
  }
  v32 = 0;
  v19 = ProviderSubSystem_Common_Globals::BeginImpersonation(v17, v18, v15, &v32);
  if ( v19 < 0 )
    goto LABEL_9;
  v20 = ProviderSubSystem_Common_Globals::SetProxyState(
          (CInterceptor_IWbemSyncUnboundObjectSink *)((char *)v16 + 112),
          0,
          &IID_IWbemUnboundObjectSink,
          a3,
          v13,
          v12);
  v19 = v20;
  if ( v20 == -2147217406 )
  {
    *a10 = a3;
    *a9 = 0;
    return 2147749890LL;
  }
  if ( v20 >= 0 )
  {
    v21 = a10;
    *a9 = 1;
    *v21 = *v13;
    v22 = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
    v19 = ProviderSubSystem_Common_Globals::SetCloaking(*v21, v23, v22);
    if ( v19 >= 0 )
      goto LABEL_9;
    ProviderSubSystem_Common_Globals::RevertProxyState(
      (CInterceptor_IWbemSyncUnboundObjectSink *)((char *)v16 + 112),
      0,
      *v13,
      *v12);
    if ( v19 == -2147217406 )
      return 2147749890LL;
  }
  ProviderSubSystem_Common_Globals::EndImpersonation(*v17, *v18, *v15);
LABEL_9:
  if ( v19 == -2147217406 )
    return 2147749890LL;
  if ( v19 < 0 )
    goto LABEL_29;
LABEL_30:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (unsigned int)v19);
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x140036450  mov     rax, rsp
0x140036453  mov     [rax+18h], rbx
0x140036457  mov     [rax+20h], r9
0x14003645b  mov     [rax+8], rcx
0x14003645f  push    rbp
0x140036460  push    rsi
0x140036461  push    rdi
0x140036462  push    r12
0x140036464  push    r13
0x140036466  push    r14
0x140036468  push    r15
0x14003646a  sub     rsp, 30h
0x14003646e  mov     r13, [rsp+68h+arg_50]
0x140036476  xor     ebx, ebx
0x140036478  mov     rbp, [rsp+68h+arg_58]
0x140036480  mov     rdi, r8
0x140036483  mov     r15, [rsp+68h+arg_28]
0x14003648b  mov     r12, rcx
0x14003648e  mov     rsi, [rsp+68h+ppOldObject]
0x140036496  mov     r14, [rsp+68h+arg_38]
0x14003649e  mov     [r13+0], ebx
0x1400364a2  mov     [rbp+0], rbx
0x1400364a6  mov     [r15], ebx
0x1400364a9  mov     [rsi], rbx
0x1400364ac  mov     [r14], rbx
0x1400364af  test    dl, dl
0x1400364b1  jz      loc_140036591
0x1400364b7  lea     r9, [rax+10h]; unsigned int *
0x1400364bb  mov     [rax+10h], ebx
0x1400364be  mov     r8, r15; int *
0x1400364c1  mov     rdx, r14; struct IServerSecurity **
0x1400364c4  mov     rcx, rsi; ppInterface
0x1400364c7  call    ?BeginImpersonation@ProviderSubSystem_Common_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAHPEAK@Z; ProviderSubSystem_Common_Globals::BeginImpersonation(IUnknown * &,IServerSecurity * &,int &,ulong *)
0x1400364cc  mov     ebx, eax
0x1400364ce  test    eax, eax
0x1400364d0  js      loc_14003657B
0x1400364d6  mov     [rsp+68h+var_40], r13; int *
0x1400364db  lea     r8, IID_IWbemUnboundObjectSink; struct _GUID *
0x1400364e2  mov     r9, rdi; struct IUnknown *
0x1400364e5  mov     [rsp+68h+var_48], rbp; struct IUnknown **
0x1400364ea  xor     edx, edx; unsigned int
0x1400364ec  lea     rcx, [r12+70h]; struct ProxyContainer *
0x1400364f1  call    ?SetProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KAEBU_GUID@@PEAUIUnknown@@AEAPEAU4@AEAH@Z; ProviderSubSystem_Common_Globals::SetProxyState(ProxyContainer &,ulong,_GUID const &,IUnknown *,IUnknown * &,int &)
0x1400364f6  mov     ebx, eax
0x1400364f8  cmp     eax, 80041002h
0x1400364fd  jnz     short loc_14003651A
0x1400364ff  mov     rax, [rsp+68h+arg_48]
0x140036507  mov     [rax], rdi
0x14003650a  mov     rax, [rsp+68h+arg_40]
0x140036512  mov     dword ptr [rax], 0
0x140036518  jmp     short loc_140036587
0x14003651a  test    eax, eax
0x14003651c  js      short loc_14003656D
0x14003651e  mov     rax, [rsp+68h+arg_40]
0x140036526  mov     rbx, [rsp+68h+arg_48]
0x14003652e  mov     dword ptr [rax], 1
0x140036534  mov     rax, [rbp+0]
0x140036538  mov     [rbx], rax
0x14003653b  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x140036540  mov     rcx, [rbx]; struct IUnknown *
0x140036543  mov     r8d, eax; unsigned int
0x140036546  call    ?SetCloaking@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@KK@Z; ProviderSubSystem_Common_Globals::SetCloaking(IUnknown *,ulong,ulong)
0x14003654b  mov     ebx, eax
0x14003654d  test    eax, eax
0x14003654f  jns     short loc_14003657B
0x140036551  mov     r9d, [r13+0]; int
0x140036555  lea     rcx, [r12+70h]; struct ProxyContainer *
0x14003655a  mov     r8, [rbp+0]; struct IUnknown *
0x14003655e  xor     edx, edx; unsigned int
0x140036560  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x140036565  cmp     ebx, 80041002h
0x14003656b  jz      short loc_140036587
0x14003656d  mov     r8d, [r15]; int
0x140036570  mov     rdx, [r14]; struct IServerSecurity *
0x140036573  mov     rcx, [rsi]; struct IUnknown *
0x140036576  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x14003657b  cmp     ebx, 80041002h
0x140036581  jnz     loc_14003672B
0x140036587  mov     eax, 80041002h
0x14003658c  jmp     loc_140036779
0x140036591  lea     rdx, [rsp+68h+ppInterface]; ppInterface
0x140036599  mov     [rsp+68h+ppInterface], rbx
0x1400365a1  lea     rcx, IID_IUnknown; riid
0x1400365a8  call    cs:__imp_CoGetCallContext
0x1400365ae  test    eax, eax
0x1400365b0  js      loc_14003665A
0x1400365b6  mov     r12d, 3
0x1400365bc  call    cs:__imp_CoImpersonateClient
0x1400365c2  mov     ebx, eax
0x1400365c4  test    eax, eax
0x1400365c6  js      short loc_1400365D6
0x1400365c8  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x1400365cd  mov     r12d, eax
0x1400365d0  call    cs:__imp_CoRevertToSelf
0x1400365d6  mov     rcx, [rsp+68h+ppInterface]
0x1400365de  mov     rax, [rcx]
0x1400365e1  mov     rax, [rax+10h]
0x1400365e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400365ea  test    ebx, ebx
0x1400365ec  js      short loc_14003657B
0x1400365ee  cmp     r12d, 2
0x1400365f2  jnz     short loc_140036653
0x1400365f4  mov     rdx, rsi; ppOldObject
0x1400365f7  xor     ecx, ecx; pNewObject
0x1400365f9  call    cs:__imp_CoSwitchCallContext
0x1400365ff  mov     ebx, eax
0x140036601  test    eax, eax
0x140036603  js      short loc_140036635
0x140036605  mov     rcx, [rsi]
0x140036608  lea     rdx, IID_IServerSecurity
0x14003660f  mov     r8, r14
0x140036612  mov     rax, [rcx]
0x140036615  mov     rax, [rax]
0x140036618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003661d  mov     ebx, eax
0x14003661f  test    eax, eax
0x140036621  js      short loc_140036635
0x140036623  mov     rcx, [r14]
0x140036626  mov     rax, [rcx]
0x140036629  mov     rax, [rax+30h]
0x14003662d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036632  mov     [r15], eax
0x140036635  mov     rax, [rsp+68h+arg_48]
0x14003663d  mov     [rax], rdi
0x140036640  mov     rax, [rsp+68h+arg_40]
0x140036648  mov     dword ptr [rax], 0
0x14003664e  jmp     loc_14003657B
0x140036653  mov     r12, [rsp+68h+arg_0]
0x140036658  xor     ebx, ebx
0x14003665a  lea     r9, [rsp+68h+arg_8]; unsigned int *
0x14003665f  mov     [rsp+68h+arg_8], ebx
0x140036663  mov     r8, r15; int *
0x140036666  mov     rdx, r14; struct IServerSecurity **
0x140036669  mov     rcx, rsi; ppInterface
0x14003666c  call    ?BeginImpersonation@ProviderSubSystem_Common_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAHPEAK@Z; ProviderSubSystem_Common_Globals::BeginImpersonation(IUnknown * &,IServerSecurity * &,int &,ulong *)
0x140036671  mov     ebx, eax
0x140036673  test    eax, eax
0x140036675  js      loc_14003657B
0x14003667b  mov     [rsp+68h+var_40], r13; int *
0x140036680  lea     r8, IID_IWbemUnboundObjectSink; struct _GUID *
0x140036687  mov     r9, rdi; struct IUnknown *
0x14003668a  mov     [rsp+68h+var_48], rbp; struct IUnknown **
0x14003668f  xor     edx, edx; unsigned int
0x140036691  lea     rcx, [r12+70h]; struct ProxyContainer *
0x140036696  call    ?SetProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KAEBU_GUID@@PEAUIUnknown@@AEAPEAU4@AEAH@Z; ProviderSubSystem_Common_Globals::SetProxyState(ProxyContainer &,ulong,_GUID const &,IUnknown *,IUnknown * &,int &)
0x14003669b  mov     ebx, eax
0x14003669d  cmp     eax, 80041002h
0x1400366a2  jnz     short loc_1400366C0
0x1400366a4  mov     rax, [rsp+68h+arg_48]
0x1400366ac  xor     ebx, ebx
0x1400366ae  mov     [rax], rdi
0x1400366b1  mov     rax, [rsp+68h+arg_40]
0x1400366b9  mov     [rax], ebx
0x1400366bb  jmp     loc_140036740
0x1400366c0  test    eax, eax
0x1400366c2  js      short loc_14003671B
0x1400366c4  mov     rax, [rsp+68h+arg_40]
0x1400366cc  mov     rbx, [rsp+68h+arg_48]
0x1400366d4  mov     dword ptr [rax], 1
0x1400366da  mov     rax, [rbp+0]
0x1400366de  mov     [rbx], rax
0x1400366e1  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x1400366e6  mov     rcx, [rbx]; struct IUnknown *
0x1400366e9  mov     r8d, eax; unsigned int
0x1400366ec  call    ?SetCloaking@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@KK@Z; ProviderSubSystem_Common_Globals::SetCloaking(IUnknown *,ulong,ulong)
0x1400366f1  mov     ebx, eax
0x1400366f3  test    eax, eax
0x1400366f5  jns     loc_14003657B
0x1400366fb  mov     r9d, [r13+0]; int
0x1400366ff  lea     rcx, [r12+70h]; struct ProxyContainer *
0x140036704  mov     r8, [rbp+0]; struct IUnknown *
0x140036708  xor     edx, edx; unsigned int
0x14003670a  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x14003670f  cmp     ebx, 80041002h
0x140036715  jz      loc_140036587
0x14003671b  mov     r8d, [r15]; int
0x14003671e  mov     rdx, [r14]; struct IServerSecurity *
0x140036721  mov     rcx, [rsi]; struct IUnknown *
0x140036724  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x140036729  jmp     short loc_14003672F
0x14003672b  test    ebx, ebx
0x14003672d  jns     short loc_140036740
0x14003672f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140036735  mov     rcx, rax
0x140036738  mov     edx, ebx
0x14003673a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140036740  mov     rcx, cs:WPP_GLOBAL_Control
0x140036747  lea     rax, WPP_GLOBAL_Control
0x14003674e  cmp     rcx, rax
0x140036751  jz      short loc_140036777
0x140036753  test    byte ptr [rcx+1Ch], 4
0x140036757  jz      short loc_140036777
0x140036759  cmp     byte ptr [rcx+19h], 2
0x14003675d  jb      short loc_140036777
0x14003675f  mov     rcx, [rcx+10h]
0x140036763  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14003676a  mov     edx, 0Ch
0x14003676f  mov     r9d, ebx
0x140036772  call    WPP_SF_d
0x140036777  mov     eax, ebx
0x140036779  mov     rbx, [rsp+68h+arg_10]
0x140036781  add     rsp, 30h
0x140036785  pop     r15
0x140036787  pop     r14
0x140036789  pop     r13
0x14003678b  pop     r12
0x14003678d  pop     rdi
0x14003678e  pop     rsi
0x14003678f  pop     rbp
0x140036790  retn
```
