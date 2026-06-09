# ServiceHandlerEx

- ea: `0x1800336e0`
- end: `0x180033c41`
- name: `ServiceHandlerEx`
- size: `1377`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x180005e74`
- `0x18000bf70`
- `0x18000bfb0`
- `0x180033108`
- `0x1800336e0`
- `0x18003ac7c`
- `0x180045104`
- `0x1800dbe18`
- `0x1800e7260`
- `0x1800e9010`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180033b93`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180033b93`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180033bd7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180033bd7`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180033a84`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180033b48`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180033a84`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180033b48`

## pseudocode

```c
__int64 __fastcall ServiceHandlerEx(DWORD dwControl, DWORD dwEventType, _DWORD *lpEventData, LPVOID lpContext)
{
  struct _LIST_ENTRY *v7; // rcx
  __int64 v8; // rdx
  DWORD v9; // ebx
  DWORD v10; // ebx
  DWORD v11; // ebx
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  int v16; // ebx
  struct _SERVICE_STATUS ServiceStatus; // [rsp+30h] [rbp-58h] BYREF

  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_Dd(WPP_GLOBAL_Control[1].Flink, 29, WPP_101c73712a933762328fe4f7a83f8625_Traceguids, dwControl, dwEventType);
    v7 = WPP_GLOBAL_Control;
  }
  v8 = 32;
  ServiceStatus.dwServiceType = 32;
  memset(&ServiceStatus.dwCurrentState, 0, 24);
  v9 = dwControl - 1;
  if ( !v9 )
    goto LABEL_84;
  v10 = v9 - 1;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( v13 )
        {
          v14 = v13 - 6;
          if ( !v14 )
          {
LABEL_19:
            if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(v7[1].Blink) & 0x2000) != 0
              && BYTE1(v7[1].Blink) >= 5u )
            {
              WPP_SF_(v7[1].Flink, 45, WPP_101c73712a933762328fe4f7a83f8625_Traceguids);
              v7 = WPP_GLOBAL_Control;
            }
            if ( RasmanShuttingDown || g_fModemPresent || !lpEventData || lpEventData[1] != 5 || dwEventType != 0x8000 )
              goto LABEL_104;
            if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(v7[1].Blink) & 0x2000) != 0
              && BYTE1(v7[1].Blink) >= 5u )
            {
              WPP_SF_s(v7[1].Flink, 46, WPP_101c73712a933762328fe4f7a83f8625_Traceguids, lpEventData + 7);
            }
            g_fModemPresent = 1;
            ((void (__fastcall *)(struct _LIST_ENTRY *, __int64, _DWORD *, LPVOID))RastapiUpdateTapiService)(
              v7,
              v8,
              lpEventData,
              lpContext);
            goto LABEL_103;
          }
          v15 = v14 - 2;
          if ( v15 )
          {
            v16 = v15 - 1;
            if ( v16 )
            {
              if ( v16 == 19 )
              {
                if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && (HIDWORD(v7[1].Blink) & 0x2000) != 0
                  && BYTE1(v7[1].Blink) >= 5u )
                {
                  WPP_SF_(v7[1].Flink, 44, WPP_101c73712a933762328fe4f7a83f8625_Traceguids);
                }
                HandleSessionChange(dwEventType, lpEventData, lpEventData, lpContext);
                v7 = WPP_GLOBAL_Control;
                goto LABEL_19;
              }
LABEL_104:
              if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(v7[1].Blink) & 0x2000) != 0
                && BYTE1(v7[1].Blink) >= 6u )
              {
                WPP_SF_d(v7[1].Flink, 47, WPP_101c73712a933762328fe4f7a83f8625_Traceguids, 0);
              }
              return 0;
            }
            goto LABEL_70;
          }
          if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v7[1].Blink) & 0x2000) != 0
            && BYTE1(v7[1].Blink) >= 5u )
          {
            WPP_SF_d(v7[1].Flink, 36, WPP_101c73712a933762328fe4f7a83f8625_Traceguids, dwEventType);
            v7 = WPP_GLOBAL_Control;
          }
          if ( dwEventType )
          {
            if ( dwEventType != 1 )
            {
              switch ( dwEventType )
              {
                case 6u:
                  if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && (HIDWORD(v7[1].Blink) & 0x2000) != 0
                    && BYTE1(v7[1].Blink) >= 5u )
                  {
                    WPP_SF_(v7[1].Flink, 39, WPP_101c73712a933762328fe4f7a83f8625_Traceguids);
                  }
                  DropAllActiveConnectionsWith(9);
                  v7 = WPP_GLOBAL_Control;
                  break;
                case 7u:
                  goto LABEL_55;
                case 8u:
                  break;
                default:
                  if ( v7 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  {
LABEL_74:
                    if ( dwEventType - 5 <= 1 )
                      goto LABEL_104;
                    HandleSessionChange(dwEventType, lpEventData, lpEventData, lpContext);
                    goto LABEL_103;
                  }
                  if ( (HIDWORD(v7[1].Blink) & 0x2000) == 0 || BYTE1(v7[1].Blink) < 5u )
                  {
LABEL_70:
                    if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                      && (HIDWORD(v7[1].Blink) & 0x2000) != 0
                      && BYTE1(v7[1].Blink) >= 5u )
                    {
                      WPP_SF_(v7[1].Flink, 43, WPP_101c73712a933762328fe4f7a83f8625_Traceguids);
                      v7 = WPP_GLOBAL_Control;
                    }
                    goto LABEL_74;
                  }
                  WPP_SF_(v7[1].Flink, 42, WPP_101c73712a933762328fe4f7a83f8625_Traceguids);
LABEL_69:
                  v7 = WPP_GLOBAL_Control;
                  goto LABEL_70;
              }
              if ( v7 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
              {
LABEL_59:
                RefreshDevices(v7, v8, lpEventData, lpContext);
                VpnProfileActiveHandleSleepResume(0);
                goto LABEL_69;
              }
              if ( (HIDWORD(v7[1].Blink) & 0x2000) != 0 && BYTE1(v7[1].Blink) >= 5u )
              {
                WPP_SF_(v7[1].Flink, 40, WPP_101c73712a933762328fe4f7a83f8625_Traceguids);
                v7 = WPP_GLOBAL_Control;
              }
LABEL_55:
              if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(v7[1].Blink) & 0x2000) != 0
                && BYTE1(v7[1].Blink) >= 5u )
              {
                WPP_SF_(v7[1].Flink, 41, WPP_101c73712a933762328fe4f7a83f8625_Traceguids);
              }
              goto LABEL_59;
            }
            if ( v7 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            {
LABEL_68:
              DropAllActiveConnectionsWith(9);
              goto LABEL_69;
            }
            if ( (HIDWORD(v7[1].Blink) & 0x2000) != 0 && BYTE1(v7[1].Blink) >= 5u )
            {
              WPP_SF_(v7[1].Flink, 37, WPP_101c73712a933762328fe4f7a83f8625_Traceguids);
              v7 = WPP_GLOBAL_Control;
            }
          }
          if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v7[1].Blink) & 0x2000) != 0
            && BYTE1(v7[1].Blink) >= 5u )
          {
            WPP_SF_(v7[1].Flink, 38, WPP_101c73712a933762328fe4f7a83f8625_Traceguids);
          }
          goto LABEL_68;
        }
LABEL_84:
        if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( (HIDWORD(v7[1].Blink) & 0x2000) != 0 && BYTE1(v7[1].Blink) >= 5u )
          {
            WPP_SF_(v7[1].Flink, 32, WPP_101c73712a933762328fe4f7a83f8625_Traceguids);
            v7 = WPP_GLOBAL_Control;
          }
          if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v7[1].Blink) & 0x2000) != 0
            && BYTE1(v7[1].Blink) >= 5u )
          {
            LOBYTE(lpContext) = RasmanShuttingDown != 0;
            WPP_SF_c(v7[1].Flink, 33, WPP_101c73712a933762328fe4f7a83f8625_Traceguids, lpContext);
            v7 = WPP_GLOBAL_Control;
          }
        }
        if ( !RasmanShuttingDown )
        {
          dwCurrentState = 3;
          ServiceStatus.dwCurrentState = 3;
          SetServiceStatus((SERVICE_STATUS_HANDLE)hService, &ServiceStatus);
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
          {
            WPP_SF_(WPP_GLOBAL_Control[1].Flink, 34, WPP_101c73712a933762328fe4f7a83f8625_Traceguids);
          }
          DropAllActiveConnectionsWith(8);
          PostQueuedCompletionStatus(hIoCompletionPort, 0, 0, &RO_CloseEvent);
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
          {
            WPP_SF_(WPP_GLOBAL_Control[1].Flink, 35, WPP_101c73712a933762328fe4f7a83f8625_Traceguids);
            v7 = WPP_GLOBAL_Control;
          }
        }
        if ( !g_hGdi32 )
          goto LABEL_104;
        FreeLibrary(g_hGdi32);
        g_hGdi32 = 0;
        g_pfnDeviceCapabilitiesExA = 0;
        goto LABEL_103;
      }
    }
  }
  if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v7[1].Blink) & 0x2000) != 0
    && BYTE1(v7[1].Blink) >= 5u )
  {
    WPP_SF_(v7[1].Flink, 30, WPP_101c73712a933762328fe4f7a83f8625_Traceguids);
  }
  ServiceStatus.dwCurrentState = dwCurrentState;
  ServiceStatus.dwControlsAccepted = dwControlsAccepted;
  ServiceStatus.dwCheckPoint = CheckPoint++;
  SetServiceStatus((SERVICE_STATUS_HANDLE)hService, &ServiceStatus);
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 5u )
      goto LABEL_104;
    WPP_SF_d(
      WPP_GLOBAL_Control[1].Flink,
      31,
      WPP_101c73712a933762328fe4f7a83f8625_Traceguids,
      (unsigned int)dwCurrentState);
LABEL_103:
    v7 = WPP_GLOBAL_Control;
    goto LABEL_104;
  }
  return 0;
}

```

