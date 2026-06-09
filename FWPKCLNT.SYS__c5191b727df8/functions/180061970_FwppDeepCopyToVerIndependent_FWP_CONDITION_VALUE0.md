# FwppDeepCopyToVerIndependent_FWP_CONDITION_VALUE0

- ea: `0x180061970`
- end: `0x180061cb2`
- name: `FwppDeepCopyToVerIndependent_FWP_CONDITION_VALUE0`
- size: `834`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation`

## callers

- `0x18005bf80`

## callees

- `0x1800050cc`
- `0x18000891c`
- `0x18000c9b4`
- `0x180012a98`
- `0x1800130d8`
- `0x1800131b0`
- `0x18005a8fc`
- `0x18005a984`
- `0x18005aa0c`
- `0x18005aa98`
- `0x18005ab24`
- `0x18005ad54`
- `0x18005b474`
- `0x18005b4f8`
- `0x180061970`
- `0x180061cb8`
- `0x180061ea4`
- `0x180062bf8`
- `0x180062c4c`
- `0x180062cf4`
- `0x180064210`
- `0x180064264`
- `0x18006430c`
- `0x180064408`
- `0x18006470c`
- `0x180065180`

## string_xrefs

- `0x180061c15`: `FwppAllocAndDeepCopyToVerIndependent_FWP_V4_ADDR_AND_MASK`
- `0x180061c6b`: `FwppDeepCopyToVerIndependent_FWP_CONDITION_VALUE0`
- `0x180061c8c`: `FwppDeepCopyToVerIndependent_FWP_CONDITION_VALUE0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyToVerIndependent_FWP_CONDITION_VALUE0(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  void *v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rbp
  __int64 v32; // rax
  _QWORD *v33; // rdi
  _QWORD *v34; // rdx
  int v35; // ecx
  __int64 v36; // rcx
  __int64 v37; // rcx
  _QWORD *v39; // [rsp+50h] [rbp+8h] BYREF

  if ( !a1 || !a2 )
  {
    v4 = WfpReportAppErrorAsNtStatus(a1, (__int64)"FwppDeepCopyToVerIndependent_FWP_CONDITION_VALUE0", 3223453724LL);
    goto LABEL_66;
  }
  v4 = FwppDeepCopyToVerIndependent_FWP_DATA_TYPE();
  if ( !v4 )
  {
    v5 = *(_DWORD *)a1;
    if ( *(int *)a1 > 256 )
    {
      v35 = v5 - 257;
      if ( v35 )
      {
        if ( v35 != 1 )
          return v4;
        v36 = *(_QWORD *)(a1 + 8);
        if ( !v36 )
          return v4;
        v14 = FwppAllocAndDeepCopyToVerIndependent_FWP_RANGE0(v36, a2 + 8);
      }
      else
      {
        v37 = *(_QWORD *)(a1 + 8);
        if ( !v37 )
          return v4;
        v14 = FwppAllocAndDeepCopyToVerIndependent_FWP_V6_ADDR_AND_MASK(v37, a2 + 8);
      }
      goto LABEL_18;
    }
    if ( v5 != 256 )
    {
      if ( v5 <= 10 )
      {
        if ( v5 == 10 )
        {
          v17 = *(_QWORD *)(a1 + 8);
          if ( !v17 )
            return v4;
          v14 = FwppAllocAndDeepCopyToVerIndependent_double(v17, a2 + 8);
        }
        else
        {
          v6 = v5 - 1;
          if ( v6 )
          {
            v7 = v6 - 1;
            if ( v7 )
            {
              v8 = v7 - 1;
              if ( v8 )
              {
                v9 = v8 - 1;
                if ( v9 )
                {
                  v10 = v9 - 1;
                  if ( v10 )
                  {
                    v11 = v10 - 1;
                    if ( v11 )
                    {
                      v12 = v11 - 1;
                      if ( v12 )
                      {
                        v13 = v12 - 1;
                        if ( v13 )
                        {
                          if ( v13 != 1 )
                            return v4;
                          v14 = FwppDeepCopyToVerIndependent_float(a1 + 8, a2 + 8);
                        }
                        else
                        {
                          v15 = *(_QWORD *)(a1 + 8);
                          if ( !v15 )
                            return v4;
                          v14 = FwppAllocAndDeepCopyToVerIndependent_INT64(v15, a2 + 8);
                        }
                      }
                      else
                      {
                        v14 = FwppDeepCopyToVerIndependent_INT32(a1 + 8, a2 + 8);
                      }
                    }
                    else
                    {
                      v14 = FwppDeepCopyToVerIndependent_INT16(a1 + 8, a2 + 8);
                    }
                  }
                  else
                  {
                    v14 = FwppDeepCopyToVerIndependent_INT8(a1 + 8, a2 + 8);
                  }
                }
                else
                {
                  v16 = *(_QWORD *)(a1 + 8);
                  if ( !v16 )
                    return v4;
                  v14 = FwppAllocAndDeepCopyToVerIndependent_UINT64(v16, a2 + 8);
                }
              }
              else
              {
                v14 = FwppDeepCopyToVerIndependent_UINT32(a1 + 8, a2 + 8);
              }
            }
            else
            {
              v14 = FwppDeepCopyToVerIndependent_UINT16(a1 + 8, a2 + 8);
            }
          }
          else
          {
            v14 = FwppDeepCopyToVerIndependent_UINT8(a1 + 8, a2 + 8);
          }
        }
        goto LABEL_18;
      }
      v18 = v5 - 11;
      if ( v18 )
      {
        v19 = v18 - 1;
        if ( !v19 )
          goto LABEL_44;
        v20 = v19 - 1;
        if ( !v20 )
        {
          v29 = *(void **)(a1 + 8);
          if ( !v29 )
            return v4;
          v14 = FwppAllocAndDeepCopyToVerIndependent_SID(v29, (_QWORD *)(a2 + 8));
          goto LABEL_18;
        }
        v21 = v20 - 1;
        if ( !v21 )
        {
LABEL_44:
          v27 = *(_QWORD *)(a1 + 8);
          if ( !v27 )
            return v4;
          v14 = FwppAllocAndDeepCopyToVerIndependent_FWP_BYTE_BLOB(v27, a2 + 8);
          goto LABEL_18;
        }
        v22 = v21 - 1;
        if ( v22 )
        {
          v23 = v22 - 1;
          if ( v23 )
          {
            v24 = v23 - 1;
            if ( v24 )
            {
              if ( v24 != 1 )
                return v4;
              v25 = *(_QWORD *)(a1 + 8);
              if ( !v25 )
                return v4;
              v14 = FwppAllocAndDeepCopyToVerIndependent_FWP_BYTE_ARRAY6(v25, a2 + 8);
            }
            else
            {
              v26 = *(_QWORD *)(a1 + 8);
              if ( !v26 )
                return v4;
              v14 = FwppAllocAndDeepCopyToVerIndependent_WSTR(v26, a2 + 8);
            }
            goto LABEL_18;
          }
          goto LABEL_44;
        }
        v28 = *(_QWORD *)(a1 + 8);
        if ( !v28 )
          return v4;
        v14 = FwppAllocAndDeepCopyToVerIndependent_FWP_TOKEN_INFORMATION(v28, a2 + 8);
      }
      else
      {
        v30 = *(_QWORD *)(a1 + 8);
        if ( !v30 )
          return v4;
        v14 = FwppAllocAndDeepCopyToVerIndependent_FWP_BYTE_ARRAY16(v30, a2 + 8);
      }
LABEL_18:
      v4 = v14;
      if ( !v14 )
        return v4;
      goto LABEL_67;
    }
    v31 = *(_QWORD *)(a1 + 8);
    if ( !v31 )
      return v4;
    v39 = 0;
    if ( a2 != -8 )
    {
      v32 = WfpPoolAllocNonPaged(8, 1886418758, &v39);
      v33 = v39;
      v4 = v32;
      if ( !v32 )
      {
        v34 = v39;
        *v39 = 0;
        v4 = FwppDeepCopyToVerIndependent_FWP_V4_ADDR_AND_MASK(v31, v34);
        if ( !v4 )
        {
          *(_QWORD *)(a2 + 8) = v33;
          return v4;
        }
      }
      FwppDeepFree_IPSEC_TRAFFIC1(v33);
      WfpReportError(v4, (int)"FwppAllocAndDeepCopyToVerIndependent_FWP_V4_ADDR_AND_MASK");
      goto LABEL_67;
    }
    v4 = 0;
LABEL_66:
    if ( !v4 )
      return v4;
  }
LABEL_67:
  FwppDeepFreeContentsOnly_FWP_CONDITION_VALUE0(a2);
  if ( v4 )
    WfpReportError(v4, (int)"FwppDeepCopyToVerIndependent_FWP_CONDITION_VALUE0");
  return v4;
}

