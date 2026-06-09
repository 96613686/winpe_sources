# CInterceptor_IWbemSyncProvider::GetObjectAsync(ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x14000b7d0`
- end: `0x14000bca8`
- name: `?GetObjectAsync@CInterceptor_IWbemSyncProvider@@UEAAJQEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `1240`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *__hidden this, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400053dc`
- `0x1400054a0`
- `0x140005544`
- `0x1400058dc`
- `0x140006c64`
- `0x14000b7d0`
- `0x14000bcb0`
- `0x14000d090`
- `0x14001ca74`
- `0x1400234b8`
- `0x140026cc4`
- `0x140028cfc`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14000b980`
- `wbemcomn!GetMemLogObject` at `0x14000bb1c`
- `wbemcomn!GetMemLogObject` at `0x14000bb59`
- `wbemcomn!GetMemLogObject` at `0x14000b980`
- `wbemcomn!GetMemLogObject` at `0x14000bb1c`
- `wbemcomn!GetMemLogObject` at `0x14000bb59`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000b98b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000bb27`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000bb64`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000b98b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000bb27`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000bb64`
- `wbemcomn!?_Free@CMUILocale@@SAHPEAX@Z` at `0x14000b92b`
- `wbemcomn!?_Free@CMUILocale@@SAHPEAX@Z` at `0x14000b92b`
- `wbemcomn!?SetPreferredLanguages@CMUILocale@@SAJKPEBGPEAK@Z` at `0x14000b91d`
- `wbemcomn!?SetPreferredLanguages@CMUILocale@@SAJKPEBGPEAK@Z` at `0x14000b91d`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000baa8`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000baa8`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000b8e0`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000b8e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInterceptor_IWbemSyncProvider::GetObjectAsync(
        CInterceptor_IWbemSyncProvider *this,
        unsigned __int16 *const a2,
        int a3,
        struct IWbemContext *a4,
        struct IWbemObjectSink *a5)
{
  unsigned __int16 *v7; // rax
  struct IWbemObjectSink *v9; // r13
  __int64 ObjectAsync; // rbx
  struct IUnknown *v11; // rsi
  _DWORD *v12; // rax
  int v13; // ecx
  int v14; // ebx
  struct IUnknown *v15; // rsi
  struct IServerSecurity *v16; // r15
  struct IUnknown *v17; // r12
  int v18; // r9d
  struct IWbemHiPerfProvider *v20; // rdx
  CMemoryLog *v21; // rax
  HRESULT v22; // eax
  int v23; // eax
  unsigned int CurrentImpersonationLevel; // eax
  unsigned int v25; // edx
  CMemoryLog *v26; // rax
  CMemoryLog *MemLogObject; // rax
  int v28; // [rsp+40h] [rbp-30h]
  int v29; // [rsp+44h] [rbp-2Ch] BYREF
  int v30; // [rsp+48h] [rbp-28h] BYREF
  struct IUnknown *v31; // [rsp+50h] [rbp-20h] BYREF
  struct IServerSecurity *v32; // [rsp+58h] [rbp-18h] BYREF
  struct IUnknown *ppInterface; // [rsp+60h] [rbp-10h] BYREF
  void *v34; // [rsp+68h] [rbp-8h] BYREF
  int v35; // [rsp+B0h] [rbp+40h] BYREF
  unsigned __int16 *v36; // [rsp+B8h] [rbp+48h]

