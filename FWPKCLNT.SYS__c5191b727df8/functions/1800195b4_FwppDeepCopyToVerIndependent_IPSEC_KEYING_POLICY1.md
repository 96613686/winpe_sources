# FwppDeepCopyToVerIndependent_IPSEC_KEYING_POLICY1

- ea: `0x1800195b4`
- end: `0x180019682`
- name: `FwppDeepCopyToVerIndependent_IPSEC_KEYING_POLICY1`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180012e04`

## callees

- `0x180004904`
- `0x18000c9b4`
- `0x1800195b4`
- `0x18001a364`
- `0x18005c0c8`

## string_xrefs

- `0x180019613`: `FwppDeepCopyToVerIndependent_IPSEC_KEYING_POLICY_FLAGS`
- `0x180019627`: `FwppDeepCopyToVerIndependent_IPSEC_KEYING_POLICY_FLAGS`
- `0x18001963e`: `FwppDeepCopyToVerIndependent_IPSEC_KEYING_POLICY1`
- `0x18001965f`: `FwppDeepCopyToVerIndependent_IPSEC_KEYING_POLICY1`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyToVerIndependent_IPSEC_KEYING_POLICY1(unsigned int *a1, unsigned int *a2)
{
  _DWORD *v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // rax

  if ( !a1 || !a2 )
  {
    v5 = WfpReportSysErrorAsNtStatus((__int64)a1, (int)"FwppDeepCopyToVerIndependent_IPSEC_KEYING_POLICY1", -1071513572);
    if ( !v5 )
      return v5;
    goto LABEL_12;
  }
  v4 = (_DWORD *)*((_QWORD *)a1 + 1);
  if ( v4 )
  {
    v5 = FwppArrayAllocAndDeepCopyToVerIndependent_GUID(v4, *a1, a2 + 2);
    if ( v5 )
      goto LABEL_12;
    *a2 = *a1;
  }
  if ( a1 != (unsigned int *)-16LL )
  {
    v4 = a2 + 4;
    if ( a2 != (unsigned int *)-16LL )
    {
      v5 = 0;
      *v4 = a1[4];
      return v5;
    }
  }
  v6 = WfpReportSysErrorAsNtStatus(
         (__int64)v4,
         (int)"FwppDeepCopyToVerIndependent_IPSEC_KEYING_POLICY_FLAGS",
         -1071513572);
  v5 = v6;
  if ( !v6 )
    return v5;
  WfpReportError(v6, (int)"FwppDeepCopyToVerIndependent_IPSEC_KEYING_POLICY_FLAGS");
LABEL_12:
  FwppDeepFreeContentsOnly_IPSEC_KEYING_POLICY1(a2);
  if ( v5 )
    WfpReportError(v5, (int)"FwppDeepCopyToVerIndependent_IPSEC_KEYING_POLICY1");
  return v5;
}

```

## disassembly

```asm
0x1800195b4  mov     [rsp+arg_0], rbx
0x1800195b9  mov     [rsp+arg_8], rsi
0x1800195be  push    rdi
0x1800195bf  sub     rsp, 20h
0x1800195c3  mov     rsi, rdx
0x1800195c6  mov     rdi, rcx
0x1800195c9  test    rcx, rcx
0x1800195cc  jz      short loc_180019638
0x1800195ce  test    rdx, rdx
0x1800195d1  jz      short loc_180019638
0x1800195d3  mov     rcx, [rcx+8]
0x1800195d7  test    rcx, rcx
0x1800195da  jz      short loc_1800195F3
0x1800195dc  lea     r8, [rdx+8]
0x1800195e0  mov     edx, [rdi]
0x1800195e2  call    FwppArrayAllocAndDeepCopyToVerIndependent_GUID
0x1800195e7  mov     rbx, rax
0x1800195ea  test    rax, rax
0x1800195ed  jnz     short loc_180019652
0x1800195ef  mov     eax, [rdi]
0x1800195f1  mov     [rsi], eax
0x1800195f3  lea     rax, [rdi+10h]
0x1800195f7  test    rax, rax
0x1800195fa  jz      short loc_18001960D
0x1800195fc  lea     rcx, [rsi+10h]
0x180019600  test    rcx, rcx
0x180019603  jz      short loc_18001960D
0x180019605  mov     eax, [rax]
0x180019607  xor     ebx, ebx
0x180019609  mov     [rcx], eax
0x18001960b  jmp     short loc_18001966E
0x18001960d  mov     r8d, 0C022001Ch
0x180019613  lea     rdx, aFwppdeepcopyto_77; "FwppDeepCopyToVerIndependent_IPSEC_KEYI"...
0x18001961a  call    WfpReportSysErrorAsNtStatus
0x18001961f  mov     rbx, rax
0x180019622  test    rax, rax
0x180019625  jz      short loc_18001966E
0x180019627  lea     rdx, aFwppdeepcopyto_77; "FwppDeepCopyToVerIndependent_IPSEC_KEYI"...
0x18001962e  mov     rcx, rax
0x180019631  call    WfpReportError
0x180019636  jmp     short loc_180019652
0x180019638  mov     r8d, 0C022001Ch
0x18001963e  lea     rdx, aFwppdeepcopyto_34; "FwppDeepCopyToVerIndependent_IPSEC_KEYI"...
0x180019645  call    WfpReportSysErrorAsNtStatus
0x18001964a  mov     rbx, rax
0x18001964d  test    rax, rax
0x180019650  jz      short loc_18001966E
0x180019652  mov     rcx, rsi
0x180019655  call    FwppDeepFreeContentsOnly_IPSEC_KEYING_POLICY1
0x18001965a  test    rbx, rbx
0x18001965d  jz      short loc_18001966E
0x18001965f  lea     rdx, aFwppdeepcopyto_34; "FwppDeepCopyToVerIndependent_IPSEC_KEYI"...
0x180019666  mov     rcx, rbx
0x180019669  call    WfpReportError
0x18001966e  mov     rsi, [rsp+28h+arg_8]
0x180019673  mov     rax, rbx
0x180019676  mov     rbx, [rsp+28h+arg_0]
0x18001967b  add     rsp, 20h
0x18001967f  pop     rdi
0x180019680  retn
```
