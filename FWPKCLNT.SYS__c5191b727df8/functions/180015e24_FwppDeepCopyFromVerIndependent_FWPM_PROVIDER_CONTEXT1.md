# FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT1

- ea: `0x180015e24`
- end: `0x18001600d`
- name: `FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT1`
- size: `489`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x180011f70`

## callees

- `0x180004904`
- `0x18000c9b4`
- `0x1800123d8`
- `0x180012618`
- `0x180012738`
- `0x180012858`
- `0x180012a98`
- `0x180015e24`
- `0x180018660`
- `0x18005981c`
- `0x180059b64`
- `0x18005a15c`
- `0x18005dd70`
- `0x18005e1f0`
- `0x18005e244`
- `0x18005e7b8`
- `0x180061318`
- `0x180064634`

## string_xrefs

- `0x180015fdc`: `FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT1`
- `0x180015fff`: `FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT1`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT1(__int64 a1, __int64 a2)
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
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rax

  if ( !a1 || !a2 )
  {
    v23 = WfpReportSysErrorAsNtStatus(a1, (int)"FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT1", -1071513572);
LABEL_39:
    v4 = v23;
    if ( !v23 )
      return v4;
    goto LABEL_40;
  }
  v4 = FwppDeepCopyFromVerIndependent_GUID(a1, a2);
  if ( v4 )
    goto LABEL_40;
  v4 = FwppDeepCopyFromVerIndependent_FWPM_DISPLAY_DATA0(a1 + 16, a2 + 16);
  if ( v4 )
    goto LABEL_40;
  v4 = FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT_FLAGS(a1 + 32, a2 + 32);
  if ( v4 )
    goto LABEL_40;
  v5 = *(_QWORD *)(a1 + 40);
  if ( v5 )
  {
    v4 = FwppAllocAndDeepCopyFromVerIndependent_GUID(v5, a2 + 40);
    if ( v4 )
      goto LABEL_40;
  }
  v4 = FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB((void **)(a1 + 48), (_DWORD *)(a2 + 48));
  if ( v4 )
    goto LABEL_40;
  v4 = FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT_TYPE(a1 + 64, a2 + 64);
  if ( v4 )
    goto LABEL_40;
  v6 = *(_DWORD *)(a1 + 64);
  if ( v6 > 6 )
  {
    v16 = v6 - 7;
    if ( !v16 )
    {
      v22 = *(_QWORD *)(a1 + 72);
      if ( !v22 )
        goto LABEL_38;
      v12 = FwppAllocAndDeepCopyFromVerIndependent_FWPM_CLASSIFY_OPTIONS0(v22, a2 + 72);
      goto LABEL_37;
    }
    v17 = v16 - 1;
    if ( !v17 )
    {
      v21 = *(_QWORD *)(a1 + 72);
      if ( !v21 )
        goto LABEL_38;
      v12 = FwppAllocAndDeepCopyToVerIndependent_FWP_BYTE_BLOB(v21, a2 + 72);
      goto LABEL_37;
    }
    v18 = v17 - 1;
    if ( !v18 )
      goto LABEL_20;
    v19 = v18 - 1;
    if ( v19 )
    {
      if ( v19 != 1 )
        goto LABEL_38;
      v20 = *(_QWORD *)(a1 + 72);
      if ( !v20 )
        goto LABEL_38;
      v12 = FwppAllocAndDeepCopyFromVerIndependent_IPSEC_DOSP_OPTIONS0(v20, a2 + 72);
      goto LABEL_37;
    }
LABEL_18:
    v11 = *(_QWORD *)(a1 + 72);
    if ( v11 )
    {
      v12 = FwppAllocAndDeepCopyFromVerIndependent_IKEEXT_POLICY1(v11, a2 + 72);
      goto LABEL_37;
    }
LABEL_38:
    v23 = FwppDeepCopyFromVerIndependent_UINT64(a1 + 80, a2 + 80);
    goto LABEL_39;
  }
  if ( v6 == 6 )
    goto LABEL_18;
  if ( !v6 )
  {
    v15 = *(_QWORD *)(a1 + 72);
    if ( !v15 )
      goto LABEL_38;
    v12 = FwppAllocAndDeepCopyFromVerIndependent_IPSEC_KEYING_POLICY0(v15, a2 + 72);
    goto LABEL_37;
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
          goto LABEL_38;
        goto LABEL_18;
      }
      goto LABEL_20;
    }
LABEL_22:
    v14 = *(_QWORD *)(a1 + 72);
    if ( !v14 )
      goto LABEL_38;
    v12 = FwppAllocAndDeepCopyFromVerIndependent_IPSEC_TRANSPORT_POLICY1(v14, a2 + 72);
    goto LABEL_37;
  }
LABEL_20:
  v13 = *(_QWORD *)(a1 + 72);
  if ( !v13 )
    goto LABEL_38;
  v12 = FwppAllocAndDeepCopyFromVerIndependent_IPSEC_TUNNEL_POLICY1(v13, a2 + 72);
LABEL_37:
  v4 = v12;
  if ( !v12 )
    goto LABEL_38;
LABEL_40:
  FwppDeepFreeContentsOnly_FWPM_PROVIDER_CONTEXT1(a2);
  if ( v4 )
    WfpReportError(v4, (int)"FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT1");
  return v4;
}

```

