# PortClose

- ea: `0x18002040c`
- end: `0x180020db8`
- name: `PortClose`
- size: `2476`
- prototype: ``
- caller_count: `7`
- callee_count: `29`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180014230`
- `0x180015c90`
- `0x1800178a0`
- `0x180020dc0`
- `0x18002a1e0`
- `0x180039ea0`
- `0x18004eb50`

## callees

- `0x1800056c8`
- `0x180005e0c`
- `0x180005e34`
- `0x180005f1c`
- `0x18000b9b4`
- `0x18000bfb0`
- `0x18000c00c`
- `0x18002040c`
- `0x180032118`
- `0x180032814`
- `0x180032a98`
- `0x18003426c`
- `0x180039c00`
- `0x18003f3a8`
- `0x18003f458`
- `0x180044e4c`
- `0x18004563c`
- `0x180047198`
- `0x180047668`
- `0x180047714`
- `0x180048464`
- `0x18004852c`
- `0x1800486b4`
- `0x18004a53c`
- `0x18007c974`
- `0x18009d51c`
- `0x1800a44c4`
- `0x1800a4874`
- `0x1800e9010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020464`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020b25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020464`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020b25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800208fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020c32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800208fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020c32`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020a28`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020a28`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180020c25`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180020c25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020a46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020a46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002085e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020907`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020b4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020b60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020b74`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002085e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020907`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020b4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020b60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020b74`

## string_xrefs

- `0x1800206b0`: `PortClose: Attempt to close server port was denied`
- `0x180020615`: `PortClose: Access was denied`

## pseudocode

