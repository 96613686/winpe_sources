# FwppDeepCopyToVerIndependent_IPSEC_SA_TRANSFORM0

- ea: `0x180063a04`
- end: `0x180063b65`
- name: `FwppDeepCopyToVerIndependent_IPSEC_SA_TRANSFORM0`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18005c5d0`

## callees

- `0x1800050cc`
- `0x18000891c`
- `0x18000c9b4`
- `0x18005add8`
- `0x18005ae64`
- `0x180062f0c`
- `0x180063a04`
- `0x180063dec`
- `0x180064fac`
- `0x180065298`

## string_xrefs

- `0x180063b03`: `FwppAllocAndDeepCopyToVerIndependent_IPSEC_CIPHER_TRANSFORM0`
- `0x180063b1e`: `FwppDeepCopyToVerIndependent_IPSEC_SA_TRANSFORM0`
- `0x180063b3f`: `FwppDeepCopyToVerIndependent_IPSEC_SA_TRANSFORM0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyToVerIndependent_IPSEC_SA_TRANSFORM0(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rbp
  __int64 v9; // rax
  _OWORD *v10; // rdi
  _OWORD *v11; // rdx
  _OWORD *v13; // [rsp+50h] [rbp+8h] BYREF

  if ( !a1 || !a2 )
  {
    v4 = WfpReportAppErrorAsNtStatus(a1, (__int64)"FwppDeepCopyToVerIndependent_IPSEC_SA_TRANSFORM0", 3223453724LL);
    goto LABEL_23;
  }
  v4 = FwppDeepCopyToVerIndependent_IPSEC_TRANSFORM_TYPE();
  if ( !v4 )
  {
    if ( *(_DWORD *)a1 == 1 || *(_DWORD *)a1 == 2 )
      goto LABEL_9;
    if ( *(_DWORD *)a1 != 3 )
    {
      if ( *(_DWORD *)a1 == 4 )
      {
        v7 = *(_QWORD *)(a1 + 8);
        if ( !v7 )
          return v4;
        v6 = FwppAllocAndDeepCopyToVerIndependent_IPSEC_AUTH_AND_CIPHER_TRANSFORM0(v7, a2 + 8);
LABEL_11:
        v4 = v6;
        if ( !v6 )
          return v4;
        goto LABEL_24;
      }
      if ( *(_DWORD *)a1 != 5 )
        return v4;
LABEL_9:
      v5 = *(_QWORD *)(a1 + 8);
      if ( !v5 )
        return v4;
      v6 = FwppAllocAndDeepCopyToVerIndependent_IPSEC_AUTH_TRANSFORM0(v5, a2 + 8);
      goto LABEL_11;
    }
    v8 = *(_QWORD *)(a1 + 8);
    if ( !v8 )
      return v4;
    v13 = 0;
    if ( a2 != -8 )
    {
      v9 = WfpPoolAllocNonPaged(16, 1886418758, &v13);
      v10 = v13;
      v4 = v9;
      if ( !v9 )
      {
        v11 = v13;
        *v13 = 0;
        v4 = FwppDeepCopyToVerIndependent_IPSEC_CIPHER_TRANSFORM0(v8, v11);
        if ( !v4 )
        {
          *(_QWORD *)(a2 + 8) = v10;
          return v4;
        }
      }
      FwppDeepFree_IPSEC_AUTH_TRANSFORM0(v10);
      WfpReportError(v4, (int)"FwppAllocAndDeepCopyToVerIndependent_IPSEC_CIPHER_TRANSFORM0");
      goto LABEL_24;
    }
    v4 = 0;
LABEL_23:
    if ( !v4 )
      return v4;
  }
LABEL_24:
  FwppDeepFreeContentsOnly_IPSEC_SA_TRANSFORM0(a2);
  if ( v4 )
    WfpReportError(v4, (int)"FwppDeepCopyToVerIndependent_IPSEC_SA_TRANSFORM0");
  return v4;
}

