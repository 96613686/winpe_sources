# s_ApfDeviceCreateRpc

- ea: `0x180007660`
- end: `0x180007d0d`
- name: `s_ApfDeviceCreateRpc`
- size: `1709`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation`

## callees

- `0x180006140`
- `0x1800061ac`
- `0x180006740`
- `0x180007124`
- `0x1800074dc`
- `0x18000754c`
- `0x1800075a0`
- `0x180007610`
- `0x180007660`
- `0x180007f64`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007920`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007920`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000790c`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000790c`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180007865`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180007865`
- `RPCRT4!RpcImpersonateClient` at `0x1800078a4`
- `RPCRT4!RpcImpersonateClient` at `0x1800078a4`
- `RPCRT4!RpcRevertToSelf` at `0x180007980`
- `RPCRT4!RpcRevertToSelf` at `0x180007980`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800076f7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800076f7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007706`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007706`
- `Apx01000!imp_ApxDeviceInitAssignInstanceId` at `0x180007b63`
- `Apx01000!imp_ApxDeviceInitAssignInstanceId` at `0x180007b63`
- `Apx01000!imp_ApxDeviceInitSetProductType` at `0x180007b22`
- `Apx01000!imp_ApxDeviceInitSetProductType` at `0x180007b22`
- `Apx01000!imp_ApxDeviceInitSetSessionId` at `0x180007ac6`
- `Apx01000!imp_ApxDeviceInitSetSessionId` at `0x180007ac6`
- `Apx01000!imp_ApxDeviceInitSetContainerId` at `0x180007b39`
- `Apx01000!imp_ApxDeviceInitSetContainerId` at `0x180007b39`
- `Apx01000!imp_ApxDeviceInitAllocate` at `0x180007a63`
- `Apx01000!imp_ApxDeviceInitAllocate` at `0x180007a63`
- `Apx01000!imp_ApxDeviceInitSetPresenceNotForDevice` at `0x180007b4c`
- `Apx01000!imp_ApxDeviceInitSetPresenceNotForDevice` at `0x180007b4c`
- `Apx01000!imp_ApxDeviceInitFree` at `0x180007750`
- `Apx01000!imp_ApxDeviceInitFree` at `0x180007750`
- `Apx01000!imp_ApxDeviceInitAssignParentInstance` at `0x180007bd4`
- `Apx01000!imp_ApxDeviceInitAssignParentInstance` at `0x180007bd4`
- `Apx01000!imp_ApxDeviceInitAssignFriendlyName` at `0x180007bfa`
- `Apx01000!imp_ApxDeviceInitAssignFriendlyName` at `0x180007bfa`
- `Apx01000!imp_ApxDeviceCreate` at `0x180007c89`
- `Apx01000!imp_ApxDeviceCreate` at `0x180007c89`
- `Apx01000!imp_ApxDeviceInitSetControlInterfaceId` at `0x180007add`
- `Apx01000!imp_ApxDeviceInitSetControlInterfaceId` at `0x180007add`
- `Apx01000!imp_ApxDeviceInitSetProductId` at `0x180007b0c`
- `Apx01000!imp_ApxDeviceInitSetProductId` at `0x180007b0c`
- `Apx01000!imp_ApxDeviceInitSetOwnerProcessId` at `0x180007ab6`
- `Apx01000!imp_ApxDeviceInitSetOwnerProcessId` at `0x180007ab6`

## pseudocode

```c
__int64 __fastcall s_ApfDeviceCreateRpc(RPC_BINDING_HANDLE BindingHandle, __int64 a2, _QWORD *a3)
{
  struct _APF_APP_INFO *v6; // r15
  signed int inited; // ebx
  _QWORD *v8; // rcx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  RPC_STATUS v13; // eax
  __int64 v14; // rdx
  RPC_STATUS v15; // eax
  signed int LastError; // eax
  signed int AppInfo; // eax
  int (__fastcall *v18)(_QWORD, __int64); // rax
  __int64 v19; // rbx
  struct _APF_APP_INFO *v20; // [rsp+30h] [rbp-20h] BYREF
  __int64 v21; // [rsp+38h] [rbp-18h] BYREF
  __int64 v22; // [rsp+40h] [rbp-10h] BYREF
  unsigned int Pid; // [rsp+90h] [rbp+40h] BYREF
  DWORD pSessionId; // [rsp+98h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_f6dcdc45f51737ce5ae61d05ae8073f7_Traceguids);
  }
  v6 = 0;
  v20 = 0;
  v22 = 0;
  v21 = 0;
  Pid = 0;
  pSessionId = 0;
  *a3 = 0;
  if ( _InterlockedIncrement(&dword_18000E4C8) == 1 && pti )
  {
    SetThreadpoolTimer(pti, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(pti, 1);
  }
  if ( *(_DWORD *)a2 != 104 )
  {
    inited = -2147024809;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_ddd(*((_QWORD *)WPP_GLOBAL_Control + 2));
    }
    goto LABEL_13;
  }
  if ( (*(_DWORD *)(a2 + 4) & 0xFFFFFF00) != 0 )
  {
    inited = -2147024809;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_DDd(*((_QWORD *)WPP_GLOBAL_Control + 2));
    }
    goto LABEL_13;
  }
  if ( *(_QWORD *)(a2 + 96) )
  {
    inited = -2147024809;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || *((char *)WPP_GLOBAL_Control + 28) >= 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v11 = 16;
    goto LABEL_33;
  }
  v13 = I_RpcBindingInqLocalClientPID(BindingHandle, &Pid);
  inited = v13;
  if ( v13 )
  {
    if ( v13 > 0 )
      inited = (unsigned __int16)v13 | 0x80070000;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = 17;
LABEL_49:
      WPP_SF_d(v8[2], v14, &WPP_f6dcdc45f51737ce5ae61d05ae8073f7_Traceguids, (unsigned int)inited);
      v8 = WPP_GLOBAL_Control;
      goto LABEL_50;
    }
    goto LABEL_50;
  }
  v15 = RpcImpersonateClient(BindingHandle);
  inited = v15;
  if ( v15 )
  {
    if ( v15 > 0 )
      inited = (unsigned __int16)v15 | 0x80070000;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = 18;
      goto LABEL_49;
    }
