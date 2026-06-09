# CWSManEventSession::DeliverEndSubscription(CRequestContext *,_WSMAN_FAULT_OBJECT *)

- ea: `0x1800dacbc`
- end: `0x1800db0a7`
- name: `?DeliverEndSubscription@CWSManEventSession@@QEAAHPEAVCRequestContext@@PEAU_WSMAN_FAULT_OBJECT@@@Z`
- size: `1003`
- prototype: `__int64 __fastcall(CWSManEventSession *__hidden this, struct CRequestContext *, struct _WSMAN_FAULT_OBJECT *)`
- caller_count: `3`
- callee_count: `17`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800dac50`
- `0x180113cf0`
- `0x18017e290`

## callees

- `0x180005d10`
- `0x18002aee0`
- `0x18002dd20`
- `0x1800567e0`
- `0x18006a358`
- `0x18006a878`
- `0x1800976c4`
- `0x1800af33c`
- `0x1800dacbc`
- `0x1800db0b0`
- `0x1800fa540`
- `0x1800fe3b0`
- `0x180112380`
- `0x1801123a8`
- `0x18011a6d4`
- `0x1801297b8`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dae71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dae71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dae0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dae92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800daf5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db02e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dae0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dae92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800daf5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db02e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dae87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dae87`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800db016`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800db016`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dadee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dadee`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800dae02`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800dae02`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWSManEventSession::DeliverEndSubscription(
        CRemoteEventDeliveryOperation **this,
        struct CRequestContext *a2,
        struct _WSMAN_FAULT_OBJECT *a3)
{
  int v7; // esi
  HANDLE CurrentThread; // rax
  DWORD v9; // eax
  DWORD v10; // esi
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 LastError; // rsi
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  unsigned int v17; // eax
  __int64 v18; // rsi
  CWSManCriticalSection *v19; // rsi
  IOperation *v20; // rcx
  __int64 v21; // rdi
  unsigned int v22; // ebx
  void *TokenHandle; // [rsp+78h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
    WPP_SF_qqq(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, WPP_76a007a742ac3fc5c4c7211ea1cbc67d_Traceguids, this, a2, a3);
  if ( !a2 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmaneventsession.cpp", 1260, L"1260", 0x54Fu, 0);
    return 0;
  }
  if ( !a3 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmaneventsession.cpp", 1261, L"1261", 0x54Fu, a2);
    return 0;
  }
  TokenHandle = (void *)-1LL;
  v7 = CWSManEventSession::SetCloseState(this, a2);
  if ( !(*(unsigned int (__fastcall **)(struct CRequestContext *))(*(_QWORD *)a2 + 144LL))(a2) )
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmaneventsession.cpp", 1268, L"1268", 0x54Fu, 0);
  if ( v7 == 3 )
  {
    (*(void (__fastcall **)(struct CRequestContext *, __int64))(*(_QWORD *)a2 + 72LL))(a2, 2150858761LL);
    return 0;
  }
  CWSManEventSession::StopHeartbeatTimer((CWSManEventSession *)this);
  CWSManEventSession::StopLatencyTimer((CWSManEventSession *)this, 1);
  TokenHandle = (void *)-1LL;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
  {
    if ( (unsigned int)CSecurity::RevertToSelf() )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
        goto LABEL_31;
      v12 = 21;
      goto LABEL_30;
    }
    CloseHandle(TokenHandle);
    TokenHandle = (void *)-1LL;
LABEL_24:
    LastError = GetLastError();
    (*(void (__fastcall **)(struct CRequestContext *, __int64))(*(_QWORD *)a2 + 72LL))(a2, LastError);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
      goto LABEL_36;
    v15 = 88;
    v16 = (unsigned int)LastError;
    goto LABEL_35;
  }
  v9 = GetLastError();
  v10 = v9;
  if ( v9 != 1008 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids, v9);
    SetLastError(v10);
    goto LABEL_24;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
    goto LABEL_31;
  v12 = 19;
LABEL_30:
  WPP_SF_(v11[2], v12, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids);
LABEL_31:
  if ( (unsigned int)CRemoteEventDeliveryOperation::SendEndSubscriptionNotification(this[141], a2, a3) )
    goto LABEL_36;
  v17 = (*(__int64 (__fastcall **)(struct CRequestContext *))(*(_QWORD *)a2 + 152LL))(a2);
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
    goto LABEL_36;
  v15 = 89;
  v16 = v17;
LABEL_35:
  WPP_SF_d(v14[2], v15, WPP_76a007a742ac3fc5c4c7211ea1cbc67d_Traceguids, v16);
LABEL_36:
  if ( !(unsigned int)CSecurity::EndRevertToSelf(TokenHandle) )
  {
    v18 = GetLastError();
    (*(void (__fastcall **)(struct CRequestContext *, __int64))(*(_QWORD *)a2 + 72LL))(a2, v18);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        90,
        WPP_76a007a742ac3fc5c4c7211ea1cbc67d_Traceguids,
        (unsigned int)v18);
  }
  v19 = (CWSManCriticalSection *)(this + 197);
  CWSManCriticalSection::Acquire((CWSManCriticalSection *)(this + 197));
  v20 = this[142];
  if ( v20 && IOperation::AddRef(v20, 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, WPP_76a007a742ac3fc5c4c7211ea1cbc67d_Traceguids, this);
    if ( !QueueUserWorkItem(CWSManEventSession::CloseMasterOperationCallback, this[142], 0x10u) )
    {
      IOperation::Release(this[142], 0);
      v21 = GetLastError();
      (*(void (__fastcall **)(struct CRequestContext *, __int64))(*(_QWORD *)a2 + 72LL))(a2, v21);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          92,
          WPP_76a007a742ac3fc5c4c7211ea1cbc67d_Traceguids,
          (unsigned int)v21);
    }
  }
  v22 = (*(__int64 (__fastcall **)(struct CRequestContext *))(*(_QWORD *)a2 + 144LL))(a2);
  CWSManCriticalSection::Release(v19);
  return v22;
}

```

