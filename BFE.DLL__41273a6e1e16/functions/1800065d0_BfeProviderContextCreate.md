# BfeProviderContextCreate

- ea: `0x1800065d0`
- end: `0x1800069fb`
- name: `BfeProviderContextCreate`
- size: `1067`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180005b60`
- `0x180006584`
- `0x1800065d0`
- `0x18000798c`
- `0x180007cd0`
- `0x18000de30`
- `0x18000fb34`
- `0x180010d60`
- `0x180012d8c`
- `0x1800133a0`
- `0x1800197d0`
- `0x1800592f4`
- `0x18005aa60`
- `0x1800756e8`

## import_xrefs

- `ntdll!RtlLookupEntryHashTable` at `0x1800066e4`
- `ntdll!RtlLookupEntryHashTable` at `0x1800066e4`
- `ntdll!RtlGetNextEntryHashTable` at `0x1800067ed`
- `ntdll!RtlGetNextEntryHashTable` at `0x1800067ed`

## string_xrefs

- `0x180006648`: `BfeProviderContextCreate`
- `0x180006913`: `BfeProviderContextCreate`
- `0x1800069ac`: `BfeProviderContextCreate`
- `0x18000699d`: `BfeObjectTypeAccessCheck`

## pseudocode

```c
__int64 __fastcall BfeProviderContextCreate(__int64 a1, _QWORD *a2)
{
  bool v2; // zf
  _DWORD *v3; // rdi
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rbx
  __int64 v8; // rcx
  _QWORD *v9; // rsi
  __int64 v10; // rbx
  __int64 v11; // r13
  __int64 v12; // rdx
  __int64 NextEntryHashTable; // rax
  const char *v14; // r8
  __int64 v16; // rbx
  _QWORD *Key; // rax
  __int64 v18; // rcx
  __int64 v19; // r8
  unsigned int i; // edx
  int v21; // [rsp+30h] [rbp-48h] BYREF
  __int128 v22; // [rsp+38h] [rbp-40h] BYREF
  const char *v23; // [rsp+48h] [rbp-30h]
  __int64 v24; // [rsp+50h] [rbp-28h]
  int *v25; // [rsp+58h] [rbp-20h]
  __int64 v26; // [rsp+60h] [rbp-18h]

  v2 = gBfeProvCtxtComponent == 0;
  v3 = (_DWORD *)a1;
  *(_QWORD *)a1 = *a2;
  *a2 = 0;
  v21 = 0;
  if ( v2 && *(_DWORD *)(*(_QWORD *)a1 + 64LL) == 5 )
  {
    v19 = *(_QWORD *)(*(_QWORD *)a1 + 72LL);
    for ( i = 0; i < *(_DWORD *)(v19 + 4); ++i )
    {
      a1 = 10LL * i;
      if ( *(_DWORD *)(*(_QWORD *)(v19 + 8) + 80LL * i) == 6 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_SsD(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v19, 0, (__int64)"BfeProviderContextCreate", 50);
        }
        if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
        {
          v21 = 50;
          v25 = &v21;
          v23 = "BfeProviderContextCreate";
          v24 = 25;
          v26 = 4;
          McGenEventWrite_EtwEventWriteTransfer(
            &MICROSOFT_WFP_PROVIDER_Context,
            (__int64)WFP_USERMODE_ERROR,
            v19,
            3,
            (__int64)&v22);
        }
        v7 = -2147024846;
        goto LABEL_51;
      }
    }
  }
  v4 = gBfeObjMgr;
  if ( !*(_DWORD *)(gBfeObjMgr + 2040) )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
  v5 = BfeAccessCheck(*(char **)(v4 + 2384), 1u, &v21);
  v7 = v5;
  if ( v5 )
  {
    WfpReportError(v5, "BfeObjectTypeAccessCheck");
    goto LABEL_51;
  }
  if ( !v21 )
  {
    if ( (unsigned int)dword_1800F57E4 >= 0xC350 )
    {
      v7 = WfpReportSysErrorAsWinError(v6, "BfeProviderContextCreate", 50);
      goto LABEL_28;
    }
    v7 = BfeValidateLowPrivilegeProvCtxt(v3);
    if ( v7 )
      goto LABEL_51;
    ++dword_1800F57E4;
    v3[2] = 1;
  }
  v8 = *(_QWORD *)v3;
  *(_QWORD *)(*(_QWORD *)v3 + 80LL) = qword_1800EE4D8;
  if ( (*(_BYTE *)(*(_QWORD *)v3 + 32LL) & 1) != 0 )
    BfeObjectSetPersistent(v3);
  v9 = *(_QWORD **)(*(_QWORD *)v3 + 40LL);
  if ( v9 )
  {
    if ( v3 == (_DWORD *)144 || !*((_QWORD *)v3 - 18) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v8);
    v10 = gBfeObjMgr;
    v23 = 0;
    v22 = 0;
    if ( !*(_DWORD *)gBfeObjMgr )
      MicrosoftTelemetryAssertTriggeredNoArgs(v8);
    v11 = v10 + 240;
    v12 = *v9 ^ v9[1];
    if ( !v12 )
      v12 = -1;
    NextEntryHashTable = RtlLookupEntryHashTable(v10 + 240, v12, &v22);
    v14 = "BfeObjectAssociateByKey";
    if ( NextEntryHashTable )
    {
      while ( 1 )
      {
        v16 = NextEntryHashTable - 16;
        Key = (_QWORD *)BfeObjectGetKey(NextEntryHashTable - 16);
        v18 = *Key - *v9;
        if ( *Key == *v9 )
          v18 = Key[1] - v9[1];
        if ( !v18 )
        {
          if ( !v16 || !*(_QWORD *)v16 )
            MicrosoftTelemetryAssertTriggeredNoArgs(0);
          if ( (*(_BYTE *)(v16 + 8) & 8) == 0 )
            break;
        }
        NextEntryHashTable = RtlGetNextEntryHashTable(v11, &v22);
        if ( !NextEntryHashTable )
          goto LABEL_38;
      }
      if ( !v16 || !*(_QWORD *)v16 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v18);
      if ( v16 )
      {
        v7 = BfeObjectAssociate(0, (_QWORD *)v3 - 18, (_QWORD *)v16);
        goto LABEL_26;
      }
LABEL_38:
      v14 = "BfeObjectAssociateByKey";
    }
    LODWORD(v7) = *(_DWORD *)(gBfeObjMgr + 72);
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
        *(_DWORD *)(gBfeObjMgr + 72));
    }
    if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
    {
      v21 = v7;
      v25 = &v21;
      v23 = "BfeObjectAssociateByKey";
      v24 = 24;
      v26 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        &MICROSOFT_WFP_PROVIDER_Context,
        (__int64)WFP_USERMODE_ERROR,
        (__int64)v14,
        3,
        (__int64)&v22);
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
  ++qword_1800EE4D8;
