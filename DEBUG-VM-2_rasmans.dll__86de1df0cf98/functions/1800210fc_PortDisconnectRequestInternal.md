# PortDisconnectRequestInternal

- ea: `0x1800210fc`
- end: `0x180021864`
- name: `PortDisconnectRequestInternal`
- size: `1896`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021060`
- `0x18004ce78`

## callees

- `0x180005d18`
- `0x180005e0c`
- `0x180005e34`
- `0x180005f1c`
- `0x18000bfb0`
- `0x18000c00c`
- `0x180013f44`
- `0x1800210fc`
- `0x180032b0c`
- `0x180039ea0`
- `0x18003ca44`
- `0x1800448e0`
- `0x1800486b4`
- `0x18007c974`
- `0x1800e9010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180021153`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180021153`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021313`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800213d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002180c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021313`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800213d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002180c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800213c9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180021803`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800213c9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180021803`

## string_xrefs

- `0x1800217ea`: `PortDisconnectRequestInternal: port is already disconnecting`
- `0x1800212ff`: `PortDisconnectRequestInternal: Access was denied`
- `0x1800213b5`: `PortDisconnectRequestInternal: Access was denied`
- `0x1800216ed`: `PortDisconnectRequestInternal: SendMessageToProtocolEngine: Failed`

## pseudocode

