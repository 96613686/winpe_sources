# BfeRpcObjectDeleteByKey

- ea: `0x180009780`
- end: `0x180009be7`
- name: `BfeRpcObjectDeleteByKey`
- size: `1127`
- prototype: ``
- caller_count: `5`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003e7e0`
- `0x180044940`
- `0x18004ad60`
- `0x18004b200`
- `0x180062cc0`

## callees

- `0x1800051f4`
- `0x18000798c`
- `0x180008f60`
- `0x180009780`
- `0x18000a070`
- `0x18000b3d4`
- `0x18000c188`
- `0x18000fb34`
- `0x180011510`
- `0x1800133a0`
- `0x180024ab0`
- `0x18002681c`
- `0x18004b024`
- `0x1800592f4`
- `0x18005aa60`

## import_xrefs

- `ntdll!RtlLookupEntryHashTable` at `0x1800098ca`
- `ntdll!RtlLookupEntryHashTable` at `0x1800098ca`
- `ntdll!RtlGetNextEntryHashTable` at `0x180009971`
- `ntdll!RtlGetNextEntryHashTable` at `0x180009971`
- `RPCRT4!RpcRaiseException` at `0x180009aa5`
- `RPCRT4!RpcRaiseException` at `0x180009ba3`
- `RPCRT4!RpcRaiseException` at `0x180009aa5`
- `RPCRT4!RpcRaiseException` at `0x180009ba3`

## string_xrefs

- `0x1800098d9`: `BfeObjectDeleteByKey`
- `0x18000990d`: `BfeObjectDeleteByKey`
- `0x180009982`: `BfeObjectDeleteByKey`
- `0x1800099b1`: `BfeObjectDeleteByKey`
- `0x180009a3e`: `BfeCallCommitEx`

## pseudocode

```c
__int64 __fastcall BfeRpcObjectDeleteByKey(__int64 a1, int a2, unsigned int a3, _QWORD *a4)
{
  __int64 v7; // r14
  __int64 v8; // rbx
  __int64 result; // rax
  __int64 v10; // rbx
  __int64 v11; // rdi
  __int64 v12; // r14
  __int64 v13; // rdx
  __int64 NextEntryHashTable; // rax
  const char *v15; // r8
  _QWORD *v16; // rcx
  const char *v17; // rdi
  __int64 v18; // rbx
  _QWORD *Key; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  RPC_STATUS v23; // ecx
  RPC_STATUS v24; // eax
  __int64 v25; // rbx
  int v26; // eax
  int v27; // [rsp+38h] [rbp-49h] BYREF
  _OWORD TlsValue[2]; // [rsp+40h] [rbp-41h] BYREF
  __int128 v29; // [rsp+60h] [rbp-21h] BYREF
  const char *v30; // [rsp+70h] [rbp-11h]
  __int64 v31; // [rsp+78h] [rbp-9h]
  int *v32; // [rsp+80h] [rbp-1h]
  __int64 v33; // [rsp+88h] [rbp+7h]

  v7 = (int)a3;
  memset(TlsValue, 0, sizeof(TlsValue));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v25 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v26 = BfeObjectTypeIdToString(a3);
    WPP_SF_S_guid_(v25, 13, (unsigned int)WPP_58c1eeaf0b3d34d2a0a5eb62f8ccddc7_Traceguids, v26, (__int64)a4);
  }
  v8 = BfeCallCreate(a1, a2, 1, 1, TlsValue);
  if ( !v8 )
  {
    v10 = gBfeObjMgr;
    v11 = 408 * v7;
    v29 = 0;
    v30 = 0;
    if ( (unsigned int)v7 >= 7 || !*(_DWORD *)(gBfeObjMgr + 408 * v7) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v12 = v10 + v11;
    v13 = *a4 ^ a4[1];
    if ( !v13 )
      v13 = -1;
    NextEntryHashTable = RtlLookupEntryHashTable(v10 + v11 + 240, v13, &v29);
    v15 = "BfeObjectDeleteByKey";
    if ( NextEntryHashTable )
    {
      while ( 1 )
      {
        v18 = NextEntryHashTable - 16;
        Key = (_QWORD *)BfeObjectGetKey(NextEntryHashTable - 16);
        v20 = *Key - *a4;
        if ( *Key == *a4 )
          v20 = Key[1] - a4[1];
        if ( !v20 )
        {
          if ( !v18 || !*(_QWORD *)v18 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          if ( (*(_BYTE *)(v18 + 8) & 8) == 0 )
            break;
        }
        NextEntryHashTable = RtlGetNextEntryHashTable(v12 + 240, &v29);
        if ( !NextEntryHashTable )
          goto LABEL_30;
      }
      if ( !v18 || !*(_QWORD *)v18 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      if ( !v18 )
      {
LABEL_30:
        v15 = "BfeObjectDeleteByKey";
        goto LABEL_16;
      }
      v21 = BfeObjectDelete(v18);
      v16 = WPP_GLOBAL_Control;
      v17 = "BfeObjectDeleteByKey";
      v8 = v21;
    }
    else
    {
LABEL_16:
      LODWORD(v8) = *(_DWORD *)(v11 + gBfeObjMgr + 72);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_SsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          (unsigned int)"BfeObjectDeleteByKey",
          0,
          (__int64)"BfeObjectDeleteByKey",
          *(_DWORD *)(v11 + gBfeObjMgr + 72));
        v16 = WPP_GLOBAL_Control;
      }
      v17 = "BfeObjectDeleteByKey";
      if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
      {
        v27 = v8;
        v32 = &v27;
        v30 = "BfeObjectDeleteByKey";
        v31 = 21;
        v33 = 4;
        McGenEventWrite_EtwEventWriteTransfer(
          (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
          (unsigned int)WFP_USERMODE_ERROR,
          (_DWORD)v15,
          3,
          (__int64)&v29);
        v16 = WPP_GLOBAL_Control;
      }
      if ( (int)v8 > 0 )
        LODWORD(v8) = (unsigned __int16)v8 | 0x80070000;
      v8 = (int)v8;
    }
    if ( v8 )
    {
      if ( v16 != &WPP_GLOBAL_Control && *((_BYTE *)v16 + 25) >= 2u && (*((_BYTE *)v16 + 28) & 1) != 0 )
        WPP_SF_Ssd(v16[2], 26, (_DWORD)v15, 0, (__int64)"BfeObjectDeleteByKey", v8);
      if ( !gWfpLogUserModeErrors || (byte_1800F6115 & 1) == 0 )
        goto LABEL_4;
      v31 = 21;
    }
    else
    {
      if ( *(_QWORD *)&TlsValue[0] )
      {
        v8 = 0;
        if ( *(_DWORD *)(*(_QWORD *)&TlsValue[0] + 36LL) )
          goto LABEL_4;
      }
      v22 = BfeTxnCommit(*((_QWORD *)&TlsValue[0] + 1), 0, v15);
      v8 = v22;
      *((_QWORD *)&TlsValue[0] + 1) = 0;
      if ( !v22 )
        goto LABEL_4;
      v17 = "BfeCallCommitEx";
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, (_DWORD)v15, 0, (__int64)"BfeCallCommitEx", v22);
      }
      if ( !gWfpLogUserModeErrors || (byte_1800F6115 & 1) == 0 )
        goto LABEL_4;
      v31 = 16;
    }
    v27 = v8;
    v32 = &v27;
    v30 = v17;
    v33 = 4;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
      (unsigned int)WFP_USERMODE_ERROR,
      (_DWORD)v15,
      3,
      (__int64)&v29);
  }
