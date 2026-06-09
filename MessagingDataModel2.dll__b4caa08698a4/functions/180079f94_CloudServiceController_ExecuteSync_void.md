# CloudServiceController::_ExecuteSync(void)

- ea: `0x180079f94`
- end: `0x18007a594`
- name: `?_ExecuteSync@CloudServiceController@@AEAAJXZ`
- size: `1536`
- prototype: `__int64 __fastcall(CloudServiceController *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task`

## callers

- `0x18007d6e0`

## callees

- `0x1800016a0`
- `0x180001cc4`
- `0x180002d6c`
- `0x180015050`
- `0x180017a70`
- `0x180046c98`
- `0x180046fbc`
- `0x1800774d0`
- `0x180079f94`
- `0x18007b578`
- `0x18007cc30`
- `0x18007d07c`
- `0x18007ec50`
- `0x180089fa8`
- `0x1800c6902`
- `0x1800c6940`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007a03b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007a053`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007a03b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007a053`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18007a061`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18007a061`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18007a044`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18007a044`
- `UserDataPlatformHelperUtil!SetThreadIOPriority` at `0x18007a234`
- `UserDataPlatformHelperUtil!SetThreadIOPriority` at `0x18007a4bc`
- `UserDataPlatformHelperUtil!SetThreadIOPriority` at `0x18007a56b`
- `UserDataPlatformHelperUtil!SetThreadIOPriority` at `0x18007a234`
- `UserDataPlatformHelperUtil!SetThreadIOPriority` at `0x18007a4bc`
- `UserDataPlatformHelperUtil!SetThreadIOPriority` at `0x18007a56b`

## string_xrefs

