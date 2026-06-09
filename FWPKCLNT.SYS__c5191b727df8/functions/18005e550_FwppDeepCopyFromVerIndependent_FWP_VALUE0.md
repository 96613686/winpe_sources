# FwppDeepCopyFromVerIndependent_FWP_VALUE0

- ea: `0x18005e550`
- end: `0x18005e7b1`
- name: `FwppDeepCopyFromVerIndependent_FWP_VALUE0`
- size: `609`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `authz_impersonation`

## callers

- `0x18005dc70`
- `0x18005de0c`

## callees

- `0x1800050cc`
- `0x18000c9b4`
- `0x180012a98`
- `0x1800130d8`
- `0x1800131b0`
- `0x1800599c8`
- `0x180059a50`
- `0x180059ad8`
- `0x180059eac`
- `0x18005a6dc`
- `0x18005a760`
- `0x18005e39c`
- `0x18005e550`
- `0x18005fcc0`
- `0x18005fd14`
- `0x18005fdbc`
- `0x180061270`
- `0x1800612c4`
- `0x18006136c`
- `0x180061468`
- `0x1800648d4`

## string_xrefs

- `0x18005e5f8`: `FwppDeepCopyFromVerIndependent_FWP_VALUE0`
- `0x18005e7a0`: `FwppDeepCopyFromVerIndependent_FWP_VALUE0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyFromVerIndependent_FWP_VALUE0(int *a1, __int64 a2)
{
  __int64 v4; // rbx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  int v13; // edx
  __int64 v14; // rax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19; // edx
  int v20; // edx
  int v21; // edx
  int v22; // edx
  int v23; // edx
  int v24; // edx
  int v25; // edx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  void *v30; // rcx
  __int64 v31; // rcx

  if ( !a1 || !a2 )
  {
    v14 = WfpReportAppErrorAsNtStatus((__int64)a1, (__int64)"FwppDeepCopyFromVerIndependent_FWP_VALUE0", 3223453724LL);
    goto LABEL_16;
  }
  v4 = FwppDeepCopyFromVerIndependent_FWP_DATA_TYPE();
  if ( !v4 )
  {
    v5 = *a1;
    if ( *a1 <= 10 )
    {
      if ( v5 == 10 )
      {
        v18 = *((_QWORD *)a1 + 1);
        if ( !v18 )
          return v4;
        v14 = FwppAllocAndDeepCopyFromVerIndependent_double(v18, a2 + 8);
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
                        v14 = FwppDeepCopyFromVerIndependent_float(a1 + 2, a2 + 8);
                      }
                      else
                      {
                        v16 = *((_QWORD *)a1 + 1);
                        if ( !v16 )
                          return v4;
                        v14 = FwppAllocAndDeepCopyFromVerIndependent_INT64(v16, a2 + 8);
                      }
                    }
                    else
                    {
                      v14 = FwppDeepCopyFromVerIndependent_INT32(a1 + 2, a2 + 8);
                    }
                  }
                  else
                  {
                    v14 = FwppDeepCopyFromVerIndependent_INT16(a1 + 2, a2 + 8);
                  }
                }
                else
                {
                  v14 = FwppDeepCopyFromVerIndependent_INT8(a1 + 2, a2 + 8);
                }
              }
              else
              {
                v17 = *((_QWORD *)a1 + 1);
                if ( !v17 )
                  return v4;
                v14 = FwppAllocAndDeepCopyFromVerIndependent_UINT64(v17, a2 + 8);
              }
            }
            else
            {
              v14 = FwppDeepCopyFromVerIndependent_UINT32(a1 + 2, (_DWORD *)(a2 + 8));
            }
          }
          else
          {
            v14 = FwppDeepCopyFromVerIndependent_UINT16(a1 + 2, a2 + 8);
          }
        }
        else
        {
          v14 = FwppDeepCopyFromVerIndependent_UINT8(a1 + 2, a2 + 8);
        }
      }
      goto LABEL_16;
    }
    v19 = v5 - 11;
    if ( !v19 )
    {
      v31 = *((_QWORD *)a1 + 1);
      if ( !v31 )
        return v4;
      v14 = FwppAllocAndDeepCopyFromVerIndependent_FWP_BYTE_ARRAY16(v31, a2 + 8);
      goto LABEL_16;
    }
    v20 = v19 - 1;
    if ( v20 )
    {
      v21 = v20 - 1;
      if ( !v21 )
      {
        v30 = (void *)*((_QWORD *)a1 + 1);
        if ( !v30 )
          return v4;
        v14 = FwppAllocAndDeepCopyToVerIndependent_SID(v30, (_QWORD *)(a2 + 8));
        goto LABEL_16;
      }
      v22 = v21 - 1;
      if ( v22 )
      {
        v23 = v22 - 1;
        if ( !v23 )
        {
          v29 = *((_QWORD *)a1 + 1);
          if ( !v29 )
            return v4;
          v14 = FwppAllocAndDeepCopyFromVerIndependent_FWP_TOKEN_INFORMATION(v29, a2 + 8);
          goto LABEL_16;
        }
        v24 = v23 - 1;
        if ( v24 )
        {
          v25 = v24 - 1;
          if ( v25 )
          {
            if ( v25 != 1 )
              return v4;
            v26 = *((_QWORD *)a1 + 1);
            if ( !v26 )
              return v4;
            v14 = FwppAllocAndDeepCopyFromVerIndependent_FWP_BYTE_ARRAY6(v26, a2 + 8);
          }
          else
          {
            v27 = *((_QWORD *)a1 + 1);
            if ( !v27 )
              return v4;
            v14 = FwppAllocAndDeepCopyToVerIndependent_WSTR(v27, a2 + 8);
          }
          goto LABEL_16;
        }
      }
    }
    v28 = *((_QWORD *)a1 + 1);
    if ( !v28 )
      return v4;
    v14 = FwppAllocAndDeepCopyToVerIndependent_FWP_BYTE_BLOB(v28, a2 + 8);
LABEL_16:
    v4 = v14;
    if ( !v14 )
      return v4;
  }
  FwppDeepFreeContentsOnly_FWP_VALUE0(a2);
  if ( v4 )
    WfpReportError(v4, (int)"FwppDeepCopyFromVerIndependent_FWP_VALUE0");
  return v4;
}

```