LABEL_50:
    if ( inited >= 0 )
      goto LABEL_18;
    goto LABEL_13;
  }
  if ( ProcessIdToSessionId(Pid, &pSessionId) )
  {
    AppInfo = GetAppInfo(Pid, &v20);
    v6 = v20;
    inited = AppInfo;
  }
  else
  {
    pSessionId = 0;
    LastError = GetLastError();
    inited = LastError;
    if ( LastError > 0 )
      inited = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        &WPP_f6dcdc45f51737ce5ae61d05ae8073f7_Traceguids,
        (unsigned int)inited);
    }
  }
  RpcRevertToSelf();
  if ( inited < 0 )
    goto LABEL_13;
  if ( !v6 )
  {
    v12 = 2147942405LL;
    inited = -2147024891;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v11 = 20;
    goto LABEL_34;
  }
  v18 = (int (__fastcall *)(_QWORD, __int64))*((_QWORD *)v6 + 5);
  if ( !v18 )
  {
    v12 = 2147942405LL;
    inited = -2147024891;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v11 = 21;
    goto LABEL_34;
  }
  if ( v18(*((_QWORD *)v6 + 2), a2) < 0 )
  {
    inited = -2147024809;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v11 = 22;
    goto LABEL_33;
  }
  v21 = imp_ApxDeviceInitAllocate(0);
  if ( !v21 )
  {
    inited = -2147024882;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v11 = 23;
    goto LABEL_33;
  }
  imp_ApxDeviceInitSetOwnerProcessId(0, v21, Pid);
  imp_ApxDeviceInitSetSessionId(0, v21, pSessionId);
  if ( (*(_BYTE *)(a2 + 4) & 1) != 0 )
    imp_ApxDeviceInitSetControlInterfaceId(0, v21, a2 + 8);
  if ( (*(_BYTE *)(a2 + 4) & 0x20) != 0 )
    imp_ApxDeviceInitSetProductId(
      0,
      v21,
      *(unsigned __int16 *)(a2 + 56),
      *(unsigned __int16 *)(a2 + 58),
      *(_DWORD *)(a2 + 60),
      *(_WORD *)(a2 + 64));
  if ( (*(_BYTE *)(a2 + 4) & 2) != 0 )
    imp_ApxDeviceInitSetProductType(0, v21, a2 + 24);
  if ( (*(_BYTE *)(a2 + 4) & 4) != 0 )
    imp_ApxDeviceInitSetContainerId(0, v21, a2 + 40);
  if ( (*(_BYTE *)(a2 + 4) & 0x40) != 0 )
    imp_ApxDeviceInitSetPresenceNotForDevice(0, v21);
  if ( (*(_BYTE *)(a2 + 4) & 8) != 0 )
  {
    inited = imp_ApxDeviceInitAssignInstanceId(0, v21, *(_QWORD *)(a2 + 72));
    if ( inited < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_13;
      }
      v11 = 24;
      goto LABEL_33;
    }
  }
  if ( (*(_BYTE *)(a2 + 4) & 0x10) != 0 )
  {
    v19 = *(_QWORD *)(a2 + 80);
    if ( v19 && !wcscmp_0(*(const wchar_t **)(a2 + 80), L"SWD\\APXENUM\\0") )
    {
      inited = imp_ApxDeviceInitAssignParentInstance(0, v21, v19);
      if ( inited >= 0 )
        goto LABEL_101;
    }
    else
    {
      inited = -2147024809;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2));
    }
    goto LABEL_13;
  }
