# FwppDeepCopyToVerIndependent_FWP_VALUE0

- ea: `0x180061fbc`
- end: `0x18006221d`
- name: `FwppDeepCopyToVerIndependent_FWP_VALUE0`
- size: `609`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `authz_impersonation`

## callers

- `0x1800614bc`
- `0x180061d60`

## callees

- `0x1800050cc`
- `0x18000c9b4`
- `0x180012a98`
- `0x1800130d8`
- `0x1800131b0`
- `0x18005a8fc`
- `0x18005a984`
- `0x18005aa98`
- `0x18005ad54`
- `0x18005b474`
- `0x18005b4f8`
- `0x180061cb8`
- `0x180061fbc`
- `0x180062bf8`
- `0x180062c4c`
- `0x180062cf4`
- `0x180064210`
- `0x180064264`
- `0x18006430c`
- `0x180064408`
- `0x1800648d4`

## string_xrefs

- `0x180062064`: `FwppDeepCopyToVerIndependent_FWP_VALUE0`
- `0x18006220c`: `FwppDeepCopyToVerIndependent_FWP_VALUE0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyToVerIndependent_FWP_VALUE0(__int64 a1, __int64 a2)
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
    v14 = WfpReportAppErrorAsNtStatus(a1, (__int64)"FwppDeepCopyToVerIndependent_FWP_VALUE0", 3223453724LL);
    goto LABEL_16;
  }
  v4 = FwppDeepCopyToVerIndependent_FWP_DATA_TYPE();
  if ( !v4 )
  {
    v5 = *(_DWORD *)a1;
    if ( *(int *)a1 <= 10 )
    {
      if ( v5 == 10 )
      {
        v18 = *(_QWORD *)(a1 + 8);
        if ( !v18 )
          return v4;
        v14 = FwppAllocAndDeepCopyToVerIndependent_double(v18, a2 + 8);
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
                        v16 = *(_QWORD *)(a1 + 8);
                        if ( !v16 )
                          return v4;
                        v14 = FwppAllocAndDeepCopyToVerIndependent_INT64(v16, a2 + 8);
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
                v17 = *(_QWORD *)(a1 + 8);
                if ( !v17 )
                  return v4;
                v14 = FwppAllocAndDeepCopyToVerIndependent_UINT64(v17, a2 + 8);
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
      goto LABEL_16;
    }
    v19 = v5 - 11;
    if ( !v19 )
    {
      v31 = *(_QWORD *)(a1 + 8);
      if ( !v31 )
        return v4;
      v14 = FwppAllocAndDeepCopyToVerIndependent_FWP_BYTE_ARRAY16(v31, a2 + 8);
      goto LABEL_16;
    }
    v20 = v19 - 1;
    if ( v20 )
    {
      v21 = v20 - 1;
      if ( !v21 )
      {
        v30 = *(void **)(a1 + 8);
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
          v29 = *(_QWORD *)(a1 + 8);
          if ( !v29 )
            return v4;
          v14 = FwppAllocAndDeepCopyToVerIndependent_FWP_TOKEN_INFORMATION(v29, a2 + 8);
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
            v26 = *(_QWORD *)(a1 + 8);
            if ( !v26 )
              return v4;
            v14 = FwppAllocAndDeepCopyToVerIndependent_FWP_BYTE_ARRAY6(v26, a2 + 8);
          }
          else
          {
            v27 = *(_QWORD *)(a1 + 8);
            if ( !v27 )
              return v4;
            v14 = FwppAllocAndDeepCopyToVerIndependent_WSTR(v27, a2 + 8);
          }
          goto LABEL_16;
        }
      }
    }
    v28 = *(_QWORD *)(a1 + 8);
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
    WfpReportError(v4, (int)"FwppDeepCopyToVerIndependent_FWP_VALUE0");
  return v4;
}

```

## disassembly

