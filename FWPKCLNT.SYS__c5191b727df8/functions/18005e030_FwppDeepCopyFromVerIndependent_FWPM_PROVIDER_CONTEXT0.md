# FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT0

- ea: `0x18005e030`
- end: `0x18005e1e9`
- name: `FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT0`
- size: `441`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x180059938`

## callees

- `0x1800050cc`
- `0x18000c9b4`
- `0x180012a98`
- `0x180018660`
- `0x18005981c`
- `0x180059b64`
- `0x180059d00`
- `0x18005a15c`
- `0x18005a538`
- `0x18005a5c8`
- `0x18005dd70`
- `0x18005e030`
- `0x18005e1f0`
- `0x18005e244`
- `0x18005e7b8`
- `0x180061318`
- `0x18006457c`

## string_xrefs

- `0x18005e1b8`: `FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT0`
- `0x18005e1db`: `FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT0(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  __int64 v5; // rcx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rax

  if ( !a1 || !a2 )
  {
    v21 = WfpReportAppErrorAsNtStatus(
            a1,
            (__int64)"FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT0",
            3223453724LL);
LABEL_33:
    v4 = v21;
    if ( !v21 )
      return v4;
    goto LABEL_34;
  }
  v4 = FwppDeepCopyFromVerIndependent_GUID(a1, a2);
  if ( v4 )
    goto LABEL_34;
  v4 = FwppDeepCopyFromVerIndependent_FWPM_DISPLAY_DATA0(a1 + 16, a2 + 16);
  if ( v4 )
    goto LABEL_34;
  v4 = FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT_FLAGS(a1 + 32, a2 + 32);
  if ( v4 )
    goto LABEL_34;
  v5 = *(_QWORD *)(a1 + 40);
  if ( v5 )
  {
    v4 = FwppAllocAndDeepCopyFromVerIndependent_GUID(v5, a2 + 40);
    if ( v4 )
      goto LABEL_34;
  }
  v4 = FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB((void **)(a1 + 48), (_DWORD *)(a2 + 48));
  if ( v4 )
    goto LABEL_34;
  v4 = FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT_TYPE(a1 + 64, a2 + 64);
  if ( v4 )
    goto LABEL_34;
  v6 = *(_DWORD *)(a1 + 64);
  if ( !v6 )
  {
    v20 = *(_QWORD *)(a1 + 72);
    if ( v20 )
    {
      v15 = FwppAllocAndDeepCopyFromVerIndependent_IPSEC_KEYING_POLICY0(v20, a2 + 72);
      goto LABEL_31;
    }
LABEL_32:
    v21 = FwppDeepCopyFromVerIndependent_UINT64(a1 + 80, a2 + 80);
    goto LABEL_33;
  }
  v7 = v6 - 1;
  if ( !v7 )
    goto LABEL_27;
  v8 = v7 - 1;
  if ( !v8 )
    goto LABEL_25;
  v9 = v8 - 1;
  if ( !v9 )
  {
LABEL_27:
    v19 = *(_QWORD *)(a1 + 72);
    if ( v19 )
    {
      v15 = FwppAllocAndDeepCopyFromVerIndependent_IPSEC_TRANSPORT_POLICY0(v19, a2 + 72);
      goto LABEL_31;
    }
    goto LABEL_32;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
LABEL_25:
    v18 = *(_QWORD *)(a1 + 72);
    if ( v18 )
    {
      v15 = FwppAllocAndDeepCopyFromVerIndependent_IPSEC_TUNNEL_POLICY0(v18, a2 + 72);
      goto LABEL_31;
    }
    goto LABEL_32;
  }
  v11 = v10 - 1;
  if ( !v11 || (v12 = v11 - 1) == 0 )
  {
    v17 = *(_QWORD *)(a1 + 72);
    if ( v17 )
    {
      v15 = FwppAllocAndDeepCopyFromVerIndependent_IKEEXT_POLICY0(v17, a2 + 72);
      goto LABEL_31;
    }
    goto LABEL_32;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
    v16 = *(_QWORD *)(a1 + 72);
    if ( v16 )
    {
      v15 = FwppAllocAndDeepCopyFromVerIndependent_FWPM_CLASSIFY_OPTIONS0(v16, a2 + 72);
      goto LABEL_31;
    }
    goto LABEL_32;
  }
  if ( v13 != 1 )
    goto LABEL_32;
  v14 = *(_QWORD *)(a1 + 72);
  if ( !v14 )
    goto LABEL_32;
  v15 = FwppAllocAndDeepCopyToVerIndependent_FWP_BYTE_BLOB(v14, a2 + 72);
LABEL_31:
  v4 = v15;
  if ( !v15 )
    goto LABEL_32;
LABEL_34:
  FwppDeepFreeContentsOnly_FWPM_PROVIDER_CONTEXT0(a2);
  if ( v4 )
    WfpReportError(v4, (int)"FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT0");
  return v4;
}

