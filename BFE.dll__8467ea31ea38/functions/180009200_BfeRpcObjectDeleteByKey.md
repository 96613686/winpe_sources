# BfeRpcObjectDeleteByKey

- ea: `0x180009200`
- end: `0x180009645`
- name: `BfeRpcObjectDeleteByKey`
- size: `1093`
- prototype: ``
- caller_count: `5`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003c0c0`
- `0x180042ef0`
- `0x180048cc0`
- `0x180049060`
- `0x1800609a0`

## callees

- `0x1800052ac`
- `0x180007460`
- `0x180008930`
- `0x180009200`
- `0x180009aa0`
- `0x18000ad28`
- `0x18000ba68`
- `0x18000f1a8`
- `0x180010ad0`
- `0x180012950`
- `0x1800223a8`
- `0x180023e78`
- `0x180049238`
- `0x1800575c4`
- `0x180058b30`

## import_xrefs

- `ntdll!RtlLookupEntryHashTable` at `0x180009349`
- `ntdll!RtlLookupEntryHashTable` at `0x180009349`
- `ntdll!RtlGetNextEntryHashTable` at `0x1800093e4`
- `ntdll!RtlGetNextEntryHashTable` at `0x1800093e4`
- `RPCRT4!RpcRaiseException` at `0x180009512`
- `RPCRT4!RpcRaiseException` at `0x180009607`
- `RPCRT4!RpcRaiseException` at `0x180009512`
- `RPCRT4!RpcRaiseException` at `0x180009607`

## string_xrefs

- `0x180009352`: `BfeObjectDeleteByKey`
- `0x180009386`: `BfeObjectDeleteByKey`
- `0x1800093ef`: `BfeObjectDeleteByKey`
- `0x18000941e`: `BfeObjectDeleteByKey`
- `0x1800094ab`: `BfeCallCommitEx`

## pseudocode

```c
__int64 __fastcall BfeRpcObjectDeleteByKey(__int64 a1, __int64 a2, unsigned int a3, _QWORD *a4)
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
      if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
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
      if ( !gWfpLogUserModeErrors || (byte_1800F30F5 & 1) == 0 )
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
      v22 = BfeTxnCommit(*((_QWORD *)&TlsValue[0] + 1), 0);
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
      if ( !gWfpLogUserModeErrors || (byte_1800F30F5 & 1) == 0 )
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
  BfeCallDestroy((__int64 *)TlsValue);
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
0x180009200  mov     r11, rsp
0x180009203  push    rbp
0x180009204  push    rbx
0x180009205  lea     rbp, [r11-5Fh]
0x180009209  sub     rsp, 0C8h
0x180009210  mov     rax, cs:__security_cookie
0x180009217  xor     rax, rsp
0x18000921a  mov     [rbp+57h+var_48], rax
0x18000921e  mov     [r11-18h], rsi
0x180009222  xorps   xmm0, xmm0
0x180009225  mov     [r11-20h], rdi
0x180009229  mov     rsi, rcx
0x18000922c  mov     [r11-28h], r12
0x180009230  mov     rdi, rdx
0x180009233  mov     [r11-38h], r14
0x180009237  mov     [r11-40h], r15
0x18000923b  mov     r15, r9
0x18000923e  movsxd  r14, r8d
0x180009241  movups  [rbp+57h+TlsValue], xmm0
0x180009245  movups  [rbp+57h+var_88], xmm0
0x180009249  mov     rbx, cs:WPP_GLOBAL_Control
0x180009250  lea     r12, WPP_GLOBAL_Control
0x180009257  cmp     rbx, r12
0x18000925a  jz      short loc_180009266
0x18000925c  cmp     byte ptr [rbx+19h], 4
0x180009260  jnb     loc_18000960E
0x180009266  mov     r9d, 1; int
0x18000926c  lea     rax, [rbp+57h+TlsValue]
0x180009270  mov     r8d, r9d; int
0x180009273  mov     [rsp+0D0h+lpTlsValue], rax; lpTlsValue
0x180009278  mov     rdx, rdi; int
0x18000927b  call    BfeCallCreate
0x180009280  mov     rbx, rax
0x180009283  test    rax, rax
0x180009286  jz      short loc_1800092F5
0x180009288  lea     rcx, [rbp+57h+TlsValue]
0x18000928c  call    BfeCallDestroy
0x180009291  mov     r15, [rsp+0D0h+var_38]
0x180009299  test    rsi, rsi
0x18000929c  mov     rsi, [rsp+0C0h]
0x1800092a4  mov     r14, [rsp+0D0h+var_30]
0x1800092ac  mov     r12, [rsp+0D0h+var_20]
0x1800092b4  mov     rdi, [rsp+0D0h+var_18]
0x1800092bc  jnz     short loc_1800092E8
0x1800092be  mov     ecx, ebx
0x1800092c0  movzx   eax, bx
0x1800092c3  and     ecx, 1FFF0000h
0x1800092c9  cmp     ecx, 70000h
0x1800092cf  cmovnz  eax, ebx
0x1800092d2  mov     rcx, [rbp+57h+var_48]
0x1800092d6  xor     rcx, rsp; StackCookie
0x1800092d9  call    __security_check_cookie
0x1800092de  add     rsp, 0C8h
0x1800092e5  pop     rbx
0x1800092e6  pop     rbp
0x1800092e7  retn
0x1800092e8  test    rbx, rbx
0x1800092eb  jnz     loc_1800094F3
0x1800092f1  xor     eax, eax
0x1800092f3  jmp     short loc_1800092D2
0x1800092f5  mov     rbx, cs:gBfeObjMgr
0x1800092fc  xor     eax, eax
0x1800092fe  imul    rdi, r14, 198h
0x180009305  xorps   xmm0, xmm0
0x180009308  movups  [rbp+57h+var_78], xmm0
0x18000930c  mov     [rsp+0D0h+var_28], r13
0x180009314  mov     [rbp+57h+var_68], rax
0x180009318  cmp     r14d, 7
0x18000931c  jnb     short loc_180009323
0x18000931e  cmp     [rbx+rdi], eax
0x180009321  jnz     short loc_180009328
0x180009323  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180009328  mov     rdx, [r15+8]
0x18000932c  lea     r14, [rbx+rdi]
0x180009330  xor     rdx, [r15]
0x180009333  lea     r8, [rbp+57h+var_78]
0x180009337  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000933e  lea     rcx, [r14+0F0h]
0x180009345  cmovz   rdx, rax
0x180009349  call    cs:__imp_RtlLookupEntryHashTable
0x18000934f  xor     r13d, r13d
0x180009352  lea     r8, aBfeobjectdelet_1; "BfeObjectDeleteByKey"
0x180009359  test    rax, rax
0x18000935c  jnz     short loc_1800093A3
0x18000935e  mov     rax, cs:gBfeObjMgr
0x180009365  mov     ebx, [rdi+rax+48h]
0x180009369  mov     rcx, cs:WPP_GLOBAL_Control
0x180009370  cmp     rcx, r12
0x180009373  jz      short loc_18000937F
0x180009375  cmp     byte ptr [rcx+19h], 2
0x180009379  jnb     loc_180009565
0x18000937f  cmp     cs:gWfpLogUserModeErrors, r13d
0x180009386  lea     rdi, aBfeobjectdelet_1; "BfeObjectDeleteByKey"
0x18000938d  jnz     loc_180009595
0x180009393  test    ebx, ebx
0x180009395  jg      loc_1800095EF
0x18000939b  movsxd  rbx, ebx
0x18000939e  jmp     loc_180009428
0x1800093a3  lea     rbx, [rax-10h]
0x1800093a7  mov     rcx, rbx
0x1800093aa  call    BfeObjectGetKey
0x1800093af  mov     rcx, [rax]
0x1800093b2  sub     rcx, [r15]
0x1800093b5  jnz     short loc_1800093BF
0x1800093b7  mov     rcx, [rax+8]
0x1800093bb  sub     rcx, [r15+8]
0x1800093bf  test    rcx, rcx
0x1800093c2  jnz     short loc_1800093D9
0x1800093c4  test    rbx, rbx
0x1800093c7  jz      short loc_1800093CE
0x1800093c9  cmp     [rbx], r13
0x1800093cc  jnz     short loc_1800093D3
0x1800093ce  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800093d3  test    byte ptr [rbx+8], 8
0x1800093d7  jz      short loc_1800093FB
0x1800093d9  lea     rdx, [rbp+57h+var_78]
0x1800093dd  lea     rcx, [r14+0F0h]
0x1800093e4  call    cs:__imp_RtlGetNextEntryHashTable
0x1800093ea  test    rax, rax
0x1800093ed  jnz     short loc_1800093A3
0x1800093ef  lea     r8, aBfeobjectdelet_1; "BfeObjectDeleteByKey"
0x1800093f6  jmp     loc_18000935E
0x1800093fb  test    rbx, rbx
0x1800093fe  jz      short loc_180009405
0x180009400  cmp     [rbx], r13
0x180009403  jnz     short loc_18000940A
0x180009405  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000940a  test    rbx, rbx
0x18000940d  jz      short loc_1800093EF
0x18000940f  mov     rcx, rbx
0x180009412  call    BfeObjectDelete
0x180009417  mov     rcx, cs:WPP_GLOBAL_Control
0x18000941e  lea     rdi, aBfeobjectdelet_1; "BfeObjectDeleteByKey"
0x180009425  mov     rbx, rax
0x180009428  test    rbx, rbx
0x18000942b  jz      short loc_18000947B
0x18000942d  cmp     rcx, r12
0x180009430  jz      short loc_180009458
0x180009432  cmp     byte ptr [rcx+19h], 2
0x180009436  jb      short loc_180009458
0x180009438  test    byte ptr [rcx+1Ch], 1
0x18000943c  jz      short loc_180009458
0x18000943e  mov     rcx, [rcx+10h]
0x180009442  mov     edx, 1Ah
0x180009447  mov     [rsp+28h], ebx
0x18000944b  xor     r9d, r9d
0x18000944e  mov     [rsp+0D0h+lpTlsValue], rdi
0x180009453  call    WPP_SF_Ssd
0x180009458  cmp     cs:gWfpLogUserModeErrors, r13d
0x18000945f  jz      loc_1800094E6
0x180009465  test    cs:byte_1800F30F5, 1
0x18000946c  jz      short loc_1800094E6
0x18000946e  mov     [rbp+57h+var_60], 15h
0x180009476  jmp     loc_18000952A
0x18000947b  mov     rax, qword ptr [rbp+57h+TlsValue]
0x18000947f  test    rax, rax
0x180009482  jz      short loc_18000948D
0x180009484  mov     rbx, r13
0x180009487  cmp     [rax+24h], r13d
0x18000948b  jnz     short loc_1800094E6
0x18000948d  mov     rcx, qword ptr [rbp+57h+TlsValue+8]
0x180009491  xor     edx, edx
0x180009493  call    BfeTxnCommit
0x180009498  mov     rbx, rax
0x18000949b  mov     qword ptr [rbp+57h+TlsValue+8], r13
0x18000949f  test    rax, rax
0x1800094a2  jz      short loc_1800094E6
0x1800094a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094ab  lea     rdi, aBfecallcommite; "BfeCallCommitEx"
0x1800094b2  cmp     rcx, r12
0x1800094b5  jz      short loc_1800094DD
0x1800094b7  cmp     byte ptr [rcx+19h], 2
0x1800094bb  jb      short loc_1800094DD
0x1800094bd  test    byte ptr [rcx+1Ch], 1
0x1800094c1  jz      short loc_1800094DD
0x1800094c3  mov     rcx, [rcx+10h]
0x1800094c7  mov     edx, 1Ah
0x1800094cc  mov     [rsp+28h], ebx
0x1800094d0  xor     r9d, r9d
0x1800094d3  mov     [rsp+0D0h+lpTlsValue], rdi
0x1800094d8  call    WPP_SF_Ssd
0x1800094dd  cmp     cs:gWfpLogUserModeErrors, r13d
0x1800094e4  jnz     short loc_180009519
0x1800094e6  mov     r13, [rsp+0D0h+var_28]
0x1800094ee  jmp     loc_180009288
0x1800094f3  call    BfeRpcIsKernelModeCaller
0x1800094f8  test    eax, eax
0x1800094fa  jnz     loc_1800095FD
0x180009500  mov     eax, ebx
0x180009502  movzx   ecx, bx
0x180009505  and     eax, 1FFF0000h
0x18000950a  cmp     eax, 70000h
0x18000950f  cmovnz  ecx, ebx; exception
0x180009512  call    cs:__imp_RpcRaiseException
0x180009518  int     3; Trap to Debugger
0x180009519  test    cs:byte_1800F30F5, 1
0x180009520  jz      short loc_1800094E6
0x180009522  mov     [rbp+57h+var_60], 10h
0x18000952a  lea     rax, [rbp+57h+var_A0]
0x18000952e  mov     [rbp+57h+var_A0], ebx
0x180009531  mov     [rbp+57h+var_58], rax
0x180009535  lea     rdx, WFP_USERMODE_ERROR
0x18000953c  lea     rax, [rbp+57h+var_78]
0x180009540  mov     [rbp+57h+var_68], rdi
0x180009544  mov     r9d, 3
0x18000954a  mov     [rsp+0D0h+lpTlsValue], rax
0x18000954f  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180009556  mov     [rbp+57h+var_50], 4
0x18000955e  call    McGenEventWrite_EtwEventWriteTransfer
0x180009563  jmp     short loc_1800094E6
0x180009565  test    byte ptr [rcx+1Ch], 1
0x180009569  jz      loc_18000937F
0x18000956f  mov     rcx, [rcx+10h]
0x180009573  mov     edx, 17h
0x180009578  mov     [rsp+28h], ebx
0x18000957c  xor     r9d, r9d
0x18000957f  mov     [rsp+0D0h+lpTlsValue], r8
0x180009584  call    WPP_SF_SsD
0x180009589  mov     rcx, cs:WPP_GLOBAL_Control
0x180009590  jmp     loc_18000937F
0x180009595  test    cs:byte_1800F30F5, 1
0x18000959c  jz      loc_180009393
0x1800095a2  lea     rax, [rbp+57h+var_A0]
0x1800095a6  mov     [rbp+57h+var_A0], ebx
0x1800095a9  mov     [rbp+57h+var_58], rax
0x1800095ad  lea     rdx, WFP_USERMODE_ERROR
0x1800095b4  lea     rax, [rbp+57h+var_78]
0x1800095b8  mov     [rbp+57h+var_68], rdi
0x1800095bc  mov     r9d, 3
0x1800095c2  mov     [rsp+0D0h+lpTlsValue], rax
0x1800095c7  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x1800095ce  mov     [rbp+57h+var_60], 15h
0x1800095d6  mov     [rbp+57h+var_50], 4
0x1800095de  call    McGenEventWrite_EtwEventWriteTransfer
0x1800095e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800095ea  jmp     loc_180009393
0x1800095ef  movzx   ebx, bx
0x1800095f2  or      ebx, 80070000h
0x1800095f8  jmp     loc_18000939B
0x1800095fd  mov     rcx, rbx
0x180009600  call    WfpErrorToNtStatus
0x180009605  mov     ecx, eax; exception
0x180009607  call    cs:__imp_RpcRaiseException
0x18000960d  int     3; Trap to Debugger
0x18000960e  test    byte ptr [rbx+1Ch], 2
0x180009612  jz      loc_180009266
0x180009618  mov     rbx, [rbx+10h]
0x18000961c  mov     ecx, r14d
0x18000961f  call    BfeObjectTypeIdToString
0x180009624  mov     r9, rax
0x180009627  mov     [rsp+0D0h+lpTlsValue], r15
0x18000962c  mov     edx, 0Dh
0x180009631  lea     r8, WPP_58c1eeaf0b3d34d2a0a5eb62f8ccddc7_Traceguids
0x180009638  mov     rcx, rbx
0x18000963b  call    WPP_SF_S_guid_
0x180009640  jmp     loc_180009266
```
