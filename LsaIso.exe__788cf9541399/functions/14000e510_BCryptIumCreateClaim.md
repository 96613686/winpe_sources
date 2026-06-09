# BCryptIumCreateClaim

- ea: `0x14000e510`
- end: `0x14000e823`
- name: `BCryptIumCreateClaim`
- size: `787`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, unsigned __int64, int, struct _BCryptrBufferDesc *, unsigned __int8 *, unsigned int, unsigned int *, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140002080`
- `0x1400021f0`
- `0x1400083a8`
- `0x140008e2c`
- `0x14000e510`
- `0x14001193c`
- `0x140011964`
- `0x140012ee8`
- `0x140037b10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000e7b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000e7c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000e7b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000e7c4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000e62f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000e6a1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000e62f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000e6a1`

## string_xrefs

- `0x14000e5d0`: `onecore\ds\security\cryptoapi\ncrypt\ium\trustlet\bcryptiumrpcimpl.cxx`
- `0x14000e604`: `onecore\ds\security\cryptoapi\ncrypt\ium\trustlet\bcryptiumrpcimpl.cxx`
- `0x14000e7a5`: `onecore\ds\security\cryptoapi\ncrypt\ium\trustlet\bcryptiumrpcimpl.cxx`

## pseudocode

```c
__int64 __fastcall BCryptIumCreateClaim(
        __int64 a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        int a4,
        struct _BCryptrBufferDesc *a5,
        unsigned __int8 *a6,
        unsigned int a7,
        unsigned int *a8,
        int a9)
{
  int Context; // eax
  unsigned int v14; // ebx
  PVOID *v15; // rcx
  RTL_SRWLOCK *v16; // rax
  RTL_SRWLOCK *v17; // rsi
  RTL_SRWLOCK *v18; // rdi
  __int64 v19; // r8
  int v20; // r12d
  int v21; // ebp
  __int64 v22; // r8
  __int64 v23; // rcx
  RTL_SRWLOCK *v24; // rax
  unsigned int ClaimKeyFlags; // eax
  unsigned int v27; // [rsp+50h] [rbp-58h] BYREF
  struct BCRYPTIUM_CONTEXT *v28; // [rsp+58h] [rbp-50h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 295, &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids);
  v28 = 0;
  Context = BCryptIumContextManagerGetContext(a1, &v28);
  v14 = Context;
  if ( Context >= 0 )
  {
    v16 = (RTL_SRWLOCK *)LookupBCryptIsoObject(v28, a2, 0x42494F4Bu);
    v17 = v16;
    if ( !v16 )
    {
      v14 = -1073741816;
      VBS_ATTEST_TRACE_ERROR_IN(
        3221225480LL,
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\trustlet\\bcryptiumrpcimpl.cxx",
        3311);
      goto LABEL_38;
    }
    v18 = 0;
    if ( !a8 )
    {
      v19 = 3318;
LABEL_12:
      v14 = -1073741811;
      VBS_ATTEST_TRACE_ERROR_IN(
        3221225485LL,
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\trustlet\\bcryptiumrpcimpl.cxx",
        v19);
LABEL_36:
      BCryptIumDereferenceObject(v17);
      if ( v18 )
        BCryptIumDereferenceObject(v18);
      goto LABEL_38;
    }
    if ( a9 )
    {
      v19 = 3328;
      goto LABEL_12;
    }
    v20 = 0;
    AcquireSRWLockShared(v16 + 5);
    v21 = a4 - 5;
    if ( v21 )
    {
      if ( v21 != 1 )
      {
        v14 = -1073741637;
        v22 = 3431;
        v23 = 3221225659LL;
LABEL_33:
        VBS_ATTEST_TRACE_ERROR_IN(
          v23,
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\trustlet\\bcryptiumrpcimpl.cxx",
          v22);
LABEL_34:
        ReleaseSRWLockShared(v17 + 5);
        if ( v20 )
          ReleaseSRWLockShared(v18 + 5);
        goto LABEL_36;
      }
      v27 = 0;
      if ( !a3 )
      {
        v23 = 3221225480LL;
        v22 = 3385;
        v14 = -1073741816;
        goto LABEL_33;
      }
      v24 = (RTL_SRWLOCK *)LookupBCryptIsoObject(v28, a3, 0x42494F4Bu);
      v18 = v24;
      if ( !v24 )
      {
        v23 = 3221225480LL;
        v22 = 3393;
        v14 = -1073741816;
        goto LABEL_33;
      }
      AcquireSRWLockShared(v24 + 5);
      v20 = 1;
      ClaimKeyFlags = BCryptIumRpcGetClaimKeyFlags(v17, &v27);
      v14 = ClaimKeyFlags;
      if ( ClaimKeyFlags )
      {
        v22 = 3408;
      }
      else
      {
        ClaimKeyFlags = CreateVsmKeyAttestationClaim(
                          v17[1].Ptr,
                          v18[1].Ptr,
                          6u,
                          a5,
                          a6,
                          a7,
                          a8,
                          v27,
                          (unsigned int)v18[2].Ptr);
        v14 = ClaimKeyFlags;
        if ( !ClaimKeyFlags )
          goto LABEL_34;
        v22 = 3424;
      }
    }
    else
    {
      v27 = 0;
      if ( a3 )
      {
        v23 = 3221225480LL;
        v22 = 3347;
        v14 = -1073741816;
        goto LABEL_33;
      }
      ClaimKeyFlags = BCryptIumRpcGetClaimKeyFlags(v17, &v27);
      v14 = ClaimKeyFlags;
      if ( ClaimKeyFlags )
      {
        v22 = 3356;
      }
      else
      {
        ClaimKeyFlags = CreateVsmKeyAttestationClaim(v17[1].Ptr, 0, 5u, a5, a6, a7, a8, v27, 0);
        v14 = ClaimKeyFlags;
        if ( !ClaimKeyFlags )
          goto LABEL_34;
        v22 = 3372;
      }
    }
    v23 = ClaimKeyFlags;
    goto LABEL_33;
  }
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v14;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      296,
      &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids,
      (unsigned int)Context);
