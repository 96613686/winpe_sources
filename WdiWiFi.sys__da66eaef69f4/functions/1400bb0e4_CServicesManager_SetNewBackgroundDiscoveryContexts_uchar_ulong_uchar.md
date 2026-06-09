# CServicesManager::SetNewBackgroundDiscoveryContexts(uchar,ulong,uchar *)

- ea: `0x1400bb0e4`
- end: `0x1400bb526`
- name: `?SetNewBackgroundDiscoveryContexts@CServicesManager@@QEAAHEKPEAE@Z`
- size: `1090`
- prototype: `__int64 __fastcall(CServicesManager *__hidden this, unsigned __int8, unsigned int, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting, service_task`

## callers

- `0x1400626e0`
- `0x1400c7acc`
- `0x1400c8130`

## callees

- `0x140017a90`
- `0x140034e04`
- `0x140034ec4`
- `0x14004363c`
- `0x140063e10`
- `0x1400707e8`
- `0x1400b9690`
- `0x1400bb0e4`
- `0x1400bd820`
- `0x1400da740`

## import_xrefs

- `ntoskrnl!tolower` at `0x1400bb3c0`
- `ntoskrnl!tolower` at `0x1400bb3c0`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb20c`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb35a`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb20c`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb35a`

## pseudocode

