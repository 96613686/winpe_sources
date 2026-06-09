# FwppDeepCopyFromVerIndependent_IPSEC_KEYING_POLICY1

- ea: `0x180017838`
- end: `0x180017906`
- name: `FwppDeepCopyFromVerIndependent_IPSEC_KEYING_POLICY1`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800126ac`

## callees

- `0x180004904`
- `0x18000c9b4`
- `0x180017838`
- `0x18001a364`
- `0x18005b67c`

## string_xrefs

- `0x180017897`: `FwppDeepCopyFromVerIndependent_IPSEC_KEYING_POLICY_FLAGS`
- `0x1800178ab`: `FwppDeepCopyFromVerIndependent_IPSEC_KEYING_POLICY_FLAGS`
- `0x1800178c2`: `FwppDeepCopyFromVerIndependent_IPSEC_KEYING_POLICY1`
- `0x1800178e3`: `FwppDeepCopyFromVerIndependent_IPSEC_KEYING_POLICY1`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyFromVerIndependent_IPSEC_KEYING_POLICY1(unsigned int *a1, unsigned int *a2)
{
  _DWORD *v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // rax

  if ( !a1 || !a2 )
  {
    v5 = WfpReportSysErrorAsNtStatus(
           (__int64)a1,
           (int)"FwppDeepCopyFromVerIndependent_IPSEC_KEYING_POLICY1",
           -1071513572);
    if ( !v5 )
      return v5;
    goto LABEL_12;
  }
  v4 = (_DWORD *)*((_QWORD *)a1 + 1);
  if ( v4 )
  {
    v5 = FwppArrayAllocAndDeepCopyFromVerIndependent_GUID(v4, *a1, a2 + 2);
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
         (int)"FwppDeepCopyFromVerIndependent_IPSEC_KEYING_POLICY_FLAGS",
         -1071513572);
  v5 = v6;
  if ( !v6 )
    return v5;
  WfpReportError(v6, (int)"FwppDeepCopyFromVerIndependent_IPSEC_KEYING_POLICY_FLAGS");
LABEL_12:
  FwppDeepFreeContentsOnly_IPSEC_KEYING_POLICY1(a2);
  if ( v5 )
    WfpReportError(v5, (int)"FwppDeepCopyFromVerIndependent_IPSEC_KEYING_POLICY1");
  return v5;
}

```

## disassembly

```asm
0x180017838  mov     [rsp+arg_0], rbx
0x18001783d  mov     [rsp+arg_8], rsi
0x180017842  push    rdi
0x180017843  sub     rsp, 20h
0x180017847  mov     rsi, rdx
0x18001784a  mov     rdi, rcx
0x18001784d  test    rcx, rcx
0x180017850  jz      short loc_1800178BC
0x180017852  test    rdx, rdx
0x180017855  jz      short loc_1800178BC
0x180017857  mov     rcx, [rcx+8]
0x18001785b  test    rcx, rcx
0x18001785e  jz      short loc_180017877
0x180017860  lea     r8, [rdx+8]
0x180017864  mov     edx, [rdi]
0x180017866  call    FwppArrayAllocAndDeepCopyFromVerIndependent_GUID
0x18001786b  mov     rbx, rax
0x18001786e  test    rax, rax
0x180017871  jnz     short loc_1800178D6
0x180017873  mov     eax, [rdi]
0x180017875  mov     [rsi], eax
0x180017877  lea     rax, [rdi+10h]
0x18001787b  test    rax, rax
0x18001787e  jz      short loc_180017891
0x180017880  lea     rcx, [rsi+10h]
0x180017884  test    rcx, rcx
0x180017887  jz      short loc_180017891
0x180017889  mov     eax, [rax]
0x18001788b  xor     ebx, ebx
0x18001788d  mov     [rcx], eax
0x18001788f  jmp     short loc_1800178F2
0x180017891  mov     r8d, 0C022001Ch
0x180017897  lea     rdx, aFwppdeepcopyfr_35; "FwppDeepCopyFromVerIndependent_IPSEC_KE"...
0x18001789e  call    WfpReportSysErrorAsNtStatus
0x1800178a3  mov     rbx, rax
0x1800178a6  test    rax, rax
0x1800178a9  jz      short loc_1800178F2
0x1800178ab  lea     rdx, aFwppdeepcopyfr_35; "FwppDeepCopyFromVerIndependent_IPSEC_KE"...
0x1800178b2  mov     rcx, rax
0x1800178b5  call    WfpReportError
0x1800178ba  jmp     short loc_1800178D6
0x1800178bc  mov     r8d, 0C022001Ch
0x1800178c2  lea     rdx, aFwppdeepcopyfr_38; "FwppDeepCopyFromVerIndependent_IPSEC_KE"...
0x1800178c9  call    WfpReportSysErrorAsNtStatus
0x1800178ce  mov     rbx, rax
0x1800178d1  test    rax, rax
0x1800178d4  jz      short loc_1800178F2
0x1800178d6  mov     rcx, rsi
0x1800178d9  call    FwppDeepFreeContentsOnly_IPSEC_KEYING_POLICY1
0x1800178de  test    rbx, rbx
0x1800178e1  jz      short loc_1800178F2
0x1800178e3  lea     rdx, aFwppdeepcopyfr_38; "FwppDeepCopyFromVerIndependent_IPSEC_KE"...
0x1800178ea  mov     rcx, rbx
0x1800178ed  call    WfpReportError
0x1800178f2  mov     rsi, [rsp+28h+arg_8]
0x1800178f7  mov     rax, rbx
0x1800178fa  mov     rbx, [rsp+28h+arg_0]
0x1800178ff  add     rsp, 20h
0x180017903  pop     rdi
0x180017904  retn
```
