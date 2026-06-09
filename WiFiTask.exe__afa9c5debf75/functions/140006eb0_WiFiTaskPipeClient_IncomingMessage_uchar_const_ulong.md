# WiFiTaskPipeClient::IncomingMessage(uchar const *,ulong)

- ea: `0x140006eb0`
- end: `0x140007283`
- name: `?IncomingMessage@WiFiTaskPipeClient@@UEAAJPEBEK@Z`
- size: `979`
- prototype: `__int64 __fastcall(WiFiTaskPipeClient *this, const unsigned __int8 *, __int64)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1400016c4`
- `0x140002168`
- `0x140002f18`
- `0x140003594`
- `0x1400066e4`
- `0x140006eb0`
- `0x140009994`
- `0x14000a628`
- `0x14000bef0`
- `0x14000bf20`
- `0x14000c028`
- `0x14000c1a4`
- `0x140010df8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1400071dc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1400071dc`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x140007231`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x140007231`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006f56`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006f56`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006f3c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140007022`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140007167`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006f3c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140007022`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140007167`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140006f69`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140007047`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000723e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140006f69`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140007047`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000723e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400071e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400071e7`

## pseudocode

```c
__int64 __fastcall WiFiTaskPipeClient::IncomingMessage(WiFiTaskPipeClient *this, const unsigned __int8 *a2, __int64 a3)
{
  const unsigned __int8 *v3; // r14
  __int64 v4; // rdx
  char *v5; // rbx
  int v6; // edi
  char *v7; // r15
  char *v9; // rdi
  __int64 v10; // rcx
  __int64 v11; // r13
  unsigned __int64 v12; // r15
  __int64 v13; // r12
  unsigned __int64 v14; // rdx
  __int64 v15; // rax
  struct _TP_WORK *ThreadpoolWork; // rax
  DWORD LastError; // eax
  _BYTE v18[64]; // [rsp+48h] [rbp-40h] BYREF
  char v21; // [rsp+A0h] [rbp+18h] BYREF
  int v22; // [rsp+A8h] [rbp+20h]

  v3 = a2;
  if ( (_DWORD)a3 == 1024 )
  {
    v4 = *((unsigned int *)a2 + 4);
    if ( (unsigned int)v4 <= 0x3E8 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Iddd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v4,
          a3,
          *(_QWORD *)v3,
          *((_DWORD *)v3 + 2),
          v4,
          *((_DWORD *)v3 + 3));
      }
      v21 = 0;
      v5 = (char *)qword_140019690;
      EnterCriticalSection(&g_csPendingState);
      if ( g_pDisconnectTimer )
        SetThreadpoolTimer(g_pDisconnectTimer, 0, 0, 0);
      ++g_dwPendingRequests;
      LeaveCriticalSection(&g_csPendingState);
      if ( *(_QWORD *)v3 == -1 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35);
        }
        v6 = -2147467260;
        goto LABEL_15;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36);
      }
      v5 = (char *)*GetOperation(v18, (__int64 *)v3, &v21);
      if ( v5 == qword_140019690 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37);
        }
        v6 = -2147024882;
        goto LABEL_15;
      }
      if ( !*((_DWORD *)v3 + 4) )
      {
LABEL_48:
        v6 = 0;
        if ( *((_DWORD *)v3 + 3) == 1 )
        {
          EnterCriticalSection(&g_csEnvironment);
          if ( g_ftpEnvironmentInitialized )
          {
            ThreadpoolWork = CreateThreadpoolWork(
                               (PTP_WORK_CALLBACK)HandleOperationAsync,
                               *(PVOID *)v5,
                               &g_tpEnvironment);
            if ( ThreadpoolWork )
            {
              SubmitThreadpoolWork(ThreadpoolWork);
            }
            else
            {
              LastError = GetLastError();
              v6 = LastError;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  39,
                  &WPP_b0092361ee8d34528df1964c4db39788_Traceguids,
                  LastError);
              }
              if ( v6 > 0 )
                v6 = (unsigned __int16)v6 | 0x80070000;
            }
          }
          else
          {
            v6 = -2147019873;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38);
            }
          }
          LeaveCriticalSection(&g_csEnvironment);
          if ( v6 < 0 )
            goto LABEL_15;
          memmove_0(v5, v5 + 8, (_BYTE *)qword_140019690 - (v5 + 8));
          qword_140019690 = (char *)qword_140019690 - 8;
        }
        if ( v21 )
          return (unsigned int)v6;
