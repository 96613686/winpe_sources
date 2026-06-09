# SiCreateSpace(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,ulong,_SP_TIER_INFO * * const)

- ea: `0x140010b5c`
- end: `0x140010f84`
- name: `?SiCreateSpace@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@KQEAPEAU_SP_TIER_INFO@@@Z`
- size: `1064`
- prototype: `__int64 __fastcall(struct _SU_POOL_OBJECT *, struct _SP_SPACE_INFO *, unsigned int, struct _SP_TIER_INFO **const)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140010360`
- `0x140012704`

## callees

- `0x14000fea0`
- `0x140010b5c`
- `0x140010f8c`
- `0x1400111c4`
- `0x140011478`
- `0x140011740`
- `0x140013c90`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140010f6b`
- `KERNEL32!LocalFree` at `0x140010f6b`
- `KERNEL32!SetLastError` at `0x140010c20`
- `KERNEL32!SetLastError` at `0x140010ece`
- `KERNEL32!SetLastError` at `0x140010c20`
- `KERNEL32!SetLastError` at `0x140010ece`
- `KERNEL32!LocalAlloc` at `0x140010c0d`
- `KERNEL32!LocalAlloc` at `0x140010c0d`

## pseudocode

```c
__int64 __fastcall SiCreateSpace(
        struct _SU_POOL_OBJECT *a1,
        struct _SP_SPACE_INFO *a2,
        unsigned int a3,
        struct _SP_TIER_INFO **const a4)
{
  unsigned int SpaceEstimate; // edi
  unsigned int v9; // edi
  int v10; // esi
  struct _SI_CREATE_CONTEXT *v11; // r14
  __int64 i; // rdx
  struct _SP_TIER_INFO *v13; // rax
  int v14; // ecx
  struct _SP_TIER_INFO *v15; // rax
  __int64 j; // r15
  struct _SP_TIER_INFO *v17; // rax
  struct _SP_TIER_INFO *v18; // rax
  struct _SP_TIER_INFO *v19; // rax
  struct _SP_TIER_INFO *v20; // rax
  struct _SP_TIER_INFO *v21; // rax
  unsigned int v22; // ecx
  __int64 v23; // rax
  unsigned int v24; // edx
  unsigned int v25; // edx
  __int64 v26; // rcx
  __int64 m; // rax
  struct _SP_TIER_INFO *v28; // rcx
  unsigned int k; // edx
  __int64 v30; // r9
  unsigned int v31; // eax
  __int64 v32; // r8
  __int64 v33; // r9
  struct _SP_TIER_INFO *v34; // rax
  __int64 n; // r15
  struct _SP_TIER_INFO *v36; // rdx
  unsigned int v38; // [rsp+20h] [rbp-58h]
  struct _SI_CREATE_CONTEXT *v39; // [rsp+28h] [rbp-50h]
  int v40; // [rsp+90h] [rbp+18h]

