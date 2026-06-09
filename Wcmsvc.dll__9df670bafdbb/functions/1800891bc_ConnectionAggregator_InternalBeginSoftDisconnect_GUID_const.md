# ConnectionAggregator::InternalBeginSoftDisconnect(_GUID const *)

- ea: `0x1800891bc`
- end: `0x1800895e8`
- name: `?InternalBeginSoftDisconnect@ConnectionAggregator@@AEAAXPEBU_GUID@@@Z`
- size: `1068`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, const struct _GUID *)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180088de0`

## callees

- `0x180010080`
- `0x180010ff0`
- `0x180011ddc`
- `0x1800137a0`
- `0x180013894`
- `0x180027630`
- `0x180027b78`
- `0x1800384ec`
- `0x18003a08c`
- `0x180048684`
- `0x18007a294`
- `0x180084f50`
- `0x1800891bc`
- `0x18008a36c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800895bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800895bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800893a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800893a5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18008939b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18008939b`

## string_xrefs

- `0x18008952c`: `onecoreuap\net\wcm\service\base\server\aggregator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ConnectionAggregator::InternalBeginSoftDisconnect(
        LPCRITICAL_SECTION lpCriticalSection,
        const struct _GUID *a2)
{
  __int64 v4; // rdx
  GUID *v5; // r8
  int InterfaceStatus; // eax
  __int64 v7; // r10
  __int64 v8; // r8
  __int64 v9; // rcx
  DWORD LastError; // eax
  unsigned int ByteCountsForInterface; // eax
  int v12; // r8d
  int v13; // r9d
  int v14; // ecx
  LPCRITICAL_SECTION lpCriticalSectiona; // [rsp+40h] [rbp-40h] BYREF
  GUID *v16; // [rsp+48h] [rbp-38h] BYREF
  const char *v17; // [rsp+50h] [rbp-30h] BYREF
  const char *v18; // [rsp+58h] [rbp-28h] BYREF
  GUID *InterfaceGuid[2]; // [rsp+60h] [rbp-20h] BYREF

  lpCriticalSectiona = 0;
  wil::EnterCriticalSection(&lpCriticalSectiona, lpCriticalSection);
  *(_OWORD *)InterfaceGuid = 0;
  ConnectionAggregator::FindInterface(lpCriticalSection);
  if ( !InterfaceGuid[0] )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF__guid_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 253, WPP_629ff72c36873acc9d3aa94b4d8c7cd2_Traceguids, a2);
    }
    goto LABEL_46;
  }
  if ( (unsigned int)WCM_CONAGG_INTERFACE_INFO::GetInterfaceStatus(InterfaceGuid[0]) != 1 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      InterfaceStatus = WCM_CONAGG_INTERFACE_INFO::GetInterfaceStatus(v5);
      WPP_SF__guid_D(*(_QWORD *)(v7 + 16), 254, WPP_629ff72c36873acc9d3aa94b4d8c7cd2_Traceguids, v8, InterfaceStatus);
    }
    goto LABEL_46;
  }
  if ( v5[42].Data1 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF__guid_D(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        255,
        WPP_629ff72c36873acc9d3aa94b4d8c7cd2_Traceguids,
        v5,
        v5[42].Data1);
      v5 = InterfaceGuid[0];
    }
    if ( v5[42].Data1 == 1 && !lpCriticalSection[2].DebugInfo )
      MicrosoftTelemetryAssertTriggeredNoArgs(v9, v4);
    goto LABEL_46;
  }
  v5[42].Data1 = 1;
  *(_DWORD *)InterfaceGuid[0][42].Data4 = 0;
  *(_DWORD *)&InterfaceGuid[0][42].Data2 = 0;
  InterfaceGuid[0][47].Data4[0] = 0;
  InterfaceGuid[0][47].Data4[1] = 0;
  if ( lpCriticalSection[2].DebugInfo )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF__guid_(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        260,
        WPP_629ff72c36873acc9d3aa94b4d8c7cd2_Traceguids,
        InterfaceGuid[0]);
    }
    goto LABEL_45;
  }
  if ( !CreateTimerQueueTimer(
          (PHANDLE)&lpCriticalSection[2].DebugInfo,
          (HANDLE)lpCriticalSection[1].SpinCount,
          ConnectionAggregator::SoftDisconnectTimerCallback,
          lpCriticalSection,
          0x61A8u,
          0x7FFFFFFFu,
          0) )
  {
    LastError = GetLastError();
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 256, WPP_629ff72c36873acc9d3aa94b4d8c7cd2_Traceguids, LastError);
    }
    lpCriticalSection[2].LockCount = 0;
    InterfaceGuid[0][42].Data1 = 0;
    goto LABEL_46;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF__guid_(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      257,
      WPP_629ff72c36873acc9d3aa94b4d8c7cd2_Traceguids,
      InterfaceGuid[0]);
  }
  ByteCountsForInterface = GetByteCountsForInterface(
                             InterfaceGuid[0],
                             (unsigned __int64 *)&InterfaceGuid[0][43].Data1,
                             (unsigned __int64 *)InterfaceGuid[0][44].Data4,
                             (unsigned __int64 *)&InterfaceGuid[0][46].Data1);
  if ( !ByteCountsForInterface )
  {
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF__guid_iii(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 259, WPP_629ff72c36873acc9d3aa94b4d8c7cd2_Traceguids);
    }
    *(_DWORD *)InterfaceGuid[0][42].Data4 = 1;
    lpCriticalSection[2].LockCount = 1;
    if ( (unsigned int)dword_18013A120 > 5 )
    {
      v16 = InterfaceGuid[0];
      v17 = "Beginning Soft-disconnect on interface";
      v18 = "onecoreuap\\net\\wcm\\service\\base\\server\\aggregator.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
        v14,
        (unsigned int)&dword_180114254,
        v12,
        v13,
        (__int64)&v18,
        (__int64)&v17,
        (__int64)&v16);
    }
