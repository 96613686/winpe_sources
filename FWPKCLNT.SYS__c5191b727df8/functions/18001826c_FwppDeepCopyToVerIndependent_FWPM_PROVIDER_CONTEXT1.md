# FwppDeepCopyToVerIndependent_FWPM_PROVIDER_CONTEXT1

- ea: `0x18001826c`
- end: `0x180018455`
- name: `FwppDeepCopyToVerIndependent_FWPM_PROVIDER_CONTEXT1`
- size: `489`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x180012978`

## callees

- `0x180004904`
- `0x18000c9b4`
- `0x180012a98`
- `0x180012c50`
- `0x180012d70`
- `0x180012e90`
- `0x180012fb0`
- `0x18001826c`
- `0x180018660`
- `0x180019e68`
- `0x18005a7e4`
- `0x18005abb0`
- `0x18005af7c`
- `0x1800615bc`
- `0x180061818`
- `0x18006186c`
- `0x180062224`
- `0x1800642b8`

## string_xrefs

- `0x180018424`: `FwppDeepCopyToVerIndependent_FWPM_PROVIDER_CONTEXT1`
- `0x180018447`: `FwppDeepCopyToVerIndependent_FWPM_PROVIDER_CONTEXT1`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyToVerIndependent_FWPM_PROVIDER_CONTEXT1(__int64 a1, __int64 a2)
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
    v23 = WfpReportSysErrorAsNtStatus(a1, (int)"FwppDeepCopyToVerIndependent_FWPM_PROVIDER_CONTEXT1", -1071513572);
LABEL_39:
    v4 = v23;
    if ( !v23 )
      return v4;
    goto LABEL_40;
  }
  v4 = FwppDeepCopyToVerIndependent_GUID();
  if ( v4 )
    goto LABEL_40;
  v4 = FwppDeepCopyToVerIndependent_FWPM_DISPLAY_DATA0(a1 + 16, a2 + 16);
  if ( v4 )
    goto LABEL_40;
  v4 = FwppDeepCopyToVerIndependent_FWPM_PROVIDER_CONTEXT_FLAGS(a1 + 32, a2 + 32);
  if ( v4 )
    goto LABEL_40;
  v5 = *(_QWORD *)(a1 + 40);
  if ( v5 )
  {
    v4 = FwppAllocAndDeepCopyToVerIndependent_GUID(v5, a2 + 40);
    if ( v4 )
      goto LABEL_40;
  }
  v4 = FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB((void **)(a1 + 48), (_DWORD *)(a2 + 48));
  if ( v4 )
    goto LABEL_40;
  v4 = FwppDeepCopyToVerIndependent_FWPM_PROVIDER_CONTEXT_TYPE(a1 + 64, a2 + 64);
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
      v12 = FwppAllocAndDeepCopyToVerIndependent_FWPM_CLASSIFY_OPTIONS0(v22, a2 + 72);
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
      v12 = FwppAllocAndDeepCopyToVerIndependent_IPSEC_DOSP_OPTIONS0(v20, a2 + 72);
      goto LABEL_37;
    }
LABEL_18:
    v11 = *(_QWORD *)(a1 + 72);
    if ( v11 )
    {
      v12 = FwppAllocAndDeepCopyToVerIndependent_IKEEXT_POLICY1(v11, a2 + 72);
      goto LABEL_37;
    }
LABEL_38:
    v23 = FwppDeepCopyToVerIndependent_UINT64(a1 + 80, a2 + 80);
    goto LABEL_39;
  }
  if ( v6 == 6 )
    goto LABEL_18;
  if ( !v6 )
  {
    v15 = *(_QWORD *)(a1 + 72);
    if ( !v15 )
      goto LABEL_38;
    v12 = FwppAllocAndDeepCopyToVerIndependent_IPSEC_KEYING_POLICY0(v15, a2 + 72);
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
    v12 = FwppAllocAndDeepCopyToVerIndependent_IPSEC_TRANSPORT_POLICY1(v14, a2 + 72);
    goto LABEL_37;
  }
LABEL_20:
  v13 = *(_QWORD *)(a1 + 72);
  if ( !v13 )
    goto LABEL_38;
  v12 = FwppAllocAndDeepCopyToVerIndependent_IPSEC_TUNNEL_POLICY1(v13, a2 + 72);
LABEL_37:
  v4 = v12;
  if ( !v12 )
    goto LABEL_38;
LABEL_40:
  FwppDeepFreeContentsOnly_FWPM_PROVIDER_CONTEXT3(a2);
  if ( v4 )
    WfpReportError(v4, (int)"FwppDeepCopyToVerIndependent_FWPM_PROVIDER_CONTEXT1");
  return v4;
}

```

