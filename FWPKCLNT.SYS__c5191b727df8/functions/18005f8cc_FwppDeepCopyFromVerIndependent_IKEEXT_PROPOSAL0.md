# FwppDeepCopyFromVerIndependent_IKEEXT_PROPOSAL0

- ea: `0x18005f8cc`
- end: `0x18005f9c4`
- name: `FwppDeepCopyFromVerIndependent_IKEEXT_PROPOSAL0`
- size: `248`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180017068`
- `0x18005b884`
- `0x18005f9cc`

## callees

- `0x1800050cc`
- `0x18000c9b4`
- `0x18005eb7c`
- `0x18005f040`
- `0x18005f8cc`
- `0x1800612c4`
- `0x18006445c`

## string_xrefs

- `0x18005f98b`: `FwppDeepCopyFromVerIndependent_IKEEXT_DH_GROUP`
- `0x18005f99f`: `FwppDeepCopyFromVerIndependent_IKEEXT_DH_GROUP`
- `0x18005f962`: `FwppDeepCopyFromVerIndependent_IKEEXT_PROPOSAL0`
- `0x18005f9b6`: `FwppDeepCopyFromVerIndependent_IKEEXT_PROPOSAL0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyFromVerIndependent_IKEEXT_PROPOSAL0(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  _DWORD *v5; // rcx
  __int64 v6; // rax
  __int64 v8; // rax

  if ( !a1 || !a2 )
  {
    v6 = WfpReportAppErrorAsNtStatus(a1, (__int64)"FwppDeepCopyFromVerIndependent_IKEEXT_PROPOSAL0", 3223453724LL);
LABEL_10:
    v4 = v6;
    if ( !v6 )
      return v4;
    goto LABEL_11;
  }
  v4 = FwppDeepCopyFromVerIndependent_IKEEXT_CIPHER_ALGORITHM0();
  if ( !v4 )
  {
    v4 = FwppDeepCopyFromVerIndependent_IKEEXT_INTEGRITY_ALGORITHM0(a1 + 12, a2 + 12);
    if ( !v4 )
    {
      v4 = FwppDeepCopyFromVerIndependent_UINT32(a1 + 16, a2 + 16);
      if ( !v4 )
      {
        if ( a1 != -20 )
        {
          v5 = (_DWORD *)(a2 + 20);
          if ( a2 != -20 )
          {
            *v5 = *(_DWORD *)(a1 + 20);
LABEL_9:
            v6 = FwppDeepCopyFromVerIndependent_UINT32(a1 + 24, a2 + 24);
            goto LABEL_10;
          }
        }
        v8 = WfpReportAppErrorAsNtStatus(
               (__int64)v5,
               (__int64)"FwppDeepCopyFromVerIndependent_IKEEXT_DH_GROUP",
               3223453724LL);
        v4 = v8;
        if ( !v8 )
          goto LABEL_9;
        WfpReportError(v8, (int)"FwppDeepCopyFromVerIndependent_IKEEXT_DH_GROUP");
      }
    }
  }
LABEL_11:
  FwppDeepFreeContentsOnly_IPSEC_SA_IDLE_TIMEOUT0(a2);
  if ( v4 )
    WfpReportError(v4, (int)"FwppDeepCopyFromVerIndependent_IKEEXT_PROPOSAL0");
  return v4;
}

```

## disassembly

```asm
0x18005f8cc  mov     [rsp+arg_0], rbx
0x18005f8d1  mov     [rsp+arg_8], rsi
0x18005f8d6  push    rdi
0x18005f8d7  sub     rsp, 30h
0x18005f8db  mov     rdi, rdx
0x18005f8de  mov     rsi, rcx
0x18005f8e1  test    rcx, rcx
0x18005f8e4  jz      loc_18005F9B0
0x18005f8ea  test    rdx, rdx
0x18005f8ed  jz      loc_18005F9B0
0x18005f8f3  call    FwppDeepCopyFromVerIndependent_IKEEXT_CIPHER_ALGORITHM0
0x18005f8f8  mov     rbx, rax
0x18005f8fb  test    rax, rax
0x18005f8fe  jnz     short loc_18005F955
0x18005f900  lea     rdx, [rdi+0Ch]
0x18005f904  lea     rcx, [rsi+0Ch]
0x18005f908  call    FwppDeepCopyFromVerIndependent_IKEEXT_INTEGRITY_ALGORITHM0
0x18005f90d  mov     rbx, rax
0x18005f910  test    rax, rax
0x18005f913  jnz     short loc_18005F955
0x18005f915  lea     rdx, [rdi+10h]
0x18005f919  lea     rcx, [rsi+10h]
0x18005f91d  call    FwppDeepCopyFromVerIndependent_UINT32
0x18005f922  mov     rbx, rax
0x18005f925  test    rax, rax
0x18005f928  jnz     short loc_18005F955
0x18005f92a  lea     rax, [rsi+14h]
0x18005f92e  test    rax, rax
0x18005f931  jz      short loc_18005F985
0x18005f933  lea     rcx, [rdi+14h]
0x18005f937  test    rcx, rcx
0x18005f93a  jz      short loc_18005F985
0x18005f93c  mov     eax, [rax]
0x18005f93e  mov     [rcx], eax
0x18005f940  lea     rdx, [rdi+18h]
0x18005f944  lea     rcx, [rsi+18h]
0x18005f948  call    FwppDeepCopyFromVerIndependent_UINT32
0x18005f94d  mov     rbx, rax
0x18005f950  test    rax, rax
0x18005f953  jz      short loc_18005F971
0x18005f955  mov     rcx, rdi
0x18005f958  call    FwppDeepFreeContentsOnly_IPSEC_SA_IDLE_TIMEOUT0
0x18005f95d  test    rbx, rbx
0x18005f960  jz      short loc_18005F971
0x18005f962  lea     rdx, aFwppdeepcopyfr_103; "FwppDeepCopyFromVerIndependent_IKEEXT_P"...
0x18005f969  mov     rcx, rbx
0x18005f96c  call    WfpReportError
0x18005f971  mov     rsi, [rsp+38h+arg_8]
0x18005f976  mov     rax, rbx
0x18005f979  mov     rbx, [rsp+38h+arg_0]
0x18005f97e  add     rsp, 30h
0x18005f982  pop     rdi
0x18005f983  retn
0x18005f985  mov     r8d, 0C022001Ch
0x18005f98b  lea     rdx, aFwppdeepcopyfr_52; "FwppDeepCopyFromVerIndependent_IKEEXT_D"...
0x18005f992  call    WfpReportAppErrorAsNtStatus
0x18005f997  mov     rbx, rax
0x18005f99a  test    rax, rax
0x18005f99d  jz      short loc_18005F940
0x18005f99f  lea     rdx, aFwppdeepcopyfr_52; "FwppDeepCopyFromVerIndependent_IKEEXT_D"...
0x18005f9a6  mov     rcx, rax
0x18005f9a9  call    WfpReportError
0x18005f9ae  jmp     short loc_18005F955
0x18005f9b0  mov     r8d, 0C022001Ch
0x18005f9b6  lea     rdx, aFwppdeepcopyfr_103; "FwppDeepCopyFromVerIndependent_IKEEXT_P"...
0x18005f9bd  call    WfpReportAppErrorAsNtStatus
0x18005f9c2  jmp     short loc_18005F94D
```
