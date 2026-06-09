# FwppDeepCopyToVerIndependent_IKEEXT_CERTIFICATE_CRITERIA0

- ea: `0x180018ad8`
- end: `0x180018c5b`
- name: `FwppDeepCopyToVerIndependent_IKEEXT_CERTIFICATE_CRITERIA0`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180013b08`

## callees

- `0x180004904`
- `0x18000891c`
- `0x18000c9b4`
- `0x180018660`
- `0x180018ad8`
- `0x180018c64`
- `0x180018d04`
- `0x18001a0b4`
- `0x18001a62c`
- `0x18001a648`
- `0x1800624a0`

## string_xrefs

- `0x180018c25`: `FwppAllocAndDeepCopyToVerIndependent_IKEEXT_CERT_EKUS0`
- `0x180018c3e`: `FwppAllocAndDeepCopyToVerIndependent_IKEEXT_CERT_NAME0`
- `0x180018bfd`: `FwppDeepCopyToVerIndependent_IKEEXT_CERTIFICATE_CRITERIA0`
- `0x180018c4d`: `FwppDeepCopyToVerIndependent_IKEEXT_CERTIFICATE_CRITERIA0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyToVerIndependent_IKEEXT_CERTIFICATE_CRITERIA0(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  __int64 v5; // r15
  __int64 v6; // rax
  _OWORD *v7; // rbp
  _OWORD *v8; // rdx
  __int64 v9; // r15
  __int64 v10; // rax
  _OWORD *v11; // rbp
  _OWORD *v12; // rdx
  __int64 v13; // rax
  const char *v15; // rdx
  _OWORD *v16; // [rsp+60h] [rbp+8h] BYREF

  if ( !a1 || !a2 )
  {
    v13 = WfpReportSysErrorAsNtStatus(a1, (int)"FwppDeepCopyToVerIndependent_IKEEXT_CERTIFICATE_CRITERIA0", -1071513572);
LABEL_16:
    v4 = v13;
    if ( !v13 )
      return v4;
    goto LABEL_17;
  }
  v4 = FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB(a1, a2);
  if ( !v4 )
  {
    v4 = FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB(a1 + 16, a2 + 16);
    if ( !v4 )
    {
      v5 = *(_QWORD *)(a1 + 32);
      if ( v5 )
      {
        v16 = 0;
        if ( a2 != -32 )
        {
          v6 = WfpPoolAllocNonPaged(16, 1886418758, &v16);
          v7 = v16;
          v4 = v6;
          if ( v6 || (v8 = v16, *v16 = 0, (v4 = FwppDeepCopyToVerIndependent_IKEEXT_CERT_EKUS0(v5, v8)) != 0) )
          {
            FwppDeepFree_IKEEXT_CERT_EKUS0(v7);
            v15 = "FwppAllocAndDeepCopyToVerIndependent_IKEEXT_CERT_EKUS0";
LABEL_21:
            WfpReportError(v4, (int)v15);
            goto LABEL_17;
          }
          *(_QWORD *)(a2 + 32) = v7;
        }
      }
      v9 = *(_QWORD *)(a1 + 40);
      if ( !v9 )
        goto LABEL_15;
      v16 = 0;
      if ( a2 == -40 )
        goto LABEL_15;
      v10 = WfpPoolAllocNonPaged(16, 1886418758, &v16);
      v11 = v16;
      v4 = v10;
      if ( !v10 )
      {
        v12 = v16;
        *v16 = 0;
        v4 = FwppDeepCopyToVerIndependent_IKEEXT_CERT_NAME0(v9, v12);
        if ( !v4 )
        {
          *(_QWORD *)(a2 + 40) = v11;
LABEL_15:
          v13 = FwppDeepCopyToVerIndependent_IKEEXT_CERT_FLAGS(a1 + 48, a2 + 48);
          goto LABEL_16;
        }
      }
      FwppDeepFree_IKEEXT_CERT_NAME0(v11);
      v15 = "FwppAllocAndDeepCopyToVerIndependent_IKEEXT_CERT_NAME0";
      goto LABEL_21;
    }
  }
LABEL_17:
  FwppDeepFreeContentsOnly_IKEEXT_CERTIFICATE_CRITERIA0(a2);
  if ( v4 )
    WfpReportError(v4, (int)"FwppDeepCopyToVerIndependent_IKEEXT_CERTIFICATE_CRITERIA0");
  return v4;
}