## disassembly

```asm
0x18001826c  push    rbx
0x18001826e  push    rsi
0x18001826f  push    rdi
0x180018270  push    r14
0x180018272  sub     rsp, 28h
0x180018276  mov     rsi, rdx
0x180018279  mov     rdi, rcx
0x18001827c  test    rcx, rcx
0x18001827f  jz      loc_180018441
0x180018285  test    rdx, rdx
0x180018288  jz      loc_180018441
0x18001828e  call    FwppDeepCopyToVerIndependent_GUID
0x180018293  mov     rbx, rax
0x180018296  test    rax, rax
0x180018299  jnz     loc_180018417
0x18001829f  lea     rdx, [rsi+10h]
0x1800182a3  lea     rcx, [rdi+10h]
0x1800182a7  call    FwppDeepCopyToVerIndependent_FWPM_DISPLAY_DATA0
0x1800182ac  mov     rbx, rax
0x1800182af  test    rax, rax
0x1800182b2  jnz     loc_180018417
0x1800182b8  lea     rdx, [rsi+20h]
0x1800182bc  lea     rcx, [rdi+20h]
0x1800182c0  call    FwppDeepCopyToVerIndependent_FWPM_PROVIDER_CONTEXT_FLAGS
0x1800182c5  mov     rbx, rax
0x1800182c8  test    rax, rax
0x1800182cb  jnz     loc_180018417
0x1800182d1  mov     rcx, [rdi+28h]
0x1800182d5  test    rcx, rcx
0x1800182d8  jz      short loc_1800182EF
0x1800182da  lea     rdx, [rsi+28h]
0x1800182de  call    FwppAllocAndDeepCopyToVerIndependent_GUID
0x1800182e3  mov     rbx, rax
0x1800182e6  test    rax, rax
0x1800182e9  jnz     loc_180018417
0x1800182ef  lea     rdx, [rsi+30h]
0x1800182f3  lea     rcx, [rdi+30h]
0x1800182f7  call    FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB
0x1800182fc  mov     rbx, rax
0x1800182ff  test    rax, rax
0x180018302  jnz     loc_180018417
0x180018308  lea     rdx, [rsi+40h]
0x18001830c  lea     rcx, [rdi+40h]
0x180018310  call    FwppDeepCopyToVerIndependent_FWPM_PROVIDER_CONTEXT_TYPE
0x180018315  mov     rbx, rax
0x180018318  test    rax, rax
0x18001831b  jnz     loc_180018417
0x180018321  mov     ecx, [rdi+40h]
0x180018324  cmp     ecx, 6
0x180018327  jg      short loc_1800183A7
0x180018329  jz      short loc_18001834C
0x18001832b  test    ecx, ecx
0x18001832d  jz      short loc_180018393
0x18001832f  sub     ecx, 1
0x180018332  jz      short loc_18001837F
0x180018334  sub     ecx, 1
0x180018337  jz      short loc_180018367
0x180018339  sub     ecx, 1
0x18001833c  jz      short loc_18001837F
0x18001833e  sub     ecx, 1
0x180018341  jz      short loc_180018367
0x180018343  cmp     ecx, 1
0x180018346  jnz     loc_180018402
0x18001834c  mov     rcx, [rdi+48h]
0x180018350  test    rcx, rcx
0x180018353  jz      loc_180018402
0x180018359  lea     rdx, [rsi+48h]
0x18001835d  call    FwppAllocAndDeepCopyToVerIndependent_IKEEXT_POLICY1
0x180018362  jmp     loc_1800183FA
0x180018367  mov     rcx, [rdi+48h]
0x18001836b  test    rcx, rcx
0x18001836e  jz      loc_180018402
0x180018374  lea     rdx, [rsi+48h]
0x180018378  call    FwppAllocAndDeepCopyToVerIndependent_IPSEC_TUNNEL_POLICY1
0x18001837d  jmp     short loc_1800183FA
0x18001837f  mov     rcx, [rdi+48h]
0x180018383  test    rcx, rcx
0x180018386  jz      short loc_180018402
0x180018388  lea     rdx, [rsi+48h]
0x18001838c  call    FwppAllocAndDeepCopyToVerIndependent_IPSEC_TRANSPORT_POLICY1
0x180018391  jmp     short loc_1800183FA
0x180018393  mov     rcx, [rdi+48h]
0x180018397  test    rcx, rcx
0x18001839a  jz      short loc_180018402
0x18001839c  lea     rdx, [rsi+48h]
0x1800183a0  call    FwppAllocAndDeepCopyToVerIndependent_IPSEC_KEYING_POLICY0
0x1800183a5  jmp     short loc_1800183FA
0x1800183a7  sub     ecx, 7
0x1800183aa  jz      short loc_1800183E8
0x1800183ac  sub     ecx, 1
0x1800183af  jz      short loc_1800183D4
0x1800183b1  sub     ecx, 1
0x1800183b4  jz      short loc_180018367
0x1800183b6  sub     ecx, 1
0x1800183b9  jz      short loc_18001834C
0x1800183bb  cmp     ecx, 1
0x1800183be  jnz     short loc_180018402
0x1800183c0  mov     rcx, [rdi+48h]
0x1800183c4  test    rcx, rcx
0x1800183c7  jz      short loc_180018402
0x1800183c9  lea     rdx, [rsi+48h]
0x1800183cd  call    FwppAllocAndDeepCopyToVerIndependent_IPSEC_DOSP_OPTIONS0
0x1800183d2  jmp     short loc_1800183FA
0x1800183d4  mov     rcx, [rdi+48h]
0x1800183d8  test    rcx, rcx
0x1800183db  jz      short loc_180018402
0x1800183dd  lea     rdx, [rsi+48h]
0x1800183e1  call    FwppAllocAndDeepCopyToVerIndependent_FWP_BYTE_BLOB
0x1800183e6  jmp     short loc_1800183FA
0x1800183e8  mov     rcx, [rdi+48h]
0x1800183ec  test    rcx, rcx
0x1800183ef  jz      short loc_180018402
0x1800183f1  lea     rdx, [rsi+48h]
0x1800183f5  call    FwppAllocAndDeepCopyToVerIndependent_FWPM_CLASSIFY_OPTIONS0
0x1800183fa  mov     rbx, rax
0x1800183fd  test    rax, rax
0x180018400  jnz     short loc_180018417
0x180018402  lea     rdx, [rsi+50h]
0x180018406  lea     rcx, [rdi+50h]
0x18001840a  call    FwppDeepCopyToVerIndependent_UINT64
0x18001840f  mov     rbx, rax
0x180018412  test    rax, rax
0x180018415  jz      short loc_180018433
0x180018417  mov     rcx, rsi
0x18001841a  call    FwppDeepFreeContentsOnly_FWPM_PROVIDER_CONTEXT3
0x18001841f  test    rbx, rbx
0x180018422  jz      short loc_180018433
0x180018424  lea     rdx, aFwppdeepcopyto_100; "FwppDeepCopyToVerIndependent_FWPM_PROVI"...
0x18001842b  mov     rcx, rbx
0x18001842e  call    WfpReportError
0x180018433  mov     rax, rbx
0x180018436  add     rsp, 28h
0x18001843a  pop     r14
0x18001843c  pop     rdi
0x18001843d  pop     rsi
0x18001843e  pop     rbx
0x18001843f  retn
0x180018441  mov     r8d, 0C022001Ch
0x180018447  lea     rdx, aFwppdeepcopyto_100; "FwppDeepCopyToVerIndependent_FWPM_PROVI"...
0x18001844e  call    WfpReportSysErrorAsNtStatus
0x180018453  jmp     short loc_18001840F
```
