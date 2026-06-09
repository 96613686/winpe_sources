# CmsStartActivityAsync

- ea: `0x1800095a0`
- end: `0x180009791`
- name: `CmsStartActivityAsync`
- size: `497`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000a660`

## callees

- `0x180001574`
- `0x180001944`
- `0x1800021dc`
- `0x180003bc4`
- `0x180005540`
- `0x1800066e4`
- `0x180006708`
- `0x1800095a0`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18000967e`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18000967e`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800096c1`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800096c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009673`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009673`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009686`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009686`

## string_xrefs

- `0x180009622`: `onecore\base\gendrv\silos\clem\client\dll\CmClientHandles.h`
- `0x180009740`: `onecore\base\gendrv\silos\clem\client\dll\CmClientHandles.h`
- `0x180009763`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsStartActivityAsync(_QWORD *a1, __int64 a2, __int64 a3)
{
  __int64 *v6; // rax
  __int64 *v7; // rsi
  int v8; // eax
  int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r15
  __int64 v13; // rbx
  DWORD LastError; // edi
  int v15; // eax
  void *v16; // rbx
  __int64 v17; // rdx
  int v19; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v21; // [rsp+70h] [rbp+8h] BYREF

  if ( !a1[3] )
  {
    v6 = (__int64 *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v7 = v6;
    if ( !v6 )
    {
      v9 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x206,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\CmClientHandles.h",
        (const char *)0x8007000ELL,
        v19);
      goto LABEL_16;
    }
    v6[1] = 0;
    v6[2] = 0;
    *v6 = 0;
    v8 = Csl::OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>::Initialize(v6, a1 + 2, a2, a3);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 521;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\CmClientHandles.h",
        (const char *)(unsigned int)v8,
        v19);
      Csl::OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>::~OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>(v7);
      operator delete(v7, (const struct std::nothrow_t *)0x18);
LABEL_16:
      v17 = 744;
      goto LABEL_17;
    }
    v11 = *(_QWORD *)(v7[2] + 8);
    *(_QWORD *)(v11 + 88) = Container::Manager::Common::CoalesceActivityNotificationQueue;
    *(_QWORD *)(v11 + 96) = 0;
    v12 = v7[1];
    v13 = *v7;
    if ( v12 )
    {
      LastError = GetLastError();
      RtlUnsubscribeWnfStateChangeNotification(v12);
      SetLastError(LastError);
    }
    v19 = (int)v7;
    v7[1] = 0;
    v15 = RtlSubscribeWnfStateChangeNotification(
            v7 + 1,
            v13,
            0,
            Csl::OutOfProcNotificationSubscriber<_CMS_CONTAINER_NOTIFICATION,2>::OnWnfStateChange);
    if ( v15 < 0 )
    {
      v8 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x202,
             (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslNotification.h",
             (const char *)(unsigned int)v15,
             (int)v7);
      v9 = v8;
      if ( v8 < 0 )
      {
        v10 = 532;
        goto LABEL_5;
      }
    }
    v16 = (void *)a1[3];
    a1[3] = v7;
    if ( v16 )
    {
      Csl::OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>::~OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>(v16);
      operator delete(v16, (const struct std::nothrow_t *)0x18);
    }
  }
  v21 = a1[1];
  v9 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(CmsRpcClt_StartActivityAsync, &v21);
  if ( v9 < 0 )
  {
    v17 = 748;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)(unsigned int)v9,
      v19);
    return (unsigned int)v9;
  }
  return 0;
}

