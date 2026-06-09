# CInterceptor_IWbemSyncProvider::PutInstanceAsync(IWbemClassObject *,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x140021dc0`
- end: `0x140022149`
- name: `?PutInstanceAsync@CInterceptor_IWbemSyncProvider@@UEAAJPEAUIWbemClassObject@@JPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `905`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *this, struct IWbemClassObject *, int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400053dc`
- `0x1400054a0`
- `0x140005544`
- `0x1400058dc`
- `0x140006c64`
- `0x14000b420`
- `0x14001ca74`
- `0x140021dc0`
- `0x1400234b8`
- `0x1400304c8`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140021e2b`
- `wbemcomn!GetMemLogObject` at `0x1400220c4`
- `wbemcomn!GetMemLogObject` at `0x140021e2b`
- `wbemcomn!GetMemLogObject` at `0x1400220c4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140021e36`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400220cf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140021e36`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400220cf`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14002207d`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14002207d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140021ed8`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140021ed8`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::PutInstanceAsync(
        CInterceptor_IWbemSyncProvider *this,
        struct IWbemClassObject *a2,
        int a3,
        struct IWbemContext *a4,
        struct IWbemObjectSink *a5)
{
  _QWORD *v6; // r10
  struct IUnknown *v7; // r15
  int v8; // edi
  __int64 v9; // rcx
  CMemoryLog *MemLogObject; // rax
  int v11; // r12d
  int v12; // r13d
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  HRESULT v19; // ebx
  int v20; // r14d
  int v21; // eax
  struct IUnknown *v22; // rbx
  struct IServerSecurity *v23; // r14
  struct IUnknown *v24; // r15
  int v26; // eax
  unsigned int CurrentImpersonationLevel; // eax
  unsigned int v28; // edx
  CMemoryLog *v29; // rax
  int v30; // [rsp+40h] [rbp-28h] BYREF
  struct IUnknown *v31; // [rsp+48h] [rbp-20h] BYREF
  struct IServerSecurity *v32; // [rsp+50h] [rbp-18h] BYREF
  struct IUnknown *ppInterface; // [rsp+58h] [rbp-10h] BYREF
  int v34; // [rsp+B0h] [rbp+48h] BYREF
  struct IWbemClassObject *v35; // [rsp+B8h] [rbp+50h]
  int v36; // [rsp+C0h] [rbp+58h]
  struct IWbemContext *v37; // [rsp+C8h] [rbp+60h]

  v37 = a4;
  v36 = a3;
  v35 = a2;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qdqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      104,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      a2,
      a3,
      a4,
      a5);
    v6 = WPP_GLOBAL_Control;
  }
  v7 = (struct IUnknown *)*((_QWORD *)this + 41);
  v8 = -2147217372;
  if ( !v7 )
    goto LABEL_5;
  v9 = *((_QWORD *)this + 75);
  if ( !*(_DWORD *)(v9 + 2020) )
    goto LABEL_5;
  v31 = 0;
  v11 = 0;
  ppInterface = 0;
  v12 = 0;
  v32 = 0;
  v13 = *(_DWORD *)(v9 + 1680);
  v30 = 0;
  v34 = 0;
  v14 = v13 - 1;
  if ( !v14
    || (v15 = v14 - 4) == 0
    || (v16 = v15 - 2) == 0
    || (v17 = v16 - 1) == 0
    || (v18 = v17 - 3) == 0
    || (unsigned int)(v18 - 1) < 2 )
  {
    v19 = 0;
    v20 = 0;
    goto LABEL_12;
  }
  v20 = 0;
  v7 = 0;
  v19 = ProviderSubSystem_Common_Globals::BeginImpersonation(&ppInterface, &v32, &v34, 0);
  v8 = -2147217406;
  if ( v19 >= 0 )
  {
    v26 = ProviderSubSystem_Common_Globals::SetProxyState(
            (CInterceptor_IWbemSyncProvider *)((char *)this + 440),
            0,
            &IID_IWbemServices,
            *((struct IUnknown **)this + 41),
            &v31,
            &v30);
    v11 = v30;
    v19 = v26;
    if ( v26 == -2147217406 )
    {
      v7 = (struct IUnknown *)*((_QWORD *)this + 41);
      v19 = 0;
      v6 = WPP_GLOBAL_Control;
      v12 = v34;
      goto LABEL_12;
    }
    if ( v26 < 0 )
      goto LABEL_44;
    v7 = v31;
    CurrentImpersonationLevel = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
    v19 = ProviderSubSystem_Common_Globals::SetCloaking(v7, v28, CurrentImpersonationLevel);
    v20 = 1;
    if ( v19 < 0 )
      goto LABEL_43;
    v19 = CoImpersonateClient();
    if ( v19 < 0 )
    {
      v19 = -2147217405;
LABEL_43:
      ProviderSubSystem_Common_Globals::RevertProxyState(
        (CInterceptor_IWbemSyncProvider *)((char *)this + 440),
        0,
        v31,
        v11);
      if ( v19 != -2147217406 )
      {
LABEL_44:
        v12 = v34;
        ProviderSubSystem_Common_Globals::EndImpersonation(ppInterface, v32, v34);
        goto LABEL_30;
      }
LABEL_5:
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v8);
      goto LABEL_23;
    }
  }
  if ( v19 == -2147217406 )
    goto LABEL_5;
  v12 = v34;
