# CPort::IncorporateBSSEntryList(ArrayOfElements<_WDI_BSS_ENTRY_CONTAINER> *,ulong *,DOT11_BSSID_CANDIDATE *)

- ea: `0x14000e838`
- end: `0x14000eac6`
- name: `?IncorporateBSSEntryList@CPort@@AEAAHPEAU?$ArrayOfElements@U_WDI_BSS_ENTRY_CONTAINER@@@@PEAKPEAUDOT11_BSSID_CANDIDATE@@@Z`
- size: `654`
- prototype: `__int64 __fastcall(CPort *this)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000e4b0`
- `0x1400886f0`

## callees

- `0x14000e838`
- `0x1400109a0`
- `0x140010b20`
- `0x140017b50`
- `0x140034e04`
- `0x140034ec4`
- `0x140048ce0`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14000e9ba`
- `ntoskrnl!RtlCompareMemory` at `0x14000e9ba`

## pseudocode

```c
__int64 __fastcall CPort::IncorporateBSSEntryList(CPort *this, __int64 a2, unsigned int *a3, __int64 a4)
{
  unsigned int v4; // r15d
  __int64 v5; // rbp
  CPort *v6; // rdi
  unsigned int *v7; // rsi
  unsigned int v8; // r14d
  bool v9; // zf
  CAdapter *m_pAdapter; // rcx
  enum _WFC_PORT_TYPE v11; // edx
  int v12; // edx
  struct CBSSListManager *BSSListManager; // rbx
  int v14; // r8d
  unsigned int v15; // r12d
  unsigned int v16; // r13d
  CAdapter *v17; // rcx
  CPropertyCache *v18; // rax
  int v19; // edx
  CBSSListManager *v20; // rsi
  unsigned int v21; // eax
  struct CBSSEntry *v22; // rbx
  struct DOT11_CONNECTION_INFO *CurrentConnectionInfo; // rax
  struct DOT11_CONNECTION_INFO *v24; // rdi
  unsigned int v25; // ebp
  unsigned __int8 *m_BssID; // rdx
  __int64 v27; // r13
  __int64 v28; // rax
  __int64 v29; // rcx
  unsigned __int8 v31[4]; // [rsp+30h] [rbp-68h] BYREF
  unsigned int v32; // [rsp+34h] [rbp-64h]
  struct CBSSEntry *v33; // [rsp+38h] [rbp-60h] BYREF
  struct CBSSListManager *v34; // [rsp+40h] [rbp-58h]
  unsigned __int64 v35; // [rsp+48h] [rbp-50h]

  v4 = 0;
  v5 = a2;
  v33 = 0;
  v6 = this;
  v7 = a3;
  v8 = 0;
  v9 = this->m_WfcPortType == WfcPortTypeExtSTA;
  m_pAdapter = this->m_pAdapter;
  v11 = WfcPortTypeExtSTA;
  if ( !v9 )
    v11 = WfcPortTypeWFDDevice;
  BSSListManager = CAdapter::GetBSSListManager(m_pAdapter, v11);
  v34 = BSSListManager;
  v15 = 0;
  v32 = 0;
  v16 = 0;
  v31[0] = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v12) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      v14,
      326,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids);
  }
  if ( v7 )
  {
    v16 = *v7;
    v32 = *v7;
  }
  v17 = v6->m_pAdapter;
  v35 = MEMORY[0xFFFFF78000000014];
  v18 = v17->GetAdapterPropertyCache(&v17->IPropertyCacheDirectory);
  CPropertyCache::GetPropertyUchar(v18, 0x86u, v31);
  v19 = 0;
  if ( *(_DWORD *)v5 )
  {
    v20 = BSSListManager;
    do
    {
      v21 = CBSSListManager::ReceiveBeaconOrProbe(
              v20,
              (CBSSEntryFactory *)(*(_QWORD *)(v5 + 8) + 144LL * v4),
              (struct _LIST_ENTRY *)v35,
              v31[0],
              &v33);
      v19 = 0;
      v8 = v21;
      if ( v21 )
        break;
      v22 = v33;
      if ( v33 )
      {
        CurrentConnectionInfo = CPort::GetCurrentConnectionInfo(v6);
        v19 = 0;
        v24 = CurrentConnectionInfo;
        if ( CurrentConnectionInfo && v22->m_SignalInfo.Rssi < 0 )
        {
          v25 = 0;
          if ( CurrentConnectionInfo->NumLinks )
          {
            m_BssID = v22->m_BssID;
            while ( 1 )
            {
              v27 = v25;
              if ( RtlCompareMemory(v24->LinkInfo[v27].AuthenticatorLinkAddress, m_BssID, 6u) == 6 )
                break;
              ++v25;
              m_BssID = v22->m_BssID;
              if ( v25 >= v24->NumLinks )
                goto LABEL_21;
            }
            v24->LinkInfo[v27].Rssi = v22->m_SignalInfo.Rssi;
LABEL_21:
            v16 = v32;
            v19 = 0;
          }
          v5 = a2;
        }
        v6 = this;
        if ( v16 > v15 )
        {
          v28 = v15++;
          v29 = 3 * v28;
          *(_DWORD *)(a4 + 4 * v29) = *(_DWORD *)v22->m_BssID;
          *(_WORD *)(a4 + 4 * v29 + 4) = *(_WORD *)&v22->m_BssID[4];
          *(_DWORD *)(a4 + 4 * v29 + 8) = v22->m_ConnectionCapabilityFlags;
          v19 = 0;
        }
      }
      ++v4;
      v33 = 0;
    }
    while ( v4 < *(_DWORD *)v5 );
    v7 = a3;
    BSSListManager = v34;
  }
  if ( v7 )
    *v7 = v15;
  BSSListManager->m_DebugScanBSSEntryCount += *(_DWORD *)v5;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v19) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v19,
      1,
      327,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
      v8);
  }
  return v8;
}