```c
double __fastcall PortDisconnectRequestInternal(__int64 a1, _DWORD *a2, __int64 a3, int a4)
{
  double result; // xmm0_8
  DWORD CurrentProcessId; // ebp
  DWORD v10; // esi
  struct _LIST_ENTRY *v11; // rcx
  __int64 v12; // rdx
  void *v13; // rdi
  __int64 v14; // rcx
  __int64 v15; // rax
  unsigned int v16; // eax
  struct _LIST_ENTRY *v17; // rcx
  _QWORD *v18; // rcx
  __int64 (*v19)(void); // rax
  unsigned int v20; // edi
  struct _LIST_ENTRY *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r9
  unsigned int v24; // eax
  int v25; // [rsp+80h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    result = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 260, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
  }
  CurrentProcessId = GetCurrentProcessId();
  if ( a2 && *a2 )
    v10 = a2[2];
  else
    v10 = *(_DWORD *)(a3 + 8);
  if ( !a1 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      result = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 261, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
    }
    *(_DWORD *)a3 = 615;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        result = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 262, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
        v11 = WPP_GLOBAL_Control;
      }
      if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v11[1].Blink) & 0x2000) != 0
        && BYTE1(v11[1].Blink) >= 6u )
      {
        v12 = 263;
        return WPP_SF_(v11[1].Flink, v12, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
      }
    }
    return result;
  }
  if ( a4 )
  {
    v13 = *(void **)a3;
    goto LABEL_43;
  }
  v13 = 0;
  if ( (unsigned __int64)(*(_QWORD *)a3 - 1LL) > 0xFFFFFFFFFFFFFFFDuLL
    || (v13 = (void *)ValidateHandleForRasman(*(HANDLE *)a3, v10),
        (((unsigned __int64)v13 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0) )
  {
    if ( *(_DWORD *)(a1 + 272) == CurrentProcessId )
    {
      if ( v10 == CurrentProcessId )
        goto LABEL_58;
      if ( (*(_BYTE *)(a1 + 40) & 8) == 0 )
      {
        v14 = *(_QWORD *)(a1 + 1064);
        if ( v14 )
        {
          if ( (unsigned int)IsRouterPhonebook((LPCWSTR)(v14 + 184)) )
          {
            *(_DWORD *)a3 = 5;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_sd(
                WPP_GLOBAL_Control[1].Flink,
                265,
                (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                a1 + 8,
                5);
            }
            TelemetryEventWriteStateChange(a1, 5, "PortDisconnectRequestInternal: Access was denied");
            CloseHandle(v13);
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
            {
              v12 = 266;
              return WPP_SF_(v11[1].Flink, v12, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
            }
            return result;
          }
        }
      }
LABEL_44:
      if ( *(_QWORD *)(a1 + 1064) )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
        {
          result = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 267, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
        }
        if ( !(unsigned int)CheckIfAllowedToManageConnection(
                              *(PSID *)(*(_QWORD *)(a1 + 1064) + 96LL),
                              *(_DWORD *)(a1 + 40) & 8,
                              0) )
        {
          *(_DWORD *)a3 = 5;
          TelemetryEventWriteStateChange(a1, 5, "PortDisconnectRequestInternal: Access was denied");
          if ( a4 )
            SetEvent(v13);
          CloseHandle(v13);
          if ( v13 == *(void **)(a1 + 1280) )
            *(_QWORD *)(a1 + 1280) = -1;
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
          {
            v12 = 268;
            return WPP_SF_(v11[1].Flink, v12, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
          }
          return result;
        }
      }
LABEL_58:
      if ( *(_DWORD *)(a1 + 28) != 3 )
      {
        if ( a4 )
          goto LABEL_80;
        if ( ((*(_QWORD *)(a1 + 1280) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        {
          v15 = *(_QWORD *)(a1 + 1064);
          if ( v15 && *(_DWORD *)(v15 + 68) == 1 )
          {
            v25 = 0;
            *(_DWORD *)g_RasEvent = 64;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
            {
              result = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 271, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
            }
            v16 = DwSendNotificationInternal(*(_QWORD *)(a1 + 1064), g_RasEvent);
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
            {
              result = WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 272, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v16);
            }
            QueueCloseConnections(*(_QWORD *)(a1 + 1064), v13, &v25);
            if ( v25 )
            {
              *(_QWORD *)(a1 + 1280) = v13;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
              {
                result = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 273, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
              }
              *(_DWORD *)a3 = 600;
              v11 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
              {
                v12 = 274;
                return WPP_SF_(v11[1].Flink, v12, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
              }
              return result;
            }
          }
LABEL_80:
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
          {
            WPP_SF_sqD(
              WPP_GLOBAL_Control[1].Flink,
              275,
              (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
              a1 + 8,
              *(_QWORD *)(a1 + 1064),
              *(_DWORD *)(a1 + 1224));
            v17 = WPP_GLOBAL_Control;
          }
          if ( !*(_QWORD *)(a1 + 1064) || (*(_DWORD *)(a1 + 1224) & 0x14) != 4 )
          {
            if ( v17 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(v17[1].Blink) & 0x2000) != 0
              && BYTE1(v17[1].Blink) >= 4u )
            {
              WPP_SF_s(v17[1].Flink, 280, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, a1 + 8);
            }
            *(_DWORD *)(a1 + 1324) = 0;
            v20 = DisconnectPort((_QWORD *)a1, v13, 0);
            goto LABEL_115;
          }
          if ( v17 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v17[1].Blink) & 0x2000) != 0
            && BYTE1(v17[1].Blink) >= 4u )
          {
            WPP_SF_q(v17[1].Flink, 276, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v13);
          }
          v18 = g_ProtocolEngMsg;
          *(_QWORD *)(a1 + 1280) = v13;
          *(_DWORD *)v18 = 1;
          v18[1] = *(_QWORD *)a1;
          v18[2] = 0;
          *((_DWORD *)v18 + 6) = 0;
          v19 = (__int64 (*)(void))qword_18010A098[8 * (__int64)*(int *)(a1 + 1360)];
          if ( v19 )
          {
            v24 = v19();
            v20 = v24;
            if ( !v24 )
            {
LABEL_101:
              v21 = WPP_GLOBAL_Control;
              goto LABEL_102;
            }
            v21 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
              goto LABEL_107;
            if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
LABEL_102:
              if ( v21 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(v21[1].Blink) & 0x2000) != 0
                && BYTE1(v21[1].Blink) >= 2u )
              {
                WPP_SF_sd(v21[1].Flink, 279, (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, a1 + 8, v20);
              }
              if ( !v20 )
              {
                v20 = 600;
                goto LABEL_115;
              }
LABEL_107:
              if ( v20 != 600 )
                goto LABEL_108;
LABEL_115:
              *(_DWORD *)a3 = v20;
              v11 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
              {
                if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
                {
                  WPP_SF_s(WPP_GLOBAL_Control[1].Flink, 281, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, a1 + 8);
                  v11 = WPP_GLOBAL_Control;
                }
                if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && (HIDWORD(v11[1].Blink) & 0x2000) != 0
                  && BYTE1(v11[1].Blink) >= 6u )
                {
                  v12 = 282;
                  return WPP_SF_(v11[1].Flink, v12, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
                }
              }
              return result;
            }
            v22 = 278;
            v23 = v24;
          }
          else
          {
            v20 = 839;
            v21 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            {
LABEL_108:
              TelemetryEventWriteStateChange(
                a1,
                v20,
                "PortDisconnectRequestInternal: SendMessageToProtocolEngine: Failed");
              goto LABEL_115;
            }
            if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
              goto LABEL_102;
            v22 = 277;
            v23 = 839;
          }
          result = WPP_SF_d(v21[1].Flink, v22, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v23);
          goto LABEL_101;
        }
      }
      *(_DWORD *)a3 = 617;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
      {
        WPP_SF_s(WPP_GLOBAL_Control[1].Flink, 269, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, a1 + 8);
      }
      TelemetryEventWriteStateChange(a1, 617, "PortDisconnectRequestInternal: port is already disconnecting");
      if ( a4 )
        SetEvent(v13);
      CloseHandle(v13);
      if ( v13 == *(void **)(a1 + 1280) )
        *(_QWORD *)(a1 + 1280) = -1;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
      {
        v12 = 270;
        return WPP_SF_(v11[1].Flink, v12, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
      }
      return result;
    }
LABEL_43:
    if ( v10 == CurrentProcessId )
      goto LABEL_58;
    goto LABEL_44;
  }
  TelemetryEventWriteStateChange(a1, 2147942487LL, "PortDisconnectRequestInternal: Invalid Handle");
  *(_DWORD *)a3 = -2147024809;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    v12 = 264;
    return WPP_SF_(v11[1].Flink, v12, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x1800210fc  push    rbx
0x1800210fe  push    rbp
0x1800210ff  push    rsi
0x180021100  push    rdi
0x180021101  push    r12
0x180021103  push    r13
0x180021105  push    r14
0x180021107  push    r15
0x180021109  sub     rsp, 38h
0x18002110d  mov     r15d, r9d
0x180021110  mov     r14, r8
0x180021113  mov     rdi, rdx
0x180021116  mov     rbx, rcx
0x180021119  mov     rcx, cs:WPP_GLOBAL_Control
0x180021120  lea     r13, WPP_GLOBAL_Control
0x180021127  mov     r12d, 2000h
0x18002112d  cmp     rcx, r13
0x180021130  jz      short loc_180021153
0x180021132  test    [rcx+1Ch], r12d
0x180021136  jz      short loc_180021153
0x180021138  cmp     byte ptr [rcx+19h], 6
0x18002113c  jb      short loc_180021153
0x18002113e  mov     rcx, [rcx+10h]
0x180021142  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180021149  mov     edx, 104h
0x18002114e  call    WPP_SF_
0x180021153  call    cs:__imp_GetCurrentProcessId
0x180021159  mov     ebp, eax
0x18002115b  test    rdi, rdi
0x18002115e  jz      short loc_18002116A
0x180021160  cmp     dword ptr [rdi], 0
0x180021163  jz      short loc_18002116A
0x180021165  mov     esi, [rdi+8]
0x180021168  jmp     short loc_18002116E
0x18002116a  mov     esi, [r14+8]
0x18002116e  test    rbx, rbx
0x180021171  jnz     loc_18002120A
0x180021177  mov     rcx, cs:WPP_GLOBAL_Control
0x18002117e  cmp     rcx, r13
0x180021181  jz      short loc_1800211A4
0x180021183  test    [rcx+1Ch], r12d
0x180021187  jz      short loc_1800211A4
0x180021189  cmp     byte ptr [rcx+19h], 2
0x18002118d  jb      short loc_1800211A4
0x18002118f  mov     rcx, [rcx+10h]
0x180021193  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18002119a  mov     edx, 105h
0x18002119f  call    WPP_SF_
0x1800211a4  mov     dword ptr [r14], 267h
0x1800211ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800211b2  cmp     rcx, r13
0x1800211b5  jz      loc_180021853
0x1800211bb  test    [rcx+1Ch], r12d
0x1800211bf  jz      short loc_1800211E3
0x1800211c1  cmp     byte ptr [rcx+19h], 2
0x1800211c5  jb      short loc_1800211E3
0x1800211c7  mov     rcx, [rcx+10h]
0x1800211cb  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x1800211d2  mov     edx, 106h
0x1800211d7  call    WPP_SF_
0x1800211dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800211e3  cmp     rcx, r13
0x1800211e6  jz      loc_180021853
0x1800211ec  test    [rcx+1Ch], r12d
0x1800211f0  jz      loc_180021853
0x1800211f6  cmp     byte ptr [rcx+19h], 6
0x1800211fa  jb      loc_180021853
0x180021200  mov     edx, 107h
0x180021205  jmp     loc_180021843
0x18002120a  test    r15d, r15d
0x18002120d  jnz     loc_180021347
0x180021213  mov     rcx, [r14]; hSourceHandle
0x180021216  xor     edi, edi
0x180021218  lea     rax, [rcx-1]
0x18002121c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180021220  ja      short loc_180021280
0x180021222  mov     edx, esi; dwProcessId
0x180021224  call    ValidateHandleForRasman
0x180021229  mov     rdi, rax
0x18002122c  lea     rcx, [rax+1]
0x180021230  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180021237  jnz     short loc_180021280
0x180021239  mov     edi, 80070057h
0x18002123e  lea     r8, aPortdisconnect; "PortDisconnectRequestInternal: Invalid "...
0x180021245  mov     edx, edi
0x180021247  mov     rcx, rbx
0x18002124a  call    TelemetryEventWriteStateChange
0x18002124f  mov     [r14], edi
0x180021252  mov     rcx, cs:WPP_GLOBAL_Control
0x180021259  cmp     rcx, r13
0x18002125c  jz      loc_180021853
0x180021262  test    [rcx+1Ch], r12d
0x180021266  jz      loc_180021853
0x18002126c  cmp     byte ptr [rcx+19h], 6
0x180021270  jb      loc_180021853
0x180021276  mov     edx, 108h
0x18002127b  jmp     loc_180021843
0x180021280  cmp     [rbx+110h], ebp
0x180021286  jnz     loc_18002134A
0x18002128c  cmp     esi, ebp
0x18002128e  jz      loc_18002141A
0x180021294  test    byte ptr [rbx+28h], 8
0x180021298  jnz     loc_180021352
0x18002129e  mov     rcx, [rbx+428h]
0x1800212a5  test    rcx, rcx
0x1800212a8  jz      loc_180021352
0x1800212ae  add     rcx, 0B8h; lpString
0x1800212b5  call    IsRouterPhonebook
0x1800212ba  test    eax, eax
0x1800212bc  jz      loc_180021352
0x1800212c2  mov     esi, 5
0x1800212c7  mov     [r14], esi
0x1800212ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800212d1  cmp     rcx, r13
0x1800212d4  jz      short loc_1800212FF
0x1800212d6  test    [rcx+1Ch], r12d
0x1800212da  jz      short loc_1800212FF
0x1800212dc  cmp     byte ptr [rcx+19h], 2
0x1800212e0  jb      short loc_1800212FF
0x1800212e2  mov     rcx, [rcx+10h]
0x1800212e6  lea     r9, [rbx+8]
0x1800212ea  mov     edx, 109h
0x1800212ef  mov     dword ptr [rsp+78h+var_58], esi
0x1800212f3  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x1800212fa  call    WPP_SF_sd
0x1800212ff  lea     r8, aPortdisconnect_1; "PortDisconnectRequestInternal: Access w"...
0x180021306  mov     edx, esi
0x180021308  mov     rcx, rbx
0x18002130b  call    TelemetryEventWriteStateChange
0x180021310  mov     rcx, rdi; hObject
0x180021313  call    cs:__imp_CloseHandle
0x180021319  mov     rcx, cs:WPP_GLOBAL_Control
0x180021320  cmp     rcx, r13
0x180021323  jz      loc_180021853
0x180021329  test    [rcx+1Ch], r12d
0x18002132d  jz      loc_180021853
0x180021333  cmp     byte ptr [rcx+19h], 6
0x180021337  jb      loc_180021853
0x18002133d  mov     edx, 10Ah
0x180021342  jmp     loc_180021843
0x180021347  mov     rdi, [r14]
0x18002134a  cmp     esi, ebp
0x18002134c  jz      loc_18002141A
0x180021352  cmp     qword ptr [rbx+428h], 0
0x18002135a  jz      loc_18002141A
0x180021360  mov     rcx, cs:WPP_GLOBAL_Control
0x180021367  cmp     rcx, r13
0x18002136a  jz      short loc_18002138D
0x18002136c  test    [rcx+1Ch], r12d
0x180021370  jz      short loc_18002138D
0x180021372  cmp     byte ptr [rcx+19h], 4
0x180021376  jb      short loc_18002138D
0x180021378  mov     rcx, [rcx+10h]
0x18002137c  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180021383  mov     edx, 10Bh
0x180021388  call    WPP_SF_
0x18002138d  mov     rcx, [rbx+428h]
0x180021394  xor     r8d, r8d
0x180021397  mov     edx, [rbx+28h]
0x18002139a  and     edx, 8
0x18002139d  mov     rcx, [rcx+60h]; pSid2
0x1800213a1  call    CheckIfAllowedToManageConnection
0x1800213a6  test    eax, eax
0x1800213a8  jnz     short loc_18002141A
0x1800213aa  lea     esi, [rax+5]
0x1800213ad  mov     rcx, rbx
0x1800213b0  mov     edx, esi
0x1800213b2  mov     [r14], esi
0x1800213b5  lea     r8, aPortdisconnect_1; "PortDisconnectRequestInternal: Access w"...
0x1800213bc  call    TelemetryEventWriteStateChange
0x1800213c1  test    r15d, r15d
0x1800213c4  jz      short loc_1800213CF
0x1800213c6  mov     rcx, rdi; hEvent
0x1800213c9  call    cs:__imp_SetEvent
0x1800213cf  mov     rcx, rdi; hObject
0x1800213d2  call    cs:__imp_CloseHandle
0x1800213d8  cmp     rdi, [rbx+500h]
0x1800213df  jnz     short loc_1800213EC
0x1800213e1  mov     qword ptr [rbx+500h], 0FFFFFFFFFFFFFFFFh
0x1800213ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800213f3  cmp     rcx, r13
0x1800213f6  jz      loc_180021853
0x1800213fc  test    [rcx+1Ch], r12d
0x180021400  jz      loc_180021853
0x180021406  cmp     byte ptr [rcx+19h], 6
0x18002140a  jb      loc_180021853
0x180021410  mov     edx, 10Ch
0x180021415  jmp     loc_180021843
0x18002141a  cmp     dword ptr [rbx+1Ch], 3
0x18002141e  jz      loc_1800217B1
0x180021424  test    r15d, r15d
0x180021427  jnz     loc_18002156D
0x18002142d  mov     rax, [rbx+500h]
0x180021434  inc     rax
0x180021437  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002143d  jnz     loc_1800217B1
0x180021443  mov     rax, [rbx+428h]
0x18002144a  test    rax, rax
0x18002144d  jz      loc_18002156D
0x180021453  cmp     dword ptr [rax+44h], 1
0x180021457  jnz     loc_18002156D
0x18002145d  mov     [rsp+78h+arg_0], r15d
0x180021465  mov     cs:g_RasEvent, 40h ; '@'
0x18002146f  mov     rcx, cs:WPP_GLOBAL_Control
0x180021476  cmp     rcx, r13
0x180021479  jz      short loc_1800214A0
0x18002147b  test    [rcx+1Ch], r12d
0x18002147f  jz      short loc_1800214A0
0x180021481  lea     esi, [r15+5]
0x180021485  cmp     [rcx+19h], sil
0x180021489  jb      short loc_1800214A0
0x18002148b  mov     rcx, [rcx+10h]
0x18002148f  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180021496  mov     edx, 10Fh
0x18002149b  call    WPP_SF_
0x1800214a0  mov     rcx, [rbx+428h]
0x1800214a7  lea     rdx, g_RasEvent
0x1800214ae  call    DwSendNotificationInternal
0x1800214b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800214ba  cmp     rcx, r13
0x1800214bd  jz      short loc_1800214E3
0x1800214bf  test    [rcx+1Ch], r12d
0x1800214c3  jz      short loc_1800214E3
0x1800214c5  cmp     byte ptr [rcx+19h], 4
0x1800214c9  jb      short loc_1800214E3
0x1800214cb  mov     rcx, [rcx+10h]
0x1800214cf  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x1800214d6  mov     edx, 110h
0x1800214db  mov     r9d, eax
0x1800214de  call    WPP_SF_d
0x1800214e3  mov     rcx, [rbx+428h]
0x1800214ea  lea     r8, [rsp+78h+arg_0]
0x1800214f2  mov     rdx, rdi
0x1800214f5  call    QueueCloseConnections
0x1800214fa  cmp     [rsp+78h+arg_0], 0
0x180021502  jz      short loc_18002156D
0x180021504  mov     [rbx+500h], rdi
0x18002150b  mov     rcx, cs:WPP_GLOBAL_Control
0x180021512  cmp     rcx, r13
0x180021515  jz      short loc_180021538
0x180021517  test    [rcx+1Ch], r12d
0x18002151b  jz      short loc_180021538
0x18002151d  cmp     byte ptr [rcx+19h], 4
0x180021521  jb      short loc_180021538
0x180021523  mov     rcx, [rcx+10h]
0x180021527  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18002152e  mov     edx, 111h
0x180021533  call    WPP_SF_
0x180021538  mov     dword ptr [r14], 258h
0x18002153f  mov     rcx, cs:WPP_GLOBAL_Control
0x180021546  cmp     rcx, r13
0x180021549  jz      loc_180021853
0x18002154f  test    [rcx+1Ch], r12d
0x180021553  jz      loc_180021853
0x180021559  cmp     byte ptr [rcx+19h], 6
0x18002155d  jb      loc_180021853
0x180021563  mov     edx, 112h
0x180021568  jmp     loc_180021843
0x18002156d  mov     rcx, cs:WPP_GLOBAL_Control
0x180021574  cmp     rcx, r13
0x180021577  jz      short loc_1800215BB
0x180021579  test    [rcx+1Ch], r12d
0x18002157d  jz      short loc_1800215BB
0x18002157f  cmp     byte ptr [rcx+19h], 4
0x180021583  jb      short loc_1800215BB
0x180021585  mov     eax, [rbx+4C8h]
0x18002158b  lea     r9, [rbx+8]
0x18002158f  mov     rcx, [rcx+10h]
0x180021593  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18002159a  mov     [rsp+78h+var_50], eax
0x18002159e  mov     edx, 113h
0x1800215a3  mov     rax, [rbx+428h]
0x1800215aa  mov     [rsp+78h+var_58], rax
0x1800215af  call    WPP_SF_sqD
0x1800215b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800215bb  cmp     qword ptr [rbx+428h], 0
0x1800215c3  jz      loc_180021707
0x1800215c9  mov     eax, [rbx+4C8h]
0x1800215cf  and     al, 14h
0x1800215d1  cmp     al, 4
0x1800215d3  jnz     loc_180021707
0x1800215d9  cmp     rcx, r13
0x1800215dc  jz      short loc_180021601
0x1800215de  test    [rcx+1Ch], r12d
0x1800215e2  jz      short loc_180021601
0x1800215e4  cmp     [rcx+19h], al
0x1800215e7  jb      short loc_180021601
0x1800215e9  mov     rcx, [rcx+10h]
0x1800215ed  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x1800215f4  mov     edx, 114h
0x1800215f9  mov     r9, rdi
0x1800215fc  call    WPP_SF_q
0x180021601  mov     rcx, cs:g_ProtocolEngMsg
0x180021608  lea     rdx, qword_18010A098
0x18002160f  mov     [rbx+500h], rdi
0x180021616  mov     dword ptr [rcx], 1
0x18002161c  mov     rax, [rbx]
0x18002161f  mov     [rcx+8], rax
0x180021623  mov     qword ptr [rcx+10h], 0
0x18002162b  mov     dword ptr [rcx+18h], 0
  ... truncated ...
```
