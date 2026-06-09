# CInterceptor_IWbemSyncProvider::Begin_IWbemServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemServices * &,int &,IUnknown * &)

- ea: `0x14000fa50`
- end: `0x14000fc9c`
- name: `?Begin_IWbemServices@CInterceptor_IWbemSyncProvider@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemServices@@01@Z`
- size: `588`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *this, int *, struct IUnknown **, struct IServerSecurity **, int *, struct IWbemServices **, int *, struct IUnknown **)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14000f7a0`
- `0x140028ef0`
- `0x140036f10`
- `0x14003b520`

## callees

- `0x1400053dc`
- `0x1400054a0`
- `0x140005544`
- `0x1400058dc`
- `0x140006c64`
- `0x14000fa50`
- `0x14001ca74`
- `0x1400234b8`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14000fc28`
- `wbemcomn!GetMemLogObject` at `0x14000fc28`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000fc33`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000fc33`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000fbc5`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000fbc5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInterceptor_IWbemSyncProvider::Begin_IWbemServices(
        CInterceptor_IWbemSyncProvider *this,
        int *a2,
        struct IUnknown **a3,
        struct IServerSecurity **a4,
        int *a5,
        struct IWbemServices **a6,
        int *a7,
        struct IUnknown **a8)
{
  int v12; // ecx
  HRESULT v13; // ebx
  int v15; // eax
  unsigned int CurrentImpersonationLevel; // eax
  unsigned int v17; // edx
  CMemoryLog *MemLogObject; // rax

  *a7 = 0;
  *a8 = 0;
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  v12 = *(_DWORD *)(*((_QWORD *)this + 75) + 1680LL);
  if ( v12 == 11 )
  {
LABEL_2:
    v13 = 0;
    *a6 = (struct IWbemServices *)*((_QWORD *)this + 41);
    *a5 = 0;
    goto LABEL_3;
  }
  switch ( v12 )
  {
    case 1:
    case 5:
    case 7:
    case 8:
    case 12:
    case 13:
      goto LABEL_2;
    default:
      v13 = ProviderSubSystem_Common_Globals::BeginImpersonation(a3, a4, a2, 0);
      if ( v13 < 0 )
        goto LABEL_6;
      v15 = ProviderSubSystem_Common_Globals::SetProxyState(
              (CInterceptor_IWbemSyncProvider *)((char *)this + 440),
              0,
              &IID_IWbemServices,
              *((struct IUnknown **)this + 41),
              a8,
              a7);
      v13 = v15;
      if ( v15 != -2147217406 )
      {
        if ( v15 >= 0 )
        {
          *a5 = 1;
          *a6 = (struct IWbemServices *)*a8;
          CurrentImpersonationLevel = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
          v13 = ProviderSubSystem_Common_Globals::SetCloaking((struct IUnknown *)*a6, v17, CurrentImpersonationLevel);
          if ( v13 < 0 )
          {
            ProviderSubSystem_Common_Globals::RevertProxyState(
              (CInterceptor_IWbemSyncProvider *)((char *)this + 440),
              0,
              *a8,
              *a7);
            if ( v13 != -2147217406 )
              goto LABEL_17;
          }
          else
          {
            v13 = CoImpersonateClient();
            if ( v13 < 0 )
            {
              v13 = -2147217405;
              ProviderSubSystem_Common_Globals::RevertProxyState(
                (CInterceptor_IWbemSyncProvider *)((char *)this + 440),
                0,
                *a8,
                *a7);
              goto LABEL_17;
            }
LABEL_6:
            if ( v13 != -2147217406 )
              goto LABEL_18;
          }
          return 2147749890LL;
        }
LABEL_17:
        ProviderSubSystem_Common_Globals::EndImpersonation(*a3, *a4, *a2);
LABEL_18:
        if ( v13 < 0 )
        {
          MemLogObject = GetMemLogObject();
          CMemoryLog::Write(MemLogObject, v13);
        }
        goto LABEL_3;
      }
      v13 = 0;
      *a6 = (struct IWbemServices *)*((_QWORD *)this + 41);
      *a5 = 0;
LABEL_3:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          71,
          WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
          (unsigned int)v13);
      }
      return (unsigned int)v13;
  }
}

```

