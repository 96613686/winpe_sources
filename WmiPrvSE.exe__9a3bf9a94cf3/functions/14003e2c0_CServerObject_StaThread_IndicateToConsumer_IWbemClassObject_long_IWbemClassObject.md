# CServerObject_StaThread::IndicateToConsumer(IWbemClassObject *,long,IWbemClassObject * *)

- ea: `0x14003e2c0`
- end: `0x14003e49b`
- name: `?IndicateToConsumer@CServerObject_StaThread@@UEAAJPEAUIWbemClassObject@@JPEAPEAU2@@Z`
- size: `475`
- prototype: `__int64 __fastcall(CServerObject_StaThread *__hidden this, struct IWbemClassObject *, int, struct IWbemClassObject **)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1400053dc`
- `0x1400054a0`
- `0x140005544`
- `0x1400058dc`
- `0x140006c64`
- `0x14001ca74`
- `0x1400234b8`
- `0x14003e2c0`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14003e3f6`
- `wbemcomn!GetMemLogObject` at `0x14003e430`
- `wbemcomn!GetMemLogObject` at `0x14003e3f6`
- `wbemcomn!GetMemLogObject` at `0x14003e430`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003e401`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003e440`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003e401`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003e440`

## pseudocode

```c
__int64 __fastcall CServerObject_StaThread::IndicateToConsumer(
        CServerObject_StaThread *this,
        struct IWbemClassObject *a2,
        unsigned int a3,
        struct IWbemClassObject **a4)
{
  int v8; // ebx
  struct IUnknown *v9; // r9
  struct ProxyContainer *v10; // rsi
  int v11; // eax
  struct IUnknown *v12; // rdi
  unsigned int CurrentImpersonationLevel; // eax
  unsigned int v14; // edx
  CMemoryLog *MemLogObject; // rax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  CMemoryLog *v19; // rax
  int v21; // [rsp+30h] [rbp-20h] BYREF
  struct IUnknown *v22; // [rsp+38h] [rbp-18h] BYREF
  struct IServerSecurity *v23; // [rsp+40h] [rbp-10h] BYREF
  struct IUnknown *ppInterface; // [rsp+48h] [rbp-8h] BYREF
  int v25; // [rsp+80h] [rbp+30h] BYREF

  if ( *((_QWORD *)this + 59) )
  {
    v21 = 0;
    ppInterface = 0;
    v23 = 0;
    v8 = ProviderSubSystem_Common_Globals::BeginImpersonation(&ppInterface, &v23, &v21, 0);
    if ( v8 < 0 )
      goto LABEL_10;
    v9 = (struct IUnknown *)*((_QWORD *)this + 59);
    v10 = (CServerObject_StaThread *)((char *)this + 520);
    v25 = 0;
    v22 = 0;
    v11 = ProviderSubSystem_Common_Globals::SetProxyState(
            (CServerObject_StaThread *)((char *)this + 520),
            6u,
            &IID_IWbemUnboundObjectSink,
            v9,
            &v22,
            &v25);
    v8 = v11;
    if ( v11 == -2147217406 )
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD, struct IWbemClassObject *, _QWORD, struct IWbemClassObject **))(**((_QWORD **)this + 59) + 24LL))(
             *((_QWORD *)this + 59),
             a2,
             a3,
             a4);
    }
    else if ( v11 >= 0 )
    {
      v12 = v22;
      CurrentImpersonationLevel = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
      v8 = ProviderSubSystem_Common_Globals::SetCloaking(v12, v14, CurrentImpersonationLevel);
      if ( v8 >= 0 )
        v8 = ((__int64 (__fastcall *)(struct IUnknown *, struct IWbemClassObject *, _QWORD, struct IWbemClassObject **))v12->lpVtbl[1].QueryInterface)(
               v12,
               a2,
               a3,
               a4);
      ProviderSubSystem_Common_Globals::RevertProxyState(v10, 6u, v22, v25);
    }
    ProviderSubSystem_Common_Globals::EndImpersonation(ppInterface, v23, v21);
    if ( v8 < 0 )
    {
LABEL_10:
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v8);
    }
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = 51;
      v18 = (unsigned int)v8;
