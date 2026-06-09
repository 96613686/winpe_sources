# CCtlPlane::OnWdiOidRequestCompleteFromMiniport(_NDIS_OID_REQUEST *,int)

- ea: `0x1400020a8`
- end: `0x1400024b2`
- name: `?OnWdiOidRequestCompleteFromMiniport@CCtlPlane@@AEAAXPEAU_NDIS_OID_REQUEST@@H@Z`
- size: `1034`
- prototype: `void __fastcall(CCtlPlane *__hidden this, struct _NDIS_OID_REQUEST *, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140001efc`
- `0x140001f30`

## callees

- `0x1400010f8`
- `0x140001248`
- `0x1400020a8`
- `0x140002b6c`
- `0x140023ae0`
- `0x140034e04`
- `0x140034ec4`
- `0x14004a134`
- `0x14007e5dc`
- `0x140082ff8`
- `0x1400da680`
- `0x1400dac80`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140002258`
- `ntoskrnl!ExAllocatePool2` at `0x140002258`

## pseudocode

```c
void __fastcall CCtlPlane::OnWdiOidRequestCompleteFromMiniport(
        CCtlPlane *this,
        struct _NDIS_OID_REQUEST *a2,
        int a3,
        int a4)
{
  int v4; // esi
  struct _NDIS_OID_REQUEST *v5; // rdi
  unsigned int Oid; // edx
  const struct _WDI_MESSAGE_HEADER *InformationBuffer; // r12
  unsigned int v9; // r13d
  unsigned int BytesWritten; // r15d
  __int64 v11; // r8
  unsigned int v12; // eax
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  __int64 Pool2; // rax
  int v17; // edx
  _WFC_MESSAGE_METADATA *v18; // r14
  int v19; // ebx
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  int v23; // edx
  void *m_pCompletionContext; // rsi
  void (__fastcall *m_HungSendCmdCompletionRoutine)(void *, unsigned int, _WFC_MESSAGE_METADATA *, IWdiMessageMemoryManager *); // rax
  void (__fastcall *m_SendCmdCompletionRoutine)(void *, unsigned int, _WFC_MESSAGE_METADATA *, IWdiMessageMemoryManager *); // rax
  int v27; // [rsp+20h] [rbp-58h]
  __int64 v28; // [rsp+28h] [rbp-50h]
  void *v29; // [rsp+58h] [rbp-20h]
  const char *v30; // [rsp+60h] [rbp-18h] BYREF
  unsigned int TransactionId; // [rsp+C0h] [rbp+48h] BYREF
  unsigned int v32; // [rsp+C8h] [rbp+50h] BYREF
  unsigned __int16 PortId; // [rsp+D0h] [rbp+58h] BYREF
  const char *v34; // [rsp+D8h] [rbp+60h] BYREF

  v4 = a3;
  v5 = a2;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      30,
      (__int64)WPP_f45970a6f4eb33a4b42e51fcb0cc11db_Traceguids);
  }
  Oid = v5->DATA.Oid;
  InformationBuffer = (const struct _WDI_MESSAGE_HEADER *)v5->DATA.QUERY_INFORMATION.InformationBuffer;
  v9 = (unsigned __int16)Oid;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_LDddD(
      WPP_GLOBAL_Control->DeviceExtension,
      Oid,
      a3,
      a4,
      v27,
      Oid,
      Oid,
      InformationBuffer->PortId,
      InformationBuffer->TransactionId,
      v4);
  this->m_bRequestPending = 0;
  if ( v5 == &this->m_OidAlternative
    || (v29 = 0, v5 == &this->m_OidRequest)
    && v5->DATA.QUERY_INFORMATION.InformationBuffer != this->m_pDefaultInformationBuffer )
  {
    v29 = v5->DATA.QUERY_INFORMATION.InformationBuffer;
    this->m_bRequestUsingAllocatedMemory = 0;
  }
  if ( v4 )
  {
    InformationBuffer->Status = v4;
    BytesWritten = 16;
  }
  else
  {
    BytesWritten = v5->DATA.METHOD_INFORMATION.BytesWritten;
  }
  CMessageHelper::LogMessage(3u, v9, this->m_pAdapter->m_TlvContext.PeerVersion, BytesWritten, InformationBuffer);
  v12 = BytesWritten + 32;
  if ( BytesWritten + 32 < BytesWritten )
  {
    v4 = -1073676267;
    if ( (unsigned int)dword_1400F8790 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400F8790, 5, v11) )
    {
      TransactionId = InformationBuffer->TransactionId;
      PortId = InformationBuffer->PortId;
      v32 = BytesWritten;
      v34 = WDI_TLV::stringify::ToLogString(v9);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v13,
        (unsigned int)word_1400EF032,
        v14,
        v15,
        (__int64)&v34,
        (__int64)&v32,
        (__int64)&PortId,
        (__int64)&TransactionId);
    }
    BytesWritten = 16;
    InformationBuffer->Status = -1073676267;
    v12 = 48;
  }
  Pool2 = ExAllocatePool2(64, v12, 1198089303);
  v18 = (_WFC_MESSAGE_METADATA *)Pool2;
  if ( Pool2 )
  {
    *(_DWORD *)(Pool2 + 8) &= 0xFFFFFFF8;
    *(_DWORD *)(Pool2 + 12) = 3;
    *(_QWORD *)(Pool2 + 24) = 0;
    *(_QWORD *)Pool2 = *(_QWORD *)&this->m_PendingWdiCommandMetadata.MessageId;
    *(_DWORD *)(Pool2 + 8) = *((_DWORD *)&this->m_PendingWdiCommandMetadata + 2);
    *(_DWORD *)(Pool2 + 16) = v5->DATA.Oid;
    *(_DWORD *)Pool2 = v9;
    *(_DWORD *)(Pool2 + 4) = BytesWritten;
    if ( v4 == -2147483643 || v4 == -1073676266 || v4 == -1073676268 )
    {
      v4 = -2147483643;
      *(_DWORD *)(Pool2 + 24) = v5->DATA.METHOD_INFORMATION.BytesNeeded;
    }
    else if ( v4 && (unsigned int)dword_1400F8790 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400F8790, 5, 0) )
    {
      TransactionId = InformationBuffer->TransactionId;
      PortId = InformationBuffer->PortId;
      LODWORD(v34) = InformationBuffer->Status;
      v32 = v4;
      v30 = WDI_TLV::stringify::ToLogString(v9);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v20,
        (unsigned int)byte_1400EEFB1,
        v21,
        v22,
        (__int64)&v30,
        (__int64)&v34,
        (__int64)&v32,
        (__int64)&PortId,
        (__int64)&TransactionId);
    }
    v18->_Command.MinimumOutputLength = v4;
    memmove(&v18->Message, v5->DATA.QUERY_INFORMATION.InformationBuffer, BytesWritten);
    m_pCompletionContext = this->m_pCompletionContext;
    if ( v5 == this->m_pHungOidRequest )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v28) = v9;
        LOBYTE(v23) = 4;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v23,
          1,
          33,
          (__int64)WPP_f45970a6f4eb33a4b42e51fcb0cc11db_Traceguids,
          v28);
      }
      m_HungSendCmdCompletionRoutine = this->m_HungSendCmdCompletionRoutine;
      this->m_HungSendCmdCompletionRoutine = 0;
      m_HungSendCmdCompletionRoutine(m_pCompletionContext, BytesWritten + 32, v18, this);
    }
    else
    {
      m_SendCmdCompletionRoutine = this->m_SendCmdCompletionRoutine;
      this->m_SendCmdCompletionRoutine = 0;
      m_SendCmdCompletionRoutine(m_pCompletionContext, BytesWritten + 32, v18, this);
    }
    v19 = 0;
  }
  else
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v17) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v17,
        1,
        32,
        (__int64)WPP_f45970a6f4eb33a4b42e51fcb0cc11db_Traceguids);
    }
    v19 = -1073741670;
  }
  if ( v29 )
    operator delete(v29);
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v28) = v19;
    LOBYTE(v17) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v17,
      1,
      34,
      (__int64)WPP_f45970a6f4eb33a4b42e51fcb0cc11db_Traceguids,
      v28);
  }
}

