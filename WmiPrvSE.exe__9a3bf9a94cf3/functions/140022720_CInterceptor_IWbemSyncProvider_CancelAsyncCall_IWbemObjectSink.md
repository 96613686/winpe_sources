# CInterceptor_IWbemSyncProvider::CancelAsyncCall(IWbemObjectSink *)

- ea: `0x140022720`
- end: `0x140022b53`
- name: `?CancelAsyncCall@CInterceptor_IWbemSyncProvider@@UEAAJPEAUIWbemObjectSink@@@Z`
- size: `1075`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *__hidden this, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400053dc`
- `0x1400054a0`
- `0x140005544`
- `0x1400058dc`
- `0x140006c64`
- `0x14001ca74`
- `0x140022720`
- `0x1400234b8`
- `0x140030438`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140022972`
- `wbemcomn!GetMemLogObject` at `0x1400229c1`
- `wbemcomn!GetMemLogObject` at `0x140022972`
- `wbemcomn!GetMemLogObject` at `0x1400229c1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14002297d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400229cc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14002297d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400229cc`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140022aa7`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140022aa7`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140022898`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140022898`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::CancelAsyncCall(
        CInterceptor_IWbemSyncProvider *this,
        struct IWbemObjectSink *a2)
{
  HRESULT v4; // ebx
  char *v5; // rbx
  __int64 v6; // rax
  int v7; // eax
  char *v8; // rcx
  __int64 v9; // r13
  __int64 v10; // rax
  __int64 v11; // rcx
  int v12; // r15d
  int v13; // edx
  int v14; // edx
  int v15; // edx
  int v16; // edx
  int v17; // edx
  int v18; // edx
  struct IUnknown *v19; // r14
  HRESULT v20; // eax
  struct IUnknown *v21; // r14
  struct IServerSecurity *v22; // r12
  struct IUnknown *v23; // r13
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v26; // rax
  int v27; // eax
  unsigned int CurrentImpersonationLevel; // eax
  unsigned int v29; // edx
  struct IUnknown *v30; // [rsp+30h] [rbp-30h] BYREF
  struct IServerSecurity *v31; // [rsp+38h] [rbp-28h] BYREF
  struct IUnknown *ppInterface; // [rsp+40h] [rbp-20h] BYREF
  __int64 v33; // [rsp+48h] [rbp-18h] BYREF
  __int64 v34; // [rsp+50h] [rbp-10h] BYREF
  __int64 v35; // [rsp+58h] [rbp-8h] BYREF
  struct IWbemObjectSink *v36; // [rsp+A0h] [rbp+40h] BYREF
  int v37; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v38; // [rsp+B8h] [rbp+58h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, a2);
  }
  v4 = -2147217372;
  if ( !*((_QWORD *)this + 41) )
  {
LABEL_29:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v4);
LABEL_30:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        76,
        WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
        (unsigned int)v4);
    }
    return (unsigned int)v4;
  }
  v5 = (char *)this + 232;
  v35 = 0;
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 29) + 48LL))((char *)this + 232);
  v6 = *((_QWORD *)this + 29);
  v36 = a2;
  v7 = (*(__int64 (__fastcall **)(char *, struct IWbemObjectSink **, __int64 *))(v6 + 72))(
         (char *)this + 232,
         &v36,
         &v35);
  v8 = (char *)this + 232;
  if ( v7 )
  {
    (*(void (__fastcall **)(char *))(*(_QWORD *)v5 + 56LL))(v8);
    return (unsigned int)-2147217406;
  }
  v10 = *(_QWORD *)v5;
  v38 = *(_QWORD *)(v35 + 40);
  v9 = v38;
  (*(void (__fastcall **)(char *))(v10 + 56))(v8);
  v33 = 0;
  v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v9)(v9, &IID_IWbemObjectSink, &v33);
  if ( v4 >= 0 )
  {
    v11 = *((_QWORD *)this + 75);
    v12 = 0;
    v30 = 0;
    ppInterface = 0;
    v31 = 0;
    v13 = *(_DWORD *)(v11 + 1680);
    LODWORD(v36) = 0;
    v37 = 0;
    v14 = v13 - 1;
    if ( v14 )
    {
      v15 = v14 - 4;
      if ( v15 )
      {
        v16 = v15 - 2;
        if ( v16 )
        {
          v17 = v16 - 1;
          if ( v17 )
          {
            v18 = v17 - 3;
            if ( v18 )
            {
              if ( (unsigned int)(v18 - 1) >= 2 )
              {
                v19 = 0;
                v4 = ProviderSubSystem_Common_Globals::BeginImpersonation(&ppInterface, &v31, &v37, 0);
                if ( v4 < 0 )
                  goto LABEL_34;
                v27 = ProviderSubSystem_Common_Globals::SetProxyState(
                        (CInterceptor_IWbemSyncProvider *)((char *)this + 440),
                        0,
                        &IID_IWbemServices,
                        *((struct IUnknown **)this + 41),
                        &v30,
                        (int *)&v36);
                v12 = (int)v36;
                v4 = v27;
                if ( v27 != -2147217406 )
                {
                  if ( v27 < 0 )
                  {
LABEL_51:
                    ProviderSubSystem_Common_Globals::EndImpersonation(ppInterface, v31, v37);
LABEL_35:
                    if ( v4 < 0 )
                    {
                      v26 = GetMemLogObject();
                      CMemoryLog::Write(v26, v4);
                    }
                    goto LABEL_13;
                  }
                  v19 = v30;
                  CurrentImpersonationLevel = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
                  v4 = ProviderSubSystem_Common_Globals::SetCloaking(v19, v29, CurrentImpersonationLevel);
                  if ( v4 < 0 )
                    goto LABEL_50;
                  v4 = CoImpersonateClient();
                  if ( v4 < 0 )
                  {
                    v4 = -2147217405;
LABEL_50:
                    ProviderSubSystem_Common_Globals::RevertProxyState(
                      (CInterceptor_IWbemSyncProvider *)((char *)this + 440),
                      0,
                      v30,
                      v12);
                    if ( v4 != -2147217406 )
                      goto LABEL_51;
LABEL_37:
                    v4 = -2147217406;
LABEL_24:
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
                    goto LABEL_25;
                  }
LABEL_34:
                  if ( v4 != -2147217406 )
                    goto LABEL_35;
                  goto LABEL_37;
                }
              }
            }
          }
        }
      }
    }
    v19 = (struct IUnknown *)*((_QWORD *)this + 41);
    v4 = 0;
LABEL_13:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        71,
        WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
        (unsigned int)v4);
    }
    if ( v4 >= 0 )
    {
      v20 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v19->lpVtbl[1].AddRef)(v19, v33);
      v21 = v30;
      v4 = v20;
      v22 = v31;
      v23 = ppInterface;
      CoRevertToSelf();
      if ( v21 )
        ProviderSubSystem_Common_Globals::RevertProxyState(
          (CInterceptor_IWbemSyncProvider *)((char *)this + 440),
          0,
          v21,
          v12);
      if ( *(_DWORD *)(*((_QWORD *)this + 75) + 1680LL) != 1
        && *(_DWORD *)(*((_QWORD *)this + 75) + 1680LL) != 5
        && *(_DWORD *)(*((_QWORD *)this + 75) + 1680LL) != 7
        && *(_DWORD *)(*((_QWORD *)this + 75) + 1680LL) != 8
        && *(_DWORD *)(*((_QWORD *)this + 75) + 1680LL) != 11
        && (unsigned int)(*(_DWORD *)(*((_QWORD *)this + 75) + 1680LL) - 12) >= 2 )
      {
        ProviderSubSystem_Common_Globals::EndImpersonation(v23, v22, v37);
      }
      v9 = v38;
    }
    goto LABEL_24;
  }