```

## disassembly

```asm
0x18005e030  push    rbx
0x18005e032  push    rsi
0x18005e033  push    rdi
0x18005e034  push    r14
0x18005e036  sub     rsp, 38h
0x18005e03a  mov     rsi, rdx
0x18005e03d  mov     rdi, rcx
0x18005e040  test    rcx, rcx
0x18005e043  jz      loc_18005E1D5
0x18005e049  test    rdx, rdx
0x18005e04c  jz      loc_18005E1D5
0x18005e052  call    FwppDeepCopyFromVerIndependent_GUID
0x18005e057  mov     rbx, rax
0x18005e05a  test    rax, rax
0x18005e05d  jnz     loc_18005E1AB
0x18005e063  lea     rdx, [rsi+10h]
0x18005e067  lea     rcx, [rdi+10h]
0x18005e06b  call    FwppDeepCopyFromVerIndependent_FWPM_DISPLAY_DATA0
0x18005e070  mov     rbx, rax
0x18005e073  test    rax, rax
0x18005e076  jnz     loc_18005E1AB
0x18005e07c  lea     rdx, [rsi+20h]
0x18005e080  lea     rcx, [rdi+20h]
0x18005e084  call    FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT_FLAGS
0x18005e089  mov     rbx, rax
0x18005e08c  test    rax, rax
0x18005e08f  jnz     loc_18005E1AB
0x18005e095  mov     rcx, [rdi+28h]
0x18005e099  test    rcx, rcx
0x18005e09c  jz      short loc_18005E0B3
0x18005e09e  lea     rdx, [rsi+28h]
0x18005e0a2  call    FwppAllocAndDeepCopyFromVerIndependent_GUID
0x18005e0a7  mov     rbx, rax
0x18005e0aa  test    rax, rax
0x18005e0ad  jnz     loc_18005E1AB
0x18005e0b3  lea     rdx, [rsi+30h]
0x18005e0b7  lea     rcx, [rdi+30h]
0x18005e0bb  call    FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB
0x18005e0c0  mov     rbx, rax
0x18005e0c3  test    rax, rax
0x18005e0c6  jnz     loc_18005E1AB
0x18005e0cc  lea     rdx, [rsi+40h]
0x18005e0d0  lea     rcx, [rdi+40h]
0x18005e0d4  call    FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT_TYPE
0x18005e0d9  mov     rbx, rax
0x18005e0dc  test    rax, rax
0x18005e0df  jnz     loc_18005E1AB
0x18005e0e5  mov     ecx, [rdi+40h]
0x18005e0e8  test    ecx, ecx
0x18005e0ea  jz      loc_18005E17C
0x18005e0f0  sub     ecx, 1
0x18005e0f3  jz      short loc_18005E168
0x18005e0f5  sub     ecx, 1
0x18005e0f8  jz      short loc_18005E154
0x18005e0fa  sub     ecx, 1
0x18005e0fd  jz      short loc_18005E168
0x18005e0ff  sub     ecx, 1
0x18005e102  jz      short loc_18005E154
0x18005e104  sub     ecx, 1
0x18005e107  jz      short loc_18005E140
0x18005e109  sub     ecx, 1
0x18005e10c  jz      short loc_18005E140
0x18005e10e  sub     ecx, 1
0x18005e111  jz      short loc_18005E12C
0x18005e113  cmp     ecx, 1
0x18005e116  jnz     short loc_18005E196
0x18005e118  mov     rcx, [rdi+48h]
0x18005e11c  test    rcx, rcx
0x18005e11f  jz      short loc_18005E196
0x18005e121  lea     rdx, [rsi+48h]
0x18005e125  call    FwppAllocAndDeepCopyToVerIndependent_FWP_BYTE_BLOB
0x18005e12a  jmp     short loc_18005E18E
0x18005e12c  mov     rcx, [rdi+48h]
0x18005e130  test    rcx, rcx
0x18005e133  jz      short loc_18005E196
0x18005e135  lea     rdx, [rsi+48h]
0x18005e139  call    FwppAllocAndDeepCopyFromVerIndependent_FWPM_CLASSIFY_OPTIONS0
0x18005e13e  jmp     short loc_18005E18E
0x18005e140  mov     rcx, [rdi+48h]
0x18005e144  test    rcx, rcx
0x18005e147  jz      short loc_18005E196
0x18005e149  lea     rdx, [rsi+48h]
0x18005e14d  call    FwppAllocAndDeepCopyFromVerIndependent_IKEEXT_POLICY0
0x18005e152  jmp     short loc_18005E18E
0x18005e154  mov     rcx, [rdi+48h]
0x18005e158  test    rcx, rcx
0x18005e15b  jz      short loc_18005E196
0x18005e15d  lea     rdx, [rsi+48h]
0x18005e161  call    FwppAllocAndDeepCopyFromVerIndependent_IPSEC_TUNNEL_POLICY0
0x18005e166  jmp     short loc_18005E18E
0x18005e168  mov     rcx, [rdi+48h]
0x18005e16c  test    rcx, rcx
0x18005e16f  jz      short loc_18005E196
0x18005e171  lea     rdx, [rsi+48h]
0x18005e175  call    FwppAllocAndDeepCopyFromVerIndependent_IPSEC_TRANSPORT_POLICY0
0x18005e17a  jmp     short loc_18005E18E
0x18005e17c  mov     rcx, [rdi+48h]
0x18005e180  test    rcx, rcx
0x18005e183  jz      short loc_18005E196
0x18005e185  lea     rdx, [rsi+48h]
0x18005e189  call    FwppAllocAndDeepCopyFromVerIndependent_IPSEC_KEYING_POLICY0
0x18005e18e  mov     rbx, rax
0x18005e191  test    rax, rax
0x18005e194  jnz     short loc_18005E1AB
0x18005e196  lea     rdx, [rsi+50h]
0x18005e19a  lea     rcx, [rdi+50h]
0x18005e19e  call    FwppDeepCopyFromVerIndependent_UINT64
0x18005e1a3  mov     rbx, rax
0x18005e1a6  test    rax, rax
0x18005e1a9  jz      short loc_18005E1C7
0x18005e1ab  mov     rcx, rsi
0x18005e1ae  call    FwppDeepFreeContentsOnly_FWPM_PROVIDER_CONTEXT0
0x18005e1b3  test    rbx, rbx
0x18005e1b6  jz      short loc_18005E1C7
0x18005e1b8  lea     rdx, aFwppdeepcopyfr_107; "FwppDeepCopyFromVerIndependent_FWPM_PRO"...
0x18005e1bf  mov     rcx, rbx
0x18005e1c2  call    WfpReportError
0x18005e1c7  mov     rax, rbx
0x18005e1ca  add     rsp, 38h
0x18005e1ce  pop     r14
0x18005e1d0  pop     rdi
0x18005e1d1  pop     rsi
0x18005e1d2  pop     rbx
0x18005e1d3  retn
0x18005e1d5  mov     r8d, 0C022001Ch
0x18005e1db  lea     rdx, aFwppdeepcopyfr_107; "FwppDeepCopyFromVerIndependent_FWPM_PRO"...
0x18005e1e2  call    WfpReportAppErrorAsNtStatus
0x18005e1e7  jmp     short loc_18005E1A3
```