LABEL_101:
  if ( (*(_BYTE *)(a2 + 4) & 0x80) != 0 )
  {
    inited = imp_ApxDeviceInitAssignFriendlyName(0, v21, *(_QWORD *)(a2 + 88), 1);
    if ( inited < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_13;
      }
      v11 = 26;
      goto LABEL_33;
    }
  }
  inited = imp_ApxDeviceCreate(0, 0, &v21, &v22);
  if ( inited < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v11 = 27;
LABEL_33:
    v12 = (unsigned int)inited;
LABEL_34:
    WPP_SF_d(v10[2], v11, &WPP_f6dcdc45f51737ce5ae61d05ae8073f7_Traceguids, v12);
LABEL_13:
    if ( v21 )
    {
      imp_ApxDeviceInitFree(0);
      v21 = 0;
    }
    if ( _InterlockedExchangeAdd(&dword_18000E4C8, 0xFFFFFFFF) == 1 )
      anonymous_namespace_::SetShutdownTimer();
    v8 = WPP_GLOBAL_Control;
    goto LABEL_18;
  }
  *a3 = v22;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 28);
    v8 = WPP_GLOBAL_Control;
  }
  inited = 0;
LABEL_18:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 5u )
    WPP_SF_(v8[2], 29, &WPP_f6dcdc45f51737ce5ae61d05ae8073f7_Traceguids);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180007660  mov     [rsp-28h+arg_0], rbx
