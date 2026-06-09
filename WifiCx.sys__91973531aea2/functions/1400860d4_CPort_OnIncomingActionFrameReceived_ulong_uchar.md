# CPort::OnIncomingActionFrameReceived(ulong,uchar *)

- ea: `0x1400860d4`
- end: `0x140086425`
- name: `?OnIncomingActionFrameReceived@CPort@@QEAAXKPEAE@Z`
- size: `849`
- prototype: `void __fastcall(CPort *this, int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140026010`

## callees

- `0x14000c778`
- `0x14000d054`
- `0x140014b30`
- `0x14001a630`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14002bd34`
- `0x140040fcc`
- `0x14008541c`
- `0x1400860d4`
- `0x14008749c`
- `0x1400889f0`
- `0x140088afc`
- `0x1400ab4e8`
- `0x1400c75f4`
- `0x1400c8ee8`
- `0x1400dfd00`
- `0x1400dfd40`

## pseudocode

```c
void __fastcall CPort::OnIncomingActionFrameReceived(CPort *this, int a2, unsigned __int8 *a3)
{
  int v4; // edi
  int v6; // eax
  int v7; // edx
  int v8; // r8d
  char v9; // di
  int v10; // edx
  __int64 v11; // rcx
  CPropertyCache *v12; // rax
  char v13; // al
  QoS::QoSManager *v14; // rcx
  unsigned int v15; // [rsp+50h] [rbp-19h] BYREF
  unsigned __int8 *v16; // [rsp+58h] [rbp-11h] BYREF
  struct _WDI_MAC_ADDRESS v17; // [rsp+60h] [rbp-9h] BYREF
  __int64 v18; // [rsp+68h] [rbp-1h] BYREF
  unsigned int v19; // [rsp+70h] [rbp+7h] BYREF
  struct _DOT11_ANQP_ACTION_FRAME *v20; // [rsp+78h] [rbp+Fh]
  char v21; // [rsp+80h] [rbp+17h]

  v18 = 0;
  v19 = 0;
  v4 = a2;
  v20 = 0;
  v21 = 0;
  *(_DWORD *)v17.Address = 0;
  *(_WORD *)&v17.Address[4] = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      185,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids);
  }
  v6 = ParseWdiIndicationActionFrameReceivedFromIhv(
         (unsigned int)(v4 - 48),
         a3 + 48,
         *((_QWORD *)this + 17) + 5384LL,
         &v17);
  v9 = v6;
  if ( v6 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_42;
    LOBYTE(v7) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      v8,
      186,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
      (char)this,
      *((_WORD *)this + 74),
      v6);
  }
  else if ( v19 >= 2 )
  {
    v10 = (int)v20;
    switch ( *(_BYTE *)v20 )
    {
      case 1:
        if ( *((_BYTE *)v20 + 1) == 4
          && QoS::QoSManager::IsDSCPToUPMappingAllowed((CPort *)((char *)this + 584))
          && *((_BYTE *)v14 + 9) )
        {
          QoS::QoSManager::HandleDSCPToUPMappingConfigureActionFrame(v14);
        }
        break;
      case 4:
        CPort::OnPublicActionFrameReceived(this, &v17, (struct _WDI_BSS_ENTRY_CHANNEL_INFO *)&v18, v19, v20);
        break;
      case 5:
        v13 = *((_BYTE *)v20 + 1);
        if ( v13 == 5 )
        {
          if ( v19 >= 3 )
            CPort::OnNeighborReportReceived(this, &v17, v19 - 3, (unsigned __int8 *)v20 + 3, 0);
        }
        else if ( !v13 && v19 >= 5 )
        {
          CPort::OnRadioMeasurementRequestReceived(this, &v17, v19, (unsigned __int8 *)v20);
        }
        break;
      case 0xA:
        if ( *((_BYTE *)v20 + 1) == 7 )
        {
          v11 = *((_QWORD *)this + 17) + 8LL;
          v15 = 0;
          v16 = 0;
          v12 = (CPropertyCache *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
          if ( !(unsigned int)CPropertyCache::GetPropertyBuffer(v12, 0x19u, &v15, &v16) )
          {
            if ( *((_DWORD *)v16 + 105) )
              CPort::OnBssTransitionManagementRequestReceived(this, &v17, v19, (unsigned __int8 *)v20);
          }
        }
        break;
      case 0x13:
        if ( *((_BYTE *)v20 + 1) == 5 && v19 >= 5 )
          QoS::QoSManager::ProcessUnsolicitedMSCSResponse(
            (CPort *)((char *)this + 584),
            &v17,
            v19,
            (const unsigned __int8 *const)v20);
        break;
      default:
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_42;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          LOBYTE(v10) = 5;
          WPP_RECORDER_SF_qDdd(
            WPP_GLOBAL_Control->DeviceExtension,
            v10,
            v19,
            188,
            (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
            (char)this,
            *((_WORD *)this + 74),
            *(_BYTE *)v20,
            v19);
        }
        break;
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_42;
    LOBYTE(v7) = 2;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      v19,
      187,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
      (char)this,
      *((_WORD *)this + 74));
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v10) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      1,
      189,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
      v9);
  }
