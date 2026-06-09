# CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemRefreshingServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemRefreshingServices * &,int &,IUnknown * &,IWbemContext *)

- ea: `0x140030f90`
- end: `0x1400310ea`
- name: `?Begin_IWbemRefreshingServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemRefreshingServices@@01PEAUIWbemContext@@@Z`
- size: `346`
- prototype: `__int64 __fastcall(struct IUnknown **this, int *, struct IUnknown **, struct IServerSecurity **, int *, struct IWbemRefreshingServices **, int *, struct IUnknown **)`
- caller_count: `6`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400307d0`
- `0x140030ac0`
- `0x140030db0`
- `0x1400341e0`
- `0x140035570`
- `0x1400358c0`

## callees

- `0x1400053dc`
- `0x1400054a0`
- `0x140005544`
- `0x1400058dc`
- `0x140006c64`
- `0x1400234b8`
- `0x140030f90`
- `0x140041478`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14003108f`
- `wbemcomn!GetMemLogObject` at `0x14003108f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003109a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003109a`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemRefreshingServices(
        struct IUnknown **this,
        int *a2,
        struct IUnknown **a3,
        struct IServerSecurity **a4,
        int *a5,
        struct IWbemRefreshingServices **a6,
        int *a7,
        struct IUnknown **a8)
{
  int v12; // ebx
  int v13; // eax
  unsigned int CurrentImpersonationLevel; // eax
  unsigned int v15; // edx
  CMemoryLog *MemLogObject; // rax

  *a2 = 0;
  *a7 = 0;
  *a8 = 0;
  *a3 = 0;
  *a4 = 0;
  v12 = ProviderSubSystem_Common_Globals::BeginCallbackImpersonation(a3, a4, a2);
  if ( v12 < 0 )
    goto LABEL_8;
  v13 = ProviderSubSystem_Common_Globals::SetProxyState(
          (struct ProxyContainer *)(this + 15),
          1u,
          &IID_IWbemRefreshingServices,
          this[13],
          a8,
          a7);
  v12 = v13;
  if ( v13 != -2147217406 )
  {
    if ( v13 >= 0 )
    {
      *a5 = 1;
      *a6 = (struct IWbemRefreshingServices *)*a8;
      CurrentImpersonationLevel = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
      v12 = ProviderSubSystem_Common_Globals::SetCloaking((struct IUnknown *)*a6, v15, CurrentImpersonationLevel);
      if ( v12 >= 0 )
        goto LABEL_9;
      ProviderSubSystem_Common_Globals::RevertProxyState((struct ProxyContainer *)(this + 15), 1u, *a8, *a7);
    }
    ProviderSubSystem_Common_Globals::EndImpersonation(*a3, *a4, *a2);
LABEL_8:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v12);
    goto LABEL_9;
  }
  v12 = 0;
  *a6 = (struct IWbemRefreshingServices *)this[13];
  *a5 = 0;
