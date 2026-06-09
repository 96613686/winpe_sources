# CP2PSendActionFrameRequestJob::ConstructCompletionIndication(void)

- ea: `0x1400c91e8`
- end: `0x1400c95a3`
- name: `?ConstructCompletionIndication@CP2PSendActionFrameRequestJob@@IEAAHXZ`
- size: `955`
- prototype: `__int64 __fastcall(CP2PSendActionFrameRequestJob *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400cbc90`

## callees

- `0x140011114`
- `0x140011244`
- `0x1400122e0`
- `0x14001a808`
- `0x1400297a0`
- `0x14002aa28`
- `0x14008dbf8`
- `0x1400c91e8`
- `0x1400ce198`
- `0x1400da4f0`
- `0x1400dac80`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400c9478`
- `ntoskrnl!ExAllocatePool2` at `0x1400c9478`

## pseudocode

```c
__int64 __fastcall CP2PSendActionFrameRequestJob::ConstructCompletionIndication(
        CP2PSendActionFrameRequestJob *this,
        __int64 a2,
        int a3)
{
  enum _WDI_P2P_ACTION_FRAME_TYPE RequestFrameType; // edx
  int v5; // r8d
  unsigned int v6; // esi
  unsigned int StatusFromTaskOutput; // eax
  unsigned int v8; // edi
  int v9; // r9d
  unsigned int v10; // eax
  unsigned __int16 GOConfigTimeout; // r9
  unsigned __int16 ClientConfigTimeout; // ax
  size_t v13; // rsi
  unsigned int v14; // eax
  unsigned int v15; // r15d
  unsigned __int8 *Pool2; // rax
  unsigned __int8 *v17; // r14
  unsigned int m_ActivityId; // [rsp+30h] [rbp-49h]
  __int64 v20; // [rsp+38h] [rbp-41h]
  int v21; // [rsp+38h] [rbp-41h]
  unsigned int v22; // [rsp+50h] [rbp-29h] BYREF
  int v23; // [rsp+54h] [rbp-25h] BYREF
  unsigned __int8 *v24; // [rsp+58h] [rbp-21h] BYREF
  int v25; // [rsp+60h] [rbp-19h] BYREF
  __int16 v26; // [rsp+64h] [rbp-15h]
  char v27; // [rsp+66h] [rbp-13h]
  size_t Size; // [rsp+68h] [rbp-11h] BYREF
  void *Src; // [rsp+70h] [rbp-9h]
  char v30; // [rsp+78h] [rbp-1h]

  v25 = 0;
  LODWORD(Size) = 0;
  Src = 0;
  v30 = 0;
  v24 = 0;
  v22 = 0;
  v23 = 0;
  v26 = 0;
  v27 = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      a3,
      129,
      (__int64)WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids,
      (char)this,
      this->m_ActivityId);
  }
  if ( (unsigned int)Task::get_OutputBuffer(&this->m_TaskCommand, &v22, &v24) || (v6 = v22, v22 < 0x30) )
  {
    v8 = -1073676267;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_47;
    v9 = 130;
    v21 = -1073676267;
LABEL_41:
    m_ActivityId = this->m_ActivityId;
LABEL_42:
    LOBYTE(RequestFrameType) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      RequestFrameType,
      v5,
      v9,
      (__int64)WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids,
      (char)this,
      m_ActivityId,
      v21);
    goto LABEL_43;
  }
  StatusFromTaskOutput = CMessageHelper::GetStatusFromTaskOutput(&this->m_TaskCommand, (unsigned int *)&v23);
  v8 = StatusFromTaskOutput;
  if ( StatusFromTaskOutput )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_47;
    v9 = 131;
    v21 = StatusFromTaskOutput;
    m_ActivityId = this->m_ActivityId;
    goto LABEL_42;
  }
  v8 = v23;
  if ( v23 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_47;
    LOBYTE(RequestFrameType) = 2;
    WPP_RECORDER_SF_qDdd(
      WPP_GLOBAL_Control->DeviceExtension,
      RequestFrameType,
      v5,
      132,
      (__int64)WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids,
      (char)this,
      this->m_ActivityId,
      v23,
      v23);
    goto LABEL_43;
  }
  v10 = ParseWdiIndicationP2pSendRequestActionFrameCompleteFromIhv(
          v6 - 48,
          v24 + 48,
          &this->m_pAdapter->m_TlvContext,
          &v25);
  v8 = v10;
  if ( v10 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_47;
    v9 = 133;
    v21 = v10;
    goto LABEL_41;
  }
  RequestFrameType = this->m_RequestParameters.RequestParams.RequestFrameType;
  if ( RequestFrameType == WDI_P2P_ACTION_FRAME_GO_NEGOTIATION_REQUEST )
  {
    GOConfigTimeout = this->m_RequestParameters.GONegotiationRequestInfo.RequestParams.GOConfigTimeout;
    ClientConfigTimeout = this->m_RequestParameters.GONegotiationRequestInfo.RequestParams.ClientConfigTimeout;
    goto LABEL_23;
  }
  if ( this->m_RequestParameters.RequestParams.RequestFrameType == WDI_P2P_ACTION_FRAME_INVITATION_REQUEST )
  {
    GOConfigTimeout = this->m_RequestParameters.InvitationRequestInfo.RequestParams.GOConfigTimeout;
    ClientConfigTimeout = this->m_RequestParameters.InvitationRequestInfo.RequestParams.ClientConfigTimeout;
    goto LABEL_23;
  }
  if ( this->m_RequestParameters.RequestParams.RequestFrameType == WDI_P2P_ACTION_FRAME_PROVISION_DISCOVERY_REQUEST
    && (*(_DWORD *)&this->m_RequestParameters.ProvisionDiscoveryRequestInfo.Optional & 2) != 0 )
  {
    GOConfigTimeout = this->m_RequestParameters.ProvisionDiscoveryRequestInfo.ServiceAttributes.GOConfigTimeout;
    ClientConfigTimeout = this->m_RequestParameters.ProvisionDiscoveryRequestInfo.ServiceAttributes.ClientConfigTimeout;
LABEL_23:
    CP2PActionFrameHelpers::ValidateConfigurationTimeoutInternal(
      this->m_pAdapter,
      (const unsigned __int8 *)Src,
      Size,
      GOConfigTimeout,
      ClientConfigTimeout,
      RequestFrameType);
  }
  if ( this->m_RequestParameters.RequestParams.RequestFrameType == WDI_P2P_ACTION_FRAME_GO_NEGOTIATION_REQUEST )
  {
    v14 = Size;
    v13 = 24;
    this->m_GONRequestSendCompleteParams.uIEsOffset = 24;
    this->m_GONRequestSendCompleteParams.Status = 0;
    this->m_GONRequestSendCompleteParams.uIEsLength = v14;
LABEL_30:
    v15 = v14 + v13;
    if ( v14 + (unsigned int)v13 >= (unsigned int)v13 )
    {
      Pool2 = (unsigned __int8 *)ExAllocatePool2(64, v15, 1198089303);
      v17 = Pool2;
      if ( Pool2 )
      {
        memmove(Pool2, &this->3780, v13);
        if ( (_DWORD)Size )
          memmove(&v17[v13], Src, (unsigned int)Size);
        this->m_pSendCompleteIndication = v17;
        this->m_SendCompleteIndicationLength = v15;
        goto LABEL_43;
      }
      v8 = -1073741670;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_47;
      v9 = 135;
      v21 = -1073741670;
    }
    else
    {
      v8 = -2147483643;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_47;
      v9 = 134;
      v21 = -2147483643;
    }
    goto LABEL_41;
  }
  if ( this->m_RequestParameters.RequestParams.RequestFrameType == WDI_P2P_ACTION_FRAME_INVITATION_REQUEST
    || this->m_RequestParameters.RequestParams.RequestFrameType == WDI_P2P_ACTION_FRAME_PROVISION_DISCOVERY_REQUEST )
  {
    this->m_GONRequestSendCompleteParams.uIEsLength = 0;
    v13 = 32;
    this->m_ProvDiscRequestSendCompleteParams.uIEsOffset = 32;
    v14 = Size;
    this->m_ProvDiscRequestSendCompleteParams.uIEsLength = Size;
    goto LABEL_30;
  }
  v8 = -1073741637;