## disassembly

```asm
0x14000fa50  push    rbx
0x14000fa52  push    rbp
0x14000fa53  push    rsi
0x14000fa54  push    rdi
0x14000fa55  push    r12
0x14000fa57  push    r13
0x14000fa59  push    r14
0x14000fa5b  push    r15
0x14000fa5d  sub     rsp, 38h
0x14000fa61  mov     r14, [rsp+78h+arg_30]
0x14000fa69  mov     rbp, r8
0x14000fa6c  mov     rsi, [rsp+78h+arg_38]
0x14000fa74  xor     r8d, r8d
0x14000fa77  mov     rdi, rcx
0x14000fa7a  mov     r15, r9
0x14000fa7d  mov     r12, rdx
0x14000fa80  mov     [r14], r8d
0x14000fa83  mov     [rsi], r8
0x14000fa86  mov     [rdx], r8d
0x14000fa89  mov     [rbp+0], r8
0x14000fa8d  mov     [r9], r8
0x14000fa90  mov     rax, [rcx+258h]
0x14000fa97  mov     ecx, [rax+690h]
0x14000fa9d  cmp     ecx, 0Bh
0x14000faa0  jnz     short loc_14000FB05
0x14000faa2  mov     rax, [rsp+78h+arg_28]; jumptable 000000014000FB20 cases 1,5,7,8,12,13
0x14000faaa  mov     ebx, r8d
0x14000faad  mov     rcx, [rdi+148h]
0x14000fab4  mov     [rax], rcx
0x14000fab7  mov     rax, [rsp+78h+arg_20]
0x14000fabf  mov     [rax], r8d
0x14000fac2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fac9  lea     rax, WPP_GLOBAL_Control
0x14000fad0  cmp     rcx, rax
0x14000fad3  jz      short loc_14000FADF
0x14000fad5  test    byte ptr [rcx+1Ch], 4
0x14000fad9  jnz     loc_14000FC3E
0x14000fadf  mov     eax, ebx
0x14000fae1  add     rsp, 38h
0x14000fae5  pop     r15
0x14000fae7  pop     r14
0x14000fae9  pop     r13
0x14000faeb  pop     r12
0x14000faed  pop     rdi
0x14000faee  pop     rsi
0x14000faef  pop     rbp
0x14000faf0  pop     rbx
0x14000faf1  retn
0x14000faf2  cmp     ebx, 80041002h
0x14000faf8  jnz     loc_14000FC20
0x14000fafe  mov     eax, 80041002h
0x14000fb03  jmp     short loc_14000FAE1
0x14000fb05  dec     ecx; switch 13 cases
0x14000fb07  cmp     ecx, 0Ch
0x14000fb0a  ja      short def_14000FB20; jumptable 000000014000FB20 default case, cases 2-4,6,9-11
0x14000fb0c  movsxd  rax, ecx
0x14000fb0f  lea     rdx, __ImageBase
0x14000fb16  mov     ecx, ds:(jpt_14000FB20 - 140000000h)[rdx+rax*4]
0x14000fb1d  add     rcx, rdx
0x14000fb20  jmp     rcx; switch jump
0x14000fb22  xor     r9d, r9d; jumptable 000000014000FB20 default case, cases 2-4,6,9-11
0x14000fb25  mov     r8, r12; int *
0x14000fb28  mov     rdx, r15; struct IServerSecurity **
0x14000fb2b  mov     rcx, rbp; ppInterface
0x14000fb2e  call    ?BeginImpersonation@ProviderSubSystem_Common_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAHPEAK@Z; ProviderSubSystem_Common_Globals::BeginImpersonation(IUnknown * &,IServerSecurity * &,int &,ulong *)
0x14000fb33  mov     ebx, eax
0x14000fb35  test    eax, eax
0x14000fb37  js      short loc_14000FAF2
0x14000fb39  mov     r9, [rdi+148h]; struct IUnknown *
0x14000fb40  lea     r8, IID_IWbemServices; struct _GUID *
0x14000fb47  mov     [rsp+78h+var_50], r14; int *
0x14000fb4c  lea     rcx, [rdi+1B8h]; struct ProxyContainer *
0x14000fb53  xor     edx, edx; unsigned int
0x14000fb55  mov     [rsp+78h+var_58], rsi; struct IUnknown **
0x14000fb5a  call    ?SetProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KAEBU_GUID@@PEAUIUnknown@@AEAPEAU4@AEAH@Z; ProviderSubSystem_Common_Globals::SetProxyState(ProxyContainer &,ulong,_GUID const &,IUnknown *,IUnknown * &,int &)
0x14000fb5f  mov     ebx, eax
0x14000fb61  cmp     eax, 80041002h
0x14000fb66  jnz     short loc_14000FB8F
0x14000fb68  mov     rax, [rsp+78h+arg_28]
0x14000fb70  xor     ebx, ebx
0x14000fb72  mov     rcx, [rdi+148h]
0x14000fb79  mov     [rax], rcx
0x14000fb7c  mov     rax, [rsp+78h+arg_20]
0x14000fb84  mov     dword ptr [rax], 0
0x14000fb8a  jmp     loc_14000FAC2
0x14000fb8f  test    eax, eax
0x14000fb91  js      short loc_14000FC10
0x14000fb93  mov     rax, [rsp+78h+arg_20]
0x14000fb9b  mov     rbx, [rsp+78h+arg_28]
0x14000fba3  mov     dword ptr [rax], 1
0x14000fba9  mov     rax, [rsi]
0x14000fbac  mov     [rbx], rax
0x14000fbaf  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x14000fbb4  mov     rcx, [rbx]; struct IUnknown *
0x14000fbb7  mov     r8d, eax; unsigned int
0x14000fbba  call    ?SetCloaking@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@KK@Z; ProviderSubSystem_Common_Globals::SetCloaking(IUnknown *,ulong,ulong)
0x14000fbbf  mov     ebx, eax
0x14000fbc1  test    eax, eax
0x14000fbc3  js      short loc_14000FBF0
0x14000fbc5  call    cs:__imp_CoImpersonateClient
0x14000fbcb  mov     ebx, eax
0x14000fbcd  test    eax, eax
0x14000fbcf  jns     loc_14000FAF2
0x14000fbd5  mov     r9d, [r14]; int
0x14000fbd8  lea     rcx, [rdi+1B8h]; struct ProxyContainer *
0x14000fbdf  mov     r8, [rsi]; struct IUnknown *
0x14000fbe2  xor     edx, edx; unsigned int
0x14000fbe4  mov     ebx, 80041003h
0x14000fbe9  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x14000fbee  jmp     short loc_14000FC10
0x14000fbf0  mov     r9d, [r14]; int
0x14000fbf3  lea     rcx, [rdi+1B8h]; struct ProxyContainer *
0x14000fbfa  mov     r8, [rsi]; struct IUnknown *
0x14000fbfd  xor     edx, edx; unsigned int
0x14000fbff  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x14000fc04  cmp     ebx, 80041002h
0x14000fc0a  jz      loc_14000FAFE
0x14000fc10  mov     r8d, [r12]; int
0x14000fc14  mov     rdx, [r15]; struct IServerSecurity *
0x14000fc17  mov     rcx, [rbp+0]; struct IUnknown *
0x14000fc1b  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x14000fc20  test    ebx, ebx
0x14000fc22  jns     loc_14000FAC2
0x14000fc28  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14000fc2e  mov     rcx, rax
0x14000fc31  mov     edx, ebx
0x14000fc33  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14000fc39  jmp     loc_14000FAC2
0x14000fc3e  cmp     byte ptr [rcx+19h], 2
0x14000fc42  jb      loc_14000FADF
0x14000fc48  mov     rcx, [rcx+10h]
0x14000fc4c  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14000fc53  mov     edx, 47h ; 'G'
0x14000fc58  mov     r9d, ebx
0x14000fc5b  call    WPP_SF_d
0x14000fc60  jmp     loc_14000FADF
```