  v36 = a2;
  v7 = a2;
  v9 = a5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Sdqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      84,
      (unsigned int)WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (_DWORD)a2,
      a3,
      (char)a4,
      (char)a5);
    v7 = v36;
  }
  LODWORD(ObjectAsync) = -2147217372;
  v11 = (struct IUnknown *)*((_QWORD *)this + 41);
  if ( v11 )
  {
    v12 = (_DWORD *)*((_QWORD *)this + 75);
    if ( !v12[506] && !v12[466] )
      goto LABEL_23;
    v34 = 0;
    v29 = 0;
    v31 = 0;
    v30 = 0;
    ppInterface = 0;
    v32 = 0;
    v13 = v12[420];
    if ( v13 == 11 )
    {
LABEL_6:
      v28 = 0;
      LODWORD(ObjectAsync) = 0;
LABEL_7:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          71,
          WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
          (unsigned int)ObjectAsync);
      }
      if ( (int)ObjectAsync >= 0 )
      {
        v14 = CMUIPreferredLanguages::Set((CMUIPreferredLanguages *)&v34, a4);
        if ( v14 < 0 )
        {
          MemLogObject = GetMemLogObject();
          CMemoryLog::Write(MemLogObject, v14);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              85,
              WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
              (unsigned int)v14);
          }
        }
        LODWORD(ObjectAsync) = CInterceptor_IWbemSyncProvider::Helper_GetObjectAsync(
                                 this,
                                 v28,
                                 v36,
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
        v22 = ProviderSubSystem_Common_Globals::BeginImpersonation(&ppInterface, &v32, &v30, 0);
        v35 = v22;
        LODWORD(ObjectAsync) = -2147217406;
        if ( v22 < 0 )
          goto LABEL_27;
        v23 = ProviderSubSystem_Common_Globals::SetProxyState(
                (CInterceptor_IWbemSyncProvider *)((char *)this + 440),
                0,
                &IID_IWbemServices,
                *((struct IUnknown **)this + 41),
                &v31,
                &v29);
        if ( v23 == -2147217406 )
        {
          v11 = (struct IUnknown *)*((_QWORD *)this + 41);
          goto LABEL_6;
        }
        if ( v23 < 0 )
        {
          LODWORD(ObjectAsync) = v23;
        }
        else
        {
          v11 = v31;
          CurrentImpersonationLevel = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
          v35 = ProviderSubSystem_Common_Globals::SetCloaking(v11, v25, CurrentImpersonationLevel);
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
            LODWORD(ObjectAsync) = v35;
          }
          else
          {
            v28 = 1;
            v22 = CoImpersonateClient();
            v35 = v22;
            if ( v22 >= 0 )
            {
LABEL_27:
              if ( v22 == -2147217406 )
                goto LABEL_14;
              LODWORD(ObjectAsync) = v35;
LABEL_43:
              if ( (int)ObjectAsync < 0 )
              {
                v26 = GetMemLogObject();
                CMemoryLog::Write(v26, ObjectAsync);
              }
              goto LABEL_7;
            }
            LODWORD(ObjectAsync) = -2147217405;
            ProviderSubSystem_Common_Globals::RevertProxyState(
              (CInterceptor_IWbemSyncProvider *)((char *)this + 440),
              0,
              v31,
              v29);
          }
        }
        ProviderSubSystem_Common_Globals::EndImpersonation(ppInterface, v32, v30);
        goto LABEL_43;
    }
  }
  v20 = (struct IWbemHiPerfProvider *)*((_QWORD *)this + 43);
  if ( !v20 )
    goto LABEL_23;
  ObjectAsync = (unsigned int)CInterceptor_IWbemSyncProvider::Helper_HiPerfGetObjectAsync(
                                this,
                                v20,
                                v7,
                                (int)a4,
                                a4,
                                v9);
  ((void (__fastcall *)(struct IWbemObjectSink *, _QWORD, __int64, _QWORD, _QWORD))v9->lpVtbl->SetStatus)(
    v9,
    0,
    ObjectAsync,
    0,
    0);
LABEL_17:
  if ( (int)ObjectAsync < 0 )
  {
LABEL_23:
    v21 = GetMemLogObject();
    CMemoryLog::Write(v21, ObjectAsync);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      86,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (unsigned int)ObjectAsync);
  }
  return (unsigned int)ObjectAsync;
}