LABEL_43:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(RequestFrameType) = 5;
    LODWORD(v20) = v8;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      RequestFrameType,
      v5,
      136,
      (__int64)WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids,
      (char)this,
      this->m_ActivityId,
      v20);
  }
LABEL_47:
  ArrayOfElements<enum _WDI_BAND_ID>::Cleanup(&Size);
  return v8;
}

```

## disassembly

```asm
0x1400c91e8  push    rbp
0x1400c91ea  push    rbx
0x1400c91eb  push    rsi
0x1400c91ec  push    rdi
0x1400c91ed  push    r12
0x1400c91ef  push    r13
0x1400c91f1  push    r14
0x1400c91f3  push    r15
0x1400c91f5  lea     rbp, [rsp-1Fh]
0x1400c91fa  sub     rsp, 98h
0x1400c9201  mov     rax, cs:__security_cookie
0x1400c9208  xor     rax, rsp
0x1400c920b  mov     [rbp+57h+var_50], rax
0x1400c920f  xor     eax, eax
0x1400c9211  mov     rbx, rcx
0x1400c9214  xor     r12d, r12d
0x1400c9217  mov     [rbp+57h+var_70], eax
0x1400c921a  mov     dword ptr [rbp+57h+Size], r12d
0x1400c921e  mov     [rbp+57h+Src], r12
0x1400c9222  mov     [rbp+57h+var_58], r12b
0x1400c9226  mov     [rbp+57h+var_78], r12
0x1400c922a  mov     [rbp+57h+var_80], r12d
0x1400c922e  mov     [rbp+57h+var_7C], r12d
0x1400c9232  mov     [rbp+57h+var_6C], ax
0x1400c9236  mov     [rbp+57h+var_6A], al
0x1400c9239  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400c9240  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400c9247  lea     r14, WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids
0x1400c924e  jz      short loc_1400C9286
0x1400c9250  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c9257  cmp     byte ptr [rcx+29h], 5
0x1400c925b  jnb     short loc_1400C9264
0x1400c925d  cmp     [rcx+48h], r12w
0x1400c9262  jz      short loc_1400C9286
0x1400c9264  mov     eax, [rbx+10h]
0x1400c9267  mov     r9d, 81h
0x1400c926d  mov     rcx, [rcx+40h]
0x1400c9271  mov     dl, 5
0x1400c9273  mov     [rsp+0D0h+var_A0], eax
0x1400c9277  mov     qword ptr [rsp+0D0h+var_A8], rbx
0x1400c927c  mov     qword ptr [rsp+0D0h+var_B0], r14
0x1400c9281  call    WPP_RECORDER_SF_qD
0x1400c9286  lea     rdi, [rbx+418h]
0x1400c928d  mov     rcx, rdi; this
0x1400c9290  lea     r8, [rbp+57h+var_78]; unsigned __int8 **
0x1400c9294  lea     rdx, [rbp+57h+var_80]; unsigned int *
0x1400c9298  call    ?get_OutputBuffer@Task@@QEAAHPEAKPEAPEAE@Z; Task::get_OutputBuffer(ulong *,uchar * *)
0x1400c929d  test    eax, eax
0x1400c929f  jnz     loc_1400C94F5
0x1400c92a5  mov     esi, [rbp+57h+var_80]
0x1400c92a8  cmp     esi, 30h ; '0'
0x1400c92ab  jb      loc_1400C94F5
0x1400c92b1  lea     rdx, [rbp+57h+var_7C]; int *
0x1400c92b5  mov     rcx, rdi; struct Task *
0x1400c92b8  call    ?GetStatusFromTaskOutput@CMessageHelper@@SAHPEAVTask@@PEAH@Z; CMessageHelper::GetStatusFromTaskOutput(Task *,int *)
0x1400c92bd  mov     edi, eax
0x1400c92bf  test    eax, eax
0x1400c92c1  jz      short loc_1400C92E6
0x1400c92c3  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400c92ca  jz      loc_1400C9577
0x1400c92d0  mov     ecx, [rbx+10h]
0x1400c92d3  mov     r9d, 83h
0x1400c92d9  mov     dword ptr [rsp+0D0h+var_98], eax
0x1400c92dd  mov     [rsp+0D0h+var_A0], ecx
0x1400c92e1  jmp     loc_1400C9518
0x1400c92e6  mov     edi, [rbp+57h+var_7C]
0x1400c92e9  test    edi, edi
0x1400c92eb  jz      short loc_1400C9330
0x1400c92ed  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400c92f4  jz      loc_1400C9577
0x1400c92fa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c9301  mov     r9d, 84h
0x1400c9307  mov     eax, [rbx+10h]
0x1400c930a  mov     dl, 2
0x1400c930c  mov     [rsp+0D0h+var_90], edi
0x1400c9310  mov     dword ptr [rsp+0D0h+var_98], edi
0x1400c9314  mov     rcx, [rcx+40h]
0x1400c9318  mov     [rsp+0D0h+var_A0], eax
0x1400c931c  mov     qword ptr [rsp+0D0h+var_A8], rbx
0x1400c9321  mov     qword ptr [rsp+0D0h+var_B0], r14
0x1400c9326  call    WPP_RECORDER_SF_qDdd
0x1400c932b  jmp     loc_1400C9534
0x1400c9330  mov     r8, [rbx+200h]
0x1400c9337  lea     ecx, [rsi-30h]
0x1400c933a  mov     rdx, [rbp+57h+var_78]
0x1400c933e  lea     r9, [rbp+57h+var_70]
0x1400c9342  add     r8, 3FF8h
0x1400c9349  add     rdx, 30h ; '0'
0x1400c934d  call    ParseWdiIndicationP2pSendRequestActionFrameCompleteFromIhv
0x1400c9352  mov     edi, eax
0x1400c9354  test    eax, eax
0x1400c9356  jz      short loc_1400C9374
0x1400c9358  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400c935f  jz      loc_1400C9577
0x1400c9365  mov     r9d, 85h
0x1400c936b  mov     dword ptr [rsp+0D0h+var_98], eax
0x1400c936f  jmp     loc_1400C9511
0x1400c9374  mov     edx, [rbx+22Ch]
0x1400c937a  mov     ecx, edx
0x1400c937c  sub     ecx, 1
0x1400c937f  jz      short loc_1400C93B7
0x1400c9381  sub     ecx, 3
0x1400c9384  jz      short loc_1400C93A6
0x1400c9386  cmp     ecx, 2
0x1400c9389  jnz     short loc_1400C93E3
0x1400c938b  mov     eax, [rbx+298h]
0x1400c9391  test    cl, al
0x1400c9393  jz      short loc_1400C93E3
0x1400c9395  movzx   r9d, word ptr [rbx+2E2h]
0x1400c939d  movzx   eax, word ptr [rbx+2E4h]
0x1400c93a4  jmp     short loc_1400C93C6
0x1400c93a6  movzx   r9d, word ptr [rbx+264h]
0x1400c93ae  movzx   eax, word ptr [rbx+266h]
0x1400c93b5  jmp     short loc_1400C93C6
0x1400c93b7  movzx   r9d, word ptr [rbx+246h]; unsigned __int16
0x1400c93bf  movzx   eax, word ptr [rbx+248h]
0x1400c93c6  mov     r8d, dword ptr [rbp+57h+Size]; unsigned int
0x1400c93ca  mov     rcx, [rbx+200h]; struct CAdapter *
0x1400c93d1  mov     [rsp+0D0h+var_A8], edx; enum _WDI_P2P_ACTION_FRAME_TYPE
0x1400c93d5  mov     rdx, [rbp+57h+Src]; unsigned __int8 *
0x1400c93d9  mov     [rsp+0D0h+var_B0], ax; unsigned __int16
0x1400c93de  call    ?ValidateConfigurationTimeoutInternal@CP2PActionFrameHelpers@@CAXPEAVCAdapter@@PEBEKGGW4_WDI_P2P_ACTION_FRAME_TYPE@@@Z; CP2PActionFrameHelpers::ValidateConfigurationTimeoutInternal(CAdapter *,uchar const *,ulong,ushort,ushort,_WDI_P2P_ACTION_FRAME_TYPE)
0x1400c93e3  mov     ecx, [rbx+22Ch]
0x1400c93e9  sub     ecx, 1
0x1400c93ec  jz      short loc_1400C9421
0x1400c93ee  sub     ecx, 3
0x1400c93f1  jz      short loc_1400C9402
0x1400c93f3  cmp     ecx, 2
0x1400c93f6  jz      short loc_1400C9402
0x1400c93f8  mov     edi, 0C00000BBh
0x1400c93fd  jmp     loc_1400C9534
0x1400c9402  mov     eax, 20h ; ' '
0x1400c9407  mov     [rbx+0ED8h], r12d
0x1400c940e  mov     esi, eax
0x1400c9410  mov     [rbx+0EDCh], eax
0x1400c9416  mov     eax, dword ptr [rbp+57h+Size]
0x1400c9419  mov     [rbx+0EE0h], eax
0x1400c941f  jmp     short loc_1400C943C
0x1400c9421  mov     eax, dword ptr [rbp+57h+Size]
0x1400c9424  mov     esi, 18h
0x1400c9429  mov     [rbx+0ED4h], esi
0x1400c942f  mov     [rbx+0ED0h], r12d
0x1400c9436  mov     [rbx+0ED8h], eax
0x1400c943c  lea     r15d, [rax+rsi]
0x1400c9440  cmp     r15d, esi
0x1400c9443  jnb     short loc_1400C946A
0x1400c9445  mov     edi, 80000005h
0x1400c944a  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400c9451  jz      loc_1400C9577
0x1400c9457  mov     r9d, 86h
0x1400c945d  mov     dword ptr [rsp+0D0h+var_98], 80000005h
0x1400c9465  jmp     loc_1400C9511
0x1400c946a  mov     edx, r15d
0x1400c946d  mov     ecx, 40h ; '@'
0x1400c9472  mov     r8d, 47696457h
0x1400c9478  call    cs:__imp_ExAllocatePool2
0x1400c947f  nop     dword ptr [rax+rax+00h]
0x1400c9484  mov     r14, rax
0x1400c9487  test    rax, rax
0x1400c948a  jnz     short loc_1400C94B5
0x1400c948c  mov     edi, 0C000009Ah
0x1400c9491  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400c9498  jz      loc_1400C9577
0x1400c949e  mov     r9d, 87h
0x1400c94a4  mov     dword ptr [rsp+0D0h+var_98], 0C000009Ah
0x1400c94ac  lea     r14, WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids
0x1400c94b3  jmp     short loc_1400C9511
0x1400c94b5  lea     rdx, [rbx+0EC4h]; Src
0x1400c94bc  mov     r8, rsi; Size
0x1400c94bf  mov     rcx, r14; void *
0x1400c94c2  call    memmove
0x1400c94c7  mov     eax, dword ptr [rbp+57h+Size]
0x1400c94ca  test    eax, eax
0x1400c94cc  jz      short loc_1400C94DE
0x1400c94ce  mov     rdx, [rbp+57h+Src]; Src
0x1400c94d2  lea     rcx, [rsi+r14]; void *
0x1400c94d6  mov     r8d, eax; Size
0x1400c94d9  call    memmove
0x1400c94de  mov     [rbx+0EB8h], r14
0x1400c94e5  lea     r14, WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids
0x1400c94ec  mov     [rbx+0EB0h], r15d
0x1400c94f3  jmp     short loc_1400C9534
0x1400c94f5  mov     edi, 0C0010015h
0x1400c94fa  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400c9501  jz      short loc_1400C9577
0x1400c9503  mov     r9d, 82h
0x1400c9509  mov     dword ptr [rsp+0D0h+var_98], 0C0010015h
0x1400c9511  mov     eax, [rbx+10h]
0x1400c9514  mov     [rsp+0D0h+var_A0], eax
0x1400c9518  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c951f  mov     dl, 2
0x1400c9521  mov     qword ptr [rsp+0D0h+var_A8], rbx
0x1400c9526  mov     qword ptr [rsp+0D0h+var_B0], r14
0x1400c952b  mov     rcx, [rcx+40h]
0x1400c952f  call    WPP_RECORDER_SF_qDD
0x1400c9534  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400c953b  jz      short loc_1400C9577
0x1400c953d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c9544  cmp     byte ptr [rcx+29h], 5
0x1400c9548  jnb     short loc_1400C9551
0x1400c954a  cmp     [rcx+48h], r12w
0x1400c954f  jz      short loc_1400C9577
0x1400c9551  mov     eax, [rbx+10h]
0x1400c9554  mov     r9d, 88h
0x1400c955a  mov     rcx, [rcx+40h]
0x1400c955e  mov     dl, 5
0x1400c9560  mov     dword ptr [rsp+0D0h+var_98], edi
0x1400c9564  mov     [rsp+0D0h+var_A0], eax
0x1400c9568  mov     qword ptr [rsp+0D0h+var_A8], rbx
0x1400c956d  mov     qword ptr [rsp+0D0h+var_B0], r14
0x1400c9572  call    WPP_RECORDER_SF_qDD
0x1400c9577  lea     rcx, [rbp+57h+Size]
0x1400c957b  call    ?Cleanup@?$ArrayOfElements@W4_WDI_BAND_ID@@@@QEAAXXZ; ArrayOfElements<_WDI_BAND_ID>::Cleanup(void)
0x1400c9580  mov     eax, edi
0x1400c9582  mov     rcx, [rbp+57h+var_50]
0x1400c9586  xor     rcx, rsp; StackCookie
0x1400c9589  call    __security_check_cookie
0x1400c958e  add     rsp, 98h
0x1400c9595  pop     r15
0x1400c9597  pop     r14
0x1400c9599  pop     r13
0x1400c959b  pop     r12
0x1400c959d  pop     rdi
0x1400c959e  pop     rsi
0x1400c959f  pop     rbx
0x1400c95a0  pop     rbp
0x1400c95a1  retn
```
