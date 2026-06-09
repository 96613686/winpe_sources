# FwpmvSwitchEventsGetSecurityInfo0

- ea: `0x180057280`
- end: `0x18005738b`
- name: `FwpmvSwitchEventsGetSecurityInfo0`
- size: `267`
- prototype: `__int64 __fastcall(int, int, int, int, PACL *, PACL *, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004904`
- `0x1800050cc`
- `0x180008440`
- `0x180008f10`
- `0x18000fccc`
- `0x180011aa8`
- `0x1800203c0`
- `0x180057280`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1800572c9`
- `ntoskrnl!KeGetCurrentIrql` at `0x1800572c9`

## string_xrefs

- `0x1800572df`: `FwpmvSwitchEventsGetSecurityInfo0`
- `0x18005731a`: `FwppProxyvSwitchEventsGetSecurityInfo`

## pseudocode

```c
__int64 __fastcall FwpmvSwitchEventsGetSecurityInfo0(
        _QWORD *a1,
        unsigned int a2,
        PSID *a3,
        PSID *a4,
        PACL *Dacl,
        PACL *Sacl,
        PSECURITY_DESCRIPTOR *a7)
{
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rax
  int SecurityInfo; // eax
  __int64 v15; // rcx
  __int64 Info; // rbx
  PSECURITY_DESCRIPTOR SecurityDescriptor[2]; // [rsp+30h] [rbp-58h] BYREF

  *(_OWORD *)SecurityDescriptor = 0;
  if ( KeGetCurrentIrql() )
  {
    v12 = 3221225659LL;
LABEL_3:
    v13 = WfpReportAppErrorAsNtStatus(v11, (__int64)"FwpmvSwitchEventsGetSecurityInfo0", v12);
    goto LABEL_9;
  }
  if ( !a1 || !a7 )
  {
    v12 = 3223453724LL;
    goto LABEL_3;
  }
  SecurityInfo = FwppProxyvSwitchEventsGetSecurityInfo(*a1, a1[1], a2, SecurityDescriptor);
  if ( SecurityInfo >= 0 )
  {
    Info = FwppSecurityDescriptorGetInfo(SecurityDescriptor[1], a2, a3, a4, Dacl, Sacl);
    if ( !Info )
    {
      *a7 = SecurityDescriptor[1];
      return WfpErrorToFwpErr(Info);
    }
    goto LABEL_10;
  }
  v13 = WfpReportSysErrorAsNtStatus(v15, (int)"FwppProxyvSwitchEventsGetSecurityInfo", SecurityInfo);
LABEL_9:
  Info = v13;
  if ( v13 )
LABEL_10:
    FwppDeepFree_GUID(SecurityDescriptor[1]);
  return WfpErrorToFwpErr(Info);
}

```

## disassembly

```asm
0x180057280  push    rbx
0x180057282  push    rbp
0x180057283  push    rsi
0x180057284  push    rdi
0x180057285  push    r12
0x180057287  push    r14
0x180057289  push    r15
0x18005728b  sub     rsp, 50h
0x18005728f  mov     rax, cs:__security_cookie
0x180057296  xor     rax, rsp
0x180057299  mov     [rsp+88h+var_48], rax
0x18005729e  mov     r15, [rsp+88h+arg_20]
0x1800572a6  xorps   xmm0, xmm0
0x1800572a9  mov     r12, [rsp+88h+arg_28]
0x1800572b1  mov     r14, r9
0x1800572b4  mov     rdi, [rsp+88h+arg_30]
0x1800572bc  mov     rbp, r8
0x1800572bf  movups  xmmword ptr [rsp+88h+SecurityDescriptor], xmm0
0x1800572c4  mov     esi, edx
0x1800572c6  mov     rbx, rcx
0x1800572c9  call    cs:__imp_KeGetCurrentIrql
0x1800572d0  nop     dword ptr [rax+rax+00h]
0x1800572d5  test    al, al
0x1800572d7  jz      short loc_1800572ED
0x1800572d9  mov     r8d, 0C00000BBh
0x1800572df  lea     rdx, aFwpmvswitcheve; "FwpmvSwitchEventsGetSecurityInfo0"
0x1800572e6  call    WfpReportAppErrorAsNtStatus
0x1800572eb  jmp     short loc_180057326
0x1800572ed  test    rbx, rbx
0x1800572f0  jnz     short loc_1800572FA
0x1800572f2  mov     r8d, 0C022001Ch
0x1800572f8  jmp     short loc_1800572DF
0x1800572fa  test    rdi, rdi
0x1800572fd  jz      short loc_1800572F2
0x1800572ff  mov     rdx, [rbx+8]
0x180057303  lea     r9, [rsp+88h+SecurityDescriptor]
0x180057308  mov     rcx, [rbx]
0x18005730b  mov     r8d, esi
0x18005730e  call    FwppProxyvSwitchEventsGetSecurityInfo
0x180057313  test    eax, eax
0x180057315  jns     short loc_18005735D
0x180057317  mov     r8d, eax
0x18005731a  lea     rdx, aFwppproxyvswit_1; "FwppProxyvSwitchEventsGetSecurityInfo"
0x180057321  call    WfpReportSysErrorAsNtStatus
0x180057326  mov     rbx, rax
0x180057329  test    rax, rax
0x18005732c  jz      short loc_180057338
0x18005732e  mov     rcx, [rsp+88h+SecurityDescriptor+8]
0x180057333  call    FwppDeepFree_GUID
0x180057338  mov     rcx, rbx
0x18005733b  call    WfpErrorToFwpErr
0x180057340  mov     rcx, [rsp+88h+var_48]
0x180057345  xor     rcx, rsp; StackCookie
0x180057348  call    __security_check_cookie
0x18005734d  add     rsp, 50h
0x180057351  pop     r15
0x180057353  pop     r14
0x180057355  pop     r12
0x180057357  pop     rdi
0x180057358  pop     rsi
0x180057359  pop     rbp
0x18005735a  pop     rbx
0x18005735b  retn
0x18005735d  mov     rcx, [rsp+88h+SecurityDescriptor+8]; SecurityDescriptor
0x180057362  mov     r9, r14
0x180057365  mov     [rsp+88h+Sacl], r12; Sacl
0x18005736a  mov     r8, rbp
0x18005736d  mov     edx, esi
0x18005736f  mov     [rsp+88h+Dacl], r15; Dacl
0x180057374  call    FwppSecurityDescriptorGetInfo
0x180057379  mov     rbx, rax
0x18005737c  test    rax, rax
0x18005737f  jnz     short loc_18005732E
0x180057381  mov     rax, [rsp+88h+SecurityDescriptor+8]
0x180057386  mov     [rdi], rax
0x180057389  jmp     short loc_180057338
```
