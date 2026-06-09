# CmsRegisterForContainerNotifications

- ea: `0x180009270`
- end: `0x18000946c`
- name: `CmsRegisterForContainerNotifications`
- size: `508`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting`

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
- `0x180009270`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x180009369`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x180009369`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800093ac`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800093ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000935e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000935e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009371`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009371`

## string_xrefs

- `0x180009328`: `onecore\base\gendrv\silos\clem\client\dll\CmClientHandles.h`
- `0x18000942e`: `onecore\base\gendrv\silos\clem\client\dll\CmClientHandles.h`
- `0x1800092a3`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsRegisterForContainerNotifications(_QWORD *a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rdx
  int v7; // ebx
  __int64 *v9; // rax
  __int64 *v10; // rsi
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rbx
  __int64 v14; // r15
  DWORD LastError; // edi
  int v16; // eax
  void *v17; // rbx
  int v18; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v20; // [rsp+70h] [rbp+8h] BYREF

  if ( !a1 )
  {
    v6 = 352;
LABEL_3:
    v7 = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)(unsigned int)v7,
      v18);
    return (unsigned int)v7;
  }
  if ( !a2 )
  {
    v6 = 353;
    goto LABEL_3;
  }
  if ( !a1[5] )
  {
    v9 = (__int64 *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v10 = v9;
    if ( !v9 )
    {
      v7 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x179,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\CmClientHandles.h",
        (const char *)0x8007000ELL,
        v18);
      goto LABEL_22;
    }
    v9[1] = 0;
    v9[2] = 0;
    *v9 = 0;
    v11 = Csl::OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>::Initialize(v9, a1 + 4, a2, a3);
    v7 = v11;
    if ( v11 < 0 )
    {
      v12 = 380;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\CmClientHandles.h",
        (const char *)(unsigned int)v11,
        v18);
      Csl::OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>::~OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>(v10);
      operator delete(v10, (const struct std::nothrow_t *)0x18);
LABEL_22:
      v6 = 366;
      goto LABEL_4;
    }
    v13 = *v10;
    v14 = v10[1];
    if ( v14 )
    {
      LastError = GetLastError();
      RtlUnsubscribeWnfStateChangeNotification(v14);
      SetLastError(LastError);
    }
    v18 = (int)v10;
    v10[1] = 0;
    v16 = RtlSubscribeWnfStateChangeNotification(
            v10 + 1,
            v13,
            0,
            Csl::OutOfProcNotificationSubscriber<_CMS_CONTAINER_NOTIFICATION,2>::OnWnfStateChange);
    if ( v16 < 0 )
    {
      v11 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x202,
              (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslNotification.h",
              (const char *)(unsigned int)v16,
              (int)v10);
      v7 = v11;
      if ( v11 < 0 )
      {
        v12 = 385;
        goto LABEL_11;
      }
    }
    v17 = (void *)a1[5];
    a1[5] = v10;
    if ( v17 )
    {
      Csl::OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>::~OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>(v17);
      operator delete(v17, (const struct std::nothrow_t *)0x18);
    }
  }
  v20 = a1[3];
  v7 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(
         CmsRpcClt_EnableContainerNotifications,
         &v20);
  if ( v7 < 0 )
  {
    v6 = 371;
    goto LABEL_4;
  }
  return 0;
}

