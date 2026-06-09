# CServerObject_StaThread::CancelAsyncCall(IWbemObjectSink *)

- ea: `0x1400294c0`
- end: `0x140029628`
- name: `?CancelAsyncCall@CServerObject_StaThread@@UEAAJPEAUIWbemObjectSink@@@Z`
- size: `360`
- prototype: `__int64 __fastcall(CServerObject_StaThread *__hidden this, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400053dc`
- `0x1400054a0`
- `0x1400055e4`
- `0x1400058dc`
- `0x1400234b8`
- `0x1400294c0`
- `0x14004612c`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1400295cb`
- `wbemcomn!GetMemLogObject` at `0x1400295cb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400295d6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400295d6`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140029516`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140029516`

## pseudocode

```c
__int64 __fastcall CServerObject_StaThread::CancelAsyncCall(CServerObject_StaThread *this, struct IWbemObjectSink *a2)
{
  struct IUnknown *v2; // r9
  struct ProxyContainer *v4; // rbp
  int Proxy; // eax
  HRESULT v6; // ebx
  unsigned __int16 *v7; // rdx
  unsigned __int16 *v8; // r8
  unsigned __int16 *v9; // r9
  int v10; // edi
  struct IUnknown *v11; // rsi
  unsigned int CurrentImpersonationLevel; // eax
  unsigned int v13; // edx
  CMemoryLog *MemLogObject; // rax
  unsigned int v16; // [rsp+20h] [rbp-38h]
  unsigned int v17; // [rsp+28h] [rbp-30h]
  unsigned int v18; // [rsp+30h] [rbp-28h]
  struct IUnknown *v19; // [rsp+60h] [rbp+8h] BYREF

  v2 = (struct IUnknown *)*((_QWORD *)this + 61);
  if ( !v2 )
  {
    v6 = -2147217372;
    goto LABEL_20;
  }
  v4 = (CServerObject_StaThread *)((char *)this + 560);
  v19 = 0;
  Proxy = ProviderSubSystem_Common_Globals::GetProxy(
            (CServerObject_StaThread *)((char *)this + 560),
            0,
            &IID_IWbemServices,
            v2,
            &v19);
  if ( Proxy < 0 )
  {
    if ( Proxy != -2147217406 )
    {
      v6 = -2147217398;
LABEL_20:
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v6);
      goto LABEL_21;
    }
LABEL_18:
    v6 = -2147217379;
    goto LABEL_20;
  }
  v6 = CoImpersonateClient();
  if ( v6 < 0 )
  {
    v10 = 0;
    v6 = -2147217405;
LABEL_9:
    ProviderSubSystem_Common_Globals::RevertProxyState(v4, 0, v19, v10);
    goto LABEL_10;
  }
  v10 = 1;
  if ( ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel() - 3 > 1 )
    v6 = SetInterfaceSecurity(v19, v7, v8, v9, v16, v17, v18);
  if ( v6 < 0 )
    goto LABEL_9;
LABEL_10:
  if ( v6 == -2147217406 )
    goto LABEL_18;
  if ( v6 < 0 )
    goto LABEL_20;
  v11 = v19;
  CurrentImpersonationLevel = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
  v6 = ProviderSubSystem_Common_Globals::SetCloaking(v11, v13, CurrentImpersonationLevel);
  if ( v6 >= 0 )
    v6 = ((__int64 (__fastcall *)(struct IUnknown *, struct IWbemObjectSink *))v11->lpVtbl[1].AddRef)(v11, a2);
  ProviderSubSystem_Common_Globals::RevertProxyState(v4, 0, v19, v10);
  if ( v6 < 0 )
    goto LABEL_20;