LABEL_19:
      WPP_SF_d(v16[2], v17, WPP_d3ea76c96a8339db06b7a6ae92e79012_Traceguids, v18);
    }
  }
  else
  {
    v19 = GetMemLogObject();
    v8 = -2147217372;
    CMemoryLog::Write(v19, -2147217372);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = 52;
      v18 = 2147749924LL;
      goto LABEL_19;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14003e2c0  mov     [rsp-28h+arg_8], rbx
0x14003e2c5  mov     [rsp-28h+arg_10], rsi
0x14003e2ca  push    rbp
0x14003e2cb  push    rdi
0x14003e2cc  push    r12
0x14003e2ce  push    r14
0x14003e2d0  push    r15
0x14003e2d2  mov     rbp, rsp
0x14003e2d5  sub     rsp, 50h
0x14003e2d9  cmp     qword ptr [rcx+1D8h], 0
0x14003e2e1  mov     r14, r9
0x14003e2e4  mov     r15d, r8d
0x14003e2e7  mov     r12, rdx
0x14003e2ea  mov     rdi, rcx
0x14003e2ed  jz      loc_14003E430
0x14003e2f3  xor     r9d, r9d; unsigned int *
0x14003e2f6  mov     [rbp+var_20], 0
0x14003e2fd  lea     r8, [rbp+var_20]; int *
0x14003e301  mov     [rbp+ppInterface], 0
0x14003e309  lea     rdx, [rbp+var_10]; struct IServerSecurity **
0x14003e30d  mov     [rbp+var_10], 0
0x14003e315  lea     rcx, [rbp+ppInterface]; ppInterface
0x14003e319  call    ?BeginImpersonation@ProviderSubSystem_Common_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAHPEAK@Z; ProviderSubSystem_Common_Globals::BeginImpersonation(IUnknown * &,IServerSecurity * &,int &,ulong *)
0x14003e31e  mov     ebx, eax
0x14003e320  test    eax, eax
0x14003e322  js      loc_14003E3F6
0x14003e328  mov     r9, [rdi+1D8h]; struct IUnknown *
0x14003e32f  lea     rax, [rbp+arg_0]
0x14003e333  mov     [rsp+50h+var_28], rax; int *
0x14003e338  lea     rsi, [rdi+208h]
0x14003e33f  lea     rax, [rbp+var_18]
0x14003e343  mov     [rbp+arg_0], 0
0x14003e34a  lea     r8, IID_IWbemUnboundObjectSink; struct _GUID *
0x14003e351  mov     [rsp+50h+var_30], rax; struct IUnknown **
0x14003e356  mov     edx, 6; unsigned int
0x14003e35b  mov     [rbp+var_18], 0
0x14003e363  mov     rcx, rsi; struct ProxyContainer *
0x14003e366  call    ?SetProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KAEBU_GUID@@PEAUIUnknown@@AEAPEAU4@AEAH@Z; ProviderSubSystem_Common_Globals::SetProxyState(ProxyContainer &,ulong,_GUID const &,IUnknown *,IUnknown * &,int &)
0x14003e36b  mov     ebx, eax
0x14003e36d  cmp     eax, 80041002h
0x14003e372  jnz     short loc_14003E394
0x14003e374  mov     rcx, [rdi+1D8h]
0x14003e37b  mov     r9, r14
0x14003e37e  mov     r8d, r15d
0x14003e381  mov     rdx, r12
0x14003e384  mov     rax, [rcx]
0x14003e387  mov     rax, [rax+18h]
0x14003e38b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e390  mov     ebx, eax
0x14003e392  jmp     short loc_14003E3E1
0x14003e394  test    eax, eax
0x14003e396  js      short loc_14003E3E1
0x14003e398  mov     rdi, [rbp+var_18]
0x14003e39c  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x14003e3a1  mov     r8d, eax; unsigned int
0x14003e3a4  mov     rcx, rdi; struct IUnknown *
0x14003e3a7  call    ?SetCloaking@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@KK@Z; ProviderSubSystem_Common_Globals::SetCloaking(IUnknown *,ulong,ulong)
0x14003e3ac  mov     ebx, eax
0x14003e3ae  test    eax, eax
0x14003e3b0  js      short loc_14003E3CC
0x14003e3b2  mov     rax, [rdi]
0x14003e3b5  mov     r9, r14
0x14003e3b8  mov     r8d, r15d
0x14003e3bb  mov     rdx, r12
0x14003e3be  mov     rcx, rdi
0x14003e3c1  mov     rax, [rax+18h]
0x14003e3c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e3ca  mov     ebx, eax
0x14003e3cc  mov     r9d, [rbp+arg_0]; int
0x14003e3d0  mov     edx, 6; unsigned int
0x14003e3d5  mov     r8, [rbp+var_18]; struct IUnknown *
0x14003e3d9  mov     rcx, rsi; struct ProxyContainer *
0x14003e3dc  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x14003e3e1  mov     r8d, [rbp+var_20]; int
0x14003e3e5  mov     rdx, [rbp+var_10]; struct IServerSecurity *
0x14003e3e9  mov     rcx, [rbp+ppInterface]; struct IUnknown *
0x14003e3ed  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x14003e3f2  test    ebx, ebx
0x14003e3f4  jns     short loc_14003E407
0x14003e3f6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003e3fc  mov     rcx, rax
0x14003e3ff  mov     edx, ebx
0x14003e401  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14003e407  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e40e  lea     rax, WPP_GLOBAL_Control
0x14003e415  cmp     rcx, rax
0x14003e418  jz      short loc_14003E480
0x14003e41a  test    byte ptr [rcx+1Ch], 4
0x14003e41e  jz      short loc_14003E480
0x14003e420  cmp     byte ptr [rcx+19h], 2
0x14003e424  jb      short loc_14003E480
0x14003e426  mov     edx, 33h ; '3'
0x14003e42b  mov     r9d, ebx
0x14003e42e  jmp     short loc_14003E470
0x14003e430  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003e436  mov     ebx, 80041024h
0x14003e43b  mov     rcx, rax
0x14003e43e  mov     edx, ebx
0x14003e440  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14003e446  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e44d  lea     rax, WPP_GLOBAL_Control
0x14003e454  cmp     rcx, rax
0x14003e457  jz      short loc_14003E480
0x14003e459  test    byte ptr [rcx+1Ch], 4
0x14003e45d  jz      short loc_14003E480
0x14003e45f  cmp     byte ptr [rcx+19h], 2
0x14003e463  jb      short loc_14003E480
0x14003e465  mov     edx, 34h ; '4'
0x14003e46a  mov     r9d, 80041024h
0x14003e470  mov     rcx, [rcx+10h]
0x14003e474  lea     r8, WPP_d3ea76c96a8339db06b7a6ae92e79012_Traceguids
0x14003e47b  call    WPP_SF_d
0x14003e480  lea     r11, [rsp+50h+var_s0]
0x14003e485  mov     eax, ebx
0x14003e487  mov     rbx, [r11+38h]
0x14003e48b  mov     rsi, [r11+40h]
0x14003e48f  mov     rsp, r11
0x14003e492  pop     r15
0x14003e494  pop     r14
0x14003e496  pop     r12
0x14003e498  pop     rdi
0x14003e499  pop     rbp
0x14003e49a  retn
```
