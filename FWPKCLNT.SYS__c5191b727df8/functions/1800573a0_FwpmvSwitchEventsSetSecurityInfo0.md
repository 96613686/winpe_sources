# FwpmvSwitchEventsSetSecurityInfo0

- ea: `0x1800573a0`
- end: `0x1800574b9`
- name: `FwpmvSwitchEventsSetSecurityInfo0`
- size: `281`
- prototype: `__int64 __fastcall(int, int, int, int, PACL, PACL)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180004904`
- `0x1800050cc`
- `0x1800083f8`
- `0x1800086fc`
- `0x180008f10`
- `0x18000fe2c`
- `0x180011ae8`
- `0x1800203c0`
- `0x1800573a0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1800573f3`
- `ntoskrnl!KeGetCurrentIrql` at `0x1800573f3`

## string_xrefs

- `0x180057409`: `FwpmvSwitchEventsSetSecurityInfo0`
- `0x18005747a`: `FwppProxyvSwitchEventsSetSecurityInfo`

## pseudocode

```c
__int64 __fastcall FwpmvSwitchEventsSetSecurityInfo0(
        _QWORD *a1,
        unsigned int a2,
        void *a3,
        void *a4,
        PACL Dacl,
        PACL Sacl)
{
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 v13; // rbx
  int v14; // eax
  __int64 v15; // rcx
  PVOID v17; // [rsp+30h] [rbp-50h] BYREF
  __int64 v18; // [rsp+38h] [rbp-48h] BYREF
  int v19; // [rsp+40h] [rbp-40h]
  _OWORD SecurityDescriptor[2]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v21; // [rsp+68h] [rbp-18h]

  v19 = 0;
  v18 = 0;
  v21 = 0;
  v17 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  if ( KeGetCurrentIrql() )
  {
    v11 = 3221225659LL;
LABEL_3:
    v12 = WfpReportAppErrorAsNtStatus(v10, (__int64)"FwpmvSwitchEventsSetSecurityInfo0", v11);
LABEL_10:
    v13 = v12;
    goto LABEL_11;
  }
  if ( !a1 )
  {
    v11 = 3223453724LL;
    goto LABEL_3;
  }
  v13 = FwppSecurityDescriptorSetInfo(SecurityDescriptor, a2, a3, a4, Dacl, Sacl);
  if ( !v13 )
  {
    v13 = BfeSecurityDescriptorEncode(SecurityDescriptor, (__int64)&v18, &v17);
    if ( !v13 )
    {
      v14 = FwppProxyvSwitchEventsSetSecurityInfo(*a1, a1[1], a2, &v18);
      if ( v14 < 0 )
      {
        v12 = WfpReportSysErrorAsNtStatus(v15, (int)"FwppProxyvSwitchEventsSetSecurityInfo", v14);
        goto LABEL_10;
      }
    }
  }
LABEL_11:
  BfeSecurityDescriptorStorageFree(&v17);
  return WfpErrorToFwpErr(v13);
}

```

## disassembly

```asm
0x1800573a0  push    rbp
0x1800573a2  push    rbx
0x1800573a3  push    rsi
0x1800573a4  push    rdi
0x1800573a5  push    r12
0x1800573a7  push    r14
0x1800573a9  push    r15
0x1800573ab  mov     rbp, rsp
0x1800573ae  sub     rsp, 80h
0x1800573b5  mov     rax, cs:__security_cookie
0x1800573bc  xor     rax, rsp
0x1800573bf  mov     [rbp+var_10], rax
0x1800573c3  mov     r15, [rbp+arg_20]
0x1800573c7  xor     eax, eax
0x1800573c9  mov     r12, [rbp+arg_28]
0x1800573cd  xorps   xmm0, xmm0
0x1800573d0  mov     [rbp+var_44], rax
0x1800573d4  mov     r14, r9
0x1800573d7  mov     [rbp-48h], rax
0x1800573db  mov     rbx, r8
0x1800573de  mov     esi, edx
0x1800573e0  mov     [rbp+var_18], rax
0x1800573e4  mov     rdi, rcx
0x1800573e7  mov     [rbp+var_50], rax
0x1800573eb  movups  [rbp+SecurityDescriptor], xmm0
0x1800573ef  movups  [rbp+var_28], xmm0
0x1800573f3  call    cs:__imp_KeGetCurrentIrql
0x1800573fa  nop     dword ptr [rax+rax+00h]
0x1800573ff  test    al, al
0x180057401  jz      short loc_180057417
0x180057403  mov     r8d, 0C00000BBh
0x180057409  lea     rdx, aFwpmvswitcheve_1; "FwpmvSwitchEventsSetSecurityInfo0"
0x180057410  call    WfpReportAppErrorAsNtStatus
0x180057415  jmp     short loc_180057486
0x180057417  test    rdi, rdi
0x18005741a  jnz     short loc_180057424
0x18005741c  mov     r8d, 0C022001Ch
0x180057422  jmp     short loc_180057409
0x180057424  mov     [rsp+80h+Sacl], r12; Sacl
0x180057429  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18005742d  mov     r9, r14
0x180057430  mov     [rsp+80h+Dacl], r15; Dacl
0x180057435  mov     r8, rbx
0x180057438  mov     edx, esi
0x18005743a  call    FwppSecurityDescriptorSetInfo
0x18005743f  mov     rbx, rax
0x180057442  test    rax, rax
0x180057445  jnz     short loc_180057489
0x180057447  lea     r8, [rbp+var_50]
0x18005744b  lea     rdx, [rbp+var_48]
0x18005744f  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x180057453  call    BfeSecurityDescriptorEncode
0x180057458  mov     rbx, rax
0x18005745b  test    rax, rax
0x18005745e  jnz     short loc_180057489
0x180057460  mov     rdx, [rdi+8]
0x180057464  lea     r9, [rbp+var_48]
0x180057468  mov     rcx, [rdi]
0x18005746b  mov     r8d, esi
0x18005746e  call    FwppProxyvSwitchEventsSetSecurityInfo
0x180057473  test    eax, eax
0x180057475  jns     short loc_180057489
0x180057477  mov     r8d, eax
0x18005747a  lea     rdx, aFwppproxyvswit; "FwppProxyvSwitchEventsSetSecurityInfo"
0x180057481  call    WfpReportSysErrorAsNtStatus
0x180057486  mov     rbx, rax
0x180057489  lea     rcx, [rbp+var_50]
0x18005748d  call    BfeSecurityDescriptorStorageFree
0x180057492  mov     rcx, rbx
0x180057495  call    WfpErrorToFwpErr
0x18005749a  mov     rcx, [rbp+var_10]
0x18005749e  xor     rcx, rsp; StackCookie
0x1800574a1  call    __security_check_cookie
0x1800574a6  add     rsp, 80h
0x1800574ad  pop     r15
0x1800574af  pop     r14
0x1800574b1  pop     r12
0x1800574b3  pop     rdi
0x1800574b4  pop     rsi
0x1800574b5  pop     rbx
0x1800574b6  pop     rbp
0x1800574b7  retn
```
