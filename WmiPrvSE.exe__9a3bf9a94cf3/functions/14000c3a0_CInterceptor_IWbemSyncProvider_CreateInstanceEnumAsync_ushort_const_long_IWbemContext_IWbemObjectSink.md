# CInterceptor_IWbemSyncProvider::CreateInstanceEnumAsync(ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x14000c3a0`
- end: `0x14000c840`
- name: `?CreateInstanceEnumAsync@CInterceptor_IWbemSyncProvider@@UEAAJQEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `1184`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *__hidden this, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400053dc`
- `0x1400054a0`
- `0x140005544`
- `0x1400058dc`
- `0x140006c64`
- `0x14000c3a0`
- `0x14000c850`
- `0x14000d090`
- `0x14000d2c4`
- `0x14001ca74`
- `0x1400234b8`
- `0x140028cfc`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14000c552`
- `wbemcomn!GetMemLogObject` at `0x14000c5ae`
- `wbemcomn!GetMemLogObject` at `0x14000c706`
- `wbemcomn!GetMemLogObject` at `0x14000c552`
- `wbemcomn!GetMemLogObject` at `0x14000c5ae`
- `wbemcomn!GetMemLogObject` at `0x14000c706`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000c55d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000c5b9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000c711`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000c55d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000c5b9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000c711`
- `wbemcomn!?_Free@CMUILocale@@SAHPEAX@Z` at `0x14000c4f0`
- `wbemcomn!?_Free@CMUILocale@@SAHPEAX@Z` at `0x14000c4f0`
- `wbemcomn!?SetPreferredLanguages@CMUILocale@@SAJKPEBGPEAK@Z` at `0x14000c4e2`
- `wbemcomn!?SetPreferredLanguages@CMUILocale@@SAJKPEBGPEAK@Z` at `0x14000c4e2`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000c66e`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000c66e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000c4a2`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000c4a2`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::CreateInstanceEnumAsync(
        CInterceptor_IWbemSyncProvider *this,
        unsigned __int16 *const a2,
        int a3,
        struct IWbemContext *a4,
        struct IWbemObjectSink *a5)
{
  struct IWbemObjectSink *v9; // r13
  int InstanceEnumAsync; // ebx
  struct IUnknown *v11; // rsi
  __int64 v12; // rax
  int v13; // ecx
  int v14; // ebx
  struct IUnknown *v15; // rsi
  struct IServerSecurity *v16; // r14
  struct IUnknown *v17; // r15
  int v18; // r9d
  struct IWbemHiPerfProvider *v20; // rdx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v22; // rax
  HRESULT v23; // eax
  int v24; // eax
  unsigned int CurrentImpersonationLevel; // eax
  unsigned int v26; // edx
  CMemoryLog *v27; // rax
  int v28; // [rsp+40h] [rbp-38h]
  int v29; // [rsp+44h] [rbp-34h] BYREF
  int v30; // [rsp+48h] [rbp-30h] BYREF
  struct IUnknown *v31; // [rsp+50h] [rbp-28h] BYREF
  struct IServerSecurity *v32; // [rsp+58h] [rbp-20h] BYREF
  struct IUnknown *ppInterface; // [rsp+60h] [rbp-18h] BYREF
  void *v34; // [rsp+68h] [rbp-10h] BYREF
  int v35; // [rsp+C0h] [rbp+48h] BYREF