```

## disassembly

```asm
0x14000e838  mov     rax, rsp
0x14000e83b  mov     [rax+20h], r9
0x14000e83f  mov     [rax+18h], r8
0x14000e843  mov     [rax+10h], rdx
0x14000e847  mov     [rax+8], rcx
0x14000e84b  push    rbx
0x14000e84c  push    rbp
0x14000e84d  push    rsi
0x14000e84e  push    rdi
0x14000e84f  push    r12
0x14000e851  push    r13
0x14000e853  push    r14
0x14000e855  push    r15
0x14000e857  sub     rsp, 58h
0x14000e85b  xor     r15d, r15d
0x14000e85e  mov     rbp, rdx
0x14000e861  mov     [rax-60h], r15
0x14000e865  mov     rdi, rcx
0x14000e868  mov     rsi, r8
0x14000e86b  mov     r14d, r15d
0x14000e86e  lea     r8d, [r15+1]
0x14000e872  cmp     [rcx+68h], r8d
0x14000e876  lea     eax, [r15+4]
0x14000e87a  mov     rcx, [rcx+58h]; this
0x14000e87e  mov     edx, r8d
0x14000e881  cmovnz  edx, eax; enum _WFC_PORT_TYPE
0x14000e884  call    ?GetBSSListManager@CAdapter@@QEAAPEAVCBSSListManager@@W4_WFC_PORT_TYPE@@@Z; CAdapter::GetBSSListManager(_WFC_PORT_TYPE)
0x14000e889  mov     rbx, rax
0x14000e88c  mov     [rsp+98h+var_58], rax
0x14000e891  mov     r12d, r15d
0x14000e894  mov     [rsp+98h+var_64], r15d
0x14000e899  mov     r13d, r15d
0x14000e89c  mov     [rsp+98h+var_68], r15b
0x14000e8a1  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000e8a8  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14000e8af  lea     rax, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x14000e8b6  jz      short loc_14000E8E2
0x14000e8b8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e8bf  cmp     byte ptr [rcx+29h], 5
0x14000e8c3  jnb     short loc_14000E8CC
0x14000e8c5  cmp     [rcx+48h], r15w
0x14000e8ca  jz      short loc_14000E8E2
0x14000e8cc  mov     rcx, [rcx+40h]
0x14000e8d0  mov     r9d, 146h
0x14000e8d6  mov     dl, 5
0x14000e8d8  mov     [rsp+98h+var_78], rax
0x14000e8dd  call    WPP_RECORDER_SF_
0x14000e8e2  test    rsi, rsi
0x14000e8e5  jz      short loc_14000E8EF
0x14000e8e7  mov     r13d, [rsi]
0x14000e8ea  mov     [rsp+98h+var_64], r13d
0x14000e8ef  mov     rax, 0FFFFF78000000014h
0x14000e8f9  mov     rax, [rax]
0x14000e8fc  mov     rcx, [rdi+58h]
0x14000e900  mov     [rsp+98h+var_50], rax
0x14000e905  add     rcx, 8
0x14000e909  mov     rax, [rcx]
0x14000e90c  mov     rax, [rax+8]
0x14000e910  call    _guard_dispatch_icall
0x14000e915  lea     r8, [rsp+98h+var_68]; unsigned __int8 *
0x14000e91a  mov     edx, 86h; unsigned int
0x14000e91f  mov     rcx, rax; this
0x14000e922  call    ?GetPropertyUchar@CPropertyCache@@QEAAHKPEAE@Z; CPropertyCache::GetPropertyUchar(ulong,uchar *)
0x14000e927  xor     edx, edx
0x14000e929  cmp     [rbp+0], edx
0x14000e92c  jbe     loc_14000EA58
0x14000e932  mov     rsi, rbx
0x14000e935  mov     r9b, [rsp+98h+var_68]; unsigned __int8
0x14000e93a  mov     rcx, rsi; this
0x14000e93d  mov     r8, [rsp+98h+var_50]; unsigned __int64
0x14000e942  mov     eax, r15d
0x14000e945  lea     rdx, [rax+rax*8]
0x14000e949  shl     rdx, 4
0x14000e94d  lea     rax, [rsp+98h+var_60]
0x14000e952  add     rdx, [rbp+8]; struct _WDI_BSS_ENTRY_CONTAINER *
0x14000e956  mov     [rsp+98h+var_78], rax; struct CBSSEntry **
0x14000e95b  call    ?ReceiveBeaconOrProbe@CBSSListManager@@QEAAHPEAU_WDI_BSS_ENTRY_CONTAINER@@_KEPEAPEAVCBSSEntry@@@Z; CBSSListManager::ReceiveBeaconOrProbe(_WDI_BSS_ENTRY_CONTAINER *,unsigned __int64,uchar,CBSSEntry * *)
0x14000e960  xor     edx, edx
0x14000e962  mov     r14d, eax
0x14000e965  test    eax, eax
0x14000e967  jnz     loc_14000EA4B
0x14000e96d  mov     rbx, [rsp+98h+var_60]
0x14000e972  test    rbx, rbx
0x14000e975  jz      loc_14000EA39
0x14000e97b  mov     rcx, rdi; this
0x14000e97e  call    ?GetCurrentConnectionInfo@CPort@@QEAAPEAUDOT11_CONNECTION_INFO@@XZ; CPort::GetCurrentConnectionInfo(void)
0x14000e983  xor     edx, edx
0x14000e985  mov     rdi, rax
0x14000e988  test    rax, rax
0x14000e98b  jz      short loc_14000E9F9
0x14000e98d  cmp     [rbx+1D0h], edx
0x14000e993  jge     short loc_14000E9F9
0x14000e995  mov     ebp, edx
0x14000e997  cmp     [rax+68h], edx
0x14000e99a  jbe     short loc_14000E9F1
0x14000e99c  lea     rdx, [rbx+1BCh]; Source2
0x14000e9a3  mov     eax, ebp
0x14000e9a5  mov     r8d, 6; Length
0x14000e9ab  lea     r13, [rax+rax*2]
0x14000e9af  shl     r13, 4
0x14000e9b3  lea     rcx, [r13+7Bh]
0x14000e9b7  add     rcx, rdi; Source1
0x14000e9ba  call    cs:__imp_RtlCompareMemory
0x14000e9c1  nop     dword ptr [rax+rax+00h]
0x14000e9c6  cmp     rax, 6
0x14000e9ca  jz      short loc_14000E9DC
0x14000e9cc  inc     ebp
0x14000e9ce  lea     rdx, [rbx+1BCh]
0x14000e9d5  cmp     ebp, [rdi+68h]
0x14000e9d8  jb      short loc_14000E9A3
0x14000e9da  jmp     short loc_14000E9EA
0x14000e9dc  mov     eax, [rbx+1D0h]
0x14000e9e2  mov     [rdi+r13+94h], eax
0x14000e9ea  mov     r13d, [rsp+98h+var_64]
0x14000e9ef  xor     edx, edx
0x14000e9f1  mov     rbp, [rsp+98h+arg_8]
0x14000e9f9  mov     rdi, [rsp+98h+arg_0]
0x14000ea01  cmp     r13d, r12d
0x14000ea04  jbe     short loc_14000EA39
0x14000ea06  mov     rdx, [rsp+98h+arg_18]
0x14000ea0e  mov     eax, r12d
0x14000ea11  inc     r12d
0x14000ea14  lea     rcx, [rax+rax*2]
0x14000ea18  mov     eax, [rbx+1BCh]
0x14000ea1e  mov     [rdx+rcx*4], eax
0x14000ea21  movzx   eax, word ptr [rbx+1C0h]
0x14000ea28  mov     [rdx+rcx*4+4], ax
0x14000ea2d  mov     eax, [rbx+2D8h]
0x14000ea33  mov     [rdx+rcx*4+8], eax
0x14000ea37  xor     edx, edx
0x14000ea39  inc     r15d
0x14000ea3c  mov     [rsp+98h+var_60], rdx
0x14000ea41  cmp     r15d, [rbp+0]
0x14000ea45  jb      loc_14000E935
0x14000ea4b  mov     rsi, [rsp+98h+arg_10]
0x14000ea53  mov     rbx, [rsp+98h+var_58]
0x14000ea58  test    rsi, rsi
0x14000ea5b  jz      short loc_14000EA60
0x14000ea5d  mov     [rsi], r12d
0x14000ea60  mov     eax, [rbp+0]
0x14000ea63  add     [rbx+30h], eax
0x14000ea66  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000ea6d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000ea74  jz      short loc_14000EAB1
0x14000ea76  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ea7d  cmp     byte ptr [rcx+29h], 5
0x14000ea81  jnb     short loc_14000EA89
0x14000ea83  cmp     [rcx+48h], dx
0x14000ea87  jz      short loc_14000EAB1
0x14000ea89  mov     rcx, [rcx+40h]
0x14000ea8d  lea     rax, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x14000ea94  mov     r9d, 147h
0x14000ea9a  mov     [rsp+98h+var_70], r14d
0x14000ea9f  mov     r8d, 1
0x14000eaa5  mov     [rsp+98h+var_78], rax
0x14000eaaa  mov     dl, 5
0x14000eaac  call    WPP_RECORDER_SF_D
0x14000eab1  mov     eax, r14d
0x14000eab4  add     rsp, 58h
0x14000eab8  pop     r15
0x14000eaba  pop     r14
0x14000eabc  pop     r13
0x14000eabe  pop     r12
0x14000eac0  pop     rdi
0x14000eac1  pop     rsi
0x14000eac2  pop     rbp
0x14000eac3  pop     rbx
0x14000eac4  retn
```
