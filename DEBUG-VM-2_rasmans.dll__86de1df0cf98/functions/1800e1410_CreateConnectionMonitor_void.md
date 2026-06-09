# CreateConnectionMonitor(void)

- ea: `0x1800e1410`
- end: `0x1800e15a0`
- name: `?CreateConnectionMonitor@@YAJXZ`
- size: `400`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800c227c`

## callees

- `0x180005e0c`
- `0x1800a5770`
- `0x1800e13c0`
- `0x1800e1410`
- `0x1800e1be4`
- `0x1800e1e64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e14ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e14ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e145e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e145e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e1470`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e1470`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800e1552`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800e1552`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800e14ac`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800e14ac`

## string_xrefs

- `0x1800e1487`: `VpnAlloc for pTempMonitor`
- `0x1800e1521`: `VpnCriticalSectionCreate for pTempMonitor->connMonitorCs`
- `0x1800e148e`: `CreateConnectionMonitor`
- `0x1800e14df`: `CreateConnectionMonitor`
- `0x1800e1528`: `CreateConnectionMonitor`
- `0x1800e14d8`: `CreateThreadpoolTimer for pTimer`

## pseudocode

```c
__int64 CreateConnectionMonitor(void)
{
  HANDLE ProcessHeap; // rax
  char *v2; // rax
  char *v3; // rdi
  unsigned int v4; // ebx
  PTP_TIMER ThreadpoolTimer; // rax
  signed int LastError; // eax
  int v7; // eax
  int v8; // eax
  unsigned int v9; // ecx
  __int64 v10; // r8

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 15, WPP_7a80880b28e336a1e0ed3acb889178fc_Traceguids);
  if ( g_pMonitor )
    return 0;
  ProcessHeap = GetProcessHeap();
  v2 = (char *)HeapAlloc(ProcessHeap, 8u, 0x48u);
  v3 = v2;
  if ( v2 )
  {
    ThreadpoolTimer = CreateThreadpoolTimer(LogConnectionDetails, v2, 0);
    *(_QWORD *)v3 = ThreadpoolTimer;
    if ( ThreadpoolTimer
      || ((LastError = GetLastError(), LastError > 0)
        ? (v4 = (unsigned __int16)LastError | 0x80070000)
        : (v4 = LastError),
          !LastError) )
    {
      v7 = VpnCriticalSectionCreate(&g_connMonitorCs);
      v4 = v7;
      if ( v7 < 0 )
      {
        v8 = (v7 >> 16) & 0x1FFF;
        v9 = (unsigned __int16)v4;
        if ( v8 != 7 )
          v9 = v4;
        if ( v9 )
        {
          v10 = (unsigned __int16)v4;
          if ( v8 != 7 )
            v10 = v4;
          VpnReportError("CreateConnectionMonitor", "VpnCriticalSectionCreate for pTempMonitor->connMonitorCs", v10);
          goto LABEL_23;
        }
      }
      CleanupConnectionDetails((struct _CONNECTION_DETAILS *)(v3 + 8));
      g_pMonitor = v3;
    }
    else
    {
      VpnReportError("CreateConnectionMonitor", "CreateThreadpoolTimer for pTimer", (unsigned int)LastError);
    }
    if ( (v4 & 0x80000000) == 0 )
      goto LABEL_26;
LABEL_23:
    if ( *(_QWORD *)v3 )
    {
      CloseThreadpoolTimer(*(PTP_TIMER *)v3);
      *(_QWORD *)v3 = 0;
    }
    MprCommonFree(v3);
    goto LABEL_26;
  }
  v4 = -2147024882;
  VpnReportError("CreateConnectionMonitor", "VpnAlloc for pTempMonitor", 14);
LABEL_26:
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 16, WPP_7a80880b28e336a1e0ed3acb889178fc_Traceguids);
  return v4;
}

```

## disassembly

