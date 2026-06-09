# BdeSvcWorkTracking::FinishWorkImpl(void)

- ea: `0x180009c30`
- end: `0x180009f1e`
- name: `?FinishWorkImpl@BdeSvcWorkTracking@@AEAAXXZ`
- size: `750`
- prototype: `void __fastcall(BdeSvcWorkTracking *__hidden this)`
- caller_count: `24`
- callee_count: `5`
- tags: ``

## callers

- `0x180007d90`
- `0x180008b50`
- `0x1800090d0`
- `0x18000a010`
- `0x18001e900`
- `0x180026720`
- `0x1800289c0`
- `0x180031570`
- `0x18003b560`
- `0x18003c780`
- `0x18003db60`
- `0x18003dc30`
- `0x1800429e0`
- `0x1800478d0`
- `0x1800494d0`
- `0x18004f540`
- `0x180054b20`
- `0x1800553b0`
- `0x180055700`
- `0x180055a10`
- `0x180057150`
- `0x1800586f0`
- `0x18005af10`
- `0x18005b6e0`

## callees

- `0x180008b70`
- `0x180009c30`
- `0x180009f30`
- `0x180009f60`
- `0x18002e628`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009c7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009c7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009d9d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009e18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009e5d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009d9d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009e18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009e5d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180009cc9`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180009cc9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009e05`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009e05`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180009e91`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180009e91`

## pseudocode

```c
void __fastcall BdeSvcWorkTracking::FinishWorkImpl(BdeSvcWorkTracking *this)
{
  char v1; // bl
  bool v2; // zf
  int v3; // eax
  int v4; // edi
  PVOID *v5; // rcx
  unsigned int KnownLastErrorHR; // eax

  v1 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
  EnterCriticalSection(&BdeSvcWorkTracking::_svcWorkTracking);
  v2 = dword_18009B8C8 == 1;
  v3 = --dword_18009B8C8;
  if ( !v2 )
  {
    if ( HIBYTE(word_18009B8E8) && v3 == 1 )
    {
      SetEvent(hObject);
      LeaveCriticalSection(&BdeSvcWorkTracking::_svcWorkTracking);
      goto LABEL_25;
    }
    goto LABEL_24;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
  ResetEvent(hEvent);
  if ( HIBYTE(word_18009B8E8) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
    byte_18009B8DC = 1;
    goto LABEL_35;
  }
  v4 = 0;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( byte_18009B8DC )
  {
    if ( v5 == &WPP_GLOBAL_Control )
      goto LABEL_24;
    if ( (*((_BYTE *)v5 + 28) & 8) == 0 )
      goto LABEL_17;
    WPP_SF_(v5[2], 33, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
    goto LABEL_16;
  }
  if ( TrySubmitThreadpoolCallback(
         BdeSvcWorkTracking::BdeSvcWorkStopTransitionWorker,
         &BdeSvcWorkTracking::_svcWorkTracking,
         &pcbe) )
  {
    byte_18009B8DC = 1;
    goto LABEL_16;
  }
  KnownLastErrorHR = NgscbGetKnownLastErrorHR();
  v4 = KnownLastErrorHR;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_17;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
      KnownLastErrorHR);
LABEL_16:
    v5 = (PVOID *)WPP_GLOBAL_Control;
LABEL_17:
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x20) != 0 )
    {
      WPP_SF_d(v5[2], 35, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, (unsigned int)v4);
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v4 >= 0 )
  {
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
      WPP_SF_(v5[2], 27, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
LABEL_24:
    LeaveCriticalSection(&BdeSvcWorkTracking::_svcWorkTracking);
    if ( !v1 )
      goto LABEL_25;
    goto LABEL_36;
  }
  v1 = 1;
  byte_18009B8DC = 1;
  if ( v5 == &WPP_GLOBAL_Control || (*((_BYTE *)v5 + 28) & 2) == 0 )
    goto LABEL_24;
  WPP_SF_(v5[2], 26, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
LABEL_35:
  LeaveCriticalSection(&BdeSvcWorkTracking::_svcWorkTracking);
LABEL_36:
  BdeSvcWorkTracking::BdeSvcWorkStopTransition(&BdeSvcWorkTracking::_svcWorkTracking, 0);
LABEL_25:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
}

```

## disassembly

```asm
0x180009c30  sub     rsp, 28h
0x180009c34  mov     [rsp+28h+arg_0], rbx
0x180009c39  xor     bl, bl
0x180009c3b  mov     [rsp+28h+arg_8], rsi
0x180009c40  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c47  lea     rsi, WPP_GLOBAL_Control
0x180009c4e  cmp     rcx, rsi
0x180009c51  jz      short loc_180009C6E
0x180009c53  test    byte ptr [rcx+1Ch], 20h
0x180009c57  jz      short loc_180009C6E
0x180009c59  mov     rcx, [rcx+10h]
0x180009c5d  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180009c64  mov     edx, 17h
0x180009c69  call    WPP_SF_
0x180009c6e  lea     rcx, ?_svcWorkTracking@BdeSvcWorkTracking@@0V1@A; lpCriticalSection
0x180009c75  mov     [rsp+28h+var_8], rdi
0x180009c7a  call    cs:__imp_EnterCriticalSection
0x180009c81  nop     dword ptr [rax+rax+00h]
0x180009c86  mov     eax, cs:dword_18009B8C8
0x180009c8c  add     eax, 0FFFFFFFFh
0x180009c8f  mov     cs:dword_18009B8C8, eax
0x180009c95  jnz     loc_180009DF1
0x180009c9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ca2  cmp     rcx, rsi
0x180009ca5  jz      short loc_180009CC2
0x180009ca7  test    byte ptr [rcx+1Ch], 8
0x180009cab  jz      short loc_180009CC2
0x180009cad  mov     rcx, [rcx+10h]
0x180009cb1  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180009cb8  mov     edx, 18h
0x180009cbd  call    WPP_SF_
0x180009cc2  mov     rcx, cs:hEvent; hEvent
0x180009cc9  call    cs:__imp_ResetEvent
0x180009cd0  nop     dword ptr [rax+rax+00h]
0x180009cd5  cmp     byte ptr cs:word_18009B8E8+1, bl
0x180009cdb  jnz     loc_180009EAD
0x180009ce1  xor     edi, edi
0x180009ce3  mov     rcx, cs:WPP_GLOBAL_Control
0x180009cea  cmp     rcx, rsi
0x180009ced  jz      short loc_180009D11
0x180009cef  test    byte ptr [rcx+1Ch], 20h
0x180009cf3  jz      short loc_180009D11
0x180009cf5  mov     rcx, [rcx+10h]
0x180009cf9  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180009d00  mov     edx, 20h ; ' '
0x180009d05  call    WPP_SF_
0x180009d0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d11  cmp     cs:byte_18009B8DC, bl
0x180009d17  jz      loc_180009E7C
0x180009d1d  cmp     rcx, rsi
0x180009d20  jz      short loc_180009D96
0x180009d22  test    byte ptr [rcx+1Ch], 8
0x180009d26  jz      short loc_180009D44
0x180009d28  mov     rcx, [rcx+10h]
0x180009d2c  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180009d33  mov     edx, 21h ; '!'
0x180009d38  call    WPP_SF_
0x180009d3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d44  cmp     rcx, rsi
0x180009d47  jz      short loc_180009D6E
0x180009d49  test    byte ptr [rcx+1Ch], 20h
0x180009d4d  jz      short loc_180009D6E
0x180009d4f  mov     rcx, [rcx+10h]
0x180009d53  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180009d5a  mov     edx, 23h ; '#'
0x180009d5f  mov     r9d, edi
0x180009d62  call    WPP_SF_d
0x180009d67  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d6e  test    edi, edi
0x180009d70  js      loc_180009E26
0x180009d76  cmp     rcx, rsi
0x180009d79  jz      short loc_180009D96
0x180009d7b  test    byte ptr [rcx+1Ch], 8
0x180009d7f  jz      short loc_180009D96
0x180009d81  mov     rcx, [rcx+10h]
0x180009d85  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180009d8c  mov     edx, 1Bh
0x180009d91  call    WPP_SF_
0x180009d96  lea     rcx, ?_svcWorkTracking@BdeSvcWorkTracking@@0V1@A; lpCriticalSection
0x180009d9d  call    cs:__imp_LeaveCriticalSection
0x180009da4  nop     dword ptr [rax+rax+00h]
0x180009da9  test    bl, bl
0x180009dab  jnz     loc_180009E69
0x180009db1  mov     rcx, cs:WPP_GLOBAL_Control
0x180009db8  mov     rdi, [rsp+28h+var_8]
0x180009dbd  cmp     rcx, rsi
0x180009dc0  mov     rsi, [rsp+28h+arg_8]
0x180009dc5  mov     rbx, [rsp+28h+arg_0]
0x180009dca  jz      short loc_180009DEB
0x180009dcc  test    byte ptr [rcx+1Ch], 20h
0x180009dd0  jz      short loc_180009DEB
0x180009dd2  mov     rcx, [rcx+10h]
0x180009dd6  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180009ddd  mov     edx, 1Ch
0x180009de2  add     rsp, 28h
0x180009de6  jmp     WPP_SF_
0x180009deb  add     rsp, 28h
0x180009def  retn
0x180009df1  cmp     byte ptr cs:word_18009B8E8+1, bl
0x180009df7  jz      short loc_180009D96
0x180009df9  cmp     eax, 1
0x180009dfc  jnz     short loc_180009D96
0x180009dfe  mov     rcx, cs:hObject; hEvent
0x180009e05  call    cs:__imp_SetEvent
0x180009e0c  nop     dword ptr [rax+rax+00h]
0x180009e11  lea     rcx, ?_svcWorkTracking@BdeSvcWorkTracking@@0V1@A; lpCriticalSection
0x180009e18  call    cs:__imp_LeaveCriticalSection
0x180009e1f  nop     dword ptr [rax+rax+00h]
0x180009e24  jmp     short loc_180009DB1
0x180009e26  mov     bl, 1
0x180009e28  mov     cs:byte_18009B8DC, bl
0x180009e2e  cmp     rcx, rsi
0x180009e31  jz      loc_180009D96
0x180009e37  test    byte ptr [rcx+1Ch], 2
0x180009e3b  jz      loc_180009D96
0x180009e41  mov     rcx, [rcx+10h]
0x180009e45  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180009e4c  mov     edx, 1Ah
0x180009e51  call    WPP_SF_
0x180009e56  lea     rcx, ?_svcWorkTracking@BdeSvcWorkTracking@@0V1@A; lpCriticalSection
0x180009e5d  call    cs:__imp_LeaveCriticalSection
0x180009e64  nop     dword ptr [rax+rax+00h]
0x180009e69  xor     edx, edx; struct _TP_CALLBACK_INSTANCE *
0x180009e6b  lea     rcx, ?_svcWorkTracking@BdeSvcWorkTracking@@0V1@A; lpCriticalSection
0x180009e72  call    ?BdeSvcWorkStopTransition@BdeSvcWorkTracking@@AEAAXPEAU_TP_CALLBACK_INSTANCE@@@Z; BdeSvcWorkTracking::BdeSvcWorkStopTransition(_TP_CALLBACK_INSTANCE *)
0x180009e77  jmp     loc_180009DB1
0x180009e7c  lea     r8, pcbe; pcbe
0x180009e83  lea     rdx, ?_svcWorkTracking@BdeSvcWorkTracking@@0V1@A; pv
0x180009e8a  lea     rcx, ?BdeSvcWorkStopTransitionWorker@BdeSvcWorkTracking@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x180009e91  call    cs:__imp_TrySubmitThreadpoolCallback
0x180009e98  nop     dword ptr [rax+rax+00h]
0x180009e9d  test    eax, eax
0x180009e9f  jz      short loc_180009EE0
0x180009ea1  mov     cs:byte_18009B8DC, 1
0x180009ea8  jmp     loc_180009D3D
0x180009ead  mov     rcx, cs:WPP_GLOBAL_Control
0x180009eb4  cmp     rcx, rsi
0x180009eb7  jz      short loc_180009ED4
0x180009eb9  test    byte ptr [rcx+1Ch], 2
0x180009ebd  jz      short loc_180009ED4
0x180009ebf  mov     rcx, [rcx+10h]
0x180009ec3  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180009eca  mov     edx, 19h
0x180009ecf  call    WPP_SF_
0x180009ed4  mov     cs:byte_18009B8DC, 1
0x180009edb  jmp     loc_180009E56
0x180009ee0  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x180009ee5  mov     edi, eax
0x180009ee7  mov     rcx, cs:WPP_GLOBAL_Control
0x180009eee  cmp     rcx, rsi
0x180009ef1  jz      loc_180009D6E
0x180009ef7  test    byte ptr [rcx+1Ch], 40h
0x180009efb  jz      loc_180009D44
0x180009f01  mov     rcx, [rcx+10h]
0x180009f05  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180009f0c  mov     edx, 22h ; '"'
0x180009f11  mov     r9d, eax
0x180009f14  call    WPP_SF_d
0x180009f19  jmp     loc_180009D3D
```