```

## disassembly

```asm
0x180063a04  mov     [rsp+arg_8], rbx
0x180063a09  mov     [rsp+arg_10], rbp
0x180063a0e  push    rsi
0x180063a0f  push    rdi
0x180063a10  push    r14
0x180063a12  sub     rsp, 30h
0x180063a16  mov     rsi, rdx
0x180063a19  mov     rdi, rcx
0x180063a1c  test    rcx, rcx
0x180063a1f  jz      loc_180063B18
0x180063a25  test    rdx, rdx
0x180063a28  jz      loc_180063B18
0x180063a2e  call    FwppDeepCopyToVerIndependent_IPSEC_TRANSFORM_TYPE
0x180063a33  mov     rbx, rax
0x180063a36  test    rax, rax
0x180063a39  jnz     loc_180063B32
0x180063a3f  mov     eax, [rdi]
0x180063a41  sub     eax, 1
0x180063a44  jz      short loc_180063A5E
0x180063a46  sub     eax, 1
0x180063a49  jz      short loc_180063A5E
0x180063a4b  sub     eax, 1
0x180063a4e  jz      short loc_180063A9D
0x180063a50  sub     eax, 1
0x180063a53  jz      short loc_180063A85
0x180063a55  cmp     eax, 1
0x180063a58  jnz     loc_180063B4E
0x180063a5e  mov     rcx, [rdi+8]
0x180063a62  test    rcx, rcx
0x180063a65  jz      loc_180063B4E
0x180063a6b  lea     rdx, [rsi+8]
0x180063a6f  call    FwppAllocAndDeepCopyToVerIndependent_IPSEC_AUTH_TRANSFORM0
0x180063a74  mov     rbx, rax
0x180063a77  test    rax, rax
0x180063a7a  jnz     loc_180063B32
0x180063a80  jmp     loc_180063B4E
0x180063a85  mov     rcx, [rdi+8]
0x180063a89  test    rcx, rcx
0x180063a8c  jz      loc_180063B4E
0x180063a92  lea     rdx, [rsi+8]
0x180063a96  call    FwppAllocAndDeepCopyToVerIndependent_IPSEC_AUTH_AND_CIPHER_TRANSFORM0
0x180063a9b  jmp     short loc_180063A74
0x180063a9d  mov     rbp, [rdi+8]
0x180063aa1  test    rbp, rbp
0x180063aa4  jz      loc_180063B4E
0x180063aaa  lea     r14, [rsi+8]
0x180063aae  mov     [rsp+48h+arg_0], 0
0x180063ab7  test    r14, r14
0x180063aba  jz      short loc_180063B14
0x180063abc  lea     r8, [rsp+48h+arg_0]
0x180063ac1  mov     edx, 70707746h
0x180063ac6  mov     ecx, 10h
0x180063acb  call    WfpPoolAllocNonPaged
0x180063ad0  mov     rdi, [rsp+48h+arg_0]
0x180063ad5  mov     rbx, rax
0x180063ad8  test    rax, rax
0x180063adb  jnz     short loc_180063AFB
0x180063add  xorps   xmm0, xmm0
0x180063ae0  mov     rdx, rdi
0x180063ae3  mov     rcx, rbp
0x180063ae6  movups  xmmword ptr [rdi], xmm0
0x180063ae9  call    FwppDeepCopyToVerIndependent_IPSEC_CIPHER_TRANSFORM0
0x180063aee  mov     rbx, rax
0x180063af1  test    rax, rax
0x180063af4  jnz     short loc_180063AFB
0x180063af6  mov     [r14], rdi
0x180063af9  jmp     short loc_180063B4E
0x180063afb  mov     rcx, rdi
0x180063afe  call    FwppDeepFree_IPSEC_AUTH_TRANSFORM0
0x180063b03  lea     rdx, aFwppallocandde_51; "FwppAllocAndDeepCopyToVerIndependent_IP"...
0x180063b0a  mov     rcx, rbx
0x180063b0d  call    WfpReportError
0x180063b12  jmp     short loc_180063B32
0x180063b14  xor     ebx, ebx
0x180063b16  jmp     short loc_180063B2D
0x180063b18  mov     r8d, 0C022001Ch
0x180063b1e  lea     rdx, aFwppdeepcopyto_65; "FwppDeepCopyToVerIndependent_IPSEC_SA_T"...
0x180063b25  call    WfpReportAppErrorAsNtStatus
0x180063b2a  mov     rbx, rax
0x180063b2d  test    rbx, rbx
0x180063b30  jz      short loc_180063B4E
0x180063b32  mov     rcx, rsi
0x180063b35  call    FwppDeepFreeContentsOnly_IPSEC_SA_TRANSFORM0
0x180063b3a  test    rbx, rbx
0x180063b3d  jz      short loc_180063B4E
0x180063b3f  lea     rdx, aFwppdeepcopyto_65; "FwppDeepCopyToVerIndependent_IPSEC_SA_T"...
0x180063b46  mov     rcx, rbx
0x180063b49  call    WfpReportError
0x180063b4e  mov     rbp, [rsp+48h+arg_10]
0x180063b53  mov     rax, rbx
0x180063b56  mov     rbx, [rsp+48h+arg_8]
0x180063b5b  add     rsp, 30h
0x180063b5f  pop     r14
0x180063b61  pop     rdi
0x180063b62  pop     rsi
0x180063b63  retn
```
