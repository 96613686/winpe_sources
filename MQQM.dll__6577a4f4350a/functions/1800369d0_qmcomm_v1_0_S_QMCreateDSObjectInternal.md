# qmcomm_v1_0_S_QMCreateDSObjectInternal

- ea: `0x1800369d0`
- end: `0x180036cfc`
- name: `qmcomm_v1_0_S_QMCreateDSObjectInternal`
- size: `812`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, unsigned int, unsigned int *, struct tagPROPVARIANT *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005690`

## callees

- `0x18000d1f0`
- `0x18000f35c`
- `0x180011578`
- `0x18002c61c`
- `0x1800363d0`
- `0x1800369d0`
- `0x180094f00`

## import_xrefs

- `msvcrt!free` at `0x180036c29`
- `msvcrt!free` at `0x180036c85`
- `msvcrt!free` at `0x180036ccb`
- `msvcrt!free` at `0x180036c29`
- `msvcrt!free` at `0x180036c85`
- `msvcrt!free` at `0x180036ccb`
- `ADVAPI32!IsValidRelativeSecurityDescriptor` at `0x180036bdb`
- `ADVAPI32!IsValidRelativeSecurityDescriptor` at `0x180036bdb`
- `mqsec!MQSec_GetLocalMachineSid` at `0x180036c39`
- `mqsec!MQSec_GetLocalMachineSid` at `0x180036c39`
- `mqsec!mqrpcIsLocalCall` at `0x180036a37`
- `mqsec!mqrpcIsLocalCall` at `0x180036a37`
- `mqsec!MQSec_GetDefaultPublicQueueSecurityDescriptor` at `0x180036c5f`
- `mqsec!MQSec_GetDefaultPublicQueueSecurityDescriptor` at `0x180036c5f`

## string_xrefs

- `0x180036b29`: `qmcommnd`
- `0x180036c10`: `qmcommnd`
- `0x180036c71`: `qmcommnd`
- `0x180036cdc`: `qmcommnd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall qmcomm_v1_0_S_QMCreateDSObjectInternal(
        void *a1,
        int a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6,
        unsigned int *a7,
        struct tagPROPVARIANT *a8,
        __int64 a9)
{
  unsigned __int16 v12; // r8
  unsigned int v13; // ebx
  int v14; // eax
  unsigned int v15; // edi
  PVOID *v17; // rcx
  int DefaultPublicQueueSecurityDescriptor; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  void *Block; // [rsp+50h] [rbp-48h] BYREF

  if ( a4 && !a5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_9c98d10e93893ba66448161eb5c1aef0_Traceguids);
    v12 = 1154;
    v13 = -1072824314;
    goto LABEL_43;
  }
  if ( !mqrpcIsLocalCall(a1) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_9c98d10e93893ba66448161eb5c1aef0_Traceguids);
    v12 = 1155;
LABEL_12:
    v13 = -1072824283;
LABEL_43:
    LogMsgHR(v13, (wchar_t *)L"qmcommnd", v12);
    return v13;
  }
  if ( !CQueueMgr::m_fCreatePublicQueueOnBehalfOfRT )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_9c98d10e93893ba66448161eb5c1aef0_Traceguids);
    v12 = 1153;
    goto LABEL_12;
  }
  v14 = QMpCheckQueueProps(a6, a7, a8, 1u, 0);
  v15 = v14;
  if ( v14 >= 0 )
  {
    v17 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
      v17 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( a2 != 56 )
    {
      v13 = -1072824319;
LABEL_42:
      v12 = 80;
      goto LABEL_43;
    }
    if ( !CQueueMgr::m_fCreatePublicQueueOnBehalfOfRT )
    {
      if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 1) != 0 )
        WPP_SF_(v17[2], 33, WPP_9c98d10e93893ba66448161eb5c1aef0_Traceguids);
      v12 = 1157;
      v13 = -1072824176;
      goto LABEL_43;
    }
    Block = 0;
    if ( a5 && !(unsigned int)IsValidRelativeSecurityDescriptor(a5, a4, 0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_9c98d10e93893ba66448161eb5c1aef0_Traceguids);
      v13 = -1072824314;
      LogMsgHR(-1072824314, (wchar_t *)L"qmcommnd", 0x486u);
      free(Block);
      return v13;
    }
    MQSec_GetLocalMachineSid(0, 0);
    DefaultPublicQueueSecurityDescriptor = MQSec_GetDefaultPublicQueueSecurityDescriptor(&Block, 1, a5);
    v13 = DefaultPublicQueueSecurityDescriptor;
    if ( DefaultPublicQueueSecurityDescriptor >= 0 )
    {
      v13 = ADCreateObject(0, v19, v20, a3, Block, a6, a7, a8, a9);
      free(Block);
      if ( (v13 & 0x80000000) != 0 )
        goto LABEL_42;
    }
    else
    {
      LogMsgHR(DefaultPublicQueueSecurityDescriptor, (wchar_t *)L"qmcommnd", 0x46u);
      free(Block);
    }
    return v13;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      31,
      WPP_9c98d10e93893ba66448161eb5c1aef0_Traceguids,
      (unsigned int)v14);
  LogMsgHR(v15, (wchar_t *)L"qmcommnd", 0x484u);
  return v15;
}

