# BfeVpnTriggerInitializeNrptTrigger

- ea: `0x180074760`
- end: `0x18007497a`
- name: `BfeVpnTriggerInitializeNrptTrigger`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180066770`

## callees

- `0x180004810`
- `0x18000e7e0`
- `0x180010d60`
- `0x180012d8c`
- `0x1800197d0`
- `0x180020690`
- `0x180024e40`
- `0x18005aa60`
- `0x18005b4fc`
- `0x1800743f8`
- `0x180074760`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800747c4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800747c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007492f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007492f`
- `RPCRT4!UuidCreate` at `0x1800747f8`
- `RPCRT4!UuidCreate` at `0x1800747f8`

## string_xrefs

- `0x18007480b`: `UuidCreate`

## pseudocode

```c
__int64 __fastcall BfeVpnTriggerInitializeNrptTrigger(__int64 a1)
{
  __int64 v2; // rbx
  __int64 v3; // rax
  unsigned int v4; // eax
  __int64 v5; // rcx
  __int64 v6; // rax
  _OWORD *v7; // rax
  int v9; // [rsp+30h] [rbp-D0h]
  _OWORD *v10; // [rsp+40h] [rbp-C0h]
  __int64 v11; // [rsp+48h] [rbp-B8h]
  _OWORD *v12; // [rsp+50h] [rbp-B0h]
  UUID Uuid; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD v14[5]; // [rsp+70h] [rbp-90h] BYREF
  __int16 v15; // [rsp+C0h] [rbp-40h]
  _OWORD v16[3]; // [rsp+C2h] [rbp-3Eh] BYREF
  _BYTE v17[30]; // [rsp+F2h] [rbp-Eh]

  LODWORD(v12) = 0;
  v11 = 0;
  v10 = 0;
  Uuid = 0;
  v2 = BfeAccessCheck((char *)qword_1800F5860, 0x400u, 0);
  if ( v2 )
    goto LABEL_13;
  AcquireSRWLockExclusive(&nrptTriggerLock);
  if ( nrptTriggerEventName )
    goto LABEL_3;
  memset_0(v14, 0, sizeof(v14));
  v4 = UuidCreate(&Uuid);
  if ( v4 )
  {
    v3 = WfpReportSysErrorAsWinError(v5, "UuidCreate", v4);
    goto LABEL_6;
  }
  BfeGuidToString(&Uuid, v16);
  v14[0] = xmmword_1800CFE80;
  v14[2] = xmmword_1800CFEA0;
  v14[1] = xmmword_1800CFE90;
  v15 = 95;
  v14[4] = xmmword_1800CFEC0;
  v14[3] = xmmword_1800CFEB0;
  LODWORD(v11) = 160;
  v12 = v14;
  if ( gBfeDriverControlComponent == (HANDLE)-1LL
    || (v6 = BfeDeviceIoControlMarshalIn(gBfeDriverControlComponent, 0x12806Cu, 0, 0, v9, 0), (v2 = v6) == 0) )
  {
    v2 = WfpMemAlloc(0x4Eu, 8u);
    if ( !v2 )
    {
      v7 = v10;
      v10 = 0;
      *v7 = v16[0];
      v7[1] = v16[1];
      v7[2] = v16[2];
      v7[3] = *(_OWORD *)v17;
      *(_OWORD *)((char *)v7 + 62) = *(_OWORD *)&v17[14];
      nrptTriggerEventName = (__int64)v7;
LABEL_3:
      v3 = BfeVpnTriggerCopyNrptTriggerEventName(a1);
LABEL_6:
      v2 = v3;
    }
  }
  else
  {
    WfpReportError(v6, "BfeDriverVpnTriggerInitializeNrptTrigger");
  }
  ReleaseSRWLockExclusive(&nrptTriggerLock);
  if ( v2 )
LABEL_13:
    WfpReportError(v2, "BfeVpnTriggerInitializeNrptTrigger");
  return v2;
}

```

## disassembly

