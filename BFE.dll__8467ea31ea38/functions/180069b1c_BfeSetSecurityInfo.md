# BfeSetSecurityInfo

- ea: `0x180069b1c`
- end: `0x180069f2e`
- name: `BfeSetSecurityInfo`
- size: `1042`
- prototype: `__int64 __fastcall(SECURITY_INFORMATION SecurityInformation, PSECURITY_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180062de0`

## callees

- `0x1800083c0`
- `0x180018b74`
- `0x180024b30`
- `0x180034ae0`
- `0x180034f30`
- `0x180034f84`
- `0x180038e90`
- `0x180039c8c`
- `0x18003fa78`
- `0x1800434e0`
- `0x18004352c`
- `0x18004a47c`
- `0x1800557a4`
- `0x180057508`
- `0x180068ec8`
- `0x180069968`
- `0x180069b1c`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x180069d3b`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180069e57`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180069d3b`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180069e57`

## string_xrefs

- `0x180069e8f`: `bfe.dll`
- `0x180069eec`: `bfe.dll`
- `0x180069be7`: `BfeNetEventsPropagateSecurityBegin`
- `0x180069c21`: `BfeConnectionPropagateSecurityBegin`
- `0x180069f04`: `BfeSetSecurityInfo`
- `0x180069cc8`: `BfeSaDbPropagateSecurityBegin`
- `0x180069d74`: `BfeDriverSetEngineSecurityDescriptorBegin`
- `0x180069cfa`: `BfeDospPropagateSecurityBegin`
- `0x180069d2c`: `BfeAlePropagateSecurityBegin`
- `0x180069c50`: `BfevSwitchEventsPropagateSecurityBegin`
- `0x180069c7f`: `BfeVpnTriggerEventsPropagateSecurityBegin`

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
  void *v16; // [rsp+A0h] [rbp+50h] BYREF
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
          v6 = BfeObjectSecurityPropagateBegin(qword_1800F2D50, v4, (__int64)&FWPM_OBJECT_TYPE_CONNECTIONS);
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
              BfeObjectSecurityPropagateCommit(&qword_1800F2D50, v5);
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
0x180069b1c  mov     [rsp-38h+arg_0], rbx
0x180069b21  push    rbp
0x180069b22  push    rsi
0x180069b23  push    rdi
0x180069b24  push    r12
0x180069b26  push    r13
0x180069b28  push    r14
0x180069b2a  push    r15
0x180069b2c  mov     rbp, rsp
0x180069b2f  sub     rsp, 50h
0x180069b33  xor     r13d, r13d
0x180069b36  lea     rax, [rbp+SecurityDescriptor]
0x180069b3a  mov     [rsp+50h+var_28], rax; __int64
0x180069b3f  mov     r9d, ecx; SecurityInformation
0x180069b42  mov     qword ptr [rsp+50h+var_30], rdx; PSECURITY_DESCRIPTOR
0x180069b47  xor     ecx, ecx; ParentDescriptor
0x180069b49  mov     rdx, cs:ParentDescriptor; pSecurityDescriptor
0x180069b50  mov     r12b, r13b
0x180069b53  lea     r8d, [r13+1]; IsContainerObject
0x180069b57  mov     [rbp+SecurityDescriptor], r13
0x180069b5b  mov     [rbp+arg_18], r13
0x180069b5f  mov     [rbp+arg_10], r13
0x180069b63  call    BfeObjectSecuritySetInfo
0x180069b68  mov     rdi, rax
0x180069b6b  test    rax, rax
0x180069b6e  jnz     loc_180069E9E
0x180069b74  lea     rcx, [rbp+arg_18]
0x180069b78  call    BfeObjectSecurityListCreate
0x180069b7d  mov     rdi, rax
0x180069b80  test    rax, rax
0x180069b83  jnz     loc_180069E9E
0x180069b89  lea     rcx, [rbp+arg_10]
0x180069b8d  call    BfeDbTxnCreate
0x180069b92  mov     rdi, rax
0x180069b95  test    rax, rax
0x180069b98  jnz     loc_180069E9E
0x180069b9e  mov     rsi, [rbp+SecurityDescriptor]
0x180069ba2  lea     rdx, FWPM_OBJECT_TYPE_ENGINE
0x180069ba9  mov     rcx, rsi; SecurityDescriptor
0x180069bac  call    BfeObjectSecuritySave
0x180069bb1  mov     rdi, rax
0x180069bb4  test    rax, rax
0x180069bb7  jnz     loc_180069E9E
0x180069bbd  mov     r14, [rbp+arg_18]
0x180069bc1  lea     rax, FWPM_OBJECT_TYPE_NET_EVENTS
0x180069bc8  mov     rcx, cs:CreatorDescriptor; CreatorDescriptor
0x180069bcf  mov     r9, r14
0x180069bd2  mov     rdx, rsi; ParentDescriptor
0x180069bd5  mov     qword ptr [rsp+50h+var_30], rax; __int64
0x180069bda  call    BfeObjectSecurityPropagateBegin
0x180069bdf  mov     rdi, rax
0x180069be2  test    rax, rax
0x180069be5  jz      short loc_180069BFB
0x180069be7  lea     rdx, aBfeneteventspr; "BfeNetEventsPropagateSecurityBegin"
0x180069bee  mov     rcx, rax
0x180069bf1  call    WfpReportError
0x180069bf6  jmp     loc_180069E9E
0x180069bfb  mov     rcx, cs:qword_1800F2D50; CreatorDescriptor
0x180069c02  lea     rax, FWPM_OBJECT_TYPE_CONNECTIONS
0x180069c09  mov     r9, r14
0x180069c0c  mov     qword ptr [rsp+50h+var_30], rax; __int64
0x180069c11  mov     rdx, rsi; ParentDescriptor
0x180069c14  call    BfeObjectSecurityPropagateBegin
0x180069c19  mov     rdi, rax
0x180069c1c  test    rax, rax
0x180069c1f  jz      short loc_180069C2A
0x180069c21  lea     rdx, aBfeconnectionp; "BfeConnectionPropagateSecurityBegin"
0x180069c28  jmp     short loc_180069BEE
0x180069c2a  mov     rcx, qword ptr cs:gBfevSwitchEventController; CreatorDescriptor
0x180069c31  lea     rax, FWPM_OBJECT_TYPE_VSWITCH_EVENTS
0x180069c38  mov     r9, r14
0x180069c3b  mov     qword ptr [rsp+50h+var_30], rax; __int64
0x180069c40  mov     rdx, rsi; ParentDescriptor
0x180069c43  call    BfeObjectSecurityPropagateBegin
0x180069c48  mov     rdi, rax
0x180069c4b  test    rax, rax
0x180069c4e  jz      short loc_180069C59
0x180069c50  lea     rdx, aBfevswitcheven_8; "BfevSwitchEventsPropagateSecurityBegin"
0x180069c57  jmp     short loc_180069BEE
0x180069c59  mov     rcx, qword ptr cs:gBfeVpnTriggerEventController; CreatorDescriptor
0x180069c60  lea     rax, FWPM_OBJECT_TYPE_VPN_TRIGGER_EVENTS
0x180069c67  mov     r9, r14
0x180069c6a  mov     qword ptr [rsp+50h+var_30], rax; __int64
0x180069c6f  mov     rdx, rsi; ParentDescriptor
0x180069c72  call    BfeObjectSecurityPropagateBegin
0x180069c77  mov     rdi, rax
0x180069c7a  test    rax, rax
0x180069c7d  jz      short loc_180069C8B
0x180069c7f  lea     rdx, aBfevpntriggere_4; "BfeVpnTriggerEventsPropagateSecurityBeg"...
0x180069c86  jmp     loc_180069BEE
0x180069c8b  mov     rdx, r14
0x180069c8e  mov     rcx, rsi; ParentDescriptor
0x180069c91  call    BfeObjectPropagateSecurityBegin
0x180069c96  mov     rdi, rax
0x180069c99  test    rax, rax
0x180069c9c  jnz     loc_180069E9E
0x180069ca2  mov     rcx, cs:pSecurityDescriptor; CreatorDescriptor
0x180069ca9  lea     rax, FWPM_OBJECT_TYPE_IPSEC_SA_DB
0x180069cb0  mov     r9, r14
0x180069cb3  mov     qword ptr [rsp+50h+var_30], rax; __int64
0x180069cb8  mov     rdx, rsi; ParentDescriptor
0x180069cbb  call    BfeObjectSecurityPropagateBegin
0x180069cc0  mov     rdi, rax
0x180069cc3  test    rax, rax
0x180069cc6  jz      short loc_180069CD4
0x180069cc8  lea     rdx, aBfesadbpropaga; "BfeSaDbPropagateSecurityBegin"
0x180069ccf  jmp     loc_180069BEE
0x180069cd4  mov     rcx, cs:gBfeDospComponent; CreatorDescriptor
0x180069cdb  lea     rax, FWPM_OBJECT_TYPE_IPSEC_DOSP
0x180069ce2  mov     r9, r14
0x180069ce5  mov     qword ptr [rsp+50h+var_30], rax; __int64
0x180069cea  mov     rdx, rsi; ParentDescriptor
0x180069ced  call    BfeObjectSecurityPropagateBegin
0x180069cf2  mov     rdi, rax
0x180069cf5  test    rax, rax
0x180069cf8  jz      short loc_180069D06
0x180069cfa  lea     rdx, aBfedosppropaga; "BfeDospPropagateSecurityBegin"
0x180069d01  jmp     loc_180069BEE
0x180069d06  mov     rcx, cs:gBfeAleComponent; CreatorDescriptor
0x180069d0d  lea     rax, FWPM_OBJECT_TYPE_ALE
0x180069d14  mov     r9, r14
0x180069d17  mov     qword ptr [rsp+50h+var_30], rax; __int64
0x180069d1c  mov     rdx, rsi; ParentDescriptor
0x180069d1f  call    BfeObjectSecurityPropagateBegin
0x180069d24  mov     rdi, rax
0x180069d27  test    rax, rax
0x180069d2a  jz      short loc_180069D38
0x180069d2c  lea     rdx, aBfealepropagat; "BfeAlePropagateSecurityBegin"
0x180069d33  jmp     loc_180069BEE
0x180069d38  mov     rcx, rsi; SecurityDescriptor
0x180069d3b  call    cs:__imp_RtlLengthSecurityDescriptor
0x180069d41  mov     rcx, cs:gBfeDriverControlComponent; FileHandle
0x180069d48  mov     r9, rsi; InputBuffer
0x180069d4b  mov     [rsp+50h+var_18], r13; __int64
0x180069d50  mov     r8d, eax; InputBufferLength
0x180069d53  mov     [rsp+50h+var_20], r13; __int64
0x180069d58  mov     edx, 124048h; IoControlCode
0x180069d5d  mov     [rsp+50h+var_28], r13; PVOID
0x180069d62  mov     [rsp+50h+var_30], r13d; ULONG
0x180069d67  call    BfeDeviceIoControl
0x180069d6c  mov     rdi, rax
0x180069d6f  test    rax, rax
0x180069d72  jz      short loc_180069D80
0x180069d74  lea     rdx, aBfedriverseten; "BfeDriverSetEngineSecurityDescriptorBeg"...
0x180069d7b  jmp     loc_180069BEE
0x180069d80  mov     rcx, [rbp+arg_10]
0x180069d84  mov     r12b, 1
0x180069d87  call    BfeDbTxnCommit
0x180069d8c  mov     rdi, rax
0x180069d8f  test    rax, rax
0x180069d92  jnz     loc_180069E9E
0x180069d98  lea     rcx, ParentDescriptor
0x180069d9f  call    BfeObjectSecurityDestroy
0x180069da4  mov     rdx, r14
0x180069da7  mov     cs:ParentDescriptor, rsi
0x180069dae  lea     rcx, CreatorDescriptor
0x180069db5  call    BfeObjectSecurityPropagateCommit
0x180069dba  mov     rdx, r14
0x180069dbd  lea     rcx, qword_1800F2D50
0x180069dc4  call    BfeObjectSecurityPropagateCommit
0x180069dc9  mov     rdx, r14
0x180069dcc  lea     rcx, gBfevSwitchEventController
0x180069dd3  call    BfeObjectSecurityPropagateCommit
0x180069dd8  mov     rdx, r14
0x180069ddb  lea     rcx, gBfeVpnTriggerEventController
0x180069de2  call    BfeObjectSecurityPropagateCommit
0x180069de7  mov     r15, r13
0x180069dea  imul    rbx, r15, 198h
0x180069df1  mov     rdx, r14
0x180069df4  add     rbx, cs:gBfeObjMgr
0x180069dfb  mov     rcx, rbx
0x180069dfe  call    BfeObjectPropagateSecurityByTypeCommit
0x180069e03  lea     rcx, [rbx+158h]
0x180069e0a  call    BfeObjectSecurityDestroy
0x180069e0f  mov     rcx, r14
0x180069e12  call    BfeObjectSecurityListPopFront
0x180069e17  inc     r15
0x180069e1a  mov     [rbx+158h], rax
0x180069e21  cmp     r15, 7
0x180069e25  jnz     short loc_180069DEA
0x180069e27  mov     rdx, r14
0x180069e2a  lea     rcx, pSecurityDescriptor
0x180069e31  call    BfeObjectSecurityPropagateCommit
0x180069e36  mov     rdx, r14
0x180069e39  lea     rcx, gBfeDospComponent
0x180069e40  call    BfeObjectSecurityPropagateCommit
0x180069e45  mov     rdx, r14
0x180069e48  lea     rcx, gBfeAleComponent
0x180069e4f  call    BfeObjectSecurityPropagateCommit
0x180069e54  mov     rcx, rsi; SecurityDescriptor
0x180069e57  call    cs:__imp_RtlLengthSecurityDescriptor
0x180069e5d  mov     rcx, cs:gBfeDriverControlComponent; FileHandle
0x180069e64  mov     r9, rsi; InputBuffer
0x180069e67  mov     [rsp+50h+var_18], r13; __int64
0x180069e6c  mov     r8d, eax; InputBufferLength
0x180069e6f  mov     [rsp+50h+var_20], r13; __int64
0x180069e74  mov     edx, 12404Ch; IoControlCode
0x180069e79  mov     [rsp+50h+var_28], r13; PVOID
0x180069e7e  mov     [rsp+50h+var_30], r13d; ULONG
0x180069e83  call    BfeDeviceIoControl
0x180069e88  test    rax, rax
0x180069e8b  jz      short loc_180069E9E
0x180069e8d  mov     edx, eax
0x180069e8f  lea     rcx, aBfeDll_0; "bfe.dll"
0x180069e96  xor     r8d, r8d
0x180069e99  call    MicrosoftTelemetryAssertTriggeredArgs
0x180069e9e  lea     rcx, [rbp+arg_10]
0x180069ea2  call    BfeDbTxnDestroy
0x180069ea7  lea     rcx, [rbp+arg_18]
0x180069eab  call    BfeObjectSecurityListDestroy
0x180069eb0  test    rdi, rdi
0x180069eb3  jz      short loc_180069F13
0x180069eb5  test    r12b, r12b
0x180069eb8  jz      short loc_180069EFB
0x180069eba  mov     rcx, cs:gBfeDriverControlComponent; FileHandle
0x180069ec1  xor     r9d, r9d; InputBuffer
0x180069ec4  mov     [rsp+50h+var_18], r13; __int64
0x180069ec9  xor     r8d, r8d; InputBufferLength
0x180069ecc  mov     [rsp+50h+var_20], r13; __int64
0x180069ed1  mov     edx, 124050h; IoControlCode
0x180069ed6  mov     [rsp+50h+var_28], r13; PVOID
0x180069edb  mov     [rsp+50h+var_30], r13d; ULONG
0x180069ee0  call    BfeDeviceIoControl
0x180069ee5  test    rax, rax
0x180069ee8  jz      short loc_180069EFB
0x180069eea  mov     edx, eax
0x180069eec  lea     rcx, aBfeDll_0; "bfe.dll"
0x180069ef3  xor     r8d, r8d
0x180069ef6  call    MicrosoftTelemetryAssertTriggeredArgs
0x180069efb  lea     rcx, [rbp+SecurityDescriptor]
0x180069eff  call    BfeObjectSecurityDestroy
0x180069f04  lea     rdx, aBfesetsecurity; "BfeSetSecurityInfo"
0x180069f0b  mov     rcx, rdi
0x180069f0e  call    WfpReportError
0x180069f13  mov     rbx, [rsp+50h+arg_0]
0x180069f1b  mov     rax, rdi
0x180069f1e  add     rsp, 50h
0x180069f22  pop     r15
0x180069f24  pop     r14
0x180069f26  pop     r13
0x180069f28  pop     r12
0x180069f2a  pop     rdi
0x180069f2b  pop     rsi
0x180069f2c  pop     rbp
0x180069f2d  retn
```
