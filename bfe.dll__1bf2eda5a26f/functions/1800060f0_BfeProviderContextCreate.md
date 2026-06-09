# BfeProviderContextCreate

- ea: `0x1800060f0`
- end: `0x180006515`
- name: `BfeProviderContextCreate`
- size: `1061`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800060a8`
- `0x1800060f0`
- `0x180007460`
- `0x180007790`
- `0x18000d6d0`
- `0x18000f1a8`
- `0x180010360`
- `0x18001236c`
- `0x180012950`
- `0x180018b74`
- `0x180026c50`
- `0x1800575c4`
- `0x180058b30`
- `0x180072e38`

## import_xrefs

- `ntdll!RtlLookupEntryHashTable` at `0x180006204`
- `ntdll!RtlLookupEntryHashTable` at `0x180006204`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000630d`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000630d`

## string_xrefs

- `0x180006168`: `BfeProviderContextCreate`
- `0x18000642d`: `BfeProviderContextCreate`
- `0x1800064c6`: `BfeProviderContextCreate`
- `0x1800064b7`: `BfeObjectTypeAccessCheck`

## pseudocode

```c
__int64 __fastcall BfeProviderContextCreate(_DWORD *a1, _QWORD *a2)
{
  bool v2; // zf
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rbx
  _QWORD *v8; // rsi
  __int64 v9; // rbx
  __int64 v10; // r13
  __int64 v11; // rdx
  __int64 NextEntryHashTable; // rax
  const char *v13; // r8
  __int64 v15; // rbx
  _QWORD *Key; // rax
  __int64 v17; // rcx
  __int64 v18; // r8
  unsigned int i; // edx
  int v20; // [rsp+30h] [rbp-48h] BYREF
  __int128 v21; // [rsp+38h] [rbp-40h] BYREF
  const char *v22; // [rsp+48h] [rbp-30h]
  __int64 v23; // [rsp+50h] [rbp-28h]
  int *v24; // [rsp+58h] [rbp-20h]
  __int64 v25; // [rsp+60h] [rbp-18h]

  v2 = LODWORD(qword_1800F2668[43]) == 0;
  *(_QWORD *)a1 = *a2;
  *a2 = 0;
  v20 = 0;
  if ( v2 && *(_DWORD *)(*(_QWORD *)a1 + 64LL) == 5 )
  {
    v18 = *(_QWORD *)(*(_QWORD *)a1 + 72LL);
    for ( i = 0; i < *(_DWORD *)(v18 + 4); ++i )
    {
      if ( *(_DWORD *)(*(_QWORD *)(v18 + 8) + 80LL * i) == 6 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_SsD(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v18, 0, (__int64)"BfeProviderContextCreate", 50);
        }
        if ( MEMORY[0x1800EF078] && (qword_1800F2668[337] & 0x10000000000LL) != 0 )
        {
          v20 = 50;
          v24 = &v20;
          v22 = "BfeProviderContextCreate";
          v23 = 25;
          v25 = 4;
          McGenEventWrite_EtwEventWriteTransfer(
            &MICROSOFT_WFP_PROVIDER_Context,
            (__int64)WFP_USERMODE_ERROR,
            v18,
            3,
            (__int64)&v21);
        }
        v7 = -2147024846;
        goto LABEL_51;
      }
    }
  }
  v4 = *(_QWORD *)&MEMORY[0x1800EF094][7];
  if ( !*(_DWORD *)(*(_QWORD *)&MEMORY[0x1800EF094][7] + 2040LL) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v5 = BfeAccessCheck(*(char **)(v4 + 2384), 1u, &v20);
  v7 = v5;
  if ( v5 )
  {
    WfpReportError(v5, "BfeObjectTypeAccessCheck");
    goto LABEL_51;
  }
  if ( !v20 )
  {
    if ( HIDWORD(qword_1800F2668[43]) >= 0xC350 )
    {
      v7 = WfpReportSysErrorAsWinError(v6, "BfeProviderContextCreate", 50);
      goto LABEL_28;
    }
    v7 = BfeValidateLowPrivilegeProvCtxt(a1);
    if ( v7 )
      goto LABEL_51;
    ++HIDWORD(qword_1800F2668[43]);
    a1[2] = 1;
  }
  *(_QWORD *)(*(_QWORD *)a1 + 80LL) = qword_1800EB3D8;
  if ( (*(_BYTE *)(*(_QWORD *)a1 + 32LL) & 1) != 0 )
    BfeObjectSetPersistent(a1);
  v8 = *(_QWORD **)(*(_QWORD *)a1 + 40LL);
  if ( v8 )
  {
    if ( a1 == (_DWORD *)144 || !*((_QWORD *)a1 - 18) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v9 = *(_QWORD *)&MEMORY[0x1800EF094][7];
    v22 = 0;
    v21 = 0;
    if ( !**(_DWORD **)&MEMORY[0x1800EF094][7] )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v10 = v9 + 240;
    v11 = *v8 ^ v8[1];
    if ( !v11 )
      v11 = -1;
    NextEntryHashTable = RtlLookupEntryHashTable(v9 + 240, v11, &v21);
    v13 = "BfeObjectAssociateByKey";
    if ( NextEntryHashTable )
    {
      while ( 1 )
      {
        v15 = NextEntryHashTable - 16;
        Key = (_QWORD *)BfeObjectGetKey(NextEntryHashTable - 16);
        v17 = *Key - *v8;
        if ( *Key == *v8 )
          v17 = Key[1] - v8[1];
        if ( !v17 )
        {
          if ( !v15 || !*(_QWORD *)v15 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          if ( (*(_BYTE *)(v15 + 8) & 8) == 0 )
            break;
        }
        NextEntryHashTable = RtlGetNextEntryHashTable(v10, &v21);
        if ( !NextEntryHashTable )
          goto LABEL_38;
      }
      if ( !v15 || !*(_QWORD *)v15 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      if ( v15 )
      {
        v7 = BfeObjectAssociate(0, (_QWORD *)a1 - 18, (_QWORD *)v15);
        goto LABEL_26;
      }
LABEL_38:
      v13 = "BfeObjectAssociateByKey";
    }
    LODWORD(v7) = *(_DWORD *)(*(_QWORD *)&MEMORY[0x1800EF094][7] + 72LL);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_SsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        (unsigned int)"BfeObjectAssociateByKey",
        0,
        (__int64)"BfeObjectAssociateByKey",
        *(_DWORD *)(*(_QWORD *)&MEMORY[0x1800EF094][7] + 72LL));
    }
    if ( MEMORY[0x1800EF078] && (qword_1800F2668[337] & 0x10000000000LL) != 0 )
    {
      v20 = v7;
      v24 = &v20;
      v22 = "BfeObjectAssociateByKey";
      v23 = 24;
      v25 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        &MICROSOFT_WFP_PROVIDER_Context,
        (__int64)WFP_USERMODE_ERROR,
        (__int64)v13,
        3,
        (__int64)&v21);
    }
    if ( (int)v7 > 0 )
      LODWORD(v7) = (unsigned __int16)v7 | 0x80070000;
    v7 = (int)v7;
LABEL_26:
    if ( v7 )
    {
      WfpReportError(v7, "BfeObjectAssociateByKey");
      goto LABEL_51;
    }
  }
  ++qword_1800EB3D8;
LABEL_28:
  if ( v7 )
  {
LABEL_51:
    BfeObjectTraceAddFailure(1, *(_QWORD *)a1);
    BfeProviderContextDestroy(a1);
    WfpReportError(v7, "BfeProviderContextCreate");
  }
  return v7;
}