```c
__int64 __fastcall CServicesManager::SetNewBackgroundDiscoveryContexts(
        CServicesManager *this,
        unsigned __int8 a2,
        unsigned int a3,
        unsigned __int8 *a4)
{
  unsigned __int8 v6; // r13
  enum _WFC_PORT_TYPE v8; // edx
  int NdisPortNumberForPortType; // eax
  int v10; // edx
  int v11; // r8d
  int v12; // r9d
  unsigned int v13; // ebx
  int v14; // r14d
  unsigned int i; // ebp
  __int64 Pool2; // rax
  struct _LIST_ENTRY *v17; // rbx
  __int64 v18; // rax
  struct _LIST_ENTRY *Blink; // rcx
  int v20; // eax
  __int64 v21; // rbp
  unsigned int v22; // r12d
  unsigned __int8 *v23; // r15
  __int64 v24; // rax
  __int64 v25; // r14
  __int64 v26; // rax
  char v27; // r8
  char v28; // dl
  int v29; // r8d
  int v30; // r9d
  unsigned int j; // r13d
  struct _LIST_ENTRY *v32; // rcx
  int v33; // ecx
  bool v34; // al
  CAdapter *m_pAdapter; // rcx
  bool v36; // zf
  int v38; // [rsp+20h] [rbp-58h]
  __int64 v39; // [rsp+28h] [rbp-50h]

  v6 = a2;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      184,
      (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids);
  }
  CServicesManager::FlushDiscoveryContexts(this);
  NdisPortNumberForPortType = CAdapter::GetNdisPortNumberForPortType(
                                this->m_pAdapter,
                                v8,
                                &this->m_NdisDevicePortNumber);
  v12 = 0;
  v13 = NdisPortNumberForPortType;
  if ( NdisPortNumberForPortType )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return v13;
    LOBYTE(v10) = 2;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      1,
      185,
      (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids,
      NdisPortNumberForPortType);
    LOWORD(v12) = 0;
  }
  else
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v10) = 5;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        v11,
        186,
        (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids,
        *((_DWORD *)a4 + 5));
      v12 = 0;
    }
    v14 = *((_DWORD *)a4 + 4);
    for ( i = 0; i < *((_DWORD *)a4 + 5); ++i )
    {
      Pool2 = ExAllocatePool2(64, 48, 1198089303);
      v12 = 0;
      v17 = (struct _LIST_ENTRY *)Pool2;
      if ( !Pool2 )
        break;
      *(_QWORD *)(Pool2 + 24) = 0;
      *(_BYTE *)(Pool2 + 32) = 0;
      InitializeCppListEntry((void *)Pool2, (struct _CPP_LIST_ENTRY *)Pool2);
      v10 = v14;
      *(_DWORD *)(v18 + 40) = *(_DWORD *)&a4[v14];
      *(_WORD *)(v18 + 44) = *(_WORD *)&a4[v14 + 4];
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) != (_WORD)v12) )
      {
        LOBYTE(v10) = 5;
        WPP_RECORDER_SF_d_MAC_(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          v11,
          187,
          (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids,
          this->m_TrackedP2PDevicesCount,
          v18 + 40);
        v12 = 0;
      }
      Blink = this->m_TrackedP2PDevicesList.Blink;
      if ( Blink->Flink != &this->m_TrackedP2PDevicesList )
LABEL_42:
        __fastfail(3u);
      v17->Flink = &this->m_TrackedP2PDevicesList;
      v14 += 6;
      v17->Blink = Blink;
      Blink->Flink = v17;
      this->m_TrackedP2PDevicesList.Blink = v17;
      ++this->m_TrackedP2PDevicesCount;
    }
    v20 = *((_DWORD *)a4 + 14);
    if ( v20 )
    {
      v21 = *((unsigned int *)a4 + 15);
      if ( a3 > (unsigned int)v21 )
      {
        v22 = a3 - v21;
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) != (_WORD)v12) )
        {
          LOBYTE(v10) = 5;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v10,
            v11,
            188,
            (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids,
            v20);
          v12 = 0;
        }
        v23 = &a4[v21];
        while ( this->m_TrackedP2PServicesCount < *((_DWORD *)a4 + 14) )
        {
          if ( v22 < 2 )
            break;
          if ( v22 < (unsigned int)*v23 + 1 )
            break;
          v24 = ExAllocatePool2(64, 304, 1198089303);
          v12 = 0;
          v25 = v24;
          if ( !v24 )
            break;
          *(_QWORD *)(v24 + 24) = 0;
          *(_BYTE *)(v24 + 32) = 0;
          InitializeCppListEntry((void *)v24, (struct _CPP_LIST_ENTRY *)v24);
          v28 = -1;
          if ( v27 != -1 )
            v28 = v27;
          *(_BYTE *)(v26 + 40) = v28;
          memset((void *)(v26 + 41), 0, 0x100u);
          for ( j = 0; j < *(unsigned __int8 *)(v25 + 40); ++j )
            *(_BYTE *)(j + v25 + 41) = tolower(v23[j + 1]);
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
            && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
          {
            WPP_RECORDER_SF_dds(
              WPP_GLOBAL_Control->DeviceExtension,
              *v23,
              v29,
              v30,
              v38,
              this->m_TrackedP2PServicesCount,
              *v23,
              v25 + 41);
          }
          v32 = this->m_TrackedP2PServicesList.Blink;
          if ( v32->Flink != &this->m_TrackedP2PServicesList )
            goto LABEL_42;
          *(_QWORD *)v25 = &this->m_TrackedP2PServicesList;
          *(_QWORD *)(v25 + 8) = v32;
          v32->Flink = (struct _LIST_ENTRY *)v25;
          this->m_TrackedP2PServicesList.Blink = (struct _LIST_ENTRY *)v25;
          ++this->m_TrackedP2PServicesCount;
          v33 = *v23;
          LODWORD(v21) = v33 + v21 + 1;
          v22 += -1 - v33;
          v23 = &a4[(unsigned int)v21];
          v12 = 0;
        }
        v6 = a2;
      }
    }
    this->m_NotifyAllDevicesAndServices = v6;
    if ( v6 || this->m_TrackedP2PDevicesCount != v12 || (v34 = v12, this->m_TrackedP2PServicesCount != v12) )
      v34 = 1;
    v13 = 0;
    this->m_P2PBackgroundNotificationsEnabled = v34;
    m_pAdapter = this->m_pAdapter;
    v36 = m_pAdapter->m_DevicePortBSSList.m_PortType == WfcPortTypeWFDDevice;
    m_pAdapter->m_DevicePortBSSList.m_BackgroundDiscoveryEnabled = v34;
    if ( v36 )
    {
      v10 = -994967296;
      m_pAdapter->m_DevicePortBSSList.m_BssEntryExpiryTime = (-(__int64)v34 & 0xC4B20100LL) + 300000000;
    }
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) != (_WORD)v12) )
  {
    LODWORD(v39) = v13;
    LOBYTE(v10) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      1,
      190,
      (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids,
      v39);
  }
  return v13;
}

```