LABEL_25:
  v34 = 0;
  if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v9)(v9, &IID_IWbemShutdown, &v34) >= 0 )
  {
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v34 + 24LL))(v34, 0, 0, 0);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  if ( v4 != -2147217406 && v4 != -2147467263 )
  {
    if ( v4 >= 0 )
      goto LABEL_30;
    goto LABEL_29;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140022720  mov     [rsp-38h+arg_8], rbx
0x140022725  push    rbp
0x140022726  push    rsi
0x140022727  push    rdi
0x140022728  push    r12
0x14002272a  push    r13
0x14002272c  push    r14
0x14002272e  push    r15
0x140022730  mov     rbp, rsp
0x140022733  sub     rsp, 60h
0x140022737  mov     rsi, rdx
0x14002273a  mov     rdi, rcx
0x14002273d  mov     rcx, cs:WPP_GLOBAL_Control
0x140022744  lea     r14, WPP_GLOBAL_Control
0x14002274b  cmp     rcx, r14
0x14002274e  jz      short loc_14002275A
0x140022750  test    byte ptr [rcx+1Ch], 4
0x140022754  jnz     loc_1400229F0
0x14002275a  cmp     qword ptr [rdi+148h], 0
0x140022762  mov     ebx, 80041024h
0x140022767  jz      loc_140022972
0x14002276d  lea     rbx, [rdi+0E8h]
0x140022774  mov     [rbp+var_8], 0
0x14002277c  mov     rax, [rbx]
0x14002277f  mov     rcx, rbx
0x140022782  mov     rax, [rax+30h]
0x140022786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002278b  mov     rax, [rbx]
0x14002278e  lea     r8, [rbp+var_8]
0x140022792  lea     rdx, [rbp+arg_0]
0x140022796  mov     [rbp+arg_0], rsi
0x14002279a  mov     rcx, rbx
0x14002279d  mov     rax, [rax+48h]
0x1400227a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400227a6  mov     rcx, rbx
0x1400227a9  test    eax, eax
0x1400227ab  jz      short loc_1400227C3
0x1400227ad  mov     rax, [rbx]
0x1400227b0  mov     rax, [rax+38h]
0x1400227b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400227b9  mov     ebx, 80041002h
0x1400227be  jmp     loc_140022958
0x1400227c3  mov     rax, [rbp+var_8]
0x1400227c7  mov     r13, [rax+28h]
0x1400227cb  mov     rax, [rbx]
0x1400227ce  mov     [rbp+arg_18], r13
0x1400227d2  mov     rax, [rax+38h]
0x1400227d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400227db  mov     [rbp+var_18], 0
0x1400227e3  lea     r8, [rbp+var_18]
0x1400227e7  mov     rax, [r13+0]
0x1400227eb  lea     rdx, IID_IWbemObjectSink
0x1400227f2  mov     rcx, r13
0x1400227f5  mov     rax, [rax]
0x1400227f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400227fd  mov     ebx, eax
0x1400227ff  mov     esi, 80041002h
0x140022804  test    eax, eax
0x140022806  js      loc_1400228F2
0x14002280c  mov     rcx, [rdi+258h]
0x140022813  xor     r15d, r15d
0x140022816  mov     [rbp+var_30], r15
0x14002281a  mov     [rbp+ppInterface], r15
0x14002281e  mov     [rbp+var_28], r15
0x140022822  mov     edx, [rcx+690h]
0x140022828  mov     dword ptr [rbp+arg_0], r15d
0x14002282c  mov     [rbp+arg_10], r15d
0x140022830  sub     edx, 1
0x140022833  jz      short loc_14002284D
0x140022835  sub     edx, 4
0x140022838  jz      short loc_14002284D
0x14002283a  sub     edx, 2
0x14002283d  jz      short loc_14002284D
0x14002283f  sub     edx, 1
0x140022842  jz      short loc_14002284D
0x140022844  sub     edx, 3
0x140022847  jnz     loc_140022A17
0x14002284d  mov     r14, [rdi+148h]
0x140022854  xor     ebx, ebx
0x140022856  mov     rcx, cs:WPP_GLOBAL_Control
0x14002285d  lea     rax, WPP_GLOBAL_Control
0x140022864  cmp     rcx, rax
0x140022867  jz      short loc_140022873
0x140022869  test    byte ptr [rcx+1Ch], 4
0x14002286d  jnz     loc_140022AEB
0x140022873  test    ebx, ebx
0x140022875  js      short loc_1400228DB
0x140022877  mov     rax, [r14]
0x14002287a  mov     rcx, r14
0x14002287d  mov     rdx, [rbp+var_18]
0x140022881  mov     rax, [rax+20h]
0x140022885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002288a  mov     r14, [rbp+var_30]
0x14002288e  mov     ebx, eax
0x140022890  mov     r12, [rbp+var_28]
0x140022894  mov     r13, [rbp+ppInterface]
0x140022898  call    cs:__imp_CoRevertToSelf
0x14002289e  test    r14, r14
0x1400228a1  jnz     loc_140022B12
0x1400228a7  mov     rcx, [rdi+258h]
0x1400228ae  mov     r8d, [rcx+690h]
0x1400228b5  sub     r8d, 1
0x1400228b9  jz      short loc_1400228D7
0x1400228bb  sub     r8d, 4
0x1400228bf  jz      short loc_1400228D7
0x1400228c1  sub     r8d, 2
0x1400228c5  jz      short loc_1400228D7
0x1400228c7  sub     r8d, 1
0x1400228cb  jz      short loc_1400228D7
0x1400228cd  sub     r8d, 3
0x1400228d1  jnz     loc_140022B2B
0x1400228d7  mov     r13, [rbp+arg_18]
0x1400228db  mov     rcx, [rbp+var_18]
0x1400228df  mov     rax, [rcx]
0x1400228e2  mov     rax, [rax+10h]
0x1400228e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400228eb  lea     r14, WPP_GLOBAL_Control
0x1400228f2  mov     [rbp+var_10], 0
0x1400228fa  lea     r8, [rbp+var_10]
0x1400228fe  mov     rax, [r13+0]
0x140022902  lea     rdx, IID_IWbemShutdown
0x140022909  mov     rcx, r13
0x14002290c  mov     rax, [rax]
0x14002290f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022914  test    eax, eax
0x140022916  js      short loc_140022940
0x140022918  mov     rcx, [rbp+var_10]
0x14002291c  xor     r9d, r9d
0x14002291f  xor     r8d, r8d
0x140022922  xor     edx, edx
0x140022924  mov     rax, [rcx]
0x140022927  mov     rax, [rax+18h]
0x14002292b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022930  mov     rcx, [rbp+var_10]
0x140022934  mov     rax, [rcx]
0x140022937  mov     rax, [rax+10h]
0x14002293b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022940  mov     rax, [r13+0]
0x140022944  mov     rcx, r13
0x140022947  mov     rax, [rax+10h]
0x14002294b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022950  cmp     ebx, esi
0x140022952  jnz     loc_1400229DE
0x140022958  mov     eax, ebx
0x14002295a  mov     rbx, [rsp+60h+arg_8]
0x140022962  add     rsp, 60h
0x140022966  pop     r15
0x140022968  pop     r14
0x14002296a  pop     r13
0x14002296c  pop     r12
0x14002296e  pop     rdi
0x14002296f  pop     rsi
0x140022970  pop     rbp
0x140022971  retn
0x140022972  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140022978  mov     rcx, rax
0x14002297b  mov     edx, ebx
0x14002297d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140022983  mov     rcx, cs:WPP_GLOBAL_Control
0x14002298a  cmp     rcx, r14
0x14002298d  jz      short loc_140022958
0x14002298f  test    byte ptr [rcx+1Ch], 4
0x140022993  jz      short loc_140022958
0x140022995  cmp     byte ptr [rcx+19h], 2
0x140022999  jb      short loc_140022958
0x14002299b  mov     rcx, [rcx+10h]
0x14002299f  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x1400229a6  mov     edx, 4Ch ; 'L'
0x1400229ab  mov     r9d, ebx
0x1400229ae  call    WPP_SF_d
0x1400229b3  jmp     short loc_140022958
0x1400229b5  cmp     ebx, esi
0x1400229b7  jz      short loc_1400229D7
0x1400229b9  test    ebx, ebx
0x1400229bb  jns     loc_140022856
0x1400229c1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400229c7  mov     rcx, rax
0x1400229ca  mov     edx, ebx
0x1400229cc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400229d2  jmp     loc_140022856
0x1400229d7  mov     ebx, esi
0x1400229d9  jmp     loc_1400228DB
0x1400229de  cmp     ebx, 80004001h
0x1400229e4  jz      loc_140022958
0x1400229ea  test    ebx, ebx
0x1400229ec  jns     short loc_140022983
0x1400229ee  jmp     short loc_140022972
0x1400229f0  cmp     byte ptr [rcx+19h], 5
0x1400229f4  jb      loc_14002275A
0x1400229fa  mov     rcx, [rcx+10h]
0x1400229fe  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x140022a05  mov     edx, 4Bh ; 'K'
0x140022a0a  mov     r9, rsi
0x140022a0d  call    WPP_SF_q
0x140022a12  jmp     loc_14002275A
0x140022a17  sub     edx, 1
0x140022a1a  jz      loc_14002284D
0x140022a20  cmp     edx, 1
0x140022a23  jz      loc_14002284D
0x140022a29  xor     r9d, r9d; unsigned int *
0x140022a2c  lea     r8, [rbp+arg_10]; int *
0x140022a30  lea     rdx, [rbp+var_28]; struct IServerSecurity **
0x140022a34  xor     r14d, r14d
0x140022a37  lea     rcx, [rbp+ppInterface]; ppInterface
0x140022a3b  call    ?BeginImpersonation@ProviderSubSystem_Common_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAHPEAK@Z; ProviderSubSystem_Common_Globals::BeginImpersonation(IUnknown * &,IServerSecurity * &,int &,ulong *)
0x140022a40  mov     ebx, eax
0x140022a42  test    eax, eax
0x140022a44  js      loc_1400229B5
0x140022a4a  mov     r9, [rdi+148h]; struct IUnknown *
0x140022a51  lea     rax, [rbp+arg_0]
0x140022a55  mov     [rsp+60h+var_38], rax; int *
0x140022a5a  lea     r12, [rdi+1B8h]
0x140022a61  lea     rax, [rbp+var_30]
0x140022a65  xor     edx, edx; unsigned int
0x140022a67  lea     r8, IID_IWbemServices; struct _GUID *
0x140022a6e  mov     [rsp+60h+var_40], rax; struct IUnknown **
0x140022a73  mov     rcx, r12; struct ProxyContainer *
0x140022a76  call    ?SetProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KAEBU_GUID@@PEAUIUnknown@@AEAPEAU4@AEAH@Z; ProviderSubSystem_Common_Globals::SetProxyState(ProxyContainer &,ulong,_GUID const &,IUnknown *,IUnknown * &,int &)
0x140022a7b  mov     r15d, dword ptr [rbp+arg_0]
0x140022a7f  mov     ebx, eax
0x140022a81  cmp     eax, esi
0x140022a83  jz      loc_14002284D
0x140022a89  test    eax, eax
0x140022a8b  js      short loc_140022AD5
0x140022a8d  mov     r14, [rbp+var_30]
0x140022a91  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x140022a96  mov     r8d, eax; unsigned int
0x140022a99  mov     rcx, r14; struct IUnknown *
0x140022a9c  call    ?SetCloaking@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@KK@Z; ProviderSubSystem_Common_Globals::SetCloaking(IUnknown *,ulong,ulong)
0x140022aa1  mov     ebx, eax
0x140022aa3  test    eax, eax
0x140022aa5  js      short loc_140022ABC
0x140022aa7  call    cs:__imp_CoImpersonateClient
0x140022aad  mov     ebx, eax
0x140022aaf  test    eax, eax
0x140022ab1  jns     loc_1400229B5
0x140022ab7  mov     ebx, 80041003h
0x140022abc  mov     r8, [rbp+var_30]; struct IUnknown *
0x140022ac0  mov     r9d, r15d; int
0x140022ac3  xor     edx, edx; unsigned int
0x140022ac5  mov     rcx, r12; struct ProxyContainer *
0x140022ac8  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x140022acd  cmp     ebx, esi
0x140022acf  jz      loc_1400229D7
0x140022ad5  mov     r8d, [rbp+arg_10]; int
0x140022ad9  mov     rdx, [rbp+var_28]; struct IServerSecurity *
0x140022add  mov     rcx, [rbp+ppInterface]; struct IUnknown *
0x140022ae1  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x140022ae6  jmp     loc_1400229B9
0x140022aeb  cmp     byte ptr [rcx+19h], 2
0x140022aef  jb      loc_140022873
0x140022af5  mov     rcx, [rcx+10h]
0x140022af9  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x140022b00  mov     edx, 47h ; 'G'
0x140022b05  mov     r9d, ebx
0x140022b08  call    WPP_SF_d
0x140022b0d  jmp     loc_140022873
0x140022b12  lea     rcx, [rdi+1B8h]; struct ProxyContainer *
0x140022b19  mov     r9d, r15d; int
0x140022b1c  mov     r8, r14; struct IUnknown *
0x140022b1f  xor     edx, edx; unsigned int
0x140022b21  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x140022b26  jmp     loc_1400228A7
0x140022b2b  sub     r8d, 1
0x140022b2f  jz      loc_1400228D7
0x140022b35  cmp     r8d, 1
0x140022b39  jz      loc_1400228D7
0x140022b3f  mov     r8d, [rbp+arg_10]; int
0x140022b43  mov     rdx, r12; struct IServerSecurity *
0x140022b46  mov     rcx, r13; struct IUnknown *
0x140022b49  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x140022b4e  jmp     loc_1400228D7
```
