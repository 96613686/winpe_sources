# CServerObject_StaThread::ExecMethodAsync(ushort * const,ushort * const,long,IWbemContext *,IWbemClassObject *,IWbemObjectSink *)

- ea: `0x140027570`
- end: `0x14002773c`
- name: `?ExecMethodAsync@CServerObject_StaThread@@UEAAJQEAG0JPEAUIWbemContext@@PEAUIWbemClassObject@@PEAUIWbemObjectSink@@@Z`
- size: `460`
- prototype: `__int64 __fastcall(CServerObject_StaThread *__hidden this, unsigned __int16 *const, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemClassObject *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400053dc`
- `0x1400054a0`
- `0x1400055e4`
- `0x1400058dc`
- `0x1400234b8`
- `0x140027570`
- `0x14004612c`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1400275de`
- `wbemcomn!GetMemLogObject` at `0x1400275de`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400275e9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400275e9`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1400275f4`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1400275f4`

## pseudocode

```c
__int64 __fastcall CServerObject_StaThread::ExecMethodAsync(
        CServerObject_StaThread *this,
        unsigned __int16 *const a2,
        unsigned __int16 *const a3,
        unsigned int a4,
        struct IWbemContext *a5,
        struct IWbemClassObject *a6,
        struct IWbemObjectSink *a7)
{
  struct IUnknown *v9; // r9
  struct ProxyContainer *v12; // rsi
  int Proxy; // eax
  HRESULT v14; // ebx
  CMemoryLog *MemLogObject; // rax
  unsigned __int16 *v16; // rdx
  unsigned __int16 *v17; // r8
  unsigned __int16 *v18; // r9
  int v19; // edi
  struct IUnknown *v20; // r14
  unsigned int CurrentImpersonationLevel; // eax
  unsigned int v22; // edx
  __int64 v23; // r9
  unsigned int v25; // [rsp+20h] [rbp-68h]
  unsigned int v26; // [rsp+28h] [rbp-60h]
  unsigned int v27; // [rsp+30h] [rbp-58h]
  struct IUnknown *v28; // [rsp+90h] [rbp+8h] BYREF

  v9 = (struct IUnknown *)*((_QWORD *)this + 61);
  if ( !v9 )
  {
    v14 = -2147217372;
    goto LABEL_6;
  }
  v12 = (CServerObject_StaThread *)((char *)this + 560);
  v28 = 0;
  Proxy = ProviderSubSystem_Common_Globals::GetProxy(
            (CServerObject_StaThread *)((char *)this + 560),
            0,
            &IID_IWbemServices,
            v9,
            &v28);
  if ( Proxy < 0 )
  {
    if ( Proxy != -2147217406 )
    {
      v14 = -2147217398;
      goto LABEL_6;
    }
    goto LABEL_4;
  }
  v14 = CoImpersonateClient();
  if ( v14 < 0 )
  {
    v19 = 0;
    v14 = -2147217405;
LABEL_13:
    ProviderSubSystem_Common_Globals::RevertProxyState(v12, 0, v28, v19);
    goto LABEL_14;
  }
  v19 = 1;
  if ( (unsigned int)ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel() - 3 > 1 )
    v14 = SetInterfaceSecurity(v28, v16, v17, v18, v25, v26, v27);
  if ( v14 < 0 )
    goto LABEL_13;
LABEL_14:
  if ( v14 == -2147217406 )
  {
LABEL_4:
    v14 = -2147217379;
LABEL_6:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v14);
    goto LABEL_21;
  }
  if ( v14 < 0 )
    goto LABEL_6;
  v20 = v28;
  CurrentImpersonationLevel = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
  v14 = ProviderSubSystem_Common_Globals::SetCloaking(v20, v22, CurrentImpersonationLevel);
  if ( v14 >= 0 )
  {
    v23 = a4;
    LODWORD(v23) = a4 & 0xFFFDFFFF;
    if ( *((_DWORD *)this + 138) >= 3u )
      v23 = a4;
    v14 = ((__int64 (__fastcall *)(struct IUnknown *, unsigned __int16 *const, unsigned __int16 *const, __int64, struct IWbemContext *, struct IWbemClassObject *, struct IWbemObjectSink *))v20->lpVtbl[8].AddRef)(
            v20,
            a2,
            a3,
            v23,
            a5,
            a6,
            a7);
  }
  ProviderSubSystem_Common_Globals::RevertProxyState(v12, 0, v28, v19);
  if ( v14 < 0 )
    goto LABEL_6;
LABEL_21:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      42,
      WPP_d3ea76c96a8339db06b7a6ae92e79012_Traceguids,
      (unsigned int)v14);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140027570  mov     r11, rsp
0x140027573  push    rbx
0x140027574  push    rbp
0x140027575  push    rsi
0x140027576  push    rdi
0x140027577  push    r12
0x140027579  push    r13
0x14002757b  push    r14
0x14002757d  push    r15
0x14002757f  sub     rsp, 48h
0x140027583  mov     r15d, r9d
0x140027586  mov     r12, r8
0x140027589  mov     r9, [rcx+1E8h]; struct IUnknown *
0x140027590  mov     r13, rdx
0x140027593  mov     rbp, rcx
0x140027596  test    r9, r9
0x140027599  jz      short loc_1400275D9
0x14002759b  lea     rsi, [rcx+230h]
0x1400275a2  mov     qword ptr [r11+8], 0
0x1400275aa  lea     rax, [r11+8]
0x1400275ae  mov     rcx, rsi; struct ProxyContainer *
0x1400275b1  lea     r8, IID_IWbemServices; struct _GUID *
0x1400275b8  mov     [r11-68h], rax
0x1400275bc  xor     edx, edx; unsigned int
0x1400275be  call    ?GetProxy@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KAEBU_GUID@@PEAUIUnknown@@AEAPEAU4@@Z; ProviderSubSystem_Common_Globals::GetProxy(ProxyContainer &,ulong,_GUID const &,IUnknown *,IUnknown * &)
0x1400275c3  test    eax, eax
0x1400275c5  jns     short loc_1400275F4
0x1400275c7  cmp     eax, 80041002h
0x1400275cc  jnz     loc_14002771E
0x1400275d2  mov     ebx, 8004101Dh
0x1400275d7  jmp     short loc_1400275DE
0x1400275d9  mov     ebx, 80041024h
0x1400275de  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400275e4  mov     rcx, rax
0x1400275e7  mov     edx, ebx
0x1400275e9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400275ef  jmp     loc_1400276D2
0x1400275f4  call    cs:__imp_CoImpersonateClient
0x1400275fa  mov     ebx, eax
0x1400275fc  test    eax, eax
0x1400275fe  js      short loc_14002761B
0x140027600  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x140027605  add     eax, 0FFFFFFFDh
0x140027608  mov     edi, 1
0x14002760d  cmp     eax, edi
0x14002760f  ja      loc_140027728
0x140027615  test    ebx, ebx
0x140027617  js      short loc_140027622
0x140027619  jmp     short loc_140027637
0x14002761b  xor     edi, edi
0x14002761d  mov     ebx, 80041003h
0x140027622  mov     r8, [rsp+88h+arg_0]; struct IUnknown *
0x14002762a  mov     r9d, edi; int
0x14002762d  xor     edx, edx; unsigned int
0x14002762f  mov     rcx, rsi; struct ProxyContainer *
0x140027632  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x140027637  cmp     ebx, 80041002h
0x14002763d  jz      short loc_1400275D2
0x14002763f  test    ebx, ebx
0x140027641  js      short loc_1400275DE
0x140027643  mov     r14, [rsp+88h+arg_0]
0x14002764b  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x140027650  mov     r8d, eax; unsigned int
0x140027653  mov     rcx, r14; struct IUnknown *
0x140027656  call    ?SetCloaking@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@KK@Z; ProviderSubSystem_Common_Globals::SetCloaking(IUnknown *,ulong,ulong)
0x14002765b  mov     ebx, eax
0x14002765d  test    eax, eax
0x14002765f  js      short loc_1400276B5
0x140027661  mov     rdx, [rsp+88h+arg_30]
0x140027669  mov     r9d, r15d
0x14002766c  mov     rax, [r14]
0x14002766f  btr     r9d, 11h
0x140027674  cmp     dword ptr [rbp+228h], 3
0x14002767b  mov     r8, r12
0x14002767e  mov     qword ptr [rsp+88h+var_58], rdx
0x140027683  mov     rcx, r14
0x140027686  mov     rdx, [rsp+88h+arg_28]
0x14002768e  cmovnb  r9d, r15d
0x140027692  mov     rax, [rax+0C8h]
0x140027699  mov     [rsp+88h+var_60], rdx
0x14002769e  mov     rdx, [rsp+88h+arg_20]
0x1400276a6  mov     [rsp+88h+var_68], rdx
0x1400276ab  mov     rdx, r13
0x1400276ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400276b3  mov     ebx, eax
0x1400276b5  mov     r8, [rsp+88h+arg_0]; struct IUnknown *
0x1400276bd  mov     r9d, edi; int
0x1400276c0  xor     edx, edx; unsigned int
0x1400276c2  mov     rcx, rsi; struct ProxyContainer *
0x1400276c5  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x1400276ca  test    ebx, ebx
0x1400276cc  js      loc_1400275DE
0x1400276d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400276d9  lea     rax, WPP_GLOBAL_Control
0x1400276e0  cmp     rcx, rax
0x1400276e3  jnz     short loc_1400276F8
0x1400276e5  mov     eax, ebx
0x1400276e7  add     rsp, 48h
0x1400276eb  pop     r15
0x1400276ed  pop     r14
0x1400276ef  pop     r13
0x1400276f1  pop     r12
0x1400276f3  pop     rdi
0x1400276f4  pop     rsi
0x1400276f5  pop     rbp
0x1400276f6  pop     rbx
0x1400276f7  retn
0x1400276f8  test    byte ptr [rcx+1Ch], 4
0x1400276fc  jz      short loc_1400276E5
0x1400276fe  cmp     byte ptr [rcx+19h], 2
0x140027702  jb      short loc_1400276E5
0x140027704  mov     rcx, [rcx+10h]
0x140027708  lea     r8, WPP_d3ea76c96a8339db06b7a6ae92e79012_Traceguids
0x14002770f  mov     edx, 2Ah ; '*'
0x140027714  mov     r9d, ebx
0x140027717  call    WPP_SF_d
0x14002771c  jmp     short loc_1400276E5
0x14002771e  mov     ebx, 8004100Ah
0x140027723  jmp     loc_1400275DE
0x140027728  mov     rcx, [rsp+88h+arg_0]; struct IUnknown *
0x140027730  call    ?SetInterfaceSecurity@@YAJPEAUIUnknown@@PEAG11KKK@Z; SetInterfaceSecurity(IUnknown *,ushort *,ushort *,ushort *,ulong,ulong,ulong)
0x140027735  mov     ebx, eax
0x140027737  jmp     loc_140027615
```