LABEL_30:
  if ( v19 < 0 )
  {
    v29 = GetMemLogObject();
    CMemoryLog::Write(v29, v19);
  }
  v6 = WPP_GLOBAL_Control;
LABEL_12:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 && *((_BYTE *)v6 + 25) >= 2u )
    WPP_SF_d(v6[2], 71, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, (unsigned int)v19);
  if ( v19 < 0 )
  {
    v8 = v19;
    goto LABEL_5;
  }
  v21 = CInterceptor_IWbemSyncProvider::Helper_PutInstanceAsync(
          this,
          v20,
          v35,
          v36,
          v37,
          a5,
          (struct IWbemServices *)v7);
  v22 = v31;
  v8 = v21;
  v23 = v32;
  v24 = ppInterface;
  CoRevertToSelf();
  if ( v22 )
    ProviderSubSystem_Common_Globals::RevertProxyState(
      (CInterceptor_IWbemSyncProvider *)((char *)this + 440),
      0,
      v22,
      v11);
  if ( *(_DWORD *)(*((_QWORD *)this + 75) + 1680LL) != 1
    && *(_DWORD *)(*((_QWORD *)this + 75) + 1680LL) != 5
    && *(_DWORD *)(*((_QWORD *)this + 75) + 1680LL) != 7
    && *(_DWORD *)(*((_QWORD *)this + 75) + 1680LL) != 8
    && *(_DWORD *)(*((_QWORD *)this + 75) + 1680LL) != 11
    && (unsigned int)(*(_DWORD *)(*((_QWORD *)this + 75) + 1680LL) - 12) >= 2 )
  {
    ProviderSubSystem_Common_Globals::EndImpersonation(v24, v23, v12);
  }
  if ( v8 < 0 )
    goto LABEL_5;