- `0x18007a547`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007a0bc`: `Process first task in queue`
- `0x180079fd0`: `CloudServiceController::_ExecuteSync`
- `0x18007a156`: `Sync CloudServicePolicyManager approved this sync task.`
- `0x18007a4e4`: `Sync CloudServicePolicyManager dennied this sync request, return gracefully.`
- `0x18007a3a3`: `SignIn task failed due to authentication failure.`
- `0x18007a1bc`: `Task finished successfully, pop it from queue.`
- `0x18007a3ed`: `Task failed due to authentication failure, schedule signin task and retry.`
- `0x18007a2a3`: `Task failed, return error and wait for retry`

## pseudocode

```c
__int64 __fastcall CloudServiceController::_ExecuteSync(CloudServiceController *this)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  HANDLE CurrentThread; // rax
  HANDLE v6; // rax
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rsi
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  CloudServicePolicyManager *v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  int v17; // eax
  int v18; // r14d
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  int v22; // eax
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  unsigned int v27; // ebx
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  __int16 *v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // r9
  int v38; // eax
  __int64 v39; // rcx
  __int64 v40; // r8
  __int64 v41; // r9
  int v42; // eax
  __int64 v43; // [rsp+20h] [rbp-E0h]
  __int64 v44; // [rsp+20h] [rbp-E0h]
  __int64 v45; // [rsp+20h] [rbp-E0h]
  __int64 v46; // [rsp+20h] [rbp-E0h]
  __int64 v47; // [rsp+20h] [rbp-E0h]
  int v48; // [rsp+40h] [rbp-C0h] BYREF
  const OLECHAR *v49; // [rsp+48h] [rbp-B8h] BYREF
  const OLECHAR *v50; // [rsp+50h] [rbp-B0h] BYREF
  const OLECHAR *v51; // [rsp+58h] [rbp-A8h] BYREF
  enum _PRIORITY_HINT v52; // [rsp+60h] [rbp-A0h] BYREF
  int v53; // [rsp+64h] [rbp-9Ch]
  unsigned __int16 v54[256]; // [rsp+70h] [rbp-90h] BYREF

  StringCchPrintfW(v54, 0x100u, L"%S(%d):%s", "CloudServiceController::_ExecuteSync", 446, L"Enter");
  if ( (unsigned int)dword_1800FD5F0 > 5 )
  {
    v51 = v54;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      v2,
      (int)&word_1800EFF36,
      v3,
      v4,
      &v51);
  }
  CloudServiceController::_SetSyncState(this, 2);
  HIDWORD(v51) = 0;
  CurrentThread = GetCurrentThread();
  LODWORD(v51) = GetThreadPriority(CurrentThread);
  if ( (_DWORD)v51 != -2 )
  {
    v6 = GetCurrentThread();
    HIDWORD(v51) = SetThreadPriority(v6, -2);
  }
  v53 = 0;
  v7 = auto_iopriority::ChangePriority((auto_iopriority *)&v52, IoPriorityHintLow);
  v8 = v7;
  if ( v7 >= 0 )
  {
    if ( !*((_QWORD *)this + 15) )
    {
LABEL_18:
      if ( v53 )
      {
        v53 = 0;
        v22 = SetThreadIOPriority(v52, 0);
        if ( v22 < 0 )
          Log_HREvent_21(v22);
      }
      v8 = 0;
      goto LABEL_22;
    }
    while ( 1 )
    {
      v9 = *((_QWORD *)this + 13);
      memset_0(v54, 0, sizeof(v54));
      LODWORD(v43) = 459;
      if ( (int)StringCchPrintfW(
                  v54,
                  0x100u,
                  L"%S(%d):%s",
                  "CloudServiceController::_ExecuteSync",
                  v43,
                  L"Process first task in queue") >= 0
        && (unsigned int)dword_1800FD5F0 > 4 )
      {
        v48 = *(_DWORD *)(v9 + 16);
        v50 = v54;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v10,
          (unsigned int)&byte_1800EFEEF,
          v11,
          v12,
          (__int64)&v50,
          (__int64)&v48);
      }
      v13 = (CloudServicePolicyManager *)*((_QWORD *)this + 12);
      v48 = 0;
      v7 = CloudServicePolicyManager::RequestToken(v13, &v48);
      v8 = v7;
      if ( v7 < 0 )
        goto LABEL_47;
      if ( !v48 )
      {
        LODWORD(v44) = 465;
        StringCchPrintfW(
          v54,
          0x100u,
          L"%S(%d):%s",
          "CloudServiceController::_ExecuteSync",
          v44,
          L"Sync CloudServicePolicyManager dennied this sync request, return gracefully.");
        if ( (unsigned int)dword_1800FD5F0 > 3 )
        {
          v49 = v54;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v39,
            (int)&unk_1800EFE78,
            v40,
            v41,
            &v49);
        }
        CloudServiceController::_SetSyncState(this, 0);
        goto LABEL_18;
      }
      LODWORD(v44) = 471;
      StringCchPrintfW(
        v54,
        0x100u,
        L"%S(%d):%s",
        "CloudServiceController::_ExecuteSync",
        v44,
        L"Sync CloudServicePolicyManager approved this sync task.");
      if ( (unsigned int)dword_1800FD5F0 > 4 )
      {
        v50 = v54;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          v14,
          (int)byte_1800EFEB5,
          v15,
          v16,
          &v50);
      }
      v17 = CloudServiceController::_ProcessSingleTask(this, *(unsigned int *)(v9 + 16));
      v18 = v17;
      if ( v17 < 0 )
        break;
      LODWORD(v45) = 476;
      StringCchPrintfW(
        v54,
        0x100u,
        L"%S(%d):%s",
        "CloudServiceController::_ExecuteSync",
        v45,
        L"Task finished successfully, pop it from queue.");
      if ( (unsigned int)dword_1800FD5F0 > 4 )
      {
        v50 = v54;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          v19,
          (int)byte_1800EFE03,
          v20,
          v21,
          &v50);
      }
      utl::list<enum MessagingCloudServiceTaskType,utl::allocator<enum MessagingCloudServiceTaskType>>::pop_front((char *)this + 104);
      if ( !*((_QWORD *)this + 15) )
        goto LABEL_18;
    }
    if ( ((v17 + 2145844847) & 0xFFFFFFFD) == 0 )
    {
      if ( *(_DWORD *)(v9 + 16) == 8 )
      {
        LODWORD(v45) = 483;
        StringCchPrintfW(
          v54,
          0x100u,
          L"%S(%d):%s",
          "CloudServiceController::_ExecuteSync",
          v45,
          L"SignIn task failed due to authentication failure.");
        if ( (unsigned int)dword_1800FD5F0 > 2 )
        {
          v49 = v54;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v32,
            (int)byte_1800EFE3D,
            v33,
            v34,
            &v49);
        }
      }
      else
      {
        LODWORD(v45) = 487;
        StringCchPrintfW(
          v54,
          0x100u,
          L"%S(%d):%s",
          "CloudServiceController::_ExecuteSync",
          v45,
          L"Task failed due to authentication failure, schedule signin task and retry.");
        if ( (unsigned int)dword_1800FD5F0 > 3 )
        {
          v49 = v54;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v35,
            (int)byte_1800EFD89,
            v36,
            v37,
            &v49);
        }
        v7 = CloudServiceController::_ScheduleTask(this, 8);
        v8 = v7;
        if ( v7 < 0 )
          goto LABEL_47;
      }
      LODWORD(v47) = 491;
      StringCchPrintfW(
        v54,
        0x100u,
        L"%S(%d):%s",
        "CloudServiceController::_ExecuteSync",
        v47,
        L"throw out failed HR to trigger retry logic");
      if ( (unsigned int)dword_1800FD5F0 > 3 )
      {
        v31 = &word_1800EFDC6;
LABEL_39:
        v49 = v54;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          v28,
          (int)v31,
          v29,
          v30,
          &v49);
      }
