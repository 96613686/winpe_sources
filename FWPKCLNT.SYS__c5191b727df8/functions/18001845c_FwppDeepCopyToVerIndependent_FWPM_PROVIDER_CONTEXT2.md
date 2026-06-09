# FwppDeepCopyToVerIndependent_FWPM_PROVIDER_CONTEXT2

- ea: `0x18001845c`
- end: `0x180018657`
- name: `FwppDeepCopyToVerIndependent_FWPM_PROVIDER_CONTEXT2`
- size: `507`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x180012a08`

## callees

- `0x180004904`
- `0x18000c9b4`
- `0x180012a98`
- `0x180012ce0`
- `0x180012d70`
- `0x180012e04`
- `0x180012f20`
- `0x180013044`
- `0x18001845c`
- `0x180018660`
- `0x180019e68`
- `0x18005a7e4`
- `0x18005abb0`
- `0x1800615bc`
- `0x180061818`
- `0x18006186c`
- `0x180062224`
- `0x1800642b8`

## string_xrefs

- `0x180018626`: `FwppDeepCopyToVerIndependent_FWPM_PROVIDER_CONTEXT2`
- `0x180018649`: `FwppDeepCopyToVerIndependent_FWPM_PROVIDER_CONTEXT2`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyToVerIndependent_FWPM_PROVIDER_CONTEXT2(__int64 a1, __int64 a2)
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
    v24 = WfpReportSysErrorAsNtStatus(a1, (int)"FwppDeepCopyToVerIndependent_FWPM_PROVIDER_CONTEXT2", -1071513572);
LABEL_41:
    v4 = v24;
    if ( !v24 )
      return v4;
    goto LABEL_42;
  }
  v4 = FwppDeepCopyToVerIndependent_GUID();
  if ( v4 )
    goto LABEL_42;
  v4 = FwppDeepCopyToVerIndependent_FWPM_DISPLAY_DATA0(a1 + 16, a2 + 16);
  if ( v4 )
    goto LABEL_42;
  v4 = FwppDeepCopyToVerIndependent_FWPM_PROVIDER_CONTEXT_FLAGS(a1 + 32, a2 + 32);
  if ( v4 )
    goto LABEL_42;
  v5 = *(_QWORD *)(a1 + 40);
  if ( v5 )
  {
    v4 = FwppAllocAndDeepCopyToVerIndependent_GUID(v5, a2 + 40);
    if ( v4 )
      goto LABEL_42;
  }
  v4 = FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB((void **)(a1 + 48), (_DWORD *)(a2 + 48));
  if ( v4 )
    goto LABEL_42;
  v4 = FwppDeepCopyToVerIndependent_FWPM_PROVIDER_CONTEXT_TYPE(a1 + 64, a2 + 64);
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
      v12 = FwppAllocAndDeepCopyToVerIndependent_FWPM_CLASSIFY_OPTIONS0(v23, a2 + 72);
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
        v12 = FwppAllocAndDeepCopyToVerIndependent_IPSEC_DOSP_OPTIONS0(v21, a2 + 72);
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
      v12 = FwppAllocAndDeepCopyToVerIndependent_IKEEXT_POLICY2(v11, a2 + 72);
      goto LABEL_39;
    }
LABEL_40:
    v24 = FwppDeepCopyToVerIndependent_UINT64(a1 + 80, a2 + 80);
    goto LABEL_41;
  }
  if ( v6 == 6 )
    goto LABEL_18;
  if ( !v6 )
  {
    v15 = *(_QWORD *)(a1 + 72);
    if ( !v15 )
      goto LABEL_40;
    v12 = FwppAllocAndDeepCopyToVerIndependent_IPSEC_KEYING_POLICY1(v15, a2 + 72);
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
    v12 = FwppAllocAndDeepCopyToVerIndependent_IPSEC_TRANSPORT_POLICY2(v14, a2 + 72);
    goto LABEL_39;
  }
LABEL_20:
  v13 = *(_QWORD *)(a1 + 72);
  if ( !v13 )
    goto LABEL_40;
  v12 = FwppAllocAndDeepCopyToVerIndependent_IPSEC_TUNNEL_POLICY2(v13, a2 + 72);
LABEL_39:
  v4 = v12;
  if ( !v12 )
    goto LABEL_40;
LABEL_42:
  FwppDeepFreeContentsOnly_FWPM_PROVIDER_CONTEXT3(a2);
  if ( v4 )
    WfpReportError(v4, (int)"FwppDeepCopyToVerIndependent_FWPM_PROVIDER_CONTEXT2");
  return v4;
}

```

