# BfeVpnTriggerInitializeNrptTrigger

- ea: `0x180071ef0`
- end: `0x1800720f7`
- name: `BfeVpnTriggerInitializeNrptTrigger`
- size: `519`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180064400`

## callees

- `0x1800047b8`
- `0x18000e000`
- `0x180010360`
- `0x18001236c`
- `0x180018b74`
- `0x180022730`
- `0x180024a44`
- `0x180058b30`
- `0x1800595ac`
- `0x180071ba4`
- `0x180071ef0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180071f54`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180071f54`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800720b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800720b3`
- `RPCRT4!UuidCreate` at `0x180071f82`
- `RPCRT4!UuidCreate` at `0x180071f82`

## string_xrefs

- `0x180071f8f`: `UuidCreate`

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
  v2 = BfeAccessCheck((char *)qword_1800F2840, 0x400u, 0);
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
  v14[0] = xmmword_1800CCEC0;
  v14[2] = xmmword_1800CCEE0;
  v14[1] = xmmword_1800CCED0;
  v15 = 95;
  v14[4] = xmmword_1800CCF00;
  v14[3] = xmmword_1800CCEF0;
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
0x180071ef0  push    rbp
0x180071ef2  push    rbx
0x180071ef3  push    rsi
0x180071ef4  push    rdi
0x180071ef5  lea     rbp, [rsp-28h]
0x180071efa  sub     rsp, 128h
0x180071f01  mov     rax, cs:__security_cookie
0x180071f08  xor     rax, rsp
0x180071f0b  mov     [rbp+40h+var_30], rax
0x180071f0f  xor     eax, eax
0x180071f11  mov     rsi, rcx
0x180071f14  mov     rcx, cs:qword_1800F2840; pSecurityDescriptor
0x180071f1b  xorps   xmm0, xmm0
0x180071f1e  mov     qword ptr [rsp+140h+var_F4], rax
0x180071f23  xor     edi, edi
0x180071f25  xor     r8d, r8d
0x180071f28  mov     [rsp+48h], rax
0x180071f2d  mov     edx, 400h
0x180071f32  mov     [rsp+140h+var_100], rdi
0x180071f37  movups  xmmword ptr [rsp+140h+Uuid.Data1], xmm0
0x180071f3c  call    BfeAccessCheck
0x180071f41  mov     rbx, rax
0x180071f44  test    rax, rax
0x180071f47  jnz     loc_1800720CD
0x180071f4d  lea     rcx, nrptTriggerLock; SRWLock
0x180071f54  call    cs:__imp_AcquireSRWLockExclusive
0x180071f5a  cmp     cs:nrptTriggerEventName, rdi
0x180071f61  jz      short loc_180071F6D
0x180071f63  mov     rcx, rsi
0x180071f66  call    BfeVpnTriggerCopyNrptTriggerEventName
0x180071f6b  jmp     short loc_180071F9B
0x180071f6d  xor     edx, edx; Val
0x180071f6f  lea     rcx, [rsp+140h+var_D0]; void *
0x180071f74  lea     r8d, [rdx+50h]; Size
0x180071f78  call    memset_0
0x180071f7d  lea     rcx, [rsp+140h+Uuid]; Uuid
0x180071f82  call    cs:__imp_UuidCreate
0x180071f88  test    eax, eax
0x180071f8a  jz      short loc_180071FA3
0x180071f8c  mov     r8d, eax
0x180071f8f  lea     rdx, aUuidcreate; "UuidCreate"
0x180071f96  call    WfpReportSysErrorAsWinError
0x180071f9b  mov     rbx, rax
0x180071f9e  jmp     loc_1800720AC
0x180071fa3  lea     rdx, [rbp+40h+var_7E]
0x180071fa7  lea     rcx, [rsp+140h+Uuid]
0x180071fac  call    BfeGuidToString
0x180071fb1  movaps  xmm0, cs:xmmword_1800CCEC0
0x180071fb8  movaps  xmm1, cs:xmmword_1800CCED0
0x180071fbf  movzx   eax, cs:word_1800CCF10
0x180071fc6  mov     rcx, cs:gBfeDriverControlComponent; FileHandle
0x180071fcd  movaps  [rsp+140h+var_D0], xmm0
0x180071fd2  movaps  xmm0, cs:xmmword_1800CCEE0
0x180071fd9  movaps  [rbp+40h+var_B0], xmm0
0x180071fdd  movaps  xmm0, cs:xmmword_1800CCF00
0x180071fe4  movaps  [rbp+40h+var_C0], xmm1
0x180071fe8  movaps  xmm1, cs:xmmword_1800CCEF0
0x180071fef  mov     [rbp+40h+var_80], ax
0x180071ff3  lea     rax, [rsp+140h+var_D0]
0x180071ff8  movaps  [rbp+40h+var_90], xmm0
0x180071ffc  movaps  [rbp+40h+var_A0], xmm1
0x180072000  mov     [rsp+140h+var_F8], 0A0h
0x180072008  mov     qword ptr [rsp+140h+var_F4+4], rax
0x18007200d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180072011  jz      short loc_180072050
0x180072013  mov     [rsp+140h+var_108], rdi; __int64
0x180072018  lea     r9, [rsp+140h+var_F8]
0x18007201d  mov     [rsp+140h+var_118], rdi; PVOID
0x180072022  lea     r8, WFP_DRIVER_VPN_NRPT_TRIGGER_INIT_IOCTL_Encode
0x180072029  mov     edx, 12806Ch; IoControlCode
0x18007202e  mov     [rsp+140h+var_120], edi; ULONG
0x180072032  call    BfeDeviceIoControlMarshalIn
0x180072037  mov     rbx, rax
0x18007203a  test    rax, rax
0x18007203d  jz      short loc_180072050
0x18007203f  lea     rdx, aBfedrivervpntr_2; "BfeDriverVpnTriggerInitializeNrptTrigge"...
0x180072046  mov     rcx, rax
0x180072049  call    WfpReportError
0x18007204e  jmp     short loc_1800720AC
0x180072050  mov     edx, 8; dwFlags
0x180072055  lea     r8, [rsp+140h+var_100]
0x18007205a  lea     ecx, [rdx+46h]; dwBytes
0x18007205d  call    WfpMemAlloc
0x180072062  mov     rbx, rax
0x180072065  test    rax, rax
0x180072068  jnz     short loc_1800720A7
0x18007206a  mov     rax, [rsp+140h+var_100]
0x18007206f  movups  xmm0, [rbp+40h+var_7E]
0x180072073  mov     [rsp+140h+var_100], rdi
0x180072078  movups  xmmword ptr [rax], xmm0
0x18007207b  movups  xmm1, [rbp+40h+var_6E]
0x18007207f  movups  xmmword ptr [rax+10h], xmm1
0x180072083  movups  xmm0, [rbp+40h+var_5E]
0x180072087  movups  xmmword ptr [rax+20h], xmm0
0x18007208b  movups  xmm1, xmmword ptr [rbp+40h+var_4E]
0x18007208f  movups  xmmword ptr [rax+30h], xmm1
0x180072093  movups  xmm0, xmmword ptr [rbp+40h+var_4E+0Eh]
0x180072097  movups  xmmword ptr [rax+3Eh], xmm0
0x18007209b  mov     cs:nrptTriggerEventName, rax
0x1800720a2  jmp     loc_180071F63
0x1800720a7  mov     rdi, [rsp+140h+var_100]
0x1800720ac  lea     rcx, nrptTriggerLock; SRWLock
0x1800720b3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800720b9  test    rbx, rbx
0x1800720bc  jz      short loc_1800720DC
0x1800720be  test    rdi, rdi
0x1800720c1  jz      short loc_1800720CD
0x1800720c3  lea     rcx, [rsp+140h+var_100]
0x1800720c8  call    WfpMemFree
0x1800720cd  lea     rdx, aBfevpntriggeri; "BfeVpnTriggerInitializeNrptTrigger"
0x1800720d4  mov     rcx, rbx
0x1800720d7  call    WfpReportError
0x1800720dc  mov     rax, rbx
0x1800720df  mov     rcx, [rbp+40h+var_30]
0x1800720e3  xor     rcx, rsp; StackCookie
0x1800720e6  call    __security_check_cookie
0x1800720eb  add     rsp, 128h
0x1800720f2  pop     rdi
0x1800720f3  pop     rsi
0x1800720f4  pop     rbx
0x1800720f5  pop     rbp
0x1800720f6  retn
```
