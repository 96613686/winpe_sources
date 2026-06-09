# CCtlPlane::SendWdiCommand(_WFC_MESSAGE_METADATA *,void (*)(void *,ulong,_WFC_MESSAGE_METADATA *,IWdiMessageMemoryManager *),void *)

- ea: `0x140002f98`
- end: `0x140003460`
- name: `?SendWdiCommand@CCtlPlane@@AEAAHPEAU_WFC_MESSAGE_METADATA@@P6AXPEAXK0PEAVIWdiMessageMemoryManager@@@Z1@Z`
- size: `1224`
- prototype: `__int64 __fastcall(CCtlPlane *__hidden this, struct _WFC_MESSAGE_METADATA *, void (*)(void *, unsigned int, struct _WFC_MESSAGE_METADATA *, struct IWdiMessageMemoryManager *), void *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140004340`

## callees

- `0x140001c64`
- `0x140001dd4`
- `0x140001efc`
- `0x1400024b8`
- `0x140002b6c`
- `0x140002f98`
- `0x140034e04`
- `0x140034ec4`
- `0x14009f720`
- `0x14009f814`
- `0x1400da680`
- `0x1400da740`
- `0x1400dac80`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400032ac`
- `ntoskrnl!ExAllocatePool2` at `0x1400032ac`

## pseudocode

```c
__int64 __fastcall CCtlPlane::SendWdiCommand(
        CCtlPlane *this,
        struct _WFC_MESSAGE_METADATA *a2,
        void (*a3)(void *, unsigned int, struct _WFC_MESSAGE_METADATA *, struct IWdiMessageMemoryManager *),
        void *a4)
{
  struct _WFC_MESSAGE_METADATA *v5; // rdi
  CAdapter *m_pAdapter; // rcx
  unsigned int m_lShutdown; // edx
  unsigned int MinimumOutputLength; // ebp
  __int64 v10; // rsi
  unsigned __int8 *m_pDefaultInformationBuffer; // r14
  _NDIS_OID_REQUEST *v12; // rsi
  unsigned int MessageId; // edx
  unsigned int MessageLength; // r9d
  int v15; // edx
  int v16; // r8d
  int v17; // r9d
  CMiniportDriver *m_MiniportDriver; // rcx
  __int16 v19; // ax
  char v20; // cl
  CAdapter *v21; // rax
  bool v22; // dl
  void *m_MiniportAdapterHandle; // rcx
  int v24; // eax
  int v25; // ebp
  unsigned int v26; // ebx
  int m_lResetRecovery; // r8d
  int v29; // [rsp+20h] [rbp-68h]
  int v30; // [rsp+20h] [rbp-68h]
  __int64 v31; // [rsp+28h] [rbp-60h]

  v5 = a2;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      16,
      (__int64)WPP_f45970a6f4eb33a4b42e51fcb0cc11db_Traceguids);
  }
  m_pAdapter = this->m_pAdapter;
  this->m_bRequestUsingAllocatedMemory = 0;
  m_lShutdown = m_pAdapter->m_lShutdown;
  if ( m_lShutdown )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_Ldd(
        WPP_GLOBAL_Control->DeviceExtension,
        m_lShutdown,
        (_DWORD)a3,
        (unsigned int)&WPP_RECORDER_INITIALIZED,
        v29,
        v5->MessageId,
        v5->MessageId,
        m_pAdapter->m_lShutdown);
    v26 = -1073741823;
    goto LABEL_30;
  }
  m_lShutdown = v5->MessageId;
  if ( v5->MessageId != 4 && v5->MessageId != 6 )
  {
    if ( v5->MessageId == 10 )
      goto LABEL_56;
    if ( v5->MessageId != 12 )
    {
      if ( v5->MessageId == 17 )
        goto LABEL_56;
      if ( v5->MessageId != 32 && v5->MessageId != 47 )
      {
        if ( v5->MessageId != 127 && v5->MessageId != 135 )
          goto LABEL_14;
LABEL_56:
        *((_DWORD *)v5 + 2) |= 1u;
        goto LABEL_14;
      }
    }
  }
  m_lResetRecovery = m_pAdapter->m_lResetRecovery;
  if ( m_lResetRecovery || m_pAdapter->m_lSurpriseRemove )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_Lddd(
        WPP_GLOBAL_Control->DeviceExtension,
        m_lShutdown,
        m_lResetRecovery,
        (unsigned int)&WPP_RECORDER_INITIALIZED,
        v29,
        m_lShutdown,
        m_lShutdown,
        m_lResetRecovery,
        m_pAdapter->m_lSurpriseRemove);
    v26 = -1073676280;
    goto LABEL_30;
  }
