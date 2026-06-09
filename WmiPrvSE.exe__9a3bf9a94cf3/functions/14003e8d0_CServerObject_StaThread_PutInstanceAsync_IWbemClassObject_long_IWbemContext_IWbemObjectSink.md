# CServerObject_StaThread::PutInstanceAsync(IWbemClassObject *,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x14003e8d0`
- end: `0x14003ea1f`
- name: `?PutInstanceAsync@CServerObject_StaThread@@UEAAJPEAUIWbemClassObject@@JPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `335`
- prototype: `__int64 __fastcall(CServerObject_StaThread *__hidden this, struct IWbemClassObject *, int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400053dc`
- `0x1400054a0`
- `0x140005544`
- `0x1400058dc`
- `0x1400234b8`
- `0x14003e8d0`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14003e9bc`
- `wbemcomn!GetMemLogObject` at `0x14003e9bc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003e9c7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003e9c7`

## pseudocode

```c
__int64 __fastcall CServerObject_StaThread::PutInstanceAsync(
        CServerObject_StaThread *this,
        struct IWbemClassObject *a2,
        unsigned int a3,
        struct IWbemContext *a4,
        struct IWbemObjectSink *a5)
{
  struct IUnknown *v7; // r9
  int v10; // ebx
  struct ProxyContainer *v11; // rsi
  int v12; // eax
  struct IUnknown *v13; // r14
  unsigned int CurrentImpersonationLevel; // eax
  unsigned int v15; // edx
  __int64 v16; // r8
  CMemoryLog *MemLogObject; // rax
  struct IUnknown *v19; // [rsp+30h] [rbp-38h] BYREF
  int v20; // [rsp+70h] [rbp+8h] BYREF

  v7 = (struct IUnknown *)*((_QWORD *)this + 61);
  v10 = -2147217372;
  if ( !v7 )
    goto LABEL_10;
  v20 = 0;
  v11 = (CServerObject_StaThread *)((char *)this + 560);
  v19 = 0;
  v12 = ProviderSubSystem_Common_Globals::SetProxyState(
          (CServerObject_StaThread *)((char *)this + 560),
          0,
          &IID_IWbemServices,
          v7,
          &v19,
          &v20);
  v10 = v12;
  if ( v12 == -2147217406 )
  {
    v10 = -2147217379;
LABEL_10:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v10);
    goto LABEL_11;
  }
  if ( v12 < 0 )
    goto LABEL_10;
  v13 = v19;
  CurrentImpersonationLevel = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
  v10 = ProviderSubSystem_Common_Globals::SetCloaking(v13, v15, CurrentImpersonationLevel);
  if ( v10 >= 0 )
  {
    v16 = a3;
    LODWORD(v16) = a3 & 0xFFFDFFFF;
    if ( *((_DWORD *)this + 138) >= 3u )
      v16 = a3;
    v10 = ((__int64 (__fastcall *)(struct IUnknown *, struct IWbemClassObject *, __int64, struct IWbemContext *, struct IWbemObjectSink *))v13->lpVtbl[5].QueryInterface)(
            v13,
            a2,
            v16,
            a4,
            a5);
  }
  ProviderSubSystem_Common_Globals::RevertProxyState(v11, 0, v19, v20);
  if ( v10 < 0 )
    goto LABEL_10;
LABEL_11:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      WPP_d3ea76c96a8339db06b7a6ae92e79012_Traceguids,
      (unsigned int)v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14003e8d0  mov     r11, rsp
0x14003e8d3  mov     [r11+10h], rbx
0x14003e8d7  mov     [r11+18h], rbp
0x14003e8db  push    rsi
0x14003e8dc  push    rdi
0x14003e8dd  push    r12
0x14003e8df  push    r14
0x14003e8e1  push    r15
0x14003e8e3  sub     rsp, 40h
0x14003e8e7  mov     r15, r9
0x14003e8ea  mov     ebp, r8d
0x14003e8ed  mov     r9, [rcx+1E8h]; struct IUnknown *
0x14003e8f4  mov     r12, rdx
0x14003e8f7  mov     rdi, rcx
0x14003e8fa  mov     ebx, 80041024h
0x14003e8ff  test    r9, r9
0x14003e902  jz      loc_14003E9BC
0x14003e908  lea     rax, [r11+8]
0x14003e90c  mov     [rsp+68h+arg_0], 0
0x14003e914  mov     [r11-40h], rax
0x14003e918  lea     rsi, [rcx+230h]
0x14003e91f  lea     rax, [r11-38h]
0x14003e923  mov     qword ptr [r11-38h], 0
0x14003e92b  lea     r8, IID_IWbemServices; struct _GUID *
0x14003e932  mov     [r11-48h], rax
0x14003e936  xor     edx, edx; unsigned int
0x14003e938  mov     rcx, rsi; struct ProxyContainer *
0x14003e93b  call    ?SetProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KAEBU_GUID@@PEAUIUnknown@@AEAPEAU4@AEAH@Z; ProviderSubSystem_Common_Globals::SetProxyState(ProxyContainer &,ulong,_GUID const &,IUnknown *,IUnknown * &,int &)
0x14003e940  mov     ebx, eax
0x14003e942  cmp     eax, 80041002h
0x14003e947  jnz     short loc_14003E94E
0x14003e949  lea     ebx, [rax+1Bh]
0x14003e94c  jmp     short loc_14003E9BC
0x14003e94e  test    eax, eax
0x14003e950  js      short loc_14003E9BC
0x14003e952  mov     r14, [rsp+68h+var_38]
0x14003e957  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x14003e95c  mov     r8d, eax; unsigned int
0x14003e95f  mov     rcx, r14; struct IUnknown *
0x14003e962  call    ?SetCloaking@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@KK@Z; ProviderSubSystem_Common_Globals::SetCloaking(IUnknown *,ulong,ulong)
0x14003e967  mov     ebx, eax
0x14003e969  test    eax, eax
0x14003e96b  js      short loc_14003E9A4
0x14003e96d  mov     rax, [r14]
0x14003e970  mov     r8d, ebp
0x14003e973  mov     rdx, [rsp+68h+arg_20]
0x14003e97b  btr     r8d, 11h
0x14003e980  cmp     dword ptr [rdi+228h], 3
0x14003e987  mov     r9, r15
0x14003e98a  mov     [rsp+68h+var_48], rdx
0x14003e98f  mov     rcx, r14
0x14003e992  mov     rax, [rax+78h]
0x14003e996  cmovnb  r8d, ebp
0x14003e99a  mov     rdx, r12
0x14003e99d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e9a2  mov     ebx, eax
0x14003e9a4  mov     r9d, [rsp+68h+arg_0]; int
0x14003e9a9  xor     edx, edx; unsigned int
0x14003e9ab  mov     r8, [rsp+68h+var_38]; struct IUnknown *
0x14003e9b0  mov     rcx, rsi; struct ProxyContainer *
0x14003e9b3  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x14003e9b8  test    ebx, ebx
0x14003e9ba  jns     short loc_14003E9CD
0x14003e9bc  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003e9c2  mov     rcx, rax
0x14003e9c5  mov     edx, ebx
0x14003e9c7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14003e9cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e9d4  lea     rax, WPP_GLOBAL_Control
0x14003e9db  cmp     rcx, rax
0x14003e9de  jz      short loc_14003EA04
0x14003e9e0  test    byte ptr [rcx+1Ch], 4
0x14003e9e4  jz      short loc_14003EA04
0x14003e9e6  cmp     byte ptr [rcx+19h], 2
0x14003e9ea  jb      short loc_14003EA04
0x14003e9ec  mov     rcx, [rcx+10h]
0x14003e9f0  lea     r8, WPP_d3ea76c96a8339db06b7a6ae92e79012_Traceguids
0x14003e9f7  mov     edx, 20h ; ' '
0x14003e9fc  mov     r9d, ebx
0x14003e9ff  call    WPP_SF_d
0x14003ea04  lea     r11, [rsp+68h+var_28]
0x14003ea09  mov     eax, ebx
0x14003ea0b  mov     rbx, [r11+38h]
0x14003ea0f  mov     rbp, [r11+40h]
0x14003ea13  mov     rsp, r11
0x14003ea16  pop     r15
0x14003ea18  pop     r14
0x14003ea1a  pop     r12
0x14003ea1c  pop     rdi
0x14003ea1d  pop     rsi
0x14003ea1e  retn
```