```

## disassembly

```asm
0x1800095a0  mov     [rsp+arg_8], rbx
0x1800095a5  mov     [rsp+arg_10], rbp
0x1800095aa  push    rsi
0x1800095ab  push    rdi
0x1800095ac  push    r13
0x1800095ae  push    r14
0x1800095b0  push    r15
0x1800095b2  sub     rsp, 40h
0x1800095b6  cmp     qword ptr [rcx+18h], 0
0x1800095bb  mov     rbx, r8
0x1800095be  mov     rdi, rdx
0x1800095c1  mov     rbp, rcx
0x1800095c4  jnz     loc_180009714
0x1800095ca  mov     r13d, 18h
0x1800095d0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800095d7  mov     ecx, r13d; unsigned __int64
0x1800095da  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800095df  mov     rsi, rax
0x1800095e2  test    rax, rax
0x1800095e5  jz      loc_18000973B
0x1800095eb  mov     qword ptr [rax+8], 0
0x1800095f3  lea     rdx, [rbp+10h]
0x1800095f7  mov     qword ptr [rax+10h], 0
0x1800095ff  mov     r9, rbx
0x180009602  xor     eax, eax
0x180009604  mov     r8, rdi
0x180009607  mov     rcx, rsi
0x18000960a  mov     [rsi], rax
0x18000960d  call    ?Initialize@?$OutOfProcNotificationSubscriber@U_CMS_ACTIVITY_NOTIFICATION@@$01@Csl@@QEAAJAEBU_WNF_STATE_NAME@@P6AXPEAU_CMS_ACTIVITY_NOTIFICATION@@PEAX@Z2@Z; Csl::OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>::Initialize(_WNF_STATE_NAME const &,void (*)(_CMS_ACTIVITY_NOTIFICATION *,void *),void *)
0x180009612  mov     ebx, eax
0x180009614  test    eax, eax
0x180009616  jns     short loc_180009649
0x180009618  mov     edx, 209h; void *
0x18000961d  mov     rcx, [rsp+68h]; this
0x180009622  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180009629  mov     r9d, eax; char *
0x18000962c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009631  mov     rcx, rsi
0x180009634  call    ??1?$OutOfProcNotificationSubscriber@U_CMS_ACTIVITY_NOTIFICATION@@$01@Csl@@QEAA@XZ; Csl::OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>::~OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>(void)
0x180009639  mov     rdx, r13; struct std::nothrow_t *
0x18000963c  mov     rcx, rsi; void *
0x18000963f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009644  jmp     loc_180009759
0x180009649  mov     rax, [rsi+10h]
0x18000964d  lea     r14, [rsi+8]
0x180009651  mov     rcx, [rax+8]
0x180009655  lea     rax, ?CoalesceActivityNotificationQueue@Common@Manager@Container@@YA_NAEBU_CMS_ACTIVITY_NOTIFICATION@@AEAV?$BlockingBoundedQueue@U_CMS_ACTIVITY_NOTIFICATION@@$01@Csl@@PEAX@Z; Container::Manager::Common::CoalesceActivityNotificationQueue(_CMS_ACTIVITY_NOTIFICATION const &,Csl::BlockingBoundedQueue<_CMS_ACTIVITY_NOTIFICATION,2> &,void *)
0x18000965c  mov     [rcx+58h], rax
0x180009660  mov     qword ptr [rcx+60h], 0
0x180009668  mov     r15, [r14]
0x18000966b  mov     rbx, [rsi]
0x18000966e  test    r15, r15
0x180009671  jz      short loc_18000968C
0x180009673  call    cs:__imp_GetLastError
0x180009679  mov     rcx, r15
0x18000967c  mov     edi, eax
0x18000967e  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x180009684  mov     ecx, edi; dwErrCode
0x180009686  call    cs:__imp_SetLastError
0x18000968c  mov     [rsp+68h+var_30], 0
0x180009694  lea     r9, ?OnWnfStateChange@?$OutOfProcNotificationSubscriber@U_CMS_CONTAINER_NOTIFICATION@@$01@Csl@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; Csl::OutOfProcNotificationSubscriber<_CMS_CONTAINER_NOTIFICATION,2>::OnWnfStateChange(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18000969b  mov     [rsp+68h+var_38], 0
0x1800096a3  xor     r8d, r8d
0x1800096a6  mov     [rsp+68h+var_40], 0
0x1800096af  mov     rdx, rbx
0x1800096b2  mov     rcx, r14
0x1800096b5  mov     qword ptr [rsp+68h+var_48], rsi; int
0x1800096ba  mov     qword ptr [r14], 0
0x1800096c1  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x1800096c7  test    eax, eax
0x1800096c9  jns     short loc_1800096F4
0x1800096cb  mov     rcx, [rsp+68h]; this
0x1800096d0  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1800096d7  mov     r9d, eax; char *
0x1800096da  mov     edx, 202h; void *
0x1800096df  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800096e4  mov     ebx, eax
0x1800096e6  test    eax, eax
0x1800096e8  jns     short loc_1800096F4
0x1800096ea  mov     edx, 214h
0x1800096ef  jmp     loc_18000961D
0x1800096f4  mov     rbx, [rbp+18h]
0x1800096f8  mov     [rbp+18h], rsi
0x1800096fc  test    rbx, rbx
0x1800096ff  jz      short loc_180009714
0x180009701  mov     rcx, rbx
0x180009704  call    ??1?$OutOfProcNotificationSubscriber@U_CMS_ACTIVITY_NOTIFICATION@@$01@Csl@@QEAA@XZ; Csl::OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>::~OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>(void)
0x180009709  mov     rdx, r13; struct std::nothrow_t *
0x18000970c  mov     rcx, rbx; void *
0x18000970f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009714  mov     rax, [rbp+8]
0x180009718  lea     rdx, [rsp+68h+arg_0]
0x18000971d  lea     rcx, CmsRpcClt_StartActivityAsync
0x180009724  mov     [rsp+68h+arg_0], rax
0x180009729  call    ??$InvokeStubFunction@P6AJPEAX@ZAEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAX@ZAEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(long (*)(void *),void * &)
0x18000972e  mov     ebx, eax
0x180009730  test    eax, eax
0x180009732  jns     short loc_180009776
0x180009734  mov     edx, 2ECh
0x180009739  jmp     short loc_18000975E
0x18000973b  mov     rcx, [rsp+68h]; this
0x180009740  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180009747  mov     ebx, 8007000Eh
0x18000974c  mov     edx, 206h; void *
0x180009751  mov     r9d, ebx; char *
0x180009754  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009759  mov     edx, 2E8h; void *
0x18000975e  mov     rcx, [rsp+68h]; this
0x180009763  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000976a  mov     r9d, ebx; char *
0x18000976d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009772  mov     eax, ebx
0x180009774  jmp     short loc_180009778
0x180009776  xor     eax, eax
0x180009778  lea     r11, [rsp+68h+var_28]
0x18000977d  mov     rbx, [r11+38h]
0x180009781  mov     rbp, [r11+40h]
0x180009785  mov     rsp, r11
0x180009788  pop     r15
0x18000978a  pop     r14
0x18000978c  pop     r13
0x18000978e  pop     rdi
0x18000978f  pop     rsi
0x180009790  retn
```