LABEL_45:
    ConnectionAggregator::UpdateInterfaceLimitedLinkConnectivity(lpCriticalSection, InterfaceGuid, 1);
    goto LABEL_46;
  }
  InterfaceGuid[0][42].Data1 = 0;
  *(_DWORD *)InterfaceGuid[0][42].Data4 = 0;
  *(_DWORD *)&InterfaceGuid[0][42].Data2 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      258,
      WPP_629ff72c36873acc9d3aa94b4d8c7cd2_Traceguids,
      ByteCountsForInterface);
  }
LABEL_46:
  if ( InterfaceGuid[1] )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)InterfaceGuid[1]);
  if ( lpCriticalSectiona )
    LeaveCriticalSection(lpCriticalSectiona);
}

```

## disassembly

```asm
0x1800891bc  mov     [rsp-28h+arg_10], rbx
0x1800891c1  push    rbp
0x1800891c2  push    rsi
0x1800891c3  push    rdi
0x1800891c4  push    r14
0x1800891c6  push    r15
0x1800891c8  mov     rbp, rsp
0x1800891cb  sub     rsp, 80h
0x1800891d2  mov     rax, cs:__security_cookie
0x1800891d9  xor     rax, rsp
0x1800891dc  mov     [rbp+var_10], rax
0x1800891e0  mov     r14, rdx
0x1800891e3  mov     rsi, rcx
0x1800891e6  xor     r15d, r15d
0x1800891e9  mov     [rbp+lpCriticalSection], r15
0x1800891ed  mov     rdx, rcx
0x1800891f0  lea     rcx, [rbp+lpCriticalSection]
0x1800891f4  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800891f9  nop
0x1800891fa  xorps   xmm0, xmm0
0x1800891fd  movups  xmmword ptr [rbp+InterfaceGuid], xmm0
0x180089201  xor     r9d, r9d
0x180089204  mov     r8, r14
0x180089207  lea     rdx, [rbp+InterfaceGuid]
0x18008920b  mov     rcx, rsi; lpCriticalSection
0x18008920e  call    ?FindInterface@ConnectionAggregator@@AEAA?AV?$shared_ptr@UWCM_CONAGG_INTERFACE_INFO@@@std@@PEBU_GUID@@H@Z; ConnectionAggregator::FindInterface(_GUID const *,int)
0x180089213  nop
0x180089214  mov     r8, [rbp+InterfaceGuid]
0x180089218  test    r8, r8
0x18008921b  jnz     short loc_180089268
0x18008921d  lea     rdi, WPP_GLOBAL_Control
0x180089224  mov     rcx, cs:WPP_GLOBAL_Control
0x18008922b  cmp     rcx, rdi
0x18008922e  jz      loc_1800895A7
0x180089234  cmp     byte ptr [rcx+19h], 3
0x180089238  jb      loc_1800895A7
0x18008923e  lea     ebx, [r15+1]
0x180089242  test    [rcx+1Ch], bl
0x180089245  jz      loc_1800895A7
0x18008924b  mov     edx, 0FDh
0x180089250  mov     r9, r14
0x180089253  lea     r8, WPP_629ff72c36873acc9d3aa94b4d8c7cd2_Traceguids
0x18008925a  mov     rcx, [rcx+10h]
0x18008925e  call    WPP_SF__guid_
0x180089263  jmp     loc_1800895A7
0x180089268  mov     rcx, r8
0x18008926b  call    ?GetInterfaceStatus@WCM_CONAGG_INTERFACE_INFO@@QEBA?AW4_WCM_INTF_STATUS@@XZ; WCM_CONAGG_INTERFACE_INFO::GetInterfaceStatus(void)
0x180089270  mov     ebx, 1
0x180089275  cmp     eax, ebx
0x180089277  jz      short loc_1800892CE
0x180089279  lea     rdi, WPP_GLOBAL_Control
0x180089280  mov     r10, cs:WPP_GLOBAL_Control
0x180089287  cmp     r10, rdi
0x18008928a  jz      loc_1800895A7
0x180089290  cmp     byte ptr [r10+19h], 3
0x180089295  jb      loc_1800895A7
0x18008929b  test    [r10+1Ch], bl
0x18008929f  jz      loc_1800895A7
0x1800892a5  mov     rcx, r8
0x1800892a8  call    ?GetInterfaceStatus@WCM_CONAGG_INTERFACE_INFO@@QEBA?AW4_WCM_INTF_STATUS@@XZ; WCM_CONAGG_INTERFACE_INFO::GetInterfaceStatus(void)
0x1800892ad  mov     edx, 0FEh
0x1800892b2  mov     [rsp+80h+DueTime], eax
0x1800892b6  mov     r9, r8
0x1800892b9  lea     r8, WPP_629ff72c36873acc9d3aa94b4d8c7cd2_Traceguids
0x1800892c0  mov     rcx, [r10+10h]
0x1800892c4  call    WPP_SF__guid_D
0x1800892c9  jmp     loc_1800895A7
0x1800892ce  mov     eax, [r8+2A0h]
0x1800892d5  test    eax, eax
0x1800892d7  jz      short loc_180089338
0x1800892d9  lea     rdi, WPP_GLOBAL_Control
0x1800892e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800892e7  cmp     rcx, rdi
0x1800892ea  jz      short loc_180089317
0x1800892ec  cmp     byte ptr [rcx+19h], 3
0x1800892f0  jb      short loc_180089317
0x1800892f2  test    [rcx+1Ch], bl
0x1800892f5  jz      short loc_180089317
0x1800892f7  mov     edx, 0FFh
0x1800892fc  mov     [rsp+80h+DueTime], eax
0x180089300  mov     r9, r8
0x180089303  lea     r8, WPP_629ff72c36873acc9d3aa94b4d8c7cd2_Traceguids
0x18008930a  mov     rcx, [rcx+10h]
0x18008930e  call    WPP_SF__guid_D
0x180089313  mov     r8, [rbp+InterfaceGuid]
0x180089317  cmp     [r8+2A0h], ebx
0x18008931e  jnz     loc_1800895A7
0x180089324  cmp     [rsi+50h], r15
0x180089328  jnz     loc_1800895A7
0x18008932e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180089333  jmp     loc_1800895A7
0x180089338  mov     [r8+2A0h], ebx
0x18008933f  mov     rax, [rbp+InterfaceGuid]
0x180089343  mov     [rax+2A8h], r15d
0x18008934a  mov     rax, [rbp+InterfaceGuid]
0x18008934e  mov     [rax+2A4h], r15d
0x180089355  mov     rax, [rbp+InterfaceGuid]
0x180089359  mov     [rax+2F8h], r15b
0x180089360  mov     rax, [rbp+InterfaceGuid]
0x180089364  mov     [rax+2F9h], r15b
0x18008936b  lea     rcx, [rsi+50h]; phNewTimer
0x18008936f  cmp     [rcx], r15
0x180089372  jnz     loc_180089560
0x180089378  mov     [rsp+80h+Flags], r15d; Flags
0x18008937d  mov     [rsp+80h+Period], 7FFFFFFFh; Period
0x180089385  mov     [rsp+80h+DueTime], 61A8h; DueTime
0x18008938d  mov     r9, rsi; Parameter
0x180089390  lea     r8, ?SoftDisconnectTimerCallback@ConnectionAggregator@@CAXPEAXE@Z; Callback
0x180089397  mov     rdx, [rsi+48h]; TimerQueue
0x18008939b  call    cs:__imp_CreateTimerQueueTimer
0x1800893a1  test    eax, eax
0x1800893a3  jnz     short loc_1800893F4
0x1800893a5  call    cs:__imp_GetLastError
0x1800893ab  lea     rdi, WPP_GLOBAL_Control
0x1800893b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800893b9  cmp     rcx, rdi
0x1800893bc  jz      short loc_1800893E0
0x1800893be  cmp     [rcx+19h], bl
0x1800893c1  jb      short loc_1800893E0
0x1800893c3  test    [rcx+1Ch], bl
0x1800893c6  jz      short loc_1800893E0
0x1800893c8  mov     edx, 100h
0x1800893cd  mov     r9d, eax
0x1800893d0  lea     r8, WPP_629ff72c36873acc9d3aa94b4d8c7cd2_Traceguids
0x1800893d7  mov     rcx, [rcx+10h]
0x1800893db  call    WPP_SF_d
0x1800893e0  mov     [rsi+58h], r15d
0x1800893e4  mov     rax, [rbp+InterfaceGuid]
0x1800893e8  mov     [rax+2A0h], r15d
0x1800893ef  jmp     loc_1800895A7
0x1800893f4  lea     rdi, WPP_GLOBAL_Control
0x1800893fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180089402  cmp     rcx, rdi
0x180089405  jz      short loc_18008942B
0x180089407  cmp     byte ptr [rcx+19h], 4
0x18008940b  jb      short loc_18008942B
0x18008940d  test    [rcx+1Ch], bl
0x180089410  jz      short loc_18008942B
0x180089412  mov     edx, 101h
0x180089417  mov     r9, [rbp+InterfaceGuid]
0x18008941b  lea     r8, WPP_629ff72c36873acc9d3aa94b4d8c7cd2_Traceguids
0x180089422  mov     rcx, [rcx+10h]
0x180089426  call    WPP_SF__guid_
0x18008942b  mov     rcx, [rbp+InterfaceGuid]; InterfaceGuid
0x18008942f  lea     r9, [rcx+2E0h]; unsigned __int64 *
0x180089436  lea     r8, [rcx+2C8h]; unsigned __int64 *
0x18008943d  lea     rdx, [rcx+2B0h]; unsigned __int64 *
0x180089444  call    ?GetByteCountsForInterface@@YAKPEBU_GUID@@PEA_K11@Z; GetByteCountsForInterface(_GUID const *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *)
0x180089449  test    eax, eax
0x18008944b  jz      short loc_1800894AD
0x18008944d  mov     rcx, [rbp+InterfaceGuid]
0x180089451  mov     [rcx+2A0h], r15d
0x180089458  mov     rcx, [rbp+InterfaceGuid]
0x18008945c  mov     [rcx+2A8h], r15d
0x180089463  mov     rcx, [rbp+InterfaceGuid]
0x180089467  mov     [rcx+2A4h], r15d
0x18008946e  mov     rcx, cs:WPP_GLOBAL_Control
0x180089475  cmp     rcx, rdi
0x180089478  jz      loc_1800895A7
0x18008947e  cmp     [rcx+19h], bl
0x180089481  jb      loc_1800895A7
0x180089487  test    [rcx+1Ch], bl
0x18008948a  jz      loc_1800895A7
0x180089490  mov     edx, 102h
0x180089495  mov     r9d, eax
0x180089498  lea     r8, WPP_629ff72c36873acc9d3aa94b4d8c7cd2_Traceguids
0x18008949f  mov     rcx, [rcx+10h]
0x1800894a3  call    WPP_SF_d
0x1800894a8  jmp     loc_1800895A7
0x1800894ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800894b4  cmp     rcx, rdi
0x1800894b7  jz      short loc_180089501
0x1800894b9  cmp     byte ptr [rcx+19h], 4
0x1800894bd  jb      short loc_180089501
0x1800894bf  test    [rcx+1Ch], bl
0x1800894c2  jz      short loc_180089501
0x1800894c4  mov     edx, 103h
0x1800894c9  mov     r9, [rbp+InterfaceGuid]
0x1800894cd  mov     rax, [r9+2E0h]
0x1800894d4  mov     qword ptr [rsp+80h+Flags], rax
0x1800894d9  mov     rax, [r9+2C8h]
0x1800894e0  mov     qword ptr [rsp+80h+Period], rax
0x1800894e5  mov     rax, [r9+2B0h]
0x1800894ec  mov     qword ptr [rsp+80h+DueTime], rax
0x1800894f1  lea     r8, WPP_629ff72c36873acc9d3aa94b4d8c7cd2_Traceguids
0x1800894f8  mov     rcx, [rcx+10h]
0x1800894fc  call    WPP_SF__guid_iii
0x180089501  mov     rax, [rbp+InterfaceGuid]
0x180089505  mov     [rax+2A8h], ebx
0x18008950b  mov     [rsi+58h], ebx
0x18008950e  mov     eax, cs:dword_18013A120
0x180089514  cmp     eax, 5
0x180089517  jbe     short loc_180089597
0x180089519  mov     rax, [rbp+InterfaceGuid]
0x18008951d  mov     [rbp+var_38], rax
0x180089521  lea     rax, aBeginningSoftD; "Beginning Soft-disconnect on interface"
0x180089528  mov     [rbp+var_30], rax
0x18008952c  lea     rax, aOnecoreuapNetW; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x180089533  mov     [rbp+var_28], rax
0x180089537  lea     rax, [rbp+var_38]
0x18008953b  mov     qword ptr [rsp+80h+Flags], rax
0x180089540  lea     rax, [rbp+var_30]
0x180089544  mov     qword ptr [rsp+80h+Period], rax
0x180089549  lea     rax, [rbp+var_28]
0x18008954d  mov     qword ptr [rsp+80h+DueTime], rax
0x180089552  lea     rdx, dword_180114254
0x180089559  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &)
0x18008955e  jmp     short loc_180089597
0x180089560  lea     rdi, WPP_GLOBAL_Control
0x180089567  mov     rcx, cs:WPP_GLOBAL_Control
0x18008956e  cmp     rcx, rdi
0x180089571  jz      short loc_180089597
0x180089573  cmp     byte ptr [rcx+19h], 4
0x180089577  jb      short loc_180089597
0x180089579  test    [rcx+1Ch], bl
0x18008957c  jz      short loc_180089597
0x18008957e  mov     edx, 104h
0x180089583  mov     r9, [rbp+InterfaceGuid]
0x180089587  lea     r8, WPP_629ff72c36873acc9d3aa94b4d8c7cd2_Traceguids
0x18008958e  mov     rcx, [rcx+10h]
0x180089592  call    WPP_SF__guid_
0x180089597  mov     r8d, ebx
0x18008959a  lea     rdx, [rbp+InterfaceGuid]
0x18008959e  mov     rcx, rsi
0x1800895a1  call    ?UpdateInterfaceLimitedLinkConnectivity@ConnectionAggregator@@AEAAXAEBV?$shared_ptr@UWCM_CONAGG_INTERFACE_INFO@@@std@@H@Z; ConnectionAggregator::UpdateInterfaceLimitedLinkConnectivity(std::shared_ptr<WCM_CONAGG_INTERFACE_INFO> const &,int)
0x1800895a6  nop
0x1800895a7  mov     rcx, [rbp+InterfaceGuid+8]; this
0x1800895ab  test    rcx, rcx
0x1800895ae  jz      short loc_1800895B6
0x1800895b0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800895b5  nop
0x1800895b6  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x1800895ba  test    rcx, rcx
0x1800895bd  jz      short loc_1800895C5
0x1800895bf  call    cs:__imp_LeaveCriticalSection
0x1800895c5  mov     rcx, [rbp+var_10]
0x1800895c9  xor     rcx, rsp; StackCookie
0x1800895cc  call    __security_check_cookie
0x1800895d1  mov     rbx, [rsp+80h+arg_10]
0x1800895d9  add     rsp, 80h
0x1800895e0  pop     r15
0x1800895e2  pop     r14
0x1800895e4  pop     rdi
0x1800895e5  pop     rsi
0x1800895e6  pop     rbp
0x1800895e7  retn
```