```asm
0x1800e1410  mov     [rsp+arg_0], rbx
0x1800e1415  mov     [rsp+arg_8], rsi
0x1800e141a  push    rdi
0x1800e141b  sub     rsp, 20h
0x1800e141f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e1426  lea     rsi, WPP_GLOBAL_Control
0x1800e142d  cmp     rcx, rsi
0x1800e1430  jz      short loc_1800E144D
0x1800e1432  test    byte ptr [rcx+1Ch], 8
0x1800e1436  jz      short loc_1800E144D
0x1800e1438  mov     rcx, [rcx+10h]
0x1800e143c  lea     r8, WPP_7a80880b28e336a1e0ed3acb889178fc_Traceguids
0x1800e1443  mov     edx, 0Fh
0x1800e1448  call    WPP_SF_
0x1800e144d  cmp     cs:?g_pMonitor@@3PEAU_CONNECTION_MONITOR@@EA, 0; _CONNECTION_MONITOR * g_pMonitor
0x1800e1455  jz      short loc_1800E145E
0x1800e1457  xor     eax, eax
0x1800e1459  jmp     loc_1800E1590
0x1800e145e  call    cs:__imp_GetProcessHeap
0x1800e1464  mov     edx, 8; dwFlags
0x1800e1469  mov     rcx, rax; hHeap
0x1800e146c  lea     r8d, [rdx+40h]; dwBytes
0x1800e1470  call    cs:__imp_HeapAlloc
0x1800e1476  mov     rdi, rax
0x1800e1479  test    rax, rax
0x1800e147c  jnz     short loc_1800E149F
0x1800e147e  lea     r8d, [rax+0Eh]
0x1800e1482  mov     ebx, 8007000Eh
0x1800e1487  lea     rdx, aVpnallocForPte; "VpnAlloc for pTempMonitor"
0x1800e148e  lea     rcx, aCreateconnecti; "CreateConnectionMonitor"
0x1800e1495  call    VpnReportError
0x1800e149a  jmp     loc_1800E1567
0x1800e149f  xor     r8d, r8d; pcbe
0x1800e14a2  lea     rcx, ?LogConnectionDetails@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800e14a9  mov     rdx, rdi; pv
0x1800e14ac  call    cs:__imp_CreateThreadpoolTimer
0x1800e14b2  mov     [rdi], rax
0x1800e14b5  test    rax, rax
0x1800e14b8  jnz     short loc_1800E14ED
0x1800e14ba  call    cs:__imp_GetLastError
0x1800e14c0  test    eax, eax
0x1800e14c2  jg      short loc_1800E14C8
0x1800e14c4  mov     ebx, eax
0x1800e14c6  jmp     short loc_1800E14D1
0x1800e14c8  movzx   ebx, ax
0x1800e14cb  or      ebx, 80070000h
0x1800e14d1  test    eax, eax
0x1800e14d3  jz      short loc_1800E14ED
0x1800e14d5  mov     r8d, eax
0x1800e14d8  lea     rdx, aCreatethreadpo; "CreateThreadpoolTimer for pTimer"
0x1800e14df  lea     rcx, aCreateconnecti; "CreateConnectionMonitor"
0x1800e14e6  call    VpnReportError
0x1800e14eb  jmp     short loc_1800E1546
0x1800e14ed  lea     rcx, ?g_connMonitorCs@@3UVPN_CRITICAL_SECTION_@@A; lpCriticalSection
0x1800e14f4  call    VpnCriticalSectionCreate
0x1800e14f9  mov     ebx, eax
0x1800e14fb  test    eax, eax
0x1800e14fd  jns     short loc_1800E1536
0x1800e14ff  sar     eax, 10h
0x1800e1502  and     eax, 1FFFh
0x1800e1507  movzx   ecx, bx
0x1800e150a  cmp     eax, 7
0x1800e150d  jz      short loc_1800E1511
0x1800e150f  mov     ecx, ebx
0x1800e1511  test    ecx, ecx
0x1800e1513  jz      short loc_1800E1536
0x1800e1515  movzx   r8d, bx
0x1800e1519  cmp     eax, 7
0x1800e151c  jz      short loc_1800E1521
0x1800e151e  mov     r8d, ebx
0x1800e1521  lea     rdx, aVpncriticalsec_9; "VpnCriticalSectionCreate for pTempMonit"...
0x1800e1528  lea     rcx, aCreateconnecti; "CreateConnectionMonitor"
0x1800e152f  call    VpnReportError
0x1800e1534  jmp     short loc_1800E154A
0x1800e1536  lea     rcx, [rdi+8]; struct _CONNECTION_DETAILS *
0x1800e153a  call    ?CleanupConnectionDetails@@YAXPEAU_CONNECTION_DETAILS@@@Z; CleanupConnectionDetails(_CONNECTION_DETAILS *)
0x1800e153f  mov     cs:?g_pMonitor@@3PEAU_CONNECTION_MONITOR@@EA, rdi; _CONNECTION_MONITOR * g_pMonitor
0x1800e1546  test    ebx, ebx
0x1800e1548  jns     short loc_1800E1567
0x1800e154a  mov     rcx, [rdi]; pti
0x1800e154d  test    rcx, rcx
0x1800e1550  jz      short loc_1800E155F
0x1800e1552  call    cs:__imp_CloseThreadpoolTimer
0x1800e1558  mov     qword ptr [rdi], 0
0x1800e155f  mov     rcx, rdi; lpMem
0x1800e1562  call    MprCommonFree
0x1800e1567  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e156e  cmp     rcx, rsi
0x1800e1571  jz      short loc_1800E158E
0x1800e1573  test    byte ptr [rcx+1Ch], 8
0x1800e1577  jz      short loc_1800E158E
0x1800e1579  mov     rcx, [rcx+10h]
0x1800e157d  lea     r8, WPP_7a80880b28e336a1e0ed3acb889178fc_Traceguids
0x1800e1584  mov     edx, 10h
0x1800e1589  call    WPP_SF_
0x1800e158e  mov     eax, ebx
0x1800e1590  mov     rbx, [rsp+28h+arg_0]
0x1800e1595  mov     rsi, [rsp+28h+arg_8]
0x1800e159a  add     rsp, 20h
0x1800e159e  pop     rdi
0x1800e159f  retn
```