## disassembly

```asm
0x1800dacbc  mov     rax, rsp
0x1800dacbf  mov     [rax+8], rbx
0x1800dacc3  mov     [rax+18h], rbp
0x1800dacc7  push    rsi
0x1800dacc8  push    rdi
0x1800dacc9  push    r12
0x1800daccb  push    r13
0x1800daccd  push    r15
0x1800daccf  sub     rsp, 40h
0x1800dacd3  mov     rbp, r8
0x1800dacd6  mov     rbx, rdx
0x1800dacd9  mov     rdi, rcx
0x1800dacdc  lea     r15, WPP_GLOBAL_Control
0x1800dace3  lea     r12, WPP_76a007a742ac3fc5c4c7211ea1cbc67d_Traceguids
0x1800dacea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dacf1  cmp     rcx, r15
0x1800dacf4  jz      short loc_1800DAD1B
0x1800dacf6  test    dword ptr [rcx+1Ch], 10000h
0x1800dacfd  jz      short loc_1800DAD1B
0x1800dacff  mov     edx, 57h ; 'W'
0x1800dad04  mov     [rax-40h], r8
0x1800dad08  mov     [rax-48h], rbx
0x1800dad0c  mov     r9, rdi
0x1800dad0f  mov     r8, r12
0x1800dad12  mov     rcx, [rcx+10h]
0x1800dad16  call    WPP_SF_qqq
0x1800dad1b  test    rbx, rbx
0x1800dad1e  jnz     short loc_1800DAD4A
0x1800dad20  mov     [rsp+68h+var_48], rbx; struct IRequestContext *
0x1800dad25  lea     r8, a1260; "1260"
0x1800dad2c  mov     edx, 4ECh; unsigned int
0x1800dad31  mov     r9d, 54Fh; unsigned int
0x1800dad37  lea     rcx, aOnecoreAdminWm_104; "onecore\\admin\\wmi\\wmx\\client\\remot"...
0x1800dad3e  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800dad43  xor     eax, eax
0x1800dad45  jmp     loc_1800DB08E
0x1800dad4a  test    rbp, rbp
0x1800dad4d  jnz     short loc_1800DAD62
0x1800dad4f  mov     [rsp+68h+var_48], rbx
0x1800dad54  lea     r8, a1261; "1261"
0x1800dad5b  mov     edx, 4EDh
0x1800dad60  jmp     short loc_1800DAD31
0x1800dad62  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800dad66  mov     [rsp+68h+TokenHandle], r13
0x1800dad6b  mov     rdx, rbx
0x1800dad6e  mov     rcx, rdi
0x1800dad71  call    ?SetCloseState@CWSManEventSession@@AEAA?AW4EventSessionState@@PEAVIRequestContext@@@Z; CWSManEventSession::SetCloseState(IRequestContext *)
0x1800dad76  mov     esi, eax
0x1800dad78  mov     rcx, [rbx]
0x1800dad7b  mov     rax, [rcx+90h]
0x1800dad82  mov     rcx, rbx
0x1800dad85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dad8a  test    eax, eax
0x1800dad8c  jnz     short loc_1800DADB4
0x1800dad8e  mov     [rsp+68h+var_48], 0; struct IRequestContext *
0x1800dad97  mov     r9d, 54Fh; unsigned int
0x1800dad9d  lea     r8, a1268; "1268"
0x1800dada4  lea     edx, [r9-5Bh]; unsigned int
0x1800dada8  lea     rcx, aOnecoreAdminWm_104; "onecore\\admin\\wmi\\wmx\\client\\remot"...
0x1800dadaf  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800dadb4  cmp     esi, 3
0x1800dadb7  jnz     short loc_1800DADD2
0x1800dadb9  mov     rax, [rbx]
0x1800dadbc  mov     edx, 80338009h
0x1800dadc1  mov     rcx, rbx
0x1800dadc4  mov     rax, [rax+48h]
0x1800dadc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dadcd  jmp     loc_1800DAD43
0x1800dadd2  mov     rcx, rdi; this
0x1800dadd5  call    ?StopHeartbeatTimer@CWSManEventSession@@AEAAHXZ; CWSManEventSession::StopHeartbeatTimer(void)
0x1800dadda  mov     esi, 1
0x1800daddf  mov     edx, esi; int
0x1800dade1  mov     rcx, rdi; this
0x1800dade4  call    ?StopLatencyTimer@CWSManEventSession@@AEAAHH@Z; CWSManEventSession::StopLatencyTimer(int)
0x1800dade9  mov     [rsp+68h+TokenHandle], r13
0x1800dadee  call    cs:__imp_GetCurrentThread
0x1800dadf4  mov     rcx, rax; ThreadHandle
0x1800dadf7  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x1800dadfc  mov     r8d, esi; OpenAsSelf
0x1800dadff  lea     edx, [rsi+3]; DesiredAccess
0x1800dae02  call    cs:__imp_OpenThreadToken
0x1800dae08  test    eax, eax
0x1800dae0a  jnz     short loc_1800DAE79
0x1800dae0c  call    cs:__imp_GetLastError
0x1800dae12  mov     esi, eax
0x1800dae14  cmp     eax, 3F0h
0x1800dae19  jnz     short loc_1800DAE42
0x1800dae1b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dae22  cmp     rcx, r15
0x1800dae25  jz      loc_1800DAEFC
0x1800dae2b  test    dword ptr [rcx+1Ch], 400h
0x1800dae32  jz      loc_1800DAEFC
0x1800dae38  mov     edx, 13h
0x1800dae3d  jmp     loc_1800DAEEC
0x1800dae42  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dae49  cmp     rcx, r15
0x1800dae4c  jz      short loc_1800DAE6F
0x1800dae4e  test    dword ptr [rcx+1Ch], 400h
0x1800dae55  jz      short loc_1800DAE6F
0x1800dae57  mov     edx, 14h
0x1800dae5c  mov     r9d, esi
0x1800dae5f  lea     r8, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids
0x1800dae66  mov     rcx, [rcx+10h]
0x1800dae6a  call    WPP_SF_d
0x1800dae6f  mov     ecx, esi; dwErrCode
0x1800dae71  call    cs:__imp_SetLastError
0x1800dae77  jmp     short loc_1800DAE92
0x1800dae79  call    ?RevertToSelf@CSecurity@@SAHXZ; CSecurity::RevertToSelf(void)
0x1800dae7e  test    eax, eax
0x1800dae80  jnz     short loc_1800DAED2
0x1800dae82  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x1800dae87  call    cs:__imp_CloseHandle
0x1800dae8d  mov     [rsp+68h+TokenHandle], r13
0x1800dae92  call    cs:__imp_GetLastError
0x1800dae98  mov     esi, eax
0x1800dae9a  mov     rcx, [rbx]
0x1800dae9d  mov     rax, [rcx+48h]
0x1800daea1  mov     edx, esi
0x1800daea3  mov     rcx, rbx
0x1800daea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800daeab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800daeb2  cmp     rcx, r15
0x1800daeb5  jz      loc_1800DAF4D
0x1800daebb  test    dword ptr [rcx+1Ch], 8000h
0x1800daec2  jz      loc_1800DAF4D
0x1800daec8  mov     edx, 58h ; 'X'
0x1800daecd  mov     r9d, esi
0x1800daed0  jmp     short loc_1800DAF41
0x1800daed2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800daed9  cmp     rcx, r15
0x1800daedc  jz      short loc_1800DAEFC
0x1800daede  test    dword ptr [rcx+1Ch], 400h
0x1800daee5  jz      short loc_1800DAEFC
0x1800daee7  mov     edx, 15h
0x1800daeec  lea     r8, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids
0x1800daef3  mov     rcx, [rcx+10h]
0x1800daef7  call    WPP_SF_
0x1800daefc  mov     r8, rbp; struct _WSMAN_FAULT_OBJECT *
0x1800daeff  mov     rdx, rbx; struct IRequestContext *
0x1800daf02  mov     rcx, [rdi+468h]; this
0x1800daf09  call    ?SendEndSubscriptionNotification@CRemoteEventDeliveryOperation@@QEAAHPEAVIRequestContext@@PEAU_WSMAN_FAULT_OBJECT@@@Z; CRemoteEventDeliveryOperation::SendEndSubscriptionNotification(IRequestContext *,_WSMAN_FAULT_OBJECT *)
0x1800daf0e  test    eax, eax
0x1800daf10  jnz     short loc_1800DAF4D
0x1800daf12  mov     rax, [rbx]
0x1800daf15  mov     rcx, rbx
0x1800daf18  mov     rax, [rax+98h]
0x1800daf1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800daf24  mov     rcx, cs:WPP_GLOBAL_Control
0x1800daf2b  cmp     rcx, r15
0x1800daf2e  jz      short loc_1800DAF4D
0x1800daf30  test    dword ptr [rcx+1Ch], 8000h
0x1800daf37  jz      short loc_1800DAF4D
0x1800daf39  mov     edx, 59h ; 'Y'
0x1800daf3e  mov     r9d, eax
0x1800daf41  mov     r8, r12
0x1800daf44  mov     rcx, [rcx+10h]
0x1800daf48  call    WPP_SF_d
0x1800daf4d  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x1800daf52  call    ?EndRevertToSelf@CSecurity@@SAHPEAX@Z; CSecurity::EndRevertToSelf(void *)
0x1800daf57  test    eax, eax
0x1800daf59  jnz     short loc_1800DAF9D
0x1800daf5b  call    cs:__imp_GetLastError
0x1800daf61  mov     esi, eax
0x1800daf63  mov     rcx, [rbx]
0x1800daf66  mov     rax, [rcx+48h]
0x1800daf6a  mov     edx, esi
0x1800daf6c  mov     rcx, rbx
0x1800daf6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800daf74  mov     rcx, cs:WPP_GLOBAL_Control
0x1800daf7b  cmp     rcx, r15
0x1800daf7e  jz      short loc_1800DAF9D
0x1800daf80  test    dword ptr [rcx+1Ch], 8000h
0x1800daf87  jz      short loc_1800DAF9D
0x1800daf89  mov     edx, 5Ah ; 'Z'
0x1800daf8e  mov     r9d, esi
0x1800daf91  mov     r8, r12
0x1800daf94  mov     rcx, [rcx+10h]
0x1800daf98  call    WPP_SF_d
0x1800daf9d  lea     rsi, [rdi+628h]
0x1800dafa4  mov     [rsp+68h+var_38], rsi
0x1800dafa9  mov     [rsp+68h+var_30], 0
0x1800dafb1  mov     rcx, rsi; this
0x1800dafb4  call    ?Acquire@CWSManCriticalSection@@QEAAXXZ; CWSManCriticalSection::Acquire(void)
0x1800dafb9  nop
0x1800dafba  mov     rcx, [rdi+470h]; this
0x1800dafc1  test    rcx, rcx
0x1800dafc4  jz      loc_1800DB070
0x1800dafca  xor     edx, edx; char *
0x1800dafcc  call    ?AddRef@IOperation@@QEAA_NPEBD@Z; IOperation::AddRef(char const *)
0x1800dafd1  test    al, al
0x1800dafd3  jz      loc_1800DB070
0x1800dafd9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dafe0  cmp     rcx, r15
0x1800dafe3  jz      short loc_1800DB002
0x1800dafe5  test    dword ptr [rcx+1Ch], 10000h
0x1800dafec  jz      short loc_1800DB002
0x1800dafee  mov     edx, 5Bh ; '['
0x1800daff3  mov     r9, rdi
0x1800daff6  mov     r8, r12
0x1800daff9  mov     rcx, [rcx+10h]
0x1800daffd  call    WPP_SF_q
0x1800db002  mov     r8d, 10h; Flags
0x1800db008  mov     rdx, [rdi+470h]; Context
0x1800db00f  lea     rcx, ?CloseMasterOperationCallback@CWSManEventSession@@CAHPEAX@Z; Function
0x1800db016  call    cs:__imp_QueueUserWorkItem
0x1800db01c  test    eax, eax
0x1800db01e  jnz     short loc_1800DB070
0x1800db020  xor     edx, edx; char *
0x1800db022  mov     rcx, [rdi+470h]; this
0x1800db029  call    ?Release@IOperation@@QEAAJPEBD@Z; IOperation::Release(char const *)
0x1800db02e  call    cs:__imp_GetLastError
0x1800db034  mov     edi, eax
0x1800db036  mov     rcx, [rbx]
0x1800db039  mov     rax, [rcx+48h]
0x1800db03d  mov     edx, edi
0x1800db03f  mov     rcx, rbx
0x1800db042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db047  mov     rcx, cs:WPP_GLOBAL_Control
0x1800db04e  cmp     rcx, r15
0x1800db051  jz      short loc_1800DB070
0x1800db053  test    dword ptr [rcx+1Ch], 8000h
0x1800db05a  jz      short loc_1800DB070
0x1800db05c  mov     edx, 5Ch ; '\'
0x1800db061  mov     r9d, edi
0x1800db064  mov     r8, r12
0x1800db067  mov     rcx, [rcx+10h]
0x1800db06b  call    WPP_SF_d
0x1800db070  mov     rax, [rbx]
0x1800db073  mov     rcx, rbx
0x1800db076  mov     rax, [rax+90h]
0x1800db07d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db082  mov     ebx, eax
0x1800db084  mov     rcx, rsi; this
0x1800db087  call    ?Release@CWSManCriticalSection@@QEAAXXZ; CWSManCriticalSection::Release(void)
0x1800db08c  mov     eax, ebx
0x1800db08e  lea     r11, [rsp+68h+var_28]
0x1800db093  mov     rbx, [r11+30h]
0x1800db097  mov     rbp, [r11+40h]
0x1800db09b  mov     rsp, r11
0x1800db09e  pop     r15
0x1800db0a0  pop     r13
0x1800db0a2  pop     r12
0x1800db0a4  pop     rdi
0x1800db0a5  pop     rsi
0x1800db0a6  retn
```
