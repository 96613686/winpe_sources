# PortOpenRequest

- ea: `0x1800228d0`
- end: `0x18002313e`
- name: `PortOpenRequest`
- size: `2158`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180035b80`

## callees

- `0x180005c6c`
- `0x180005d18`
- `0x180005e0c`
- `0x180005e34`
- `0x180005e74`
- `0x180005f1c`
- `0x18000bf70`
- `0x18000bfb0`
- `0x18000c00c`
- `0x1800228d0`
- `0x180032118`
- `0x18003426c`
- `0x180037dc4`
- `0x180044d00`
- `0x180047714`
- `0x1800486b4`
- `0x1800e9010`

## import_xrefs

- `msvcrt!_stricmp` at `0x180022c72`
- `msvcrt!_stricmp` at `0x180022c72`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180022adc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180022adc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002295e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002295e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800229ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800229ca`

## string_xrefs

- `0x180022b85`: `PortOpenRequest: Port is already opened`
- `0x180022afa`: `PortOpenRequest: Port is not available`
- `0x180022a4f`: `PortOpenRequest: Port is in process of being removed`
- `0x180022e92`: `PortOpenRequest: Failed to open port`

## pseudocode

```c
double __fastcall PortOpenRequest(__int64 a1, _DWORD *a2, __int64 a3)
{
  struct _LIST_ENTRY *v5; // rcx
  double result; // xmm0_8
  int v7; // edi
  unsigned int v8; // ecx
  _QWORD *v9; // rbx
  unsigned __int8 *v10; // rax
  int v11; // edx
  int v12; // r8d
  __int64 v13; // r9
  struct _LIST_ENTRY *v14; // rcx
  struct _LIST_ENTRY *v15; // rcx
  __int64 v16; // rdx
  DWORD v17; // r15d
  unsigned int v18; // esi
  struct _LIST_ENTRY *v19; // rcx
  __int64 v20; // rax
  unsigned int v21; // eax
  unsigned int v22; // eax
  int v23; // ecx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rax
  char *v27; // rcx
  __int64 v28; // rax
  void *v29; // rbp

  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      result = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 128, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
      v5 = WPP_GLOBAL_Control;
    }
    if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v5[1].Blink) & 0x2000) != 0
      && BYTE1(v5[1].Blink) >= 6u )
    {
      result = WPP_SF_(v5[1].Flink, 191, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids);
    }
  }
  v7 = 0;
  EnterCriticalSection(&PcbLock);
  v8 = 0;
  if ( MaxPorts )
  {
    while ( 1 )
    {
      v9 = (_QWORD *)*((_QWORD *)Pcb + v8);
      if ( v9 && *((_DWORD *)v9 + 6) != 3 )
      {
        v10 = (unsigned __int8 *)(v9 + 1);
        do
        {
          v11 = v10[a3 + 32 - (_QWORD)(v9 + 1)];
          v12 = *v10 - v11;
          if ( v12 )
            break;
          ++v10;
        }
        while ( v11 );
        if ( !v12 )
          break;
      }
      if ( ++v8 >= MaxPorts )
        goto LABEL_20;
    }
    v7 = 1;
  }
  else
  {
    v9 = 0;
  }
LABEL_20:
  LeaveCriticalSection(&PcbLock);
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    LOBYTE(v13) = v7;
    WPP_SF_c(WPP_GLOBAL_Control[1].Flink, 192, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids, v13);
    v14 = WPP_GLOBAL_Control;
  }
  if ( !v7 || !v9 )
  {
    *(_DWORD *)a3 = 615;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_s(WPP_GLOBAL_Control[1].Flink, 129, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, a3 + 32);
        v15 = WPP_GLOBAL_Control;
      }
      if ( v15 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v15[1].Blink) & 0x2000) != 0
        && BYTE1(v15[1].Blink) >= 6u )
      {
        v16 = 130;
        return WPP_SF_(v15[1].Flink, v16, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
      }
    }
    return result;
  }
  if ( v14 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v14[1].Blink) & 0x2000) != 0
    && BYTE1(v14[1].Blink) >= 4u )
  {
    WPP_SF_qD(v14[1].Flink, 131, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, *v9, *((unsigned __int16 *)v9 + 22));
  }
  if ( *((_DWORD *)v9 + 6) == 2 )
  {
    TelemetryEventWriteStateChange(v9, 615, "PortOpenRequest: Port is in process of being removed");
    *(_DWORD *)a3 = 615;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 132, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, *v9);
        v15 = WPP_GLOBAL_Control;
      }
      if ( v15 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v15[1].Blink) & 0x2000) != 0
        && BYTE1(v15[1].Blink) >= 6u )
      {
        v16 = 133;
        return WPP_SF_(v15[1].Flink, v16, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
      }
    }
    return result;
  }
  if ( a2 && *a2 )
    v17 = a2[2];
  else
    v17 = *(_DWORD *)(a3 + 24);
  if ( v17 == GetCurrentProcessId() || (*((_BYTE *)v9 + 36) & 2) != 0 )
  {
    if ( (v9[153] & 8) != 0 )
    {
      TelemetryEventWriteStateChange(v9, 602, "PortOpenRequest: Port is already opened");
      *(_DWORD *)a3 = 602;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 136, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, *v9);
          v15 = WPP_GLOBAL_Control;
        }
        if ( v15 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v15[1].Blink) & 0x2000) != 0
          && BYTE1(v15[1].Blink) >= 6u )
        {
          v16 = 137;
          return WPP_SF_(v15[1].Flink, v16, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
        }
      }
      return result;
    }
    if ( *((_WORD *)v9 + 22) >= 2u )
    {
      v18 = 602;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      {
LABEL_106:
        TelemetryEventWriteStateChange(v9, v18, "PortOpenRequest: Failed to open port");
LABEL_124:
        *(_DWORD *)a3 = v18;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
        {
          return WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 147, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v18);
        }
        return result;
      }
      if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_Dd(
          WPP_GLOBAL_Control[1].Flink,
          138,
          WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
          *((unsigned __int16 *)v9 + 22),
          602);
LABEL_101:
        v19 = WPP_GLOBAL_Control;
      }
LABEL_102:
      if ( v19 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v19[1].Blink) & 0x2000) != 0
        && BYTE1(v19[1].Blink) >= 2u )
      {
        WPP_SF_sd(v19[1].Flink, 146, (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, (_DWORD)v9 + 8, v18);
      }
      goto LABEL_106;
    }
    if ( *((_DWORD *)v9 + 6) != 1 )
    {
      v22 = *((_DWORD *)v9 + 7);
      v18 = 0;
      if ( v22 != 1 )
      {
        if ( v22 <= 5 )
        {
          v23 = 37;
          if ( _bittest(&v23, v22) )
          {
            v19 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
            {
              WPP_SF_sd(
                WPP_GLOBAL_Control[1].Flink,
                140,
                (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                (_DWORD)v9 + 8,
                *((_DWORD *)v9 + 8));
              v19 = WPP_GLOBAL_Control;
            }
            if ( *((_DWORD *)v9 + 8) == 2 && (*((_DWORD *)v9 + 7) & 0xFFFFFFFD) == 0 )
            {
              ++*((_WORD *)v9 + 22);
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
              {
                WPP_SF_qD(
                  WPP_GLOBAL_Control[1].Flink,
                  141,
                  WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                  *v9,
                  *((unsigned __int16 *)v9 + 22));
              }
              *(_QWORD *)(a3 + 16) = *v9;
              *(_DWORD *)a3 = 0;
              v15 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
              {
                v16 = 142;
                return WPP_SF_(v15[1].Flink, v16, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
              }
              return result;
            }
            v18 = 602;
            if ( v19 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
              goto LABEL_106;
            if ( (HIDWORD(v19[1].Blink) & 0x2000) == 0 || BYTE1(v19[1].Blink) < 2u )
              goto LABEL_102;
            result = WPP_SF_d(v19[1].Flink, 143, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, 602);
            goto LABEL_101;
          }
        }
        FreeNotifierHandle((HANDLE)v9[58]);
        v9[58] = -1;
      }
      ReOpenBiplexPort(v9);
      goto LABEL_109;
    }
    if ( !_stricmp((const char *)v9[6], "rastapi") && (v20 = v9[133]) != 0 && !*(_BYTE *)(v20 + 445) )
    {
      v21 = ((__int64 (__fastcall *)(_QWORD *, _QWORD *, HANDLE, _QWORD, int))RastapiPortOpen)(
              v9 + 1,
              v9 + 27,
              hIoCompletionPort,
              *(unsigned int *)v9,
              2);
      v18 = v21;
      if ( !v21 )
        goto LABEL_109;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_78;
      }
      result = WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 139, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v21);
    }
    else
    {
      v18 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD *, HANDLE, _QWORD))(v9[6] + 24LL))(
              v9 + 1,
              v9 + 27,
              hIoCompletionPort,
              *(unsigned int *)v9);
    }
    v19 = WPP_GLOBAL_Control;
LABEL_78:
    if ( v18 )
      goto LABEL_102;
LABEL_109:
    SetRasmanServiceStopControl(0);
    *((_DWORD *)v9 + 6) = 0;
    SetPortConnState(v25, v24, v9, 4);
    *((_DWORD *)v9 + 67) = 3;
    *((_DWORD *)v9 + 331) = 3;
    ++*((_WORD *)v9 + 22);
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control[1].Flink,
        144,
        WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
        *v9,
        *((unsigned __int16 *)v9 + 22));
    }
    v9[28] = v9[27];
    v26 = 0;
    *((_DWORD *)v9 + 68) = v17;
    v9[70] = 0;
    v9[71] = 0;
    v9[132] = 0;
    v9[131] = 0;
    v9[133] = 0;
    *((_DWORD *)v9 + 268) = 0;
    v9[150] = 0;
    v9[151] = 0;
    v9[152] = 0;
    v9[157] = 0;
    v9[159] = 0;
    *((_DWORD *)v9 + 66) = 0;
    v9[160] = -1;
    do
    {
      *((_DWORD *)v9 + v26 + 183) = 0;
      *((_DWORD *)v9 + v26 + 222) = 0;
      *((_DWORD *)v9 + v26++ + 144) = 0;
    }
    while ( v26 != 39 );
    *((_DWORD *)v9 + 8) = 0;
    v27 = *(char **)(a3 + 8);
    if ( (unsigned __int64)(v27 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v28 = ValidateHandleForRasman(v27, v17);
      v29 = (void *)v28;
      if ( (unsigned __int64)(v28 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        v18 = AddNotifierToList(v9 + 53, v28, 2, v17);
        if ( v18 )
        {
          FreeNotifierHandle(v29);
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            result = WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 145, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v18);
          }
        }
      }
    }
    *(_QWORD *)(a3 + 16) = *v9;
    v9[136] = v9 + 135;
    v9[135] = v9 + 135;
    *((_DWORD *)v9 + 274) = 0;
    if ( !*(_DWORD *)(a3 + 28) )
      (*(void (__fastcall **)(_QWORD))(v9[6] + 32LL))(v9[27]);
    goto LABEL_124;
  }
  TelemetryEventWriteStateChange(v9, 633, "PortOpenRequest: Port is not available");
  *(_DWORD *)a3 = 633;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 134, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, *v9);
      v15 = WPP_GLOBAL_Control;
    }
    if ( v15 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v15[1].Blink) & 0x2000) != 0
      && BYTE1(v15[1].Blink) >= 6u )
    {
      v16 = 135;
      return WPP_SF_(v15[1].Flink, v16, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800228d0  push    rbx
0x1800228d2  push    rbp
0x1800228d3  push    rsi
0x1800228d4  push    rdi
0x1800228d5  push    r12
0x1800228d7  push    r13
0x1800228d9  push    r14
0x1800228db  push    r15
0x1800228dd  sub     rsp, 38h
0x1800228e1  mov     r14, r8
0x1800228e4  mov     r15, rdx
0x1800228e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800228ee  lea     rbp, WPP_GLOBAL_Control
0x1800228f5  lea     rsi, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x1800228fc  mov     r13d, 2000h
0x180022902  cmp     rcx, rbp
0x180022905  jz      short loc_180022951
0x180022907  test    [rcx+1Ch], r13d
0x18002290b  jz      short loc_18002292B
0x18002290d  cmp     byte ptr [rcx+19h], 6
0x180022911  jb      short loc_18002292B
0x180022913  mov     rcx, [rcx+10h]
0x180022917  mov     edx, 80h
0x18002291c  mov     r8, rsi
0x18002291f  call    WPP_SF_
0x180022924  mov     rcx, cs:WPP_GLOBAL_Control
0x18002292b  cmp     rcx, rbp
0x18002292e  jz      short loc_180022951
0x180022930  test    [rcx+1Ch], r13d
0x180022934  jz      short loc_180022951
0x180022936  cmp     byte ptr [rcx+19h], 6
0x18002293a  jb      short loc_180022951
0x18002293c  mov     rcx, [rcx+10h]
0x180022940  lea     r8, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids
0x180022947  mov     edx, 0BFh
0x18002294c  call    WPP_SF_
0x180022951  xor     r12d, r12d
0x180022954  lea     rcx, PcbLock; lpCriticalSection
0x18002295b  mov     edi, r12d
0x18002295e  call    cs:__imp_EnterCriticalSection
0x180022964  mov     r10d, cs:MaxPorts
0x18002296b  mov     ecx, r12d
0x18002296e  test    r10d, r10d
0x180022971  jz      short loc_1800229C0
0x180022973  mov     r11, cs:Pcb
0x18002297a  mov     eax, ecx
0x18002297c  mov     rbx, [r11+rax*8]
0x180022980  test    rbx, rbx
0x180022983  jz      short loc_1800229B0
0x180022985  cmp     dword ptr [rbx+18h], 3
0x180022989  jz      short loc_1800229B0
0x18002298b  lea     r9, [r14+20h]
0x18002298f  lea     rax, [rbx+8]
0x180022993  sub     r9, rax
0x180022996  movzx   r8d, byte ptr [rax]
0x18002299a  movzx   edx, byte ptr [rax+r9]
0x18002299f  sub     r8d, edx
0x1800229a2  jnz     short loc_1800229AB
0x1800229a4  inc     rax
0x1800229a7  test    edx, edx
0x1800229a9  jnz     short loc_180022996
0x1800229ab  test    r8d, r8d
0x1800229ae  jz      short loc_1800229B9
0x1800229b0  inc     ecx
0x1800229b2  cmp     ecx, r10d
0x1800229b5  jb      short loc_18002297A
0x1800229b7  jmp     short loc_1800229C3
0x1800229b9  mov     edi, 1
0x1800229be  jmp     short loc_1800229C3
0x1800229c0  mov     rbx, r12
0x1800229c3  lea     rcx, PcbLock; lpCriticalSection
0x1800229ca  call    cs:__imp_LeaveCriticalSection
0x1800229d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800229d7  cmp     rcx, rbp
0x1800229da  jz      short loc_180022A07
0x1800229dc  test    [rcx+1Ch], r13d
0x1800229e0  jz      short loc_180022A07
0x1800229e2  cmp     byte ptr [rcx+19h], 6
0x1800229e6  jb      short loc_180022A07
0x1800229e8  mov     rcx, [rcx+10h]
0x1800229ec  lea     r8, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids
0x1800229f3  mov     r9b, dil
0x1800229f6  mov     edx, 0C0h
0x1800229fb  call    WPP_SF_c
0x180022a00  mov     rcx, cs:WPP_GLOBAL_Control
0x180022a07  test    edi, edi
0x180022a09  jz      loc_1800230CD
0x180022a0f  test    rbx, rbx
0x180022a12  jz      loc_1800230CD
0x180022a18  cmp     rcx, rbp
0x180022a1b  jz      short loc_180022A45
0x180022a1d  test    [rcx+1Ch], r13d
0x180022a21  jz      short loc_180022A45
0x180022a23  cmp     byte ptr [rcx+19h], 4
0x180022a27  jb      short loc_180022A45
0x180022a29  movzx   eax, word ptr [rbx+2Ch]
0x180022a2d  mov     edx, 83h
0x180022a32  mov     r9, [rbx]
0x180022a35  mov     r8, rsi
0x180022a38  mov     rcx, [rcx+10h]
0x180022a3c  mov     [rsp+78h+var_58], eax
0x180022a40  call    WPP_SF_qD
0x180022a45  mov     edi, 2
0x180022a4a  cmp     [rbx+18h], edi
0x180022a4d  jnz     short loc_180022AC8
0x180022a4f  lea     r8, aPortopenreques; "PortOpenRequest: Port is in process of "...
0x180022a56  mov     edx, 267h
0x180022a5b  mov     rcx, rbx
0x180022a5e  call    TelemetryEventWriteStateChange
0x180022a63  mov     dword ptr [r14], 267h
0x180022a6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022a71  cmp     rcx, rbp
0x180022a74  jz      loc_18002312D
0x180022a7a  test    [rcx+1Ch], r13d
0x180022a7e  jz      short loc_180022AA1
0x180022a80  cmp     [rcx+19h], dil
0x180022a84  jb      short loc_180022AA1
0x180022a86  mov     r9, [rbx]
0x180022a89  mov     edx, 84h
0x180022a8e  mov     rcx, [rcx+10h]
0x180022a92  mov     r8, rsi
0x180022a95  call    WPP_SF_q
0x180022a9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022aa1  cmp     rcx, rbp
0x180022aa4  jz      loc_18002312D
0x180022aaa  test    [rcx+1Ch], r13d
0x180022aae  jz      loc_18002312D
0x180022ab4  cmp     byte ptr [rcx+19h], 6
0x180022ab8  jb      loc_18002312D
0x180022abe  mov     edx, 85h
0x180022ac3  jmp     loc_180023121
0x180022ac8  test    r15, r15
0x180022acb  jz      short loc_180022AD8
0x180022acd  cmp     [r15], r12d
0x180022ad0  jz      short loc_180022AD8
0x180022ad2  mov     r15d, [r15+8]
0x180022ad6  jmp     short loc_180022ADC
0x180022ad8  mov     r15d, [r14+18h]
0x180022adc  call    cs:__imp_GetCurrentProcessId
0x180022ae2  cmp     r15d, eax
0x180022ae5  jz      loc_180022B77
0x180022aeb  test    [rbx+24h], dil
0x180022aef  jnz     loc_180022B77
0x180022af5  mov     esi, 279h
0x180022afa  lea     r8, aPortopenreques_2; "PortOpenRequest: Port is not available"
0x180022b01  mov     edx, esi
0x180022b03  mov     rcx, rbx
0x180022b06  call    TelemetryEventWriteStateChange
0x180022b0b  mov     [r14], esi
0x180022b0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b15  cmp     rcx, rbp
0x180022b18  jz      loc_18002312D
0x180022b1e  test    [rcx+1Ch], r13d
0x180022b22  jz      short loc_180022B49
0x180022b24  cmp     [rcx+19h], dil
0x180022b28  jb      short loc_180022B49
0x180022b2a  mov     r9, [rbx]
0x180022b2d  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180022b34  mov     rcx, [rcx+10h]
0x180022b38  mov     edx, 86h
0x180022b3d  call    WPP_SF_q
0x180022b42  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b49  cmp     rcx, rbp
0x180022b4c  jz      loc_18002312D
0x180022b52  test    [rcx+1Ch], r13d
0x180022b56  jz      loc_18002312D
0x180022b5c  cmp     byte ptr [rcx+19h], 6
0x180022b60  jb      loc_18002312D
0x180022b66  mov     edx, 87h
0x180022b6b  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180022b72  jmp     loc_180023124
0x180022b77  test    byte ptr [rbx+4C8h], 8
0x180022b7e  jz      short loc_180022BFE
0x180022b80  mov     ebp, 25Ah
0x180022b85  lea     r8, aPortopenreques_0; "PortOpenRequest: Port is already opened"
0x180022b8c  mov     edx, ebp
0x180022b8e  mov     rcx, rbx
0x180022b91  call    TelemetryEventWriteStateChange
0x180022b96  mov     [r14], ebp
0x180022b99  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ba0  lea     r15, WPP_GLOBAL_Control
0x180022ba7  cmp     rcx, r15
0x180022baa  jz      loc_18002312D
0x180022bb0  test    [rcx+1Ch], r13d
0x180022bb4  jz      short loc_180022BD7
0x180022bb6  cmp     [rcx+19h], dil
0x180022bba  jb      short loc_180022BD7
0x180022bbc  mov     r9, [rbx]
0x180022bbf  mov     edx, 88h
0x180022bc4  mov     rcx, [rcx+10h]
0x180022bc8  mov     r8, rsi
0x180022bcb  call    WPP_SF_q
0x180022bd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180022bd7  cmp     rcx, r15
0x180022bda  jz      loc_18002312D
0x180022be0  test    [rcx+1Ch], r13d
0x180022be4  jz      loc_18002312D
0x180022bea  cmp     byte ptr [rcx+19h], 6
0x180022bee  jb      loc_18002312D
0x180022bf4  mov     edx, 89h
0x180022bf9  jmp     loc_180023121
0x180022bfe  cmp     [rbx+2Ch], di
0x180022c02  jb      short loc_180022C59
0x180022c04  mov     ebp, 25Ah
0x180022c09  mov     esi, ebp
0x180022c0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c12  lea     r15, WPP_GLOBAL_Control
0x180022c19  cmp     rcx, r15
0x180022c1c  jz      loc_180022E8B
0x180022c22  test    [rcx+1Ch], r13d
0x180022c26  jz      loc_180022E54
0x180022c2c  cmp     [rcx+19h], dil
0x180022c30  jb      loc_180022E54
0x180022c36  movzx   r9d, word ptr [rbx+2Ch]
0x180022c3b  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180022c42  mov     rcx, [rcx+10h]
0x180022c46  mov     edx, 8Ah
0x180022c4b  mov     [rsp+78h+var_58], ebp
0x180022c4f  call    WPP_SF_Dd
0x180022c54  jmp     loc_180022E4D
0x180022c59  mov     edx, 1
0x180022c5e  cmp     [rbx+18h], edx
0x180022c61  jnz     loc_180022D2B
0x180022c67  mov     rcx, [rbx+30h]; String1
0x180022c6b  lea     rdx, String2; "rastapi"
0x180022c72  call    cs:__imp__stricmp
0x180022c78  test    eax, eax
0x180022c7a  jnz     short loc_180022CF3
0x180022c7c  mov     rax, [rbx+428h]
0x180022c83  test    rax, rax
0x180022c86  jz      short loc_180022CF3
0x180022c88  cmp     [rax+1BDh], r12b
0x180022c8f  jnz     short loc_180022CF3
0x180022c91  mov     r9d, [rbx]
0x180022c94  lea     rdx, [rbx+0D8h]
0x180022c9b  mov     r8, cs:hIoCompletionPort
0x180022ca2  lea     rcx, [rbx+8]
0x180022ca6  mov     rax, cs:RastapiPortOpen
0x180022cad  mov     [rsp+78h+var_58], edi
0x180022cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022cb6  mov     rsi, rax
0x180022cb9  test    eax, eax
0x180022cbb  jz      loc_180022EC7
0x180022cc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180022cc8  cmp     rcx, rbp
0x180022ccb  jz      short loc_180022D1E
0x180022ccd  test    [rcx+1Ch], r13d
0x180022cd1  jz      short loc_180022D1E
0x180022cd3  cmp     [rcx+19h], dil
0x180022cd7  jb      short loc_180022D1E
0x180022cd9  mov     rcx, [rcx+10h]
0x180022cdd  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180022ce4  mov     edx, 8Bh
0x180022ce9  mov     r9d, eax
0x180022cec  call    WPP_SF_d
0x180022cf1  jmp     short loc_180022D17
0x180022cf3  mov     rax, [rbx+30h]
0x180022cf7  lea     rdx, [rbx+0D8h]
0x180022cfe  mov     r9d, [rbx]
0x180022d01  lea     rcx, [rbx+8]
0x180022d05  mov     r8, cs:hIoCompletionPort
0x180022d0c  mov     rax, [rax+18h]
0x180022d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d15  mov     esi, eax
0x180022d17  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d1e  test    esi, esi
0x180022d20  jnz     loc_180022E5B
0x180022d26  jmp     loc_180022EC7
0x180022d2b  mov     eax, [rbx+1Ch]
0x180022d2e  mov     esi, r12d
0x180022d31  cmp     eax, edx
0x180022d33  jz      loc_180022EBF
0x180022d39  cmp     eax, 5
0x180022d3c  ja      loc_180022EA8
0x180022d42  mov     ecx, 25h ; '%'
0x180022d47  bt      ecx, eax
0x180022d4a  jnb     loc_180022EA8
0x180022d50  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d57  cmp     rcx, rbp
0x180022d5a  jz      short loc_180022D94
0x180022d5c  test    [rcx+1Ch], r13d
0x180022d60  jz      short loc_180022D94
0x180022d62  cmp     byte ptr [rcx+19h], 4
0x180022d66  jb      short loc_180022D94
0x180022d68  mov     eax, [rbx+20h]
0x180022d6b  lea     r9, [rbx+8]
0x180022d6f  mov     rcx, [rcx+10h]
0x180022d73  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180022d7a  mov     edx, 8Ch
0x180022d7f  mov     [rsp+78h+var_58], eax
0x180022d83  call    WPP_SF_sd
0x180022d88  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d8f  mov     edx, 1
0x180022d94  cmp     [rbx+20h], edi
0x180022d97  jnz     short loc_180022E16
0x180022d99  test    dword ptr [rbx+1Ch], 0FFFFFFFDh
0x180022da0  jnz     short loc_180022E16
0x180022da2  add     [rbx+2Ch], dx
0x180022da6  mov     rcx, cs:WPP_GLOBAL_Control
0x180022dad  cmp     rcx, rbp
  ... truncated ...
```