```c
__int64 __fastcall PortClose(_QWORD *a1, unsigned int a2, char a3, char a4)
{
  DWORD CurrentProcessId; // edi
  struct _LIST_ENTRY *v9; // rcx
  struct _LIST_ENTRY *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rax
  struct _LIST_ENTRY *v14; // rcx
  __int64 v15; // rdx
  bool v16; // r13
  int v17; // eax
  void *v18; // rcx
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rdi
  void *v24; // rcx
  void *v25; // rcx
  void *v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  unsigned int v29; // ebx
  unsigned int i; // edi
  unsigned int v31; // eax
  unsigned int v32; // eax

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 148, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
  }
  CurrentProcessId = GetCurrentProcessId();
  if ( a1 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control[1].Flink,
        151,
        WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
        *a1,
        *((unsigned __int16 *)a1 + 22));
      v11 = WPP_GLOBAL_Control;
    }
    if ( *((_DWORD *)a1 + 7) == 3 && *((_DWORD *)a1 + 118) == 9 )
    {
      if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v11[1].Blink) & 0x2000) != 0
        && BYTE1(v11[1].Blink) >= 4u )
      {
        WPP_SF_s(v11[1].Flink, 152, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, a1 + 1);
      }
      *((_DWORD *)a1 + 268) = 1;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 6u )
      {
        return 0;
      }
      v12 = 153;
LABEL_165:
      WPP_SF_d(v11[1].Flink, v12, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, 0);
      return 0;
    }
    if ( *((_DWORD *)a1 + 6) == 1 )
    {
      if ( v11 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(v11[1].Blink) & 0x2000) == 0
        || BYTE1(v11[1].Blink) < 6u )
      {
        return 0;
      }
      v12 = 154;
      goto LABEL_165;
    }
    if ( *((_DWORD *)a1 + 68) == CurrentProcessId && a2 != CurrentProcessId )
    {
      v13 = a1[133];
      if ( v13 )
      {
        if ( (unsigned int)IsRouterPhonebook((LPCWSTR)(v13 + 184)) )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
          {
            WPP_SF_(WPP_GLOBAL_Control[1].Flink, 155, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
          }
          TelemetryEventWriteStateChange(a1, 5, "PortClose: Access was denied");
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 6u )
          {
            return 5;
          }
          v15 = 156;
LABEL_58:
          WPP_SF_d(v14[1].Flink, v15, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, 5);
          return 5;
        }
        v11 = WPP_GLOBAL_Control;
      }
    }
    if ( *((_WORD *)a1 + 22) == 1 && CurrentProcessId == *((_DWORD *)a1 + 115) && !a4 )
    {
      if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v11[1].Blink) & 0x2000) != 0
        && BYTE1(v11[1].Blink) >= 2u )
      {
        WPP_SF_d(v11[1].Flink, 157, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, a2);
      }
      TelemetryEventWriteStateChange(a1, 5, "PortClose: Attempt to close server port was denied");
      *((_DWORD *)a1 + 306) &= 0xFFFFFFF3;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 6u )
      {
        return 5;
      }
      v15 = 158;
      goto LABEL_58;
    }
    v16 = a2 == *((_DWORD *)a1 + 68);
    if ( *((_WORD *)a1 + 22) == 2
      && *((_DWORD *)a1 + 115) == a2
      && !*((_DWORD *)a1 + 67)
      && v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v11[1].Blink) & 0x2000) != 0
      && BYTE1(v11[1].Blink) >= 2u )
    {
      WPP_SF_s(v11[1].Flink, 159, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, a1 + 1);
      v11 = WPP_GLOBAL_Control;
    }
    if ( *((_DWORD *)a1 + 118) && *((_DWORD *)a1 + 7) != 3 )
    {
      v17 = *((_DWORD *)a1 + 66);
      if ( !v17 || v17 == 600 )
        *((_DWORD *)a1 + 66) = 619;
      CompleteAsyncRequest(a1);
      v11 = WPP_GLOBAL_Control;
    }
    if ( a1[143] )
    {
      if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v11[1].Blink) & 0x2000) != 0
        && BYTE1(v11[1].Blink) >= 4u )
      {
        WPP_SF_(v11[1].Flink, 160, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
      }
      SetDialMachineEventHandleCommon(a1, a1[143], *((unsigned int *)a1 + 290), 0, 0, 0, 0, 0, a1[144]);
      v11 = WPP_GLOBAL_Control;
    }
    if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v11[1].Blink) & 0x2000) != 0
      && BYTE1(v11[1].Blink) >= 4u )
    {
      WPP_SF_q(v11[1].Flink, 161, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, *a1);
    }
    FreeNotifierList(a1 + 53);
    v18 = (void *)a1[70];
    if ( v18 )
    {
      LocalFree(v18);
      a1[70] = 0;
      *((_DWORD *)a1 + 142) = 0;
    }
    if ( !a4 && *(_WORD *)(a1[154] + 96LL) == 9 )
    {
      v19 = DisableClientIpSecFilter(a1);
      if ( v19
        && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_sd(
          WPP_GLOBAL_Control[1].Flink,
          162,
          (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
          (_DWORD)a1 + 8,
          v19);
      }
      FreeIkeInitiateContext((HLOCAL)a1[162]);
      a1[162] = 0;
    }
    v20 = a1[163];
    if ( v20 )
    {
      CloseHandle(*(HANDLE *)(v20 + 8));
      LocalFree((HLOCAL)a1[163]);
      a1[163] = 0;
    }
    FreeUserData(a1 + 135);
    *((_DWORD *)a1 + 68) = 0;
    --*((_WORD *)a1 + 22);
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control[1].Flink,
        163,
        WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
        *a1,
        *((unsigned __int16 *)a1 + 22));
    }
    *((_DWORD *)a1 + 8) &= ~4u;
    if ( !*((_WORD *)a1 + 22) || *((_DWORD *)a1 + 6) == 2 || (a1[153] & 8) != 0 )
    {
      if ( *((_DWORD *)a1 + 7) != 4 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
        {
          WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 164, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, *a1);
        }
        SignalPortDisconnect(a1, 0);
        EnterCriticalSection(&g_csConnectionNotifierList);
        SignalNotifiers(pConnectionNotifierList, 2, 0);
        LeaveCriticalSection(&g_csConnectionNotifierList);
      }
      if ( (a3 || *((_DWORD *)a1 + 6) == 2)
        && ((*(void (__fastcall **)(_QWORD))(a1[6] + 32LL))(a1[27]), *((_DWORD *)a1 + 6) == 2) )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
        {
          WPP_SF_sq(
            WPP_GLOBAL_Control[1].Flink,
            165,
            (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
            (_DWORD)a1 + 8,
            *a1);
        }
        RemovePort(*a1);
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control[1].Flink, 166, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
        }
      }
      else
      {
        SetPortAsyncReqType("onecoreuap\\net\\rras\\ras\\rasman\\rasman\\request.c", 3190, a1, 0);
        SetPortConnState(v22, v21, a1, 4);
        *((_DWORD *)a1 + 130) = 0;
        *((_DWORD *)a1 + 6) = 1;
        *((_DWORD *)a1 + 143) = 0;
      }
    }
    else
    {
      a1[70] = a1[56];
      *((_DWORD *)a1 + 142) = *((_DWORD *)a1 + 114);
      if ( !a3 )
        (*(void (__fastcall **)(_QWORD *, _QWORD *, HANDLE, _QWORD))(a1[6] + 24LL))(
          a1 + 1,
          a1 + 27,
          hIoCompletionPort,
          *(unsigned int *)a1);
      RePostListenOnBiplexPort(a1);
    }
    if ( a2 == GetCurrentProcessId() )
      *((_DWORD *)a1 + 306) &= ~8u;
    v23 = a1[133];
    v24 = (void *)a1[150];
    a1[133] = 0;
    LocalFree(v24);
    v25 = (void *)a1[151];
    a1[150] = 0;
    LocalFree(v25);
    v26 = (void *)a1[152];
    a1[151] = 0;
    LocalFree(v26);
    a1[152] = 0;
    a1[157] = 0;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
    {
      WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 167, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, *a1);
    }
    v28 = a1[160];
    *((_DWORD *)a1 + 306) &= 0xFFFFFFEB;
    *((_DWORD *)a1 + 10) = 0;
    a1[159] = 0;
    *((_DWORD *)a1 + 329) = 0;
    if ( (unsigned __int64)(v28 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
      {
        WPP_SF_qs(
          WPP_GLOBAL_Control[1].Flink,
          168,
          (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
          v28,
          (__int64)(a1 + 1));
      }
      SetEvent((HANDLE)a1[160]);
      CloseHandle((HANDLE)a1[160]);
    }
    LOBYTE(v27) = v16;
    a1[160] = -1;
    RemoveConnectionPort(a1, v23, v27);
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
    {
      WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 169, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, *a1);
    }
    *((_DWORD *)a1 + 268) = 0;
    if ( *((_DWORD *)a1 + 316) )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
      {
        WPP_SF_sq(
          WPP_GLOBAL_Control[1].Flink,
          170,
          (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
          (_DWORD)a1 + 8,
          a1[30]);
      }
      a1[30] = 0;
      *((_DWORD *)a1 + 316) = 0;
    }
    if ( !(unsigned int)fAnyConnectedPorts() )
    {
      SetRasmanServiceStopControl(1);
      v29 = 0;
      for ( i = 1; i < 6; ++i )
      {
        v31 = DisableAutoWPPTracingForSubComponent(i);
        if ( v31 )
          v29 = v31;
      }
      if ( v29
        && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 171, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v29);
      }
      v32 = DisableAutoTracing();
      if ( v32 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          return 0;
        if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          goto LABEL_161;
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 172, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v32);
      }
    }
    v11 = WPP_GLOBAL_Control;
LABEL_161:
    if ( v11 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(v11[1].Blink) & 0x2000) == 0
      || BYTE1(v11[1].Blink) < 6u )
    {
      return 0;
    }
    v12 = 173;
    goto LABEL_165;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 149, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
      v9 = WPP_GLOBAL_Control;
    }
    if ( v9 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v9[1].Blink) & 0x2000) != 0
      && BYTE1(v9[1].Blink) >= 6u )
    {
      WPP_SF_d(v9[1].Flink, 150, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, 615);
    }
  }
  return 615;
}

```