```asm
0x180074760  push    rbp
0x180074762  push    rbx
0x180074763  push    rsi
0x180074764  push    rdi
0x180074765  lea     rbp, [rsp-28h]
0x18007476a  sub     rsp, 128h
0x180074771  mov     rax, cs:__security_cookie
0x180074778  xor     rax, rsp
0x18007477b  mov     [rbp+40h+var_30], rax
0x18007477f  xor     eax, eax
0x180074781  mov     rsi, rcx
0x180074784  mov     rcx, cs:qword_1800F5860; pSecurityDescriptor
0x18007478b  xorps   xmm0, xmm0
0x18007478e  mov     qword ptr [rsp+140h+var_F4], rax
0x180074793  xor     edi, edi
0x180074795  xor     r8d, r8d
0x180074798  mov     [rsp+48h], rax
0x18007479d  mov     edx, 400h
0x1800747a2  mov     [rsp+140h+var_100], rdi
0x1800747a7  movups  xmmword ptr [rsp+140h+Uuid.Data1], xmm0
0x1800747ac  call    BfeAccessCheck
0x1800747b1  mov     rbx, rax
0x1800747b4  test    rax, rax
0x1800747b7  jnz     loc_18007494F
0x1800747bd  lea     rcx, nrptTriggerLock; SRWLock
0x1800747c4  call    cs:__imp_AcquireSRWLockExclusive
0x1800747cb  nop     dword ptr [rax+rax+00h]
0x1800747d0  cmp     cs:nrptTriggerEventName, rdi
0x1800747d7  jz      short loc_1800747E3
0x1800747d9  mov     rcx, rsi
0x1800747dc  call    BfeVpnTriggerCopyNrptTriggerEventName
0x1800747e1  jmp     short loc_180074817
0x1800747e3  xor     edx, edx; Val
0x1800747e5  lea     rcx, [rsp+140h+var_D0]; void *
0x1800747ea  lea     r8d, [rdx+50h]; Size
0x1800747ee  call    memset_0
0x1800747f3  lea     rcx, [rsp+140h+Uuid]; Uuid
0x1800747f8  call    cs:__imp_UuidCreate
0x1800747ff  nop     dword ptr [rax+rax+00h]
0x180074804  test    eax, eax
0x180074806  jz      short loc_18007481F
0x180074808  mov     r8d, eax
0x18007480b  lea     rdx, aUuidcreate; "UuidCreate"
0x180074812  call    WfpReportSysErrorAsWinError
0x180074817  mov     rbx, rax
0x18007481a  jmp     loc_180074928
0x18007481f  lea     rdx, [rbp+40h+var_7E]
0x180074823  lea     rcx, [rsp+140h+Uuid]
0x180074828  call    BfeGuidToString
0x18007482d  movaps  xmm0, cs:xmmword_1800CFE80
0x180074834  movaps  xmm1, cs:xmmword_1800CFE90
0x18007483b  movzx   eax, cs:word_1800CFED0
0x180074842  mov     rcx, cs:gBfeDriverControlComponent; FileHandle
0x180074849  movaps  [rsp+140h+var_D0], xmm0
0x18007484e  movaps  xmm0, cs:xmmword_1800CFEA0
0x180074855  movaps  [rbp+40h+var_B0], xmm0
0x180074859  movaps  xmm0, cs:xmmword_1800CFEC0
0x180074860  movaps  [rbp+40h+var_C0], xmm1
0x180074864  movaps  xmm1, cs:xmmword_1800CFEB0
0x18007486b  mov     [rbp+40h+var_80], ax
0x18007486f  lea     rax, [rsp+140h+var_D0]
0x180074874  movaps  [rbp+40h+var_90], xmm0
0x180074878  movaps  [rbp+40h+var_A0], xmm1
0x18007487c  mov     [rsp+140h+var_F8], 0A0h
0x180074884  mov     qword ptr [rsp+140h+var_F4+4], rax
0x180074889  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18007488d  jz      short loc_1800748CC
0x18007488f  mov     [rsp+140h+var_108], rdi; __int64
0x180074894  lea     r9, [rsp+140h+var_F8]
0x180074899  mov     [rsp+140h+var_118], rdi; PVOID
0x18007489e  lea     r8, WFP_DRIVER_VPN_NRPT_TRIGGER_INIT_IOCTL_Encode
0x1800748a5  mov     edx, 12806Ch; IoControlCode
0x1800748aa  mov     [rsp+140h+var_120], edi; ULONG
0x1800748ae  call    BfeDeviceIoControlMarshalIn
0x1800748b3  mov     rbx, rax
0x1800748b6  test    rax, rax
0x1800748b9  jz      short loc_1800748CC
0x1800748bb  lea     rdx, aBfedrivervpntr_2; "BfeDriverVpnTriggerInitializeNrptTrigge"...
0x1800748c2  mov     rcx, rax
0x1800748c5  call    WfpReportError
0x1800748ca  jmp     short loc_180074928
0x1800748cc  mov     edx, 8; dwFlags
0x1800748d1  lea     r8, [rsp+140h+var_100]
0x1800748d6  lea     ecx, [rdx+46h]; dwBytes
0x1800748d9  call    WfpMemAlloc
0x1800748de  mov     rbx, rax
0x1800748e1  test    rax, rax
0x1800748e4  jnz     short loc_180074923
0x1800748e6  mov     rax, [rsp+140h+var_100]
0x1800748eb  movups  xmm0, [rbp+40h+var_7E]
0x1800748ef  mov     [rsp+140h+var_100], rdi
0x1800748f4  movups  xmmword ptr [rax], xmm0
0x1800748f7  movups  xmm1, [rbp+40h+var_6E]
0x1800748fb  movups  xmmword ptr [rax+10h], xmm1
0x1800748ff  movups  xmm0, [rbp+40h+var_5E]
0x180074903  movups  xmmword ptr [rax+20h], xmm0
0x180074907  movups  xmm1, xmmword ptr [rbp+40h+var_4E]
0x18007490b  movups  xmmword ptr [rax+30h], xmm1
0x18007490f  movups  xmm0, xmmword ptr [rbp+40h+var_4E+0Eh]
0x180074913  movups  xmmword ptr [rax+3Eh], xmm0
0x180074917  mov     cs:nrptTriggerEventName, rax
0x18007491e  jmp     loc_1800747D9
0x180074923  mov     rdi, [rsp+140h+var_100]
0x180074928  lea     rcx, nrptTriggerLock; SRWLock
0x18007492f  call    cs:__imp_ReleaseSRWLockExclusive
0x180074936  nop     dword ptr [rax+rax+00h]
0x18007493b  test    rbx, rbx
0x18007493e  jz      short loc_18007495E
0x180074940  test    rdi, rdi
0x180074943  jz      short loc_18007494F
0x180074945  lea     rcx, [rsp+140h+var_100]
0x18007494a  call    WfpMemFree
0x18007494f  lea     rdx, aBfevpntriggeri; "BfeVpnTriggerInitializeNrptTrigger"
0x180074956  mov     rcx, rbx
0x180074959  call    WfpReportError
0x18007495e  mov     rax, rbx
0x180074961  mov     rcx, [rbp+40h+var_30]
0x180074965  xor     rcx, rsp; StackCookie
0x180074968  call    __security_check_cookie
0x18007496d  add     rsp, 128h
0x180074974  pop     rdi
0x180074975  pop     rsi
0x180074976  pop     rbx
0x180074977  pop     rbp
0x180074978  retn
```
