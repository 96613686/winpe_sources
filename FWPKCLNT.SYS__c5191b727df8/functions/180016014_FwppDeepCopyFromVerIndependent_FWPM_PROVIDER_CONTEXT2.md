# FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT2

- ea: `0x180016014`
- end: `0x18001620f`
- name: `FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT2`
- size: `507`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x180012000`

## callees

- `0x180004904`
- `0x18000c9b4`
- `0x180012468`
- `0x180012618`
- `0x1800126ac`
- `0x1800127c8`
- `0x1800128e8`
- `0x180012a98`
- `0x180016014`
- `0x180018660`
- `0x180019d88`
- `0x18005981c`
- `0x180059b64`
- `0x18005dd70`
- `0x18005e1f0`
- `0x18005e244`
- `0x18005e7b8`
- `0x180061318`

## string_xrefs

- `0x1800161de`: `FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT2`
- `0x180016201`: `FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT2`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT2(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  __int64 v5; // rcx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rax

  if ( !a1 || !a2 )
  {
    v24 = WfpReportSysErrorAsNtStatus(a1, (int)"FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT2", -1071513572);
LABEL_41:
    v4 = v24;
    if ( !v24 )
      return v4;
    goto LABEL_42;
  }
  v4 = FwppDeepCopyFromVerIndependent_GUID(a1, a2);
  if ( v4 )
    goto LABEL_42;
  v4 = FwppDeepCopyFromVerIndependent_FWPM_DISPLAY_DATA0(a1 + 16, a2 + 16);
  if ( v4 )
    goto LABEL_42;
  v4 = FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT_FLAGS(a1 + 32, a2 + 32);
  if ( v4 )
    goto LABEL_42;
  v5 = *(_QWORD *)(a1 + 40);
  if ( v5 )
  {
    v4 = FwppAllocAndDeepCopyFromVerIndependent_GUID(v5, a2 + 40);
    if ( v4 )
      goto LABEL_42;
  }
  v4 = FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB((void **)(a1 + 48), (_DWORD *)(a2 + 48));
  if ( v4 )
    goto LABEL_42;
  v4 = FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT_TYPE(a1 + 64, a2 + 64);
  if ( v4 )
    goto LABEL_42;
  v6 = *(_DWORD *)(a1 + 64);
  if ( v6 > 6 )
  {
    v16 = v6 - 7;
    if ( !v16 )
    {
      v23 = *(_QWORD *)(a1 + 72);
      if ( !v23 )
        goto LABEL_40;
      v12 = FwppAllocAndDeepCopyFromVerIndependent_FWPM_CLASSIFY_OPTIONS0(v23, a2 + 72);
      goto LABEL_39;
    }
    v17 = v16 - 1;
    if ( !v17 )
    {
      v22 = *(_QWORD *)(a1 + 72);
      if ( !v22 )
        goto LABEL_40;
      v12 = FwppAllocAndDeepCopyToVerIndependent_FWP_BYTE_BLOB(v22, a2 + 72);
      goto LABEL_39;
    }
    v18 = v17 - 1;
    if ( !v18 )
      goto LABEL_20;
    v19 = v18 - 1;
    if ( v19 )
    {
      v20 = v19 - 1;
      if ( !v20 )
      {
        v21 = *(_QWORD *)(a1 + 72);
        if ( !v21 )
          goto LABEL_40;
        v12 = FwppAllocAndDeepCopyFromVerIndependent_IPSEC_DOSP_OPTIONS0(v21, a2 + 72);
        goto LABEL_39;
      }
      if ( v20 != 1 )
        goto LABEL_40;
      goto LABEL_22;
    }
LABEL_18:
    v11 = *(_QWORD *)(a1 + 72);
    if ( v11 )
    {
      v12 = FwppAllocAndDeepCopyFromVerIndependent_IKEEXT_POLICY2(v11, a2 + 72);
      goto LABEL_39;
    }
LABEL_40:
    v24 = FwppDeepCopyFromVerIndependent_UINT64(a1 + 80, a2 + 80);
    goto LABEL_41;
  }
  if ( v6 == 6 )
    goto LABEL_18;
  if ( !v6 )
  {
    v15 = *(_QWORD *)(a1 + 72);
    if ( !v15 )
      goto LABEL_40;
    v12 = FwppAllocAndDeepCopyFromVerIndependent_IPSEC_KEYING_POLICY1(v15, a2 + 72);
    goto LABEL_39;
  }
  v7 = v6 - 1;
  if ( !v7 )
    goto LABEL_22;
  v8 = v7 - 1;
  if ( v8 )
  {
    v9 = v8 - 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        if ( v10 != 1 )
          goto LABEL_40;
        goto LABEL_18;
      }
      goto LABEL_20;
    }
LABEL_22:
    v14 = *(_QWORD *)(a1 + 72);
    if ( !v14 )
      goto LABEL_40;
    v12 = FwppAllocAndDeepCopyFromVerIndependent_IPSEC_TRANSPORT_POLICY2(v14, a2 + 72);
    goto LABEL_39;
  }
LABEL_20:
  v13 = *(_QWORD *)(a1 + 72);
  if ( !v13 )
    goto LABEL_40;
  v12 = FwppAllocAndDeepCopyFromVerIndependent_IPSEC_TUNNEL_POLICY2(v13, a2 + 72);
LABEL_39:
  v4 = v12;
  if ( !v12 )
    goto LABEL_40;
LABEL_42:
  FwppDeepFreeContentsOnly_FWPM_PROVIDER_CONTEXT2(a2);
  if ( v4 )
    WfpReportError(v4, (int)"FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT2");
  return v4;
}

```