LABEL_40:
      if ( v53 )
      {
        v53 = 0;
        v38 = SetThreadIOPriority(v52, 0);
        if ( v38 < 0 )
          Log_HREvent_21(v38);
      }
      v8 = v18;
      goto LABEL_22;
    }
    memset_0(v54, 0, sizeof(v54));
    LODWORD(v45) = 499;
    if ( (int)StringCchPrintfW(
                v54,
                0x100u,
                L"%S(%d):%s",
                "CloudServiceController::_ExecuteSync",
                v45,
                L"Task failed, return error and wait for retry") >= 0
      && (unsigned int)dword_1800FD5F0 > 3 )
    {
      v48 = *(_DWORD *)(v9 + 16);
      v49 = v54;
      LODWORD(v50) = v18;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v24,
        (unsigned int)word_1800EFCFA,
        v25,
        v26,
        (__int64)&v49,
        (__int64)&v50,
        (__int64)&v48);
    }
    v27 = *(_DWORD *)(v9 + 16);
    if ( v27 == 8
      || (utl::list<enum MessagingCloudServiceTaskType,utl::allocator<enum MessagingCloudServiceTaskType>>::pop_front((char *)this + 104),
          v7 = CloudServiceController::_ScheduleTask(this, v27),
          v8 = v7,
          v7 >= 0) )
    {
      LODWORD(v46) = 510;
      StringCchPrintfW(
        v54,
        0x100u,
        L"%S(%d):%s",
        "CloudServiceController::_ExecuteSync",
        v46,
        L"throw out failed HR to trigger retry logic");
      if ( (unsigned int)dword_1800FD5F0 > 3 )
      {
        v31 = (__int16 *)&dword_1800EFD4C;
        goto LABEL_39;
      }
      goto LABEL_40;
    }
  }
LABEL_47:
  Log_HREvent_58(v7);
  if ( v53 )
  {
    v53 = 0;
    v42 = SetThreadIOPriority(v52, 0);
    if ( v42 < 0 )
      Log_HREvent_21(v42);
  }
LABEL_22:
  auto_threadpriority::Reset((auto_threadpriority *)&v51);
  return v8;
}