LABEL_42:
  ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(&v19);
}

```

## disassembly

```asm
0x1400860d4  push    rbp
0x1400860d6  push    rbx
0x1400860d7  push    rsi
0x1400860d8  push    rdi
0x1400860d9  push    r12
0x1400860db  push    r13
0x1400860dd  push    r14
0x1400860df  lea     rbp, [rsp-27h]
0x1400860e4  sub     rsp, 90h
0x1400860eb  mov     rax, cs:__security_cookie
0x1400860f2  xor     rax, rsp
0x1400860f5  mov     [rbp+57h+var_38], rax
0x1400860f9  xor     eax, eax
0x1400860fb  mov     rsi, r8
0x1400860fe  xor     r14d, r14d
0x140086101  mov     [rbp+57h+var_58], rax
0x140086105  mov     [rbp+57h+var_50], r14d
0x140086109  mov     edi, edx
0x14008610b  mov     [rbp+57h+var_48], r14
0x14008610f  mov     rbx, rcx
0x140086112  mov     [rbp+57h+var_40], r14b
0x140086116  mov     dword ptr [rbp+57h+var_60.Address], eax
0x140086119  mov     word ptr [rbp+57h+var_60.Address+4], ax
0x14008611d  lea     r12, WPP_RECORDER_INITIALIZED
0x140086124  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14008612b  lea     r13, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x140086132  jz      short loc_140086164
0x140086134  mov     rcx, cs:WPP_GLOBAL_Control
0x14008613b  cmp     byte ptr [rcx+29h], 5
0x14008613f  jnb     short loc_140086148
0x140086141  cmp     [rcx+48h], r14w
0x140086146  jz      short loc_140086164
0x140086148  mov     rcx, [rcx+40h]
0x14008614c  mov     r9d, 0B9h
0x140086152  mov     r8d, 1
0x140086158  mov     [rsp+0C0h+var_A0], r13
0x14008615d  mov     dl, 5
0x14008615f  call    WPP_RECORDER_SF_
0x140086164  mov     r8, [rbx+88h]
0x14008616b  lea     rdx, [rsi+30h]
0x14008616f  add     r8, 1508h
0x140086176  lea     ecx, [rdi-30h]
0x140086179  lea     r9, [rbp+57h+var_60]
0x14008617d  call    ParseWdiIndicationActionFrameReceivedFromIhv
0x140086182  mov     edi, eax
0x140086184  test    eax, eax
0x140086186  jz      short loc_1400861CB
0x140086188  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14008618f  jz      loc_1400863FD
0x140086195  movzx   ecx, word ptr [rbx+94h]
0x14008619c  mov     r9d, 0BAh
0x1400861a2  mov     [rsp+0C0h+var_88], eax
0x1400861a6  mov     dl, 2
0x1400861a8  mov     [rsp+0C0h+var_90], ecx
0x1400861ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400861b3  mov     [rsp+0C0h+var_98], rbx
0x1400861b8  mov     [rsp+0C0h+var_A0], r13
0x1400861bd  mov     rcx, [rcx+40h]
0x1400861c1  call    WPP_RECORDER_SF_qDD
0x1400861c6  jmp     loc_1400863C0
0x1400861cb  mov     r8d, [rbp+57h+var_50]; unsigned int
0x1400861cf  cmp     r8d, 2
0x1400861d3  jnb     short loc_140086214
0x1400861d5  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400861dc  jz      loc_1400863FD
0x1400861e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400861e9  mov     r9d, 0BBh
0x1400861ef  movzx   eax, word ptr [rbx+94h]
0x1400861f6  mov     dl, 2
0x1400861f8  mov     [rsp+0C0h+var_90], eax
0x1400861fc  mov     [rsp+0C0h+var_98], rbx
0x140086201  mov     rcx, [rcx+40h]
0x140086205  mov     [rsp+0C0h+var_A0], r13
0x14008620a  call    WPP_RECORDER_SF_qD
0x14008620f  jmp     loc_1400863C0
0x140086214  mov     rdx, [rbp+57h+var_48]
0x140086218  movzx   r10d, byte ptr [rdx]
0x14008621c  mov     ecx, r10d
0x14008621f  sub     ecx, 1
0x140086222  jz      loc_14008639B
0x140086228  sub     ecx, 3
0x14008622b  jz      loc_140086381
0x140086231  sub     ecx, 1
0x140086234  jz      loc_14008633E
0x14008623a  sub     ecx, 5
0x14008623d  jz      loc_1400862CE
0x140086243  cmp     ecx, 9
0x140086246  jz      short loc_1400862A2
0x140086248  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14008624f  jz      loc_1400863FD
0x140086255  mov     rcx, cs:WPP_GLOBAL_Control
0x14008625c  cmp     byte ptr [rcx+29h], 5
0x140086260  jnb     short loc_14008626D
0x140086262  cmp     [rcx+48h], r14w
0x140086267  jz      loc_1400863C0
0x14008626d  movzx   eax, word ptr [rbx+94h]
0x140086274  mov     r9d, 0BCh
0x14008627a  mov     rcx, [rcx+40h]
0x14008627e  mov     dl, 5
0x140086280  mov     [rsp+0C0h+var_80], r8d
0x140086285  mov     [rsp+0C0h+var_88], r10d
0x14008628a  mov     [rsp+0C0h+var_90], eax
0x14008628e  mov     [rsp+0C0h+var_98], rbx
0x140086293  mov     [rsp+0C0h+var_A0], r13
0x140086298  call    WPP_RECORDER_SF_qDdd
0x14008629d  jmp     loc_1400863C0
0x1400862a2  cmp     byte ptr [rdx+1], 5
0x1400862a6  jnz     loc_1400863C0
0x1400862ac  cmp     r8d, 5
0x1400862b0  jb      loc_1400863C0
0x1400862b6  mov     r9, rdx; unsigned __int8 *
0x1400862b9  lea     rcx, [rbx+248h]; this
0x1400862c0  lea     rdx, [rbp+57h+var_60]; struct _WDI_MAC_ADDRESS *
0x1400862c4  call    ?ProcessUnsolicitedMSCSResponse@QoSManager@QoS@@QEAAXAEBU_WDI_MAC_ADDRESS@@KQEBE@Z; QoS::QoSManager::ProcessUnsolicitedMSCSResponse(_WDI_MAC_ADDRESS const &,ulong,uchar const * const)
0x1400862c9  jmp     loc_1400863C0
0x1400862ce  cmp     byte ptr [rdx+1], 7
0x1400862d2  jnz     loc_1400863C0
0x1400862d8  mov     rcx, [rbx+88h]
0x1400862df  add     rcx, 8
0x1400862e3  mov     [rbp+57h+var_70], r14d
0x1400862e7  mov     [rbp+57h+var_68], r14
0x1400862eb  mov     rax, [rcx]
0x1400862ee  mov     rax, [rax+8]
0x1400862f2  call    _guard_dispatch_icall
0x1400862f7  lea     r9, [rbp+57h+var_68]; unsigned __int8 **
0x1400862fb  mov     edx, 19h; unsigned int
0x140086300  lea     r8, [rbp+57h+var_70]; unsigned int *
0x140086304  mov     rcx, rax; this
0x140086307  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z; CPropertyCache::GetPropertyBuffer(ulong,ulong *,uchar * *)
0x14008630c  test    eax, eax
0x14008630e  jnz     loc_1400863C0
0x140086314  mov     rax, [rbp+57h+var_68]
0x140086318  cmp     [rax+1A4h], r14d
0x14008631f  jz      loc_1400863C0
0x140086325  mov     r9, [rbp+57h+var_48]; unsigned __int8 *
0x140086329  lea     rdx, [rbp+57h+var_60]; struct _WDI_MAC_ADDRESS *
0x14008632d  mov     r8d, [rbp+57h+var_50]; unsigned int
0x140086331  mov     rcx, rbx; this
0x140086334  call    ?OnBssTransitionManagementRequestReceived@CPort@@QEAAXAEBU_WDI_MAC_ADDRESS@@KPEAE@Z; CPort::OnBssTransitionManagementRequestReceived(_WDI_MAC_ADDRESS const &,ulong,uchar *)
0x140086339  jmp     loc_1400863C0
0x14008633e  mov     al, [rdx+1]
0x140086341  cmp     al, 5
0x140086343  jnz     short loc_140086366
0x140086345  cmp     r8d, 3
0x140086349  jb      short loc_1400863C0
0x14008634b  lea     r9, [rdx+3]; unsigned __int8 *
0x14008634f  mov     byte ptr [rsp+0C0h+var_A0], r14b; bool
0x140086354  lea     rdx, [rbp+57h+var_60]; struct _WDI_MAC_ADDRESS *
0x140086358  add     r8d, 0FFFFFFFDh; unsigned int
0x14008635c  mov     rcx, rbx; this
0x14008635f  call    ?OnNeighborReportReceived@CPort@@QEAAXAEBU_WDI_MAC_ADDRESS@@KPEAE_N@Z; CPort::OnNeighborReportReceived(_WDI_MAC_ADDRESS const &,ulong,uchar *,bool)
0x140086364  jmp     short loc_1400863C0
0x140086366  test    al, al
0x140086368  jnz     short loc_1400863C0
0x14008636a  cmp     r8d, 5
0x14008636e  jb      short loc_1400863C0
0x140086370  mov     r9, rdx; unsigned __int8 *
0x140086373  mov     rcx, rbx; this
0x140086376  lea     rdx, [rbp+57h+var_60]; struct _WDI_MAC_ADDRESS *
0x14008637a  call    ?OnRadioMeasurementRequestReceived@CPort@@QEAAXAEBU_WDI_MAC_ADDRESS@@KPEAE@Z; CPort::OnRadioMeasurementRequestReceived(_WDI_MAC_ADDRESS const &,ulong,uchar *)
0x14008637f  jmp     short loc_1400863C0
0x140086381  mov     [rsp+0C0h+var_A0], rdx; struct _DOT11_ANQP_ACTION_FRAME *
0x140086386  mov     r9d, r8d; unsigned int
0x140086389  lea     r8, [rbp+57h+var_58]; struct _WDI_BSS_ENTRY_CHANNEL_INFO *
0x14008638d  mov     rcx, rbx; this
0x140086390  lea     rdx, [rbp+57h+var_60]; struct _WDI_MAC_ADDRESS *
0x140086394  call    ?OnPublicActionFrameReceived@CPort@@QEAAXPEAU_WDI_MAC_ADDRESS@@PEAU_WDI_BSS_ENTRY_CHANNEL_INFO@@KPEAE@Z; CPort::OnPublicActionFrameReceived(_WDI_MAC_ADDRESS *,_WDI_BSS_ENTRY_CHANNEL_INFO *,ulong,uchar *)
0x140086399  jmp     short loc_1400863C0
0x14008639b  cmp     byte ptr [rdx+1], 4
0x14008639f  jnz     short loc_1400863C0
0x1400863a1  lea     rcx, [rbx+248h]; this
0x1400863a8  call    ?IsDSCPToUPMappingAllowed@QoSManager@QoS@@QEBA_NXZ; QoS::QoSManager::IsDSCPToUPMappingAllowed(void)
0x1400863ad  test    al, al
0x1400863af  jz      short loc_1400863C0
0x1400863b1  cmp     [rcx+9], r14b
0x1400863b5  jz      short loc_1400863C0
0x1400863b7  lea     rdx, [rbp+57h+var_50]
0x1400863bb  call    ?HandleDSCPToUPMappingConfigureActionFrame@QoSManager@QoS@@AEAAXAEBU?$ArrayOfElements@E@@@Z; QoS::QoSManager::HandleDSCPToUPMappingConfigureActionFrame(ArrayOfElements<uchar> const &)
0x1400863c0  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400863c7  jz      short loc_1400863FD
0x1400863c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400863d0  cmp     byte ptr [rcx+29h], 5
0x1400863d4  jnb     short loc_1400863DD
0x1400863d6  cmp     [rcx+48h], r14w
0x1400863db  jz      short loc_1400863FD
0x1400863dd  mov     rcx, [rcx+40h]
0x1400863e1  mov     r9d, 0BDh
0x1400863e7  mov     dword ptr [rsp+0C0h+var_98], edi
0x1400863eb  mov     r8d, 1
0x1400863f1  mov     dl, 5
0x1400863f3  mov     [rsp+0C0h+var_A0], r13
0x1400863f8  call    WPP_RECORDER_SF_d
0x1400863fd  lea     rcx, [rbp+57h+var_50]; void *
0x140086401  call    ?Cleanup@?$ArrayOfElements@U_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER@WiFiCxTLVStaging@@@@QEAAXXZ; ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(void)
0x140086406  mov     rcx, [rbp+57h+var_38]
0x14008640a  xor     rcx, rsp; StackCookie
0x14008640d  call    __security_check_cookie
0x140086412  add     rsp, 90h
0x140086419  pop     r14
0x14008641b  pop     r13
0x14008641d  pop     r12
0x14008641f  pop     rdi
0x140086420  pop     rsi
0x140086421  pop     rbx
0x140086422  pop     rbp
0x140086423  retn
```