## disassembly

```asm
0x180016014  push    rbx
0x180016016  push    rsi
0x180016017  push    rdi
0x180016018  push    r14
0x18001601a  sub     rsp, 28h
0x18001601e  mov     rsi, rdx
0x180016021  mov     rdi, rcx
0x180016024  test    rcx, rcx
0x180016027  jz      loc_1800161FB
0x18001602d  test    rdx, rdx
0x180016030  jz      loc_1800161FB
0x180016036  call    FwppDeepCopyFromVerIndependent_GUID
0x18001603b  mov     rbx, rax
0x18001603e  test    rax, rax
0x180016041  jnz     loc_1800161D1
0x180016047  lea     rdx, [rsi+10h]
0x18001604b  lea     rcx, [rdi+10h]
0x18001604f  call    FwppDeepCopyFromVerIndependent_FWPM_DISPLAY_DATA0
0x180016054  mov     rbx, rax
0x180016057  test    rax, rax
0x18001605a  jnz     loc_1800161D1
0x180016060  lea     rdx, [rsi+20h]
0x180016064  lea     rcx, [rdi+20h]
0x180016068  call    FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT_FLAGS
0x18001606d  mov     rbx, rax
0x180016070  test    rax, rax
0x180016073  jnz     loc_1800161D1
0x180016079  mov     rcx, [rdi+28h]
0x18001607d  test    rcx, rcx
0x180016080  jz      short loc_180016097
0x180016082  lea     rdx, [rsi+28h]
0x180016086  call    FwppAllocAndDeepCopyFromVerIndependent_GUID
0x18001608b  mov     rbx, rax
0x18001608e  test    rax, rax
0x180016091  jnz     loc_1800161D1
0x180016097  lea     rdx, [rsi+30h]
0x18001609b  lea     rcx, [rdi+30h]
0x18001609f  call    FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB
0x1800160a4  mov     rbx, rax
0x1800160a7  test    rax, rax
0x1800160aa  jnz     loc_1800161D1
0x1800160b0  lea     rdx, [rsi+40h]
0x1800160b4  lea     rcx, [rdi+40h]
0x1800160b8  call    FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT_TYPE
0x1800160bd  mov     rbx, rax
0x1800160c0  test    rax, rax
0x1800160c3  jnz     loc_1800161D1
0x1800160c9  mov     ecx, [rdi+40h]
0x1800160cc  cmp     ecx, 6
0x1800160cf  jg      loc_18001615A
0x1800160d5  jz      short loc_1800160F8
0x1800160d7  test    ecx, ecx
0x1800160d9  jz      short loc_180016146
0x1800160db  sub     ecx, 1
0x1800160de  jz      short loc_18001612E
0x1800160e0  sub     ecx, 1
0x1800160e3  jz      short loc_180016113
0x1800160e5  sub     ecx, 1
0x1800160e8  jz      short loc_18001612E
0x1800160ea  sub     ecx, 1
0x1800160ed  jz      short loc_180016113
0x1800160ef  cmp     ecx, 1
0x1800160f2  jnz     loc_1800161BC
0x1800160f8  mov     rcx, [rdi+48h]
0x1800160fc  test    rcx, rcx
0x1800160ff  jz      loc_1800161BC
0x180016105  lea     rdx, [rsi+48h]
0x180016109  call    FwppAllocAndDeepCopyFromVerIndependent_IKEEXT_POLICY2
0x18001610e  jmp     loc_1800161B4
0x180016113  mov     rcx, [rdi+48h]
0x180016117  test    rcx, rcx
0x18001611a  jz      loc_1800161BC
0x180016120  lea     rdx, [rsi+48h]
0x180016124  call    FwppAllocAndDeepCopyFromVerIndependent_IPSEC_TUNNEL_POLICY2
0x180016129  jmp     loc_1800161B4
0x18001612e  mov     rcx, [rdi+48h]
0x180016132  test    rcx, rcx
0x180016135  jz      loc_1800161BC
0x18001613b  lea     rdx, [rsi+48h]
0x18001613f  call    FwppAllocAndDeepCopyFromVerIndependent_IPSEC_TRANSPORT_POLICY2
0x180016144  jmp     short loc_1800161B4
0x180016146  mov     rcx, [rdi+48h]
0x18001614a  test    rcx, rcx
0x18001614d  jz      short loc_1800161BC
0x18001614f  lea     rdx, [rsi+48h]
0x180016153  call    FwppAllocAndDeepCopyFromVerIndependent_IPSEC_KEYING_POLICY1
0x180016158  jmp     short loc_1800161B4
0x18001615a  sub     ecx, 7
0x18001615d  jz      short loc_1800161A2
0x18001615f  sub     ecx, 1
0x180016162  jz      short loc_18001618E
0x180016164  sub     ecx, 1
0x180016167  jz      short loc_180016113
0x180016169  sub     ecx, 1
0x18001616c  jz      short loc_1800160F8
0x18001616e  sub     ecx, 1
0x180016171  jz      short loc_18001617A
0x180016173  cmp     ecx, 1
0x180016176  jnz     short loc_1800161BC
0x180016178  jmp     short loc_18001612E
0x18001617a  mov     rcx, [rdi+48h]
0x18001617e  test    rcx, rcx
0x180016181  jz      short loc_1800161BC
0x180016183  lea     rdx, [rsi+48h]
0x180016187  call    FwppAllocAndDeepCopyFromVerIndependent_IPSEC_DOSP_OPTIONS0
0x18001618c  jmp     short loc_1800161B4
0x18001618e  mov     rcx, [rdi+48h]
0x180016192  test    rcx, rcx
0x180016195  jz      short loc_1800161BC
0x180016197  lea     rdx, [rsi+48h]
0x18001619b  call    FwppAllocAndDeepCopyToVerIndependent_FWP_BYTE_BLOB
0x1800161a0  jmp     short loc_1800161B4
0x1800161a2  mov     rcx, [rdi+48h]
0x1800161a6  test    rcx, rcx
0x1800161a9  jz      short loc_1800161BC
0x1800161ab  lea     rdx, [rsi+48h]
0x1800161af  call    FwppAllocAndDeepCopyFromVerIndependent_FWPM_CLASSIFY_OPTIONS0
0x1800161b4  mov     rbx, rax
0x1800161b7  test    rax, rax
0x1800161ba  jnz     short loc_1800161D1
0x1800161bc  lea     rdx, [rsi+50h]
0x1800161c0  lea     rcx, [rdi+50h]
0x1800161c4  call    FwppDeepCopyFromVerIndependent_UINT64
0x1800161c9  mov     rbx, rax
0x1800161cc  test    rax, rax
0x1800161cf  jz      short loc_1800161ED
0x1800161d1  mov     rcx, rsi
0x1800161d4  call    FwppDeepFreeContentsOnly_FWPM_PROVIDER_CONTEXT2
0x1800161d9  test    rbx, rbx
0x1800161dc  jz      short loc_1800161ED
0x1800161de  lea     rdx, aFwppdeepcopyfr_133; "FwppDeepCopyFromVerIndependent_FWPM_PRO"...
0x1800161e5  mov     rcx, rbx
0x1800161e8  call    WfpReportError
0x1800161ed  mov     rax, rbx
0x1800161f0  add     rsp, 28h
0x1800161f4  pop     r14
0x1800161f6  pop     rdi
0x1800161f7  pop     rsi
0x1800161f8  pop     rbx
0x1800161f9  retn
0x1800161fb  mov     r8d, 0C022001Ch
0x180016201  lea     rdx, aFwppdeepcopyfr_133; "FwppDeepCopyFromVerIndependent_FWPM_PRO"...
0x180016208  call    WfpReportSysErrorAsNtStatus
0x18001620d  jmp     short loc_1800161C9
```