```

## disassembly

```asm
0x180079f94  push    rbp
0x180079f96  push    rbx
0x180079f97  push    rsi
0x180079f98  push    rdi
0x180079f99  push    r12
0x180079f9b  push    r13
0x180079f9d  push    r14
0x180079f9f  push    r15
0x180079fa1  lea     rbp, [rsp-188h]
0x180079fa9  sub     rsp, 288h
0x180079fb0  mov     rax, cs:__security_cookie
0x180079fb7  xor     rax, rsp
0x180079fba  mov     [rbp+1C0h+var_50], rax
0x180079fc1  lea     rax, aEnter; "Enter"
0x180079fc8  mov     rdi, rcx
0x180079fcb  mov     [rsp+2C0h+var_298], rax
0x180079fd0  lea     r13, aCloudserviceco_5; "CloudServiceController::_ExecuteSync"
0x180079fd7  lea     r14, aSDS; "%S(%d):%s"
0x180079fde  mov     dword ptr [rsp+2C0h+var_2A0], 1BEh
0x180079fe6  mov     r9, r13
0x180079fe9  lea     rcx, [rsp+2C0h+var_250]; unsigned __int16 *
0x180079fee  mov     r8, r14; unsigned __int16 *
0x180079ff1  mov     edx, 100h; unsigned __int64
0x180079ff6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180079ffb  mov     eax, cs:dword_1800FD5F0
0x18007a001  cmp     eax, 5
0x18007a004  jbe     short loc_18007A026
0x18007a006  lea     rax, [rsp+2C0h+var_250]
0x18007a00b  mov     [rsp+2C0h+var_268], rax
0x18007a010  lea     rdx, word_1800EFF36
0x18007a017  lea     rax, [rsp+2C0h+var_268]
0x18007a01c  mov     [rsp+2C0h+var_2A0], rax
0x18007a021  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18007a026  mov     edx, 2
0x18007a02b  mov     rcx, rdi
0x18007a02e  call    ?_SetSyncState@CloudServiceController@@AEAAXW4SyncState@1@@Z; CloudServiceController::_SetSyncState(CloudServiceController::SyncState)
0x18007a033  xor     r12d, r12d
0x18007a036  mov     dword ptr [rsp+2C0h+var_268+4], r12d
0x18007a03b  call    cs:__imp_GetCurrentThread
0x18007a041  mov     rcx, rax; hThread
0x18007a044  call    cs:__imp_GetThreadPriority
0x18007a04a  mov     dword ptr [rsp+2C0h+var_268], eax
0x18007a04e  cmp     eax, 0FFFFFFFEh
0x18007a051  jz      short loc_18007A06B
0x18007a053  call    cs:__imp_GetCurrentThread
0x18007a059  mov     rcx, rax; hThread
0x18007a05c  lea     edx, [r12-2]; nPriority
0x18007a061  call    cs:__imp_SetThreadPriority
0x18007a067  mov     dword ptr [rsp+2C0h+var_268+4], eax
0x18007a06b  mov     esi, 1
0x18007a070  mov     [rsp+2C0h+var_25C], r12d
0x18007a075  mov     edx, esi; enum _PRIORITY_HINT
0x18007a077  lea     rcx, [rsp+2C0h+var_260]; this
0x18007a07c  call    ?ChangePriority@auto_iopriority@@QEAAJW4_PRIORITY_HINT@@@Z; auto_iopriority::ChangePriority(_PRIORITY_HINT)
0x18007a081  mov     ebx, eax
0x18007a083  test    eax, eax
0x18007a085  jns     short loc_18007A094
0x18007a087  mov     r9d, 1C5h
0x18007a08d  mov     edx, esi
0x18007a08f  jmp     loc_18007A547
0x18007a094  cmp     [rdi+78h], r12
0x18007a098  jbe     loc_18007A222
0x18007a09e  lea     r15, [rdi+68h]
0x18007a0a2  mov     ebx, 100h
0x18007a0a7  mov     rsi, [r15]
0x18007a0aa  lea     rcx, [rsp+2C0h+var_250]; void *
0x18007a0af  xor     edx, edx; Val
0x18007a0b1  mov     r8d, 200h; Size
0x18007a0b7  call    memset_0
0x18007a0bc  lea     rax, aProcessFirstTa; "Process first task in queue"
0x18007a0c3  mov     r9, r13
0x18007a0c6  mov     [rsp+2C0h+var_298], rax
0x18007a0cb  lea     rcx, [rsp+2C0h+var_250]; unsigned __int16 *
0x18007a0d0  mov     r8, r14; unsigned __int16 *
0x18007a0d3  mov     dword ptr [rsp+2C0h+var_2A0], 1CBh
0x18007a0db  mov     rdx, rbx; unsigned __int64
0x18007a0de  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007a0e3  test    eax, eax
0x18007a0e5  js      short loc_18007A123
0x18007a0e7  mov     eax, cs:dword_1800FD5F0
0x18007a0ed  cmp     eax, 4
0x18007a0f0  jbe     short loc_18007A123
0x18007a0f2  mov     eax, [rsi+10h]
0x18007a0f5  lea     rdx, byte_1800EFEEF
0x18007a0fc  mov     [rsp+2C0h+var_280], eax
0x18007a100  lea     rax, [rsp+2C0h+var_250]
0x18007a105  mov     [rsp+2C0h+var_270], rax
0x18007a10a  lea     rax, [rsp+2C0h+var_280]
0x18007a10f  mov     [rsp+2C0h+var_298], rax
0x18007a114  lea     rax, [rsp+2C0h+var_270]
0x18007a119  mov     [rsp+2C0h+var_2A0], rax
0x18007a11e  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18007a123  mov     rcx, [rdi+60h]; this
0x18007a127  lea     rdx, [rsp+2C0h+var_280]; int *
0x18007a12c  mov     [rsp+2C0h+var_280], r12d
0x18007a131  call    ?RequestToken@CloudServicePolicyManager@@QEAAJPEAH@Z; CloudServicePolicyManager::RequestToken(int *)
0x18007a136  mov     ebx, eax
0x18007a138  test    eax, eax
0x18007a13a  js      loc_18007A53C
0x18007a140  lea     rcx, [rsp+2C0h+var_250]; unsigned __int16 *
0x18007a145  mov     r9, r13
0x18007a148  mov     r8, r14; unsigned __int16 *
0x18007a14b  cmp     [rsp+2C0h+var_280], r12d
0x18007a150  jz      loc_18007A4E4
0x18007a156  lea     rax, aSyncCloudservi_0; "Sync CloudServicePolicyManager approved"...
0x18007a15d  mov     ebx, 100h
0x18007a162  mov     [rsp+2C0h+var_298], rax
0x18007a167  mov     edx, ebx; unsigned __int64
0x18007a169  mov     dword ptr [rsp+2C0h+var_2A0], 1D7h
0x18007a171  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007a176  mov     eax, cs:dword_1800FD5F0
0x18007a17c  cmp     eax, 4
0x18007a17f  jbe     short loc_18007A1A1
0x18007a181  lea     rax, [rsp+2C0h+var_250]
0x18007a186  mov     [rsp+2C0h+var_270], rax
0x18007a18b  lea     rdx, byte_1800EFEB5
0x18007a192  lea     rax, [rsp+2C0h+var_270]
0x18007a197  mov     [rsp+2C0h+var_2A0], rax
0x18007a19c  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18007a1a1  mov     edx, [rsi+10h]
0x18007a1a4  mov     rcx, rdi
0x18007a1a7  call    ?_ProcessSingleTask@CloudServiceController@@AEAAJW4MessagingCloudServiceTaskType@@@Z; CloudServiceController::_ProcessSingleTask(MessagingCloudServiceTaskType)
0x18007a1ac  lea     rcx, [rsp+2C0h+var_250]; unsigned __int16 *
0x18007a1b1  mov     r14d, eax
0x18007a1b4  test    eax, eax
0x18007a1b6  js      loc_18007A286
0x18007a1bc  lea     rax, aTaskFinishedSu; "Task finished successfully, pop it from"...
0x18007a1c3  mov     r9, r13
0x18007a1c6  mov     [rsp+2C0h+var_298], rax
0x18007a1cb  lea     r14, aSDS; "%S(%d):%s"
0x18007a1d2  mov     r8, r14; unsigned __int16 *
0x18007a1d5  mov     dword ptr [rsp+2C0h+var_2A0], 1DCh
0x18007a1dd  mov     rdx, rbx; unsigned __int64
0x18007a1e0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007a1e5  mov     eax, cs:dword_1800FD5F0
0x18007a1eb  cmp     eax, 4
0x18007a1ee  jbe     short loc_18007A210
0x18007a1f0  lea     rax, [rsp+2C0h+var_250]
0x18007a1f5  mov     [rsp+2C0h+var_270], rax
0x18007a1fa  lea     rdx, byte_1800EFE03
0x18007a201  lea     rax, [rsp+2C0h+var_270]
0x18007a206  mov     [rsp+2C0h+var_2A0], rax
0x18007a20b  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18007a210  mov     rcx, r15
0x18007a213  call    ?pop_front@?$list@W4MessagingCloudServiceTaskType@@V?$allocator@W4MessagingCloudServiceTaskType@@@utl@@@utl@@QEAAXXZ; utl::list<MessagingCloudServiceTaskType,utl::allocator<MessagingCloudServiceTaskType>>::pop_front(void)
0x18007a218  cmp     [rdi+78h], r12
0x18007a21c  ja      loc_18007A0A7
0x18007a222  cmp     [rsp+2C0h+var_25C], r12d
0x18007a227  jz      short loc_18007A254
0x18007a229  mov     ecx, [rsp+2C0h+var_260]
0x18007a22d  xor     edx, edx
0x18007a22f  mov     [rsp+2C0h+var_25C], r12d
0x18007a234  call    cs:__imp_?SetThreadIOPriority@@YAJW4_PRIORITY_HINT@@PEAX@Z; SetThreadIOPriority(_PRIORITY_HINT,void *)
0x18007a23a  test    eax, eax
0x18007a23c  jns     short loc_18007A254
0x18007a23e  mov     r9d, 2DBh
0x18007a244  lea     r8, aOnecoreuapPriv_0; "onecoreuap\\private\\base\\inc\\UserDat"...
0x18007a24b  xor     edx, edx
0x18007a24d  mov     ecx, eax; int
0x18007a24f  call    Log_HREvent_21
0x18007a254  mov     ebx, r12d
0x18007a257  lea     rcx, [rsp+2C0h+var_268]; this
0x18007a25c  call    ?Reset@auto_threadpriority@@QEAAXXZ; auto_threadpriority::Reset(void)
0x18007a261  mov     eax, ebx
0x18007a263  mov     rcx, [rbp+1C0h+var_50]
0x18007a26a  xor     rcx, rsp; StackCookie
0x18007a26d  call    __security_check_cookie
0x18007a272  add     rsp, 288h
0x18007a279  pop     r15
0x18007a27b  pop     r14
0x18007a27d  pop     r13
0x18007a27f  pop     r12
0x18007a281  pop     rdi
0x18007a282  pop     rsi
0x18007a283  pop     rbx
0x18007a284  pop     rbp
0x18007a285  retn
0x18007a286  add     eax, 7FE6FE6Fh
0x18007a28b  test    eax, 0FFFFFFFDh
0x18007a290  jz      loc_18007A390
0x18007a296  xor     edx, edx; Val
0x18007a298  mov     r8d, 200h; Size
0x18007a29e  call    memset_0
0x18007a2a3  lea     rax, aTaskFailedRetu; "Task failed, return error and wait for "...
0x18007a2aa  mov     r9, r13
0x18007a2ad  mov     [rsp+2C0h+var_298], rax
0x18007a2b2  lea     r8, aSDS; "%S(%d):%s"
0x18007a2b9  mov     rdx, rbx; unsigned __int64
0x18007a2bc  mov     dword ptr [rsp+2C0h+var_2A0], 1F3h
0x18007a2c4  lea     rcx, [rsp+2C0h+var_250]; unsigned __int16 *
0x18007a2c9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007a2ce  test    eax, eax
0x18007a2d0  js      short loc_18007A31D
0x18007a2d2  mov     eax, cs:dword_1800FD5F0
0x18007a2d8  cmp     eax, 3
0x18007a2db  jbe     short loc_18007A31D
0x18007a2dd  mov     eax, [rsi+10h]
0x18007a2e0  lea     rdx, word_1800EFCFA
0x18007a2e7  mov     [rsp+2C0h+var_280], eax
0x18007a2eb  lea     rax, [rsp+2C0h+var_250]
0x18007a2f0  mov     [rsp+2C0h+var_278], rax
0x18007a2f5  lea     rax, [rsp+2C0h+var_280]
0x18007a2fa  mov     [rsp+2C0h+var_290], rax
0x18007a2ff  lea     rax, [rsp+2C0h+var_270]
0x18007a304  mov     [rsp+2C0h+var_298], rax
0x18007a309  lea     rax, [rsp+2C0h+var_278]
0x18007a30e  mov     [rsp+2C0h+var_2A0], rax
0x18007a313  mov     dword ptr [rsp+2C0h+var_270], r14d
0x18007a318  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18007a31d  mov     ebx, [rsi+10h]
0x18007a320  cmp     ebx, 8
0x18007a323  jz      short loc_18007A348
0x18007a325  mov     rcx, r15
0x18007a328  call    ?pop_front@?$list@W4MessagingCloudServiceTaskType@@V?$allocator@W4MessagingCloudServiceTaskType@@@utl@@@utl@@QEAAXXZ; utl::list<MessagingCloudServiceTaskType,utl::allocator<MessagingCloudServiceTaskType>>::pop_front(void)
0x18007a32d  mov     edx, ebx
0x18007a32f  mov     rcx, rdi
0x18007a332  call    ?_ScheduleTask@CloudServiceController@@AEAAJW4MessagingCloudServiceTaskType@@@Z; CloudServiceController::_ScheduleTask(MessagingCloudServiceTaskType)
0x18007a337  mov     ebx, eax
0x18007a339  test    eax, eax
0x18007a33b  jns     short loc_18007A348
0x18007a33d  mov     r9d, 1FAh
0x18007a343  jmp     loc_18007A542
0x18007a348  lea     rax, aThrowOutFailed; "throw out failed HR to trigger retry lo"...
0x18007a34f  mov     r9, r13
0x18007a352  mov     [rsp+2C0h+var_298], rax
0x18007a357  lea     r8, aSDS; "%S(%d):%s"
0x18007a35e  mov     edx, 100h; unsigned __int64
0x18007a363  mov     dword ptr [rsp+2C0h+var_2A0], 1FEh
0x18007a36b  lea     rcx, [rsp+2C0h+var_250]; unsigned __int16 *
0x18007a370  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007a375  mov     eax, cs:dword_1800FD5F0
0x18007a37b  cmp     eax, 3
0x18007a37e  jbe     loc_18007A4AA
0x18007a384  lea     rdx, dword_1800EFD4C
0x18007a38b  jmp     loc_18007A491
0x18007a390  cmp     dword ptr [rsi+10h], 8
0x18007a394  lea     r8, aSDS; "%S(%d):%s"
0x18007a39b  mov     r9, r13
0x18007a39e  mov     rdx, rbx; unsigned __int64
0x18007a3a1  jnz     short loc_18007A3ED
0x18007a3a3  lea     rax, aSigninTaskFail; "SignIn task failed due to authenticatio"...
0x18007a3aa  mov     [rsp+2C0h+var_298], rax
0x18007a3af  mov     dword ptr [rsp+2C0h+var_2A0], 1E3h
0x18007a3b7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007a3bc  mov     eax, cs:dword_1800FD5F0
0x18007a3c2  cmp     eax, 2
0x18007a3c5  jbe     loc_18007A454
0x18007a3cb  lea     rax, [rsp+2C0h+var_250]
0x18007a3d0  mov     [rsp+2C0h+var_278], rax
0x18007a3d5  lea     rdx, byte_1800EFE3D
0x18007a3dc  lea     rax, [rsp+2C0h+var_278]
0x18007a3e1  mov     [rsp+2C0h+var_2A0], rax
0x18007a3e6  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18007a3eb  jmp     short loc_18007A454
0x18007a3ed  lea     rax, aTaskFailedDueT; "Task failed due to authentication failu"...
0x18007a3f4  mov     [rsp+2C0h+var_298], rax
0x18007a3f9  mov     dword ptr [rsp+2C0h+var_2A0], 1E7h
0x18007a401  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007a406  mov     eax, cs:dword_1800FD5F0
0x18007a40c  cmp     eax, 3
0x18007a40f  jbe     short loc_18007A431
0x18007a411  lea     rax, [rsp+2C0h+var_250]
0x18007a416  mov     [rsp+2C0h+var_278], rax
0x18007a41b  lea     rdx, byte_1800EFD89
0x18007a422  lea     rax, [rsp+2C0h+var_278]
0x18007a427  mov     [rsp+2C0h+var_2A0], rax
0x18007a42c  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18007a431  mov     edx, 8
0x18007a436  mov     rcx, rdi
0x18007a439  call    ?_ScheduleTask@CloudServiceController@@AEAAJW4MessagingCloudServiceTaskType@@@Z; CloudServiceController::_ScheduleTask(MessagingCloudServiceTaskType)
0x18007a43e  mov     ebx, eax
0x18007a440  test    eax, eax
0x18007a442  jns     short loc_18007A44F
0x18007a444  mov     r9d, 1E8h
0x18007a44a  jmp     loc_18007A542
0x18007a44f  mov     ebx, 100h
0x18007a454  lea     rax, aThrowOutFailed; "throw out failed HR to trigger retry lo"...
0x18007a45b  mov     r9, r13
0x18007a45e  mov     [rsp+2C0h+var_298], rax
0x18007a463  lea     r8, aSDS; "%S(%d):%s"
0x18007a46a  mov     rdx, rbx; unsigned __int64
0x18007a46d  mov     dword ptr [rsp+2C0h+var_2A0], 1EBh
0x18007a475  lea     rcx, [rsp+2C0h+var_250]; unsigned __int16 *
0x18007a47a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007a47f  mov     eax, cs:dword_1800FD5F0
0x18007a485  cmp     eax, 3
0x18007a488  jbe     short loc_18007A4AA
0x18007a48a  lea     rdx, word_1800EFDC6
0x18007a491  lea     rax, [rsp+2C0h+var_250]
0x18007a496  mov     [rsp+2C0h+var_278], rax
0x18007a49b  lea     rax, [rsp+2C0h+var_278]
0x18007a4a0  mov     [rsp+2C0h+var_2A0], rax
0x18007a4a5  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18007a4aa  cmp     [rsp+2C0h+var_25C], r12d
0x18007a4af  jz      short loc_18007A4DC
0x18007a4b1  mov     ecx, [rsp+2C0h+var_260]
0x18007a4b5  xor     edx, edx
0x18007a4b7  mov     [rsp+2C0h+var_25C], r12d
0x18007a4bc  call    cs:__imp_?SetThreadIOPriority@@YAJW4_PRIORITY_HINT@@PEAX@Z; SetThreadIOPriority(_PRIORITY_HINT,void *)
0x18007a4c2  test    eax, eax
  ... truncated ...
```