```asm
0x180061fbc  mov     [rsp+arg_0], rbx
0x180061fc1  mov     [rsp+arg_8], rsi
0x180061fc6  push    rdi
0x180061fc7  sub     rsp, 30h
0x180061fcb  mov     rsi, rdx
0x180061fce  mov     rdi, rcx
0x180061fd1  test    rcx, rcx
0x180061fd4  jz      loc_180062206
0x180061fda  test    rdx, rdx
0x180061fdd  jz      loc_180062206
0x180061fe3  call    FwppDeepCopyToVerIndependent_FWP_DATA_TYPE
0x180061fe8  mov     rbx, rax
0x180061feb  test    rax, rax
0x180061fee  jnz     short loc_180062057
0x180061ff0  mov     edx, [rdi]
0x180061ff2  cmp     edx, 0Ah
0x180061ff5  jg      loc_180062130
0x180061ffb  jz      loc_180062115
0x180062001  sub     edx, 1
0x180062004  jz      loc_180062103
0x18006200a  sub     edx, 1
0x18006200d  jz      loc_1800620F1
0x180062013  sub     edx, 1
0x180062016  jz      loc_1800620DF
0x18006201c  sub     edx, 1
0x18006201f  jz      loc_1800620C8
0x180062025  sub     edx, 1
0x180062028  jz      loc_1800620B9
0x18006202e  sub     edx, 1
0x180062031  jz      short loc_1800620AA
0x180062033  sub     edx, 1
0x180062036  jz      short loc_18006209B
0x180062038  sub     edx, 1
0x18006203b  jz      short loc_180062087
0x18006203d  cmp     edx, 1
0x180062040  jnz     short loc_180062073
0x180062042  lea     rdx, [rsi+8]
0x180062046  lea     rcx, [rdi+8]
0x18006204a  call    FwppDeepCopyToVerIndependent_float
0x18006204f  mov     rbx, rax
0x180062052  test    rax, rax
0x180062055  jz      short loc_180062073
0x180062057  mov     rcx, rsi
0x18006205a  call    FwppDeepFreeContentsOnly_FWP_VALUE0
0x18006205f  test    rbx, rbx
0x180062062  jz      short loc_180062073
0x180062064  lea     rdx, aFwppdeepcopyto_110; "FwppDeepCopyToVerIndependent_FWP_VALUE0"
0x18006206b  mov     rcx, rbx
0x18006206e  call    WfpReportError
0x180062073  mov     rsi, [rsp+38h+arg_8]
0x180062078  mov     rax, rbx
0x18006207b  mov     rbx, [rsp+38h+arg_0]
0x180062080  add     rsp, 30h
0x180062084  pop     rdi
0x180062085  retn
0x180062087  mov     rcx, [rdi+8]
0x18006208b  test    rcx, rcx
0x18006208e  jz      short loc_180062073
0x180062090  lea     rdx, [rsi+8]
0x180062094  call    FwppAllocAndDeepCopyToVerIndependent_INT64
0x180062099  jmp     short loc_18006204F
0x18006209b  lea     rdx, [rsi+8]
0x18006209f  lea     rcx, [rdi+8]
0x1800620a3  call    FwppDeepCopyToVerIndependent_INT32
0x1800620a8  jmp     short loc_18006204F
0x1800620aa  lea     rdx, [rsi+8]
0x1800620ae  lea     rcx, [rdi+8]
0x1800620b2  call    FwppDeepCopyToVerIndependent_INT16
0x1800620b7  jmp     short loc_18006204F
0x1800620b9  lea     rdx, [rsi+8]
0x1800620bd  lea     rcx, [rdi+8]
0x1800620c1  call    FwppDeepCopyToVerIndependent_INT8
0x1800620c6  jmp     short loc_18006204F
0x1800620c8  mov     rcx, [rdi+8]
0x1800620cc  test    rcx, rcx
0x1800620cf  jz      short loc_180062073
0x1800620d1  lea     rdx, [rsi+8]
0x1800620d5  call    FwppAllocAndDeepCopyToVerIndependent_UINT64
0x1800620da  jmp     loc_18006204F
0x1800620df  lea     rdx, [rsi+8]
0x1800620e3  lea     rcx, [rdi+8]
0x1800620e7  call    FwppDeepCopyToVerIndependent_UINT32
0x1800620ec  jmp     loc_18006204F
0x1800620f1  lea     rdx, [rsi+8]
0x1800620f5  lea     rcx, [rdi+8]
0x1800620f9  call    FwppDeepCopyToVerIndependent_UINT16
0x1800620fe  jmp     loc_18006204F
0x180062103  lea     rdx, [rsi+8]
0x180062107  lea     rcx, [rdi+8]
0x18006210b  call    FwppDeepCopyToVerIndependent_UINT8
0x180062110  jmp     loc_18006204F
0x180062115  mov     rcx, [rdi+8]
0x180062119  test    rcx, rcx
0x18006211c  jz      loc_180062073
0x180062122  lea     rdx, [rsi+8]
0x180062126  call    FwppAllocAndDeepCopyToVerIndependent_double
0x18006212b  jmp     loc_18006204F
0x180062130  sub     edx, 0Bh
0x180062133  jz      loc_1800621EB
0x180062139  sub     edx, 1
0x18006213c  jz      short loc_18006219A
0x18006213e  sub     edx, 1
0x180062141  jz      loc_1800621D0
0x180062147  sub     edx, 1
0x18006214a  jz      short loc_18006219A
0x18006214c  sub     edx, 1
0x18006214f  jz      short loc_1800621B5
0x180062151  sub     edx, 1
0x180062154  jz      short loc_18006219A
0x180062156  sub     edx, 1
0x180062159  jz      short loc_18006217F
0x18006215b  cmp     edx, 1
0x18006215e  jnz     loc_180062073
0x180062164  mov     rcx, [rdi+8]
0x180062168  test    rcx, rcx
0x18006216b  jz      loc_180062073
0x180062171  lea     rdx, [rsi+8]
0x180062175  call    FwppAllocAndDeepCopyToVerIndependent_FWP_BYTE_ARRAY6
0x18006217a  jmp     loc_18006204F
0x18006217f  mov     rcx, [rdi+8]
0x180062183  test    rcx, rcx
0x180062186  jz      loc_180062073
0x18006218c  lea     rdx, [rsi+8]
0x180062190  call    FwppAllocAndDeepCopyToVerIndependent_WSTR
0x180062195  jmp     loc_18006204F
0x18006219a  mov     rcx, [rdi+8]
0x18006219e  test    rcx, rcx
0x1800621a1  jz      loc_180062073
0x1800621a7  lea     rdx, [rsi+8]
0x1800621ab  call    FwppAllocAndDeepCopyToVerIndependent_FWP_BYTE_BLOB
0x1800621b0  jmp     loc_18006204F
0x1800621b5  mov     rcx, [rdi+8]
0x1800621b9  test    rcx, rcx
0x1800621bc  jz      loc_180062073
0x1800621c2  lea     rdx, [rsi+8]
0x1800621c6  call    FwppAllocAndDeepCopyToVerIndependent_FWP_TOKEN_INFORMATION
0x1800621cb  jmp     loc_18006204F
0x1800621d0  mov     rcx, [rdi+8]; SourceSid
0x1800621d4  test    rcx, rcx
0x1800621d7  jz      loc_180062073
0x1800621dd  lea     rdx, [rsi+8]
0x1800621e1  call    FwppAllocAndDeepCopyToVerIndependent_SID
0x1800621e6  jmp     loc_18006204F
0x1800621eb  mov     rcx, [rdi+8]
0x1800621ef  test    rcx, rcx
0x1800621f2  jz      loc_180062073
0x1800621f8  lea     rdx, [rsi+8]
0x1800621fc  call    FwppAllocAndDeepCopyToVerIndependent_FWP_BYTE_ARRAY16
0x180062201  jmp     loc_18006204F
0x180062206  mov     r8d, 0C022001Ch
0x18006220c  lea     rdx, aFwppdeepcopyto_110; "FwppDeepCopyToVerIndependent_FWP_VALUE0"
0x180062213  call    WfpReportAppErrorAsNtStatus
0x180062218  jmp     loc_18006204F
```