  if ( a3 )
  {
    v9 = *((_DWORD *)a1 + 661);
    v10 = 0;
    v38 = v9;
    switch ( *((_BYTE *)a2 + 2600) )
    {
      case 2:
        v10 = 1;
        break;
      case 4:
        v10 = 2;
        break;
      case 5:
        v10 = 3;
        break;
      case 6:
        v10 = 4;
        break;
      case 7:
        v10 = 5;
        break;
      case 0xA:
        v10 = 6;
        break;
      case 0xB:
        v10 = 7;
        break;
    }
    v11 = (struct _SI_CREATE_CONTEXT *)LocalAlloc(0x40u, 56 * a3);
    if ( !v11 )
    {
      SetLastError(0x5AAu);
      return 0;
    }
    v40 = 0;
    if ( v9 <= 0xE )
    {
      for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
      {
        v13 = a4[i];
        if ( *((_DWORD *)v13 + 654) == v10 )
        {
          v14 = *((_DWORD *)v13 + 666);
          *(_OWORD *)((char *)v13 + 2648) = *(_OWORD *)((char *)a2 + 2696);
          *(_OWORD *)((char *)v13 + 2664) = *(_OWORD *)((char *)a2 + 2712);
          *((_DWORD *)a4[i] + 666) = v14;
          v15 = a4[i];
          *(_OWORD *)((char *)v15 + 2692) = *(_OWORD *)((char *)a2 + 2748);
          *(_QWORD *)((char *)v15 + 2708) = *(_QWORD *)((char *)a2 + 2764);
        }
      }
    }
    for ( j = 0; (unsigned int)j < a3; j = (unsigned int)(j + 1) )
    {
      v17 = a4[j];
      if ( *((_DWORD *)v17 + 654) == v10 )
      {
        *(_OWORD *)((char *)v17 + 40) = *(_OWORD *)((char *)a2 + 24);
        *((_QWORD *)a2 + 333) = *((_QWORD *)a4[j] + 328);
        v18 = a4[j];
        *(_OWORD *)((char *)a2 + 2696) = *(_OWORD *)((char *)v18 + 2648);
        *(_OWORD *)((char *)a2 + 2712) = *(_OWORD *)((char *)v18 + 2664);
        v19 = a4[j];
        *(_OWORD *)((char *)a2 + 2748) = *(_OWORD *)((char *)v19 + 2692);
        *(_QWORD *)((char *)a2 + 2764) = *(_QWORD *)((char *)v19 + 2708);
        if ( v9 > 0xE && v10 == 1 && *((_QWORD *)a2 + 338) == -1 )
        {
          v40 = 1;
          *((_QWORD *)a2 + 338) = *((_QWORD *)a1 + 342)
                                - (unsigned __int64)(*((_QWORD *)a1 + 342) + 0xFFFFFFFFLL) % *((_QWORD *)a1 + 342)
                                + 0xFFFFFFFF;
        }
        v39 = (struct _SI_CREATE_CONTEXT *)((char *)v11 + 56 * (unsigned int)j);
        SpaceEstimate = SiCreateSpaceEstimate(a1, a2, v39);
        if ( !SpaceEstimate )
          goto LABEL_67;
        v20 = a4[j];
        v9 = v38;
        *(_OWORD *)((char *)v20 + 2648) = *(_OWORD *)((char *)a2 + 2696);
        *(_OWORD *)((char *)v20 + 2664) = *(_OWORD *)((char *)a2 + 2712);
        v21 = a4[j];
        *(_OWORD *)((char *)v21 + 2692) = *(_OWORD *)((char *)a2 + 2748);
        *(_QWORD *)((char *)v21 + 2708) = *(_QWORD *)((char *)a2 + 2764);
        *((_QWORD *)v39 + 1) = (char *)a4[j] + 2648;
        *((_QWORD *)v39 + 2) = (char *)a4[j] + 2692;
      }
    }
    if ( v9 > 0xE )
    {
      if ( v40 )
      {
        SpaceEstimate = SiFixupContext(a1, a3, v11);
        if ( !SpaceEstimate )
        {
LABEL_67:
          LocalFree(v11);
          return SpaceEstimate;
        }
      }
      else
      {
        for ( k = 0; k < a3; ++k )
        {
          v30 = 56LL * k;
          if ( (*((_BYTE *)v11 + v30) & 1) != 0 )
          {
            v31 = SP_RESILIENCY_INFO::NumberOfDataColumns(*(SP_RESILIENCY_INFO **)((char *)v11 + v30 + 16));
            if ( v32 )
            {
              if ( v32 != *(_QWORD *)(*(_QWORD *)((char *)v11 + v33 + 8) + 8LL) * v31 )
              {
                SetLastError(0x80E7000E);
                SpaceEstimate = 0;
                goto LABEL_67;
              }
            }
          }
        }
      }
    }
    else
    {
      v22 = 0;
      if ( a3 )
      {
        do
        {
          v23 = 56LL * v22;
          if ( (*((_BYTE *)v11 + v23) & 1) != 0 )
          {
            v24 = *(_DWORD *)(*(_QWORD *)((char *)v11 + v23 + 16) + 16LL);
            if ( v24 < *((_DWORD *)a2 + 691) )
              *((_DWORD *)a2 + 691) = v24;
          }
          ++v22;
        }
        while ( v22 < a3 );
        v25 = 0;
        do
        {
          v26 = 56LL * v25;
          if ( (*((_BYTE *)v11 + v26) & 1) != 0 )
            *(_DWORD *)(*(_QWORD *)((char *)v11 + v26 + 16) + 16LL) = *((_DWORD *)a2 + 691);
          ++v25;
        }
        while ( v25 < a3 );
      }
    }
    for ( m = 0; (unsigned int)m < a3; m = (unsigned int)(m + 1) )
    {
      v28 = a4[m];
      if ( *((_DWORD *)v28 + 654) == v10 )
      {
        _mm_lfence();
        *(_OWORD *)((char *)a2 + 2696) = *(_OWORD *)((char *)v28 + 2648);
        *(_OWORD *)((char *)a2 + 2712) = *(_OWORD *)((char *)v28 + 2664);
        v34 = a4[m];
        *(_OWORD *)((char *)a2 + 2748) = *(_OWORD *)((char *)v34 + 2692);
        *(_QWORD *)((char *)a2 + 2764) = *(_QWORD *)((char *)v34 + 2708);
        break;
      }
    }
    *((_QWORD *)a2 + 333) = 0;
    SpaceEstimate = SiCreateSpaceInternal(a1, a2);
    if ( SpaceEstimate )
    {
      for ( n = 0; (unsigned int)n < a3; n = (unsigned int)(n + 1) )
      {
        v36 = a4[n];
        if ( *((_DWORD *)v36 + 654) == v10 )
        {
          SpaceEstimate = SiCreateTierInternal(a1, v36);
          if ( !SpaceEstimate )
          {
            SiCleanupSpace((struct _SP_SPACE_INFO *)((char *)a2 + 8));
            goto LABEL_67;
          }
        }
      }
    }
    goto LABEL_67;
  }
  SpaceEstimate = SiCreateSpaceEstimate(a1, a2, 0);
  if ( SpaceEstimate )
    return (unsigned int)SiCreateSpaceInternal(a1, a2);
  return SpaceEstimate;
}