```

## disassembly

```asm
0x1400020a8  push    rbp
0x1400020aa  push    rbx
0x1400020ab  push    rsi
0x1400020ac  push    rdi
0x1400020ad  push    r12
0x1400020af  push    r13
0x1400020b1  push    r14
0x1400020b3  push    r15
0x1400020b5  mov     rbp, rsp
0x1400020b8  sub     rsp, 78h
0x1400020bc  mov     esi, r8d
0x1400020bf  mov     rdi, rdx
0x1400020c2  mov     rbx, rcx
0x1400020c5  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400020cc  xor     r14d, r14d
0x1400020cf  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400020d6  lea     rax, WPP_f45970a6f4eb33a4b42e51fcb0cc11db_Traceguids
0x1400020dd  jz      short loc_14000210D
0x1400020df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400020e6  cmp     byte ptr [rcx+29h], 5
0x1400020ea  jnb     short loc_1400020F3
0x1400020ec  cmp     [rcx+48h], r14w
0x1400020f1  jz      short loc_14000210D
0x1400020f3  mov     rcx, [rcx+40h]
0x1400020f7  mov     r9d, 1Eh
0x1400020fd  mov     dl, 5
0x1400020ff  mov     [rsp+78h+var_58], rax
0x140002104  lea     r8d, [r9-1Dh]
0x140002108  call    WPP_RECORDER_SF_
0x14000210d  mov     edx, [rdi+20h]
0x140002110  mov     r12, [rdi+28h]
0x140002114  movzx   r13d, dx
0x140002118  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14000211f  jz      short loc_140002150
0x140002121  movzx   ecx, word ptr [r12]
0x140002126  mov     eax, [r12+8]
0x14000212b  mov     [rsp+78h+var_30], esi
0x14000212f  mov     dword ptr [rsp+78h+var_38], eax
0x140002133  mov     dword ptr [rsp+78h+var_40], ecx
0x140002137  mov     rcx, cs:WPP_GLOBAL_Control
0x14000213e  mov     dword ptr [rsp+78h+var_48], edx
0x140002142  mov     dword ptr [rsp+78h+var_50], r13d
0x140002147  mov     rcx, [rcx+40h]
0x14000214b  call    WPP_RECORDER_SF_LDddD
0x140002150  lea     rax, [rbx+130h]
0x140002157  mov     [rbx+20h], r14b
0x14000215b  cmp     rdi, rax
0x14000215e  jz      short loc_14000217A
0x140002160  lea     rax, [rbx+38h]
0x140002164  mov     [rbp+var_20], r14
0x140002168  cmp     rdi, rax
0x14000216b  jnz     short loc_140002186
0x14000216d  mov     rax, [rbx+238h]
0x140002174  cmp     [rdi+28h], rax
0x140002178  jz      short loc_140002186
0x14000217a  mov     rax, [rdi+28h]
0x14000217e  mov     [rbp+var_20], rax
0x140002182  mov     [rbx+30h], r14b
0x140002186  test    esi, esi
0x140002188  jnz     short loc_140002190
0x14000218a  mov     r15d, [rdi+3Ch]
0x14000218e  jmp     short loc_14000219B
0x140002190  mov     [r12+4], esi
0x140002195  mov     r15d, 10h
0x14000219b  mov     r8, [rbx+8]
0x14000219f  mov     r9d, r15d; unsigned int
0x1400021a2  mov     edx, r13d; unsigned int
0x1400021a5  mov     [rsp+78h+var_58], r12; struct _WDI_MESSAGE_HEADER *
0x1400021aa  mov     cl, 3; unsigned __int8
0x1400021ac  mov     r8d, [r8+4000h]; unsigned int
0x1400021b3  call    ?LogMessage@CMessageHelper@@SAXEKKKPEBU_WDI_MESSAGE_HEADER@@@Z; CMessageHelper::LogMessage(uchar,ulong,ulong,ulong,_WDI_MESSAGE_HEADER const *)
0x1400021b8  lea     eax, [r15+20h]
0x1400021bc  cmp     eax, r15d
0x1400021bf  jnb     loc_14000224B
0x1400021c5  mov     eax, cs:dword_1400F8790
0x1400021cb  mov     esi, 0C0010015h
0x1400021d0  cmp     eax, 2
0x1400021d3  jbe     short loc_14000223C
0x1400021d5  mov     edx, 5
0x1400021da  lea     rcx, dword_1400F8790
0x1400021e1  call    _tlgKeywordOn
0x1400021e6  test    al, al
0x1400021e8  jz      short loc_14000223C
0x1400021ea  mov     eax, [r12+8]
0x1400021ef  movzx   ecx, r13w
0x1400021f3  mov     [rbp+arg_0], eax
0x1400021f6  movzx   eax, word ptr [r12]
0x1400021fb  mov     [rbp+arg_10], ax
0x1400021ff  mov     [rbp+arg_8], r15d
0x140002203  call    ?ToLogString@stringify@WDI_TLV@@YAPEBDW4MESSAGE_ID@ENUMS@2@@Z; WDI_TLV::stringify::ToLogString(WDI_TLV::ENUMS::MESSAGE_ID)
0x140002208  mov     [rbp+arg_18], rax
0x14000220c  lea     rdx, word_1400EF032
0x140002213  lea     rax, [rbp+arg_0]
0x140002217  mov     [rsp+78h+var_40], rax
0x14000221c  lea     rax, [rbp+arg_10]
0x140002220  mov     [rsp+78h+var_48], rax
0x140002225  lea     rax, [rbp+arg_8]
0x140002229  mov     [rsp+78h+var_50], rax
0x14000222e  lea     rax, [rbp+arg_18]
0x140002232  mov     [rsp+78h+var_58], rax
0x140002237  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x14000223c  mov     r15d, 10h
0x140002242  mov     [r12+4], esi
0x140002247  lea     eax, [r15+20h]
0x14000224b  mov     edx, eax
0x14000224d  mov     ecx, 40h ; '@'
0x140002252  mov     r8d, 47696457h
0x140002258  call    cs:__imp_ExAllocatePool2
0x14000225f  nop     dword ptr [rax+rax+00h]
0x140002264  xor     r8d, r8d
0x140002267  mov     r14, rax
0x14000226a  test    rax, rax
0x14000226d  jnz     short loc_1400022B1
0x14000226f  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140002276  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000227d  lea     r13, WPP_f45970a6f4eb33a4b42e51fcb0cc11db_Traceguids
0x140002284  jz      short loc_1400022A5
0x140002286  mov     rcx, cs:WPP_GLOBAL_Control
0x14000228d  lea     r9d, [rax+20h]
0x140002291  lea     r8d, [rax+1]
0x140002295  mov     [rsp+78h+var_58], r13
0x14000229a  mov     dl, 2
0x14000229c  mov     rcx, [rcx+40h]
0x1400022a0  call    WPP_RECORDER_SF_
0x1400022a5  mov     ebx, 0C000009Ah
0x1400022aa  xor     edi, edi
0x1400022ac  jmp     loc_140002455
0x1400022b1  and     dword ptr [rax+8], 0FFFFFFF8h
0x1400022b5  mov     dword ptr [rax+0Ch], 3
0x1400022bc  mov     [rax+18h], r8
0x1400022c0  movsd   xmm0, qword ptr [rbx+250h]
0x1400022c8  movsd   qword ptr [rax], xmm0
0x1400022cc  mov     eax, [rbx+258h]
0x1400022d2  mov     [r14+8], eax
0x1400022d6  mov     eax, [rdi+20h]
0x1400022d9  mov     [r14+10h], eax
0x1400022dd  mov     eax, 80000005h
0x1400022e2  mov     [rbp+var_28], r8d
0x1400022e6  mov     [r14], r13d
0x1400022e9  mov     [r14+4], r15d
0x1400022ed  cmp     esi, eax
0x1400022ef  jz      loc_14000239D
0x1400022f5  cmp     esi, 0C0010016h
0x1400022fb  jz      loc_14000239D
0x140002301  cmp     esi, 0C0010014h
0x140002307  jz      loc_14000239D
0x14000230d  test    esi, esi
0x14000230f  jz      loc_1400023A6
0x140002315  mov     eax, cs:dword_1400F8790
0x14000231b  cmp     eax, 2
0x14000231e  jbe     loc_1400023A6
0x140002324  mov     edx, 5
0x140002329  lea     rcx, dword_1400F8790
0x140002330  call    _tlgKeywordOn
0x140002335  test    al, al
0x140002337  jz      short loc_1400023A6
0x140002339  mov     eax, [r12+8]
0x14000233e  movzx   ecx, r13w
0x140002342  mov     [rbp+arg_0], eax
0x140002345  movzx   eax, word ptr [r12]
0x14000234a  mov     [rbp+arg_10], ax
0x14000234e  mov     eax, [r12+4]
0x140002353  mov     dword ptr [rbp+arg_18], eax
0x140002356  mov     [rbp+arg_8], esi
0x140002359  call    ?ToLogString@stringify@WDI_TLV@@YAPEBDW4MESSAGE_ID@ENUMS@2@@Z; WDI_TLV::stringify::ToLogString(WDI_TLV::ENUMS::MESSAGE_ID)
0x14000235e  mov     [rbp+var_18], rax
0x140002362  lea     rdx, byte_1400EEFB1
0x140002369  lea     rax, [rbp+arg_0]
0x14000236d  mov     [rsp+78h+var_38], rax
0x140002372  lea     rax, [rbp+arg_10]
0x140002376  mov     [rsp+78h+var_40], rax
0x14000237b  lea     rax, [rbp+arg_8]
0x14000237f  mov     [rsp+78h+var_48], rax
0x140002384  lea     rax, [rbp+arg_18]
0x140002388  mov     [rsp+78h+var_50], rax
0x14000238d  lea     rax, [rbp+var_18]
0x140002391  mov     [rsp+78h+var_58], rax
0x140002396  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x14000239b  jmp     short loc_1400023A6
0x14000239d  mov     esi, eax
0x14000239f  mov     eax, [rdi+44h]
0x1400023a2  mov     [r14+18h], eax
0x1400023a6  mov     [r14+14h], esi
0x1400023aa  lea     rcx, [r14+20h]; void *
0x1400023ae  mov     rdx, [rdi+28h]; Src
0x1400023b2  mov     r8d, r15d; Size
0x1400023b5  call    memmove
0x1400023ba  mov     rsi, [rbx+228h]
0x1400023c1  cmp     rdi, [rbx+280h]
0x1400023c8  jnz     short loc_140002422
0x1400023ca  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400023d1  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400023d8  jz      short loc_140002409
0x1400023da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400023e1  mov     r9d, 21h ; '!'
0x1400023e7  mov     dword ptr [rsp+78h+var_50], r13d
0x1400023ec  mov     dl, 4
0x1400023ee  lea     r13, WPP_f45970a6f4eb33a4b42e51fcb0cc11db_Traceguids
0x1400023f5  mov     [rsp+78h+var_58], r13
0x1400023fa  mov     rcx, [rcx+40h]
0x1400023fe  lea     r8d, [r9-20h]
0x140002402  call    WPP_RECORDER_SF_D
0x140002407  jmp     short loc_140002410
0x140002409  lea     r13, WPP_f45970a6f4eb33a4b42e51fcb0cc11db_Traceguids
0x140002410  mov     rax, [rbx+288h]
0x140002417  xor     edi, edi
0x140002419  mov     [rbx+288h], rdi
0x140002420  jmp     short loc_140002440
0x140002422  mov     rax, [rbx+230h]
0x140002429  lea     r12, WPP_RECORDER_INITIALIZED
0x140002430  xor     edi, edi
0x140002432  lea     r13, WPP_f45970a6f4eb33a4b42e51fcb0cc11db_Traceguids
0x140002439  mov     [rbx+230h], rdi
0x140002440  mov     r9, rbx
0x140002443  lea     edx, [r15+20h]
0x140002447  mov     r8, r14
0x14000244a  mov     rcx, rsi
0x14000244d  call    _guard_dispatch_icall
0x140002452  mov     ebx, [rbp+var_28]
0x140002455  mov     rax, [rbp+var_20]
0x140002459  test    rax, rax
0x14000245c  jz      short loc_140002466
0x14000245e  mov     rcx, rax; void *
0x140002461  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002466  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000246d  jz      short loc_1400024A0
0x14000246f  mov     rcx, cs:WPP_GLOBAL_Control
0x140002476  cmp     byte ptr [rcx+29h], 5
0x14000247a  jnb     short loc_140002482
0x14000247c  cmp     [rcx+48h], di
0x140002480  jz      short loc_1400024A0
0x140002482  mov     rcx, [rcx+40h]
0x140002486  mov     r9d, 22h ; '"'
0x14000248c  mov     dword ptr [rsp+78h+var_50], ebx
0x140002490  mov     dl, 5
0x140002492  mov     [rsp+78h+var_58], r13
0x140002497  lea     r8d, [r9-21h]
0x14000249b  call    WPP_RECORDER_SF_D
0x1400024a0  add     rsp, 78h
0x1400024a4  pop     r15
0x1400024a6  pop     r14
0x1400024a8  pop     r13
0x1400024aa  pop     r12
0x1400024ac  pop     rdi
0x1400024ad  pop     rsi
0x1400024ae  pop     rbx
0x1400024af  pop     rbp
0x1400024b0  retn
```