LABEL_28:
  if ( v7 )
  {
LABEL_51:
    BfeObjectTraceAddFailure(1, *(_QWORD *)v3);
    BfeProviderContextDestroy(v3);
    WfpReportError(v7, "BfeProviderContextCreate");
  }
  return v7;
}

```

## disassembly

```asm
0x1800065d0  push    rbp
0x1800065d2  push    rbx
0x1800065d3  push    rsi
0x1800065d4  push    rdi
0x1800065d5  push    r12
0x1800065d7  push    r15
0x1800065d9  mov     rbp, rsp
0x1800065dc  sub     rsp, 78h
0x1800065e0  mov     rax, cs:__security_cookie
0x1800065e7  xor     rax, rsp
0x1800065ea  mov     [rbp+var_10], rax
0x1800065ee  mov     rax, [rdx]
0x1800065f1  xor     r9d, r9d
0x1800065f4  cmp     cs:gBfeProvCtxtComponent, r9d
0x1800065fb  mov     rdi, rcx
0x1800065fe  mov     [rcx], rax
0x180006601  mov     [rdx], r9
0x180006604  mov     [rbp+var_48], r9d
0x180006608  jz      loc_18000680A
0x18000660e  mov     rbx, cs:gBfeObjMgr
0x180006615  cmp     [rbx+7F8h], r9d
0x18000661c  jnz     short loc_180006623
0x18000661e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180006623  mov     rcx, [rbx+950h]; pSecurityDescriptor
0x18000662a  lea     r8, [rbp+var_48]
0x18000662e  mov     r15d, 1
0x180006634  mov     edx, r15d
0x180006637  call    BfeAccessCheck
0x18000663c  mov     rbx, rax
0x18000663f  test    rax, rax
0x180006642  jnz     loc_18000699D
0x180006648  lea     r12, aBfeprovidercon_1; "BfeProviderContextCreate"
0x18000664f  cmp     [rbp+var_48], eax
0x180006652  jz      loc_1800069B8
0x180006658  mov     rax, cs:qword_1800EE4D8
0x18000665f  mov     rcx, [rdi]
0x180006662  mov     [rcx+50h], rax
0x180006666  mov     rax, [rdi]
0x180006669  test    [rax+20h], r15b
0x18000666d  jnz     loc_1800069DE
0x180006673  mov     rax, [rdi]
0x180006676  mov     rsi, [rax+28h]
0x18000667a  test    rsi, rsi
0x18000667d  jz      loc_180006783
0x180006683  mov     [rsp+78h+arg_10], r13
0x18000668b  mov     [rsp+78h+var_8], r14
0x180006690  lea     r14, [rdi-90h]
0x180006697  test    r14, r14
0x18000669a  jz      short loc_1800066A2
0x18000669c  cmp     qword ptr [r14], 0
0x1800066a0  jnz     short loc_1800066A7
0x1800066a2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800066a7  mov     rbx, cs:gBfeObjMgr
0x1800066ae  xor     eax, eax
0x1800066b0  xorps   xmm0, xmm0
0x1800066b3  mov     [rbp+var_30], rax
0x1800066b7  movups  [rbp+var_40], xmm0
0x1800066bb  cmp     [rbx], eax
0x1800066bd  jnz     short loc_1800066C4
0x1800066bf  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800066c4  mov     rdx, [rsi+8]
0x1800066c8  lea     r13, [rbx+0F0h]
0x1800066cf  xor     rdx, [rsi]
0x1800066d2  lea     r8, [rbp+var_40]
0x1800066d6  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800066dd  mov     rcx, r13
0x1800066e0  cmovz   rdx, rax
0x1800066e4  call    cs:__imp_RtlLookupEntryHashTable
0x1800066eb  nop     dword ptr [rax+rax+00h]
0x1800066f0  lea     r8, aBfeobjectassoc_1; "BfeObjectAssociateByKey"
0x1800066f7  test    rax, rax
0x1800066fa  jnz     loc_1800067B0
0x180006700  mov     rax, cs:gBfeObjMgr
0x180006707  mov     ebx, [rax+48h]
0x18000670a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006711  lea     rax, WPP_GLOBAL_Control
0x180006718  cmp     rcx, rax
0x18000671b  jz      short loc_180006727
0x18000671d  cmp     byte ptr [rcx+19h], 2
0x180006721  jnb     loc_18000683B
0x180006727  cmp     cs:gWfpLogUserModeErrors, 0
0x18000672e  lea     rsi, aBfeobjectassoc_1; "BfeObjectAssociateByKey"
0x180006735  jnz     loc_180006864
0x18000673b  test    ebx, ebx
0x18000673d  jg      loc_1800068B7
0x180006743  movsxd  rbx, ebx
0x180006746  jmp     short loc_18000676D
0x180006748  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000674d  test    rbx, rbx
0x180006750  jz      loc_1800067FE
0x180006756  mov     r8, rbx
0x180006759  mov     rdx, r14
0x18000675c  xor     ecx, ecx
0x18000675e  call    BfeObjectAssociate
0x180006763  mov     rbx, rax
0x180006766  lea     rsi, aBfeobjectassoc_1; "BfeObjectAssociateByKey"
0x18000676d  mov     r14, [rsp+78h+var_8]
0x180006772  mov     r13, [rsp+78h+arg_10]
0x18000677a  test    rbx, rbx
0x18000677d  jnz     loc_1800069EB
0x180006783  inc     cs:qword_1800EE4D8
0x18000678a  test    rbx, rbx
0x18000678d  jnz     loc_1800068DF
0x180006793  mov     rax, rbx
0x180006796  mov     rcx, [rbp+var_10]
0x18000679a  xor     rcx, rsp; StackCookie
0x18000679d  call    __security_check_cookie
0x1800067a2  add     rsp, 78h
0x1800067a6  pop     r15
0x1800067a8  pop     r12
0x1800067aa  pop     rdi
0x1800067ab  pop     rsi
0x1800067ac  pop     rbx
0x1800067ad  pop     rbp
0x1800067ae  retn
0x1800067b0  lea     rbx, [rax-10h]
0x1800067b4  mov     rcx, rbx
0x1800067b7  call    BfeObjectGetKey
0x1800067bc  mov     rcx, [rax]
0x1800067bf  sub     rcx, [rsi]
0x1800067c2  jnz     short loc_1800067CC
0x1800067c4  mov     rcx, [rax+8]
0x1800067c8  sub     rcx, [rsi+8]
0x1800067cc  test    rcx, rcx
0x1800067cf  jnz     short loc_1800067E6
0x1800067d1  test    rbx, rbx
0x1800067d4  jz      short loc_1800067DB
0x1800067d6  cmp     [rbx], rcx
0x1800067d9  jnz     short loc_1800067E0
0x1800067db  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800067e0  test    byte ptr [rbx+8], 8
0x1800067e4  jz      short loc_180006823
0x1800067e6  lea     rdx, [rbp+var_40]
0x1800067ea  mov     rcx, r13
0x1800067ed  call    cs:__imp_RtlGetNextEntryHashTable
0x1800067f4  nop     dword ptr [rax+rax+00h]
0x1800067f9  test    rax, rax
0x1800067fc  jnz     short loc_1800067B0
0x1800067fe  lea     r8, aBfeobjectassoc_1; "BfeObjectAssociateByKey"
0x180006805  jmp     loc_180006700
0x18000680a  mov     rax, [rcx]
0x18000680d  cmp     dword ptr [rax+40h], 5
0x180006811  jnz     loc_18000660E
0x180006817  mov     r8, [rax+48h]
0x18000681b  mov     edx, r9d
0x18000681e  jmp     loc_18008B624
0x180006823  test    rbx, rbx
0x180006826  jz      loc_180006748
0x18000682c  cmp     qword ptr [rbx], 0
0x180006830  jz      loc_180006748
0x180006836  jmp     loc_18000674D
0x18000683b  test    [rcx+1Ch], r15b
0x18000683f  jz      loc_180006727
0x180006845  mov     rcx, [rcx+10h]
0x180006849  mov     edx, 17h
0x18000684e  mov     [rsp+78h+var_50], ebx
0x180006852  xor     r9d, r9d
0x180006855  mov     [rsp+78h+var_58], r8
0x18000685a  call    WPP_SF_SsD
0x18000685f  jmp     loc_180006727
0x180006864  test    cs:byte_1800F6115, r15b
0x18000686b  jz      loc_18000673B
0x180006871  lea     rax, [rbp+var_48]
0x180006875  mov     [rbp+var_48], ebx
0x180006878  mov     [rbp+var_20], rax
0x18000687c  lea     rdx, WFP_USERMODE_ERROR
0x180006883  lea     rax, [rbp+var_40]
0x180006887  mov     [rbp+var_30], rsi
0x18000688b  mov     r9d, 3
0x180006891  mov     [rsp+78h+var_58], rax
0x180006896  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18000689d  mov     [rbp+var_28], 18h
0x1800068a5  mov     [rbp+var_18], 4
0x1800068ad  call    McGenEventWrite_EtwEventWriteTransfer
0x1800068b2  jmp     loc_18000673B
0x1800068b7  movzx   ebx, bx
0x1800068ba  or      ebx, 80070000h
0x1800068c0  jmp     loc_180006743
0x1800068c5  test    cs:byte_1800F6115, 1
0x1800068cc  jnz     loc_180006953
0x1800068d2  mov     rbx, 0FFFFFFFF80070032h
0x1800068d9  mov     r15d, 1
0x1800068df  mov     rdx, [rdi]
0x1800068e2  mov     ecx, r15d
0x1800068e5  mov     rsi, rdi
0x1800068e8  call    BfeObjectTraceAddFailure
0x1800068ed  mov     rcx, rdi
0x1800068f0  call    BfeProviderContextDestroy
0x1800068f5  mov     rdx, r12
0x1800068f8  mov     rcx, rbx
0x1800068fb  call    WfpReportError
0x180006900  jmp     loc_180006793
0x180006905  mov     rcx, cs:WPP_GLOBAL_Control
0x18000690c  lea     rax, WPP_GLOBAL_Control
0x180006913  lea     r12, aBfeprovidercon_1; "BfeProviderContextCreate"
0x18000691a  cmp     rcx, rax
0x18000691d  jz      short loc_180006925
0x18000691f  cmp     byte ptr [rcx+19h], 2
0x180006923  jnb     short loc_180006930
0x180006925  cmp     cs:gWfpLogUserModeErrors, 0
0x18000692c  jz      short loc_1800068D2
0x18000692e  jmp     short loc_1800068C5
0x180006930  test    byte ptr [rcx+1Ch], 1
0x180006934  jz      short loc_180006925
0x180006936  mov     rcx, [rcx+10h]
0x18000693a  mov     edx, 17h
0x18000693f  mov     [rsp+78h+var_50], 32h ; '2'
0x180006947  mov     [rsp+78h+var_58], r12
0x18000694c  call    WPP_SF_SsD
0x180006951  jmp     short loc_180006925
0x180006953  lea     rax, [rbp+var_48]
0x180006957  mov     [rbp+var_48], 32h ; '2'
0x18000695e  mov     [rbp+var_20], rax
0x180006962  lea     rdx, WFP_USERMODE_ERROR
0x180006969  lea     rax, [rbp+var_40]
0x18000696d  mov     [rbp+var_30], r12
0x180006971  mov     r9d, 3
0x180006977  mov     [rsp+78h+var_58], rax
0x18000697c  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180006983  mov     [rbp+var_28], 19h
0x18000698b  mov     [rbp+var_18], 4
0x180006993  call    McGenEventWrite_EtwEventWriteTransfer
0x180006998  jmp     loc_1800068D2
0x18000699d  lea     rdx, aBfeobjecttypea; "BfeObjectTypeAccessCheck"
0x1800069a4  mov     rcx, rax
0x1800069a7  call    WfpReportError
0x1800069ac  lea     r12, aBfeprovidercon_1; "BfeProviderContextCreate"
0x1800069b3  jmp     loc_1800068DF
0x1800069b8  cmp     cs:dword_1800F57E4, 0C350h
0x1800069c2  jb      loc_18008B649
0x1800069c8  mov     r8d, 32h ; '2'
0x1800069ce  mov     rdx, r12
0x1800069d1  call    WfpReportSysErrorAsWinError
0x1800069d6  mov     rbx, rax
0x1800069d9  jmp     loc_18000678A
0x1800069de  mov     rcx, rdi
0x1800069e1  call    BfeObjectSetPersistent
0x1800069e6  jmp     loc_180006673
0x1800069eb  mov     rdx, rsi
0x1800069ee  mov     rcx, rbx
0x1800069f1  call    WfpReportError
0x1800069f6  jmp     loc_1800068DF
0x18008b624  cmp     edx, [r8+4]
0x18008b628  jnb     loc_18000660E
0x18008b62e  mov     eax, edx
0x18008b630  lea     rcx, [rax+rax*4]
0x18008b634  mov     rax, [r8+8]
0x18008b638  add     rcx, rcx
0x18008b63b  cmp     dword ptr [rax+rcx*8], 6
0x18008b63f  jz      loc_180006905
0x18008b645  inc     edx
0x18008b647  jmp     short loc_18008B624
0x18008b649  mov     rcx, rdi
0x18008b64c  call    BfeValidateLowPrivilegeProvCtxt
0x18008b651  mov     rbx, rax
0x18008b654  test    rax, rax
0x18008b657  jnz     loc_1800068DF
0x18008b65d  inc     cs:dword_1800F57E4
0x18008b663  mov     [rdi+8], r15d
0x18008b667  jmp     loc_180006658
```