LABEL_23:
        EnterCriticalSection(&g_csPendingState);
        if ( !--g_dwPendingRequests )
        {
          if ( g_pDisconnectTimer )
            StartDisconnectTimer();
        }
        LeaveCriticalSection(&g_csPendingState);
        return (unsigned int)v6;
      }
      v9 = *(char **)v5;
      v10 = *(_QWORD *)(*(_QWORD *)v5 + 16LL);
      v11 = *(_QWORD *)(*(_QWORD *)v5 + 24LL);
      v12 = v11 - v10;
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        v13 = *((unsigned int *)v3 + 4);
        v14 = v13 + v12;
        if ( v13 + v12 < v12 )
        {
          v15 = v10 + v14;
LABEL_46:
          *((_QWORD *)v9 + 3) = v15;
          goto LABEL_67;
        }
        if ( v13 + v12 > v12 )
        {
          if ( v14 <= *((_QWORD *)v9 + 4) - v10 )
          {
            memset_0(*(void **)(*(_QWORD *)v5 + 24LL), 0, *((unsigned int *)v3 + 4));
            v15 = v13 + v11;
            goto LABEL_46;
          }
          std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v9 + 16);
        }
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
        {
          v22 = -2147024882;
          v3 = a2;
          v6 = -2147024882;
          __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_1400071B2);
LABEL_15:
          if ( v5 != qword_140019690 )
          {
            v7 = *(char **)v5;
            if ( *(_QWORD *)v5 )
            {
              std::vector<unsigned char>::~vector<unsigned char>(v7 + 16);
              operator delete(v7);
            }
            memmove_0(v5, v5 + 8, (_BYTE *)qword_140019690 - (v5 + 8));
            qword_140019690 = (char *)qword_140019690 - 8;
          }
          if ( *(_QWORD *)v3 != -1 )
            WiFiTaskPipeClient::SendOperationPacket(this, *(_QWORD *)v3, v6, 0, 0);
          goto LABEL_23;
        }
      }
LABEL_67:
      memcpy_s(
        (void *const)(*(_QWORD *)(*(_QWORD *)v5 + 16LL) + (unsigned int)v12),
        *(_DWORD *)(*(_QWORD *)v5 + 24LL) - (unsigned int)*(_QWORD *)(*(_QWORD *)v5 + 16LL) - (unsigned int)v12,
        v3 + 20,
        *((unsigned int *)v3 + 4));
      goto LABEL_48;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x140006eb0  mov     [rsp+arg_8], rdx