LABEL_23:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      105,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (unsigned int)v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140021dc0  mov     [rsp-40h+arg_18], r9
0x140021dc5  mov     [rsp-40h+arg_10], r8d
0x140021dca  mov     [rsp-40h+arg_8], rdx
0x140021dcf  push    rbp
0x140021dd0  push    rbx
0x140021dd1  push    rsi
0x140021dd2  push    rdi
0x140021dd3  push    r12
0x140021dd5  push    r13
0x140021dd7  push    r14
0x140021dd9  push    r15
0x140021ddb  mov     rbp, rsp
0x140021dde  sub     rsp, 68h
0x140021de2  mov     rax, r9
0x140021de5  mov     rsi, rcx
0x140021de8  mov     r9, rdx
0x140021deb  mov     r10, cs:WPP_GLOBAL_Control
0x140021df2  lea     rcx, WPP_GLOBAL_Control
0x140021df9  cmp     r10, rcx
0x140021dfc  jz      short loc_140021E09
0x140021dfe  test    byte ptr [r10+1Ch], 4
0x140021e03  jnz     loc_140021F8B
0x140021e09  mov     r15, [rsi+148h]
0x140021e10  xor     edx, edx
0x140021e12  mov     edi, 80041024h
0x140021e17  test    r15, r15
0x140021e1a  jz      short loc_140021E2B
0x140021e1c  mov     rcx, [rsi+258h]
0x140021e23  cmp     [rcx+7E4h], edx
0x140021e29  jnz     short loc_140021E41
0x140021e2b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140021e31  mov     rcx, rax
0x140021e34  mov     edx, edi
0x140021e36  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140021e3c  jmp     loc_140021F1F
0x140021e41  mov     [rbp+var_20], rdx
0x140021e45  mov     r12d, edx
0x140021e48  mov     [rbp+ppInterface], rdx
0x140021e4c  mov     r13d, edx
0x140021e4f  mov     [rbp+var_18], rdx
0x140021e53  mov     ecx, [rcx+690h]
0x140021e59  mov     [rbp+var_28], edx
0x140021e5c  mov     [rbp+arg_0], edx
0x140021e5f  sub     ecx, 1
0x140021e62  jz      short loc_140021E7C
0x140021e64  sub     ecx, 4
0x140021e67  jz      short loc_140021E7C
0x140021e69  sub     ecx, 2
0x140021e6c  jz      short loc_140021E7C
0x140021e6e  sub     ecx, 1
0x140021e71  jz      short loc_140021E7C
0x140021e73  sub     ecx, 3
0x140021e76  jnz     loc_140021FCA
0x140021e7c  mov     ebx, edx
0x140021e7e  mov     r14d, edx
0x140021e81  lea     rax, WPP_GLOBAL_Control
0x140021e88  cmp     r10, rax
0x140021e8b  jz      short loc_140021E98
0x140021e8d  test    byte ptr [r10+1Ch], 4
0x140021e92  jnz     loc_1400220DA
0x140021e98  test    ebx, ebx
0x140021e9a  js      loc_140022142
0x140021ea0  mov     rax, [rbp+arg_20]
0x140021ea4  mov     edx, r14d; int
0x140021ea7  mov     r9d, [rbp+arg_10]; int
0x140021eab  mov     rcx, rsi; this
0x140021eae  mov     r8, [rbp+arg_8]; struct IWbemClassObject *
0x140021eb2  mov     [rsp+68h+var_38], r15; struct IWbemServices *
0x140021eb7  mov     [rsp+68h+var_40], rax; struct IWbemObjectSink *
0x140021ebc  mov     rax, [rbp+arg_18]
0x140021ec0  mov     [rsp+68h+var_48], rax; struct IWbemContext *
0x140021ec5  call    ?Helper_PutInstanceAsync@CInterceptor_IWbemSyncProvider@@AEAAJHPEAUIWbemClassObject@@JPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAUIWbemServices@@@Z; CInterceptor_IWbemSyncProvider::Helper_PutInstanceAsync(int,IWbemClassObject *,long,IWbemContext *,IWbemObjectSink *,IWbemServices *)
0x140021eca  mov     rbx, [rbp+var_20]
0x140021ece  mov     edi, eax
0x140021ed0  mov     r14, [rbp+var_18]
0x140021ed4  mov     r15, [rbp+ppInterface]
0x140021ed8  call    cs:__imp_CoRevertToSelf
0x140021ede  test    rbx, rbx
0x140021ee1  jnz     loc_140022102
0x140021ee7  mov     rcx, [rsi+258h]
0x140021eee  mov     r9d, [rcx+690h]
0x140021ef5  sub     r9d, 1
0x140021ef9  jz      short loc_140021F17
0x140021efb  sub     r9d, 4
0x140021eff  jz      short loc_140021F17
0x140021f01  sub     r9d, 2
0x140021f05  jz      short loc_140021F17
0x140021f07  sub     r9d, 1
0x140021f0b  jz      short loc_140021F17
0x140021f0d  sub     r9d, 3
0x140021f11  jnz     loc_14002211B
0x140021f17  test    edi, edi
0x140021f19  js      loc_140021E2B
0x140021f1f  mov     rcx, cs:WPP_GLOBAL_Control
0x140021f26  lea     rax, WPP_GLOBAL_Control
0x140021f2d  cmp     rcx, rax
0x140021f30  jnz     short loc_140021F45
0x140021f32  mov     eax, edi
0x140021f34  add     rsp, 68h
0x140021f38  pop     r15
0x140021f3a  pop     r14
0x140021f3c  pop     r13
0x140021f3e  pop     r12
0x140021f40  pop     rdi
0x140021f41  pop     rsi
0x140021f42  pop     rbx
0x140021f43  pop     rbp
0x140021f44  retn
0x140021f45  test    byte ptr [rcx+1Ch], 4
0x140021f49  jz      short loc_140021F32
0x140021f4b  cmp     byte ptr [rcx+19h], 2
0x140021f4f  jb      short loc_140021F32
0x140021f51  mov     rcx, [rcx+10h]
0x140021f55  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x140021f5c  mov     edx, 69h ; 'i'
0x140021f61  mov     r9d, edi
0x140021f64  call    WPP_SF_d
0x140021f69  jmp     short loc_140021F32
0x140021f6b  cmp     ebx, edi
0x140021f6d  jz      loc_140021E2B
0x140021f73  mov     r13d, [rbp+arg_0]
0x140021f77  test    ebx, ebx
0x140021f79  js      loc_1400220C4
0x140021f7f  mov     r10, cs:WPP_GLOBAL_Control
0x140021f86  jmp     loc_140021E81
0x140021f8b  cmp     byte ptr [r10+19h], 5
0x140021f90  jb      loc_140021E09
0x140021f96  mov     rcx, [rbp+arg_20]
0x140021f9a  mov     edx, 68h ; 'h'
0x140021f9f  mov     [rsp+68h+var_38], rcx
0x140021fa4  mov     rcx, [r10+10h]
0x140021fa8  mov     [rsp+68h+var_40], rax
0x140021fad  mov     dword ptr [rsp+68h+var_48], r8d
0x140021fb2  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x140021fb9  call    WPP_SF_qdqq
0x140021fbe  mov     r10, cs:WPP_GLOBAL_Control
0x140021fc5  jmp     loc_140021E09
0x140021fca  sub     ecx, 1
0x140021fcd  jz      loc_140021E7C
0x140021fd3  cmp     ecx, 1
0x140021fd6  jz      loc_140021E7C
0x140021fdc  mov     r14d, edx
0x140021fdf  lea     r8, [rbp+arg_0]; int *
0x140021fe3  mov     r15, rdx
0x140021fe6  lea     rcx, [rbp+ppInterface]; ppInterface
0x140021fea  lea     rdx, [rbp+var_18]; struct IServerSecurity **
0x140021fee  xor     r9d, r9d; unsigned int *
0x140021ff1  call    ?BeginImpersonation@ProviderSubSystem_Common_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAHPEAK@Z; ProviderSubSystem_Common_Globals::BeginImpersonation(IUnknown * &,IServerSecurity * &,int &,ulong *)
0x140021ff6  mov     ebx, eax
0x140021ff8  mov     edi, 80041002h
0x140021ffd  test    eax, eax
0x140021fff  js      loc_140021F6B
0x140022005  mov     r9, [rsi+148h]; struct IUnknown *
0x14002200c  lea     rax, [rbp+var_28]
0x140022010  mov     [rsp+68h+var_40], rax; int *
0x140022015  lea     r13, [rsi+1B8h]
0x14002201c  lea     rax, [rbp+var_20]
0x140022020  xor     edx, edx; unsigned int
0x140022022  lea     r8, IID_IWbemServices; struct _GUID *
0x140022029  mov     [rsp+68h+var_48], rax; struct IUnknown **
0x14002202e  mov     rcx, r13; struct ProxyContainer *
0x140022031  call    ?SetProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KAEBU_GUID@@PEAUIUnknown@@AEAPEAU4@AEAH@Z; ProviderSubSystem_Common_Globals::SetProxyState(ProxyContainer &,ulong,_GUID const &,IUnknown *,IUnknown * &,int &)
0x140022036  mov     r12d, [rbp+var_28]
0x14002203a  mov     ebx, eax
0x14002203c  cmp     eax, edi
0x14002203e  jnz     short loc_140022059
0x140022040  mov     r15, [rsi+148h]
0x140022047  xor     ebx, ebx
0x140022049  mov     r10, cs:WPP_GLOBAL_Control
0x140022050  mov     r13d, [rbp+arg_0]
0x140022054  jmp     loc_140021E81
0x140022059  test    eax, eax
0x14002205b  js      short loc_1400220AB
0x14002205d  mov     r15, [rbp+var_20]
0x140022061  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x140022066  mov     r8d, eax; unsigned int
0x140022069  mov     rcx, r15; struct IUnknown *
0x14002206c  call    ?SetCloaking@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@KK@Z; ProviderSubSystem_Common_Globals::SetCloaking(IUnknown *,ulong,ulong)
0x140022071  mov     ebx, eax
0x140022073  mov     r14d, 1
0x140022079  test    eax, eax
0x14002207b  js      short loc_140022092
0x14002207d  call    cs:__imp_CoImpersonateClient
0x140022083  mov     ebx, eax
0x140022085  test    eax, eax
0x140022087  jns     loc_140021F6B
0x14002208d  mov     ebx, 80041003h
0x140022092  mov     r8, [rbp+var_20]; struct IUnknown *
0x140022096  mov     r9d, r12d; int
0x140022099  xor     edx, edx; unsigned int
0x14002209b  mov     rcx, r13; struct ProxyContainer *
0x14002209e  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x1400220a3  cmp     ebx, edi
0x1400220a5  jz      loc_140021E2B
0x1400220ab  mov     r13d, [rbp+arg_0]
0x1400220af  mov     r8d, r13d; int
0x1400220b2  mov     rdx, [rbp+var_18]; struct IServerSecurity *
0x1400220b6  mov     rcx, [rbp+ppInterface]; struct IUnknown *
0x1400220ba  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x1400220bf  jmp     loc_140021F77
0x1400220c4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400220ca  mov     rcx, rax
0x1400220cd  mov     edx, ebx
0x1400220cf  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400220d5  jmp     loc_140021F7F
0x1400220da  cmp     byte ptr [r10+19h], 2
0x1400220df  jb      loc_140021E98
0x1400220e5  mov     rcx, [r10+10h]
0x1400220e9  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x1400220f0  mov     edx, 47h ; 'G'
0x1400220f5  mov     r9d, ebx
0x1400220f8  call    WPP_SF_d
0x1400220fd  jmp     loc_140021E98
0x140022102  lea     rcx, [rsi+1B8h]; struct ProxyContainer *
0x140022109  mov     r9d, r12d; int
0x14002210c  mov     r8, rbx; struct IUnknown *
0x14002210f  xor     edx, edx; unsigned int
0x140022111  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x140022116  jmp     loc_140021EE7
0x14002211b  sub     r9d, 1
0x14002211f  jz      loc_140021F17
0x140022125  cmp     r9d, 1
0x140022129  jz      loc_140021F17
0x14002212f  mov     r8d, r13d; int
0x140022132  mov     rdx, r14; struct IServerSecurity *
0x140022135  mov     rcx, r15; struct IUnknown *
0x140022138  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x14002213d  jmp     loc_140021F17
0x140022142  mov     edi, ebx
0x140022144  jmp     loc_140021E2B
```
