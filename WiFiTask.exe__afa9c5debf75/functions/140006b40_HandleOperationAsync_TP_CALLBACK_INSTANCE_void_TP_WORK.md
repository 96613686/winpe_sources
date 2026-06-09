# HandleOperationAsync(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x140006b40`
- end: `0x140006ce5`
- name: `?HandleOperationAsync@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `421`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, _DWORD *Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task`

## callees

- `0x1400016c4`
- `0x140003594`
- `0x140006b40`
- `0x140009994`
- `0x14000a628`
- `0x14000bf20`
- `0x14000bf60`
- `0x14000eb40`
- `0x14000ec34`
- `0x14000ed48`
- `0x14000ee64`
- `0x14000f1c8`
- `0x14000f338`
- `0x14000f45c`
- `0x14000fc50`
- `0x140010684`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x140006ca3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x140006ca3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006cb0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006cb0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140006ccb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140006ccb`

## pseudocode

```c
void __fastcall HandleOperationAsync(PTP_CALLBACK_INSTANCE Instance, _DWORD *Context, PTP_WORK Work)
{
  __int64 v5; // rcx
  unsigned int v6; // edi
  unsigned int v7; // eax
  unsigned __int8 *v8[2]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v9; // [rsp+40h] [rbp-38h]

  *(_OWORD *)v8 = 0;
  v9 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      &WPP_b0092361ee8d34528df1964c4db39788_Traceguids,
      (unsigned int)Context[2]);
  }
  switch ( Context[2] )
  {
    case 0xD:
      v7 = ExecuteSendNotification((unsigned int)Context[2], Context + 4, v8);
      goto LABEL_24;
    case 0xE:
      v7 = ExecuteRemoveNotification((unsigned int)(Context[2] - 14), Context + 4);
      goto LABEL_24;
    case 0xF:
      v7 = ExecuteClearNotifications();
      goto LABEL_24;
    case 0x10:
      v7 = ExecuteLaunchSettingsUi((unsigned int)(Context[2] - 16), Context + 4);
      goto LABEL_24;
    case 0x14:
      v7 = ExecuteLaunchBrowser((unsigned int)(Context[2] - 20), Context + 4);
      goto LABEL_24;
    case 0x15:
      v7 = ExecuteSendWwanNotification((unsigned int)(Context[2] - 21), Context + 4, v8);
      goto LABEL_24;
    case 0x16:
      v7 = ExecuteRemoveWwanNotification((unsigned int)(Context[2] - 22), Context + 4);
      goto LABEL_24;
  }
  v5 = (unsigned int)(Context[2] - 23);
  if ( Context[2] == 23 )
  {
    v7 = ExecuteClearWwanNotifications(v5, Context + 4);
    goto LABEL_24;
  }
  if ( Context[2] == 24 )
  {
    v7 = ExecuteActivateApplication(v5, Context + 4);
LABEL_24:
    v6 = v7;
    goto LABEL_25;
  }
  v6 = 4317;
LABEL_25:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_ID(*((_QWORD *)WPP_GLOBAL_Control + 2), Context, Work, *(_QWORD *)Context, v6);
  }
  WiFiTaskPipeClient::SendOperationPacket(g_TaskPipe, *(_QWORD *)Context, v6, v8[0], LODWORD(v8[1]) - LODWORD(v8[0]));
  std::vector<unsigned char>::~vector<unsigned char>(Context + 4);
  operator delete(Context);
  CloseThreadpoolWork(Work);
  EnterCriticalSection(&g_csPendingState);
  if ( !--g_dwPendingRequests )
    StartDisconnectTimer();
  LeaveCriticalSection(&g_csPendingState);
  std::vector<unsigned char>::~vector<unsigned char>(v8);
}

