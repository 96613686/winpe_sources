# FwppAllocAndDeepCopyToVerIndependent_SID

- ea: `0x1800130d8`
- end: `0x1800131aa`
- name: `FwppAllocAndDeepCopyToVerIndependent_SID`
- size: `210`
- prototype: `__int64 __fastcall(PSID SourceSid)`
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18005e550`
- `0x1800611dc`
- `0x180061970`
- `0x180061fbc`
- `0x18006417c`

## callees

- `0x180004904`
- `0x180008480`
- `0x18000891c`
- `0x18000c9b4`
- `0x1800130d8`

## import_xrefs

- `ntoskrnl!RtlCopySid` at `0x180013149`
- `ntoskrnl!RtlCopySid` at `0x180013149`
- `ntoskrnl!RtlLengthSid` at `0x180013115`
- `ntoskrnl!RtlLengthSid` at `0x180013115`
- `ntoskrnl!RtlValidSid` at `0x1800130fa`
- `ntoskrnl!RtlValidSid` at `0x1800130fa`

## string_xrefs

- `0x180013170`: `FwppAllocAndDeepCopyToVerIndependent_SID`
- `0x18001318e`: `FwppAllocAndDeepCopyToVerIndependent_SID`
- `0x18001315c`: `RtlCopySid`

## pseudocode

```c
__int64 __fastcall FwppAllocAndDeepCopyToVerIndependent_SID(PSID SourceSid, _QWORD *a2)
{
  int v4; // r8d
  ULONG v5; // ebp
  __int64 v6; // rcx
  __int64 v7; // rbx
  PSID v8; // r8
  PSID v9; // rdi
  NTSTATUS v10; // eax
  const char *v11; // rdx
  PSID DestinationSid; // [rsp+50h] [rbp+8h] BYREF

  DestinationSid = 0;
  if ( !SourceSid || !a2 )
  {
    v4 = -1071513572;
    goto LABEL_10;
  }
  if ( !RtlValidSid(SourceSid) )
  {
    v4 = -1073741811;
LABEL_10:
    v11 = "FwppAllocAndDeepCopyToVerIndependent_SID";
    goto LABEL_11;
  }
  v5 = RtlLengthSid(SourceSid);
  v7 = WfpPoolAllocNonPaged(v5, 1886418758, &DestinationSid);
  if ( v7 )
  {
LABEL_12:
    WfpNamedPoolFree(v6, &DestinationSid);
    WfpReportError(v7, (int)"FwppAllocAndDeepCopyToVerIndependent_SID");
    return v7;
  }
  v8 = SourceSid;
  v9 = DestinationSid;
  v10 = RtlCopySid(v5, DestinationSid, v8);
  if ( !v10 )
  {
    *a2 = v9;
    return v7;
  }
  v4 = v10;
  v11 = "RtlCopySid";
LABEL_11:
  v7 = WfpReportSysErrorAsNtStatus((__int64)SourceSid, (int)v11, v4);
  if ( v7 )
    goto LABEL_12;
  return v7;
}

```

## disassembly

```asm
0x1800130d8  push    rbx
0x1800130da  push    rbp
0x1800130db  push    rsi
0x1800130dc  push    rdi
0x1800130dd  sub     rsp, 28h
0x1800130e1  mov     [rsp+48h+DestinationSid], 0
0x1800130ea  mov     rsi, rdx
0x1800130ed  mov     rdi, rcx
0x1800130f0  test    rcx, rcx
0x1800130f3  jz      short loc_18001316A
0x1800130f5  test    rdx, rdx
0x1800130f8  jz      short loc_18001316A
0x1800130fa  call    cs:__imp_RtlValidSid
0x180013101  nop     dword ptr [rax+rax+00h]
0x180013106  test    al, al
0x180013108  jnz     short loc_180013112
0x18001310a  mov     r8d, 0C000000Dh
0x180013110  jmp     short loc_180013170
0x180013112  mov     rcx, rdi; Sid
0x180013115  call    cs:__imp_RtlLengthSid
0x18001311c  nop     dword ptr [rax+rax+00h]
0x180013121  mov     ecx, eax
0x180013123  lea     r8, [rsp+48h+DestinationSid]
0x180013128  mov     edx, 70707746h
0x18001312d  mov     ebp, eax
0x18001312f  call    WfpPoolAllocNonPaged
0x180013134  mov     rbx, rax
0x180013137  test    rax, rax
0x18001313a  jnz     short loc_180013184
0x18001313c  mov     r8, rdi; SourceSid
0x18001313f  mov     ecx, ebp; DestinationSidLength
0x180013141  mov     rdi, [rsp+48h+DestinationSid]
0x180013146  mov     rdx, rdi; DestinationSid
0x180013149  call    cs:__imp_RtlCopySid
0x180013150  nop     dword ptr [rax+rax+00h]
0x180013155  test    eax, eax
0x180013157  jz      short loc_180013165
0x180013159  mov     r8d, eax
0x18001315c  lea     rdx, aRtlcopysid; "RtlCopySid"
0x180013163  jmp     short loc_180013177
0x180013165  mov     [rsi], rdi
0x180013168  jmp     short loc_18001319D
0x18001316a  mov     r8d, 0C022001Ch
0x180013170  lea     rdx, aFwppallocandde_84; "FwppAllocAndDeepCopyToVerIndependent_SI"...
0x180013177  call    WfpReportSysErrorAsNtStatus
0x18001317c  mov     rbx, rax
0x18001317f  test    rax, rax
0x180013182  jz      short loc_18001319D
0x180013184  lea     rdx, [rsp+48h+DestinationSid]
0x180013189  call    WfpNamedPoolFree
0x18001318e  lea     rdx, aFwppallocandde_84; "FwppAllocAndDeepCopyToVerIndependent_SI"...
0x180013195  mov     rcx, rbx
0x180013198  call    WfpReportError
0x18001319d  mov     rax, rbx
0x1800131a0  add     rsp, 28h
0x1800131a4  pop     rdi
0x1800131a5  pop     rsi
0x1800131a6  pop     rbp
0x1800131a7  pop     rbx
0x1800131a8  retn
```