## disassembly

```asm
0x180015e24  push    rbx
0x180015e26  push    rsi
0x180015e27  push    rdi
0x180015e28  push    r14
0x180015e2a  sub     rsp, 28h
0x180015e2e  mov     rsi, rdx
0x180015e31  mov     rdi, rcx
0x180015e34  test    rcx, rcx
0x180015e37  jz      loc_180015FF9
0x180015e3d  test    rdx, rdx
0x180015e40  jz      loc_180015FF9
0x180015e46  call    FwppDeepCopyFromVerIndependent_GUID
0x180015e4b  mov     rbx, rax
0x180015e4e  test    rax, rax
0x180015e51  jnz     loc_180015FCF
0x180015e57  lea     rdx, [rsi+10h]
0x180015e5b  lea     rcx, [rdi+10h]
0x180015e5f  call    FwppDeepCopyFromVerIndependent_FWPM_DISPLAY_DATA0
0x180015e64  mov     rbx, rax
0x180015e67  test    rax, rax
0x180015e6a  jnz     loc_180015FCF
0x180015e70  lea     rdx, [rsi+20h]
0x180015e74  lea     rcx, [rdi+20h]
0x180015e78  call    FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT_FLAGS
0x180015e7d  mov     rbx, rax
0x180015e80  test    rax, rax
0x180015e83  jnz     loc_180015FCF
0x180015e89  mov     rcx, [rdi+28h]
0x180015e8d  test    rcx, rcx
0x180015e90  jz      short loc_180015EA7
0x180015e92  lea     rdx, [rsi+28h]
0x180015e96  call    FwppAllocAndDeepCopyFromVerIndependent_GUID
0x180015e9b  mov     rbx, rax
0x180015e9e  test    rax, rax
0x180015ea1  jnz     loc_180015FCF
0x180015ea7  lea     rdx, [rsi+30h]
0x180015eab  lea     rcx, [rdi+30h]
0x180015eaf  call    FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB
0x180015eb4  mov     rbx, rax
0x180015eb7  test    rax, rax
0x180015eba  jnz     loc_180015FCF
0x180015ec0  lea     rdx, [rsi+40h]
0x180015ec4  lea     rcx, [rdi+40h]
0x180015ec8  call    FwppDeepCopyFromVerIndependent_FWPM_PROVIDER_CONTEXT_TYPE
0x180015ecd  mov     rbx, rax
0x180015ed0  test    rax, rax
0x180015ed3  jnz     loc_180015FCF
0x180015ed9  mov     ecx, [rdi+40h]
0x180015edc  cmp     ecx, 6
0x180015edf  jg      short loc_180015F5F
0x180015ee1  jz      short loc_180015F04
0x180015ee3  test    ecx, ecx
0x180015ee5  jz      short loc_180015F4B
0x180015ee7  sub     ecx, 1
0x180015eea  jz      short loc_180015F37
0x180015eec  sub     ecx, 1
0x180015eef  jz      short loc_180015F1F
0x180015ef1  sub     ecx, 1
0x180015ef4  jz      short loc_180015F37
0x180015ef6  sub     ecx, 1
0x180015ef9  jz      short loc_180015F1F
0x180015efb  cmp     ecx, 1
0x180015efe  jnz     loc_180015FBA
0x180015f04  mov     rcx, [rdi+48h]
0x180015f08  test    rcx, rcx
0x180015f0b  jz      loc_180015FBA
0x180015f11  lea     rdx, [rsi+48h]
0x180015f15  call    FwppAllocAndDeepCopyFromVerIndependent_IKEEXT_POLICY1
0x180015f1a  jmp     loc_180015FB2
0x180015f1f  mov     rcx, [rdi+48h]
0x180015f23  test    rcx, rcx
0x180015f26  jz      loc_180015FBA
0x180015f2c  lea     rdx, [rsi+48h]
0x180015f30  call    FwppAllocAndDeepCopyFromVerIndependent_IPSEC_TUNNEL_POLICY1
0x180015f35  jmp     short loc_180015FB2
0x180015f37  mov     rcx, [rdi+48h]
0x180015f3b  test    rcx, rcx
0x180015f3e  jz      short loc_180015FBA
0x180015f40  lea     rdx, [rsi+48h]
0x180015f44  call    FwppAllocAndDeepCopyFromVerIndependent_IPSEC_TRANSPORT_POLICY1
0x180015f49  jmp     short loc_180015FB2
0x180015f4b  mov     rcx, [rdi+48h]
0x180015f4f  test    rcx, rcx
0x180015f52  jz      short loc_180015FBA
0x180015f54  lea     rdx, [rsi+48h]
0x180015f58  call    FwppAllocAndDeepCopyFromVerIndependent_IPSEC_KEYING_POLICY0
0x180015f5d  jmp     short loc_180015FB2
0x180015f5f  sub     ecx, 7
0x180015f62  jz      short loc_180015FA0
0x180015f64  sub     ecx, 1
0x180015f67  jz      short loc_180015F8C
0x180015f69  sub     ecx, 1
0x180015f6c  jz      short loc_180015F1F
0x180015f6e  sub     ecx, 1
0x180015f71  jz      short loc_180015F04
0x180015f73  cmp     ecx, 1
0x180015f76  jnz     short loc_180015FBA
0x180015f78  mov     rcx, [rdi+48h]
0x180015f7c  test    rcx, rcx
0x180015f7f  jz      short loc_180015FBA
0x180015f81  lea     rdx, [rsi+48h]
0x180015f85  call    FwppAllocAndDeepCopyFromVerIndependent_IPSEC_DOSP_OPTIONS0
0x180015f8a  jmp     short loc_180015FB2
0x180015f8c  mov     rcx, [rdi+48h]
0x180015f90  test    rcx, rcx
0x180015f93  jz      short loc_180015FBA
0x180015f95  lea     rdx, [rsi+48h]
0x180015f99  call    FwppAllocAndDeepCopyToVerIndependent_FWP_BYTE_BLOB
0x180015f9e  jmp     short loc_180015FB2
0x180015fa0  mov     rcx, [rdi+48h]
0x180015fa4  test    rcx, rcx
0x180015fa7  jz      short loc_180015FBA
0x180015fa9  lea     rdx, [rsi+48h]
0x180015fad  call    FwppAllocAndDeepCopyFromVerIndependent_FWPM_CLASSIFY_OPTIONS0
0x180015fb2  mov     rbx, rax
0x180015fb5  test    rax, rax
0x180015fb8  jnz     short loc_180015FCF
0x180015fba  lea     rdx, [rsi+50h]
0x180015fbe  lea     rcx, [rdi+50h]
0x180015fc2  call    FwppDeepCopyFromVerIndependent_UINT64
0x180015fc7  mov     rbx, rax
0x180015fca  test    rax, rax
0x180015fcd  jz      short loc_180015FEB
0x180015fcf  mov     rcx, rsi
0x180015fd2  call    FwppDeepFreeContentsOnly_FWPM_PROVIDER_CONTEXT1
0x180015fd7  test    rbx, rbx
0x180015fda  jz      short loc_180015FEB
0x180015fdc  lea     rdx, aFwppdeepcopyfr_55; "FwppDeepCopyFromVerIndependent_FWPM_PRO"...
0x180015fe3  mov     rcx, rbx
0x180015fe6  call    WfpReportError
0x180015feb  mov     rax, rbx
0x180015fee  add     rsp, 28h
0x180015ff2  pop     r14
0x180015ff4  pop     rdi
0x180015ff5  pop     rsi
0x180015ff6  pop     rbx
0x180015ff7  retn
0x180015ff9  mov     r8d, 0C022001Ch
0x180015fff  lea     rdx, aFwppdeepcopyfr_55; "FwppDeepCopyFromVerIndependent_FWPM_PRO"...
0x180016006  call    WfpReportSysErrorAsNtStatus
0x18001600b  jmp     short loc_180015FC7
```