```

## disassembly

```asm
0x1800369d0  push    rbx
0x1800369d2  push    rbp
0x1800369d3  push    rdi
0x1800369d4  push    r12
0x1800369d6  push    r13
0x1800369d8  push    r14
0x1800369da  push    r15
0x1800369dc  sub     rsp, 60h
0x1800369e0  mov     ebp, r9d
0x1800369e3  mov     r15, r8
0x1800369e6  mov     r14d, edx
0x1800369e9  test    r9d, r9d
0x1800369ec  jz      short loc_180036A37
0x1800369ee  cmp     [rsp+98h+arg_20], 0
0x1800369f7  jnz     short loc_180036A37
0x1800369f9  lea     rbx, WPP_GLOBAL_Control
0x180036a00  mov     rcx, cs:WPP_GLOBAL_Control
0x180036a07  cmp     rcx, rbx
0x180036a0a  jz      short loc_180036A27
0x180036a0c  test    byte ptr [rcx+1Ch], 1
0x180036a10  jz      short loc_180036A27
0x180036a12  mov     edx, 1Ch
0x180036a17  lea     r8, WPP_9c98d10e93893ba66448161eb5c1aef0_Traceguids
0x180036a1e  mov     rcx, [rcx+10h]
0x180036a22  call    WPP_SF_
0x180036a27  mov     r8d, 482h
0x180036a2d  mov     ebx, 0C00E0006h
0x180036a32  jmp     loc_180036CDC
0x180036a37  call    cs:__imp_?mqrpcIsLocalCall@@YAHPEAX@Z; mqrpcIsLocalCall(void *)
0x180036a3d  test    eax, eax
0x180036a3f  jnz     short loc_180036A7D
0x180036a41  lea     rbx, WPP_GLOBAL_Control
0x180036a48  mov     rcx, cs:WPP_GLOBAL_Control
0x180036a4f  cmp     rcx, rbx
0x180036a52  jz      short loc_180036A6D
0x180036a54  test    byte ptr [rcx+1Ch], 1
0x180036a58  jz      short loc_180036A6D
0x180036a5a  lea     edx, [rax+1Dh]
0x180036a5d  lea     r8, WPP_9c98d10e93893ba66448161eb5c1aef0_Traceguids
0x180036a64  mov     rcx, [rcx+10h]
0x180036a68  call    WPP_SF_
0x180036a6d  mov     r8d, 483h
0x180036a73  mov     ebx, 0C00E0025h
0x180036a78  jmp     loc_180036CDC
0x180036a7d  cmp     cs:?m_fCreatePublicQueueOnBehalfOfRT@CQueueMgr@@0_NA, 0; bool CQueueMgr::m_fCreatePublicQueueOnBehalfOfRT
0x180036a84  jnz     short loc_180036ABC
0x180036a86  lea     rbx, WPP_GLOBAL_Control
0x180036a8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180036a94  cmp     rcx, rbx
0x180036a97  jz      short loc_180036AB4
0x180036a99  test    byte ptr [rcx+1Ch], 1
0x180036a9d  jz      short loc_180036AB4
0x180036a9f  mov     edx, 1Eh
0x180036aa4  lea     r8, WPP_9c98d10e93893ba66448161eb5c1aef0_Traceguids
0x180036aab  mov     rcx, [rcx+10h]
0x180036aaf  call    WPP_SF_
0x180036ab4  mov     r8d, 481h
0x180036aba  jmp     short loc_180036A73
0x180036abc  mov     [rsp+98h+var_78], 0; int
0x180036ac4  mov     r9d, 1; unsigned int
0x180036aca  mov     r12, [rsp+98h+arg_38]
0x180036ad2  mov     r8, r12; struct tagPROPVARIANT *
0x180036ad5  mov     r13, [rsp+98h+arg_30]
0x180036add  mov     rdx, r13; unsigned int *
0x180036ae0  mov     ecx, [rsp+98h+arg_28]; unsigned int
0x180036ae7  call    ?QMpCheckQueueProps@@YAJKPEAKPEAUtagPROPVARIANT@@KH@Z; QMpCheckQueueProps(ulong,ulong *,tagPROPVARIANT *,ulong,int)
0x180036aec  mov     edi, eax
0x180036aee  test    eax, eax
0x180036af0  jns     short loc_180036B3E
0x180036af2  lea     rbx, WPP_GLOBAL_Control
0x180036af9  mov     rcx, cs:WPP_GLOBAL_Control
0x180036b00  cmp     rcx, rbx
0x180036b03  jz      short loc_180036B23
0x180036b05  test    byte ptr [rcx+1Ch], 1
0x180036b09  jz      short loc_180036B23
0x180036b0b  mov     edx, 1Fh
0x180036b10  mov     r9d, eax
0x180036b13  lea     r8, WPP_9c98d10e93893ba66448161eb5c1aef0_Traceguids
0x180036b1a  mov     rcx, [rcx+10h]
0x180036b1e  call    WPP_SF_d
0x180036b23  mov     r8d, 484h; unsigned __int16
0x180036b29  lea     rdx, aQmcommnd; "qmcommnd"
0x180036b30  mov     ecx, edi; int
0x180036b32  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180036b37  mov     eax, edi
0x180036b39  jmp     loc_180036CEC
0x180036b3e  lea     rbx, WPP_GLOBAL_Control
0x180036b45  mov     rcx, cs:WPP_GLOBAL_Control
0x180036b4c  cmp     rcx, rbx
0x180036b4f  jz      short loc_180036B76
0x180036b51  test    byte ptr [rcx+1Ch], 4
0x180036b55  jz      short loc_180036B76
0x180036b57  mov     edx, 20h ; ' '
0x180036b5c  mov     r9, r15
0x180036b5f  lea     r8, WPP_9c98d10e93893ba66448161eb5c1aef0_Traceguids
0x180036b66  mov     rcx, [rcx+10h]; LoggerHandle
0x180036b6a  call    WPP_SF_S
0x180036b6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180036b76  cmp     r14d, 38h ; '8'
0x180036b7a  jz      short loc_180036B86
0x180036b7c  mov     ebx, 0C00E0001h
0x180036b81  jmp     loc_180036CD6
0x180036b86  xor     edi, edi
0x180036b88  cmp     cs:?m_fCreatePublicQueueOnBehalfOfRT@CQueueMgr@@0_NA, dil; bool CQueueMgr::m_fCreatePublicQueueOnBehalfOfRT
0x180036b8f  jnz     short loc_180036BBF
0x180036b91  cmp     rcx, rbx
0x180036b94  jz      short loc_180036BAF
0x180036b96  test    byte ptr [rcx+1Ch], 1
0x180036b9a  jz      short loc_180036BAF
0x180036b9c  lea     edx, [rdi+21h]
0x180036b9f  lea     r8, WPP_9c98d10e93893ba66448161eb5c1aef0_Traceguids
0x180036ba6  mov     rcx, [rcx+10h]
0x180036baa  call    WPP_SF_
0x180036baf  mov     r8d, 485h
0x180036bb5  mov     ebx, 0C00E0090h
0x180036bba  jmp     loc_180036CDC
0x180036bbf  mov     [rsp+98h+Block], rdi
0x180036bc4  cmp     [rsp+98h+arg_20], rdi
0x180036bcc  jz      short loc_180036C35
0x180036bce  xor     r8d, r8d
0x180036bd1  mov     edx, ebp
0x180036bd3  mov     rcx, [rsp+98h+arg_20]
0x180036bdb  call    cs:__imp_IsValidRelativeSecurityDescriptor
0x180036be1  test    eax, eax
0x180036be3  jnz     short loc_180036C35
0x180036be5  mov     rcx, cs:WPP_GLOBAL_Control
0x180036bec  cmp     rcx, rbx
0x180036bef  jz      short loc_180036C0A
0x180036bf1  test    byte ptr [rcx+1Ch], 1
0x180036bf5  jz      short loc_180036C0A
0x180036bf7  lea     edx, [rax+22h]
0x180036bfa  lea     r8, WPP_9c98d10e93893ba66448161eb5c1aef0_Traceguids
0x180036c01  mov     rcx, [rcx+10h]
0x180036c05  call    WPP_SF_
0x180036c0a  mov     r8d, 486h; unsigned __int16
0x180036c10  lea     rdx, aQmcommnd; "qmcommnd"
0x180036c17  mov     ebx, 0C00E0006h
0x180036c1c  mov     ecx, ebx; int
0x180036c1e  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180036c23  nop
0x180036c24  mov     rcx, [rsp+98h+Block]; Block
0x180036c29  call    cs:__imp_free
0x180036c2f  nop
0x180036c30  jmp     loc_180036CEA
0x180036c35  xor     edx, edx
0x180036c37  xor     ecx, ecx
0x180036c39  call    cs:__imp_?MQSec_GetLocalMachineSid@@YAPEAXHPEAK@Z; MQSec_GetLocalMachineSid(int,ulong *)
0x180036c3f  mov     [rsp+98h+var_70], rax
0x180036c44  mov     [rsp+98h+var_78], edi
0x180036c48  mov     r9d, 3
0x180036c4e  mov     r8, [rsp+98h+arg_20]
0x180036c56  lea     edx, [r9-2]
0x180036c5a  lea     rcx, [rsp+98h+Block]
0x180036c5f  call    cs:__imp_?MQSec_GetDefaultPublicQueueSecurityDescriptor@@YAJPEAPEAXHPEAXKW4enumDaclType@@1@Z; MQSec_GetDefaultPublicQueueSecurityDescriptor(void * *,int,void *,ulong,enumDaclType,void *)
0x180036c65  mov     ebx, eax
0x180036c67  test    eax, eax
0x180036c69  jns     short loc_180036C8E
0x180036c6b  mov     r8d, 46h ; 'F'; unsigned __int16
0x180036c71  lea     rdx, aQmcommnd; "qmcommnd"
0x180036c78  mov     ecx, eax; int
0x180036c7a  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180036c7f  nop
0x180036c80  mov     rcx, [rsp+98h+Block]; Block
0x180036c85  call    cs:__imp_free
0x180036c8b  nop
0x180036c8c  jmp     short loc_180036CEA
0x180036c8e  mov     rax, [rsp+98h+arg_40]
0x180036c96  mov     [rsp+98h+var_58], rax
0x180036c9b  mov     [rsp+98h+var_60], r12
0x180036ca0  mov     [rsp+98h+var_68], r13
0x180036ca5  mov     eax, [rsp+98h+arg_28]
0x180036cac  mov     dword ptr [rsp+98h+var_70], eax
0x180036cb0  mov     rax, [rsp+98h+Block]
0x180036cb5  mov     qword ptr [rsp+98h+var_78], rax
0x180036cba  mov     r9, r15
0x180036cbd  xor     ecx, ecx
0x180036cbf  call    ?ADCreateObject@@YAJW4AD_OBJECT@@PEB_W_N1PEAXKQEBKQEBUtagPROPVARIANT@@PEAU_GUID@@@Z; ADCreateObject(AD_OBJECT,wchar_t const *,bool,wchar_t const *,void *,ulong,ulong const * const,tagPROPVARIANT const * const,_GUID *)
0x180036cc4  mov     ebx, eax
0x180036cc6  mov     rcx, [rsp+98h+Block]; Block
0x180036ccb  call    cs:__imp_free
0x180036cd1  nop
0x180036cd2  test    ebx, ebx
0x180036cd4  jns     short loc_180036CEA
0x180036cd6  mov     r8d, 50h ; 'P'; unsigned __int16
0x180036cdc  lea     rdx, aQmcommnd; "qmcommnd"
0x180036ce3  mov     ecx, ebx; int
0x180036ce5  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180036cea  mov     eax, ebx
0x180036cec  add     rsp, 60h
0x180036cf0  pop     r15
0x180036cf2  pop     r14
0x180036cf4  pop     r13
0x180036cf6  pop     r12
0x180036cf8  pop     rdi
0x180036cf9  pop     rbp
0x180036cfa  pop     rbx
0x180036cfb  retn
```
