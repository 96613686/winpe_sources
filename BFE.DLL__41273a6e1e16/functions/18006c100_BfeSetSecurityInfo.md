# BfeSetSecurityInfo

- ea: `0x18006c100`
- end: `0x18006c51f`
- name: `BfeSetSecurityInfo`
- size: `1055`
- prototype: `__int64 __fastcall(SECURITY_INFORMATION SecurityInformation, PSECURITY_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180065130`

## callees

- `0x1800089a0`
- `0x1800197d0`
- `0x18002077c`
- `0x1800349f8`
- `0x180034e74`
- `0x180034ed8`
- `0x1800376d0`
- `0x1800387b4`
- `0x180040dcc`
- `0x1800451a0`
- `0x1800451ec`
- `0x18004c0fc`
- `0x1800575a0`
- `0x18005922c`
- `0x18006b460`
- `0x18006bf3c`
- `0x18006c100`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x18006c31f`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18006c441`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18006c31f`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18006c441`

## string_xrefs

- `0x18006c47f`: `bfe.dll`
- `0x18006c4dc`: `bfe.dll`
- `0x18006c1cb`: `BfeNetEventsPropagateSecurityBegin`
- `0x18006c205`: `BfeConnectionPropagateSecurityBegin`
- `0x18006c4f4`: `BfeSetSecurityInfo`
- `0x18006c2ac`: `BfeSaDbPropagateSecurityBegin`
- `0x18006c35e`: `BfeDriverSetEngineSecurityDescriptorBegin`
- `0x18006c2de`: `BfeDospPropagateSecurityBegin`
- `0x18006c310`: `BfeAlePropagateSecurityBegin`
- `0x18006c234`: `BfevSwitchEventsPropagateSecurityBegin`
- `0x18006c263`: `BfeVpnTriggerEventsPropagateSecurityBegin`

## pseudocode

