# CInterceptor_IWbemSyncProvider::CreateClassEnumAsync(ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x14000ed60`
- end: `0x14000f1b2`
- name: `?CreateClassEnumAsync@CInterceptor_IWbemSyncProvider@@UEAAJQEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `1106`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *this, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400053dc`
- `0x1400054a0`
- `0x140005544`
- `0x1400058dc`
- `0x140006c64`
- `0x14000d090`
- `0x14000ed60`
- `0x14000f1b8`
- `0x14001ca74`
- `0x1400234b8`
- `0x140028cfc`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14000edcf`
- `wbemcomn!GetMemLogObject` at `0x14000f0ae`
- `wbemcomn!GetMemLogObject` at `0x14000f0f2`
- `wbemcomn!GetMemLogObject` at `0x14000edcf`
- `wbemcomn!GetMemLogObject` at `0x14000f0ae`
- `wbemcomn!GetMemLogObject` at `0x14000f0f2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000edda`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000f0b9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000f0fd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000edda`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000f0b9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000f0fd`
- `wbemcomn!?_Free@CMUILocale@@SAHPEAX@Z` at `0x14000ef20`
- `wbemcomn!?_Free@CMUILocale@@SAHPEAX@Z` at `0x14000ef20`
- `wbemcomn!?SetPreferredLanguages@CMUILocale@@SAJKPEBGPEAK@Z` at `0x14000ef12`
- `wbemcomn!?SetPreferredLanguages@CMUILocale@@SAJKPEBGPEAK@Z` at `0x14000ef12`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000f066`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000f066`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000eeb3`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000eeb3`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::CreateClassEnumAsync(
        CInterceptor_IWbemSyncProvider *this,
        unsigned __int16 *const a2,
        int a3,
        struct IWbemContext *a4,
        struct IWbemObjectSink *a5)
{
  struct IWbemContext *v5; // rdi
  _QWORD *v7; // rcx
  HRESULT ClassEnumAsync; // ebx
  struct IUnknown *v9; // r15
  __int64 v10; // rdx
  CMemoryLog *v11; // rax
  __int64 result; // rax
  int v13; // r12d
  int v14; // r13d
  int v15; // edx
  int v16; // edx
  int v17; // edx
  int v18; // edx
  int v19; // edx
  int v20; // r14d
  int v21; // ebx
  struct IUnknown *v22; // rdi
  struct IServerSecurity *v23; // r14
  struct IUnknown *v24; // r15
  int v25; // eax
  unsigned int CurrentImpersonationLevel; // eax
  unsigned int v27; // edx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v29; // rax
  int v30; // [rsp+40h] [rbp-38h] BYREF
  struct IUnknown *v31; // [rsp+48h] [rbp-30h] BYREF
  struct IServerSecurity *v32; // [rsp+50h] [rbp-28h] BYREF
  struct IUnknown *ppInterface; // [rsp+58h] [rbp-20h] BYREF
  void *v34; // [rsp+60h] [rbp-18h] BYREF
  int v35; // [rsp+C0h] [rbp+48h] BYREF
  unsigned __int16 *v36; // [rsp+C8h] [rbp+50h]
  int v37; // [rsp+D0h] [rbp+58h]
  struct IWbemContext *v38; // [rsp+D8h] [rbp+60h]

  v38 = a4;
  v37 = a3;
  v36 = a2;
  v5 = a4;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Sdqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      99,
      (unsigned int)WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (_DWORD)a2,
      a3,
      (char)a4,
      (char)a5);
    v7 = WPP_GLOBAL_Control;
  }
  ClassEnumAsync = -2147217372;
  v9 = (struct IUnknown *)*((_QWORD *)this + 41);
  if ( !v9 )
    goto LABEL_5;
  v10 = *((_QWORD *)this + 75);
  if ( !*(_DWORD *)(v10 + 1872) )
    goto LABEL_5;
  v34 = 0;
  v13 = 0;
  v35 = 0;
  v31 = 0;
  v14 = 0;
  v30 = 0;
  ppInterface = 0;
  v32 = 0;
  v15 = *(_DWORD *)(v10 + 1680) - 1;
  if ( v15 )
  {
    v16 = v15 - 4;
    if ( v16 )
    {
      v17 = v16 - 2;
      if ( v17 )
      {
        v18 = v17 - 1;
        if ( v18 )
        {
          v19 = v18 - 3;
          if ( v19 )
          {
            if ( (unsigned int)(v19 - 1) >= 2 )
            {
              v20 = 0;
              v9 = 0;
              ClassEnumAsync = ProviderSubSystem_Common_Globals::BeginImpersonation(&ppInterface, &v32, &v30, 0);
              v14 = v30;
              if ( ClassEnumAsync >= 0 )
              {
                v25 = ProviderSubSystem_Common_Globals::SetProxyState(
                        (CInterceptor_IWbemSyncProvider *)((char *)this + 440),
                        0,
                        &IID_IWbemServices,
                        *((struct IUnknown **)this + 41),
                        &v31,
                        &v35);
                ClassEnumAsync = v25;
                v13 = v35;
                if ( v25 == -2147217406 )
                {
                  v9 = (struct IUnknown *)*((_QWORD *)this + 41);
                  ClassEnumAsync = 0;
LABEL_37:
                  v7 = WPP_GLOBAL_Control;
                  v5 = v38;
                  goto LABEL_15;
                }
                if ( v25 < 0 )
                  goto LABEL_50;
                v9 = v31;
                CurrentImpersonationLevel = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
                ClassEnumAsync = ProviderSubSystem_Common_Globals::SetCloaking(v9, v27, CurrentImpersonationLevel);
                v20 = 1;
                if ( ClassEnumAsync < 0 )
                  goto LABEL_49;
                ClassEnumAsync = CoImpersonateClient();
                if ( ClassEnumAsync < 0 )
                {
                  ClassEnumAsync = -2147217405;
LABEL_49:
                  ProviderSubSystem_Common_Globals::RevertProxyState(
                    (CInterceptor_IWbemSyncProvider *)((char *)this + 440),
                    0,
                    v31,
                    v13);
                  if ( ClassEnumAsync != -2147217406 )
                  {
LABEL_50:
                    ProviderSubSystem_Common_Globals::EndImpersonation(ppInterface, v32, v14);
LABEL_35:
                    if ( ClassEnumAsync < 0 )
                    {
                      MemLogObject = GetMemLogObject();
                      CMemoryLog::Write(MemLogObject, ClassEnumAsync);
                    }
                    goto LABEL_37;
                  }
LABEL_38:
                  ClassEnumAsync = -2147217406;
LABEL_26:
                  v7 = WPP_GLOBAL_Control;
                  goto LABEL_27;
                }
              }
              if ( ClassEnumAsync != -2147217406 )
                goto LABEL_35;
              goto LABEL_38;
            }
          }
        }
      }
    }
  }
  ClassEnumAsync = 0;
  v20 = 0;
LABEL_15:
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 && *((_BYTE *)v7 + 25) >= 2u )
  {
    WPP_SF_d(v7[2], 71, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, (unsigned int)ClassEnumAsync);
    v7 = WPP_GLOBAL_Control;
  }
  if ( ClassEnumAsync >= 0 )
  {
    v21 = CMUIPreferredLanguages::Set((CMUIPreferredLanguages *)&v34, v5);
    if ( v21 < 0 )
    {
      v29 = GetMemLogObject();
      CMemoryLog::Write(v29, v21);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          100,
          WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
          (unsigned int)v21);
      }
    }
    ClassEnumAsync = CInterceptor_IWbemSyncProvider::Helper_CreateClassEnumAsync(
                       this,
                       v20,
                       v36,
                       v37,
                       v5,
                       a5,
                       (struct IWbemServices *)v9);
    v22 = v31;
    v23 = v32;
    v24 = ppInterface;
    CoRevertToSelf();
    if ( v22 )
      ProviderSubSystem_Common_Globals::RevertProxyState(
        (CInterceptor_IWbemSyncProvider *)((char *)this + 440),
        0,
        v22,
        v13);
    if ( *(_DWORD *)(*((_QWORD *)this + 75) + 1680LL) != 1
      && *(_DWORD *)(*((_QWORD *)this + 75) + 1680LL) != 5
      && *(_DWORD *)(*((_QWORD *)this + 75) + 1680LL) != 7
      && *(_DWORD *)(*((_QWORD *)this + 75) + 1680LL) != 8
      && *(_DWORD *)(*((_QWORD *)this + 75) + 1680LL) != 11
      && (unsigned int)(*(_DWORD *)(*((_QWORD *)this + 75) + 1680LL) - 12) >= 2 )
    {
      ProviderSubSystem_Common_Globals::EndImpersonation(v24, v23, v14);
    }
    goto LABEL_26;
  }
LABEL_27:
  if ( v34 )
  {
    v35 = 0;
    if ( (int)CMUILocale::SetPreferredLanguages(8u, (const unsigned __int16 *)v34, (unsigned int *)&v35) >= 0 )
      CMUILocale::_Free(v34);
    v7 = WPP_GLOBAL_Control;
  }
  result = 2147749890LL;
  if ( ClassEnumAsync != -2147217406 )
  {
    if ( ClassEnumAsync >= 0 )
    {
LABEL_6:
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 && *((_BYTE *)v7 + 25) >= 2u )
        WPP_SF_d(v7[2], 101, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, (unsigned int)ClassEnumAsync);
      return (unsigned int)ClassEnumAsync;
    }
LABEL_5:
    v11 = GetMemLogObject();
    CMemoryLog::Write(v11, ClassEnumAsync);
    v7 = WPP_GLOBAL_Control;
    goto LABEL_6;
  }
  return result;
}

```

