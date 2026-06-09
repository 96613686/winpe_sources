# CP2PSendActionFrameResponseJob::HandleCommandCompletion(void *,int,int,ulong,uchar *,bool *)

- ea: `0x1400c9860`
- end: `0x1400c9ba8`
- name: `?HandleCommandCompletion@CP2PSendActionFrameResponseJob@@UEAAHPEAXHHKPEAEPEA_N@Z`
- size: `840`
- prototype: `__int64 __fastcall(CP2PSendActionFrameResponseJob *__hidden this, void *, int, int, unsigned int, unsigned __int8 *, bool *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1400122e0`
- `0x14001a808`
- `0x14002aa28`
- `0x14008dc30`
- `0x1400c9860`
- `0x1400ce198`
- `0x1400da4f0`
- `0x1400dac80`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400c9ac3`
- `ntoskrnl!ExAllocatePool2` at `0x1400c9ac3`

## pseudocode

```c
__int64 __fastcall CP2PSendActionFrameResponseJob::HandleCommandCompletion(
        CP2PSendActionFrameResponseJob *this,
        void *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned __int8 *a6,
        bool *a7)
{
  unsigned int v8; // edi
  __int64 *v10; // rdx
  int v11; // r9d
  int v12; // edx
  int v13; // r8d
  unsigned int v14; // eax
  int v15; // r9d
  enum _WDI_P2P_ACTION_FRAME_TYPE ResponseFrameType; // ecx
  unsigned __int16 GOConfigTimeout; // r9
  unsigned __int16 ClientConfigTimeout; // ax
  unsigned int v19; // eax
  unsigned int v20; // r14d
  __int64 Pool2; // rax
  unsigned __int8 *v22; // rsi
  unsigned int m_ActivityId; // [rsp+30h] [rbp-48h]
  __int64 v25; // [rsp+38h] [rbp-40h]
  unsigned int v26; // [rsp+38h] [rbp-40h]
  int v27; // [rsp+38h] [rbp-40h]
  __int64 v28; // [rsp+40h] [rbp-38h] BYREF
  size_t Size; // [rsp+48h] [rbp-30h] BYREF
  void *Src; // [rsp+50h] [rbp-28h]
  char v31; // [rsp+58h] [rbp-20h]

  LODWORD(Size) = 0;
  Src = 0;
  v8 = a3;
  v31 = 0;
  LODWORD(v28) = 0;
  WORD2(v28) = 0;
  BYTE6(v28) = 0;
  v10 = WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v10) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v10,
      a3,
      169,
      (__int64)WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids,
      (char)this,
      this->m_ActivityId);
    v10 = WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids;
  }
  *a7 = 0;
  if ( v8 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_43;
    v11 = 170;
    v26 = v8;
    goto LABEL_8;
  }
  if ( !a4 )
  {
    v14 = ParseWdiIndicationP2pSendResponseActionFrameCompleteFromIhv(
            a5 - 48,
            a6 + 48,
            &this->m_pAdapter->m_TlvContext,
            &v28);
    v8 = v14;
    if ( v14 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_43;
      v15 = 172;
      v27 = v14;
      m_ActivityId = this->m_ActivityId;
LABEL_15:
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        v13,
        v15,
        (__int64)WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids,
        (char)this,
        m_ActivityId,
        v27,
        v28);
      goto LABEL_39;
    }
    ResponseFrameType = this->m_ResponseParameters.ResponseParams.ResponseFrameType;
    if ( ResponseFrameType == WDI_P2P_ACTION_FRAME_GO_NEGOTIATION_RESPONSE )
    {
      GOConfigTimeout = this->m_ResponseParameters.GONegotiationResponseInfo.ResponseParams.GOConfigTimeout;
      ClientConfigTimeout = this->m_ResponseParameters.GONegotiationResponseInfo.ResponseParams.ClientConfigTimeout;
    }
    else if ( ResponseFrameType == WDI_P2P_ACTION_FRAME_INVITATION_RESPONSE )
    {
      GOConfigTimeout = this->m_ResponseParameters.InvitationResponseInfo.ResponseParams.GOConfigTimeout;
      ClientConfigTimeout = this->m_ResponseParameters.InvitationResponseInfo.ResponseParams.ClientConfigTimeout;
    }
    else
    {
      if ( ResponseFrameType != WDI_P2P_ACTION_FRAME_PROVISION_DISCOVERY_RESPONSE
        || (*(_DWORD *)&this->m_ResponseParameters.ProvisionDiscoveryResponseInfo.Optional & 1) == 0 )
      {
        goto LABEL_24;
      }
      GOConfigTimeout = this->m_ResponseParameters.ProvisionDiscoveryResponseInfo.ServiceAttributes.GOConfigTimeout;
      ClientConfigTimeout = this->m_ResponseParameters.ProvisionDiscoveryResponseInfo.ServiceAttributes.ClientConfigTimeout;
    }
    CP2PActionFrameHelpers::ValidateConfigurationTimeoutInternal(
      this->m_pAdapter,
      (const unsigned __int8 *)Src,
      Size,
      GOConfigTimeout,
      ClientConfigTimeout,
      ResponseFrameType);