0x140006eb5  mov     [rsp+arg_0], rcx
0x140006eba  push    rbx
0x140006ebb  push    rdi
0x140006ebc  push    r12
0x140006ebe  push    r13
0x140006ec0  push    r14
0x140006ec2  push    r15
0x140006ec4  sub     rsp, 58h
0x140006ec8  mov     r14, rdx
0x140006ecb  cmp     r8d, 400h
0x140006ed2  jnz     loc_14000726F
0x140006ed8  mov     edx, [rdx+10h]
0x140006edb  cmp     edx, 3E8h
0x140006ee1  ja      loc_14000726F
0x140006ee7  lea     r15, WPP_GLOBAL_Control
0x140006eee  mov     rcx, cs:WPP_GLOBAL_Control
0x140006ef5  cmp     rcx, r15
0x140006ef8  jz      short loc_140006F26
0x140006efa  cmp     byte ptr [rcx+19h], 5
0x140006efe  jb      short loc_140006F26
0x140006f00  test    byte ptr [rcx+1Ch], 1
0x140006f04  jz      short loc_140006F26
0x140006f06  mov     eax, [r14+0Ch]
0x140006f0a  mov     [rsp+88h+var_58], eax
0x140006f0e  mov     [rsp+88h+var_60], edx
0x140006f12  mov     eax, [r14+8]
0x140006f16  mov     [rsp+88h+var_68], eax
0x140006f1a  mov     r9, [r14]
0x140006f1d  mov     rcx, [rcx+10h]
0x140006f21  call    WPP_SF_Iddd
0x140006f26  mov     [rsp+88h+arg_10], 0
0x140006f2e  mov     rbx, cs:qword_140019690
0x140006f35  lea     rcx, ?g_csPendingState@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140006f3c  call    cs:__imp_EnterCriticalSection
0x140006f42  mov     rcx, cs:?g_pDisconnectTimer@@3PEAU_TP_TIMER@@EA; pti
0x140006f49  test    rcx, rcx
0x140006f4c  jz      short loc_140006F5C
0x140006f4e  xor     r9d, r9d; msWindowLength
0x140006f51  xor     r8d, r8d; msPeriod
0x140006f54  xor     edx, edx; pftDueTime
0x140006f56  call    cs:__imp_SetThreadpoolTimer
0x140006f5c  inc     cs:?g_dwPendingRequests@@3KA; ulong g_dwPendingRequests
0x140006f62  lea     rcx, ?g_csPendingState@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140006f69  call    cs:__imp_LeaveCriticalSection
0x140006f6f  cmp     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x140006f73  jnz     loc_140007054
0x140006f79  mov     rcx, cs:WPP_GLOBAL_Control
0x140006f80  cmp     rcx, r15
0x140006f83  jz      short loc_140006F9F
0x140006f85  cmp     byte ptr [rcx+19h], 2
0x140006f89  jb      short loc_140006F9F
0x140006f8b  test    byte ptr [rcx+1Ch], 1
0x140006f8f  jz      short loc_140006F9F
0x140006f91  mov     edx, 23h ; '#'
0x140006f96  mov     rcx, [rcx+10h]
0x140006f9a  call    WPP_SF_
0x140006f9f  mov     edi, 80004004h
0x140006fa4  cmp     rbx, cs:qword_140019690
0x140006fab  jz      short loc_140006FE9
0x140006fad  mov     r15, [rbx]
0x140006fb0  test    r15, r15
0x140006fb3  jz      short loc_140006FCB
0x140006fb5  lea     rcx, [r15+10h]
0x140006fb9  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x140006fbe  mov     edx, 28h ; '('
0x140006fc3  mov     rcx, r15; Block
0x140006fc6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140006fcb  lea     rdx, [rbx+8]; Src
0x140006fcf  mov     r8, cs:qword_140019690
0x140006fd6  sub     r8, rdx; Size
0x140006fd9  mov     rcx, rbx; void *
0x140006fdc  call    memmove_0
0x140006fe1  sub     cs:qword_140019690, 8
0x140006fe9  cmp     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x140006fed  jz      short loc_14000700D
0x140006fef  mov     [rsp+88h+var_68], 0; unsigned int
0x140006ff7  xor     r9d, r9d; unsigned __int8 *
0x140006ffa  mov     r8d, edi; unsigned int
0x140006ffd  mov     rdx, [r14]; unsigned __int64
0x140007000  mov     rcx, [rsp+88h+arg_0]; this
0x140007008  call    ?SendOperationPacket@WiFiTaskPipeClient@@QEAAJ_KKPEBEK@Z; WiFiTaskPipeClient::SendOperationPacket(unsigned __int64,ulong,uchar const *,ulong)
0x14000700d  test    edi, edi
0x14000700f  js      short loc_14000701B
0x140007011  cmp     [rsp+88h+arg_10], 0
0x140007019  jnz     short loc_14000704D
0x14000701b  lea     rcx, ?g_csPendingState@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140007022  call    cs:__imp_EnterCriticalSection
0x140007028  add     cs:?g_dwPendingRequests@@3KA, 0FFFFFFFFh; ulong g_dwPendingRequests
0x14000702f  jnz     short loc_140007040
0x140007031  cmp     cs:?g_pDisconnectTimer@@3PEAU_TP_TIMER@@EA, 0; _TP_TIMER * g_pDisconnectTimer
0x140007039  jz      short loc_140007040
0x14000703b  call    ?StartDisconnectTimer@@YAXXZ; StartDisconnectTimer(void)
0x140007040  lea     rcx, ?g_csPendingState@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140007047  call    cs:__imp_LeaveCriticalSection
0x14000704d  mov     eax, edi
0x14000704f  jmp     loc_140007274
0x140007054  mov     rcx, cs:WPP_GLOBAL_Control
0x14000705b  cmp     rcx, r15
0x14000705e  jz      short loc_14000707A
0x140007060  cmp     byte ptr [rcx+19h], 5
0x140007064  jb      short loc_14000707A
0x140007066  test    byte ptr [rcx+1Ch], 1
0x14000706a  jz      short loc_14000707A
0x14000706c  mov     edx, 24h ; '$'
0x140007071  mov     rcx, [rcx+10h]
0x140007075  call    WPP_SF_
0x14000707a  lea     r8, [rsp+88h+arg_10]
0x140007082  mov     rdx, r14
0x140007085  lea     rcx, [rsp+88h+var_40]
0x14000708a  call    ?GetOperation@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAVOperation@@@std@@@std@@@std@@PEAUWIFI_PIPE_PACKET@@PEA_N@Z; GetOperation(WIFI_PIPE_PACKET *,bool *)
0x14000708f  mov     rbx, [rax]
0x140007092  mov     [rsp+88h+var_48], rbx
0x140007097  cmp     rbx, cs:qword_140019690
0x14000709e  jnz     short loc_1400070D0
0x1400070a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400070a7  cmp     rcx, r15
0x1400070aa  jz      short loc_1400070C6
0x1400070ac  cmp     byte ptr [rcx+19h], 2
0x1400070b0  jb      short loc_1400070C6
0x1400070b2  test    byte ptr [rcx+1Ch], 1
0x1400070b6  jz      short loc_1400070C6
0x1400070b8  mov     edx, 25h ; '%'
0x1400070bd  mov     rcx, [rcx+10h]
0x1400070c1  call    WPP_SF_
0x1400070c6  mov     edi, 8007000Eh
0x1400070cb  jmp     loc_140006FA4
0x1400070d0  cmp     dword ptr [r14+10h], 0
0x1400070d5  jbe     short loc_140007153
0x1400070d7  mov     rdi, [rbx]
0x1400070da  mov     rcx, [rdi+10h]
0x1400070de  mov     r13, [rdi+18h]
0x1400070e2  mov     r15, r13
0x1400070e5  sub     r15, rcx
0x1400070e8  mov     r12d, [r14+10h]
0x1400070ec  lea     rdx, [r12+r15]
0x1400070f0  cmp     rdx, r15
0x1400070f3  jnb     short loc_1400070FB
0x1400070f5  lea     rax, [rcx+rdx]
0x1400070f9  jmp     short loc_140007125
0x1400070fb  jbe     short loc_140007129
0x1400070fd  mov     rax, [rdi+20h]
0x140007101  sub     rax, rcx
0x140007104  cmp     rdx, rax
0x140007107  jbe     short loc_140007114
0x140007109  lea     rcx, [rdi+10h]
0x14000710d  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x140007112  jmp     short loc_140007129
0x140007114  mov     r8, r12; Size
0x140007117  xor     edx, edx; Val
0x140007119  mov     rcx, r13; void *
0x14000711c  call    memset_0
0x140007121  lea     rax, [r12+r13]
0x140007125  mov     [rdi+18h], rax
0x140007129  mov     rax, [rbx]
0x14000712c  mov     r10, [rax+10h]
0x140007130  mov     ecx, r15d
0x140007133  mov     r9d, [r14+10h]; SourceSize
0x140007137  lea     r8, [r14+14h]; Source
0x14000713b  mov     edx, [rax+18h]
0x14000713e  sub     edx, r10d
0x140007141  sub     edx, r15d; DestinationSize
0x140007144  add     rcx, r10; Destination
0x140007147  call    memcpy_s
0x14000714c  lea     r15, WPP_GLOBAL_Control
0x140007153  xor     edi, edi
0x140007155  cmp     dword ptr [r14+0Ch], 1
0x14000715a  jnz     loc_140007011
0x140007160  lea     rcx, ?g_csEnvironment@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140007167  call    cs:__imp_EnterCriticalSection
0x14000716d  cmp     cs:?g_ftpEnvironmentInitialized@@3_NA, dil; bool g_ftpEnvironmentInitialized
0x140007174  jnz     short loc_1400071CB
0x140007176  mov     edi, 8007139Fh
0x14000717b  mov     rcx, cs:WPP_GLOBAL_Control
0x140007182  cmp     rcx, r15
0x140007185  jz      loc_140007237
0x14000718b  cmp     byte ptr [rcx+19h], 2
0x14000718f  jb      loc_140007237
0x140007195  test    byte ptr [rcx+1Ch], 1
0x140007199  jz      loc_140007237
0x14000719f  mov     edx, 26h ; '&'
0x1400071a4  mov     rcx, [rcx+10h]
0x1400071a8  call    WPP_SF_
0x1400071ad  jmp     loc_140007237
0x1400071b2  mov     r14, [rsp+88h+arg_8]
0x1400071ba  mov     edi, [rsp+88h+arg_18]
0x1400071c1  mov     rbx, [rsp+88h+var_48]
0x1400071c6  jmp     loc_140006FA4
0x1400071cb  lea     r8, ?g_tpEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x1400071d2  mov     rdx, [rbx]; pv
0x1400071d5  lea     rcx, ?HandleOperationAsync@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1400071dc  call    cs:__imp_CreateThreadpoolWork
0x1400071e2  test    rax, rax
0x1400071e5  jnz     short loc_14000722E
0x1400071e7  call    cs:__imp_GetLastError
0x1400071ed  mov     edi, eax
0x1400071ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400071f6  cmp     rcx, r15
0x1400071f9  jz      short loc_14000721F
0x1400071fb  cmp     byte ptr [rcx+19h], 2
0x1400071ff  jb      short loc_14000721F
0x140007201  test    byte ptr [rcx+1Ch], 1
0x140007205  jz      short loc_14000721F
0x140007207  mov     edx, 27h ; '''
0x14000720c  mov     r9d, eax
0x14000720f  lea     r8, WPP_b0092361ee8d34528df1964c4db39788_Traceguids
0x140007216  mov     rcx, [rcx+10h]
0x14000721a  call    WPP_SF_d
0x14000721f  test    edi, edi
0x140007221  jle     short loc_140007237
0x140007223  movzx   edi, di
0x140007226  or      edi, 80070000h
0x14000722c  jmp     short loc_140007237
0x14000722e  mov     rcx, rax; pwk
0x140007231  call    cs:__imp_SubmitThreadpoolWork
0x140007237  lea     rcx, ?g_csEnvironment@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000723e  call    cs:__imp_LeaveCriticalSection
0x140007244  test    edi, edi
0x140007246  js      loc_140006FA4
0x14000724c  lea     rdx, [rbx+8]; Src
0x140007250  mov     r8, cs:qword_140019690
0x140007257  sub     r8, rdx; Size
0x14000725a  mov     rcx, rbx; void *
0x14000725d  call    memmove_0
0x140007262  sub     cs:qword_140019690, 8
0x14000726a  jmp     loc_140007011
0x14000726f  mov     eax, 80070057h
0x140007274  add     rsp, 58h
0x140007278  pop     r15
0x14000727a  pop     r14
0x14000727c  pop     r13
0x14000727e  pop     r12
0x140007280  pop     rdi
0x140007281  pop     rbx
0x140007282  retn
```