```

## disassembly

```asm
0x1800060f0  push    rbp
0x1800060f2  push    rbx
0x1800060f3  push    rsi
0x1800060f4  push    rdi
0x1800060f5  push    r12
0x1800060f7  push    r15
0x1800060f9  mov     rbp, rsp
0x1800060fc  sub     rsp, 78h
0x180006100  mov     rax, cs:__security_cookie
0x180006107  xor     rax, rsp
0x18000610a  mov     [rbp+var_10], rax
0x18000610e  mov     rax, [rdx]
0x180006111  xor     r9d, r9d
0x180006114  cmp     dword ptr cs:qword_1800F2668+158h, r9d
0x18000611b  mov     rdi, rcx
0x18000611e  mov     [rcx], rax
0x180006121  mov     [rdx], r9
0x180006124  mov     [rbp+var_48], r9d
0x180006128  jz      loc_180006324
0x18000612e  mov     rbx, cs:1800EF0B0h
0x180006135  cmp     [rbx+7F8h], r9d
0x18000613c  jnz     short loc_180006143
0x18000613e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180006143  mov     rcx, [rbx+950h]; pSecurityDescriptor
0x18000614a  lea     r8, [rbp+var_48]
0x18000614e  mov     r15d, 1
0x180006154  mov     edx, r15d
0x180006157  call    BfeAccessCheck
0x18000615c  mov     rbx, rax
0x18000615f  test    rax, rax
0x180006162  jnz     loc_1800064B7
0x180006168  lea     r12, aBfeprovidercon_1; "BfeProviderContextCreate"
0x18000616f  cmp     [rbp+var_48], eax
0x180006172  jz      loc_1800064D2
0x180006178  mov     rax, cs:qword_1800EB3D8
0x18000617f  mov     rcx, [rdi]
0x180006182  mov     [rcx+50h], rax
0x180006186  mov     rax, [rdi]
0x180006189  test    [rax+20h], r15b
0x18000618d  jnz     loc_1800064F8
0x180006193  mov     rax, [rdi]
0x180006196  mov     rsi, [rax+28h]
0x18000619a  test    rsi, rsi
0x18000619d  jz      loc_18000629D
0x1800061a3  mov     [rsp+78h+arg_10], r13
0x1800061ab  mov     [rsp+78h+var_8], r14
0x1800061b0  lea     r14, [rdi-90h]
0x1800061b7  test    r14, r14
0x1800061ba  jz      short loc_1800061C2
0x1800061bc  cmp     qword ptr [r14], 0
0x1800061c0  jnz     short loc_1800061C7
0x1800061c2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800061c7  mov     rbx, cs:1800EF0B0h
0x1800061ce  xor     eax, eax
0x1800061d0  xorps   xmm0, xmm0
0x1800061d3  mov     [rbp+var_30], rax
0x1800061d7  movups  [rbp+var_40], xmm0
0x1800061db  cmp     [rbx], eax
0x1800061dd  jnz     short loc_1800061E4
0x1800061df  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800061e4  mov     rdx, [rsi+8]
0x1800061e8  lea     r13, [rbx+0F0h]
0x1800061ef  xor     rdx, [rsi]
0x1800061f2  lea     r8, [rbp+var_40]
0x1800061f6  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800061fd  mov     rcx, r13
0x180006200  cmovz   rdx, rax
0x180006204  call    cs:__imp_RtlLookupEntryHashTable
0x18000620a  lea     r8, aBfeobjectassoc_1; "BfeObjectAssociateByKey"
0x180006211  test    rax, rax
0x180006214  jnz     loc_1800062D0
0x18000621a  mov     rax, cs:1800EF0B0h
0x180006221  mov     ebx, [rax+48h]
0x180006224  mov     rcx, cs:WPP_GLOBAL_Control
0x18000622b  lea     rax, WPP_GLOBAL_Control
0x180006232  cmp     rcx, rax
0x180006235  jz      short loc_180006241
0x180006237  cmp     byte ptr [rcx+19h], 2
0x18000623b  jnb     loc_180006355
0x180006241  cmp     dword ptr cs:1800EF078h, 0
0x180006248  lea     rsi, aBfeobjectassoc_1; "BfeObjectAssociateByKey"
0x18000624f  jnz     loc_18000637E
0x180006255  test    ebx, ebx
0x180006257  jg      loc_1800063D1
0x18000625d  movsxd  rbx, ebx
0x180006260  jmp     short loc_180006287
0x180006262  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180006267  test    rbx, rbx
0x18000626a  jz      loc_180006318
0x180006270  mov     r8, rbx
0x180006273  mov     rdx, r14
0x180006276  xor     ecx, ecx
0x180006278  call    BfeObjectAssociate
0x18000627d  mov     rbx, rax
0x180006280  lea     rsi, aBfeobjectassoc_1; "BfeObjectAssociateByKey"
0x180006287  mov     r14, [rsp+78h+var_8]
0x18000628c  mov     r13, [rsp+78h+arg_10]
0x180006294  test    rbx, rbx
0x180006297  jnz     loc_180006505
0x18000629d  inc     cs:qword_1800EB3D8
0x1800062a4  test    rbx, rbx
0x1800062a7  jnz     loc_1800063F9
0x1800062ad  mov     rax, rbx
0x1800062b0  mov     rcx, [rbp+var_10]
0x1800062b4  xor     rcx, rsp; StackCookie
0x1800062b7  call    __security_check_cookie
0x1800062bc  add     rsp, 78h
0x1800062c0  pop     r15
0x1800062c2  pop     r12
0x1800062c4  pop     rdi
0x1800062c5  pop     rsi
0x1800062c6  pop     rbx
0x1800062c7  pop     rbp
0x1800062c8  retn
0x1800062d0  lea     rbx, [rax-10h]
0x1800062d4  mov     rcx, rbx
0x1800062d7  call    BfeObjectGetKey
0x1800062dc  mov     rcx, [rax]
0x1800062df  sub     rcx, [rsi]
0x1800062e2  jnz     short loc_1800062EC
0x1800062e4  mov     rcx, [rax+8]
0x1800062e8  sub     rcx, [rsi+8]
0x1800062ec  test    rcx, rcx
0x1800062ef  jnz     short loc_180006306
0x1800062f1  test    rbx, rbx
0x1800062f4  jz      short loc_1800062FB
0x1800062f6  cmp     [rbx], rcx
0x1800062f9  jnz     short loc_180006300
0x1800062fb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180006300  test    byte ptr [rbx+8], 8
0x180006304  jz      short loc_18000633D
0x180006306  lea     rdx, [rbp+var_40]
0x18000630a  mov     rcx, r13
0x18000630d  call    cs:__imp_RtlGetNextEntryHashTable
0x180006313  test    rax, rax
0x180006316  jnz     short loc_1800062D0
0x180006318  lea     r8, aBfeobjectassoc_1; "BfeObjectAssociateByKey"
0x18000631f  jmp     loc_18000621A
0x180006324  mov     rax, [rcx]
0x180006327  cmp     dword ptr [rax+40h], 5
0x18000632b  jnz     loc_18000612E
0x180006331  mov     r8, [rax+48h]
0x180006335  mov     edx, r9d
0x180006338  jmp     loc_180088742
0x18000633d  test    rbx, rbx
0x180006340  jz      loc_180006262
0x180006346  cmp     qword ptr [rbx], 0
0x18000634a  jz      loc_180006262
0x180006350  jmp     loc_180006267
0x180006355  test    [rcx+1Ch], r15b
0x180006359  jz      loc_180006241
0x18000635f  mov     rcx, [rcx+10h]
0x180006363  mov     edx, 17h
0x180006368  mov     [rsp+78h+var_50], ebx
0x18000636c  xor     r9d, r9d
0x18000636f  mov     [rsp+78h+var_58], r8
0x180006374  call    WPP_SF_SsD
0x180006379  jmp     loc_180006241
0x18000637e  test    byte ptr cs:qword_1800F2668+0A8Dh, r15b
0x180006385  jz      loc_180006255
0x18000638b  lea     rax, [rbp+var_48]
0x18000638f  mov     [rbp+var_48], ebx
0x180006392  mov     [rbp+var_20], rax
0x180006396  lea     rdx, WFP_USERMODE_ERROR
0x18000639d  lea     rax, [rbp+var_40]
0x1800063a1  mov     [rbp+var_30], rsi
0x1800063a5  mov     r9d, 3
0x1800063ab  mov     [rsp+78h+var_58], rax
0x1800063b0  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x1800063b7  mov     [rbp+var_28], 18h
0x1800063bf  mov     [rbp+var_18], 4
0x1800063c7  call    McGenEventWrite_EtwEventWriteTransfer
0x1800063cc  jmp     loc_180006255
0x1800063d1  movzx   ebx, bx
0x1800063d4  or      ebx, 80070000h
0x1800063da  jmp     loc_18000625D
0x1800063df  test    byte ptr cs:qword_1800F2668+0A8Dh, 1
0x1800063e6  jnz     loc_18000646D
0x1800063ec  mov     rbx, 0FFFFFFFF80070032h
0x1800063f3  mov     r15d, 1
0x1800063f9  mov     rdx, [rdi]
0x1800063fc  mov     ecx, r15d
0x1800063ff  mov     rsi, rdi
0x180006402  call    BfeObjectTraceAddFailure
0x180006407  mov     rcx, rdi
0x18000640a  call    BfeProviderContextDestroy
0x18000640f  mov     rdx, r12
0x180006412  mov     rcx, rbx
0x180006415  call    WfpReportError
0x18000641a  jmp     loc_1800062AD
0x18000641f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006426  lea     rax, WPP_GLOBAL_Control
0x18000642d  lea     r12, aBfeprovidercon_1; "BfeProviderContextCreate"
0x180006434  cmp     rcx, rax
0x180006437  jz      short loc_18000643F
0x180006439  cmp     byte ptr [rcx+19h], 2
0x18000643d  jnb     short loc_18000644A
0x18000643f  cmp     dword ptr cs:1800EF078h, 0
0x180006446  jz      short loc_1800063EC
0x180006448  jmp     short loc_1800063DF
0x18000644a  test    byte ptr [rcx+1Ch], 1
0x18000644e  jz      short loc_18000643F
0x180006450  mov     rcx, [rcx+10h]
0x180006454  mov     edx, 17h
0x180006459  mov     [rsp+78h+var_50], 32h ; '2'
0x180006461  mov     [rsp+78h+var_58], r12
0x180006466  call    WPP_SF_SsD
0x18000646b  jmp     short loc_18000643F
0x18000646d  lea     rax, [rbp+var_48]
0x180006471  mov     [rbp+var_48], 32h ; '2'
0x180006478  mov     [rbp+var_20], rax
0x18000647c  lea     rdx, WFP_USERMODE_ERROR
0x180006483  lea     rax, [rbp+var_40]
0x180006487  mov     [rbp+var_30], r12
0x18000648b  mov     r9d, 3
0x180006491  mov     [rsp+78h+var_58], rax
0x180006496  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18000649d  mov     [rbp+var_28], 19h
0x1800064a5  mov     [rbp+var_18], 4
0x1800064ad  call    McGenEventWrite_EtwEventWriteTransfer
0x1800064b2  jmp     loc_1800063EC
0x1800064b7  lea     rdx, aBfeobjecttypea; "BfeObjectTypeAccessCheck"
0x1800064be  mov     rcx, rax
0x1800064c1  call    WfpReportError
0x1800064c6  lea     r12, aBfeprovidercon_1; "BfeProviderContextCreate"
0x1800064cd  jmp     loc_1800063F9
0x1800064d2  cmp     dword ptr cs:qword_1800F2668+15Ch, 0C350h
0x1800064dc  jb      loc_180088767
0x1800064e2  mov     r8d, 32h ; '2'
0x1800064e8  mov     rdx, r12
0x1800064eb  call    WfpReportSysErrorAsWinError
0x1800064f0  mov     rbx, rax
0x1800064f3  jmp     loc_1800062A4
0x1800064f8  mov     rcx, rdi
0x1800064fb  call    BfeObjectSetPersistent
0x180006500  jmp     loc_180006193
0x180006505  mov     rdx, rsi
0x180006508  mov     rcx, rbx
0x18000650b  call    WfpReportError
0x180006510  jmp     loc_1800063F9
0x180088742  cmp     edx, [r8+4]
0x180088746  jnb     loc_18000612E
0x18008874c  mov     eax, edx
0x18008874e  lea     rcx, [rax+rax*4]
0x180088752  mov     rax, [r8+8]
0x180088756  add     rcx, rcx
0x180088759  cmp     dword ptr [rax+rcx*8], 6
0x18008875d  jz      loc_18000641F
0x180088763  inc     edx
0x180088765  jmp     short loc_180088742
0x180088767  mov     rcx, rdi
0x18008876a  call    BfeValidateLowPrivilegeProvCtxt
0x18008876f  mov     rbx, rax
0x180088772  test    rax, rax
0x180088775  jnz     loc_1800063F9
0x18008877b  inc     dword ptr cs:qword_1800F2668+15Ch
0x180088781  mov     [rdi+8], r15d
0x180088785  jmp     loc_180006178
```
