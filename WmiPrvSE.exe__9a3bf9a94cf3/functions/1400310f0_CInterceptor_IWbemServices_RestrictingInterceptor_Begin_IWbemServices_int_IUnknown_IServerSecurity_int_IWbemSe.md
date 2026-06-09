# CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemServices * &,int &,IUnknown * &,IWbemContext *)

- ea: `0x1400310f0`
- end: `0x140031240`
- name: `?Begin_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemServices@@01PEAUIWbemContext@@@Z`
- size: `336`
- prototype: `__int64 __fastcall(struct IUnknown **this, int *, struct IUnknown **, struct IServerSecurity **, int *, struct IWbemServices **, int *, struct IUnknown **)`
- caller_count: `23`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x140031340`
- `0x1400315d0`
- `0x140031890`
- `0x140031b60`
- `0x140031e20`
- `0x140032100`
- `0x1400323c0`
- `0x140032690`
- `0x140032950`
- `0x140032d20`
- `0x140033030`
- `0x140033310`
- `0x140033610`
- `0x1400337b0`
- `0x140033ab0`
- `0x140033d70`
- `0x140033f20`
- `0x1400344e0`
- `0x1400347b0`
- `0x140034a70`
- `0x140034d40`
- `0x140035000`
- `0x1400352c0`

## callees

- `0x1400053dc`
- `0x1400054a0`
- `0x140005544`
- `0x1400058dc`
- `0x140006c64`
- `0x1400234b8`
- `0x1400310f0`
- `0x140041478`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1400311e5`
- `wbemcomn!GetMemLogObject` at `0x1400311e5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400311f0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400311f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(
        struct IUnknown **this,
        int *a2,
        struct IUnknown **a3,
        struct IServerSecurity **a4,
        int *a5,
        struct IWbemServices **a6,
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
          0,
          &IID_IWbemServices,
          this[12],
          a8,
          a7);
  v12 = v13;
  if ( v13 != -2147217406 )
  {
    if ( v13 >= 0 )
    {
      *a5 = 1;
      *a6 = (struct IWbemServices *)*a8;
      CurrentImpersonationLevel = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
      v12 = ProviderSubSystem_Common_Globals::SetCloaking((struct IUnknown *)*a6, v15, CurrentImpersonationLevel);
      if ( v12 >= 0 )
        goto LABEL_9;
      ProviderSubSystem_Common_Globals::RevertProxyState((struct ProxyContainer *)(this + 15), 0, *a8, *a7);
    }
    ProviderSubSystem_Common_Globals::EndImpersonation(*a3, *a4, *a2);
LABEL_8:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v12);
    goto LABEL_9;
  }
  v12 = 0;
  *a6 = (struct IWbemServices *)this[12];
  *a5 = 0;
LABEL_9:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      69,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (unsigned int)v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1400310f0  push    rbx
0x1400310f2  push    rbp
0x1400310f3  push    rsi
0x1400310f4  push    rdi
0x1400310f5  push    r12
0x1400310f7  push    r13
0x1400310f9  push    r14
0x1400310fb  push    r15
0x1400310fd  sub     rsp, 38h
0x140031101  mov     r14, [rsp+78h+arg_30]
0x140031109  xor     r13d, r13d
0x14003110c  mov     rsi, [rsp+78h+arg_38]
0x140031114  mov     rbp, r8
0x140031117  mov     r12, rdx
0x14003111a  mov     [rdx], r13d
0x14003111d  mov     rdi, rcx
0x140031120  mov     r15, r9
0x140031123  mov     [r14], r13d
0x140031126  mov     rcx, rbp; ppInterface
0x140031129  mov     [rsi], r13
0x14003112c  mov     [r8], r13
0x14003112f  mov     r8, rdx; int *
0x140031132  mov     rdx, r9; struct IServerSecurity **
0x140031135  mov     [r9], r13
0x140031138  call    ?BeginCallbackImpersonation@ProviderSubSystem_Common_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAH@Z; ProviderSubSystem_Common_Globals::BeginCallbackImpersonation(IUnknown * &,IServerSecurity * &,int &)
0x14003113d  mov     ebx, eax
0x14003113f  test    eax, eax
0x140031141  js      loc_1400311E5
0x140031147  mov     r9, [rdi+60h]; struct IUnknown *
0x14003114b  lea     r8, IID_IWbemServices; struct _GUID *
0x140031152  mov     [rsp+78h+var_50], r14; int *
0x140031157  lea     rcx, [rdi+78h]; struct ProxyContainer *
0x14003115b  xor     edx, edx; unsigned int
0x14003115d  mov     [rsp+78h+var_58], rsi; struct IUnknown **
0x140031162  call    ?SetProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KAEBU_GUID@@PEAUIUnknown@@AEAPEAU4@AEAH@Z; ProviderSubSystem_Common_Globals::SetProxyState(ProxyContainer &,ulong,_GUID const &,IUnknown *,IUnknown * &,int &)
0x140031167  mov     ebx, eax
0x140031169  cmp     eax, 80041002h
0x14003116e  jnz     short loc_14003118E
0x140031170  mov     rax, [rsp+78h+arg_28]
0x140031178  xor     ebx, ebx
0x14003117a  mov     rcx, [rdi+60h]
0x14003117e  mov     [rax], rcx
0x140031181  mov     rax, [rsp+78h+arg_20]
0x140031189  mov     [rax], r13d
0x14003118c  jmp     short loc_1400311F6
0x14003118e  test    eax, eax
0x140031190  js      short loc_1400311D5
0x140031192  mov     rax, [rsp+78h+arg_20]
0x14003119a  mov     rbx, [rsp+78h+arg_28]
0x1400311a2  mov     dword ptr [rax], 1
0x1400311a8  mov     rax, [rsi]
0x1400311ab  mov     [rbx], rax
0x1400311ae  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x1400311b3  mov     rcx, [rbx]; struct IUnknown *
0x1400311b6  mov     r8d, eax; unsigned int
0x1400311b9  call    ?SetCloaking@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@KK@Z; ProviderSubSystem_Common_Globals::SetCloaking(IUnknown *,ulong,ulong)
0x1400311be  mov     ebx, eax
0x1400311c0  test    eax, eax
0x1400311c2  jns     short loc_1400311F6
0x1400311c4  mov     r9d, [r14]; int
0x1400311c7  lea     rcx, [rdi+78h]; struct ProxyContainer *
0x1400311cb  mov     r8, [rsi]; struct IUnknown *
0x1400311ce  xor     edx, edx; unsigned int
0x1400311d0  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x1400311d5  mov     r8d, [r12]; int
0x1400311d9  mov     rdx, [r15]; struct IServerSecurity *
0x1400311dc  mov     rcx, [rbp+0]; struct IUnknown *
0x1400311e0  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x1400311e5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400311eb  mov     rcx, rax
0x1400311ee  mov     edx, ebx
0x1400311f0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400311f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400311fd  lea     rax, WPP_GLOBAL_Control
0x140031204  cmp     rcx, rax
0x140031207  jz      short loc_14003122D
0x140031209  test    byte ptr [rcx+1Ch], 4
0x14003120d  jz      short loc_14003122D
0x14003120f  cmp     byte ptr [rcx+19h], 2
0x140031213  jb      short loc_14003122D
0x140031215  mov     rcx, [rcx+10h]
0x140031219  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140031220  mov     edx, 45h ; 'E'
0x140031225  mov     r9d, ebx
0x140031228  call    WPP_SF_d
0x14003122d  mov     eax, ebx
0x14003122f  add     rsp, 38h
0x140031233  pop     r15
0x140031235  pop     r14
0x140031237  pop     r13
0x140031239  pop     r12
0x14003123b  pop     rdi
0x14003123c  pop     rsi
0x14003123d  pop     rbp
0x14003123e  pop     rbx
0x14003123f  retn
```