```

## disassembly

```asm
0x180061970  mov     [rsp+arg_8], rbx
0x180061975  mov     [rsp+arg_10], rbp
0x18006197a  push    rsi
0x18006197b  push    rdi
0x18006197c  push    r14
0x18006197e  sub     rsp, 30h
0x180061982  mov     rsi, rdx
0x180061985  mov     rdi, rcx
0x180061988  test    rcx, rcx
0x18006198b  jz      loc_180061C65
0x180061991  test    rdx, rdx
0x180061994  jz      loc_180061C65
0x18006199a  call    FwppDeepCopyToVerIndependent_FWP_DATA_TYPE
0x18006199f  mov     rbx, rax
0x1800619a2  test    rax, rax
0x1800619a5  jnz     loc_180061C7F
0x1800619ab  mov     ecx, [rdi]
0x1800619ad  mov     eax, 100h
0x1800619b2  cmp     ecx, eax
0x1800619b4  jg      loc_180061C2A
0x1800619ba  jz      loc_180061BAF
0x1800619c0  cmp     ecx, 0Ah
0x1800619c3  jg      loc_180061AD9
0x1800619c9  jz      loc_180061ABE
0x1800619cf  sub     ecx, 1
0x1800619d2  jz      loc_180061AAC
0x1800619d8  sub     ecx, 1
0x1800619db  jz      loc_180061A9A
0x1800619e1  sub     ecx, 1
0x1800619e4  jz      loc_180061A8B
0x1800619ea  sub     ecx, 1
0x1800619ed  jz      loc_180061A73
0x1800619f3  sub     ecx, 1
0x1800619f6  jz      short loc_180061A64
0x1800619f8  sub     ecx, 1
0x1800619fb  jz      short loc_180061A55
0x1800619fd  sub     ecx, 1
0x180061a00  jz      short loc_180061A46
0x180061a02  sub     ecx, 1
0x180061a05  jz      short loc_180061A2E
0x180061a07  cmp     ecx, 1
0x180061a0a  jnz     loc_180061C9B
0x180061a10  lea     rdx, [rsi+8]
0x180061a14  lea     rcx, [rdi+8]
0x180061a18  call    FwppDeepCopyToVerIndependent_float
0x180061a1d  mov     rbx, rax
0x180061a20  test    rax, rax
0x180061a23  jnz     loc_180061C7F
0x180061a29  jmp     loc_180061C9B
0x180061a2e  mov     rcx, [rdi+8]
0x180061a32  test    rcx, rcx
0x180061a35  jz      loc_180061C9B
0x180061a3b  lea     rdx, [rsi+8]
0x180061a3f  call    FwppAllocAndDeepCopyToVerIndependent_INT64
0x180061a44  jmp     short loc_180061A1D
0x180061a46  lea     rdx, [rsi+8]
0x180061a4a  lea     rcx, [rdi+8]
0x180061a4e  call    FwppDeepCopyToVerIndependent_INT32
0x180061a53  jmp     short loc_180061A1D
0x180061a55  lea     rdx, [rsi+8]
0x180061a59  lea     rcx, [rdi+8]
0x180061a5d  call    FwppDeepCopyToVerIndependent_INT16
0x180061a62  jmp     short loc_180061A1D
0x180061a64  lea     rdx, [rsi+8]
0x180061a68  lea     rcx, [rdi+8]
0x180061a6c  call    FwppDeepCopyToVerIndependent_INT8
0x180061a71  jmp     short loc_180061A1D
0x180061a73  mov     rcx, [rdi+8]
0x180061a77  test    rcx, rcx
0x180061a7a  jz      loc_180061C9B
0x180061a80  lea     rdx, [rsi+8]
0x180061a84  call    FwppAllocAndDeepCopyToVerIndependent_UINT64
0x180061a89  jmp     short loc_180061A1D
0x180061a8b  lea     rdx, [rsi+8]
0x180061a8f  lea     rcx, [rdi+8]
0x180061a93  call    FwppDeepCopyToVerIndependent_UINT32
0x180061a98  jmp     short loc_180061A1D
0x180061a9a  lea     rdx, [rsi+8]
0x180061a9e  lea     rcx, [rdi+8]
0x180061aa2  call    FwppDeepCopyToVerIndependent_UINT16
0x180061aa7  jmp     loc_180061A1D
0x180061aac  lea     rdx, [rsi+8]
0x180061ab0  lea     rcx, [rdi+8]
0x180061ab4  call    FwppDeepCopyToVerIndependent_UINT8
0x180061ab9  jmp     loc_180061A1D
0x180061abe  mov     rcx, [rdi+8]
0x180061ac2  test    rcx, rcx
0x180061ac5  jz      loc_180061C9B
0x180061acb  lea     rdx, [rsi+8]
0x180061acf  call    FwppAllocAndDeepCopyToVerIndependent_double
0x180061ad4  jmp     loc_180061A1D
0x180061ad9  sub     ecx, 0Bh
0x180061adc  jz      loc_180061B94
0x180061ae2  sub     ecx, 1
0x180061ae5  jz      short loc_180061B43
0x180061ae7  sub     ecx, 1
0x180061aea  jz      loc_180061B79
0x180061af0  sub     ecx, 1
0x180061af3  jz      short loc_180061B43
0x180061af5  sub     ecx, 1
0x180061af8  jz      short loc_180061B5E
0x180061afa  sub     ecx, 1
0x180061afd  jz      short loc_180061B43
0x180061aff  sub     ecx, 1
0x180061b02  jz      short loc_180061B28
0x180061b04  cmp     ecx, 1
0x180061b07  jnz     loc_180061C9B
0x180061b0d  mov     rcx, [rdi+8]
0x180061b11  test    rcx, rcx
0x180061b14  jz      loc_180061C9B
0x180061b1a  lea     rdx, [rsi+8]
0x180061b1e  call    FwppAllocAndDeepCopyToVerIndependent_FWP_BYTE_ARRAY6
0x180061b23  jmp     loc_180061A1D
0x180061b28  mov     rcx, [rdi+8]
0x180061b2c  test    rcx, rcx
0x180061b2f  jz      loc_180061C9B
0x180061b35  lea     rdx, [rsi+8]
0x180061b39  call    FwppAllocAndDeepCopyToVerIndependent_WSTR
0x180061b3e  jmp     loc_180061A1D
0x180061b43  mov     rcx, [rdi+8]
0x180061b47  test    rcx, rcx
0x180061b4a  jz      loc_180061C9B
0x180061b50  lea     rdx, [rsi+8]
0x180061b54  call    FwppAllocAndDeepCopyToVerIndependent_FWP_BYTE_BLOB
0x180061b59  jmp     loc_180061A1D
0x180061b5e  mov     rcx, [rdi+8]
0x180061b62  test    rcx, rcx
0x180061b65  jz      loc_180061C9B
0x180061b6b  lea     rdx, [rsi+8]
0x180061b6f  call    FwppAllocAndDeepCopyToVerIndependent_FWP_TOKEN_INFORMATION
0x180061b74  jmp     loc_180061A1D
0x180061b79  mov     rcx, [rdi+8]; SourceSid
0x180061b7d  test    rcx, rcx
0x180061b80  jz      loc_180061C9B
0x180061b86  lea     rdx, [rsi+8]
0x180061b8a  call    FwppAllocAndDeepCopyToVerIndependent_SID
0x180061b8f  jmp     loc_180061A1D
0x180061b94  mov     rcx, [rdi+8]
0x180061b98  test    rcx, rcx
0x180061b9b  jz      loc_180061C9B
0x180061ba1  lea     rdx, [rsi+8]
0x180061ba5  call    FwppAllocAndDeepCopyToVerIndependent_FWP_BYTE_ARRAY16
0x180061baa  jmp     loc_180061A1D
0x180061baf  mov     rbp, [rdi+8]
0x180061bb3  test    rbp, rbp
0x180061bb6  jz      loc_180061C9B
0x180061bbc  lea     r14, [rsi+8]
0x180061bc0  mov     [rsp+48h+arg_0], 0
0x180061bc9  test    r14, r14
0x180061bcc  jz      short loc_180061C26
0x180061bce  lea     r8, [rsp+48h+arg_0]
0x180061bd3  mov     edx, 70707746h
0x180061bd8  mov     ecx, 8
0x180061bdd  call    WfpPoolAllocNonPaged
0x180061be2  mov     rdi, [rsp+48h+arg_0]
0x180061be7  mov     rbx, rax
0x180061bea  test    rax, rax
0x180061bed  jnz     short loc_180061C0D
0x180061bef  mov     rdx, rdi
0x180061bf2  mov     [rdi], rax
0x180061bf5  mov     rcx, rbp
0x180061bf8  call    FwppDeepCopyToVerIndependent_FWP_V4_ADDR_AND_MASK
0x180061bfd  mov     rbx, rax
0x180061c00  test    rax, rax
0x180061c03  jnz     short loc_180061C0D
0x180061c05  mov     [r14], rdi
0x180061c08  jmp     loc_180061C9B
0x180061c0d  mov     rcx, rdi
0x180061c10  call    FwppDeepFree_IPSEC_TRAFFIC1
0x180061c15  lea     rdx, aFwppallocandde_14; "FwppAllocAndDeepCopyToVerIndependent_FW"...
0x180061c1c  mov     rcx, rbx
0x180061c1f  call    WfpReportError
0x180061c24  jmp     short loc_180061C7F
0x180061c26  xor     ebx, ebx
0x180061c28  jmp     short loc_180061C7A
0x180061c2a  sub     ecx, 101h
0x180061c30  jz      short loc_180061C4E
0x180061c32  cmp     ecx, 1
0x180061c35  jnz     short loc_180061C9B
0x180061c37  mov     rcx, [rdi+8]
0x180061c3b  test    rcx, rcx
0x180061c3e  jz      short loc_180061C9B
0x180061c40  lea     rdx, [rsi+8]
0x180061c44  call    FwppAllocAndDeepCopyToVerIndependent_FWP_RANGE0
0x180061c49  jmp     loc_180061A1D
0x180061c4e  mov     rcx, [rdi+8]
0x180061c52  test    rcx, rcx
0x180061c55  jz      short loc_180061C9B
0x180061c57  lea     rdx, [rsi+8]
0x180061c5b  call    FwppAllocAndDeepCopyToVerIndependent_FWP_V6_ADDR_AND_MASK
0x180061c60  jmp     loc_180061A1D
0x180061c65  mov     r8d, 0C022001Ch
0x180061c6b  lea     rdx, aFwppdeepcopyto_7; "FwppDeepCopyToVerIndependent_FWP_CONDIT"...
0x180061c72  call    WfpReportAppErrorAsNtStatus
0x180061c77  mov     rbx, rax
0x180061c7a  test    rbx, rbx
0x180061c7d  jz      short loc_180061C9B
0x180061c7f  mov     rcx, rsi
0x180061c82  call    FwppDeepFreeContentsOnly_FWP_CONDITION_VALUE0
0x180061c87  test    rbx, rbx
0x180061c8a  jz      short loc_180061C9B
0x180061c8c  lea     rdx, aFwppdeepcopyto_7; "FwppDeepCopyToVerIndependent_FWP_CONDIT"...
0x180061c93  mov     rcx, rbx
0x180061c96  call    WfpReportError
0x180061c9b  mov     rbp, [rsp+48h+arg_10]
0x180061ca0  mov     rax, rbx
0x180061ca3  mov     rbx, [rsp+48h+arg_8]
0x180061ca8  add     rsp, 30h
0x180061cac  pop     r14
0x180061cae  pop     rdi
0x180061caf  pop     rsi
0x180061cb0  retn
```