LABEL_21:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_d3ea76c96a8339db06b7a6ae92e79012_Traceguids, (unsigned int)v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400294c0  mov     r11, rsp
0x1400294c3  mov     [r11+10h], rbx
0x1400294c7  mov     [r11+18h], rbp
0x1400294cb  push    rsi
0x1400294cc  push    rdi
0x1400294cd  push    r14
0x1400294cf  sub     rsp, 40h
0x1400294d3  mov     r9, [rcx+1E8h]; struct IUnknown *
0x1400294da  mov     r14, rdx
0x1400294dd  test    r9, r9
0x1400294e0  jz      loc_1400295C6
0x1400294e6  lea     rbp, [rcx+230h]
0x1400294ed  mov     qword ptr [r11+8], 0
0x1400294f5  lea     rax, [r11+8]
0x1400294f9  mov     rcx, rbp; struct ProxyContainer *
0x1400294fc  lea     r8, IID_IWbemServices; struct _GUID *
0x140029503  mov     [r11-38h], rax
0x140029507  xor     edx, edx; unsigned int
0x140029509  call    ?GetProxy@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KAEBU_GUID@@PEAUIUnknown@@AEAPEAU4@@Z; ProviderSubSystem_Common_Globals::GetProxy(ProxyContainer &,ulong,_GUID const &,IUnknown *,IUnknown * &)
0x14002950e  test    eax, eax
0x140029510  js      loc_1400295B1
0x140029516  call    cs:__imp_CoImpersonateClient
0x14002951c  mov     ebx, eax
0x14002951e  test    eax, eax
0x140029520  js      short loc_140029545
0x140029522  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x140029527  add     eax, 0FFFFFFFDh
0x14002952a  mov     edi, 1
0x14002952f  cmp     eax, edi
0x140029531  jbe     short loc_14002953F
0x140029533  mov     rcx, [rsp+58h+arg_0]; struct IUnknown *
0x140029538  call    ?SetInterfaceSecurity@@YAJPEAUIUnknown@@PEAG11KKK@Z; SetInterfaceSecurity(IUnknown *,ushort *,ushort *,ushort *,ulong,ulong,ulong)
0x14002953d  mov     ebx, eax
0x14002953f  test    ebx, ebx
0x140029541  js      short loc_14002954C
0x140029543  jmp     short loc_14002955E
0x140029545  xor     edi, edi
0x140029547  mov     ebx, 80041003h
0x14002954c  mov     r8, [rsp+58h+arg_0]; struct IUnknown *
0x140029551  mov     r9d, edi; int
0x140029554  xor     edx, edx; unsigned int
0x140029556  mov     rcx, rbp; struct ProxyContainer *
0x140029559  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x14002955e  cmp     ebx, 80041002h
0x140029564  jz      short loc_1400295BF
0x140029566  test    ebx, ebx
0x140029568  js      short loc_1400295CB
0x14002956a  mov     rsi, [rsp+58h+arg_0]
0x14002956f  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x140029574  mov     r8d, eax; unsigned int
0x140029577  mov     rcx, rsi; struct IUnknown *
0x14002957a  call    ?SetCloaking@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@KK@Z; ProviderSubSystem_Common_Globals::SetCloaking(IUnknown *,ulong,ulong)
0x14002957f  mov     ebx, eax
0x140029581  test    eax, eax
0x140029583  js      short loc_140029599
0x140029585  mov     rax, [rsi]
0x140029588  mov     rdx, r14
0x14002958b  mov     rcx, rsi
0x14002958e  mov     rax, [rax+20h]
0x140029592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029597  mov     ebx, eax
0x140029599  mov     r8, [rsp+58h+arg_0]; struct IUnknown *
0x14002959e  mov     r9d, edi; int
0x1400295a1  xor     edx, edx; unsigned int
0x1400295a3  mov     rcx, rbp; struct ProxyContainer *
0x1400295a6  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x1400295ab  test    ebx, ebx
0x1400295ad  js      short loc_1400295CB
0x1400295af  jmp     short loc_1400295DC
0x1400295b1  cmp     eax, 80041002h
0x1400295b6  jz      short loc_1400295BF
0x1400295b8  mov     ebx, 8004100Ah
0x1400295bd  jmp     short loc_1400295CB
0x1400295bf  mov     ebx, 8004101Dh
0x1400295c4  jmp     short loc_1400295CB
0x1400295c6  mov     ebx, 80041024h
0x1400295cb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400295d1  mov     rcx, rax
0x1400295d4  mov     edx, ebx
0x1400295d6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400295dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400295e3  lea     rax, WPP_GLOBAL_Control
0x1400295ea  cmp     rcx, rax
0x1400295ed  jz      short loc_140029613
0x1400295ef  test    byte ptr [rcx+1Ch], 4
0x1400295f3  jz      short loc_140029613
0x1400295f5  cmp     byte ptr [rcx+19h], 2
0x1400295f9  jb      short loc_140029613
0x1400295fb  mov     rcx, [rcx+10h]
0x1400295ff  lea     r8, WPP_d3ea76c96a8339db06b7a6ae92e79012_Traceguids
0x140029606  mov     edx, 15h
0x14002960b  mov     r9d, ebx
0x14002960e  call    WPP_SF_d
0x140029613  mov     rbp, [rsp+58h+arg_10]
0x140029618  mov     eax, ebx
0x14002961a  mov     rbx, [rsp+58h+arg_8]
0x14002961f  add     rsp, 40h
0x140029623  pop     r14
0x140029625  pop     rdi
0x140029626  pop     rsi
0x140029627  retn
```