```

## disassembly

```asm
0x140006b40  push    rbx
0x140006b42  push    rbp
0x140006b43  push    rsi
0x140006b44  push    rdi
0x140006b45  sub     rsp, 58h
0x140006b49  mov     rsi, r8
0x140006b4c  mov     rbx, rdx
0x140006b4f  xorps   xmm0, xmm0
0x140006b52  movdqu  xmmword ptr [rsp+78h+var_48], xmm0
0x140006b58  mov     [rsp+78h+var_38], 0
0x140006b61  lea     rbp, WPP_GLOBAL_Control
0x140006b68  mov     rcx, cs:WPP_GLOBAL_Control
0x140006b6f  cmp     rcx, rbp
0x140006b72  jz      short loc_140006B99
0x140006b74  cmp     byte ptr [rcx+19h], 4
0x140006b78  jb      short loc_140006B99
0x140006b7a  test    byte ptr [rcx+1Ch], 1
0x140006b7e  jz      short loc_140006B99
0x140006b80  mov     edx, 1Dh
0x140006b85  mov     r9d, [rbx+8]
0x140006b89  lea     r8, WPP_b0092361ee8d34528df1964c4db39788_Traceguids
0x140006b90  mov     rcx, [rcx+10h]
0x140006b94  call    WPP_SF_d
0x140006b99  mov     ecx, [rbx+8]
0x140006b9c  sub     ecx, 0Dh
0x140006b9f  jz      loc_140006C2D
0x140006ba5  sub     ecx, 1
0x140006ba8  jz      short loc_140006C22
0x140006baa  sub     ecx, 1
0x140006bad  jz      short loc_140006C1B
0x140006baf  sub     ecx, 1
0x140006bb2  jz      short loc_140006C10
0x140006bb4  sub     ecx, 4
0x140006bb7  jz      short loc_140006C05
0x140006bb9  sub     ecx, 1
0x140006bbc  jz      short loc_140006BF5
0x140006bbe  sub     ecx, 1
0x140006bc1  jz      short loc_140006BEA
0x140006bc3  sub     ecx, 1
0x140006bc6  jz      short loc_140006BDF
0x140006bc8  cmp     ecx, 1
0x140006bcb  jz      short loc_140006BD4
0x140006bcd  mov     edi, 10DDh
0x140006bd2  jmp     short loc_140006C40
0x140006bd4  lea     rdx, [rbx+10h]
0x140006bd8  call    ?ExecuteActivateApplication@@YAKW4WiFiTaskOpcode@@AEBV?$vector@EV?$allocator@E@std@@@std@@AEAV23@@Z; ExecuteActivateApplication(WiFiTaskOpcode,std::vector<uchar> const &,std::vector<uchar> &)
0x140006bdd  jmp     short loc_140006C3E
0x140006bdf  lea     rdx, [rbx+10h]
0x140006be3  call    ?ExecuteClearWwanNotifications@@YAKW4WiFiTaskOpcode@@AEBV?$vector@EV?$allocator@E@std@@@std@@AEAV23@@Z; ExecuteClearWwanNotifications(WiFiTaskOpcode,std::vector<uchar> const &,std::vector<uchar> &)
0x140006be8  jmp     short loc_140006C3E
0x140006bea  lea     rdx, [rbx+10h]
0x140006bee  call    ?ExecuteRemoveWwanNotification@@YAKW4WiFiTaskOpcode@@AEBV?$vector@EV?$allocator@E@std@@@std@@AEAV23@@Z; ExecuteRemoveWwanNotification(WiFiTaskOpcode,std::vector<uchar> const &,std::vector<uchar> &)
0x140006bf3  jmp     short loc_140006C3E
0x140006bf5  lea     rdx, [rbx+10h]
0x140006bf9  lea     r8, [rsp+78h+var_48]
0x140006bfe  call    ?ExecuteSendWwanNotification@@YAKW4WiFiTaskOpcode@@AEBV?$vector@EV?$allocator@E@std@@@std@@AEAV23@@Z; ExecuteSendWwanNotification(WiFiTaskOpcode,std::vector<uchar> const &,std::vector<uchar> &)
0x140006c03  jmp     short loc_140006C3E
0x140006c05  lea     rdx, [rbx+10h]
0x140006c09  call    ?ExecuteLaunchBrowser@@YAKW4WiFiTaskOpcode@@AEBV?$vector@EV?$allocator@E@std@@@std@@AEAV23@@Z; ExecuteLaunchBrowser(WiFiTaskOpcode,std::vector<uchar> const &,std::vector<uchar> &)
0x140006c0e  jmp     short loc_140006C3E
0x140006c10  lea     rdx, [rbx+10h]
0x140006c14  call    ?ExecuteLaunchSettingsUi@@YAKW4WiFiTaskOpcode@@AEBV?$vector@EV?$allocator@E@std@@@std@@AEAV23@@Z; ExecuteLaunchSettingsUi(WiFiTaskOpcode,std::vector<uchar> const &,std::vector<uchar> &)
0x140006c19  jmp     short loc_140006C3E
0x140006c1b  call    ?ExecuteClearNotifications@@YAKW4WiFiTaskOpcode@@AEBV?$vector@EV?$allocator@E@std@@@std@@AEAV23@@Z; ExecuteClearNotifications(WiFiTaskOpcode,std::vector<uchar> const &,std::vector<uchar> &)
0x140006c20  jmp     short loc_140006C3E
0x140006c22  lea     rdx, [rbx+10h]
0x140006c26  call    ?ExecuteRemoveNotification@@YAKW4WiFiTaskOpcode@@AEBV?$vector@EV?$allocator@E@std@@@std@@AEAV23@@Z; ExecuteRemoveNotification(WiFiTaskOpcode,std::vector<uchar> const &,std::vector<uchar> &)
0x140006c2b  jmp     short loc_140006C3E
0x140006c2d  lea     rdx, [rbx+10h]
0x140006c31  lea     r8, [rsp+78h+var_48]
0x140006c36  mov     ecx, [rbx+8]
0x140006c39  call    ?ExecuteSendNotification@@YAKW4WiFiTaskOpcode@@AEBV?$vector@EV?$allocator@E@std@@@std@@AEAV23@@Z; ExecuteSendNotification(WiFiTaskOpcode,std::vector<uchar> const &,std::vector<uchar> &)
0x140006c3e  mov     edi, eax
0x140006c40  mov     rcx, cs:WPP_GLOBAL_Control
0x140006c47  cmp     rcx, rbp
0x140006c4a  jz      short loc_140006C68
0x140006c4c  cmp     byte ptr [rcx+19h], 4
0x140006c50  jb      short loc_140006C68
0x140006c52  test    byte ptr [rcx+1Ch], 1
0x140006c56  jz      short loc_140006C68
0x140006c58  mov     [rsp+78h+var_58], edi
0x140006c5c  mov     r9, [rbx]
0x140006c5f  mov     rcx, [rcx+10h]
0x140006c63  call    WPP_SF_ID
0x140006c68  mov     eax, dword ptr [rsp+78h+var_48+8]
0x140006c6c  mov     r9, [rsp+78h+var_48]; unsigned __int8 *
0x140006c71  sub     eax, r9d
0x140006c74  mov     [rsp+78h+var_58], eax; unsigned int
0x140006c78  mov     r8d, edi; unsigned int
0x140006c7b  mov     rdx, [rbx]; unsigned __int64
0x140006c7e  mov     rcx, cs:?g_TaskPipe@@3PEAVWiFiTaskPipeClient@@EA; this
0x140006c85  call    ?SendOperationPacket@WiFiTaskPipeClient@@QEAAJ_KKPEBEK@Z; WiFiTaskPipeClient::SendOperationPacket(unsigned __int64,ulong,uchar const *,ulong)
0x140006c8a  lea     rcx, [rbx+10h]
0x140006c8e  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x140006c93  mov     edx, 28h ; '('
0x140006c98  mov     rcx, rbx; Block
0x140006c9b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140006ca0  mov     rcx, rsi; pwk
0x140006ca3  call    cs:__imp_CloseThreadpoolWork
0x140006ca9  lea     rcx, ?g_csPendingState@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140006cb0  call    cs:__imp_EnterCriticalSection
0x140006cb6  add     cs:?g_dwPendingRequests@@3KA, 0FFFFFFFFh; ulong g_dwPendingRequests
0x140006cbd  jnz     short loc_140006CC4
0x140006cbf  call    ?StartDisconnectTimer@@YAXXZ; StartDisconnectTimer(void)
0x140006cc4  lea     rcx, ?g_csPendingState@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140006ccb  call    cs:__imp_LeaveCriticalSection
0x140006cd1  nop
0x140006cd2  lea     rcx, [rsp+78h+var_48]
0x140006cd7  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x140006cdc  add     rsp, 58h
0x140006ce0  pop     rdi
0x140006ce1  pop     rsi
0x140006ce2  pop     rbp
0x140006ce3  pop     rbx
0x140006ce4  retn
```