LABEL_14:
  MinimumOutputLength = v5->_Command.MinimumOutputLength;
  v10 = this->m_pAdapter->m_lResetRecovery != 0 ? 304LL : 56LL;
  if ( MinimumOutputLength <= v5->MessageLength )
    MinimumOutputLength = v5->MessageLength;
  if ( MinimumOutputLength < 0x7FE )
  {
    MinimumOutputLength = 2046;
    goto LABEL_18;
  }
  if ( MinimumOutputLength <= 0x7FE )
  {
LABEL_18:
    if ( !this->m_pAdapter->m_lResetRecovery )
    {
      m_pDefaultInformationBuffer = this->m_pDefaultInformationBuffer;
      goto LABEL_20;
    }
  }
  this->m_bRequestUsingAllocatedMemory = 1;
  m_pDefaultInformationBuffer = (unsigned __int8 *)ExAllocatePool2(64, MinimumOutputLength, 1198089303);
  if ( m_pDefaultInformationBuffer )
  {
LABEL_20:
    v12 = (_NDIS_OID_REQUEST *)((char *)this + v10);
    if ( this->m_pAdapter->m_lResetRecovery && this->m_bRequestPending )
    {
      this->m_pHungOidRequest = this->m_pPendingOidRequest;
      this->m_HungSendCmdCompletionRoutine = this->m_SendCmdCompletionRoutine;
    }
    this->m_pCompletionContext = a4;
    this->m_SendCmdCompletionRoutine = DeviceCommandScheduler::s_CtlPlaneWdiOidCompleteCallback;
    MessageId = v5->MessageId;
    MessageLength = v5->MessageLength;
    v5->_Command.MappedWdiOid = v5->MessageId | 0xE4400000;
    CMessageHelper::LogMessage(1u, MessageId, this->m_pAdapter->m_TlvContext.PeerVersion, MessageLength, &v5->Message);
    memmove(m_pDefaultInformationBuffer, &v5->Message, v5->MessageLength);
    memset(v12, 0, sizeof(_NDIS_OID_REQUEST));
    m_MiniportDriver = this->m_pAdapter->m_MiniportDriver;
    if ( m_MiniportDriver->m_MiniportDriverCharacteristics.MajorNdisVersion > 6u
      || m_MiniportDriver->m_MiniportDriverCharacteristics.MajorNdisVersion == 6
      && m_MiniportDriver->m_MiniportDriverCharacteristics.MinorNdisVersion >= 0x32u )
    {
      v19 = 248;
      v20 = 2;
    }
    else
    {
      v19 = 236;
      v20 = 1;
    }
    v12->Header.Type = -106;
    v12->Header.Revision = v20;
    v12->Header.Size = v19;
    v12->RequestType = NdisRequestMethod;
    v12->DATA.Oid = v5->_Command.MappedWdiOid;
    v12->DATA.QUERY_INFORMATION.InformationBuffer = m_pDefaultInformationBuffer;
    v12->DATA.QUERY_INFORMATION.InformationBufferLength = v5->MessageLength;
    v12->DATA.QUERY_INFORMATION.BytesWritten = MinimumOutputLength;
    this->m_bRequestPending = 1;
    this->m_pPendingOidRequest = v12;
    *(_OWORD *)&this->m_PendingWdiCommandMetadata.MessageId = *(_OWORD *)&v5->MessageId;
    this->m_PendingWdiCommandMetadata.16 = v5->16;
    this->m_PendingWdiCommandMetadata.Message = v5->Message;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_LDddq(
        WPP_GLOBAL_Control->DeviceExtension,
        v15,
        v16,
        v17,
        v30,
        v5->MessageId,
        v5->_Command.MappedWdiOid,
        v5->Message.PortId,
        v5->Message.TransactionId,
        (char)this->m_pAdapter->m_MiniportAdapterHandle);
    v21 = this->m_pAdapter;
    v22 = *((_BYTE *)v5 + 8) & 1;
    if ( v21->m_ExpandStackSizeFlags.AsULong64 )
    {
      v24 = CCtlPlane::InvokeNdisCalloutWithBestEffortExpendStackSize(this, v22, v12);
    }
    else
    {
      m_MiniportAdapterHandle = v21->m_MiniportAdapterHandle;
      if ( v22 )
        v24 = g_pWdiDriver->m_NdisHook.m_NdisRawDispatch.InvokeDirectOidRequestHandler(m_MiniportAdapterHandle, v12);
      else
        v24 = g_pWdiDriver->m_NdisHook.m_NdisRawDispatch.InvokeOidRequestHandler(m_MiniportAdapterHandle, v12);
    }
    v25 = v24;
    if ( v24 != 259 )
    {
      if ( v24 && *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(m_lShutdown) = 2;
        WPP_RECORDER_SF_LDD(
          WPP_GLOBAL_Control->DeviceExtension,
          m_lShutdown,
          1,
          21,
          (__int64)WPP_f45970a6f4eb33a4b42e51fcb0cc11db_Traceguids,
          v5->MessageId,
          v5->_Command.MappedWdiOid,
          v24);
      }
      CCtlPlane::OnOidRequestCompleteFromMiniport(this, v12, v25);
    }
    v26 = 0;
    goto LABEL_30;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(m_lShutdown) = 2;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      m_lShutdown,
      1,
      19,
      (__int64)WPP_f45970a6f4eb33a4b42e51fcb0cc11db_Traceguids);
  }
  v26 = -1073741670;