  v9 = a5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Sdqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      114,
      (unsigned int)WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (_DWORD)a2,
      a3,
      (char)a4,
      (char)a5);
  }
  InstanceEnumAsync = -2147217372;
  v11 = (struct IUnknown *)*((_QWORD *)this + 41);
  if ( v11 )
  {
    v12 = *((_QWORD *)this + 75);
    if ( !*(_DWORD *)(v12 + 2032) )
    {
LABEL_23:
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, InstanceEnumAsync);
      goto LABEL_18;
    }
    v34 = 0;
    v29 = 0;
    v31 = 0;
    v30 = 0;
    ppInterface = 0;
    v32 = 0;
    v13 = *(_DWORD *)(v12 + 1680);
    if ( v13 == 11 )
    {
LABEL_6:
      InstanceEnumAsync = 0;
      v28 = 0;
LABEL_7:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          71,
          WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
          (unsigned int)InstanceEnumAsync);
      }
      if ( InstanceEnumAsync >= 0 )
      {
        v14 = CMUIPreferredLanguages::Set((CMUIPreferredLanguages *)&v34, a4);
        if ( v14 < 0 )
        {
          v27 = GetMemLogObject();
          CMemoryLog::Write(v27, v14);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              115,
              WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
              (unsigned int)v14);
          }
        }
        InstanceEnumAsync = CInterceptor_IWbemSyncProvider::Helper_CreateInstanceEnumAsync(
                              this,
                              v28,
                              a2,
                              a3,
                              a4,
                              v9,
                              (struct IWbemServices *)v11);
        v15 = v31;
        v16 = v32;
        v17 = ppInterface;
        CoRevertToSelf();
        if ( v15 )
          ProviderSubSystem_Common_Globals::RevertProxyState(
            (CInterceptor_IWbemSyncProvider *)((char *)this + 440),
            0,
            v15,
            v29);
        v18 = *(_DWORD *)(*((_QWORD *)this + 75) + 1680LL);
        if ( v18 != 11 )
        {
          switch ( v18 )
          {
            case 1:
            case 5:
            case 7:
            case 8:
            case 12:
            case 13:
              break;
            default:
              ProviderSubSystem_Common_Globals::EndImpersonation(v17, v16, v30);
              break;
          }
        }
      }
LABEL_14:
      if ( v34 )
      {
        v35 = 0;
        if ( (int)CMUILocale::SetPreferredLanguages(8u, (const unsigned __int16 *)v34, (unsigned int *)&v35) >= 0 )
          CMUILocale::_Free(v34);
      }
      goto LABEL_17;
    }
    switch ( v13 )
    {
      case 1:
      case 5:
      case 7:
      case 8:
      case 12:
      case 13:
        goto LABEL_6;
      default:
        v28 = 0;
        v11 = 0;
        v23 = ProviderSubSystem_Common_Globals::BeginImpersonation(&ppInterface, &v32, &v30, 0);
        v35 = v23;
        InstanceEnumAsync = -2147217406;
        if ( v23 < 0 )
          goto LABEL_26;
        v24 = ProviderSubSystem_Common_Globals::SetProxyState(
                (CInterceptor_IWbemSyncProvider *)((char *)this + 440),
                0,
                &IID_IWbemServices,
                *((struct IUnknown **)this + 41),
                &v31,
                &v29);
        if ( v24 == -2147217406 )
        {
          v11 = (struct IUnknown *)*((_QWORD *)this + 41);
          v28 = 0;
          InstanceEnumAsync = 0;
          goto LABEL_7;
        }
        if ( v24 < 0 )
        {
          InstanceEnumAsync = v24;
        }
        else
        {
          v11 = v31;
          CurrentImpersonationLevel = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
          v35 = ProviderSubSystem_Common_Globals::SetCloaking(v11, v26, CurrentImpersonationLevel);
          if ( v35 < 0 )
          {
            ProviderSubSystem_Common_Globals::RevertProxyState(
              (CInterceptor_IWbemSyncProvider *)((char *)this + 440),
              0,
              v31,
              v29);
            if ( v35 == -2147217406 )
              goto LABEL_14;
            v28 = 1;
            InstanceEnumAsync = v35;
          }
          else
          {
            v28 = 1;
            v23 = CoImpersonateClient();
            v35 = v23;
            if ( v23 >= 0 )
            {
LABEL_26:
              if ( v23 == -2147217406 )
                goto LABEL_14;
              InstanceEnumAsync = v35;
LABEL_28:
              if ( InstanceEnumAsync < 0 )
              {
                v22 = GetMemLogObject();
                CMemoryLog::Write(v22, InstanceEnumAsync);
              }
              goto LABEL_7;
            }
            InstanceEnumAsync = -2147217405;
            ProviderSubSystem_Common_Globals::RevertProxyState(
              (CInterceptor_IWbemSyncProvider *)((char *)this + 440),
              0,
              v31,
              v29);
          }
        }
        ProviderSubSystem_Common_Globals::EndImpersonation(ppInterface, v32, v30);
        goto LABEL_28;
    }
  }
  v20 = (struct IWbemHiPerfProvider *)*((_QWORD *)this + 43);
  if ( !v20 )
    goto LABEL_23;
  InstanceEnumAsync = CInterceptor_IWbemSyncProvider::Helper_QueryInstancesAsync(this, v20, a2, a3, a4, v9);