LABEL_4:
  BfeCallDestroy(TlsValue);
  if ( a1 )
  {
    if ( v8 )
    {
      if ( !(unsigned int)BfeRpcIsKernelModeCaller() )
      {
        v23 = (unsigned __int16)v8;
        if ( (v8 & 0x1FFF0000) != 0x70000 )
          v23 = v8;
        RpcRaiseException(v23);
      }
      v24 = WfpErrorToNtStatus(v8);
      RpcRaiseException(v24);
    }
    return 0;
  }
  else
  {
    result = (unsigned __int16)v8;
    if ( (v8 & 0x1FFF0000) != 0x70000 )
      return (unsigned int)v8;
  }
  return result;
}

```

## disassembly

```asm
0x180009780  mov     r11, rsp
0x180009783  push    rbp
0x180009784  push    rbx
0x180009785  lea     rbp, [r11-5Fh]
0x180009789  sub     rsp, 0C8h
0x180009790  mov     rax, cs:__security_cookie
0x180009797  xor     rax, rsp
0x18000979a  mov     [rbp+57h+var_48], rax
0x18000979e  mov     [r11-18h], rsi
0x1800097a2  xorps   xmm0, xmm0
0x1800097a5  mov     [r11-20h], rdi
0x1800097a9  mov     rsi, rcx
0x1800097ac  mov     [r11-28h], r12
0x1800097b0  mov     rdi, rdx
0x1800097b3  mov     [r11-38h], r14
0x1800097b7  mov     [r11-40h], r15
0x1800097bb  mov     r15, r9
0x1800097be  movsxd  r14, r8d
0x1800097c1  movups  [rbp+57h+TlsValue], xmm0
0x1800097c5  movups  [rbp+57h+var_88], xmm0
0x1800097c9  mov     rbx, cs:WPP_GLOBAL_Control
0x1800097d0  lea     r12, WPP_GLOBAL_Control
0x1800097d7  cmp     rbx, r12
0x1800097da  jz      short loc_1800097E6
0x1800097dc  cmp     byte ptr [rbx+19h], 4
0x1800097e0  jnb     loc_180009BB0
0x1800097e6  mov     r9d, 1; int
0x1800097ec  lea     rax, [rbp+57h+TlsValue]
0x1800097f0  mov     r8d, r9d; int
0x1800097f3  mov     [rsp+0D0h+lpTlsValue], rax; lpTlsValue
0x1800097f8  mov     rdx, rdi; int
0x1800097fb  call    BfeCallCreate
0x180009800  mov     rbx, rax
0x180009803  test    rax, rax
0x180009806  jz      short loc_180009876
0x180009808  lea     rcx, [rbp+57h+TlsValue]
0x18000980c  call    BfeCallDestroy
0x180009811  mov     r15, [rsp+0D0h+var_38]
0x180009819  test    rsi, rsi
0x18000981c  mov     rsi, [rsp+0C0h]
0x180009824  mov     r14, [rsp+0D0h+var_30]
0x18000982c  mov     r12, [rsp+0D0h+var_20]
0x180009834  mov     rdi, [rsp+0D0h+var_18]
0x18000983c  jnz     short loc_180009869
0x18000983e  mov     ecx, ebx
0x180009840  movzx   eax, bx
0x180009843  and     ecx, 1FFF0000h
0x180009849  cmp     ecx, 70000h
0x18000984f  cmovnz  eax, ebx
0x180009852  mov     rcx, [rbp+57h+var_48]
0x180009856  xor     rcx, rsp; StackCookie
0x180009859  call    __security_check_cookie
0x18000985e  add     rsp, 0C8h
0x180009865  pop     rbx
0x180009866  pop     rbp
0x180009867  retn
0x180009869  test    rbx, rbx
0x18000986c  jnz     loc_180009A86
0x180009872  xor     eax, eax
0x180009874  jmp     short loc_180009852
0x180009876  mov     rbx, cs:gBfeObjMgr
0x18000987d  xor     eax, eax
0x18000987f  imul    rdi, r14, 198h
0x180009886  xorps   xmm0, xmm0
0x180009889  movups  [rbp+57h+var_78], xmm0
0x18000988d  mov     [rsp+0D0h+var_28], r13
0x180009895  mov     [rbp+57h+var_68], rax
0x180009899  cmp     r14d, 7
0x18000989d  jnb     short loc_1800098A4
0x18000989f  cmp     [rbx+rdi], eax
0x1800098a2  jnz     short loc_1800098A9
0x1800098a4  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "BfeObjectTypeIdIsValid(typeId)")
0x1800098a9  mov     rdx, [r15+8]
0x1800098ad  lea     r14, [rbx+rdi]
0x1800098b1  xor     rdx, [r15]
0x1800098b4  lea     r8, [rbp+57h+var_78]
0x1800098b8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800098bf  lea     rcx, [r14+0F0h]
0x1800098c6  cmovz   rdx, rax
0x1800098ca  call    cs:__imp_RtlLookupEntryHashTable
0x1800098d1  nop     dword ptr [rax+rax+00h]
0x1800098d6  xor     r13d, r13d
0x1800098d9  lea     r8, aBfeobjectdelet_1; "BfeObjectDeleteByKey"
0x1800098e0  test    rax, rax
0x1800098e3  jnz     short loc_180009930
0x1800098e5  mov     rax, cs:gBfeObjMgr
0x1800098ec  mov     ebx, [rdi+rax+48h]
0x1800098f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800098f7  cmp     rcx, r12
0x1800098fa  jz      short loc_180009906
0x1800098fc  cmp     byte ptr [rcx+19h], 2
0x180009900  jnb     loc_180009B01
0x180009906  cmp     cs:gWfpLogUserModeErrors, r13d
0x18000990d  lea     rdi, aBfeobjectdelet_1; "BfeObjectDeleteByKey"
0x180009914  jnz     loc_180009B31
0x18000991a  test    ebx, ebx
0x18000991c  jg      loc_180009B8B
0x180009922  movsxd  rbx, ebx
0x180009925  jmp     loc_1800099BB
0x180009930  lea     rbx, [rax-10h]
0x180009934  mov     rcx, rbx
0x180009937  call    BfeObjectGetKey
0x18000993c  mov     rcx, [rax]
0x18000993f  sub     rcx, [r15]
0x180009942  jnz     short loc_18000994C
0x180009944  mov     rcx, [rax+8]
0x180009948  sub     rcx, [r15+8]
0x18000994c  test    rcx, rcx
0x18000994f  jnz     short loc_180009966
0x180009951  test    rbx, rbx
0x180009954  jz      short loc_18000995B
0x180009956  cmp     [rbx], r13
0x180009959  jnz     short loc_180009960
0x18000995b  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "BfeObjectIsValid(obj)")
0x180009960  test    byte ptr [rbx+8], 8
0x180009964  jz      short loc_18000998E
0x180009966  lea     rdx, [rbp+57h+var_78]
0x18000996a  lea     rcx, [r14+0F0h]
0x180009971  call    cs:__imp_RtlGetNextEntryHashTable
0x180009978  nop     dword ptr [rax+rax+00h]
0x18000997d  test    rax, rax
0x180009980  jnz     short loc_180009930
0x180009982  lea     r8, aBfeobjectdelet_1; "BfeObjectDeleteByKey"
0x180009989  jmp     loc_1800098E5
0x18000998e  test    rbx, rbx
0x180009991  jz      short loc_180009998
0x180009993  cmp     [rbx], r13
0x180009996  jnz     short loc_18000999D
0x180009998  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "BfeObjectIsValid(obj)")
0x18000999d  test    rbx, rbx
0x1800099a0  jz      short loc_180009982
0x1800099a2  mov     rcx, rbx
0x1800099a5  call    BfeObjectDelete
0x1800099aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099b1  lea     rdi, aBfeobjectdelet_1; "BfeObjectDeleteByKey"
0x1800099b8  mov     rbx, rax
0x1800099bb  test    rbx, rbx
0x1800099be  jz      short loc_180009A0E
0x1800099c0  cmp     rcx, r12
0x1800099c3  jz      short loc_1800099EB
0x1800099c5  cmp     byte ptr [rcx+19h], 2
0x1800099c9  jb      short loc_1800099EB
0x1800099cb  test    byte ptr [rcx+1Ch], 1
0x1800099cf  jz      short loc_1800099EB
0x1800099d1  mov     rcx, [rcx+10h]
0x1800099d5  mov     edx, 1Ah
0x1800099da  mov     [rsp+28h], ebx
0x1800099de  xor     r9d, r9d
0x1800099e1  mov     [rsp+0D0h+lpTlsValue], rdi
0x1800099e6  call    WPP_SF_Ssd
0x1800099eb  cmp     cs:gWfpLogUserModeErrors, r13d
0x1800099f2  jz      loc_180009A79
0x1800099f8  test    cs:byte_1800F6115, 1
0x1800099ff  jz      short loc_180009A79
0x180009a01  mov     [rbp+57h+var_60], 15h
0x180009a09  jmp     loc_180009AC3
0x180009a0e  mov     rax, qword ptr [rbp+57h+TlsValue]
0x180009a12  test    rax, rax
0x180009a15  jz      short loc_180009A20
0x180009a17  mov     rbx, r13
0x180009a1a  cmp     [rax+24h], r13d
0x180009a1e  jnz     short loc_180009A79
0x180009a20  mov     rcx, qword ptr [rbp+57h+TlsValue+8]
0x180009a24  xor     edx, edx
0x180009a26  call    BfeTxnCommit
0x180009a2b  mov     rbx, rax
0x180009a2e  mov     qword ptr [rbp+57h+TlsValue+8], r13
0x180009a32  test    rax, rax
0x180009a35  jz      short loc_180009A79
0x180009a37  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a3e  lea     rdi, aBfecallcommite; "BfeCallCommitEx"
0x180009a45  cmp     rcx, r12
0x180009a48  jz      short loc_180009A70
0x180009a4a  cmp     byte ptr [rcx+19h], 2
0x180009a4e  jb      short loc_180009A70
0x180009a50  test    byte ptr [rcx+1Ch], 1
0x180009a54  jz      short loc_180009A70
0x180009a56  mov     rcx, [rcx+10h]
0x180009a5a  mov     edx, 1Ah
0x180009a5f  mov     [rsp+28h], ebx
0x180009a63  xor     r9d, r9d
0x180009a66  mov     [rsp+0D0h+lpTlsValue], rdi
0x180009a6b  call    WPP_SF_Ssd
0x180009a70  cmp     cs:gWfpLogUserModeErrors, r13d
0x180009a77  jnz     short loc_180009AB2
0x180009a79  mov     r13, [rsp+0D0h+var_28]
0x180009a81  jmp     loc_180009808
0x180009a86  call    BfeRpcIsKernelModeCaller
0x180009a8b  test    eax, eax
0x180009a8d  jnz     loc_180009B99
0x180009a93  mov     eax, ebx
0x180009a95  movzx   ecx, bx
0x180009a98  and     eax, 1FFF0000h
0x180009a9d  cmp     eax, 70000h
0x180009aa2  cmovnz  ecx, ebx; exception
0x180009aa5  call    cs:__imp_RpcRaiseException
0x180009aac  nop     dword ptr [rax+rax+00h]
0x180009ab1  int     3; Trap to Debugger
0x180009ab2  test    cs:byte_1800F6115, 1
0x180009ab9  jz      short loc_180009A79
0x180009abb  mov     [rbp+57h+var_60], 10h
0x180009ac3  lea     rax, [rbp+57h+var_A0]
0x180009ac7  mov     [rbp+57h+var_A0], ebx
0x180009aca  mov     [rbp+57h+var_58], rax
0x180009ace  lea     rdx, WFP_USERMODE_ERROR
0x180009ad5  lea     rax, [rbp+57h+var_78]
0x180009ad9  mov     [rbp+57h+var_68], rdi
0x180009add  mov     r9d, 3
0x180009ae3  mov     [rsp+0D0h+lpTlsValue], rax
0x180009ae8  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180009aef  mov     [rbp+57h+var_50], 4
0x180009af7  call    McGenEventWrite_EtwEventWriteTransfer
0x180009afc  jmp     loc_180009A79
0x180009b01  test    byte ptr [rcx+1Ch], 1
0x180009b05  jz      loc_180009906
0x180009b0b  mov     rcx, [rcx+10h]
0x180009b0f  mov     edx, 17h
0x180009b14  mov     [rsp+28h], ebx
0x180009b18  xor     r9d, r9d
0x180009b1b  mov     [rsp+0D0h+lpTlsValue], r8
0x180009b20  call    WPP_SF_SsD
0x180009b25  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b2c  jmp     loc_180009906
0x180009b31  test    cs:byte_1800F6115, 1
0x180009b38  jz      loc_18000991A
0x180009b3e  lea     rax, [rbp+57h+var_A0]
0x180009b42  mov     [rbp+57h+var_A0], ebx
0x180009b45  mov     [rbp+57h+var_58], rax
0x180009b49  lea     rdx, WFP_USERMODE_ERROR
0x180009b50  lea     rax, [rbp+57h+var_78]
0x180009b54  mov     [rbp+57h+var_68], rdi
0x180009b58  mov     r9d, 3
0x180009b5e  mov     [rsp+0D0h+lpTlsValue], rax
0x180009b63  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180009b6a  mov     [rbp+57h+var_60], 15h
0x180009b72  mov     [rbp+57h+var_50], 4
0x180009b7a  call    McGenEventWrite_EtwEventWriteTransfer
0x180009b7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b86  jmp     loc_18000991A
0x180009b8b  movzx   ebx, bx
0x180009b8e  or      ebx, 80070000h
0x180009b94  jmp     loc_180009922
0x180009b99  mov     rcx, rbx
0x180009b9c  call    WfpErrorToNtStatus
0x180009ba1  mov     ecx, eax; exception
0x180009ba3  call    cs:__imp_RpcRaiseException
0x180009baa  nop     dword ptr [rax+rax+00h]
0x180009baf  int     3; Trap to Debugger
0x180009bb0  test    byte ptr [rbx+1Ch], 2
0x180009bb4  jz      loc_1800097E6
0x180009bba  mov     rbx, [rbx+10h]
0x180009bbe  mov     ecx, r14d
0x180009bc1  call    BfeObjectTypeIdToString
0x180009bc6  mov     r9, rax
0x180009bc9  mov     [rsp+0D0h+lpTlsValue], r15
0x180009bce  mov     edx, 0Dh
0x180009bd3  lea     r8, WPP_58c1eeaf0b3d34d2a0a5eb62f8ccddc7_Traceguids
0x180009bda  mov     rcx, rbx
0x180009bdd  call    WPP_SF_S_guid_
0x180009be2  jmp     loc_1800097E6
```