LABEL_30:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v31) = v26;
    LOBYTE(m_lShutdown) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      m_lShutdown,
      1,
      22,
      (__int64)WPP_f45970a6f4eb33a4b42e51fcb0cc11db_Traceguids,
      v31);
  }
  return v26;
}

```

## disassembly

```asm
0x140002f98  push    rbx
0x140002f9a  push    rbp
0x140002f9b  push    rsi
0x140002f9c  push    rdi
0x140002f9d  push    r12
0x140002f9f  push    r14
0x140002fa1  push    r15
0x140002fa3  sub     rsp, 50h
0x140002fa7  mov     r15, r9
0x140002faa  mov     rdi, rdx
0x140002fad  mov     rbx, rcx
0x140002fb0  lea     r9, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140002fb7  xor     r12d, r12d
0x140002fba  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x140002fc1  lea     rsi, WPP_f45970a6f4eb33a4b42e51fcb0cc11db_Traceguids
0x140002fc8  jz      short loc_140002FE6
0x140002fca  mov     rcx, cs:WPP_GLOBAL_Control
0x140002fd1  cmp     byte ptr [rcx+29h], 5
0x140002fd5  jnb     loc_140003310
0x140002fdb  cmp     [rcx+48h], r12w
0x140002fe0  jnz     loc_140003310
0x140002fe6  mov     rcx, [rbx+8]
0x140002fea  mov     [rbx+30h], r12b
0x140002fee  mov     edx, [rcx+15D0h]
0x140002ff4  test    edx, edx
0x140002ff6  jnz     loc_14000337D
0x140002ffc  mov     edx, [rdi]
0x140002ffe  mov     eax, edx
0x140003000  sub     eax, 4
0x140003003  jz      loc_14000325E
0x140003009  sub     eax, 2
0x14000300c  jz      loc_14000325E
0x140003012  sub     eax, 4
0x140003015  jz      loc_1400033AE
0x14000301b  sub     eax, 2
0x14000301e  jz      loc_14000325E
0x140003024  sub     eax, 5
0x140003027  jz      loc_1400033AE
0x14000302d  sub     eax, 0Fh
0x140003030  jz      loc_14000325E
0x140003036  sub     eax, 0Fh
0x140003039  jz      loc_14000325E
0x14000303f  sub     eax, 50h ; 'P'
0x140003042  jz      loc_1400033AE
0x140003048  cmp     eax, 8
0x14000304b  jz      loc_1400033AE
0x140003051  mov     rax, [rbx+8]
0x140003055  mov     ebp, [rdi+14h]
0x140003058  mov     ecx, [rax+15C8h]
0x14000305e  mov     eax, ecx
0x140003060  neg     eax
0x140003062  mov     eax, [rdi+4]
0x140003065  sbb     rsi, rsi
0x140003068  and     esi, 0F8h
0x14000306e  add     rsi, 38h ; '8'
0x140003072  cmp     ebp, eax
0x140003074  cmovbe  ebp, eax
0x140003077  mov     eax, 7FEh
0x14000307c  cmp     ebp, eax
0x14000307e  jnb     loc_140003295
0x140003084  mov     ebp, eax
0x140003086  test    ecx, ecx
0x140003088  jnz     loc_14000329B
0x14000308e  mov     r14, [rbx+238h]
0x140003095  mov     rax, [rbx+8]
0x140003099  add     rsi, rbx
0x14000309c  cmp     [rax+15C8h], r12d
0x1400030a3  jnz     loc_1400033DD
0x1400030a9  mov     [rbx+228h], r15
0x1400030b0  lea     rax, ?s_CtlPlaneWdiOidCompleteCallback@DeviceCommandScheduler@@KAXPEAXKPEAU_WFC_MESSAGE_METADATA@@PEAVIWdiMessageMemoryManager@@@Z; DeviceCommandScheduler::s_CtlPlaneWdiOidCompleteCallback(void *,ulong,_WFC_MESSAGE_METADATA *,IWdiMessageMemoryManager *)
0x1400030b7  mov     [rbx+230h], rax
0x1400030be  lea     r15, [rdi+20h]
0x1400030c2  mov     edx, [rdi]; unsigned int
0x1400030c4  mov     cl, 1; unsigned __int8
0x1400030c6  mov     r9d, [rdi+4]; unsigned int
0x1400030ca  mov     eax, edx
0x1400030cc  or      eax, 0E4400000h
0x1400030d1  mov     [rsp+88h+var_68], r15; struct _WDI_MESSAGE_HEADER *
0x1400030d6  mov     [rdi+10h], eax
0x1400030d9  mov     r8, [rbx+8]
0x1400030dd  mov     r8d, [r8+4000h]; unsigned int
0x1400030e4  call    ?LogMessage@CMessageHelper@@SAXEKKKPEBU_WDI_MESSAGE_HEADER@@@Z; CMessageHelper::LogMessage(uchar,ulong,ulong,ulong,_WDI_MESSAGE_HEADER const *)
0x1400030e9  mov     r8d, [rdi+4]; Size
0x1400030ed  mov     rdx, r15; Src
0x1400030f0  mov     rcx, r14; void *
0x1400030f3  call    memmove
0x1400030f8  xor     edx, edx; Val
0x1400030fa  mov     r8d, 0F8h; Size
0x140003100  mov     rcx, rsi; void *
0x140003103  call    memset
0x140003108  mov     rax, [rbx+8]
0x14000310c  mov     rcx, [rax+68h]
0x140003110  cmp     byte ptr [rcx+34h], 6
0x140003114  jbe     loc_140003208
0x14000311a  mov     eax, 0F8h
0x14000311f  mov     cl, 2
0x140003121  mov     byte ptr [rsi], 96h
0x140003124  mov     [rsi+1], cl
0x140003127  mov     [rsi+2], ax
0x14000312b  mov     dword ptr [rsi+4], 0Ch
0x140003132  mov     eax, [rdi+10h]
0x140003135  mov     [rsi+20h], eax
0x140003138  mov     [rsi+28h], r14
0x14000313c  mov     eax, [rdi+4]
0x14000313f  mov     [rsi+30h], eax
0x140003142  mov     [rsi+34h], ebp
0x140003145  mov     byte ptr [rbx+20h], 1
0x140003149  mov     [rbx+28h], rsi
0x14000314d  movups  xmm0, xmmword ptr [rdi]
0x140003150  movups  xmmword ptr [rbx+250h], xmm0
0x140003157  movups  xmm1, xmmword ptr [rdi+10h]
0x14000315b  movups  xmmword ptr [rbx+260h], xmm1
0x140003162  movups  xmm0, xmmword ptr [rdi+20h]
0x140003166  movups  xmmword ptr [rbx+270h], xmm0
0x14000316d  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140003174  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000317b  jnz     loc_140003220
0x140003181  mov     rax, [rbx+8]
0x140003185  mov     dl, [rdi+8]
0x140003188  and     dl, 1; bool
0x14000318b  cmp     [rax+3FA0h], r12
0x140003192  jnz     loc_140003300
0x140003198  mov     rcx, [rax+58h]
0x14000319c  test    dl, dl
0x14000319e  mov     rax, cs:?g_pWdiDriver@@3PEAVCWdiDriver@@EA; CWdiDriver * g_pWdiDriver
0x1400031a5  mov     rdx, rsi
0x1400031a8  jnz     loc_140003405
0x1400031ae  mov     rax, [rax+0E0h]
0x1400031b5  call    _guard_dispatch_icall
0x1400031ba  mov     ebp, eax
0x1400031bc  cmp     eax, 103h
0x1400031c1  jnz     loc_1400032E9
0x1400031c7  mov     ebx, r12d
0x1400031ca  lea     rsi, WPP_f45970a6f4eb33a4b42e51fcb0cc11db_Traceguids
0x1400031d1  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400031d8  jz      short loc_1400031F6
0x1400031da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400031e1  cmp     byte ptr [rcx+29h], 5
0x1400031e5  jnb     loc_14000343D
0x1400031eb  cmp     [rcx+48h], r12w
0x1400031f0  jnz     loc_14000343D
0x1400031f6  mov     eax, ebx
0x1400031f8  add     rsp, 50h
0x1400031fc  pop     r15
0x1400031fe  pop     r14
0x140003200  pop     r12
0x140003202  pop     rdi
0x140003203  pop     rsi
0x140003204  pop     rbp
0x140003205  pop     rbx
0x140003206  retn
0x140003208  jnz     short loc_140003214
0x14000320a  cmp     byte ptr [rcx+35h], 32h ; '2'
0x14000320e  jnb     loc_14000311A
0x140003214  mov     eax, 0ECh
0x140003219  mov     cl, 1
0x14000321b  jmp     loc_140003121
0x140003220  movzx   ecx, word ptr [r15]
0x140003224  mov     rax, [rbx+8]
0x140003228  mov     rax, [rax+58h]
0x14000322c  mov     [rsp+88h+var_40], rax
0x140003231  mov     eax, [rdi+28h]
0x140003234  mov     [rsp+88h+var_48], eax
0x140003238  mov     eax, [rdi+10h]
0x14000323b  mov     [rsp+88h+var_50], ecx
0x14000323f  mov     rcx, cs:WPP_GLOBAL_Control
0x140003246  mov     [rsp+88h+var_58], eax
0x14000324a  mov     eax, [rdi]
0x14000324c  mov     dword ptr [rsp+88h+var_60], eax
0x140003250  mov     rcx, [rcx+40h]
0x140003254  call    WPP_RECORDER_SF_LDddq
0x140003259  jmp     loc_140003181
0x14000325e  mov     r8d, [rcx+15C8h]
0x140003265  test    r8d, r8d
0x140003268  jnz     short loc_140003277
0x14000326a  cmp     [rcx+15CCh], r12d
0x140003271  jz      loc_140003051
0x140003277  cmp     cs:WPP_RECORDER_INITIALIZED, r9; __annotation("TMF:",
0x14000327e  jnz     loc_140003411
0x140003284  mov     ebx, 0C0010008h
0x140003289  lea     r14, WPP_RECORDER_INITIALIZED
0x140003290  jmp     loc_1400031D1
0x140003295  jbe     loc_140003086
0x14000329b  mov     edx, ebp
0x14000329d  mov     ecx, 40h ; '@'
0x1400032a2  mov     r8d, 47696457h
0x1400032a8  mov     byte ptr [rbx+30h], 1
0x1400032ac  call    cs:__imp_ExAllocatePool2
0x1400032b3  nop     dword ptr [rax+rax+00h]
0x1400032b8  mov     r14, rax
0x1400032bb  test    rax, rax
0x1400032be  jnz     loc_140003095
0x1400032c4  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400032cb  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400032d2  lea     rsi, WPP_f45970a6f4eb33a4b42e51fcb0cc11db_Traceguids
0x1400032d9  jnz     loc_1400033B7
0x1400032df  mov     ebx, 0C000009Ah
0x1400032e4  jmp     loc_1400031D1
0x1400032e9  test    ebp, ebp
0x1400032eb  jnz     short loc_140003336
0x1400032ed  mov     r8d, ebp; int
0x1400032f0  mov     rdx, rsi; struct _NDIS_OID_REQUEST *
0x1400032f3  mov     rcx, rbx; this
0x1400032f6  call    ?OnOidRequestCompleteFromMiniport@CCtlPlane@@QEAAXPEAU_NDIS_OID_REQUEST@@H@Z; CCtlPlane::OnOidRequestCompleteFromMiniport(_NDIS_OID_REQUEST *,int)
0x1400032fb  jmp     loc_1400031C7
0x140003300  mov     r8, rsi; struct _NDIS_OID_REQUEST *
0x140003303  mov     rcx, rbx; this
0x140003306  call    ?InvokeNdisCalloutWithBestEffortExpendStackSize@CCtlPlane@@AEAAH_NPEAU_NDIS_OID_REQUEST@@@Z; CCtlPlane::InvokeNdisCalloutWithBestEffortExpendStackSize(bool,_NDIS_OID_REQUEST *)
0x14000330b  jmp     loc_1400031BA
0x140003310  mov     rcx, [rcx+40h]
0x140003314  mov     r9d, 10h
0x14000331a  mov     dl, 5
0x14000331c  mov     [rsp+88h+var_68], rsi
0x140003321  lea     r8d, [r9-0Fh]
0x140003325  call    WPP_RECORDER_SF_
0x14000332a  lea     r9, WPP_RECORDER_INITIALIZED
0x140003331  jmp     loc_140002FE6
0x140003336  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14000333d  jz      short loc_1400032ED
0x14000333f  mov     eax, [rdi+10h]
0x140003342  mov     r9d, 15h
0x140003348  mov     rcx, cs:WPP_GLOBAL_Control
0x14000334f  mov     dl, 2
0x140003351  mov     [rsp+88h+var_50], ebp
0x140003355  mov     [rsp+88h+var_58], eax
0x140003359  mov     eax, [rdi]
0x14000335b  lea     r8d, [r9-14h]
0x14000335f  mov     rcx, [rcx+40h]
0x140003363  mov     dword ptr [rsp+88h+var_60], eax
0x140003367  lea     rax, WPP_f45970a6f4eb33a4b42e51fcb0cc11db_Traceguids
0x14000336e  mov     [rsp+88h+var_68], rax
0x140003373  call    WPP_RECORDER_SF_LDD
0x140003378  jmp     loc_1400032ED
0x14000337d  cmp     cs:WPP_RECORDER_INITIALIZED, r9; __annotation("TMF:",
0x140003384  jz      short loc_1400033A4
0x140003386  mov     eax, [rdi]
0x140003388  mov     rcx, cs:WPP_GLOBAL_Control
0x14000338f  mov     [rsp+88h+var_50], edx
0x140003393  mov     [rsp+88h+var_58], eax
0x140003397  mov     dword ptr [rsp+88h+var_60], eax
0x14000339b  mov     rcx, [rcx+40h]
0x14000339f  call    WPP_RECORDER_SF_Ldd
0x1400033a4  mov     ebx, 0C0000001h
0x1400033a9  jmp     loc_140003289
0x1400033ae  or      dword ptr [rdi+8], 1
0x1400033b2  jmp     loc_140003051
0x1400033b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400033be  mov     r9d, 13h
0x1400033c4  mov     dl, 2
0x1400033c6  mov     [rsp+88h+var_68], rsi
0x1400033cb  mov     rcx, [rcx+40h]
0x1400033cf  lea     r8d, [r9-12h]
0x1400033d3  call    WPP_RECORDER_SF_
0x1400033d8  jmp     loc_1400032DF
0x1400033dd  cmp     [rbx+20h], r12b
0x1400033e1  jz      loc_1400030A9
0x1400033e7  mov     rax, [rbx+28h]
0x1400033eb  mov     [rbx+280h], rax
0x1400033f2  mov     rax, [rbx+230h]
0x1400033f9  mov     [rbx+288h], rax
0x140003400  jmp     loc_1400030A9
0x140003405  mov     rax, [rax+0F0h]
0x14000340c  jmp     loc_1400031B5
0x140003411  mov     eax, [rcx+15CCh]
0x140003417  mov     rcx, cs:WPP_GLOBAL_Control
0x14000341e  mov     [rsp+88h+var_48], eax
0x140003422  mov     [rsp+88h+var_50], r8d
0x140003427  mov     [rsp+88h+var_58], edx
0x14000342b  mov     rcx, [rcx+40h]
0x14000342f  mov     dword ptr [rsp+88h+var_60], edx
0x140003433  call    WPP_RECORDER_SF_Lddd
0x140003438  jmp     loc_140003284
0x14000343d  mov     rcx, [rcx+40h]
0x140003441  mov     r9d, 16h
0x140003447  mov     dword ptr [rsp+88h+var_60], ebx
0x14000344b  mov     dl, 5
0x14000344d  mov     [rsp+88h+var_68], rsi
0x140003452  lea     r8d, [r9-15h]
0x140003456  call    WPP_RECORDER_SF_D
0x14000345b  jmp     loc_1400031F6
```
