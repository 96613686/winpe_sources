# CInterceptor_IWbemSyncProvider::Begin_Interface(IUnknown *,_GUID const &,ulong,int &,IUnknown * &,IServerSecurity * &,int &,IUnknown * &,int &,IUnknown * &)

- ea: `0x14001bdb4`
- end: `0x14001c037`
- name: `?Begin_Interface@CInterceptor_IWbemSyncProvider@@AEAAJPEAUIUnknown@@AEBU_GUID@@KAEAHAEAPEAU2@AEAPEAUIServerSecurity@@2323@Z`
- size: `643`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *this, struct IUnknown *, struct _GUID *, unsigned int, int *, struct IUnknown **, struct IServerSecurity **, int *, struct IUnknown **, int *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001ba40`

## callees

- `0x1400053dc`
- `0x1400054a0`
- `0x140005544`
- `0x1400058dc`
- `0x140006c64`
- `0x14001bdb4`
- `0x14001ca74`
- `0x1400234b8`
- `0x140041b08`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14001be94`
- `wbemcomn!GetMemLogObject` at `0x14001be94`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001be9f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001be9f`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x14001bef3`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x14001bef3`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14001befd`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14001befd`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14001bf10`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14001bf10`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInterceptor_IWbemSyncProvider::Begin_Interface(
        CInterceptor_IWbemSyncProvider *this,
        struct IUnknown *a2,
        struct _GUID *a3,
        unsigned int a4,
        int *a5,
        struct IUnknown **a6,
        struct IServerSecurity **a7,
        int *a8,
        struct IUnknown **a9,
        int *a10,
        struct IUnknown **a11)
{
  int *v11; // r15
  struct IUnknown **v13; // r14
  int *v14; // rbp
  struct IUnknown **v15; // r12
  struct IServerSecurity **v16; // r13
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  unsigned int CurrentImpersonationLevel; // edi
  int v22; // ecx
  HRESULT v23; // ebx
  CMemoryLog *MemLogObject; // rax
  struct ProxyContainer *v26; // rcx
  HRESULT v27; // eax
  struct IUnknown **v28; // rbx
  unsigned int v29; // eax
  unsigned int v30; // edx
  void *ppInterface; // [rsp+80h] [rbp+18h] BYREF
  unsigned int v33; // [rsp+88h] [rbp+20h] BYREF

  v33 = a4;
  ppInterface = a3;
  v11 = a10;
  v13 = a11;
  v14 = a5;
  v15 = a6;
  v16 = a7;
  *a10 = 0;
  *v13 = 0;
  *v14 = 0;
  *v15 = 0;
  *v16 = 0;
  v17 = *(_DWORD *)(*((_QWORD *)this + 75) + 1680LL) - 1;
  if ( !v17
    || (v18 = v17 - 4) == 0
    || (v19 = v18 - 2) == 0
    || (v20 = v19 - 1) == 0
    || (CurrentImpersonationLevel = 3, (v22 = v20 - 3) == 0)
    || (unsigned int)(v22 - 1) < 2 )
  {
    v23 = 0;
    *a9 = a2;
    *a8 = 0;
    goto LABEL_7;
  }
  v33 = 0;
  v23 = ProviderSubSystem_Common_Globals::BeginImpersonation(v15, v16, v14, &v33);
  if ( v23 < 0 )
    goto LABEL_10;
  ppInterface = 0;
  if ( CoGetCallContext(&IID_IUnknown, &ppInterface) < 0 )
    goto LABEL_19;
  v23 = CoImpersonateClient();
  if ( v23 >= 0 )
  {
    CurrentImpersonationLevel = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
    CoRevertToSelf();
  }
  (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 16LL))(ppInterface);
  if ( v23 >= 0 )
  {
LABEL_19:
    v26 = (CInterceptor_IWbemSyncProvider *)((char *)this + 440);
    if ( CurrentImpersonationLevel == 2 )
      v27 = ProviderSubSystem_Common_Globals::SetProxyState_NoImpersonation(
              v26,
              5u,
              &IID_IWbemEventProviderSecurity,
              a2,
              v13,
              v11);
    else
      v27 = ProviderSubSystem_Common_Globals::SetProxyState(v26, 5u, &IID_IWbemEventProviderSecurity, a2, v13, v11);
    v23 = v27;
  }
  if ( v23 != -2147217406 )
  {
    if ( v23 < 0 )
    {
LABEL_28:
      ProviderSubSystem_Common_Globals::EndImpersonation(*v15, *v16, *v14);
LABEL_12:
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v23);
      goto LABEL_7;
    }
    v28 = a9;
    *a8 = 1;
    *v28 = *v13;
    v29 = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
    v23 = ProviderSubSystem_Common_Globals::SetCloaking(*v28, v30, v29);
    if ( v23 < 0 )
    {
      ProviderSubSystem_Common_Globals::RevertProxyState(
        (CInterceptor_IWbemSyncProvider *)((char *)this + 440),
        5u,
        *v13,
        *v11);
      if ( v23 != -2147217406 )
        goto LABEL_28;
      return 2147749890LL;
    }
LABEL_10:
    if ( v23 != -2147217406 )
    {
      if ( v23 >= 0 )
        goto LABEL_7;
      goto LABEL_12;
    }
    return 2147749890LL;
  }
  v23 = 0;
  *a9 = a2;
  *a8 = 0;
LABEL_7:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      72,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (unsigned int)v23);
  }
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x14001bdb4  mov     rax, rsp
0x14001bdb7  mov     [rax+10h], rbx
0x14001bdbb  mov     [rax+20h], r9d
0x14001bdbf  mov     [rax+18h], r8
0x14001bdc3  mov     [rax+8], rcx
0x14001bdc7  push    rbp
0x14001bdc8  push    rsi
0x14001bdc9  push    rdi
0x14001bdca  push    r12
0x14001bdcc  push    r13
0x14001bdce  push    r14
0x14001bdd0  push    r15
0x14001bdd2  sub     rsp, 30h
0x14001bdd6  mov     r15, [rsp+68h+arg_48]
0x14001bdde  mov     rsi, rdx
0x14001bde1  mov     r14, [rsp+68h+arg_50]
0x14001bde9  xor     edx, edx
0x14001bdeb  mov     rbp, [rsp+68h+arg_20]
0x14001bdf3  mov     r12, [rsp+68h+arg_28]
0x14001bdfb  mov     r13, [rsp+68h+arg_30]
0x14001be03  mov     [r15], edx
0x14001be06  mov     [r14], rdx
0x14001be09  mov     [rbp+0], edx
0x14001be0c  mov     [r12], rdx
0x14001be10  mov     [r13+0], rdx
0x14001be14  mov     r8, [rcx+258h]
0x14001be1b  mov     ecx, [r8+690h]
0x14001be22  sub     ecx, 1
0x14001be25  jz      short loc_14001BE3D
0x14001be27  sub     ecx, 4
0x14001be2a  jz      short loc_14001BE3D
0x14001be2c  sub     ecx, 2
0x14001be2f  jz      short loc_14001BE3D
0x14001be31  sub     ecx, 1
0x14001be34  jz      short loc_14001BE3D
0x14001be36  lea     edi, [rdx+3]
0x14001be39  sub     ecx, edi
0x14001be3b  jnz     short loc_14001BEA7
0x14001be3d  mov     rax, [rsp+68h+arg_40]
0x14001be45  mov     ebx, edx
0x14001be47  mov     [rax], rsi
0x14001be4a  mov     rax, [rsp+68h+arg_38]
0x14001be52  mov     [rax], edx
0x14001be54  mov     rcx, cs:WPP_GLOBAL_Control
0x14001be5b  lea     rax, WPP_GLOBAL_Control
0x14001be62  cmp     rcx, rax
0x14001be65  jz      short loc_14001BE71
0x14001be67  test    byte ptr [rcx+1Ch], 4
0x14001be6b  jnz     loc_14001C010
0x14001be71  mov     eax, ebx
0x14001be73  mov     rbx, [rsp+68h+arg_8]
0x14001be78  add     rsp, 30h
0x14001be7c  pop     r15
0x14001be7e  pop     r14
0x14001be80  pop     r13
0x14001be82  pop     r12
0x14001be84  pop     rdi
0x14001be85  pop     rsi
0x14001be86  pop     rbp
0x14001be87  retn
0x14001be88  cmp     ebx, edi
0x14001be8a  jz      loc_14001C009
0x14001be90  test    ebx, ebx
0x14001be92  jns     short loc_14001BE54
0x14001be94  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14001be9a  mov     rcx, rax
0x14001be9d  mov     edx, ebx
0x14001be9f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14001bea5  jmp     short loc_14001BE54
0x14001bea7  sub     ecx, 1
0x14001beaa  jz      short loc_14001BE3D
0x14001beac  cmp     ecx, 1
0x14001beaf  jz      short loc_14001BE3D
0x14001beb1  mov     [rsp+68h+arg_18], edx
0x14001beb8  lea     r9, [rsp+68h+arg_18]; unsigned int *
0x14001bec0  mov     rdx, r13; struct IServerSecurity **
0x14001bec3  mov     r8, rbp; int *
0x14001bec6  mov     rcx, r12; ppInterface
0x14001bec9  call    ?BeginImpersonation@ProviderSubSystem_Common_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAHPEAK@Z; ProviderSubSystem_Common_Globals::BeginImpersonation(IUnknown * &,IServerSecurity * &,int &,ulong *)
0x14001bece  mov     ebx, eax
0x14001bed0  test    eax, eax
0x14001bed2  js      loc_14001BFFF
0x14001bed8  lea     rdx, [rsp+68h+ppInterface]; ppInterface
0x14001bee0  mov     [rsp+68h+ppInterface], 0
0x14001beec  lea     rcx, IID_IUnknown; riid
0x14001bef3  call    cs:__imp_CoGetCallContext
0x14001bef9  test    eax, eax
0x14001befb  js      short loc_14001BF2E
0x14001befd  call    cs:__imp_CoImpersonateClient
0x14001bf03  mov     ebx, eax
0x14001bf05  test    eax, eax
0x14001bf07  js      short loc_14001BF16
0x14001bf09  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x14001bf0e  mov     edi, eax
0x14001bf10  call    cs:__imp_CoRevertToSelf
0x14001bf16  mov     rcx, [rsp+68h+ppInterface]
0x14001bf1e  mov     rdx, [rcx]
0x14001bf21  mov     rax, [rdx+10h]
0x14001bf25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bf2a  test    ebx, ebx
0x14001bf2c  js      short loc_14001BF66
0x14001bf2e  mov     rcx, [rsp+68h+arg_0]
0x14001bf33  lea     r8, IID_IWbemEventProviderSecurity; struct _GUID *
0x14001bf3a  add     rcx, 1B8h; struct ProxyContainer *
0x14001bf41  mov     [rsp+68h+var_40], r15; int *
0x14001bf46  mov     [rsp+68h+var_48], r14; struct IUnknown **
0x14001bf4b  mov     r9, rsi; struct IUnknown *
0x14001bf4e  mov     edx, 5; unsigned int
0x14001bf53  cmp     edi, 2
0x14001bf56  jnz     short loc_14001BF5F
0x14001bf58  call    ?SetProxyState_NoImpersonation@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KAEBU_GUID@@PEAUIUnknown@@AEAPEAU4@AEAH@Z; ProviderSubSystem_Common_Globals::SetProxyState_NoImpersonation(ProxyContainer &,ulong,_GUID const &,IUnknown *,IUnknown * &,int &)
0x14001bf5d  jmp     short loc_14001BF64
0x14001bf5f  call    ?SetProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KAEBU_GUID@@PEAUIUnknown@@AEAPEAU4@AEAH@Z; ProviderSubSystem_Common_Globals::SetProxyState(ProxyContainer &,ulong,_GUID const &,IUnknown *,IUnknown * &,int &)
0x14001bf64  mov     ebx, eax
0x14001bf66  mov     edi, 80041002h
0x14001bf6b  cmp     ebx, edi
0x14001bf6d  jnz     short loc_14001BF8F
0x14001bf6f  mov     rax, [rsp+68h+arg_40]
0x14001bf77  xor     ebx, ebx
0x14001bf79  mov     [rax], rsi
0x14001bf7c  mov     rax, [rsp+68h+arg_38]
0x14001bf84  mov     dword ptr [rax], 0
0x14001bf8a  jmp     loc_14001BE54
0x14001bf8f  test    ebx, ebx
0x14001bf91  js      short loc_14001BFE9
0x14001bf93  mov     rax, [rsp+68h+arg_38]
0x14001bf9b  mov     rbx, [rsp+68h+arg_40]
0x14001bfa3  mov     dword ptr [rax], 1
0x14001bfa9  mov     rax, [r14]
0x14001bfac  mov     [rbx], rax
0x14001bfaf  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x14001bfb4  mov     rcx, [rbx]; struct IUnknown *
0x14001bfb7  mov     r8d, eax; unsigned int
0x14001bfba  call    ?SetCloaking@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@KK@Z; ProviderSubSystem_Common_Globals::SetCloaking(IUnknown *,ulong,ulong)
0x14001bfbf  mov     ebx, eax
0x14001bfc1  test    eax, eax
0x14001bfc3  jns     loc_14001BE88
0x14001bfc9  mov     rcx, [rsp+68h+arg_0]
0x14001bfce  mov     edx, 5; unsigned int
0x14001bfd3  mov     r9d, [r15]; int
0x14001bfd6  add     rcx, 1B8h; struct ProxyContainer *
0x14001bfdd  mov     r8, [r14]; struct IUnknown *
0x14001bfe0  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x14001bfe5  cmp     ebx, edi
0x14001bfe7  jz      short loc_14001C009
0x14001bfe9  mov     r8d, [rbp+0]; int
0x14001bfed  mov     rdx, [r13+0]; struct IServerSecurity *
0x14001bff1  mov     rcx, [r12]; struct IUnknown *
0x14001bff5  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x14001bffa  jmp     loc_14001BE94
0x14001bfff  mov     edi, 80041002h
0x14001c004  jmp     loc_14001BE88
0x14001c009  mov     eax, edi
0x14001c00b  jmp     loc_14001BE73
0x14001c010  cmp     byte ptr [rcx+19h], 2
0x14001c014  jb      loc_14001BE71
0x14001c01a  mov     rcx, [rcx+10h]
0x14001c01e  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14001c025  mov     edx, 48h ; 'H'
0x14001c02a  mov     r9d, ebx
0x14001c02d  call    WPP_SF_d
0x14001c032  jmp     loc_14001BE71
```