## disassembly

```asm
0x18005e550  mov     [rsp+arg_0], rbx
0x18005e555  mov     [rsp+arg_8], rsi
0x18005e55a  push    rdi
0x18005e55b  sub     rsp, 30h
0x18005e55f  mov     rsi, rdx
0x18005e562  mov     rdi, rcx
0x18005e565  test    rcx, rcx
0x18005e568  jz      loc_18005E79A
0x18005e56e  test    rdx, rdx
0x18005e571  jz      loc_18005E79A
0x18005e577  call    FwppDeepCopyFromVerIndependent_FWP_DATA_TYPE
0x18005e57c  mov     rbx, rax
0x18005e57f  test    rax, rax
0x18005e582  jnz     short loc_18005E5EB
0x18005e584  mov     edx, [rdi]
0x18005e586  cmp     edx, 0Ah
0x18005e589  jg      loc_18005E6C4
0x18005e58f  jz      loc_18005E6A9
0x18005e595  sub     edx, 1
0x18005e598  jz      loc_18005E697
0x18005e59e  sub     edx, 1
0x18005e5a1  jz      loc_18005E685
0x18005e5a7  sub     edx, 1
0x18005e5aa  jz      loc_18005E673
0x18005e5b0  sub     edx, 1
0x18005e5b3  jz      loc_18005E65C
0x18005e5b9  sub     edx, 1
0x18005e5bc  jz      loc_18005E64D
0x18005e5c2  sub     edx, 1
0x18005e5c5  jz      short loc_18005E63E
0x18005e5c7  sub     edx, 1
0x18005e5ca  jz      short loc_18005E62F
0x18005e5cc  sub     edx, 1
0x18005e5cf  jz      short loc_18005E61B
0x18005e5d1  cmp     edx, 1
0x18005e5d4  jnz     short loc_18005E607
0x18005e5d6  lea     rdx, [rsi+8]
0x18005e5da  lea     rcx, [rdi+8]
0x18005e5de  call    FwppDeepCopyFromVerIndependent_float
0x18005e5e3  mov     rbx, rax
0x18005e5e6  test    rax, rax
0x18005e5e9  jz      short loc_18005E607
0x18005e5eb  mov     rcx, rsi
0x18005e5ee  call    FwppDeepFreeContentsOnly_FWP_VALUE0
0x18005e5f3  test    rbx, rbx
0x18005e5f6  jz      short loc_18005E607
0x18005e5f8  lea     rdx, aFwppdeepcopyfr_86; "FwppDeepCopyFromVerIndependent_FWP_VALU"...
0x18005e5ff  mov     rcx, rbx
0x18005e602  call    WfpReportError
0x18005e607  mov     rsi, [rsp+38h+arg_8]
0x18005e60c  mov     rax, rbx
0x18005e60f  mov     rbx, [rsp+38h+arg_0]
0x18005e614  add     rsp, 30h
0x18005e618  pop     rdi
0x18005e619  retn
0x18005e61b  mov     rcx, [rdi+8]
0x18005e61f  test    rcx, rcx
0x18005e622  jz      short loc_18005E607
0x18005e624  lea     rdx, [rsi+8]
0x18005e628  call    FwppAllocAndDeepCopyFromVerIndependent_INT64
0x18005e62d  jmp     short loc_18005E5E3
0x18005e62f  lea     rdx, [rsi+8]
0x18005e633  lea     rcx, [rdi+8]
0x18005e637  call    FwppDeepCopyFromVerIndependent_INT32
0x18005e63c  jmp     short loc_18005E5E3
0x18005e63e  lea     rdx, [rsi+8]
0x18005e642  lea     rcx, [rdi+8]
0x18005e646  call    FwppDeepCopyFromVerIndependent_INT16
0x18005e64b  jmp     short loc_18005E5E3
0x18005e64d  lea     rdx, [rsi+8]
0x18005e651  lea     rcx, [rdi+8]
0x18005e655  call    FwppDeepCopyFromVerIndependent_INT8
0x18005e65a  jmp     short loc_18005E5E3
0x18005e65c  mov     rcx, [rdi+8]
0x18005e660  test    rcx, rcx
0x18005e663  jz      short loc_18005E607
0x18005e665  lea     rdx, [rsi+8]
0x18005e669  call    FwppAllocAndDeepCopyFromVerIndependent_UINT64
0x18005e66e  jmp     loc_18005E5E3
0x18005e673  lea     rdx, [rsi+8]
0x18005e677  lea     rcx, [rdi+8]
0x18005e67b  call    FwppDeepCopyFromVerIndependent_UINT32
0x18005e680  jmp     loc_18005E5E3
0x18005e685  lea     rdx, [rsi+8]
0x18005e689  lea     rcx, [rdi+8]
0x18005e68d  call    FwppDeepCopyFromVerIndependent_UINT16
0x18005e692  jmp     loc_18005E5E3
0x18005e697  lea     rdx, [rsi+8]
0x18005e69b  lea     rcx, [rdi+8]
0x18005e69f  call    FwppDeepCopyFromVerIndependent_UINT8
0x18005e6a4  jmp     loc_18005E5E3
0x18005e6a9  mov     rcx, [rdi+8]
0x18005e6ad  test    rcx, rcx
0x18005e6b0  jz      loc_18005E607
0x18005e6b6  lea     rdx, [rsi+8]
0x18005e6ba  call    FwppAllocAndDeepCopyFromVerIndependent_double
0x18005e6bf  jmp     loc_18005E5E3
0x18005e6c4  sub     edx, 0Bh
0x18005e6c7  jz      loc_18005E77F
0x18005e6cd  sub     edx, 1
0x18005e6d0  jz      short loc_18005E72E
0x18005e6d2  sub     edx, 1
0x18005e6d5  jz      loc_18005E764
0x18005e6db  sub     edx, 1
0x18005e6de  jz      short loc_18005E72E
0x18005e6e0  sub     edx, 1
0x18005e6e3  jz      short loc_18005E749
0x18005e6e5  sub     edx, 1
0x18005e6e8  jz      short loc_18005E72E
0x18005e6ea  sub     edx, 1
0x18005e6ed  jz      short loc_18005E713
0x18005e6ef  cmp     edx, 1
0x18005e6f2  jnz     loc_18005E607
0x18005e6f8  mov     rcx, [rdi+8]
0x18005e6fc  test    rcx, rcx
0x18005e6ff  jz      loc_18005E607
0x18005e705  lea     rdx, [rsi+8]
0x18005e709  call    FwppAllocAndDeepCopyFromVerIndependent_FWP_BYTE_ARRAY6
0x18005e70e  jmp     loc_18005E5E3
0x18005e713  mov     rcx, [rdi+8]
0x18005e717  test    rcx, rcx
0x18005e71a  jz      loc_18005E607
0x18005e720  lea     rdx, [rsi+8]
0x18005e724  call    FwppAllocAndDeepCopyToVerIndependent_WSTR
0x18005e729  jmp     loc_18005E5E3
0x18005e72e  mov     rcx, [rdi+8]
0x18005e732  test    rcx, rcx
0x18005e735  jz      loc_18005E607
0x18005e73b  lea     rdx, [rsi+8]
0x18005e73f  call    FwppAllocAndDeepCopyToVerIndependent_FWP_BYTE_BLOB
0x18005e744  jmp     loc_18005E5E3
0x18005e749  mov     rcx, [rdi+8]
0x18005e74d  test    rcx, rcx
0x18005e750  jz      loc_18005E607
0x18005e756  lea     rdx, [rsi+8]
0x18005e75a  call    FwppAllocAndDeepCopyFromVerIndependent_FWP_TOKEN_INFORMATION
0x18005e75f  jmp     loc_18005E5E3
0x18005e764  mov     rcx, [rdi+8]; SourceSid
0x18005e768  test    rcx, rcx
0x18005e76b  jz      loc_18005E607
0x18005e771  lea     rdx, [rsi+8]
0x18005e775  call    FwppAllocAndDeepCopyToVerIndependent_SID
0x18005e77a  jmp     loc_18005E5E3
0x18005e77f  mov     rcx, [rdi+8]
0x18005e783  test    rcx, rcx
0x18005e786  jz      loc_18005E607
0x18005e78c  lea     rdx, [rsi+8]
0x18005e790  call    FwppAllocAndDeepCopyFromVerIndependent_FWP_BYTE_ARRAY16
0x18005e795  jmp     loc_18005E5E3
0x18005e79a  mov     r8d, 0C022001Ch
0x18005e7a0  lea     rdx, aFwppdeepcopyfr_86; "FwppDeepCopyFromVerIndependent_FWP_VALU"...
0x18005e7a7  call    WfpReportAppErrorAsNtStatus
0x18005e7ac  jmp     loc_18005E5E3
```