## disassembly

```asm
0x14000ed60  mov     [rsp-40h+arg_18], r9
0x14000ed65  mov     [rsp-40h+arg_10], r8d
0x14000ed6a  mov     [rsp-40h+arg_8], rdx
0x14000ed6f  push    rbp
0x14000ed70  push    rbx
0x14000ed71  push    rsi
0x14000ed72  push    rdi
0x14000ed73  push    r12
0x14000ed75  push    r13
0x14000ed77  push    r14
0x14000ed79  push    r15
0x14000ed7b  mov     rbp, rsp
0x14000ed7e  sub     rsp, 78h
0x14000ed82  mov     rdi, r9
0x14000ed85  mov     eax, r8d
0x14000ed88  mov     r8, rdx
0x14000ed8b  mov     rsi, rcx
0x14000ed8e  lea     rdx, WPP_GLOBAL_Control
0x14000ed95  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ed9c  cmp     rcx, rdx
0x14000ed9f  jz      short loc_14000EDAB
0x14000eda1  test    byte ptr [rcx+1Ch], 4
0x14000eda5  jnz     loc_14000EF7C
0x14000edab  mov     ebx, 80041024h
0x14000edb0  mov     r15, [rsi+148h]
0x14000edb7  xor     r8d, r8d
0x14000edba  test    r15, r15
0x14000edbd  jz      short loc_14000EDCF
0x14000edbf  mov     rdx, [rsi+258h]
0x14000edc6  cmp     [rdx+750h], r8d
0x14000edcd  jnz     short loc_14000EE04
0x14000edcf  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14000edd5  mov     edx, ebx
0x14000edd7  mov     rcx, rax
0x14000edda  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14000ede0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ede7  lea     rax, WPP_GLOBAL_Control
0x14000edee  cmp     rcx, rax
0x14000edf1  jz      short loc_14000EDFD
0x14000edf3  test    byte ptr [rcx+1Ch], 4
0x14000edf7  jnz     loc_14000F18B
0x14000edfd  mov     eax, ebx
0x14000edff  jmp     loc_14000EF36
0x14000ee04  mov     [rbp+var_18], r8
0x14000ee08  mov     r12d, r8d
0x14000ee0b  mov     [rbp+arg_0], r8d
0x14000ee0f  mov     [rbp+var_30], r8
0x14000ee13  mov     r13d, r8d
0x14000ee16  mov     [rbp+var_38], r8d
0x14000ee1a  mov     [rbp+ppInterface], r8
0x14000ee1e  mov     [rbp+var_28], r8
0x14000ee22  mov     edx, [rdx+690h]
0x14000ee28  sub     edx, 1
0x14000ee2b  jz      short loc_14000EE45
0x14000ee2d  sub     edx, 4
0x14000ee30  jz      short loc_14000EE45
0x14000ee32  sub     edx, 2
0x14000ee35  jz      short loc_14000EE45
0x14000ee37  sub     edx, 1
0x14000ee3a  jz      short loc_14000EE45
0x14000ee3c  sub     edx, 3
0x14000ee3f  jnz     loc_14000EFBC
0x14000ee45  mov     ebx, r8d
0x14000ee48  mov     r14d, r8d
0x14000ee4b  lea     rax, WPP_GLOBAL_Control
0x14000ee52  cmp     rcx, rax
0x14000ee55  jz      short loc_14000EE61
0x14000ee57  test    byte ptr [rcx+1Ch], 4
0x14000ee5b  jnz     loc_14000F0C4
0x14000ee61  test    ebx, ebx
0x14000ee63  js      loc_14000EEF9
0x14000ee69  mov     rdx, rdi; struct IWbemContext *
0x14000ee6c  lea     rcx, [rbp+var_18]; this
0x14000ee70  call    ?Set@CMUIPreferredLanguages@@QEAAJPEAUIWbemContext@@@Z; CMUIPreferredLanguages::Set(IWbemContext *)
0x14000ee75  mov     ebx, eax
0x14000ee77  test    eax, eax
0x14000ee79  js      loc_14000F0F2
0x14000ee7f  mov     [rsp+78h+var_48], r15; struct IWbemServices *
0x14000ee84  mov     rax, [rbp+arg_20]
0x14000ee88  mov     [rsp+78h+var_50], rax; struct IWbemObjectSink *
0x14000ee8d  mov     [rsp+78h+var_58], rdi; struct IWbemContext *
0x14000ee92  mov     r9d, [rbp+arg_10]; int
0x14000ee96  mov     r8, [rbp+arg_8]; unsigned __int16 *
0x14000ee9a  mov     edx, r14d; int
0x14000ee9d  mov     rcx, rsi; this
0x14000eea0  call    ?Helper_CreateClassEnumAsync@CInterceptor_IWbemSyncProvider@@AEAAJHQEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAUIWbemServices@@@Z; CInterceptor_IWbemSyncProvider::Helper_CreateClassEnumAsync(int,ushort * const,long,IWbemContext *,IWbemObjectSink *,IWbemServices *)
0x14000eea5  mov     ebx, eax
0x14000eea7  mov     rdi, [rbp+var_30]
0x14000eeab  mov     r14, [rbp+var_28]
0x14000eeaf  mov     r15, [rbp+ppInterface]
0x14000eeb3  call    cs:__imp_CoRevertToSelf
0x14000eeb9  test    rdi, rdi
0x14000eebc  jnz     loc_14000F14B
0x14000eec2  mov     rcx, [rsi+258h]
0x14000eec9  mov     r9d, [rcx+690h]
0x14000eed0  sub     r9d, 1
0x14000eed4  jz      short loc_14000EEF2
0x14000eed6  sub     r9d, 4
0x14000eeda  jz      short loc_14000EEF2
0x14000eedc  sub     r9d, 2
0x14000eee0  jz      short loc_14000EEF2
0x14000eee2  sub     r9d, 1
0x14000eee6  jz      short loc_14000EEF2
0x14000eee8  sub     r9d, 3
0x14000eeec  jnz     loc_14000F164
0x14000eef2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eef9  mov     rdx, [rbp+var_18]
0x14000eefd  test    rdx, rdx
0x14000ef00  jz      short loc_14000EF2D
0x14000ef02  mov     [rbp+arg_0], 0
0x14000ef09  lea     r8, [rbp+arg_0]
0x14000ef0d  mov     ecx, 8
0x14000ef12  call    cs:__imp_?SetPreferredLanguages@CMUILocale@@SAJKPEBGPEAK@Z; CMUILocale::SetPreferredLanguages(ulong,ushort const *,ulong *)
0x14000ef18  test    eax, eax
0x14000ef1a  js      short loc_14000EF26
0x14000ef1c  mov     rcx, [rbp+var_18]
0x14000ef20  call    cs:__imp_?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x14000ef26  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ef2d  mov     eax, 80041002h
0x14000ef32  cmp     ebx, eax
0x14000ef34  jnz     short loc_14000EF47
0x14000ef36  add     rsp, 78h
0x14000ef3a  pop     r15
0x14000ef3c  pop     r14
0x14000ef3e  pop     r13
0x14000ef40  pop     r12
0x14000ef42  pop     rdi
0x14000ef43  pop     rsi
0x14000ef44  pop     rbx
0x14000ef45  pop     rbp
0x14000ef46  retn
0x14000ef47  test    ebx, ebx
0x14000ef49  jns     loc_14000EDE7
0x14000ef4f  jmp     loc_14000EDCF
0x14000ef54  mov     eax, 80041002h
0x14000ef59  cmp     ebx, eax
0x14000ef5b  jz      short loc_14000EF75
0x14000ef5d  test    ebx, ebx
0x14000ef5f  js      loc_14000F0AE
0x14000ef65  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ef6c  mov     rdi, [rbp+arg_18]
0x14000ef70  jmp     loc_14000EE4B
0x14000ef75  mov     ebx, eax
0x14000ef77  jmp     loc_14000EEF2
0x14000ef7c  cmp     byte ptr [rcx+19h], 5
0x14000ef80  jb      loc_14000EDAB
0x14000ef86  mov     edx, 63h ; 'c'
0x14000ef8b  mov     r9, [rbp+arg_20]
0x14000ef8f  mov     [rsp+78h+var_48], r9
0x14000ef94  mov     [rsp+78h+var_50], rdi
0x14000ef99  mov     dword ptr [rsp+78h+var_58], eax
0x14000ef9d  mov     r9, r8
0x14000efa0  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14000efa7  mov     rcx, [rcx+10h]
0x14000efab  call    WPP_SF_Sdqq
0x14000efb0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000efb7  jmp     loc_14000EDAB
0x14000efbc  sub     edx, 1
0x14000efbf  jz      loc_14000EE45
0x14000efc5  cmp     edx, 1
0x14000efc8  jz      loc_14000EE45
0x14000efce  mov     r14d, r8d
0x14000efd1  mov     r15, r8
0x14000efd4  xor     r9d, r9d; unsigned int *
0x14000efd7  lea     r8, [rbp+var_38]; int *
0x14000efdb  lea     rdx, [rbp+var_28]; struct IServerSecurity **
0x14000efdf  lea     rcx, [rbp+ppInterface]; ppInterface
0x14000efe3  call    ?BeginImpersonation@ProviderSubSystem_Common_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAHPEAK@Z; ProviderSubSystem_Common_Globals::BeginImpersonation(IUnknown * &,IServerSecurity * &,int &,ulong *)
0x14000efe8  mov     ebx, eax
0x14000efea  mov     r13d, [rbp+var_38]
0x14000efee  test    eax, eax
0x14000eff0  js      loc_14000EF54
0x14000eff6  lea     rdi, [rsi+1B8h]
0x14000effd  lea     rax, [rbp+arg_0]
0x14000f001  mov     [rsp+78h+var_50], rax; int *
0x14000f006  lea     rax, [rbp+var_30]
0x14000f00a  mov     [rsp+78h+var_58], rax; struct IUnknown **
0x14000f00f  mov     r9, [rsi+148h]; struct IUnknown *
0x14000f016  lea     r8, IID_IWbemServices; struct _GUID *
0x14000f01d  xor     edx, edx; unsigned int
0x14000f01f  mov     rcx, rdi; struct ProxyContainer *
0x14000f022  call    ?SetProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KAEBU_GUID@@PEAUIUnknown@@AEAPEAU4@AEAH@Z; ProviderSubSystem_Common_Globals::SetProxyState(ProxyContainer &,ulong,_GUID const &,IUnknown *,IUnknown * &,int &)
0x14000f027  mov     ebx, eax
0x14000f029  mov     r12d, [rbp+arg_0]
0x14000f02d  cmp     eax, 80041002h
0x14000f032  jnz     short loc_14000F042
0x14000f034  mov     r15, [rsi+148h]
0x14000f03b  xor     ebx, ebx
0x14000f03d  jmp     loc_14000EF65
0x14000f042  test    eax, eax
0x14000f044  js      short loc_14000F099
0x14000f046  mov     r15, [rbp+var_30]
0x14000f04a  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x14000f04f  mov     r8d, eax; unsigned int
0x14000f052  mov     rcx, r15; struct IUnknown *
0x14000f055  call    ?SetCloaking@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@KK@Z; ProviderSubSystem_Common_Globals::SetCloaking(IUnknown *,ulong,ulong)
0x14000f05a  mov     ebx, eax
0x14000f05c  mov     r14d, 1
0x14000f062  test    eax, eax
0x14000f064  js      short loc_14000F07B
0x14000f066  call    cs:__imp_CoImpersonateClient
0x14000f06c  mov     ebx, eax
0x14000f06e  test    eax, eax
0x14000f070  jns     loc_14000EF54
0x14000f076  mov     ebx, 80041003h
0x14000f07b  mov     r9d, r12d; int
0x14000f07e  mov     r8, [rbp+var_30]; struct IUnknown *
0x14000f082  xor     edx, edx; unsigned int
0x14000f084  mov     rcx, rdi; struct ProxyContainer *
0x14000f087  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x14000f08c  mov     eax, 80041002h
0x14000f091  cmp     ebx, eax
0x14000f093  jz      loc_14000EF75
0x14000f099  mov     r8d, r13d; int
0x14000f09c  mov     rdx, [rbp+var_28]; struct IServerSecurity *
0x14000f0a0  mov     rcx, [rbp+ppInterface]; struct IUnknown *
0x14000f0a4  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x14000f0a9  jmp     loc_14000EF5D
0x14000f0ae  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14000f0b4  mov     edx, ebx
0x14000f0b6  mov     rcx, rax
0x14000f0b9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14000f0bf  jmp     loc_14000EF65
0x14000f0c4  cmp     byte ptr [rcx+19h], 2
0x14000f0c8  jb      loc_14000EE61
0x14000f0ce  mov     edx, 47h ; 'G'
0x14000f0d3  mov     r9d, ebx
0x14000f0d6  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14000f0dd  mov     rcx, [rcx+10h]
0x14000f0e1  call    WPP_SF_d
0x14000f0e6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f0ed  jmp     loc_14000EE61
0x14000f0f2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14000f0f8  mov     edx, ebx
0x14000f0fa  mov     rcx, rax
0x14000f0fd  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14000f103  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f10a  lea     rax, WPP_GLOBAL_Control
0x14000f111  cmp     rcx, rax
0x14000f114  jz      loc_14000EE7F
0x14000f11a  test    byte ptr [rcx+1Ch], 4
0x14000f11e  jz      loc_14000EE7F
0x14000f124  cmp     byte ptr [rcx+19h], 2
0x14000f128  jb      loc_14000EE7F
0x14000f12e  mov     edx, 64h ; 'd'
0x14000f133  mov     r9d, ebx
0x14000f136  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14000f13d  mov     rcx, [rcx+10h]
0x14000f141  call    WPP_SF_d
0x14000f146  jmp     loc_14000EE7F
0x14000f14b  lea     rcx, [rsi+1B8h]; struct ProxyContainer *
0x14000f152  mov     r9d, r12d; int
0x14000f155  mov     r8, rdi; struct IUnknown *
0x14000f158  xor     edx, edx; unsigned int
0x14000f15a  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x14000f15f  jmp     loc_14000EEC2
0x14000f164  sub     r9d, 1
0x14000f168  jz      loc_14000EEF2
0x14000f16e  cmp     r9d, 1
0x14000f172  jz      loc_14000EEF2
0x14000f178  mov     r8d, r13d; int
0x14000f17b  mov     rdx, r14; struct IServerSecurity *
0x14000f17e  mov     rcx, r15; struct IUnknown *
0x14000f181  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x14000f186  jmp     loc_14000EEF2
0x14000f18b  cmp     byte ptr [rcx+19h], 2
0x14000f18f  jb      loc_14000EDFD
0x14000f195  mov     edx, 65h ; 'e'
0x14000f19a  mov     r9d, ebx
0x14000f19d  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14000f1a4  mov     rcx, [rcx+10h]
0x14000f1a8  call    WPP_SF_d
0x14000f1ad  jmp     loc_14000EDFD
```