LABEL_24:
    if ( this->m_ResponseParameters.ResponseParams.ResponseFrameType != WDI_P2P_ACTION_FRAME_GO_NEGOTIATION_RESPONSE
      && this->m_ResponseParameters.ResponseParams.ResponseFrameType != WDI_P2P_ACTION_FRAME_GO_NEGOTIATION_CONFIRM
      && this->m_ResponseParameters.ResponseParams.ResponseFrameType != WDI_P2P_ACTION_FRAME_INVITATION_RESPONSE
      && this->m_ResponseParameters.ResponseParams.ResponseFrameType != WDI_P2P_ACTION_FRAME_PROVISION_DISCOVERY_RESPONSE )
    {
      v8 = -1073741637;
      goto LABEL_39;
    }
    v19 = Size;
    this->m_GONResponseSendCompleteParams.Status = 0;
    this->m_GONResponseSendCompleteParams.uIEsOffset = 24;
    this->m_GONResponseSendCompleteParams.uIEsLength = v19;
    v20 = v19 + 24;
    if ( v19 < 0xFFFFFFE8 )
    {
      Pool2 = ExAllocatePool2(64, v20, 1198089303);
      v22 = (unsigned __int8 *)Pool2;
      if ( Pool2 )
      {
        *(_OWORD *)Pool2 = *(_OWORD *)&this->m_GONResponseSendCompleteParams.Header.Type;
        *(_QWORD *)(Pool2 + 16) = *(_QWORD *)&this->m_InvitationResponseSendCompleteParams.uIEsOffset;
        if ( (_DWORD)Size )
          memmove((void *)(Pool2 + 24), Src, (unsigned int)Size);
        this->m_pSendCompleteIndication = v22;
        this->m_SendCompleteIndicationLength = v20;
        goto LABEL_39;
      }
      v8 = -1073741670;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_43;
      v15 = 174;
      v27 = -1073741670;
    }
    else
    {
      v8 = -2147483643;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_43;
      v15 = 173;
      v27 = -2147483643;
    }
    m_ActivityId = this->m_ActivityId;
    goto LABEL_15;
  }
  v8 = a4;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
    goto LABEL_43;
  v11 = 171;
  v26 = a4;
LABEL_8:
  LOBYTE(v10) = 2;
  WPP_RECORDER_SF_qDD(
    WPP_GLOBAL_Control->DeviceExtension,
    (_DWORD)v10,
    a3,
    v11,
    (__int64)WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids,
    (char)this,
    this->m_ActivityId,
    v26,
    v28);
LABEL_39:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v12) = 5;
    LODWORD(v25) = v8;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      v13,
      175,
      (__int64)WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids,
      (char)this,
      this->m_ActivityId,
      v25);
  }
LABEL_43:
  ArrayOfElements<enum _WDI_BAND_ID>::Cleanup(&Size);
  return v8;
}