```c
__int64 __fastcall BfeSetSecurityInfo(signed int SecurityInformation, PSECURITY_DESCRIPTOR a2)
{
  char v2; // r12
  __int64 v3; // rdi
  PSECURITY_DESCRIPTOR v4; // rsi
  __int64 v5; // r14
  __int64 v6; // rax
  const char *v7; // rdx
  ULONG v8; // eax
  __int64 i; // r15
  __int64 v10; // rbx
  ULONG v11; // eax
  __int64 v12; // rax
  __int64 v13; // rax
  PSECURITY_DESCRIPTOR SecurityDescriptor[2]; // [rsp+40h] [rbp-10h] BYREF
  __int64 v16; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v17; // [rsp+A8h] [rbp+58h] BYREF

  v2 = 0;
  SecurityDescriptor[0] = 0;
  v17 = 0;
  v16 = 0;
  v3 = BfeObjectSecuritySetInfo(0, ParentDescriptor, 1, SecurityInformation, a2, (__int64)SecurityDescriptor);
  if ( !v3 )
  {
    v3 = BfeObjectSecurityListCreate(&v17);
    if ( !v3 )
    {
      v3 = BfeDbTxnCreate(&v16);
      if ( !v3 )
      {
        v4 = SecurityDescriptor[0];
        v3 = BfeObjectSecuritySave(SecurityDescriptor[0]);
        if ( !v3 )
        {
          v5 = v17;
          v6 = BfeObjectSecurityPropagateBegin(CreatorDescriptor, v4, (__int64)&FWPM_OBJECT_TYPE_NET_EVENTS);
          v3 = v6;
          if ( v6 )
          {
            v7 = "BfeNetEventsPropagateSecurityBegin";
LABEL_7:
            WfpReportError(v6, v7);
            goto LABEL_28;
          }
          v6 = BfeObjectSecurityPropagateBegin(qword_1800F5D70, v4, (__int64)&FWPM_OBJECT_TYPE_CONNECTIONS);
          v3 = v6;
          if ( v6 )
          {
            v7 = "BfeConnectionPropagateSecurityBegin";
            goto LABEL_7;
          }
          v6 = BfeObjectSecurityPropagateBegin(
                 gBfevSwitchEventController,
                 v4,
                 (__int64)&FWPM_OBJECT_TYPE_VSWITCH_EVENTS);
          v3 = v6;
          if ( v6 )
          {
            v7 = "BfevSwitchEventsPropagateSecurityBegin";
            goto LABEL_7;
          }
          v6 = BfeObjectSecurityPropagateBegin(
                 gBfeVpnTriggerEventController,
                 v4,
                 (__int64)&FWPM_OBJECT_TYPE_VPN_TRIGGER_EVENTS);
          v3 = v6;
          if ( v6 )
          {
            v7 = "BfeVpnTriggerEventsPropagateSecurityBegin";
            goto LABEL_7;
          }
          v3 = BfeObjectPropagateSecurityBegin(v4);
          if ( !v3 )
          {
            v6 = BfeObjectSecurityPropagateBegin(pSecurityDescriptor, v4, (__int64)&FWPM_OBJECT_TYPE_IPSEC_SA_DB);
            v3 = v6;
            if ( v6 )
            {
              v7 = "BfeSaDbPropagateSecurityBegin";
              goto LABEL_7;
            }
            v6 = BfeObjectSecurityPropagateBegin(gBfeDospComponent, v4, (__int64)&FWPM_OBJECT_TYPE_IPSEC_DOSP);
            v3 = v6;
            if ( v6 )
            {
              v7 = "BfeDospPropagateSecurityBegin";
              goto LABEL_7;
            }
            v6 = BfeObjectSecurityPropagateBegin(gBfeAleComponent, v4, (__int64)&FWPM_OBJECT_TYPE_ALE);
            v3 = v6;
            if ( v6 )
            {
              v7 = "BfeAlePropagateSecurityBegin";
              goto LABEL_7;
            }
            v8 = RtlLengthSecurityDescriptor(v4);
            v6 = BfeDeviceIoControl(gBfeDriverControlComponent, 0x124048u, v8, v4, 0, 0, 0, 0);
            v3 = v6;
            if ( v6 )
            {
              v7 = "BfeDriverSetEngineSecurityDescriptorBegin";
              goto LABEL_7;
            }
            v2 = 1;
            v3 = BfeDbTxnCommit(v16);
            if ( !v3 )
            {
              BfeObjectSecurityDestroy(&ParentDescriptor);
              ParentDescriptor = v4;
              BfeObjectSecurityPropagateCommit(&CreatorDescriptor, v5);
              BfeObjectSecurityPropagateCommit(&qword_1800F5D70, v5);
              BfeObjectSecurityPropagateCommit(&gBfevSwitchEventController, v5);
              BfeObjectSecurityPropagateCommit(&gBfeVpnTriggerEventController, v5);
              for ( i = 0; i != 7; ++i )
              {
                v10 = gBfeObjMgr + 408 * i;
                BfeObjectPropagateSecurityByTypeCommit(v10, v5);
                BfeObjectSecurityDestroy(v10 + 344);
                *(_QWORD *)(v10 + 344) = BfeObjectSecurityListPopFront(v5);
              }
              BfeObjectSecurityPropagateCommit(&pSecurityDescriptor, v5);
              BfeObjectSecurityPropagateCommit(&gBfeDospComponent, v5);
              BfeObjectSecurityPropagateCommit(&gBfeAleComponent, v5);
              v11 = RtlLengthSecurityDescriptor(v4);
              v12 = BfeDeviceIoControl(gBfeDriverControlComponent, 0x12404Cu, v11, v4, 0, 0, 0, 0);
              if ( v12 )
                MicrosoftTelemetryAssertTriggeredArgs("bfe.dll", (unsigned int)v12, 0);
            }
          }
        }
      }
    }
  }
LABEL_28:
  BfeDbTxnDestroy(&v16);
  BfeObjectSecurityListDestroy(&v17);
  if ( v3 )
  {
    if ( v2 )
    {
      v13 = BfeDeviceIoControl(gBfeDriverControlComponent, 0x124050u, 0, 0, 0, 0, 0, 0);
      if ( v13 )
        MicrosoftTelemetryAssertTriggeredArgs("bfe.dll", (unsigned int)v13, 0);
    }
    BfeObjectSecurityDestroy(SecurityDescriptor);
    WfpReportError(v3, "BfeSetSecurityInfo");
  }
  return v3;
}

```