## disassembly

```asm
0x18001845c  push    rbx
0x18001845e  push    rsi
0x18001845f  push    rdi
0x180018460  push    r14
0x180018462  sub     rsp, 28h
0x180018466  mov     rsi, rdx
0x180018469  mov     rdi, rcx
0x18001846c  test    rcx, rcx
0x18001846f  jz      loc_180018643
0x180018475  test    rdx, rdx
0x180018478  jz      loc_180018643
0x18001847e  call    FwppDeepCopyToVerIndependent_GUID
0x180018483  mov     rbx, rax
0x180018486  test    rax, rax
0x180018489  jnz     loc_180018619
0x18001848f  lea     rdx, [rsi+10h]
0x180018493  lea     rcx, [rdi+10h]
0x180018497  call    FwppDeepCopyToVerIndependent_FWPM_DISPLAY_DATA0
0x18001849c  mov     rbx, rax
0x18001849f  test    rax, rax
0x1800184a2  jnz     loc_180018619
0x1800184a8  lea     rdx, [rsi+20h]
0x1800184ac  lea     rcx, [rdi+20h]
0x1800184b0  call    FwppDeepCopyToVerIndependent_FWPM_PROVIDER_CONTEXT_FLAGS
0x1800184b5  mov     rbx, rax
0x1800184b8  test    rax, rax
0x1800184bb  jnz     loc_180018619
0x1800184c1  mov     rcx, [rdi+28h]
0x1800184c5  test    rcx, rcx
0x1800184c8  jz      short loc_1800184DF
0x1800184ca  lea     rdx, [rsi+28h]
0x1800184ce  call    FwppAllocAndDeepCopyToVerIndependent_GUID
0x1800184d3  mov     rbx, rax
0x1800184d6  test    rax, rax
0x1800184d9  jnz     loc_180018619
0x1800184df  lea     rdx, [rsi+30h]
0x1800184e3  lea     rcx, [rdi+30h]
0x1800184e7  call    FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB
0x1800184ec  mov     rbx, rax
0x1800184ef  test    rax, rax
0x1800184f2  jnz     loc_180018619
0x1800184f8  lea     rdx, [rsi+40h]
0x1800184fc  lea     rcx, [rdi+40h]
0x180018500  call    FwppDeepCopyToVerIndependent_FWPM_PROVIDER_CONTEXT_TYPE
0x180018505  mov     rbx, rax
0x180018508  test    rax, rax
0x18001850b  jnz     loc_180018619
0x180018511  mov     ecx, [rdi+40h]
0x180018514  cmp     ecx, 6
0x180018517  jg      loc_1800185A2
0x18001851d  jz      short loc_180018540
0x18001851f  test    ecx, ecx
0x180018521  jz      short loc_18001858E
0x180018523  sub     ecx, 1
0x180018526  jz      short loc_180018576
0x180018528  sub     ecx, 1
0x18001852b  jz      short loc_18001855B
0x18001852d  sub     ecx, 1
0x180018530  jz      short loc_180018576
0x180018532  sub     ecx, 1
0x180018535  jz      short loc_18001855B
0x180018537  cmp     ecx, 1
0x18001853a  jnz     loc_180018604
0x180018540  mov     rcx, [rdi+48h]
0x180018544  test    rcx, rcx
0x180018547  jz      loc_180018604
0x18001854d  lea     rdx, [rsi+48h]
0x180018551  call    FwppAllocAndDeepCopyToVerIndependent_IKEEXT_POLICY2
0x180018556  jmp     loc_1800185FC
0x18001855b  mov     rcx, [rdi+48h]
0x18001855f  test    rcx, rcx
0x180018562  jz      loc_180018604
0x180018568  lea     rdx, [rsi+48h]
0x18001856c  call    FwppAllocAndDeepCopyToVerIndependent_IPSEC_TUNNEL_POLICY2
0x180018571  jmp     loc_1800185FC
0x180018576  mov     rcx, [rdi+48h]
0x18001857a  test    rcx, rcx
0x18001857d  jz      loc_180018604
0x180018583  lea     rdx, [rsi+48h]
0x180018587  call    FwppAllocAndDeepCopyToVerIndependent_IPSEC_TRANSPORT_POLICY2
0x18001858c  jmp     short loc_1800185FC
0x18001858e  mov     rcx, [rdi+48h]
0x180018592  test    rcx, rcx
0x180018595  jz      short loc_180018604
0x180018597  lea     rdx, [rsi+48h]
0x18001859b  call    FwppAllocAndDeepCopyToVerIndependent_IPSEC_KEYING_POLICY1
0x1800185a0  jmp     short loc_1800185FC
0x1800185a2  sub     ecx, 7
0x1800185a5  jz      short loc_1800185EA
0x1800185a7  sub     ecx, 1
0x1800185aa  jz      short loc_1800185D6
0x1800185ac  sub     ecx, 1
0x1800185af  jz      short loc_18001855B
0x1800185b1  sub     ecx, 1
0x1800185b4  jz      short loc_180018540
0x1800185b6  sub     ecx, 1
0x1800185b9  jz      short loc_1800185C2
0x1800185bb  cmp     ecx, 1
0x1800185be  jnz     short loc_180018604
0x1800185c0  jmp     short loc_180018576
0x1800185c2  mov     rcx, [rdi+48h]
0x1800185c6  test    rcx, rcx
0x1800185c9  jz      short loc_180018604
0x1800185cb  lea     rdx, [rsi+48h]
0x1800185cf  call    FwppAllocAndDeepCopyToVerIndependent_IPSEC_DOSP_OPTIONS0
0x1800185d4  jmp     short loc_1800185FC
0x1800185d6  mov     rcx, [rdi+48h]
0x1800185da  test    rcx, rcx
0x1800185dd  jz      short loc_180018604
0x1800185df  lea     rdx, [rsi+48h]
0x1800185e3  call    FwppAllocAndDeepCopyToVerIndependent_FWP_BYTE_BLOB
0x1800185e8  jmp     short loc_1800185FC
0x1800185ea  mov     rcx, [rdi+48h]
0x1800185ee  test    rcx, rcx
0x1800185f1  jz      short loc_180018604
0x1800185f3  lea     rdx, [rsi+48h]
0x1800185f7  call    FwppAllocAndDeepCopyToVerIndependent_FWPM_CLASSIFY_OPTIONS0
0x1800185fc  mov     rbx, rax
0x1800185ff  test    rax, rax
0x180018602  jnz     short loc_180018619
0x180018604  lea     rdx, [rsi+50h]
0x180018608  lea     rcx, [rdi+50h]
0x18001860c  call    FwppDeepCopyToVerIndependent_UINT64
0x180018611  mov     rbx, rax
0x180018614  test    rax, rax
0x180018617  jz      short loc_180018635
0x180018619  mov     rcx, rsi
0x18001861c  call    FwppDeepFreeContentsOnly_FWPM_PROVIDER_CONTEXT3
0x180018621  test    rbx, rbx
0x180018624  jz      short loc_180018635
0x180018626  lea     rdx, aFwppdeepcopyto_32; "FwppDeepCopyToVerIndependent_FWPM_PROVI"...
0x18001862d  mov     rcx, rbx
0x180018630  call    WfpReportError
0x180018635  mov     rax, rbx
0x180018638  add     rsp, 28h
0x18001863c  pop     r14
0x18001863e  pop     rdi
0x18001863f  pop     rsi
0x180018640  pop     rbx
0x180018641  retn
0x180018643  mov     r8d, 0C022001Ch
0x180018649  lea     rdx, aFwppdeepcopyto_32; "FwppDeepCopyToVerIndependent_FWPM_PROVI"...
0x180018650  call    WfpReportSysErrorAsNtStatus
0x180018655  jmp     short loc_180018611
```