LABEL_17:
  if ( InstanceEnumAsync < 0 )
    goto LABEL_23;
LABEL_18:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      116,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (unsigned int)InstanceEnumAsync);
  }
  return (unsigned int)InstanceEnumAsync;
}

```

## disassembly

```asm
0x14000c3a0  push    rbp
0x14000c3a2  push    rbx
0x14000c3a3  push    rsi
0x14000c3a4  push    rdi
0x14000c3a5  push    r12
0x14000c3a7  push    r13
0x14000c3a9  push    r14
0x14000c3ab  push    r15
0x14000c3ad  mov     rbp, rsp
0x14000c3b0  sub     rsp, 78h
0x14000c3b4  mov     r14, r9
0x14000c3b7  mov     r15d, r8d
0x14000c3ba  mov     r12, rdx
0x14000c3bd  mov     rdi, rcx
0x14000c3c0  lea     rax, WPP_GLOBAL_Control
0x14000c3c7  mov     r13, [rbp+arg_20]
0x14000c3cb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c3d2  cmp     rcx, rax
0x14000c3d5  jz      short loc_14000C3E1
0x14000c3d7  test    byte ptr [rcx+1Ch], 4
0x14000c3db  jnz     loc_14000C565
0x14000c3e1  mov     ebx, 80041024h
0x14000c3e6  mov     rsi, [rdi+148h]
0x14000c3ed  test    rsi, rsi
0x14000c3f0  jz      loc_14000C52A
0x14000c3f6  mov     rax, [rdi+258h]
0x14000c3fd  cmp     dword ptr [rax+7F0h], 0
0x14000c404  jz      loc_14000C552
0x14000c40a  xor     edx, edx
0x14000c40c  mov     [rbp+var_10], rdx
0x14000c410  mov     [rbp+var_34], edx
0x14000c413  mov     [rbp+var_28], rdx
0x14000c417  mov     [rbp+var_30], edx
0x14000c41a  mov     [rbp+ppInterface], rdx
0x14000c41e  mov     [rbp+var_20], rdx
0x14000c422  mov     ecx, [rax+690h]
0x14000c428  lea     r8, __ImageBase
0x14000c42f  cmp     ecx, 0Bh
0x14000c432  jnz     loc_14000C5C4
0x14000c438  mov     ebx, edx; jumptable 000000014000C5D9 cases 1,5,7,8,12,13
0x14000c43a  mov     [rbp+var_38], edx
0x14000c43d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c444  lea     rax, WPP_GLOBAL_Control
0x14000c44b  cmp     rcx, rax
0x14000c44e  jz      short loc_14000C45A
0x14000c450  test    byte ptr [rcx+1Ch], 4
0x14000c454  jnz     loc_14000C6DF
0x14000c45a  test    ebx, ebx
0x14000c45c  js      short loc_14000C4C9; jumptable 000000014000C797 cases 1,5,7,8,12,13
0x14000c45e  mov     rdx, r14; struct IWbemContext *
0x14000c461  lea     rcx, [rbp+var_10]; this
0x14000c465  call    ?Set@CMUIPreferredLanguages@@QEAAJPEAUIWbemContext@@@Z; CMUIPreferredLanguages::Set(IWbemContext *)
0x14000c46a  mov     ebx, eax
0x14000c46c  test    eax, eax
0x14000c46e  js      loc_14000C706
0x14000c474  mov     [rsp+78h+var_48], rsi; struct IWbemServices *
0x14000c479  mov     [rsp+78h+var_50], r13; struct IWbemObjectSink *
0x14000c47e  mov     [rsp+78h+var_58], r14; struct IWbemContext *
0x14000c483  mov     r9d, r15d; int
0x14000c486  mov     r8, r12; unsigned __int16 *
0x14000c489  mov     edx, [rbp+var_38]; int
0x14000c48c  mov     rcx, rdi; this
0x14000c48f  call    ?Helper_CreateInstanceEnumAsync@CInterceptor_IWbemSyncProvider@@AEAAJHQEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAUIWbemServices@@@Z; CInterceptor_IWbemSyncProvider::Helper_CreateInstanceEnumAsync(int,ushort * const,long,IWbemContext *,IWbemObjectSink *,IWbemServices *)
0x14000c494  mov     ebx, eax
0x14000c496  mov     rsi, [rbp+var_28]
0x14000c49a  mov     r14, [rbp+var_20]
0x14000c49e  mov     r15, [rbp+ppInterface]
0x14000c4a2  call    cs:__imp_CoRevertToSelf
0x14000c4a8  test    rsi, rsi
0x14000c4ab  jnz     loc_14000C75F
0x14000c4b1  mov     rax, [rdi+258h]
0x14000c4b8  mov     r9d, [rax+690h]
0x14000c4bf  cmp     r9d, 0Bh
0x14000c4c3  jnz     loc_14000C779
0x14000c4c9  mov     rdx, [rbp+var_10]; jumptable 000000014000C797 cases 1,5,7,8,12,13
0x14000c4cd  test    rdx, rdx
0x14000c4d0  jz      short loc_14000C4F6
0x14000c4d2  mov     [rbp+arg_0], 0
0x14000c4d9  lea     r8, [rbp+arg_0]
0x14000c4dd  mov     ecx, 8
0x14000c4e2  call    cs:__imp_?SetPreferredLanguages@CMUILocale@@SAJKPEBGPEAK@Z; CMUILocale::SetPreferredLanguages(ulong,ushort const *,ulong *)
0x14000c4e8  test    eax, eax
0x14000c4ea  js      short loc_14000C4F6
0x14000c4ec  mov     rcx, [rbp+var_10]
0x14000c4f0  call    cs:__imp_?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x14000c4f6  test    ebx, ebx
0x14000c4f8  js      short loc_14000C552
0x14000c4fa  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c501  lea     rax, WPP_GLOBAL_Control
0x14000c508  cmp     rcx, rax
0x14000c50b  jz      short loc_14000C517
0x14000c50d  test    byte ptr [rcx+1Ch], 4
0x14000c511  jnz     loc_14000C7AE
0x14000c517  mov     eax, ebx
0x14000c519  add     rsp, 78h
0x14000c51d  pop     r15
0x14000c51f  pop     r14
0x14000c521  pop     r13
0x14000c523  pop     r12
0x14000c525  pop     rdi
0x14000c526  pop     rsi
0x14000c527  pop     rbx
0x14000c528  pop     rbp
0x14000c529  retn
0x14000c52a  mov     rdx, [rdi+158h]; struct IWbemHiPerfProvider *
0x14000c531  test    rdx, rdx
0x14000c534  jz      short loc_14000C552
0x14000c536  mov     [rsp+78h+var_50], r13; struct IWbemObjectSink *
0x14000c53b  mov     [rsp+78h+var_58], r14; struct IWbemContext *
0x14000c540  mov     r9d, r15d; int
0x14000c543  mov     r8, r12; unsigned __int16 *
0x14000c546  mov     rcx, rdi; this
0x14000c549  call    ?Helper_QueryInstancesAsync@CInterceptor_IWbemSyncProvider@@AEAAJPEAUIWbemHiPerfProvider@@QEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z; CInterceptor_IWbemSyncProvider::Helper_QueryInstancesAsync(IWbemHiPerfProvider *,ushort * const,long,IWbemContext *,IWbemObjectSink *)
0x14000c54e  mov     ebx, eax
0x14000c550  jmp     short loc_14000C4F6
0x14000c552  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14000c558  mov     edx, ebx
0x14000c55a  mov     rcx, rax
0x14000c55d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14000c563  jmp     short loc_14000C4FA
0x14000c565  cmp     byte ptr [rcx+19h], 5
0x14000c569  jb      loc_14000C3E1
0x14000c56f  mov     edx, 72h ; 'r'
0x14000c574  mov     [rsp+78h+var_48], r13
0x14000c579  mov     [rsp+78h+var_50], r14
0x14000c57e  mov     dword ptr [rsp+78h+var_58], r15d
0x14000c583  mov     r9, r12
0x14000c586  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14000c58d  mov     rcx, [rcx+10h]
0x14000c591  call    WPP_SF_Sdqq
0x14000c596  jmp     loc_14000C3E1
0x14000c59b  cmp     eax, ebx
0x14000c59d  jz      loc_14000C4C9; jumptable 000000014000C797 cases 1,5,7,8,12,13
0x14000c5a3  mov     ebx, [rbp+arg_0]
0x14000c5a6  test    ebx, ebx
0x14000c5a8  jns     loc_14000C43D
0x14000c5ae  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14000c5b4  mov     edx, ebx
0x14000c5b6  mov     rcx, rax
0x14000c5b9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14000c5bf  jmp     loc_14000C43D
0x14000c5c4  dec     ecx; switch 13 cases
0x14000c5c6  cmp     ecx, 0Ch
0x14000c5c9  ja      short def_14000C5D9; jumptable 000000014000C5D9 default case, cases 2-4,6,9-11
0x14000c5cb  movsxd  rax, ecx
0x14000c5ce  mov     ecx, ds:(jpt_14000C5D9 - 140000000h)[r8+rax*4]
0x14000c5d6  add     rcx, r8
0x14000c5d9  jmp     rcx; switch jump
0x14000c5db  mov     [rbp+var_38], edx; jumptable 000000014000C5D9 default case, cases 2-4,6,9-11
0x14000c5de  mov     rsi, rdx
0x14000c5e1  xor     r9d, r9d; unsigned int *
0x14000c5e4  lea     r8, [rbp+var_30]; int *
0x14000c5e8  lea     rdx, [rbp+var_20]; struct IServerSecurity **
0x14000c5ec  lea     rcx, [rbp+ppInterface]; ppInterface
0x14000c5f0  call    ?BeginImpersonation@ProviderSubSystem_Common_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAHPEAK@Z; ProviderSubSystem_Common_Globals::BeginImpersonation(IUnknown * &,IServerSecurity * &,int &,ulong *)
0x14000c5f5  mov     [rbp+arg_0], eax
0x14000c5f8  mov     ebx, 80041002h
0x14000c5fd  test    eax, eax
0x14000c5ff  js      short loc_14000C59B
0x14000c601  lea     rcx, [rbp+var_34]
0x14000c605  mov     [rsp+78h+var_50], rcx; int *
0x14000c60a  lea     rcx, [rbp+var_28]
0x14000c60e  mov     [rsp+78h+var_58], rcx; struct IUnknown **
0x14000c613  mov     r9, [rdi+148h]; struct IUnknown *
0x14000c61a  lea     r8, IID_IWbemServices; struct _GUID *
0x14000c621  xor     edx, edx; unsigned int
0x14000c623  lea     rcx, [rdi+1B8h]; struct ProxyContainer *
0x14000c62a  call    ?SetProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KAEBU_GUID@@PEAUIUnknown@@AEAPEAU4@AEAH@Z; ProviderSubSystem_Common_Globals::SetProxyState(ProxyContainer &,ulong,_GUID const &,IUnknown *,IUnknown * &,int &)
0x14000c62f  cmp     eax, ebx
0x14000c631  jnz     short loc_14000C648
0x14000c633  mov     rsi, [rdi+148h]
0x14000c63a  mov     [rbp+var_38], 0
0x14000c641  xor     ebx, ebx
0x14000c643  jmp     loc_14000C43D
0x14000c648  test    eax, eax
0x14000c64a  js      short loc_14000C6C7
0x14000c64c  mov     rsi, [rbp+var_28]
0x14000c650  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x14000c655  mov     r8d, eax; unsigned int
0x14000c658  mov     rcx, rsi; struct IUnknown *
0x14000c65b  call    ?SetCloaking@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@KK@Z; ProviderSubSystem_Common_Globals::SetCloaking(IUnknown *,ulong,ulong)
0x14000c660  mov     [rbp+arg_0], eax
0x14000c663  test    eax, eax
0x14000c665  js      short loc_14000C69C
0x14000c667  mov     [rbp+var_38], 1
0x14000c66e  call    cs:__imp_CoImpersonateClient
0x14000c674  mov     [rbp+arg_0], eax
0x14000c677  test    eax, eax
0x14000c679  jns     loc_14000C59B
0x14000c67f  mov     ebx, 80041003h
0x14000c684  mov     r9d, [rbp+var_34]; int
0x14000c688  mov     r8, [rbp+var_28]; struct IUnknown *
0x14000c68c  xor     edx, edx; unsigned int
0x14000c68e  lea     rcx, [rdi+1B8h]; struct ProxyContainer *
0x14000c695  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x14000c69a  jmp     short loc_14000C6C9
0x14000c69c  mov     r9d, [rbp+var_34]; int
0x14000c6a0  mov     r8, [rbp+var_28]; struct IUnknown *
0x14000c6a4  xor     edx, edx; unsigned int
0x14000c6a6  lea     rcx, [rdi+1B8h]; struct ProxyContainer *
0x14000c6ad  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x14000c6b2  cmp     [rbp+arg_0], ebx
0x14000c6b5  jz      loc_14000C4C9; jumptable 000000014000C797 cases 1,5,7,8,12,13
0x14000c6bb  mov     [rbp+var_38], 1
0x14000c6c2  mov     ebx, [rbp+arg_0]
0x14000c6c5  jmp     short loc_14000C6C9
0x14000c6c7  mov     ebx, eax
0x14000c6c9  mov     r8d, [rbp+var_30]; int
0x14000c6cd  mov     rdx, [rbp+var_20]; struct IServerSecurity *
0x14000c6d1  mov     rcx, [rbp+ppInterface]; struct IUnknown *
0x14000c6d5  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x14000c6da  jmp     loc_14000C5A6
0x14000c6df  cmp     byte ptr [rcx+19h], 2
0x14000c6e3  jb      loc_14000C45A
0x14000c6e9  mov     edx, 47h ; 'G'
0x14000c6ee  mov     r9d, ebx
0x14000c6f1  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14000c6f8  mov     rcx, [rcx+10h]
0x14000c6fc  call    WPP_SF_d
0x14000c701  jmp     loc_14000C45A
0x14000c706  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14000c70c  mov     edx, ebx
0x14000c70e  mov     rcx, rax
0x14000c711  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14000c717  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c71e  lea     rax, WPP_GLOBAL_Control
0x14000c725  cmp     rcx, rax
0x14000c728  jz      loc_14000C474
0x14000c72e  test    byte ptr [rcx+1Ch], 4
0x14000c732  jz      loc_14000C474
0x14000c738  cmp     byte ptr [rcx+19h], 2
0x14000c73c  jb      loc_14000C474
0x14000c742  mov     edx, 73h ; 's'
0x14000c747  mov     r9d, ebx
0x14000c74a  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14000c751  mov     rcx, [rcx+10h]
0x14000c755  call    WPP_SF_d
0x14000c75a  jmp     loc_14000C474
0x14000c75f  lea     rcx, [rdi+1B8h]; struct ProxyContainer *
0x14000c766  mov     r9d, [rbp+var_34]; int
0x14000c76a  mov     r8, rsi; struct IUnknown *
0x14000c76d  xor     edx, edx; unsigned int
0x14000c76f  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x14000c774  jmp     loc_14000C4B1
0x14000c779  dec     r9d; switch 13 cases
0x14000c77c  cmp     r9d, 0Ch
0x14000c780  ja      short def_14000C797; jumptable 000000014000C797 default case, cases 2-4,6,9-11
0x14000c782  movsxd  rax, r9d
0x14000c785  lea     rcx, __ImageBase
0x14000c78c  mov     r9d, ds:(jpt_14000C797 - 140000000h)[rcx+rax*4]
0x14000c794  add     r9, rcx
0x14000c797  jmp     r9; switch jump
0x14000c79a  mov     r8d, [rbp+var_30]; jumptable 000000014000C797 default case, cases 2-4,6,9-11
0x14000c79e  mov     rdx, r14; struct IServerSecurity *
0x14000c7a1  mov     rcx, r15; struct IUnknown *
0x14000c7a4  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x14000c7a9  jmp     loc_14000C4C9; jumptable 000000014000C797 cases 1,5,7,8,12,13
0x14000c7ae  cmp     byte ptr [rcx+19h], 2
0x14000c7b2  jb      loc_14000C517
0x14000c7b8  mov     edx, 74h ; 't'
0x14000c7bd  mov     r9d, ebx
0x14000c7c0  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14000c7c7  mov     rcx, [rcx+10h]
0x14000c7cb  call    WPP_SF_d
0x14000c7d0  jmp     loc_14000C517
```