## disassembly

```asm
0x18006c100  mov     [rsp-38h+arg_0], rbx
0x18006c105  push    rbp
0x18006c106  push    rsi
0x18006c107  push    rdi
0x18006c108  push    r12
0x18006c10a  push    r13
0x18006c10c  push    r14
0x18006c10e  push    r15
0x18006c110  mov     rbp, rsp
0x18006c113  sub     rsp, 50h
0x18006c117  xor     r13d, r13d
0x18006c11a  lea     rax, [rbp+SecurityDescriptor]
0x18006c11e  mov     [rsp+50h+var_28], rax; __int64
0x18006c123  mov     r9d, ecx; SecurityInformation
0x18006c126  mov     qword ptr [rsp+50h+var_30], rdx; PSECURITY_DESCRIPTOR
0x18006c12b  xor     ecx, ecx; ParentDescriptor
0x18006c12d  mov     rdx, cs:ParentDescriptor; pSecurityDescriptor
0x18006c134  mov     r12b, r13b
0x18006c137  lea     r8d, [r13+1]; IsContainerObject
0x18006c13b  mov     [rbp+SecurityDescriptor], r13
0x18006c13f  mov     [rbp+arg_18], r13
0x18006c143  mov     [rbp+arg_10], r13
0x18006c147  call    BfeObjectSecuritySetInfo
0x18006c14c  mov     rdi, rax
0x18006c14f  test    rax, rax
0x18006c152  jnz     loc_18006C48E
0x18006c158  lea     rcx, [rbp+arg_18]
0x18006c15c  call    BfeObjectSecurityListCreate
0x18006c161  mov     rdi, rax
0x18006c164  test    rax, rax
0x18006c167  jnz     loc_18006C48E
0x18006c16d  lea     rcx, [rbp+arg_10]
0x18006c171  call    BfeDbTxnCreate
0x18006c176  mov     rdi, rax
0x18006c179  test    rax, rax
0x18006c17c  jnz     loc_18006C48E
0x18006c182  mov     rsi, [rbp+SecurityDescriptor]
0x18006c186  lea     rdx, FWPM_OBJECT_TYPE_ENGINE
0x18006c18d  mov     rcx, rsi; SecurityDescriptor
0x18006c190  call    BfeObjectSecuritySave
0x18006c195  mov     rdi, rax
0x18006c198  test    rax, rax
0x18006c19b  jnz     loc_18006C48E
0x18006c1a1  mov     r14, [rbp+arg_18]
0x18006c1a5  lea     rax, FWPM_OBJECT_TYPE_NET_EVENTS
0x18006c1ac  mov     rcx, cs:CreatorDescriptor; CreatorDescriptor
0x18006c1b3  mov     r9, r14
0x18006c1b6  mov     rdx, rsi; ParentDescriptor
0x18006c1b9  mov     qword ptr [rsp+50h+var_30], rax; __int64
0x18006c1be  call    BfeObjectSecurityPropagateBegin
0x18006c1c3  mov     rdi, rax
0x18006c1c6  test    rax, rax
0x18006c1c9  jz      short loc_18006C1DF
0x18006c1cb  lea     rdx, aBfeneteventspr; "BfeNetEventsPropagateSecurityBegin"
0x18006c1d2  mov     rcx, rax
0x18006c1d5  call    WfpReportError
0x18006c1da  jmp     loc_18006C48E
0x18006c1df  mov     rcx, cs:qword_1800F5D70; CreatorDescriptor
0x18006c1e6  lea     rax, FWPM_OBJECT_TYPE_CONNECTIONS
0x18006c1ed  mov     r9, r14
0x18006c1f0  mov     qword ptr [rsp+50h+var_30], rax; __int64
0x18006c1f5  mov     rdx, rsi; ParentDescriptor
0x18006c1f8  call    BfeObjectSecurityPropagateBegin
0x18006c1fd  mov     rdi, rax
0x18006c200  test    rax, rax
0x18006c203  jz      short loc_18006C20E
0x18006c205  lea     rdx, aBfeconnectionp; "BfeConnectionPropagateSecurityBegin"
0x18006c20c  jmp     short loc_18006C1D2
0x18006c20e  mov     rcx, qword ptr cs:gBfevSwitchEventController; CreatorDescriptor
0x18006c215  lea     rax, FWPM_OBJECT_TYPE_VSWITCH_EVENTS
0x18006c21c  mov     r9, r14
0x18006c21f  mov     qword ptr [rsp+50h+var_30], rax; __int64
0x18006c224  mov     rdx, rsi; ParentDescriptor
0x18006c227  call    BfeObjectSecurityPropagateBegin
0x18006c22c  mov     rdi, rax
0x18006c22f  test    rax, rax
0x18006c232  jz      short loc_18006C23D
0x18006c234  lea     rdx, aBfevswitcheven_8; "BfevSwitchEventsPropagateSecurityBegin"
0x18006c23b  jmp     short loc_18006C1D2
0x18006c23d  mov     rcx, qword ptr cs:gBfeVpnTriggerEventController; CreatorDescriptor
0x18006c244  lea     rax, FWPM_OBJECT_TYPE_VPN_TRIGGER_EVENTS
0x18006c24b  mov     r9, r14
0x18006c24e  mov     qword ptr [rsp+50h+var_30], rax; __int64
0x18006c253  mov     rdx, rsi; ParentDescriptor
0x18006c256  call    BfeObjectSecurityPropagateBegin
0x18006c25b  mov     rdi, rax
0x18006c25e  test    rax, rax
0x18006c261  jz      short loc_18006C26F
0x18006c263  lea     rdx, aBfevpntriggere_4; "BfeVpnTriggerEventsPropagateSecurityBeg"...
0x18006c26a  jmp     loc_18006C1D2
0x18006c26f  mov     rdx, r14
0x18006c272  mov     rcx, rsi; ParentDescriptor
0x18006c275  call    BfeObjectPropagateSecurityBegin
0x18006c27a  mov     rdi, rax
0x18006c27d  test    rax, rax
0x18006c280  jnz     loc_18006C48E
0x18006c286  mov     rcx, cs:pSecurityDescriptor; CreatorDescriptor
0x18006c28d  lea     rax, FWPM_OBJECT_TYPE_IPSEC_SA_DB
0x18006c294  mov     r9, r14
0x18006c297  mov     qword ptr [rsp+50h+var_30], rax; __int64
0x18006c29c  mov     rdx, rsi; ParentDescriptor
0x18006c29f  call    BfeObjectSecurityPropagateBegin
0x18006c2a4  mov     rdi, rax
0x18006c2a7  test    rax, rax
0x18006c2aa  jz      short loc_18006C2B8
0x18006c2ac  lea     rdx, aBfesadbpropaga; "BfeSaDbPropagateSecurityBegin"
0x18006c2b3  jmp     loc_18006C1D2
0x18006c2b8  mov     rcx, cs:gBfeDospComponent; CreatorDescriptor
0x18006c2bf  lea     rax, FWPM_OBJECT_TYPE_IPSEC_DOSP
0x18006c2c6  mov     r9, r14
0x18006c2c9  mov     qword ptr [rsp+50h+var_30], rax; __int64
0x18006c2ce  mov     rdx, rsi; ParentDescriptor
0x18006c2d1  call    BfeObjectSecurityPropagateBegin
0x18006c2d6  mov     rdi, rax
0x18006c2d9  test    rax, rax
0x18006c2dc  jz      short loc_18006C2EA
0x18006c2de  lea     rdx, aBfedosppropaga; "BfeDospPropagateSecurityBegin"
0x18006c2e5  jmp     loc_18006C1D2
0x18006c2ea  mov     rcx, cs:gBfeAleComponent; CreatorDescriptor
0x18006c2f1  lea     rax, FWPM_OBJECT_TYPE_ALE
0x18006c2f8  mov     r9, r14
0x18006c2fb  mov     qword ptr [rsp+50h+var_30], rax; __int64
0x18006c300  mov     rdx, rsi; ParentDescriptor
0x18006c303  call    BfeObjectSecurityPropagateBegin
0x18006c308  mov     rdi, rax
0x18006c30b  test    rax, rax
0x18006c30e  jz      short loc_18006C31C
0x18006c310  lea     rdx, aBfealepropagat; "BfeAlePropagateSecurityBegin"
0x18006c317  jmp     loc_18006C1D2
0x18006c31c  mov     rcx, rsi; SecurityDescriptor
0x18006c31f  call    cs:__imp_RtlLengthSecurityDescriptor
0x18006c326  nop     dword ptr [rax+rax+00h]
0x18006c32b  mov     rcx, cs:gBfeDriverControlComponent; FileHandle
0x18006c332  mov     r9, rsi; InputBuffer
0x18006c335  mov     [rsp+50h+var_18], r13; __int64
0x18006c33a  mov     r8d, eax; InputBufferLength
0x18006c33d  mov     [rsp+50h+var_20], r13; __int64
0x18006c342  mov     edx, 124048h; IoControlCode
0x18006c347  mov     [rsp+50h+var_28], r13; PVOID
0x18006c34c  mov     [rsp+50h+var_30], r13d; ULONG
0x18006c351  call    BfeDeviceIoControl
0x18006c356  mov     rdi, rax
0x18006c359  test    rax, rax
0x18006c35c  jz      short loc_18006C36A
0x18006c35e  lea     rdx, aBfedriverseten; "BfeDriverSetEngineSecurityDescriptorBeg"...
0x18006c365  jmp     loc_18006C1D2
0x18006c36a  mov     rcx, [rbp+arg_10]
0x18006c36e  mov     r12b, 1
0x18006c371  call    BfeDbTxnCommit
0x18006c376  mov     rdi, rax
0x18006c379  test    rax, rax
0x18006c37c  jnz     loc_18006C48E
0x18006c382  lea     rcx, ParentDescriptor
0x18006c389  call    BfeObjectSecurityDestroy
0x18006c38e  mov     rdx, r14
0x18006c391  mov     cs:ParentDescriptor, rsi
0x18006c398  lea     rcx, CreatorDescriptor
0x18006c39f  call    BfeObjectSecurityPropagateCommit
0x18006c3a4  mov     rdx, r14
0x18006c3a7  lea     rcx, qword_1800F5D70
0x18006c3ae  call    BfeObjectSecurityPropagateCommit
0x18006c3b3  mov     rdx, r14
0x18006c3b6  lea     rcx, gBfevSwitchEventController
0x18006c3bd  call    BfeObjectSecurityPropagateCommit
0x18006c3c2  mov     rdx, r14
0x18006c3c5  lea     rcx, gBfeVpnTriggerEventController
0x18006c3cc  call    BfeObjectSecurityPropagateCommit
0x18006c3d1  mov     r15, r13
0x18006c3d4  imul    rbx, r15, 198h
0x18006c3db  mov     rdx, r14
0x18006c3de  add     rbx, cs:gBfeObjMgr
0x18006c3e5  mov     rcx, rbx
0x18006c3e8  call    BfeObjectPropagateSecurityByTypeCommit
0x18006c3ed  lea     rcx, [rbx+158h]
0x18006c3f4  call    BfeObjectSecurityDestroy
0x18006c3f9  mov     rcx, r14
0x18006c3fc  call    BfeObjectSecurityListPopFront
0x18006c401  inc     r15
0x18006c404  mov     [rbx+158h], rax
0x18006c40b  cmp     r15, 7
0x18006c40f  jnz     short loc_18006C3D4
0x18006c411  mov     rdx, r14
0x18006c414  lea     rcx, pSecurityDescriptor
0x18006c41b  call    BfeObjectSecurityPropagateCommit
0x18006c420  mov     rdx, r14
0x18006c423  lea     rcx, gBfeDospComponent
0x18006c42a  call    BfeObjectSecurityPropagateCommit
0x18006c42f  mov     rdx, r14
0x18006c432  lea     rcx, gBfeAleComponent
0x18006c439  call    BfeObjectSecurityPropagateCommit
0x18006c43e  mov     rcx, rsi; SecurityDescriptor
0x18006c441  call    cs:__imp_RtlLengthSecurityDescriptor
0x18006c448  nop     dword ptr [rax+rax+00h]
0x18006c44d  mov     rcx, cs:gBfeDriverControlComponent; FileHandle
0x18006c454  mov     r9, rsi; InputBuffer
0x18006c457  mov     [rsp+50h+var_18], r13; __int64
0x18006c45c  mov     r8d, eax; InputBufferLength
0x18006c45f  mov     [rsp+50h+var_20], r13; __int64
0x18006c464  mov     edx, 12404Ch; IoControlCode
0x18006c469  mov     [rsp+50h+var_28], r13; PVOID
0x18006c46e  mov     [rsp+50h+var_30], r13d; ULONG
0x18006c473  call    BfeDeviceIoControl
0x18006c478  test    rax, rax
0x18006c47b  jz      short loc_18006C48E
0x18006c47d  mov     edx, eax; __annotation("Debug", "TelemetryAssert", "WFP_IS_SUCCESS(result)")
0x18006c47f  lea     rcx, aBfeDll_0; "bfe.dll"
0x18006c486  xor     r8d, r8d
0x18006c489  call    MicrosoftTelemetryAssertTriggeredArgs
0x18006c48e  lea     rcx, [rbp+arg_10]
0x18006c492  call    BfeDbTxnDestroy
0x18006c497  lea     rcx, [rbp+arg_18]
0x18006c49b  call    BfeObjectSecurityListDestroy
0x18006c4a0  test    rdi, rdi
0x18006c4a3  jz      short loc_18006C503
0x18006c4a5  test    r12b, r12b
0x18006c4a8  jz      short loc_18006C4EB
0x18006c4aa  mov     rcx, cs:gBfeDriverControlComponent; FileHandle
0x18006c4b1  xor     r9d, r9d; InputBuffer
0x18006c4b4  mov     [rsp+50h+var_18], r13; __int64
0x18006c4b9  xor     r8d, r8d; InputBufferLength
0x18006c4bc  mov     [rsp+50h+var_20], r13; __int64
0x18006c4c1  mov     edx, 124050h; IoControlCode
0x18006c4c6  mov     [rsp+50h+var_28], r13; PVOID
0x18006c4cb  mov     [rsp+50h+var_30], r13d; ULONG
0x18006c4d0  call    BfeDeviceIoControl
0x18006c4d5  test    rax, rax
0x18006c4d8  jz      short loc_18006C4EB
0x18006c4da  mov     edx, eax; __annotation("Debug", "TelemetryAssert", "WFP_IS_SUCCESS(result)")
0x18006c4dc  lea     rcx, aBfeDll_0; "bfe.dll"
0x18006c4e3  xor     r8d, r8d
0x18006c4e6  call    MicrosoftTelemetryAssertTriggeredArgs
0x18006c4eb  lea     rcx, [rbp+SecurityDescriptor]
0x18006c4ef  call    BfeObjectSecurityDestroy
0x18006c4f4  lea     rdx, aBfesetsecurity; "BfeSetSecurityInfo"
0x18006c4fb  mov     rcx, rdi
0x18006c4fe  call    WfpReportError
0x18006c503  mov     rbx, [rsp+50h+arg_0]
0x18006c50b  mov     rax, rdi
0x18006c50e  add     rsp, 50h
0x18006c512  pop     r15
0x18006c514  pop     r14
0x18006c516  pop     r13
0x18006c518  pop     r12
0x18006c51a  pop     rdi
0x18006c51b  pop     rsi
0x18006c51c  pop     rbp
0x18006c51d  retn
```