## disassembly

```asm
0x18002040c  push    rbx
0x18002040e  push    rbp
0x18002040f  push    rsi
0x180020410  push    rdi
0x180020411  push    r12
0x180020413  push    r13
0x180020415  push    r14
0x180020417  push    r15
0x180020419  sub     rsp, 58h
0x18002041d  mov     r14b, r9b
0x180020420  mov     r12b, r8b
0x180020423  mov     r15d, edx
0x180020426  mov     rbx, rcx
0x180020429  mov     rcx, cs:WPP_GLOBAL_Control
0x180020430  lea     r13, WPP_GLOBAL_Control
0x180020437  lea     rbp, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18002043e  mov     esi, 2000h
0x180020443  cmp     rcx, r13
0x180020446  jz      short loc_180020464
0x180020448  test    [rcx+1Ch], esi
0x18002044b  jz      short loc_180020464
0x18002044d  cmp     byte ptr [rcx+19h], 6
0x180020451  jb      short loc_180020464
0x180020453  mov     rcx, [rcx+10h]
0x180020457  mov     edx, 94h
0x18002045c  mov     r8, rbp
0x18002045f  call    WPP_SF_
0x180020464  call    cs:__imp_GetCurrentProcessId
0x18002046a  mov     edi, eax
0x18002046c  test    rbx, rbx
0x18002046f  jnz     short loc_1800204DA
0x180020471  mov     rcx, cs:WPP_GLOBAL_Control
0x180020478  mov     ebx, 267h
0x18002047d  cmp     rcx, r13
0x180020480  jz      short loc_1800204D3
0x180020482  test    [rcx+1Ch], esi
0x180020485  jz      short loc_1800204AF
0x180020487  mov     esi, 2
0x18002048c  cmp     [rcx+19h], sil
0x180020490  jb      short loc_1800204AA
0x180020492  mov     rcx, [rcx+10h]
0x180020496  mov     edx, 95h
0x18002049b  mov     r8, rbp
0x18002049e  call    WPP_SF_
0x1800204a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800204aa  mov     esi, 2000h
0x1800204af  cmp     rcx, r13
0x1800204b2  jz      short loc_1800204D3
0x1800204b4  test    [rcx+1Ch], esi
0x1800204b7  jz      short loc_1800204D3
0x1800204b9  cmp     byte ptr [rcx+19h], 6
0x1800204bd  jb      short loc_1800204D3
0x1800204bf  mov     rcx, [rcx+10h]
0x1800204c3  mov     edx, 96h
0x1800204c8  mov     r9d, ebx
0x1800204cb  mov     r8, rbp
0x1800204ce  call    WPP_SF_d
0x1800204d3  mov     eax, ebx
0x1800204d5  jmp     loc_180020DA7
0x1800204da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800204e1  cmp     rcx, r13
0x1800204e4  jz      short loc_180020514
0x1800204e6  test    [rcx+1Ch], esi
0x1800204e9  jz      short loc_180020514
0x1800204eb  cmp     byte ptr [rcx+19h], 4
0x1800204ef  jb      short loc_180020514
0x1800204f1  movzx   eax, word ptr [rbx+2Ch]
0x1800204f5  mov     edx, 97h
0x1800204fa  mov     r9, [rbx]
0x1800204fd  mov     r8, rbp
0x180020500  mov     rcx, [rcx+10h]
0x180020504  mov     dword ptr [rsp+98h+var_78], eax
0x180020508  call    WPP_SF_qD
0x18002050d  mov     rcx, cs:WPP_GLOBAL_Control
0x180020514  cmp     dword ptr [rbx+1Ch], 3
0x180020518  jnz     short loc_18002057F
0x18002051a  cmp     dword ptr [rbx+1D8h], 9
0x180020521  jnz     short loc_18002057F
0x180020523  cmp     rcx, r13
0x180020526  jz      short loc_180020548
0x180020528  test    [rcx+1Ch], esi
0x18002052b  jz      short loc_180020548
0x18002052d  cmp     byte ptr [rcx+19h], 4
0x180020531  jb      short loc_180020548
0x180020533  mov     rcx, [rcx+10h]
0x180020537  lea     r9, [rbx+8]
0x18002053b  mov     edx, 98h
0x180020540  mov     r8, rbp
0x180020543  call    WPP_SF_s
0x180020548  mov     dword ptr [rbx+430h], 1
0x180020552  mov     rcx, cs:WPP_GLOBAL_Control
0x180020559  cmp     rcx, r13
0x18002055c  jz      loc_180020DA5
0x180020562  test    [rcx+1Ch], esi
0x180020565  jz      loc_180020DA5
0x18002056b  cmp     byte ptr [rcx+19h], 6
0x18002056f  jb      loc_180020DA5
0x180020575  mov     edx, 99h
0x18002057a  jmp     loc_180020D92
0x18002057f  mov     ebp, 1
0x180020584  cmp     [rbx+18h], ebp
0x180020587  jnz     short loc_1800205AF
0x180020589  cmp     rcx, r13
0x18002058c  jz      loc_180020DA5
0x180020592  test    [rcx+1Ch], esi
0x180020595  jz      loc_180020DA5
0x18002059b  cmp     byte ptr [rcx+19h], 6
0x18002059f  jb      loc_180020DA5
0x1800205a5  mov     edx, 9Ah
0x1800205aa  jmp     loc_180020D92
0x1800205af  cmp     [rbx+110h], edi
0x1800205b5  jnz     loc_18002065A
0x1800205bb  cmp     r15d, edi
0x1800205be  jz      loc_18002065A
0x1800205c4  mov     rax, [rbx+428h]
0x1800205cb  test    rax, rax
0x1800205ce  jz      loc_18002065A
0x1800205d4  lea     rcx, [rax+0B8h]; lpString
0x1800205db  call    IsRouterPhonebook
0x1800205e0  test    eax, eax
0x1800205e2  jz      short loc_180020653
0x1800205e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800205eb  cmp     rcx, r13
0x1800205ee  jz      short loc_180020610
0x1800205f0  test    [rcx+1Ch], esi
0x1800205f3  jz      short loc_180020610
0x1800205f5  cmp     byte ptr [rcx+19h], 4
0x1800205f9  jb      short loc_180020610
0x1800205fb  mov     rcx, [rcx+10h]
0x1800205ff  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180020606  mov     edx, 9Bh
0x18002060b  call    WPP_SF_
0x180020610  mov     edi, 5
0x180020615  lea     r8, aPortcloseAcces; "PortClose: Access was denied"
0x18002061c  mov     edx, edi
0x18002061e  mov     rcx, rbx
0x180020621  call    TelemetryEventWriteStateChange
0x180020626  mov     rcx, cs:WPP_GLOBAL_Control
0x18002062d  cmp     rcx, r13
0x180020630  jz      loc_1800206F7
0x180020636  test    [rcx+1Ch], esi
0x180020639  jz      loc_1800206F7
0x18002063f  cmp     byte ptr [rcx+19h], 6
0x180020643  jb      loc_1800206F7
0x180020649  mov     edx, 9Ch
0x18002064e  jmp     loc_1800206E4
0x180020653  mov     rcx, cs:WPP_GLOBAL_Control
0x18002065a  cmp     [rbx+2Ch], bp
0x18002065e  jnz     loc_1800206FE
0x180020664  cmp     edi, [rbx+1CCh]
0x18002066a  jnz     loc_1800206FE
0x180020670  xor     edi, edi
0x180020672  test    r14b, r14b
0x180020675  jnz     loc_180020700
0x18002067b  cmp     rcx, r13
0x18002067e  jz      short loc_1800206AB
0x180020680  test    [rcx+1Ch], esi
0x180020683  jz      short loc_1800206AB
0x180020685  lea     esi, [rdi+2]
0x180020688  cmp     [rcx+19h], sil
0x18002068c  jb      short loc_1800206A6
0x18002068e  mov     rcx, [rcx+10h]
0x180020692  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180020699  mov     edx, 9Dh
0x18002069e  mov     r9d, r15d
0x1800206a1  call    WPP_SF_d
0x1800206a6  mov     esi, 2000h
0x1800206ab  mov     edi, 5
0x1800206b0  lea     r8, aPortcloseAttem; "PortClose: Attempt to close server port"...
0x1800206b7  mov     edx, edi
0x1800206b9  mov     rcx, rbx
0x1800206bc  call    TelemetryEventWriteStateChange
0x1800206c1  and     dword ptr [rbx+4C8h], 0FFFFFFF3h
0x1800206c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800206cf  cmp     rcx, r13
0x1800206d2  jz      short loc_1800206F7
0x1800206d4  test    [rcx+1Ch], esi
0x1800206d7  jz      short loc_1800206F7
0x1800206d9  cmp     byte ptr [rcx+19h], 6
0x1800206dd  jb      short loc_1800206F7
0x1800206df  mov     edx, 9Eh
0x1800206e4  mov     rcx, [rcx+10h]
0x1800206e8  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x1800206ef  mov     r9d, edi
0x1800206f2  call    WPP_SF_d
0x1800206f7  mov     eax, edi
0x1800206f9  jmp     loc_180020DA7
0x1800206fe  xor     edi, edi
0x180020700  cmp     r15d, [rbx+110h]
0x180020707  mov     esi, 2
0x18002070c  setz    r13b
0x180020710  cmp     [rbx+2Ch], si
0x180020714  jnz     short loc_180020762
0x180020716  cmp     [rbx+1CCh], r15d
0x18002071d  jnz     short loc_180020762
0x18002071f  cmp     [rbx+10Ch], edi
0x180020725  jnz     short loc_180020762
0x180020727  lea     rdx, WPP_GLOBAL_Control
0x18002072e  cmp     rcx, rdx
0x180020731  jz      short loc_180020762
0x180020733  test    dword ptr [rcx+1Ch], 2000h
0x18002073a  jz      short loc_180020762
0x18002073c  cmp     [rcx+19h], sil
0x180020740  jb      short loc_180020762
0x180020742  mov     rcx, [rcx+10h]
0x180020746  lea     r9, [rbx+8]
0x18002074a  mov     edx, 9Fh
0x18002074f  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180020756  call    WPP_SF_s
0x18002075b  mov     rcx, cs:WPP_GLOBAL_Control
0x180020762  cmp     [rbx+1D8h], edi
0x180020768  jz      short loc_18002079A
0x18002076a  cmp     dword ptr [rbx+1Ch], 3
0x18002076e  jz      short loc_18002079A
0x180020770  mov     eax, [rbx+108h]
0x180020776  test    eax, eax
0x180020778  jz      short loc_180020781
0x18002077a  cmp     eax, 258h
0x18002077f  jnz     short loc_18002078B
0x180020781  mov     dword ptr [rbx+108h], 26Bh
0x18002078b  mov     rcx, rbx
0x18002078e  call    CompleteAsyncRequest
0x180020793  mov     rcx, cs:WPP_GLOBAL_Control
0x18002079a  cmp     [rbx+478h], rdi
0x1800207a1  jz      short loc_180020813
0x1800207a3  lea     rax, WPP_GLOBAL_Control
0x1800207aa  cmp     rcx, rax
0x1800207ad  jz      short loc_1800207D3
0x1800207af  test    dword ptr [rcx+1Ch], 2000h
0x1800207b6  jz      short loc_1800207D3
0x1800207b8  cmp     byte ptr [rcx+19h], 4
0x1800207bc  jb      short loc_1800207D3
0x1800207be  mov     rcx, [rcx+10h]
0x1800207c2  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x1800207c9  mov     edx, 0A0h
0x1800207ce  call    WPP_SF_
0x1800207d3  mov     rax, [rbx+480h]
0x1800207da  xor     r9d, r9d
0x1800207dd  mov     r8d, [rbx+488h]
0x1800207e4  mov     rcx, rbx
0x1800207e7  mov     rdx, [rbx+478h]
0x1800207ee  mov     [rsp+98h+var_58], rax
0x1800207f3  mov     [rsp+98h+var_60], rdi
0x1800207f8  mov     [rsp+98h+var_68], rdi
0x1800207fd  mov     [rsp+98h+var_70], rdi
0x180020802  mov     [rsp+98h+var_78], rdi
0x180020807  call    SetDialMachineEventHandleCommon
0x18002080c  mov     rcx, cs:WPP_GLOBAL_Control
0x180020813  lea     rax, WPP_GLOBAL_Control
0x18002081a  cmp     rcx, rax
0x18002081d  jz      short loc_180020846
0x18002081f  test    dword ptr [rcx+1Ch], 2000h
0x180020826  jz      short loc_180020846
0x180020828  cmp     byte ptr [rcx+19h], 4
0x18002082c  jb      short loc_180020846
0x18002082e  mov     r9, [rbx]
0x180020831  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180020838  mov     rcx, [rcx+10h]
0x18002083c  mov     edx, 0A1h
0x180020841  call    WPP_SF_q
0x180020846  lea     rcx, [rbx+1A8h]
0x18002084d  call    FreeNotifierList
0x180020852  mov     rcx, [rbx+230h]; hMem
0x180020859  test    rcx, rcx
0x18002085c  jz      short loc_180020871
0x18002085e  call    cs:__imp_LocalFree
0x180020864  mov     [rbx+230h], rdi
0x18002086b  mov     [rbx+238h], edi
0x180020871  test    r14b, r14b
0x180020874  jnz     short loc_1800208E7
0x180020876  mov     rax, [rbx+4D0h]
0x18002087d  cmp     word ptr [rax+60h], 9
0x180020882  jnz     short loc_1800208E7
0x180020884  mov     rcx, rbx
0x180020887  call    DisableClientIpSecFilter
0x18002088c  xor     r14d, r14d
0x18002088f  test    eax, eax
0x180020891  jz      short loc_1800208D2
0x180020893  mov     rcx, cs:WPP_GLOBAL_Control
0x18002089a  lea     rdx, WPP_GLOBAL_Control
0x1800208a1  cmp     rcx, rdx
0x1800208a4  jz      short loc_1800208D2
0x1800208a6  test    dword ptr [rcx+1Ch], 2000h
0x1800208ad  jz      short loc_1800208D2
0x1800208af  cmp     [rcx+19h], sil
0x1800208b3  jb      short loc_1800208D2
0x1800208b5  mov     rcx, [rcx+10h]
0x1800208b9  lea     r9, [rbx+8]
0x1800208bd  mov     edx, 0A2h
0x1800208c2  mov     dword ptr [rsp+98h+var_78], eax
0x1800208c6  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x1800208cd  call    WPP_SF_sd
0x1800208d2  mov     rcx, [rbx+510h]; hMem
0x1800208d9  call    FreeIkeInitiateContext
0x1800208de  mov     [rbx+510h], r14
0x1800208e5  jmp     short loc_1800208EA
0x1800208e7  xor     r14d, r14d
0x1800208ea  mov     rcx, [rbx+518h]
0x1800208f1  test    rcx, rcx
0x1800208f4  jz      short loc_180020914
  ... truncated ...
```