```

## disassembly

```asm
0x1400c9860  push    rbp
0x1400c9862  push    rbx
0x1400c9863  push    rsi
0x1400c9864  push    rdi
0x1400c9865  push    r12
0x1400c9867  push    r13
0x1400c9869  push    r14
0x1400c986b  push    r15
0x1400c986d  mov     rbp, rsp
0x1400c9870  sub     rsp, 78h
0x1400c9874  mov     rax, cs:__security_cookie
0x1400c987b  xor     rax, rsp
0x1400c987e  mov     [rbp+var_18], rax
0x1400c9882  mov     r15, [rbp+arg_28]
0x1400c9886  xor     eax, eax
0x1400c9888  mov     r14, [rbp+arg_30]
0x1400c988c  xor     r12d, r12d
0x1400c988f  mov     dword ptr [rbp+Size], r12d
0x1400c9893  mov     esi, r9d
0x1400c9896  mov     [rbp+Src], r12
0x1400c989a  mov     edi, r8d
0x1400c989d  mov     [rbp+var_20], r12b
0x1400c98a1  mov     rbx, rcx
0x1400c98a4  mov     [rbp+var_38], eax
0x1400c98a7  mov     [rbp+var_34], ax
0x1400c98ab  mov     [rbp+var_32], al
0x1400c98ae  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400c98b5  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400c98bc  lea     rdx, WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids
0x1400c98c3  jz      short loc_1400C9902
0x1400c98c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c98cc  cmp     byte ptr [rcx+29h], 5
0x1400c98d0  jnb     short loc_1400C98D9
0x1400c98d2  cmp     [rcx+48h], r12w
0x1400c98d7  jz      short loc_1400C9902
0x1400c98d9  mov     eax, [rbx+10h]
0x1400c98dc  mov     r9d, 0A9h
0x1400c98e2  mov     rcx, [rcx+40h]
0x1400c98e6  mov     [rsp+78h+var_48], eax
0x1400c98ea  mov     qword ptr [rsp+78h+var_50], rbx
0x1400c98ef  mov     qword ptr [rsp+78h+var_58], rdx
0x1400c98f4  mov     dl, 5
0x1400c98f6  call    WPP_RECORDER_SF_qD
0x1400c98fb  lea     rdx, WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids
0x1400c9902  mov     [r14], r12b
0x1400c9905  test    edi, edi
0x1400c9907  jz      short loc_1400C9948
0x1400c9909  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400c9910  jz      loc_1400C9B7F
0x1400c9916  mov     r9d, 0AAh
0x1400c991c  mov     dword ptr [rsp+78h+var_40], edi
0x1400c9920  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c9927  mov     eax, [rbx+10h]
0x1400c992a  mov     [rsp+78h+var_48], eax
0x1400c992e  mov     qword ptr [rsp+78h+var_50], rbx
0x1400c9933  mov     rcx, [rcx+40h]
0x1400c9937  mov     qword ptr [rsp+78h+var_58], rdx
0x1400c993c  mov     dl, 2
0x1400c993e  call    WPP_RECORDER_SF_qDD
0x1400c9943  jmp     loc_1400C9B35
0x1400c9948  test    esi, esi
0x1400c994a  jz      short loc_1400C9967
0x1400c994c  mov     edi, esi
0x1400c994e  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400c9955  jz      loc_1400C9B7F
0x1400c995b  mov     r9d, 0ABh
0x1400c9961  mov     dword ptr [rsp+78h+var_40], esi
0x1400c9965  jmp     short loc_1400C9920
0x1400c9967  mov     r8, [rbx+200h]
0x1400c996e  lea     rdx, [r15+30h]
0x1400c9972  mov     ecx, [rbp+arg_20]
0x1400c9975  lea     r9, [rbp+var_38]
0x1400c9979  add     r8, 3FF8h
0x1400c9980  add     ecx, 0FFFFFFD0h
0x1400c9983  call    ParseWdiIndicationP2pSendResponseActionFrameCompleteFromIhv
0x1400c9988  mov     edi, eax
0x1400c998a  test    eax, eax
0x1400c998c  jz      short loc_1400C99D4
0x1400c998e  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400c9995  jz      loc_1400C9B7F
0x1400c999b  mov     ecx, [rbx+10h]
0x1400c999e  mov     r9d, 0ACh
0x1400c99a4  mov     dword ptr [rsp+78h+var_40], eax
0x1400c99a8  mov     [rsp+78h+var_48], ecx
0x1400c99ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c99b3  lea     rsi, WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids
0x1400c99ba  mov     qword ptr [rsp+78h+var_50], rbx
0x1400c99bf  mov     dl, 2
0x1400c99c1  mov     qword ptr [rsp+78h+var_58], rsi
0x1400c99c6  mov     rcx, [rcx+40h]
0x1400c99ca  call    WPP_RECORDER_SF_qDD
0x1400c99cf  jmp     loc_1400C9B3C
0x1400c99d4  mov     ecx, [rbx+434h]
0x1400c99da  cmp     ecx, 2
0x1400c99dd  jz      short loc_1400C9A15
0x1400c99df  cmp     ecx, 5
0x1400c99e2  jz      short loc_1400C9A04
0x1400c99e4  cmp     ecx, 7
0x1400c99e7  jnz     short loc_1400C9A41
0x1400c99e9  mov     eax, [rbx+4C8h]
0x1400c99ef  test    al, 1
0x1400c99f1  jz      short loc_1400C9A41
0x1400c99f3  movzx   r9d, word ptr [rbx+4F2h]
0x1400c99fb  movzx   eax, word ptr [rbx+4F4h]
0x1400c9a02  jmp     short loc_1400C9A24
0x1400c9a04  movzx   r9d, word ptr [rbx+4B6h]
0x1400c9a0c  movzx   eax, word ptr [rbx+4B8h]
0x1400c9a13  jmp     short loc_1400C9A24
0x1400c9a15  movzx   r9d, word ptr [rbx+450h]; unsigned __int16
0x1400c9a1d  movzx   eax, word ptr [rbx+452h]
0x1400c9a24  mov     r8d, dword ptr [rbp+Size]; unsigned int
0x1400c9a28  mov     rdx, [rbp+Src]; unsigned __int8 *
0x1400c9a2c  mov     [rsp+78h+var_50], ecx; enum _WDI_P2P_ACTION_FRAME_TYPE
0x1400c9a30  mov     rcx, [rbx+200h]; struct CAdapter *
0x1400c9a37  mov     [rsp+78h+var_58], ax; unsigned __int16
0x1400c9a3c  call    ?ValidateConfigurationTimeoutInternal@CP2PActionFrameHelpers@@CAXPEAVCAdapter@@PEBEKGGW4_WDI_P2P_ACTION_FRAME_TYPE@@@Z; CP2PActionFrameHelpers::ValidateConfigurationTimeoutInternal(CAdapter *,uchar const *,ulong,ushort,ushort,_WDI_P2P_ACTION_FRAME_TYPE)
0x1400c9a41  mov     ecx, [rbx+434h]
0x1400c9a47  sub     ecx, 2
0x1400c9a4a  jz      short loc_1400C9A65
0x1400c9a4c  sub     ecx, 1
0x1400c9a4f  jz      short loc_1400C9A65
0x1400c9a51  sub     ecx, 2
0x1400c9a54  jz      short loc_1400C9A65
0x1400c9a56  cmp     ecx, 2
0x1400c9a59  jz      short loc_1400C9A65
0x1400c9a5b  mov     edi, 0C00000BBh
0x1400c9a60  jmp     loc_1400C9B35
0x1400c9a65  mov     eax, dword ptr [rbp+Size]
0x1400c9a68  mov     [rbx+61Ch], r12d
0x1400c9a6f  mov     dword ptr [rbx+620h], 18h
0x1400c9a79  mov     [rbx+624h], eax
0x1400c9a7f  lea     r14d, [rax+18h]
0x1400c9a83  cmp     r14d, 18h
0x1400c9a87  jnb     short loc_1400C9AB5
0x1400c9a89  mov     edi, 80000005h
0x1400c9a8e  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400c9a95  jz      loc_1400C9B7F
0x1400c9a9b  mov     r9d, 0ADh
0x1400c9aa1  mov     dword ptr [rsp+78h+var_40], 80000005h
0x1400c9aa9  mov     eax, [rbx+10h]
0x1400c9aac  mov     [rsp+78h+var_48], eax
0x1400c9ab0  jmp     loc_1400C99AC
0x1400c9ab5  mov     edx, r14d
0x1400c9ab8  mov     ecx, 40h ; '@'
0x1400c9abd  mov     r8d, 47696457h
0x1400c9ac3  call    cs:__imp_ExAllocatePool2
0x1400c9aca  nop     dword ptr [rax+rax+00h]
0x1400c9acf  mov     rsi, rax
0x1400c9ad2  test    rax, rax
0x1400c9ad5  jnz     short loc_1400C9AF9
0x1400c9ad7  mov     edi, 0C000009Ah
0x1400c9adc  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400c9ae3  jz      loc_1400C9B7F
0x1400c9ae9  mov     r9d, 0AEh
0x1400c9aef  mov     dword ptr [rsp+78h+var_40], 0C000009Ah
0x1400c9af7  jmp     short loc_1400C9AA9
0x1400c9af9  movups  xmm0, xmmword ptr [rbx+610h]
0x1400c9b00  movups  xmmword ptr [rax], xmm0
0x1400c9b03  movsd   xmm1, qword ptr [rbx+620h]
0x1400c9b0b  movsd   qword ptr [rax+10h], xmm1
0x1400c9b10  mov     eax, dword ptr [rbp+Size]
0x1400c9b13  test    eax, eax
0x1400c9b15  jz      short loc_1400C9B27
0x1400c9b17  mov     rdx, [rbp+Src]; Src
0x1400c9b1b  lea     rcx, [rsi+18h]; void *
0x1400c9b1f  mov     r8d, eax; Size
0x1400c9b22  call    memmove
0x1400c9b27  mov     [rbx+608h], rsi
0x1400c9b2e  mov     [rbx+600h], r14d
0x1400c9b35  lea     rsi, WPP_fe57965ba5083d01a32a2a61a938c51f_Traceguids
0x1400c9b3c  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400c9b43  jz      short loc_1400C9B7F
0x1400c9b45  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c9b4c  cmp     byte ptr [rcx+29h], 5
0x1400c9b50  jnb     short loc_1400C9B59
0x1400c9b52  cmp     [rcx+48h], r12w
0x1400c9b57  jz      short loc_1400C9B7F
0x1400c9b59  mov     eax, [rbx+10h]
0x1400c9b5c  mov     r9d, 0AFh
0x1400c9b62  mov     rcx, [rcx+40h]
0x1400c9b66  mov     dl, 5
0x1400c9b68  mov     dword ptr [rsp+78h+var_40], edi
0x1400c9b6c  mov     [rsp+78h+var_48], eax
0x1400c9b70  mov     qword ptr [rsp+78h+var_50], rbx
0x1400c9b75  mov     qword ptr [rsp+78h+var_58], rsi
0x1400c9b7a  call    WPP_RECORDER_SF_qDD
0x1400c9b7f  lea     rcx, [rbp+Size]
0x1400c9b83  call    ?Cleanup@?$ArrayOfElements@W4_WDI_BAND_ID@@@@QEAAXXZ; ArrayOfElements<_WDI_BAND_ID>::Cleanup(void)
0x1400c9b88  mov     eax, edi
0x1400c9b8a  mov     rcx, [rbp+var_18]
0x1400c9b8e  xor     rcx, rsp; StackCookie
0x1400c9b91  call    __security_check_cookie
0x1400c9b96  add     rsp, 78h
0x1400c9b9a  pop     r15
0x1400c9b9c  pop     r14
0x1400c9b9e  pop     r13
0x1400c9ba0  pop     r12
0x1400c9ba2  pop     rdi
0x1400c9ba3  pop     rsi
0x1400c9ba4  pop     rbx
0x1400c9ba5  pop     rbp
0x1400c9ba6  retn
```