```

## disassembly

```asm
0x180018ad8  push    rbx
0x180018ada  push    rbp
0x180018adb  push    rsi
0x180018adc  push    rdi
0x180018add  push    r14
0x180018adf  push    r15
0x180018ae1  sub     rsp, 28h
0x180018ae5  mov     rdi, rdx
0x180018ae8  mov     rsi, rcx
0x180018aeb  test    rcx, rcx
0x180018aee  jz      loc_180018C47
0x180018af4  test    rdx, rdx
0x180018af7  jz      loc_180018C47
0x180018afd  call    FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB
0x180018b02  mov     rbx, rax
0x180018b05  test    rax, rax
0x180018b08  jnz     loc_180018BF0
0x180018b0e  lea     rdx, [rdi+10h]
0x180018b12  lea     rcx, [rsi+10h]
0x180018b16  call    FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB
0x180018b1b  mov     rbx, rax
0x180018b1e  test    rax, rax
0x180018b21  jnz     loc_180018BF0
0x180018b27  mov     r15, [rsi+20h]
0x180018b2b  test    r15, r15
0x180018b2e  jz      short loc_180018B82
0x180018b30  lea     r14, [rdi+20h]
0x180018b34  mov     [rsp+58h+arg_0], rax
0x180018b39  test    r14, r14
0x180018b3c  jz      short loc_180018B82
0x180018b3e  lea     r8, [rsp+58h+arg_0]
0x180018b43  mov     edx, 70707746h
0x180018b48  lea     ecx, [rax+10h]
0x180018b4b  call    WfpPoolAllocNonPaged
0x180018b50  mov     rbp, [rsp+58h+arg_0]
0x180018b55  mov     rbx, rax
0x180018b58  test    rax, rax
0x180018b5b  jnz     loc_180018C1D
0x180018b61  xorps   xmm0, xmm0
0x180018b64  mov     rdx, rbp
0x180018b67  mov     rcx, r15
0x180018b6a  movups  xmmword ptr [rbp+0], xmm0
0x180018b6e  call    FwppDeepCopyToVerIndependent_IKEEXT_CERT_EKUS0
0x180018b73  mov     rbx, rax
0x180018b76  test    rax, rax
0x180018b79  jnz     loc_180018C1D
0x180018b7f  mov     [r14], rbp
0x180018b82  mov     r15, [rsi+28h]
0x180018b86  test    r15, r15
0x180018b89  jz      short loc_180018BDB
0x180018b8b  lea     r14, [rdi+28h]
0x180018b8f  mov     [rsp+58h+arg_0], 0
0x180018b98  test    r14, r14
0x180018b9b  jz      short loc_180018BDB
0x180018b9d  lea     r8, [rsp+58h+arg_0]
0x180018ba2  mov     edx, 70707746h
0x180018ba7  mov     ecx, 10h
0x180018bac  call    WfpPoolAllocNonPaged
0x180018bb1  mov     rbp, [rsp+58h+arg_0]
0x180018bb6  mov     rbx, rax
0x180018bb9  test    rax, rax
0x180018bbc  jnz     short loc_180018C36
0x180018bbe  xorps   xmm0, xmm0
0x180018bc1  mov     rdx, rbp
0x180018bc4  mov     rcx, r15
0x180018bc7  movups  xmmword ptr [rbp+0], xmm0
0x180018bcb  call    FwppDeepCopyToVerIndependent_IKEEXT_CERT_NAME0
0x180018bd0  mov     rbx, rax
0x180018bd3  test    rax, rax
0x180018bd6  jnz     short loc_180018C36
0x180018bd8  mov     [r14], rbp
0x180018bdb  lea     rdx, [rdi+30h]
0x180018bdf  lea     rcx, [rsi+30h]
0x180018be3  call    FwppDeepCopyToVerIndependent_IKEEXT_CERT_FLAGS
0x180018be8  mov     rbx, rax
0x180018beb  test    rax, rax
0x180018bee  jz      short loc_180018C0C
0x180018bf0  mov     rcx, rdi
0x180018bf3  call    FwppDeepFreeContentsOnly_IKEEXT_CERTIFICATE_CRITERIA0
0x180018bf8  test    rbx, rbx
0x180018bfb  jz      short loc_180018C0C
0x180018bfd  lea     rdx, aFwppdeepcopyto_33; "FwppDeepCopyToVerIndependent_IKEEXT_CER"...
0x180018c04  mov     rcx, rbx
0x180018c07  call    WfpReportError
0x180018c0c  mov     rax, rbx
0x180018c0f  add     rsp, 28h
0x180018c13  pop     r15
0x180018c15  pop     r14
0x180018c17  pop     rdi
0x180018c18  pop     rsi
0x180018c19  pop     rbp
0x180018c1a  pop     rbx
0x180018c1b  retn
0x180018c1d  mov     rcx, rbp
0x180018c20  call    FwppDeepFree_IKEEXT_CERT_EKUS0
0x180018c25  lea     rdx, aFwppallocandde_22; "FwppAllocAndDeepCopyToVerIndependent_IK"...
0x180018c2c  mov     rcx, rbx
0x180018c2f  call    WfpReportError
0x180018c34  jmp     short loc_180018BF0
0x180018c36  mov     rcx, rbp
0x180018c39  call    FwppDeepFree_IKEEXT_CERT_NAME0
0x180018c3e  lea     rdx, aFwppallocandde_13; "FwppAllocAndDeepCopyToVerIndependent_IK"...
0x180018c45  jmp     short loc_180018C2C
0x180018c47  mov     r8d, 0C022001Ch
0x180018c4d  lea     rdx, aFwppdeepcopyto_33; "FwppDeepCopyToVerIndependent_IKEEXT_CER"...
0x180018c54  call    WfpReportSysErrorAsNtStatus
0x180018c59  jmp     short loc_180018BE8
```