```

## disassembly

```asm
0x14000b7d0  mov     [rsp-38h+arg_10], rbx
0x14000b7d5  mov     [rsp-38h+arg_8], rdx
0x14000b7da  push    rbp
0x14000b7db  push    rsi
0x14000b7dc  push    rdi
0x14000b7dd  push    r12
0x14000b7df  push    r13
0x14000b7e1  push    r14
0x14000b7e3  push    r15
0x14000b7e5  mov     rbp, rsp
0x14000b7e8  sub     rsp, 70h
0x14000b7ec  mov     r15, r9
0x14000b7ef  mov     r12d, r8d
0x14000b7f2  mov     rax, rdx
0x14000b7f5  mov     rdi, rcx
0x14000b7f8  lea     rbx, WPP_GLOBAL_Control
0x14000b7ff  mov     r13, [rbp+arg_20]
0x14000b803  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b80a  cmp     rcx, rbx
0x14000b80d  jz      short loc_14000B819
0x14000b80f  test    byte ptr [rcx+1Ch], 4
0x14000b813  jnz     loc_14000B9C9
0x14000b819  mov     ebx, 80041024h
0x14000b81e  mov     rsi, [rdi+148h]
0x14000b825  test    rsi, rsi
0x14000b828  jz      loc_14000B970
0x14000b82e  mov     rax, [rdi+258h]
0x14000b835  cmp     dword ptr [rax+7E8h], 0
0x14000b83c  jz      loc_14000B962
0x14000b842  xor     r14d, r14d
0x14000b845  mov     [rbp+var_8], r14
0x14000b849  mov     [rbp+var_2C], r14d
0x14000b84d  mov     [rbp+var_20], r14
0x14000b851  mov     [rbp+var_28], r14d
0x14000b855  mov     [rbp+ppInterface], r14
0x14000b859  mov     [rbp+var_18], r14
0x14000b85d  mov     ecx, [rax+690h]
0x14000b863  lea     rdx, __ImageBase
0x14000b86a  cmp     ecx, 0Bh
0x14000b86d  jnz     loc_14000BA03
0x14000b873  mov     [rbp+var_30], r14d; jumptable 000000014000BA17 cases 1,5,7,8,12,13
0x14000b877  mov     ebx, r14d
0x14000b87a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b881  lea     rax, WPP_GLOBAL_Control
0x14000b888  cmp     rcx, rax
0x14000b88b  jz      short loc_14000B897
0x14000b88d  test    byte ptr [rcx+1Ch], 4
0x14000b891  jnz     loc_14000BB32
0x14000b897  test    ebx, ebx
0x14000b899  js      short loc_14000B907; jumptable 000000014000BBEA cases 1,5,7,8,12,13
0x14000b89b  mov     rdx, r15; struct IWbemContext *
0x14000b89e  lea     rcx, [rbp+var_8]; this
0x14000b8a2  call    ?Set@CMUIPreferredLanguages@@QEAAJPEAUIWbemContext@@@Z; CMUIPreferredLanguages::Set(IWbemContext *)
0x14000b8a7  mov     ebx, eax
0x14000b8a9  test    eax, eax
0x14000b8ab  js      loc_14000BB59
0x14000b8b1  mov     [rsp+70h+var_40], rsi; struct IWbemServices *
0x14000b8b6  mov     [rsp+70h+var_48], r13; struct IWbemObjectSink *
0x14000b8bb  mov     [rsp+70h+var_50], r15; struct IWbemContext *
0x14000b8c0  mov     r9d, r12d; int
0x14000b8c3  mov     r8, [rbp+arg_8]; unsigned __int16 *
0x14000b8c7  mov     edx, [rbp+var_30]; int
0x14000b8ca  mov     rcx, rdi; this
0x14000b8cd  call    ?Helper_GetObjectAsync@CInterceptor_IWbemSyncProvider@@AEAAJHQEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAUIWbemServices@@@Z; CInterceptor_IWbemSyncProvider::Helper_GetObjectAsync(int,ushort * const,long,IWbemContext *,IWbemObjectSink *,IWbemServices *)
0x14000b8d2  mov     ebx, eax
0x14000b8d4  mov     rsi, [rbp+var_20]
0x14000b8d8  mov     r15, [rbp+var_18]
0x14000b8dc  mov     r12, [rbp+ppInterface]
0x14000b8e0  call    cs:__imp_CoRevertToSelf
0x14000b8e6  test    rsi, rsi
0x14000b8e9  jnz     loc_14000BBB2
0x14000b8ef  mov     rax, [rdi+258h]
0x14000b8f6  mov     r9d, [rax+690h]
0x14000b8fd  cmp     r9d, 0Bh
0x14000b901  jnz     loc_14000BBCC
0x14000b907  mov     rdx, [rbp+var_8]; jumptable 000000014000BBEA cases 1,5,7,8,12,13
0x14000b90b  test    rdx, rdx
0x14000b90e  jz      short loc_14000B931
0x14000b910  mov     [rbp+arg_0], r14d
0x14000b914  lea     r8, [rbp+arg_0]
0x14000b918  mov     ecx, 8
0x14000b91d  call    cs:__imp_?SetPreferredLanguages@CMUILocale@@SAJKPEBGPEAK@Z; CMUILocale::SetPreferredLanguages(ulong,ushort const *,ulong *)
0x14000b923  test    eax, eax
0x14000b925  js      short loc_14000B931
0x14000b927  mov     rcx, [rbp+var_8]
0x14000b92b  call    cs:__imp_?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x14000b931  test    ebx, ebx
0x14000b933  js      short loc_14000B980
0x14000b935  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b93c  lea     rax, WPP_GLOBAL_Control
0x14000b943  cmp     rcx, rax
0x14000b946  jnz     short loc_14000B993
0x14000b948  mov     eax, ebx
0x14000b94a  mov     rbx, [rsp+70h+arg_10]
0x14000b952  add     rsp, 70h
0x14000b956  pop     r15
0x14000b958  pop     r14
0x14000b95a  pop     r13
0x14000b95c  pop     r12
0x14000b95e  pop     rdi
0x14000b95f  pop     rsi
0x14000b960  pop     rbp
0x14000b961  retn
0x14000b962  cmp     dword ptr [rax+748h], 0
0x14000b969  jz      short loc_14000B980
0x14000b96b  jmp     loc_14000B842
0x14000b970  mov     rdx, [rdi+158h]; struct IWbemHiPerfProvider *
0x14000b977  test    rdx, rdx
0x14000b97a  jnz     loc_14000BC01
0x14000b980  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14000b986  mov     edx, ebx
0x14000b988  mov     rcx, rax
0x14000b98b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14000b991  jmp     short loc_14000B935
0x14000b993  test    byte ptr [rcx+1Ch], 4
0x14000b997  jz      short loc_14000B948
0x14000b999  cmp     byte ptr [rcx+19h], 2
0x14000b99d  jb      short loc_14000B948
0x14000b99f  mov     edx, 56h ; 'V'
0x14000b9a4  mov     r9d, ebx
0x14000b9a7  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14000b9ae  mov     rcx, [rcx+10h]
0x14000b9b2  call    WPP_SF_d
0x14000b9b7  jmp     short loc_14000B948
0x14000b9b9  cmp     eax, ebx
0x14000b9bb  jz      loc_14000B907; jumptable 000000014000BBEA cases 1,5,7,8,12,13
0x14000b9c1  mov     ebx, [rbp+arg_0]
0x14000b9c4  jmp     loc_14000BB14
0x14000b9c9  cmp     byte ptr [rcx+19h], 5
0x14000b9cd  jb      loc_14000B819
0x14000b9d3  mov     edx, 54h ; 'T'
0x14000b9d8  mov     [rsp+70h+var_40], r13
0x14000b9dd  mov     [rsp+70h+var_48], r15
0x14000b9e2  mov     dword ptr [rsp+70h+var_50], r12d
0x14000b9e7  mov     r9, rax
0x14000b9ea  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14000b9f1  mov     rcx, [rcx+10h]
0x14000b9f5  call    WPP_SF_Sdqq
0x14000b9fa  mov     rax, [rbp+arg_8]
0x14000b9fe  jmp     loc_14000B819
0x14000ba03  dec     ecx; switch 13 cases
0x14000ba05  cmp     ecx, 0Ch
0x14000ba08  ja      short def_14000BA17; jumptable 000000014000BA17 default case, cases 2-4,6,9-11
0x14000ba0a  movsxd  rax, ecx
0x14000ba0d  mov     ecx, ds:(jpt_14000BA17 - 140000000h)[rdx+rax*4]
0x14000ba14  add     rcx, rdx
0x14000ba17  jmp     rcx; switch jump
0x14000ba19  mov     [rbp+var_30], r14d; jumptable 000000014000BA17 default case, cases 2-4,6,9-11
0x14000ba1d  mov     rsi, r14
0x14000ba20  xor     r9d, r9d; unsigned int *
0x14000ba23  lea     r8, [rbp+var_28]; int *
0x14000ba27  lea     rdx, [rbp+var_18]; struct IServerSecurity **
0x14000ba2b  lea     rcx, [rbp+ppInterface]; ppInterface
0x14000ba2f  call    ?BeginImpersonation@ProviderSubSystem_Common_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAHPEAK@Z; ProviderSubSystem_Common_Globals::BeginImpersonation(IUnknown * &,IServerSecurity * &,int &,ulong *)
0x14000ba34  mov     [rbp+arg_0], eax
0x14000ba37  mov     ebx, 80041002h
0x14000ba3c  test    eax, eax
0x14000ba3e  js      loc_14000B9B9
0x14000ba44  lea     rcx, [rbp+var_2C]
0x14000ba48  mov     [rsp+70h+var_48], rcx; int *
0x14000ba4d  lea     rcx, [rbp+var_20]
0x14000ba51  mov     [rsp+70h+var_50], rcx; struct IUnknown **
0x14000ba56  mov     r9, [rdi+148h]; struct IUnknown *
0x14000ba5d  lea     r8, IID_IWbemServices; struct _GUID *
0x14000ba64  xor     edx, edx; unsigned int
0x14000ba66  lea     rcx, [rdi+1B8h]; struct ProxyContainer *
0x14000ba6d  call    ?SetProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KAEBU_GUID@@PEAUIUnknown@@AEAPEAU4@AEAH@Z; ProviderSubSystem_Common_Globals::SetProxyState(ProxyContainer &,ulong,_GUID const &,IUnknown *,IUnknown * &,int &)
0x14000ba72  cmp     eax, ebx
0x14000ba74  jnz     short loc_14000BA82
0x14000ba76  mov     rsi, [rdi+148h]
0x14000ba7d  jmp     loc_14000B873; jumptable 000000014000BA17 cases 1,5,7,8,12,13
0x14000ba82  test    eax, eax
0x14000ba84  js      short loc_14000BB01
0x14000ba86  mov     rsi, [rbp+var_20]
0x14000ba8a  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x14000ba8f  mov     r8d, eax; unsigned int
0x14000ba92  mov     rcx, rsi; struct IUnknown *
0x14000ba95  call    ?SetCloaking@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@KK@Z; ProviderSubSystem_Common_Globals::SetCloaking(IUnknown *,ulong,ulong)
0x14000ba9a  mov     [rbp+arg_0], eax
0x14000ba9d  test    eax, eax
0x14000ba9f  js      short loc_14000BAD6
0x14000baa1  mov     [rbp+var_30], 1
0x14000baa8  call    cs:__imp_CoImpersonateClient
0x14000baae  mov     [rbp+arg_0], eax
0x14000bab1  test    eax, eax
0x14000bab3  jns     loc_14000B9B9
0x14000bab9  mov     ebx, 80041003h
0x14000babe  mov     r9d, [rbp+var_2C]; int
0x14000bac2  mov     r8, [rbp+var_20]; struct IUnknown *
0x14000bac6  xor     edx, edx; unsigned int
0x14000bac8  lea     rcx, [rdi+1B8h]; struct ProxyContainer *
0x14000bacf  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x14000bad4  jmp     short loc_14000BB03
0x14000bad6  mov     r9d, [rbp+var_2C]; int
0x14000bada  mov     r8, [rbp+var_20]; struct IUnknown *
0x14000bade  xor     edx, edx; unsigned int
0x14000bae0  lea     rcx, [rdi+1B8h]; struct ProxyContainer *
0x14000bae7  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x14000baec  cmp     [rbp+arg_0], ebx
0x14000baef  jz      loc_14000B907; jumptable 000000014000BBEA cases 1,5,7,8,12,13
0x14000baf5  mov     [rbp+var_30], 1
0x14000bafc  mov     ebx, [rbp+arg_0]
0x14000baff  jmp     short loc_14000BB03
0x14000bb01  mov     ebx, eax
0x14000bb03  mov     r8d, [rbp+var_28]; int
0x14000bb07  mov     rdx, [rbp+var_18]; struct IServerSecurity *
0x14000bb0b  mov     rcx, [rbp+ppInterface]; struct IUnknown *
0x14000bb0f  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x14000bb14  test    ebx, ebx
0x14000bb16  jns     loc_14000B87A
0x14000bb1c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14000bb22  mov     edx, ebx
0x14000bb24  mov     rcx, rax
0x14000bb27  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14000bb2d  jmp     loc_14000B87A
0x14000bb32  cmp     byte ptr [rcx+19h], 2
0x14000bb36  jb      loc_14000B897
0x14000bb3c  mov     edx, 47h ; 'G'
0x14000bb41  mov     r9d, ebx
0x14000bb44  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14000bb4b  mov     rcx, [rcx+10h]
0x14000bb4f  call    WPP_SF_d
0x14000bb54  jmp     loc_14000B897
0x14000bb59  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14000bb5f  mov     edx, ebx
0x14000bb61  mov     rcx, rax
0x14000bb64  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14000bb6a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bb71  lea     rax, WPP_GLOBAL_Control
0x14000bb78  cmp     rcx, rax
0x14000bb7b  jz      loc_14000B8B1
0x14000bb81  test    byte ptr [rcx+1Ch], 4
0x14000bb85  jz      loc_14000B8B1
0x14000bb8b  cmp     byte ptr [rcx+19h], 2
0x14000bb8f  jb      loc_14000B8B1
0x14000bb95  mov     edx, 55h ; 'U'
0x14000bb9a  mov     r9d, ebx
0x14000bb9d  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14000bba4  mov     rcx, [rcx+10h]
0x14000bba8  call    WPP_SF_d
0x14000bbad  jmp     loc_14000B8B1
0x14000bbb2  lea     rcx, [rdi+1B8h]; struct ProxyContainer *
0x14000bbb9  mov     r9d, [rbp+var_2C]; int
0x14000bbbd  mov     r8, rsi; struct IUnknown *
0x14000bbc0  xor     edx, edx; unsigned int
0x14000bbc2  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x14000bbc7  jmp     loc_14000B8EF
0x14000bbcc  dec     r9d; switch 13 cases
0x14000bbcf  cmp     r9d, 0Ch
0x14000bbd3  ja      short def_14000BBEA; jumptable 000000014000BBEA default case, cases 2-4,6,9-11
0x14000bbd5  movsxd  rax, r9d
0x14000bbd8  lea     rcx, __ImageBase
0x14000bbdf  mov     r9d, ds:(jpt_14000BBEA - 140000000h)[rcx+rax*4]
0x14000bbe7  add     r9, rcx
0x14000bbea  jmp     r9; switch jump
0x14000bbed  mov     r8d, [rbp+var_28]; jumptable 000000014000BBEA default case, cases 2-4,6,9-11
0x14000bbf1  mov     rdx, r15; struct IServerSecurity *
0x14000bbf4  mov     rcx, r12; struct IUnknown *
0x14000bbf7  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x14000bbfc  jmp     loc_14000B907; jumptable 000000014000BBEA cases 1,5,7,8,12,13
0x14000bc01  mov     [rsp+70h+var_48], r13; struct IWbemObjectSink *
0x14000bc06  mov     [rsp+70h+var_50], r15; struct IWbemContext *
0x14000bc0b  mov     r8, rax; unsigned __int16 *
0x14000bc0e  mov     rcx, rdi; this
0x14000bc11  call    ?Helper_HiPerfGetObjectAsync@CInterceptor_IWbemSyncProvider@@AEAAJPEAUIWbemHiPerfProvider@@QEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z; CInterceptor_IWbemSyncProvider::Helper_HiPerfGetObjectAsync(IWbemHiPerfProvider *,ushort * const,long,IWbemContext *,IWbemObjectSink *)
0x14000bc16  mov     ebx, eax
0x14000bc18  mov     rax, [r13+0]
0x14000bc1c  xor     r14d, r14d
0x14000bc1f  mov     [rsp+70h+var_50], r14
0x14000bc24  xor     r9d, r9d
0x14000bc27  mov     r8d, ebx
0x14000bc2a  xor     edx, edx
0x14000bc2c  mov     rcx, r13
0x14000bc2f  mov     rax, [rax+20h]
0x14000bc33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bc38  jmp     loc_14000B931
```