## disassembly

```asm
0x1400bb0e4  mov     [rsp+arg_10], rbx
0x1400bb0e9  mov     [rsp+arg_8], dl
0x1400bb0ed  push    rbp
0x1400bb0ee  push    rsi
0x1400bb0ef  push    rdi
0x1400bb0f0  push    r12
0x1400bb0f2  push    r13
0x1400bb0f4  push    r14
0x1400bb0f6  push    r15
0x1400bb0f8  sub     rsp, 40h
0x1400bb0fc  mov     rsi, r9
0x1400bb0ff  mov     r12d, r8d
0x1400bb102  mov     r13b, dl
0x1400bb105  mov     rdi, rcx
0x1400bb108  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400bb10f  xor     eax, eax
0x1400bb111  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400bb118  lea     rbp, WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids
0x1400bb11f  jz      short loc_1400BB150
0x1400bb121  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb128  cmp     byte ptr [rcx+29h], 5
0x1400bb12c  jnb     short loc_1400BB134
0x1400bb12e  cmp     [rcx+48h], ax
0x1400bb132  jz      short loc_1400BB150
0x1400bb134  mov     rcx, [rcx+40h]
0x1400bb138  mov     r9d, 0B8h
0x1400bb13e  mov     r8d, 1
0x1400bb144  mov     [rsp+78h+var_58], rbp
0x1400bb149  mov     dl, 5
0x1400bb14b  call    WPP_RECORDER_SF_
0x1400bb150  mov     rcx, rdi; this
0x1400bb153  call    ?FlushDiscoveryContexts@CServicesManager@@AEAAXXZ; CServicesManager::FlushDiscoveryContexts(void)
0x1400bb158  mov     rcx, [rdi+8]; this
0x1400bb15c  lea     r8, [rdi+18h]; unsigned int *
0x1400bb160  call    ?GetNdisPortNumberForPortType@CAdapter@@QEAAHW4_WFC_PORT_TYPE@@PEAK@Z; CAdapter::GetNdisPortNumberForPortType(_WFC_PORT_TYPE,ulong *)
0x1400bb165  xor     r9d, r9d
0x1400bb168  mov     [rsp+78h+arg_0], eax
0x1400bb16f  mov     ebx, eax
0x1400bb171  test    eax, eax
0x1400bb173  jz      short loc_1400BB1B1
0x1400bb175  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400bb17c  jz      loc_1400BB50B
0x1400bb182  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb189  mov     r9d, 0B9h
0x1400bb18f  mov     dword ptr [rsp+78h+var_50], eax
0x1400bb193  mov     r8d, 1
0x1400bb199  mov     dl, 2
0x1400bb19b  mov     [rsp+78h+var_58], rbp
0x1400bb1a0  mov     rcx, [rcx+40h]
0x1400bb1a4  call    WPP_RECORDER_SF_D
0x1400bb1a9  xor     r9d, r9d
0x1400bb1ac  jmp     loc_1400BB4CE
0x1400bb1b1  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400bb1b8  jz      short loc_1400BB1EE
0x1400bb1ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb1c1  cmp     byte ptr [rcx+29h], 5
0x1400bb1c5  jnb     short loc_1400BB1CE
0x1400bb1c7  cmp     [rcx+48h], r9w
0x1400bb1cc  jz      short loc_1400BB1EE
0x1400bb1ce  mov     eax, [rsi+14h]
0x1400bb1d1  mov     r9d, 0BAh
0x1400bb1d7  mov     rcx, [rcx+40h]
0x1400bb1db  mov     dl, 5
0x1400bb1dd  mov     dword ptr [rsp+78h+var_50], eax
0x1400bb1e1  mov     [rsp+78h+var_58], rbp
0x1400bb1e6  call    WPP_RECORDER_SF_d
0x1400bb1eb  xor     r9d, r9d
0x1400bb1ee  mov     r14d, [rsi+10h]
0x1400bb1f2  mov     ebp, r9d
0x1400bb1f5  cmp     ebp, [rsi+14h]
0x1400bb1f8  jnb     loc_1400BB2C6
0x1400bb1fe  mov     edx, 30h ; '0'
0x1400bb203  mov     r8d, 47696457h
0x1400bb209  lea     ecx, [rdx+10h]
0x1400bb20c  call    cs:__imp_ExAllocatePool2
0x1400bb213  nop     dword ptr [rax+rax+00h]
0x1400bb218  xor     r9d, r9d
0x1400bb21b  mov     rbx, rax
0x1400bb21e  test    rax, rax
0x1400bb221  jz      loc_1400BB2C6
0x1400bb227  mov     rdx, rax; struct _CPP_LIST_ENTRY *
0x1400bb22a  mov     [rax+18h], r9
0x1400bb22e  mov     rcx, rax; void *
0x1400bb231  mov     [rax+20h], r9b
0x1400bb235  call    ?InitializeCppListEntry@@YAXPEAXPEAU_CPP_LIST_ENTRY@@@Z; InitializeCppListEntry(void *,_CPP_LIST_ENTRY *)
0x1400bb23a  mov     edx, r14d
0x1400bb23d  mov     ecx, [rdx+rsi]
0x1400bb240  mov     [rax+28h], ecx
0x1400bb243  movzx   ecx, word ptr [rdx+rsi+4]
0x1400bb248  mov     [rax+2Ch], cx
0x1400bb24c  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400bb253  jz      short loc_1400BB299
0x1400bb255  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb25c  cmp     byte ptr [rcx+29h], 5
0x1400bb260  jnb     short loc_1400BB269
0x1400bb262  cmp     [rcx+48h], r9w
0x1400bb267  jz      short loc_1400BB299
0x1400bb269  mov     rcx, [rcx+40h]
0x1400bb26d  add     rax, 28h ; '('
0x1400bb271  mov     [rsp+78h+var_48], rax
0x1400bb276  mov     r9d, 0BBh
0x1400bb27c  mov     eax, [rdi+5Ch]
0x1400bb27f  mov     dl, 5
0x1400bb281  mov     dword ptr [rsp+78h+var_50], eax
0x1400bb285  lea     rax, WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids
0x1400bb28c  mov     [rsp+78h+var_58], rax
0x1400bb291  call    WPP_RECORDER_SF_d_MAC_
0x1400bb296  xor     r9d, r9d
0x1400bb299  lea     rax, [rdi+38h]
0x1400bb29d  mov     rcx, [rax+8]
0x1400bb2a1  cmp     [rcx], rax
0x1400bb2a4  jnz     loc_1400BB460
0x1400bb2aa  mov     [rbx], rax
0x1400bb2ad  add     r14d, 6
0x1400bb2b1  mov     [rbx+8], rcx
0x1400bb2b5  mov     [rcx], rbx
0x1400bb2b8  mov     [rax+8], rbx
0x1400bb2bc  inc     dword ptr [rdi+5Ch]
0x1400bb2bf  inc     ebp
0x1400bb2c1  jmp     loc_1400BB1F5
0x1400bb2c6  mov     eax, [rsi+38h]
0x1400bb2c9  test    eax, eax
0x1400bb2cb  jz      loc_1400BB476
0x1400bb2d1  mov     ebp, [rsi+3Ch]
0x1400bb2d4  cmp     r12d, ebp
0x1400bb2d7  jbe     loc_1400BB476
0x1400bb2dd  sub     r12d, ebp
0x1400bb2e0  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400bb2e7  jz      short loc_1400BB321
0x1400bb2e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb2f0  cmp     byte ptr [rcx+29h], 5
0x1400bb2f4  jnb     short loc_1400BB2FD
0x1400bb2f6  cmp     [rcx+48h], r9w
0x1400bb2fb  jz      short loc_1400BB321
0x1400bb2fd  mov     rcx, [rcx+40h]
0x1400bb301  mov     r9d, 0BCh
0x1400bb307  mov     dword ptr [rsp+78h+var_50], eax
0x1400bb30b  mov     dl, 5
0x1400bb30d  lea     rax, WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids
0x1400bb314  mov     [rsp+78h+var_58], rax
0x1400bb319  call    WPP_RECORDER_SF_d
0x1400bb31e  xor     r9d, r9d
0x1400bb321  lea     r15, [rsi+rbp]
0x1400bb325  mov     eax, [rsi+38h]
0x1400bb328  cmp     [rdi+58h], eax
0x1400bb32b  jnb     loc_1400BB467
0x1400bb331  cmp     r12d, 2
0x1400bb335  jb      loc_1400BB467
0x1400bb33b  movzx   eax, byte ptr [r15]
0x1400bb33f  inc     eax
0x1400bb341  cmp     r12d, eax
0x1400bb344  jb      loc_1400BB467
0x1400bb34a  mov     edx, 130h
0x1400bb34f  mov     ecx, 40h ; '@'
0x1400bb354  mov     r8d, 47696457h
0x1400bb35a  call    cs:__imp_ExAllocatePool2
0x1400bb361  nop     dword ptr [rax+rax+00h]
0x1400bb366  xor     r9d, r9d
0x1400bb369  mov     r14, rax
0x1400bb36c  test    rax, rax
0x1400bb36f  jz      loc_1400BB467
0x1400bb375  movzx   r8d, byte ptr [r15]
0x1400bb379  mov     rdx, rax; struct _CPP_LIST_ENTRY *
0x1400bb37c  mov     rcx, rax; void *
0x1400bb37f  mov     [rax+18h], r9
0x1400bb383  mov     [rax+20h], r9b
0x1400bb387  call    ?InitializeCppListEntry@@YAXPEAXPEAU_CPP_LIST_ENTRY@@@Z; InitializeCppListEntry(void *,_CPP_LIST_ENTRY *)
0x1400bb38c  mov     edx, 0FFh
0x1400bb391  lea     rcx, [rax+29h]; void *
0x1400bb395  cmp     r8b, dl
0x1400bb398  cmovb   edx, r8d
0x1400bb39c  mov     r8d, 100h; Size
0x1400bb3a2  mov     [rax+28h], dl
0x1400bb3a5  xor     edx, edx; Val
0x1400bb3a7  call    memset
0x1400bb3ac  xor     eax, eax
0x1400bb3ae  mov     r13d, eax
0x1400bb3b1  cmp     [r14+28h], al
0x1400bb3b5  jbe     short loc_1400BB3E0
0x1400bb3b7  mov     ebx, r13d
0x1400bb3ba  movzx   ecx, byte ptr [rbx+r15+1]; C
0x1400bb3c0  call    cs:__imp_tolower
0x1400bb3c7  nop     dword ptr [rax+rax+00h]
0x1400bb3cc  mov     [rbx+r14+29h], al
0x1400bb3d1  inc     r13d
0x1400bb3d4  movzx   eax, byte ptr [r14+28h]
0x1400bb3d9  cmp     r13d, eax
0x1400bb3dc  jb      short loc_1400BB3B7
0x1400bb3de  xor     eax, eax
0x1400bb3e0  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400bb3e7  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400bb3ee  jz      short loc_1400BB424
0x1400bb3f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb3f7  cmp     byte ptr [rcx+29h], 5
0x1400bb3fb  jnb     short loc_1400BB403
0x1400bb3fd  cmp     [rcx+48h], ax
0x1400bb401  jz      short loc_1400BB424
0x1400bb403  movzx   edx, byte ptr [r15]
0x1400bb407  lea     rax, [r14+29h]
0x1400bb40b  mov     rcx, [rcx+40h]
0x1400bb40f  mov     [rsp+78h+var_40], rax
0x1400bb414  mov     eax, [rdi+58h]
0x1400bb417  mov     dword ptr [rsp+78h+var_48], edx
0x1400bb41b  mov     dword ptr [rsp+78h+var_50], eax
0x1400bb41f  call    WPP_RECORDER_SF_dds
0x1400bb424  lea     rax, [rdi+48h]
0x1400bb428  mov     rcx, [rax+8]
0x1400bb42c  cmp     [rcx], rax
0x1400bb42f  jnz     short loc_1400BB460
0x1400bb431  mov     [r14], rax
0x1400bb434  inc     ebp
0x1400bb436  mov     [r14+8], rcx
0x1400bb43a  mov     [rcx], r14
0x1400bb43d  mov     [rax+8], r14
0x1400bb441  or      eax, 0FFFFFFFFh
0x1400bb444  inc     dword ptr [rdi+58h]
0x1400bb447  movzx   ecx, byte ptr [r15]
0x1400bb44b  add     ebp, ecx
0x1400bb44d  sub     eax, ecx
0x1400bb44f  mov     r15d, ebp
0x1400bb452  add     r12d, eax
0x1400bb455  add     r15, rsi
0x1400bb458  xor     r9d, r9d
0x1400bb45b  jmp     loc_1400BB325
0x1400bb460  mov     ecx, 3
0x1400bb465  int     29h; Win8: RtlFailFast(ecx)
0x1400bb467  mov     r13b, [rsp+78h+arg_8]
0x1400bb46f  lea     r15, WPP_RECORDER_INITIALIZED
0x1400bb476  mov     [rdi+35h], r13b
0x1400bb47a  test    r13b, r13b
0x1400bb47d  jnz     short loc_1400BB48E
0x1400bb47f  cmp     [rdi+5Ch], r9d
0x1400bb483  jnz     short loc_1400BB48E
0x1400bb485  mov     al, r9b
0x1400bb488  cmp     [rdi+58h], r9d
0x1400bb48c  jz      short loc_1400BB490
0x1400bb48e  mov     al, 1
0x1400bb490  mov     ebx, [rsp+78h+arg_0]
0x1400bb497  lea     rbp, WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids
0x1400bb49e  mov     [rdi+34h], al
0x1400bb4a1  mov     rcx, [rdi+8]
0x1400bb4a5  cmp     dword ptr [rcx+718h], 4
0x1400bb4ac  mov     [rcx+734h], al
0x1400bb4b2  jnz     short loc_1400BB4CE
0x1400bb4b4  neg     al
0x1400bb4b6  mov     edx, 0C4B20100h
0x1400bb4bb  sbb     rax, rax
0x1400bb4be  and     rax, rdx
0x1400bb4c1  add     rax, 11E1A300h
0x1400bb4c7  mov     [rcx+748h], rax
0x1400bb4ce  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400bb4d5  jz      short loc_1400BB50B
0x1400bb4d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb4de  cmp     byte ptr [rcx+29h], 5
0x1400bb4e2  jnb     short loc_1400BB4EB
0x1400bb4e4  cmp     [rcx+48h], r9w
0x1400bb4e9  jz      short loc_1400BB50B
0x1400bb4eb  mov     rcx, [rcx+40h]
0x1400bb4ef  mov     r9d, 0BEh
0x1400bb4f5  mov     dword ptr [rsp+78h+var_50], ebx
0x1400bb4f9  mov     r8d, 1
0x1400bb4ff  mov     dl, 5
0x1400bb501  mov     [rsp+78h+var_58], rbp
0x1400bb506  call    WPP_RECORDER_SF_D
0x1400bb50b  mov     eax, ebx
0x1400bb50d  mov     rbx, [rsp+78h+arg_10]
0x1400bb515  add     rsp, 40h
0x1400bb519  pop     r15
0x1400bb51b  pop     r14
0x1400bb51d  pop     r13
0x1400bb51f  pop     r12
0x1400bb521  pop     rdi
0x1400bb522  pop     rsi
0x1400bb523  pop     rbp
0x1400bb524  retn
```