## disassembly

```asm
0x1800336e0  mov     [rsp+arg_18], rbx
0x1800336e5  push    rbp
0x1800336e6  push    rsi
0x1800336e7  push    rdi
0x1800336e8  push    r14
0x1800336ea  push    r15
0x1800336ec  sub     rsp, 60h
0x1800336f0  mov     rax, cs:__security_cookie
0x1800336f7  xor     rax, rsp
0x1800336fa  mov     [rsp+88h+var_38], rax
0x1800336ff  mov     rsi, r8
0x180033702  mov     edi, edx
0x180033704  mov     ebx, ecx
0x180033706  mov     rcx, cs:WPP_GLOBAL_Control
0x18003370d  lea     r14, WPP_GLOBAL_Control
0x180033714  lea     r15, WPP_101c73712a933762328fe4f7a83f8625_Traceguids
0x18003371b  mov     ebp, 2000h
0x180033720  cmp     rcx, r14
0x180033723  jz      short loc_18003374F
0x180033725  test    [rcx+1Ch], ebp
0x180033728  jz      short loc_18003374F
0x18003372a  cmp     byte ptr [rcx+19h], 6
0x18003372e  jb      short loc_18003374F
0x180033730  mov     rcx, [rcx+10h]
0x180033734  mov     edx, 1Dh
0x180033739  mov     r9d, ebx
0x18003373c  mov     [rsp+88h+var_68], edi
0x180033740  mov     r8, r15
0x180033743  call    WPP_SF_Dd
0x180033748  mov     rcx, cs:WPP_GLOBAL_Control
0x18003374f  mov     qword ptr [rsp+88h+ServiceStatus.dwCheckPoint], 0
0x180033758  xorps   xmm0, xmm0
0x18003375b  mov     edx, 20h ; ' '
0x180033760  mov     [rsp+88h+ServiceStatus.dwServiceType], edx
0x180033764  movdqu  xmmword ptr [rsp+88h+ServiceStatus.dwCurrentState], xmm0
0x18003376a  sub     ebx, 1
0x18003376d  jz      loc_180033ACA
0x180033773  sub     ebx, 1
0x180033776  jz      loc_180033A31
0x18003377c  sub     ebx, 1
0x18003377f  jz      loc_180033A31
0x180033785  sub     ebx, 1
0x180033788  jz      loc_180033A31
0x18003378e  sub     ebx, 1
0x180033791  jz      loc_180033ACA
0x180033797  sub     ebx, 6
0x18003379a  jz      short loc_1800337E7
0x18003379c  sub     ebx, 2
0x18003379f  jz      loc_180033888
0x1800337a5  sub     ebx, 1
0x1800337a8  jz      loc_1800339EE
0x1800337ae  cmp     ebx, 13h
0x1800337b1  jnz     loc_180033BFA
0x1800337b7  cmp     rcx, r14
0x1800337ba  jz      short loc_1800337D6
0x1800337bc  test    [rcx+1Ch], ebp
0x1800337bf  jz      short loc_1800337D6
0x1800337c1  cmp     byte ptr [rcx+19h], 5
0x1800337c5  jb      short loc_1800337D6
0x1800337c7  mov     rcx, [rcx+10h]
0x1800337cb  lea     edx, [rbx+19h]
0x1800337ce  mov     r8, r15
0x1800337d1  call    WPP_SF_
0x1800337d6  mov     rdx, rsi
0x1800337d9  mov     ecx, edi
0x1800337db  call    HandleSessionChange
0x1800337e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800337e7  cmp     rcx, r14
0x1800337ea  jz      short loc_18003380F
0x1800337ec  test    [rcx+1Ch], ebp
0x1800337ef  jz      short loc_18003380F
0x1800337f1  cmp     byte ptr [rcx+19h], 5
0x1800337f5  jb      short loc_18003380F
0x1800337f7  mov     rcx, [rcx+10h]
0x1800337fb  mov     edx, 2Dh ; '-'
0x180033800  mov     r8, r15
0x180033803  call    WPP_SF_
0x180033808  mov     rcx, cs:WPP_GLOBAL_Control
0x18003380f  cmp     cs:RasmanShuttingDown, 0
0x180033816  jnz     loc_180033BFA
0x18003381c  cmp     cs:g_fModemPresent, 0
0x180033823  jnz     loc_180033BFA
0x180033829  test    rsi, rsi
0x18003382c  jz      loc_180033BFA
0x180033832  cmp     dword ptr [rsi+4], 5
0x180033836  jnz     loc_180033BFA
0x18003383c  cmp     edi, 8000h
0x180033842  jnz     loc_180033BFA
0x180033848  cmp     rcx, r14
0x18003384b  jz      short loc_18003386D
0x18003384d  test    [rcx+1Ch], ebp
0x180033850  jz      short loc_18003386D
0x180033852  cmp     byte ptr [rcx+19h], 5
0x180033856  jb      short loc_18003386D
0x180033858  mov     rcx, [rcx+10h]
0x18003385c  lea     r9, [rsi+1Ch]
0x180033860  mov     edx, 2Eh ; '.'
0x180033865  mov     r8, r15
0x180033868  call    WPP_SF_s
0x18003386d  mov     rax, cs:RastapiUpdateTapiService
0x180033874  mov     cs:g_fModemPresent, 1
0x18003387e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033883  jmp     loc_180033BF3
0x180033888  cmp     rcx, r14
0x18003388b  jz      short loc_1800338B3
0x18003388d  test    [rcx+1Ch], ebp
0x180033890  jz      short loc_1800338B3
0x180033892  cmp     byte ptr [rcx+19h], 5
0x180033896  jb      short loc_1800338B3
0x180033898  mov     rcx, [rcx+10h]
0x18003389c  mov     edx, 24h ; '$'
0x1800338a1  mov     r9d, edi
0x1800338a4  mov     r8, r15
0x1800338a7  call    WPP_SF_d
0x1800338ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800338b3  mov     eax, edi
0x1800338b5  test    edi, edi
0x1800338b7  jz      loc_1800339BC
0x1800338bd  sub     eax, 1
0x1800338c0  jz      loc_180033994
0x1800338c6  sub     eax, 5
0x1800338c9  jz      short loc_18003390B
0x1800338cb  sub     eax, 1
0x1800338ce  jz      loc_180033965
0x1800338d4  cmp     eax, 1
0x1800338d7  jz      short loc_18003393D
0x1800338d9  cmp     rcx, r14
0x1800338dc  jz      loc_180033A16
0x1800338e2  test    [rcx+1Ch], ebp
0x1800338e5  jz      loc_1800339EE
0x1800338eb  cmp     byte ptr [rcx+19h], 5
0x1800338ef  jb      loc_1800339EE
0x1800338f5  mov     rcx, [rcx+10h]
0x1800338f9  mov     edx, 2Ah ; '*'
0x1800338fe  mov     r8, r15
0x180033901  call    WPP_SF_
0x180033906  jmp     loc_1800339E7
0x18003390b  cmp     rcx, r14
0x18003390e  jz      short loc_18003392C
0x180033910  test    [rcx+1Ch], ebp
0x180033913  jz      short loc_18003392C
0x180033915  cmp     byte ptr [rcx+19h], 5
0x180033919  jb      short loc_18003392C
0x18003391b  mov     rcx, [rcx+10h]
0x18003391f  mov     edx, 27h ; '''
0x180033924  mov     r8, r15
0x180033927  call    WPP_SF_
0x18003392c  xor     edx, edx
0x18003392e  lea     ecx, [rdx+9]
0x180033931  call    DropAllActiveConnectionsWith
0x180033936  mov     rcx, cs:WPP_GLOBAL_Control
0x18003393d  cmp     rcx, r14
0x180033940  jz      short loc_180033986
0x180033942  test    [rcx+1Ch], ebp
0x180033945  jz      short loc_180033965
0x180033947  cmp     byte ptr [rcx+19h], 5
0x18003394b  jb      short loc_180033965
0x18003394d  mov     rcx, [rcx+10h]
0x180033951  mov     edx, 28h ; '('
0x180033956  mov     r8, r15
0x180033959  call    WPP_SF_
0x18003395e  mov     rcx, cs:WPP_GLOBAL_Control
0x180033965  cmp     rcx, r14
0x180033968  jz      short loc_180033986
0x18003396a  test    [rcx+1Ch], ebp
0x18003396d  jz      short loc_180033986
0x18003396f  cmp     byte ptr [rcx+19h], 5
0x180033973  jb      short loc_180033986
0x180033975  mov     rcx, [rcx+10h]
0x180033979  mov     edx, 29h ; ')'
0x18003397e  mov     r8, r15
0x180033981  call    WPP_SF_
0x180033986  call    RefreshDevices
0x18003398b  xor     ecx, ecx
0x18003398d  call    VpnProfileActiveHandleSleepResume
0x180033992  jmp     short loc_1800339E7
0x180033994  cmp     rcx, r14
0x180033997  jz      short loc_1800339DD
0x180033999  test    [rcx+1Ch], ebp
0x18003399c  jz      short loc_1800339BC
0x18003399e  cmp     byte ptr [rcx+19h], 5
0x1800339a2  jb      short loc_1800339BC
0x1800339a4  mov     rcx, [rcx+10h]
0x1800339a8  mov     edx, 25h ; '%'
0x1800339ad  mov     r8, r15
0x1800339b0  call    WPP_SF_
0x1800339b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800339bc  cmp     rcx, r14
0x1800339bf  jz      short loc_1800339DD
0x1800339c1  test    [rcx+1Ch], ebp
0x1800339c4  jz      short loc_1800339DD
0x1800339c6  cmp     byte ptr [rcx+19h], 5
0x1800339ca  jb      short loc_1800339DD
0x1800339cc  mov     rcx, [rcx+10h]
0x1800339d0  mov     edx, 26h ; '&'
0x1800339d5  mov     r8, r15
0x1800339d8  call    WPP_SF_
0x1800339dd  xor     edx, edx
0x1800339df  lea     ecx, [rdx+9]
0x1800339e2  call    DropAllActiveConnectionsWith
0x1800339e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800339ee  cmp     rcx, r14
0x1800339f1  jz      short loc_180033A16
0x1800339f3  test    [rcx+1Ch], ebp
0x1800339f6  jz      short loc_180033A16
0x1800339f8  cmp     byte ptr [rcx+19h], 5
0x1800339fc  jb      short loc_180033A16
0x1800339fe  mov     rcx, [rcx+10h]
0x180033a02  mov     edx, 2Bh ; '+'
0x180033a07  mov     r8, r15
0x180033a0a  call    WPP_SF_
0x180033a0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180033a16  lea     eax, [rdi-5]
0x180033a19  cmp     eax, 1
0x180033a1c  jbe     loc_180033BFA
0x180033a22  mov     rdx, rsi
0x180033a25  mov     ecx, edi
0x180033a27  call    HandleSessionChange
0x180033a2c  jmp     loc_180033BF3
0x180033a31  cmp     rcx, r14
0x180033a34  jz      short loc_180033A52
0x180033a36  test    [rcx+1Ch], ebp
0x180033a39  jz      short loc_180033A52
0x180033a3b  cmp     byte ptr [rcx+19h], 5
0x180033a3f  jb      short loc_180033A52
0x180033a41  mov     rcx, [rcx+10h]
0x180033a45  mov     edx, 1Eh
0x180033a4a  mov     r8, r15
0x180033a4d  call    WPP_SF_
0x180033a52  mov     eax, cs:dwCurrentState
0x180033a58  lea     rdx, [rsp+88h+ServiceStatus]; lpServiceStatus
0x180033a5d  mov     rcx, cs:hService; hServiceStatus
0x180033a64  mov     [rsp+88h+ServiceStatus.dwCurrentState], eax
0x180033a68  mov     eax, cs:dwControlsAccepted
0x180033a6e  mov     [rsp+88h+ServiceStatus.dwControlsAccepted], eax
0x180033a72  mov     eax, cs:CheckPoint
0x180033a78  mov     [rsp+88h+ServiceStatus.dwCheckPoint], eax
0x180033a7c  inc     eax
0x180033a7e  mov     cs:CheckPoint, eax
0x180033a84  call    cs:__imp_SetServiceStatus
0x180033a8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180033a91  cmp     rcx, r14
0x180033a94  jz      loc_180033C1E
0x180033a9a  test    [rcx+1Ch], ebp
0x180033a9d  jz      loc_180033BFA
0x180033aa3  cmp     byte ptr [rcx+19h], 5
0x180033aa7  jb      loc_180033BFA
0x180033aad  mov     r9d, cs:dwCurrentState
0x180033ab4  mov     edx, 1Fh
0x180033ab9  mov     rcx, [rcx+10h]
0x180033abd  mov     r8, r15
0x180033ac0  call    WPP_SF_d
0x180033ac5  jmp     loc_180033BF3
0x180033aca  cmp     rcx, r14
0x180033acd  jz      short loc_180033B20
0x180033acf  test    [rcx+1Ch], ebp
0x180033ad2  jz      short loc_180033AED
0x180033ad4  cmp     byte ptr [rcx+19h], 5
0x180033ad8  jb      short loc_180033AED
0x180033ada  mov     rcx, [rcx+10h]
0x180033ade  mov     r8, r15
0x180033ae1  call    WPP_SF_
0x180033ae6  mov     rcx, cs:WPP_GLOBAL_Control
0x180033aed  cmp     rcx, r14
0x180033af0  jz      short loc_180033B20
0x180033af2  test    [rcx+1Ch], ebp
0x180033af5  jz      short loc_180033B20
0x180033af7  cmp     byte ptr [rcx+19h], 5
0x180033afb  jb      short loc_180033B20
0x180033afd  cmp     cs:RasmanShuttingDown, 0
0x180033b04  mov     edx, 21h ; '!'
0x180033b09  mov     rcx, [rcx+10h]
0x180033b0d  mov     r8, r15
0x180033b10  setnz   r9b
0x180033b14  call    WPP_SF_c
0x180033b19  mov     rcx, cs:WPP_GLOBAL_Control
0x180033b20  cmp     cs:RasmanShuttingDown, 0
0x180033b27  jnz     loc_180033BC8
0x180033b2d  mov     rcx, cs:hService; hServiceStatus
0x180033b34  lea     rdx, [rsp+88h+ServiceStatus]; lpServiceStatus
0x180033b39  mov     eax, 3
0x180033b3e  mov     cs:dwCurrentState, eax
0x180033b44  mov     [rsp+88h+ServiceStatus.dwCurrentState], eax
0x180033b48  call    cs:__imp_SetServiceStatus
0x180033b4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180033b55  cmp     rcx, r14
0x180033b58  jz      short loc_180033B76
0x180033b5a  test    [rcx+1Ch], ebp
0x180033b5d  jz      short loc_180033B76
0x180033b5f  cmp     byte ptr [rcx+19h], 5
0x180033b63  jb      short loc_180033B76
0x180033b65  mov     rcx, [rcx+10h]
0x180033b69  mov     edx, 22h ; '"'
0x180033b6e  mov     r8, r15
0x180033b71  call    WPP_SF_
0x180033b76  xor     edx, edx
0x180033b78  lea     ecx, [rdx+8]
0x180033b7b  call    DropAllActiveConnectionsWith
0x180033b80  mov     rcx, cs:hIoCompletionPort; CompletionPort
0x180033b87  lea     r9, RO_CloseEvent; lpOverlapped
  ... truncated ...
```