```

## disassembly

```asm
0x140010b5c  push    rbx
0x140010b5e  push    rbp
0x140010b5f  push    rsi
0x140010b60  push    rdi
0x140010b61  push    r12
0x140010b63  push    r13
0x140010b65  push    r14
0x140010b67  push    r15
0x140010b69  sub     rsp, 38h
0x140010b6d  mov     r12, r9
0x140010b70  mov     ebp, r8d
0x140010b73  mov     rbx, rdx
0x140010b76  mov     r13, rcx
0x140010b79  test    r8d, r8d
0x140010b7c  jnz     short loc_140010BA2
0x140010b7e  xor     r8d, r8d; struct _SI_CREATE_CONTEXT *
0x140010b81  call    ?SiCreateSpaceEstimate@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@PEAU_SI_CREATE_CONTEXT@@@Z; SiCreateSpaceEstimate(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,_SI_CREATE_CONTEXT *)
0x140010b86  mov     edi, eax
0x140010b88  test    eax, eax
0x140010b8a  jz      loc_140010F71
0x140010b90  mov     rdx, rbx; struct _SP_SPACE_INFO *
0x140010b93  mov     rcx, r13; struct _SU_POOL_OBJECT *
0x140010b96  call    ?SiCreateSpaceInternal@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@@Z; SiCreateSpaceInternal(_SU_POOL_OBJECT *,_SP_SPACE_INFO *)
0x140010b9b  mov     edi, eax
0x140010b9d  jmp     loc_140010F71
0x140010ba2  mov     edi, [rcx+0A54h]
0x140010ba8  xor     esi, esi
0x140010baa  movzx   ecx, byte ptr [rdx+0A28h]
0x140010bb1  mov     [rsp+78h+var_58], edi
0x140010bb5  sub     ecx, 2
0x140010bb8  jz      short loc_140010C00
0x140010bba  sub     ecx, 2
0x140010bbd  jz      short loc_140010BF9
0x140010bbf  sub     ecx, 1
0x140010bc2  jz      short loc_140010BF2
0x140010bc4  sub     ecx, 1
0x140010bc7  jz      short loc_140010BEB
0x140010bc9  sub     ecx, 1
0x140010bcc  jz      short loc_140010BE4
0x140010bce  sub     ecx, 3
0x140010bd1  jz      short loc_140010BDD
0x140010bd3  cmp     ecx, 1
0x140010bd6  jnz     short loc_140010C05
0x140010bd8  lea     esi, [rcx+6]
0x140010bdb  jmp     short loc_140010C05
0x140010bdd  mov     esi, 6
0x140010be2  jmp     short loc_140010C05
0x140010be4  mov     esi, 5
0x140010be9  jmp     short loc_140010C05
0x140010beb  mov     esi, 4
0x140010bf0  jmp     short loc_140010C05
0x140010bf2  mov     esi, 3
0x140010bf7  jmp     short loc_140010C05
0x140010bf9  mov     esi, 2
0x140010bfe  jmp     short loc_140010C05
0x140010c00  mov     esi, 1
0x140010c05  imul    edx, ebp, 38h ; '8'; uBytes
0x140010c08  mov     ecx, 40h ; '@'; uFlags
0x140010c0d  call    cs:__imp_LocalAlloc
0x140010c13  mov     r14, rax
0x140010c16  test    rax, rax
0x140010c19  jnz     short loc_140010C2D
0x140010c1b  mov     ecx, 5AAh; dwErrCode
0x140010c20  call    cs:__imp_SetLastError
0x140010c26  xor     edi, edi
0x140010c28  jmp     loc_140010F71
0x140010c2d  mov     [rsp+78h+arg_10], 0
0x140010c38  cmp     edi, 0Eh
0x140010c3b  ja      short loc_140010CA3
0x140010c3d  xor     edx, edx
0x140010c3f  test    ebp, ebp
0x140010c41  jz      short loc_140010CA3
0x140010c43  mov     rax, [r12+rdx*8]
0x140010c47  cmp     [rax+0A38h], esi
0x140010c4d  jnz     short loc_140010C9D
0x140010c4f  mov     ecx, [rax+0A68h]
0x140010c55  movups  xmm0, xmmword ptr [rbx+0A88h]
0x140010c5c  movups  xmmword ptr [rax+0A58h], xmm0
0x140010c63  movups  xmm1, xmmword ptr [rbx+0A98h]
0x140010c6a  movups  xmmword ptr [rax+0A68h], xmm1
0x140010c71  mov     rax, [r12+rdx*8]
0x140010c75  mov     [rax+0A68h], ecx
0x140010c7b  mov     rax, [r12+rdx*8]
0x140010c7f  movups  xmm0, xmmword ptr [rbx+0ABCh]
0x140010c86  movups  xmmword ptr [rax+0A84h], xmm0
0x140010c8d  movsd   xmm1, qword ptr [rbx+0ACCh]
0x140010c95  movsd   qword ptr [rax+0A94h], xmm1
0x140010c9d  inc     edx
0x140010c9f  cmp     edx, ebp
0x140010ca1  jb      short loc_140010C43
0x140010ca3  xor     r15d, r15d
0x140010ca6  mov     r9d, 0FFFFFFFFh
0x140010cac  cmp     r15d, ebp
0x140010caf  jnb     loc_140010DF6
0x140010cb5  mov     rax, [r12+r15*8]
0x140010cb9  mov     r8d, r15d
0x140010cbc  cmp     [rax+0A38h], esi
0x140010cc2  jnz     loc_140010DEE
0x140010cc8  movups  xmm0, xmmword ptr [rbx+18h]
0x140010ccc  movdqu  xmmword ptr [rax+28h], xmm0
0x140010cd1  mov     rax, [r12+r15*8]
0x140010cd5  mov     rcx, [rax+0A40h]
0x140010cdc  mov     [rbx+0A68h], rcx
0x140010ce3  mov     rax, [r12+r15*8]
0x140010ce7  movups  xmm0, xmmword ptr [rax+0A58h]
0x140010cee  movups  xmmword ptr [rbx+0A88h], xmm0
0x140010cf5  movups  xmm1, xmmword ptr [rax+0A68h]
0x140010cfc  movups  xmmword ptr [rbx+0A98h], xmm1
0x140010d03  mov     rax, [r12+r15*8]
0x140010d07  movups  xmm0, xmmword ptr [rax+0A84h]
0x140010d0e  movups  xmmword ptr [rbx+0ABCh], xmm0
0x140010d15  movsd   xmm1, qword ptr [rax+0A94h]
0x140010d1d  movsd   qword ptr [rbx+0ACCh], xmm1
0x140010d25  cmp     edi, 0Eh
0x140010d28  jbe     short loc_140010D5D
0x140010d2a  cmp     esi, 1
0x140010d2d  jnz     short loc_140010D5D
0x140010d2f  cmp     qword ptr [rbx+0A90h], 0FFFFFFFFFFFFFFFFh
0x140010d37  jnz     short loc_140010D5D
0x140010d39  mov     rcx, [r13+0AB0h]
0x140010d40  xor     edx, edx
0x140010d42  mov     [rsp+78h+arg_10], esi
0x140010d49  lea     rax, [rcx+r9]
0x140010d4d  div     rcx
0x140010d50  sub     rcx, rdx
0x140010d53  add     rcx, r9
0x140010d56  mov     [rbx+0A90h], rcx
0x140010d5d  imul    rax, r8, 38h ; '8'
0x140010d61  mov     rdx, rbx; struct _SP_SPACE_INFO *
0x140010d64  mov     rcx, r13; struct _SU_POOL_OBJECT *
0x140010d67  add     rax, r14
0x140010d6a  mov     r8, rax; struct _SI_CREATE_CONTEXT *
0x140010d6d  mov     [rsp+78h+var_50], rax
0x140010d72  call    ?SiCreateSpaceEstimate@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@PEAU_SI_CREATE_CONTEXT@@@Z; SiCreateSpaceEstimate(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,_SI_CREATE_CONTEXT *)
0x140010d77  mov     edi, eax
0x140010d79  test    eax, eax
0x140010d7b  jz      loc_140010F68
0x140010d81  mov     rax, [r12+r15*8]
0x140010d85  mov     r9d, 0FFFFFFFFh
0x140010d8b  movups  xmm0, xmmword ptr [rbx+0A88h]
0x140010d92  mov     rdx, [rsp+78h+var_50]
0x140010d97  mov     edi, [rsp+78h+var_58]
0x140010d9b  movups  xmmword ptr [rax+0A58h], xmm0
0x140010da2  movups  xmm1, xmmword ptr [rbx+0A98h]
0x140010da9  movups  xmmword ptr [rax+0A68h], xmm1
0x140010db0  mov     rax, [r12+r15*8]
0x140010db4  movups  xmm0, xmmword ptr [rbx+0ABCh]
0x140010dbb  movups  xmmword ptr [rax+0A84h], xmm0
0x140010dc2  movsd   xmm1, qword ptr [rbx+0ACCh]
0x140010dca  movsd   qword ptr [rax+0A94h], xmm1
0x140010dd2  mov     rax, [r12+r15*8]
0x140010dd6  add     rax, 0A58h
0x140010ddc  mov     [rdx+8], rax
0x140010de0  mov     rax, [r12+r15*8]
0x140010de4  add     rax, 0A84h
0x140010dea  mov     [rdx+10h], rax
0x140010dee  inc     r15d
0x140010df1  jmp     loc_140010CAC
0x140010df6  cmp     edi, 0Eh
0x140010df9  ja      short loc_140010E67
0x140010dfb  xor     ecx, ecx
0x140010dfd  test    ebp, ebp
0x140010dff  jz      short loc_140010E4D
0x140010e01  mov     eax, ecx
0x140010e03  imul    rax, 38h ; '8'
0x140010e07  test    byte ptr [rax+r14], 1
0x140010e0c  jz      short loc_140010E24
0x140010e0e  mov     rax, [rax+r14+10h]
0x140010e13  mov     edx, [rax+10h]
0x140010e16  cmp     edx, [rbx+0ACCh]
0x140010e1c  jnb     short loc_140010E24
0x140010e1e  mov     [rbx+0ACCh], edx
0x140010e24  inc     ecx
0x140010e26  cmp     ecx, ebp
0x140010e28  jb      short loc_140010E01
0x140010e2a  xor     edx, edx
0x140010e2c  mov     eax, edx
0x140010e2e  imul    rcx, rax, 38h ; '8'
0x140010e32  test    byte ptr [rcx+r14], 1
0x140010e37  jz      short loc_140010E47
0x140010e39  mov     rcx, [rcx+r14+10h]
0x140010e3e  mov     eax, [rbx+0ACCh]
0x140010e44  mov     [rcx+10h], eax
0x140010e47  inc     edx
0x140010e49  cmp     edx, ebp
0x140010e4b  jb      short loc_140010E2C
0x140010e4d  xor     eax, eax
0x140010e4f  cmp     eax, ebp
0x140010e51  jnb     loc_140010F1C
0x140010e57  mov     rcx, [r12+rax*8]
0x140010e5b  cmp     [rcx+0A38h], esi
0x140010e61  jz      short loc_140010EDB
0x140010e63  inc     eax
0x140010e65  jmp     short loc_140010E4F
0x140010e67  cmp     [rsp+78h+arg_10], 0
0x140010e6f  jz      short loc_140010E8A
0x140010e71  mov     r8, r14; struct _SI_CREATE_CONTEXT *
0x140010e74  mov     edx, ebp; unsigned int
0x140010e76  mov     rcx, r13; struct _SU_POOL_OBJECT *
0x140010e79  call    ?SiFixupContext@@YAHPEAU_SU_POOL_OBJECT@@KPEAU_SI_CREATE_CONTEXT@@@Z; SiFixupContext(_SU_POOL_OBJECT *,ulong,_SI_CREATE_CONTEXT *)
0x140010e7e  mov     edi, eax
0x140010e80  test    eax, eax
0x140010e82  jz      loc_140010F68
0x140010e88  jmp     short loc_140010E4D
0x140010e8a  xor     r8d, r8d
0x140010e8d  xor     edx, edx
0x140010e8f  cmp     edx, ebp
0x140010e91  jnb     short loc_140010E4D
0x140010e93  mov     eax, edx
0x140010e95  imul    r9, rax, 38h ; '8'
0x140010e99  test    byte ptr [r9+r14], 1
0x140010e9e  jz      short loc_140010EC5
0x140010ea0  mov     rcx, [r9+r14+10h]; this
0x140010ea5  call    ?NumberOfDataColumns@SP_RESILIENCY_INFO@@QEAAKXZ; SP_RESILIENCY_INFO::NumberOfDataColumns(void)
0x140010eaa  mov     ecx, eax
0x140010eac  mov     rax, [r9+r14+8]
0x140010eb1  imul    rcx, [rax+8]
0x140010eb6  test    r8, r8
0x140010eb9  jnz     short loc_140010EC0
0x140010ebb  mov     r8, rcx
0x140010ebe  jmp     short loc_140010EC5
0x140010ec0  cmp     r8, rcx
0x140010ec3  jnz     short loc_140010EC9
0x140010ec5  inc     edx
0x140010ec7  jmp     short loc_140010E8F
0x140010ec9  mov     ecx, 80E7000Eh; dwErrCode
0x140010ece  call    cs:__imp_SetLastError
0x140010ed4  xor     edi, edi
0x140010ed6  jmp     loc_140010F68
0x140010edb  lfence
0x140010ede  movups  xmm0, xmmword ptr [rcx+0A58h]
0x140010ee5  movups  xmmword ptr [rbx+0A88h], xmm0
0x140010eec  movups  xmm1, xmmword ptr [rcx+0A68h]
0x140010ef3  movups  xmmword ptr [rbx+0A98h], xmm1
0x140010efa  mov     rax, [r12+rax*8]
0x140010efe  movups  xmm0, xmmword ptr [rax+0A84h]
0x140010f05  movups  xmmword ptr [rbx+0ABCh], xmm0
0x140010f0c  movsd   xmm1, qword ptr [rax+0A94h]
0x140010f14  movsd   qword ptr [rbx+0ACCh], xmm1
0x140010f1c  mov     rdx, rbx; struct _SP_SPACE_INFO *
0x140010f1f  mov     qword ptr [rbx+0A68h], 0
0x140010f2a  mov     rcx, r13; struct _SU_POOL_OBJECT *
0x140010f2d  call    ?SiCreateSpaceInternal@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@@Z; SiCreateSpaceInternal(_SU_POOL_OBJECT *,_SP_SPACE_INFO *)
0x140010f32  mov     edi, eax
0x140010f34  test    eax, eax
0x140010f36  jz      short loc_140010F68
0x140010f38  xor     r15d, r15d
0x140010f3b  cmp     r15d, ebp
0x140010f3e  jnb     short loc_140010F68
0x140010f40  mov     rdx, [r12+r15*8]; struct _SP_TIER_INFO *
0x140010f44  cmp     [rdx+0A38h], esi
0x140010f4a  jnz     short loc_140010F5A
0x140010f4c  mov     rcx, r13; struct _SU_POOL_OBJECT *
0x140010f4f  call    ?SiCreateTierInternal@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_TIER_INFO@@@Z; SiCreateTierInternal(_SU_POOL_OBJECT *,_SP_TIER_INFO *)
0x140010f54  mov     edi, eax
0x140010f56  test    eax, eax
0x140010f58  jz      short loc_140010F5F
0x140010f5a  inc     r15d
0x140010f5d  jmp     short loc_140010F3B
0x140010f5f  lea     rcx, [rbx+8]; lpInBuffer
0x140010f63  call    ?SiCleanupSpace@@YAXPEAU_SP_ID@@@Z; SiCleanupSpace(_SP_ID *)
0x140010f68  mov     rcx, r14; hMem
0x140010f6b  call    cs:__imp_LocalFree
0x140010f71  mov     eax, edi
0x140010f73  add     rsp, 38h
0x140010f77  pop     r15
0x140010f79  pop     r14
0x140010f7b  pop     r13
0x140010f7d  pop     r12
0x140010f7f  pop     rdi
0x140010f80  pop     rsi
0x140010f81  pop     rbp
0x140010f82  pop     rbx
0x140010f83  retn
```