```

## disassembly

```asm
0x180009270  mov     [rsp+arg_8], rbx
0x180009275  mov     [rsp+arg_10], rbp
0x18000927a  push    rsi
0x18000927b  push    rdi
0x18000927c  push    r13
0x18000927e  push    r14
0x180009280  push    r15
0x180009282  sub     rsp, 40h
0x180009286  mov     rdi, r8
0x180009289  mov     rbx, rdx
0x18000928c  mov     rbp, rcx
0x18000928f  test    rcx, rcx
0x180009292  jnz     short loc_1800092B9
0x180009294  mov     edx, 160h; void *
0x180009299  mov     ebx, 80070057h
0x18000929e  mov     rcx, [rsp+68h]; this
0x1800092a3  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x1800092aa  mov     r9d, ebx; char *
0x1800092ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800092b2  mov     eax, ebx
0x1800092b4  jmp     loc_180009453
0x1800092b9  test    rbx, rbx
0x1800092bc  jnz     short loc_1800092C5
0x1800092be  mov     edx, 161h
0x1800092c3  jmp     short loc_180009299
0x1800092c5  cmp     qword ptr [rcx+28h], 0
0x1800092ca  jnz     loc_1800093FF
0x1800092d0  mov     r13d, 18h
0x1800092d6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800092dd  mov     ecx, r13d; unsigned __int64
0x1800092e0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800092e5  mov     rsi, rax
0x1800092e8  test    rax, rax
0x1800092eb  jz      loc_180009429
0x1800092f1  mov     qword ptr [rax+8], 0
0x1800092f9  lea     rdx, [rbp+20h]
0x1800092fd  mov     qword ptr [rax+10h], 0
0x180009305  mov     r9, rdi
0x180009308  xor     eax, eax
0x18000930a  mov     r8, rbx
0x18000930d  mov     rcx, rsi
0x180009310  mov     [rsi], rax
0x180009313  call    ?Initialize@?$OutOfProcNotificationSubscriber@U_CMS_ACTIVITY_NOTIFICATION@@$01@Csl@@QEAAJAEBU_WNF_STATE_NAME@@P6AXPEAU_CMS_ACTIVITY_NOTIFICATION@@PEAX@Z2@Z; Csl::OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>::Initialize(_WNF_STATE_NAME const &,void (*)(_CMS_ACTIVITY_NOTIFICATION *,void *),void *)
0x180009318  mov     ebx, eax
0x18000931a  test    eax, eax
0x18000931c  jns     short loc_18000934F
0x18000931e  mov     edx, 17Ch; void *
0x180009323  mov     rcx, [rsp+68h]; this
0x180009328  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000932f  mov     r9d, eax; char *
0x180009332  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009337  mov     rcx, rsi
0x18000933a  call    ??1?$OutOfProcNotificationSubscriber@U_CMS_ACTIVITY_NOTIFICATION@@$01@Csl@@QEAA@XZ; Csl::OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>::~OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>(void)
0x18000933f  mov     rdx, r13; struct std::nothrow_t *
0x180009342  mov     rcx, rsi; void *
0x180009345  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000934a  jmp     loc_180009447
0x18000934f  mov     rbx, [rsi]
0x180009352  lea     r14, [rsi+8]
0x180009356  mov     r15, [r14]
0x180009359  test    r15, r15
0x18000935c  jz      short loc_180009377
0x18000935e  call    cs:__imp_GetLastError
0x180009364  mov     rcx, r15
0x180009367  mov     edi, eax
0x180009369  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x18000936f  mov     ecx, edi; dwErrCode
0x180009371  call    cs:__imp_SetLastError
0x180009377  mov     [rsp+68h+var_30], 0
0x18000937f  lea     r9, ?OnWnfStateChange@?$OutOfProcNotificationSubscriber@U_CMS_CONTAINER_NOTIFICATION@@$01@Csl@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; Csl::OutOfProcNotificationSubscriber<_CMS_CONTAINER_NOTIFICATION,2>::OnWnfStateChange(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180009386  mov     [rsp+68h+var_38], 0
0x18000938e  xor     r8d, r8d
0x180009391  mov     [rsp+68h+var_40], 0
0x18000939a  mov     rdx, rbx
0x18000939d  mov     rcx, r14
0x1800093a0  mov     qword ptr [rsp+68h+var_48], rsi; int
0x1800093a5  mov     qword ptr [r14], 0
0x1800093ac  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x1800093b2  test    eax, eax
0x1800093b4  jns     short loc_1800093DF
0x1800093b6  mov     rcx, [rsp+68h]; this
0x1800093bb  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1800093c2  mov     r9d, eax; char *
0x1800093c5  mov     edx, 202h; void *
0x1800093ca  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800093cf  mov     ebx, eax
0x1800093d1  test    eax, eax
0x1800093d3  jns     short loc_1800093DF
0x1800093d5  mov     edx, 181h
0x1800093da  jmp     loc_180009323
0x1800093df  mov     rbx, [rbp+28h]
0x1800093e3  mov     [rbp+28h], rsi
0x1800093e7  test    rbx, rbx
0x1800093ea  jz      short loc_1800093FF
0x1800093ec  mov     rcx, rbx
0x1800093ef  call    ??1?$OutOfProcNotificationSubscriber@U_CMS_ACTIVITY_NOTIFICATION@@$01@Csl@@QEAA@XZ; Csl::OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>::~OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>(void)
0x1800093f4  mov     rdx, r13; struct std::nothrow_t *
0x1800093f7  mov     rcx, rbx; void *
0x1800093fa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800093ff  mov     rax, [rbp+18h]
0x180009403  lea     rdx, [rsp+68h+arg_0]
0x180009408  lea     rcx, CmsRpcClt_EnableContainerNotifications
0x18000940f  mov     [rsp+68h+arg_0], rax
0x180009414  call    ??$InvokeStubFunction@P6AJPEAX@ZAEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAX@ZAEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(long (*)(void *),void * &)
0x180009419  mov     ebx, eax
0x18000941b  test    eax, eax
0x18000941d  jns     short loc_180009451
0x18000941f  mov     edx, 173h
0x180009424  jmp     loc_18000929E
0x180009429  mov     rcx, [rsp+68h]; this
0x18000942e  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180009435  mov     ebx, 8007000Eh
0x18000943a  mov     edx, 179h; void *
0x18000943f  mov     r9d, ebx; char *
0x180009442  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009447  mov     edx, 16Eh
0x18000944c  jmp     loc_18000929E
0x180009451  xor     eax, eax
0x180009453  lea     r11, [rsp+68h+var_28]
0x180009458  mov     rbx, [r11+38h]
0x18000945c  mov     rbp, [r11+40h]
0x180009460  mov     rsp, r11
0x180009463  pop     r15
0x180009465  pop     r14
0x180009467  pop     r13
0x180009469  pop     rdi
0x18000946a  pop     rsi
0x18000946b  retn
```