LABEL_38:
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 4) != 0 )
    WPP_SF_d(v15[2], 301, &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x14000e510  push    rbx
0x14000e512  push    rbp
0x14000e513  push    rsi
0x14000e514  push    rdi
0x14000e515  push    r12
0x14000e517  push    r13
0x14000e519  push    r14
0x14000e51b  push    r15
0x14000e51d  sub     rsp, 68h
0x14000e521  mov     ebp, r9d
0x14000e524  mov     r14, r8
0x14000e527  mov     rdi, rdx
0x14000e52a  mov     rbx, rcx
0x14000e52d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e534  lea     r12, WPP_GLOBAL_Control
0x14000e53b  cmp     rcx, r12
0x14000e53e  jz      short loc_14000E55B
0x14000e540  test    byte ptr [rcx+1Ch], 4
0x14000e544  jz      short loc_14000E55B
0x14000e546  mov     rcx, [rcx+10h]
0x14000e54a  lea     r8, WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids
0x14000e551  mov     edx, 127h
0x14000e556  call    WPP_SF_
0x14000e55b  lea     rdx, [rsp+0A8h+var_50]
0x14000e560  mov     [rsp+0A8h+var_50], 0
0x14000e569  mov     rcx, rbx
0x14000e56c  call    BCryptIumContextManagerGetContext
0x14000e571  mov     ebx, eax
0x14000e573  test    eax, eax
0x14000e575  jns     short loc_14000E5AE
0x14000e577  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e57e  cmp     rcx, r12
0x14000e581  jz      loc_14000E810
0x14000e587  test    byte ptr [rcx+1Ch], 4
0x14000e58b  jz      loc_14000E7ED
0x14000e591  mov     rcx, [rcx+10h]
0x14000e595  lea     r8, WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids
0x14000e59c  mov     edx, 128h
0x14000e5a1  mov     r9d, eax
0x14000e5a4  call    WPP_SF_d
0x14000e5a9  jmp     loc_14000E7E6
0x14000e5ae  mov     rcx, [rsp+0A8h+var_50]; struct BCRYPTIUM_CONTEXT *
0x14000e5b3  mov     r8d, 42494F4Bh; unsigned int
0x14000e5b9  mov     rdx, rdi; unsigned __int64
0x14000e5bc  call    ?LookupBCryptIsoObject@@YAPEAU_BCRYPT_ISO_OBJECT@@PEAUBCRYPTIUM_CONTEXT@@_KK@Z; LookupBCryptIsoObject(BCRYPTIUM_CONTEXT *,unsigned __int64,ulong)
0x14000e5c1  xor     ebx, ebx
0x14000e5c3  mov     rsi, rax
0x14000e5c6  test    rax, rax
0x14000e5c9  jnz     short loc_14000E5E9
0x14000e5cb  mov     ecx, 0C0000008h
0x14000e5d0  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x14000e5d7  mov     r8d, 0CEFh
0x14000e5dd  mov     ebx, ecx
0x14000e5df  call    VBS_ATTEST_TRACE_ERROR_IN
0x14000e5e4  jmp     loc_14000E7E6
0x14000e5e9  mov     r15, [rsp+0A8h+arg_38]
0x14000e5f1  mov     rdi, rbx
0x14000e5f4  test    r15, r15
0x14000e5f7  jnz     short loc_14000E617
0x14000e5f9  mov     r8d, 0CF6h
0x14000e5ff  mov     ecx, 0C000000Dh
0x14000e604  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x14000e60b  mov     ebx, ecx
0x14000e60d  call    VBS_ATTEST_TRACE_ERROR_IN
0x14000e612  jmp     loc_14000E7D1
0x14000e617  cmp     [rsp+0A8h+arg_40], ebx
0x14000e61e  jz      short loc_14000E628
0x14000e620  mov     r8d, 0D00h
0x14000e626  jmp     short loc_14000E5FF
0x14000e628  lea     rcx, [rax+28h]; SRWLock
0x14000e62c  mov     r12d, ebx
0x14000e62f  call    cs:__imp_AcquireSRWLockShared
0x14000e635  sub     ebp, 5
0x14000e638  jz      loc_14000E724
0x14000e63e  cmp     ebp, 1
0x14000e641  jz      short loc_14000E655
0x14000e643  mov     ebx, 0C00000BBh
0x14000e648  mov     r8d, 0D67h
0x14000e64e  mov     ecx, ebx
0x14000e650  jmp     loc_14000E7A5
0x14000e655  mov     [rsp+0A8h+var_58], ebx
0x14000e659  test    r14, r14
0x14000e65c  jnz     short loc_14000E670
0x14000e65e  mov     ecx, 0C0000008h
0x14000e663  mov     r8d, 0D39h
0x14000e669  mov     ebx, ecx
0x14000e66b  jmp     loc_14000E7A5
0x14000e670  mov     rcx, [rsp+0A8h+var_50]; struct BCRYPTIUM_CONTEXT *
0x14000e675  mov     r8d, 42494F4Bh; unsigned int
0x14000e67b  mov     rdx, r14; unsigned __int64
0x14000e67e  call    ?LookupBCryptIsoObject@@YAPEAU_BCRYPT_ISO_OBJECT@@PEAUBCRYPTIUM_CONTEXT@@_KK@Z; LookupBCryptIsoObject(BCRYPTIUM_CONTEXT *,unsigned __int64,ulong)
0x14000e683  mov     rdi, rax
0x14000e686  test    rax, rax
0x14000e689  jnz     short loc_14000E69D
0x14000e68b  mov     ecx, 0C0000008h
0x14000e690  mov     r8d, 0D41h
0x14000e696  mov     ebx, ecx
0x14000e698  jmp     loc_14000E7A5
0x14000e69d  lea     rcx, [rax+28h]; SRWLock
0x14000e6a1  call    cs:__imp_AcquireSRWLockShared
0x14000e6a7  lea     rdx, [rsp+0A8h+var_58]
0x14000e6ac  mov     rcx, rsi
0x14000e6af  mov     r12d, 1
0x14000e6b5  call    BCryptIumRpcGetClaimKeyFlags
0x14000e6ba  mov     ebx, eax
0x14000e6bc  test    eax, eax
0x14000e6be  jz      short loc_14000E6CB
0x14000e6c0  mov     r8d, 0D50h
0x14000e6c6  jmp     loc_14000E7A3
0x14000e6cb  mov     eax, [rdi+10h]
0x14000e6ce  mov     r8d, 6; unsigned int
0x14000e6d4  mov     r9, [rsp+0A8h+arg_20]; struct _BCryptrBufferDesc *
0x14000e6dc  mov     rdx, [rdi+8]; void *
0x14000e6e0  mov     rcx, [rsi+8]; void *
0x14000e6e4  mov     [rsp+0A8h+var_68], eax; unsigned int
0x14000e6e8  mov     eax, [rsp+0A8h+var_58]
0x14000e6ec  mov     [rsp+0A8h+var_70], eax; unsigned int
0x14000e6f0  mov     eax, [rsp+0A8h+arg_30]
0x14000e6f7  mov     [rsp+0A8h+var_78], r15; unsigned int *
0x14000e6fc  mov     [rsp+0A8h+var_80], eax; unsigned int
0x14000e700  mov     rax, [rsp+0A8h+arg_28]
0x14000e708  mov     [rsp+0A8h+var_88], rax; unsigned __int8 *
0x14000e70d  call    ?CreateVsmKeyAttestationClaim@@YAJPEAX0KPEAU_BCryptrBufferDesc@@PEAEKPEAKKK@Z; CreateVsmKeyAttestationClaim(void *,void *,ulong,_BCryptrBufferDesc *,uchar *,ulong,ulong *,ulong,ulong)
0x14000e712  mov     ebx, eax
0x14000e714  test    eax, eax
0x14000e716  jz      loc_14000E7B1
0x14000e71c  mov     r8d, 0D60h
0x14000e722  jmp     short loc_14000E7A3
0x14000e724  mov     [rsp+0A8h+var_58], ebx
0x14000e728  test    r14, r14
0x14000e72b  jz      short loc_14000E73C
0x14000e72d  mov     ecx, 0C0000008h
0x14000e732  mov     r8d, 0D13h
0x14000e738  mov     ebx, ecx
0x14000e73a  jmp     short loc_14000E7A5
0x14000e73c  lea     rdx, [rsp+0A8h+var_58]
0x14000e741  mov     rcx, rsi
0x14000e744  call    BCryptIumRpcGetClaimKeyFlags
0x14000e749  mov     ebx, eax
0x14000e74b  test    eax, eax
0x14000e74d  jz      short loc_14000E757
0x14000e74f  mov     r8d, 0D1Ch
0x14000e755  jmp     short loc_14000E7A3
0x14000e757  mov     eax, [rsp+0A8h+var_58]
0x14000e75b  xor     edx, edx; void *
0x14000e75d  mov     r9, [rsp+0A8h+arg_20]; struct _BCryptrBufferDesc *
0x14000e765  mov     rcx, [rsi+8]; void *
0x14000e769  mov     [rsp+0A8h+var_68], edi; unsigned int
0x14000e76d  mov     [rsp+0A8h+var_70], eax; unsigned int
0x14000e771  lea     r8d, [rdx+5]; unsigned int
0x14000e775  mov     eax, [rsp+0A8h+arg_30]
0x14000e77c  mov     [rsp+0A8h+var_78], r15; unsigned int *
0x14000e781  mov     [rsp+0A8h+var_80], eax; unsigned int
0x14000e785  mov     rax, [rsp+0A8h+arg_28]
0x14000e78d  mov     [rsp+0A8h+var_88], rax; unsigned __int8 *
0x14000e792  call    ?CreateVsmKeyAttestationClaim@@YAJPEAX0KPEAU_BCryptrBufferDesc@@PEAEKPEAKKK@Z; CreateVsmKeyAttestationClaim(void *,void *,ulong,_BCryptrBufferDesc *,uchar *,ulong,ulong *,ulong,ulong)
0x14000e797  mov     ebx, eax
0x14000e799  test    eax, eax
0x14000e79b  jz      short loc_14000E7B1
0x14000e79d  mov     r8d, 0D2Ch
0x14000e7a3  mov     ecx, eax
0x14000e7a5  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x14000e7ac  call    VBS_ATTEST_TRACE_ERROR_IN
0x14000e7b1  lea     rcx, [rsi+28h]; SRWLock
0x14000e7b5  call    cs:__imp_ReleaseSRWLockShared
0x14000e7bb  test    r12d, r12d
0x14000e7be  jz      short loc_14000E7CA
0x14000e7c0  lea     rcx, [rdi+28h]; SRWLock
0x14000e7c4  call    cs:__imp_ReleaseSRWLockShared
0x14000e7ca  lea     r12, WPP_GLOBAL_Control
0x14000e7d1  mov     rcx, rsi; hMem
0x14000e7d4  call    ?BCryptIumDereferenceObject@@YAXPEAU_BCRYPT_ISO_OBJECT@@@Z; BCryptIumDereferenceObject(_BCRYPT_ISO_OBJECT *)
0x14000e7d9  test    rdi, rdi
0x14000e7dc  jz      short loc_14000E7E6
0x14000e7de  mov     rcx, rdi; hMem
0x14000e7e1  call    ?BCryptIumDereferenceObject@@YAXPEAU_BCRYPT_ISO_OBJECT@@@Z; BCryptIumDereferenceObject(_BCRYPT_ISO_OBJECT *)
0x14000e7e6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e7ed  cmp     rcx, r12
0x14000e7f0  jz      short loc_14000E810
0x14000e7f2  test    byte ptr [rcx+1Ch], 4
0x14000e7f6  jz      short loc_14000E810
0x14000e7f8  mov     rcx, [rcx+10h]
0x14000e7fc  lea     r8, WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids
0x14000e803  mov     edx, 12Dh
0x14000e808  mov     r9d, ebx
0x14000e80b  call    WPP_SF_d
0x14000e810  mov     eax, ebx
0x14000e812  add     rsp, 68h
0x14000e816  pop     r15
0x14000e818  pop     r14
0x14000e81a  pop     r13
0x14000e81c  pop     r12
0x14000e81e  pop     rdi
0x14000e81f  pop     rsi
0x14000e820  pop     rbp
0x14000e821  pop     rbx
0x14000e822  retn
```