LABEL_9:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      70,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (unsigned int)v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140030f90  push    rbx
0x140030f92  push    rbp
0x140030f93  push    rsi
0x140030f94  push    rdi
0x140030f95  push    r12
0x140030f97  push    r13
0x140030f99  push    r14
0x140030f9b  push    r15
0x140030f9d  sub     rsp, 38h
0x140030fa1  mov     r12, [rsp+78h+arg_30]
0x140030fa9  xor     r13d, r13d
0x140030fac  mov     rsi, [rsp+78h+arg_38]
0x140030fb4  mov     r15, r8
0x140030fb7  mov     rbp, rdx
0x140030fba  mov     [rdx], r13d
0x140030fbd  mov     rdi, rcx
0x140030fc0  mov     r14, r9
0x140030fc3  mov     [r12], r13d
0x140030fc7  mov     rcx, r15; ppInterface
0x140030fca  mov     [rsi], r13
0x140030fcd  mov     [r8], r13
0x140030fd0  mov     r8, rdx; int *
0x140030fd3  mov     rdx, r9; struct IServerSecurity **
0x140030fd6  mov     [r9], r13
0x140030fd9  call    ?BeginCallbackImpersonation@ProviderSubSystem_Common_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAH@Z; ProviderSubSystem_Common_Globals::BeginCallbackImpersonation(IUnknown * &,IServerSecurity * &,int &)
0x140030fde  mov     ebx, eax
0x140030fe0  test    eax, eax
0x140030fe2  js      loc_14003108F
0x140030fe8  mov     r9, [rdi+68h]; struct IUnknown *
0x140030fec  lea     r13, [rdi+78h]
0x140030ff0  mov     rcx, r13; struct ProxyContainer *
0x140030ff3  mov     [rsp+78h+var_50], r12; int *
0x140030ff8  lea     r8, IID_IWbemRefreshingServices; struct _GUID *
0x140030fff  mov     [rsp+78h+var_58], rsi; struct IUnknown **
0x140031004  mov     edx, 1; unsigned int
0x140031009  call    ?SetProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KAEBU_GUID@@PEAUIUnknown@@AEAPEAU4@AEAH@Z; ProviderSubSystem_Common_Globals::SetProxyState(ProxyContainer &,ulong,_GUID const &,IUnknown *,IUnknown * &,int &)
0x14003100e  mov     ebx, eax
0x140031010  cmp     eax, 80041002h
0x140031015  jnz     short loc_140031038
0x140031017  mov     rax, [rsp+78h+arg_28]
0x14003101f  xor     ebx, ebx
0x140031021  mov     rcx, [rdi+68h]
0x140031025  mov     [rax], rcx
0x140031028  mov     rax, [rsp+78h+arg_20]
0x140031030  mov     dword ptr [rax], 0
0x140031036  jmp     short loc_1400310A0
0x140031038  test    eax, eax
0x14003103a  js      short loc_140031080
0x14003103c  mov     rax, [rsp+78h+arg_20]
0x140031044  mov     edi, 1
0x140031049  mov     rbx, [rsp+78h+arg_28]
0x140031051  mov     [rax], edi
0x140031053  mov     rax, [rsi]
0x140031056  mov     [rbx], rax
0x140031059  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x14003105e  mov     rcx, [rbx]; struct IUnknown *
0x140031061  mov     r8d, eax; unsigned int
0x140031064  call    ?SetCloaking@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@KK@Z; ProviderSubSystem_Common_Globals::SetCloaking(IUnknown *,ulong,ulong)
0x140031069  mov     ebx, eax
0x14003106b  test    eax, eax
0x14003106d  jns     short loc_1400310A0
0x14003106f  mov     r9d, [r12]; int
0x140031073  mov     edx, edi; unsigned int
0x140031075  mov     r8, [rsi]; struct IUnknown *
0x140031078  mov     rcx, r13; struct ProxyContainer *
0x14003107b  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x140031080  mov     r8d, [rbp+0]; int
0x140031084  mov     rdx, [r14]; struct IServerSecurity *
0x140031087  mov     rcx, [r15]; struct IUnknown *
0x14003108a  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x14003108f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140031095  mov     rcx, rax
0x140031098  mov     edx, ebx
0x14003109a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400310a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400310a7  lea     rax, WPP_GLOBAL_Control
0x1400310ae  cmp     rcx, rax
0x1400310b1  jz      short loc_1400310D7
0x1400310b3  test    byte ptr [rcx+1Ch], 4
0x1400310b7  jz      short loc_1400310D7
0x1400310b9  cmp     byte ptr [rcx+19h], 2
0x1400310bd  jb      short loc_1400310D7
0x1400310bf  mov     rcx, [rcx+10h]
0x1400310c3  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x1400310ca  mov     edx, 46h ; 'F'
0x1400310cf  mov     r9d, ebx
0x1400310d2  call    WPP_SF_d
0x1400310d7  mov     eax, ebx
0x1400310d9  add     rsp, 38h
0x1400310dd  pop     r15
0x1400310df  pop     r14
0x1400310e1  pop     r13
0x1400310e3  pop     r12
0x1400310e5  pop     rdi
0x1400310e6  pop     rsi
0x1400310e7  pop     rbp
0x1400310e8  pop     rbx
0x1400310e9  retn
```