0x180007665  mov     [rsp-28h+arg_8], rsi
0x18000766a  push    rbp
0x18000766b  push    rdi
0x18000766c  push    r12
0x18000766e  push    r14
0x180007670  push    r15
0x180007672  mov     rbp, rsp
0x180007675  sub     rsp, 50h
0x180007679  mov     r12, r8
0x18000767c  mov     r14, rdx
0x18000767f  mov     rdi, rcx
0x180007682  mov     rcx, cs:WPP_GLOBAL_Control
0x180007689  lea     rsi, WPP_GLOBAL_Control
0x180007690  mov     ebx, 1
0x180007695  cmp     rcx, rsi
0x180007698  jz      short loc_1800076B8
0x18000769a  test    [rcx+1Ch], bl
0x18000769d  jz      short loc_1800076B8
0x18000769f  cmp     byte ptr [rcx+19h], 5
0x1800076a3  jb      short loc_1800076B8
0x1800076a5  mov     rcx, [rcx+10h]
0x1800076a9  lea     edx, [rbx+0Bh]
0x1800076ac  lea     r8, WPP_f6dcdc45f51737ce5ae61d05ae8073f7_Traceguids
0x1800076b3  call    WPP_SF_
0x1800076b8  xor     r15d, r15d
0x1800076bb  mov     eax, ebx
0x1800076bd  mov     [rbp+var_20], r15
0x1800076c1  mov     [rbp+var_10], r15
0x1800076c5  mov     [rbp+var_18], r15
0x1800076c9  mov     [rbp+Pid], r15d
0x1800076cd  mov     [rbp+pSessionId], r15d
0x1800076d1  mov     [r12], r15
0x1800076d5  lock xadd cs:dword_18000E4C8, eax
0x1800076dd  add     eax, ebx
0x1800076df  cmp     eax, ebx
0x1800076e1  jnz     short loc_18000770C
0x1800076e3  mov     rcx, cs:pti; pti
0x1800076ea  test    rcx, rcx
0x1800076ed  jz      short loc_18000770C
0x1800076ef  xor     r9d, r9d; msWindowLength
0x1800076f2  xor     r8d, r8d; msPeriod
0x1800076f5  xor     edx, edx; pftDueTime
0x1800076f7  call    cs:__imp_SetThreadpoolTimer
0x1800076fd  mov     rcx, cs:pti; pti
0x180007704  mov     edx, ebx; fCancelPendingCallbacks
0x180007706  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000770c  mov     r9d, [r14]
0x18000770f  cmp     r9d, 68h ; 'h'
0x180007713  jz      loc_1800077C2
0x180007719  mov     ebx, 80070057h
0x18000771e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007725  cmp     rcx, rsi
0x180007728  jz      short loc_180007745
0x18000772a  mov     sil, 80h
0x18000772d  test    [rcx+1Ch], sil
0x180007731  jz      short loc_180007745
0x180007733  mov     dil, 2
0x180007736  cmp     [rcx+19h], dil
0x18000773a  jb      short loc_180007745
0x18000773c  mov     rcx, [rcx+10h]
0x180007740  call    WPP_SF_ddd
0x180007745  mov     rdx, [rbp+var_18]
0x180007749  test    rdx, rdx
0x18000774c  jz      short loc_18000775E
0x18000774e  xor     ecx, ecx
0x180007750  call    cs:__imp_imp_ApxDeviceInitFree
0x180007756  mov     [rbp+var_18], 0
0x18000775e  or      eax, 0FFFFFFFFh
0x180007761  lock xadd cs:dword_18000E4C8, eax
0x180007769  cmp     eax, 1
0x18000776c  jnz     short loc_180007773
0x18000776e  call    _anonymous_namespace___SetShutdownTimer
0x180007773  mov     rcx, cs:WPP_GLOBAL_Control
0x18000777a  lea     rax, WPP_GLOBAL_Control
0x180007781  cmp     rcx, rax
0x180007784  jz      short loc_1800077A7
0x180007786  test    byte ptr [rcx+1Ch], 1
0x18000778a  jz      short loc_1800077A7
0x18000778c  cmp     byte ptr [rcx+19h], 5
0x180007790  jb      short loc_1800077A7
0x180007792  mov     rcx, [rcx+10h]
0x180007796  lea     r8, WPP_f6dcdc45f51737ce5ae61d05ae8073f7_Traceguids
0x18000779d  mov     edx, 1Dh
0x1800077a2  call    WPP_SF_
0x1800077a7  lea     r11, [rsp+50h+var_s0]
0x1800077ac  mov     eax, ebx
0x1800077ae  mov     rbx, [r11+30h]
0x1800077b2  mov     rsi, [r11+38h]
0x1800077b6  mov     rsp, r11
0x1800077b9  pop     r15
0x1800077bb  pop     r14
0x1800077bd  pop     r12
0x1800077bf  pop     rdi
0x1800077c0  pop     rbp
0x1800077c1  retn
0x1800077c2  mov     r9d, [r14+4]
0x1800077c6  test    r9d, 0FFFFFF00h
0x1800077cd  jz      short loc_18000780C
0x1800077cf  mov     ebx, 80070057h
0x1800077d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800077db  cmp     rcx, rsi
0x1800077de  jz      loc_180007745
0x1800077e4  mov     sil, 80h
0x1800077e7  test    [rcx+1Ch], sil
0x1800077eb  jz      loc_180007745
0x1800077f1  mov     dil, 2
0x1800077f4  cmp     [rcx+19h], dil
0x1800077f8  jb      loc_180007745
0x1800077fe  mov     rcx, [rcx+10h]
0x180007802  call    WPP_SF_DDd
0x180007807  jmp     loc_180007745
0x18000780c  cmp     [r14+60h], r15
0x180007810  jz      short loc_18000785E
0x180007812  mov     ebx, 80070057h
0x180007817  mov     rcx, cs:WPP_GLOBAL_Control
0x18000781e  cmp     rcx, rsi
0x180007821  jz      loc_180007745
0x180007827  mov     sil, 80h
0x18000782a  test    [rcx+1Ch], sil
0x18000782e  jz      loc_180007745
0x180007834  mov     dil, 2
0x180007837  cmp     [rcx+19h], dil
0x18000783b  jb      loc_180007745
0x180007841  mov     edx, 10h
0x180007846  mov     r9d, ebx
0x180007849  mov     rcx, [rcx+10h]
0x18000784d  lea     r8, WPP_f6dcdc45f51737ce5ae61d05ae8073f7_Traceguids
0x180007854  call    WPP_SF_d
0x180007859  jmp     loc_180007745
0x18000785e  lea     rdx, [rbp+Pid]; Pid
0x180007862  mov     rcx, rdi; Binding
0x180007865  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000786b  mov     ebx, eax
0x18000786d  test    eax, eax
0x18000786f  jz      short loc_1800078A1
0x180007871  jle     short loc_18000787C
0x180007873  movzx   ebx, ax
0x180007876  or      ebx, 80070000h
0x18000787c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007883  cmp     rcx, rsi
0x180007886  jz      short loc_1800078F8
0x180007888  mov     sil, 80h
0x18000788b  test    [rcx+1Ch], sil
0x18000788f  jz      short loc_1800078F8
0x180007891  mov     dil, 2
0x180007894  cmp     [rcx+19h], dil
0x180007898  jb      short loc_1800078F8
0x18000789a  mov     edx, 11h
0x18000789f  jmp     short loc_1800078DE
0x1800078a1  mov     rcx, rdi; BindingHandle
0x1800078a4  call    cs:__imp_RpcImpersonateClient
0x1800078aa  mov     ebx, eax
0x1800078ac  test    eax, eax
0x1800078ae  jz      short loc_180007905
0x1800078b0  jle     short loc_1800078BB
0x1800078b2  movzx   ebx, ax
0x1800078b5  or      ebx, 80070000h
0x1800078bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800078c2  cmp     rcx, rsi
0x1800078c5  jz      short loc_1800078F8
0x1800078c7  mov     sil, 80h
0x1800078ca  test    [rcx+1Ch], sil
0x1800078ce  jz      short loc_1800078F8
0x1800078d0  mov     dil, 2
0x1800078d3  cmp     [rcx+19h], dil
0x1800078d7  jb      short loc_1800078F8
0x1800078d9  mov     edx, 12h
0x1800078de  mov     rcx, [rcx+10h]
0x1800078e2  lea     r8, WPP_f6dcdc45f51737ce5ae61d05ae8073f7_Traceguids
0x1800078e9  mov     r9d, ebx
0x1800078ec  call    WPP_SF_d
0x1800078f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800078f8  test    ebx, ebx
0x1800078fa  jns     loc_18000777A
0x180007900  jmp     loc_180007745
0x180007905  mov     ecx, [rbp+Pid]; dwProcessId
0x180007908  lea     rdx, [rbp+pSessionId]; pSessionId
0x18000790c  call    cs:__imp_ProcessIdToSessionId
0x180007912  mov     dil, 2
0x180007915  mov     sil, 80h
0x180007918  test    eax, eax
0x18000791a  jnz     short loc_18000796E
0x18000791c  mov     [rbp+pSessionId], r15d
0x180007920  call    cs:__imp_GetLastError
0x180007926  mov     ebx, eax
0x180007928  test    eax, eax
0x18000792a  jle     short loc_180007935
0x18000792c  movzx   ebx, ax
0x18000792f  or      ebx, 80070000h
0x180007935  mov     rcx, cs:WPP_GLOBAL_Control
0x18000793c  lea     rax, WPP_GLOBAL_Control
0x180007943  cmp     rcx, rax
0x180007946  jz      short loc_180007980
0x180007948  test    [rcx+1Ch], sil
0x18000794c  jz      short loc_180007980
0x18000794e  cmp     [rcx+19h], dil
0x180007952  jb      short loc_180007980
0x180007954  mov     rcx, [rcx+10h]
0x180007958  lea     r8, WPP_f6dcdc45f51737ce5ae61d05ae8073f7_Traceguids
0x18000795f  mov     edx, 13h
0x180007964  mov     r9d, ebx
0x180007967  call    WPP_SF_d
0x18000796c  jmp     short loc_180007980
0x18000796e  mov     ecx, [rbp+Pid]; dwProcessId
0x180007971  lea     rdx, [rbp+var_20]; struct _APF_APP_INFO **
0x180007975  call    ?GetAppInfo@@YAJKPEAPEAU_APF_APP_INFO@@@Z; GetAppInfo(ulong,_APF_APP_INFO * *)
0x18000797a  mov     r15, [rbp+var_20]
0x18000797e  mov     ebx, eax
0x180007980  call    cs:__imp_RpcRevertToSelf
0x180007986  test    ebx, ebx
0x180007988  js      loc_180007745
0x18000798e  test    r15, r15
0x180007991  jnz     short loc_1800079D0
0x180007993  mov     r9d, 80070005h
0x180007999  mov     ebx, r9d
0x18000799c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800079a3  lea     rax, WPP_GLOBAL_Control
0x1800079aa  cmp     rcx, rax
0x1800079ad  jz      loc_180007745
0x1800079b3  test    [rcx+1Ch], sil
0x1800079b7  jz      loc_180007745
0x1800079bd  cmp     [rcx+19h], dil
0x1800079c1  jb      loc_180007745
0x1800079c7  lea     edx, [r15+14h]
0x1800079cb  jmp     loc_180007849
0x1800079d0  mov     rax, [r15+28h]
0x1800079d4  test    rax, rax
0x1800079d7  jnz     short loc_180007A17
0x1800079d9  mov     r9d, 80070005h
0x1800079df  mov     ebx, r9d
0x1800079e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800079e9  lea     rax, WPP_GLOBAL_Control
0x1800079f0  cmp     rcx, rax
0x1800079f3  jz      loc_180007745
0x1800079f9  test    [rcx+1Ch], sil
0x1800079fd  jz      loc_180007745
0x180007a03  cmp     [rcx+19h], dil
0x180007a07  jb      loc_180007745
0x180007a0d  mov     edx, 15h
0x180007a12  jmp     loc_180007849
0x180007a17  mov     rcx, [r15+10h]
0x180007a1b  mov     rdx, r14
0x180007a1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a23  test    eax, eax
0x180007a25  jns     short loc_180007A61
0x180007a27  mov     ebx, 80070057h
0x180007a2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a33  lea     rax, WPP_GLOBAL_Control
0x180007a3a  cmp     rcx, rax
0x180007a3d  jz      loc_180007745
0x180007a43  test    [rcx+1Ch], sil
0x180007a47  jz      loc_180007745
0x180007a4d  cmp     [rcx+19h], dil
0x180007a51  jb      loc_180007745
0x180007a57  mov     edx, 16h
0x180007a5c  jmp     loc_180007846
0x180007a61  xor     ecx, ecx
0x180007a63  call    cs:__imp_imp_ApxDeviceInitAllocate
0x180007a69  mov     [rbp+var_18], rax
0x180007a6d  test    rax, rax
0x180007a70  jnz     short loc_180007AAC
0x180007a72  mov     ebx, 8007000Eh
0x180007a77  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a7e  lea     rax, WPP_GLOBAL_Control
0x180007a85  cmp     rcx, rax
0x180007a88  jz      loc_180007745
0x180007a8e  test    [rcx+1Ch], sil
0x180007a92  jz      loc_180007745
0x180007a98  cmp     [rcx+19h], dil
0x180007a9c  jb      loc_180007745
0x180007aa2  mov     edx, 17h
0x180007aa7  jmp     loc_180007846
0x180007aac  mov     r8d, [rbp+Pid]
0x180007ab0  xor     ecx, ecx
0x180007ab2  mov     rdx, [rbp+var_18]
0x180007ab6  call    cs:__imp_imp_ApxDeviceInitSetOwnerProcessId
0x180007abc  mov     r8d, [rbp+pSessionId]
0x180007ac0  xor     ecx, ecx
0x180007ac2  mov     rdx, [rbp+var_18]
0x180007ac6  call    cs:__imp_imp_ApxDeviceInitSetSessionId
0x180007acc  test    byte ptr [r14+4], 1
0x180007ad1  jz      short loc_180007AE3
0x180007ad3  mov     rdx, [rbp+var_18]
0x180007ad7  lea     r8, [r14+8]
0x180007adb  xor     ecx, ecx
0x180007add  call    cs:__imp_imp_ApxDeviceInitSetControlInterfaceId
0x180007ae3  test    byte ptr [r14+4], 20h
0x180007ae8  jz      short loc_180007B12
0x180007aea  movzx   eax, word ptr [r14+40h]
0x180007aef  xor     ecx, ecx
0x180007af1  movzx   r9d, word ptr [r14+3Ah]
0x180007af6  movzx   r8d, word ptr [r14+38h]
0x180007afb  mov     rdx, [rbp+var_18]
0x180007aff  mov     [rsp+50h+var_28], ax
0x180007b04  mov     eax, [r14+3Ch]
0x180007b08  mov     [rsp+50h+var_30], eax
0x180007b0c  call    cs:__imp_imp_ApxDeviceInitSetProductId
0x180007b12  test    [r14+4], dil
0x180007b16  jz      short loc_180007B28
  ... truncated ...
```
