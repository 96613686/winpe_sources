# KerbCheckCachedKeys(int,_LARGE_INTEGER *,KERB_ALGORITHM_IDENTIFIER *,KDCDHKeyInfo *,_CERT_X942_DH_PARAMETERS *,void * *,void * *)

- ea: `0x180055d94`
- end: `0x18005609b`
- name: `?KerbCheckCachedKeys@@YAJHPEAT_LARGE_INTEGER@@PEAUKERB_ALGORITHM_IDENTIFIER@@PEAUKDCDHKeyInfo@@PEAU_CERT_X942_DH_PARAMETERS@@PEAPEAX4@Z`
- size: `775`
- prototype: `__int64 __fastcall(int, union _LARGE_INTEGER *, struct KERB_ALGORITHM_IDENTIFIER *, struct KDCDHKeyInfo *, struct _CERT_X942_DH_PARAMETERS *, void **, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180050e78`

## callees

- `0x1800038e4`
- `0x1800101ec`
- `0x180055d94`
- `0x1800790c8`
- `0x18007f2f8`
- `0x18008441c`
- `0x180084fd0`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180056082`
- `ntdll!RtlReleaseResource` at `0x180056082`
- `ntdll!RtlAcquireResourceExclusive` at `0x180055e17`
- `ntdll!RtlAcquireResourceExclusive` at `0x180055fb4`
- `ntdll!RtlAcquireResourceExclusive` at `0x180055e17`
- `ntdll!RtlAcquireResourceExclusive` at `0x180055fb4`
- `ntdll!RtlConvertSharedToExclusive` at `0x180055e50`
- `ntdll!RtlConvertSharedToExclusive` at `0x180055fe4`
- `ntdll!RtlConvertSharedToExclusive` at `0x180055e50`
- `ntdll!RtlConvertSharedToExclusive` at `0x180055fe4`
- `bcrypt!BCryptDestroyKey` at `0x180055e93`
- `bcrypt!BCryptDestroyKey` at `0x180055e93`

## pseudocode

```c
__int64 __fastcall KerbCheckCachedKeys(
        int a1,
        union _LARGE_INTEGER *a2,
        struct KERB_ALGORITHM_IDENTIFIER *a3,
        struct KDCDHKeyInfo *a4,
        struct _CERT_X942_DH_PARAMETERS *a5,
        void **a6,
        void **a7)
{
  unsigned int ECDHKey; // ebx
  __int64 j; // rsi
  unsigned int v12; // eax
  union _LARGE_INTEGER near **v13; // r8
  BCRYPT_KEY_HANDLE *v14; // r14
  __int64 i; // rsi
  union _LARGE_INTEGER near **v16; // rdx
  void **v17; // rdi
  union _LARGE_INTEGER near **v19; // [rsp+20h] [rbp-58h]
  struct _CERT_X942_DH_PARAMETERS *v20; // [rsp+28h] [rbp-50h]
  struct _CERT_X942_DH_PARAMETERS *v21; // [rsp+28h] [rbp-50h]

  ECDHKey = 0;
  if ( !a1 )
  {
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= 2 )
        return ECDHKey;
      v21 = (struct _CERT_X942_DH_PARAMETERS *)&_ImageBase[36 * i + 369216];
      if ( (unsigned int)KerbEqualDHDomainParameters(v21, a5) )
        break;
    }
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        84,
        WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids,
        (unsigned int)i);
    }
    RtlAcquireResourceExclusive(&KdcGlobalDHParametersLock, 1u);
    v16 = &(&KdcGlobalDHKeyExpirationTime)[i];
    v19 = v16;
    if ( SkewTime.QuadPart + a2->QuadPart <= (__int64)*v16 )
    {
      v17 = (void **)&(&KdcGlobalCachedDHKeys)[i];
    }
    else
    {
      RtlConvertSharedToExclusive(&KdcGlobalDHParametersLock);
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          85,
          WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids,
          (unsigned int)i);
      }
      v17 = (void **)&(&KdcGlobalCachedDHKeys)[i];
      ECDHKey = KerbDHCreateBCryptKey(v21, v17);
      if ( ECDHKey )
      {
LABEL_36:
        RtlReleaseResource(&KdcGlobalDHParametersLock);
        return ECDHKey;
      }
      v16 = v19;
      *v19 = (union _LARGE_INTEGER near *)(KdcGlobalAllowedDHKeyLifeTime.QuadPart + a2->QuadPart);
    }
    *(_WORD *)a4 |= 0x80u;
    KerbConvertLargeIntToGeneralizedTime((char *)a4 + 28, 0, v16);
    *a6 = *v17;
    goto LABEL_36;
  }
  if ( !KdcGlobalModpDHOnly )
  {
    for ( j = 0; ; j = (unsigned int)(j + 1) )
    {
      if ( (unsigned int)j >= 3 )
        return ECDHKey;
      v12 = *((_DWORD *)a3 + 4);
      if ( dword_1800B21A8[18 * j] == v12 && !memcmp_0((&off_1800B21B0)[9 * j], *((const void **)a3 + 3), v12) )
        break;
    }
    RtlAcquireResourceExclusive(&KdcGlobalDHParametersLock, 1u);
    v13 = &(&KdcGlobalECDHKeyExpirationTime)[j];
    v20 = (struct _CERT_X942_DH_PARAMETERS *)v13;
    if ( a2->QuadPart + SkewTime.QuadPart <= (__int64)*v13 )
    {
      v14 = (BCRYPT_KEY_HANDLE *)&(&KdcGlobalCachedECDHKeys)[j];
LABEL_17:
      *(_WORD *)a4 |= 0x80u;
      KerbConvertLargeIntToGeneralizedTime((char *)a4 + 28, 0, v13);
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          83,
          WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids,
          (unsigned int)j);
      }
      *a7 = *v14;
      goto LABEL_36;
    }
    RtlConvertSharedToExclusive(&KdcGlobalDHParametersLock);
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        82,
        WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids,
        (unsigned int)j);
    }
    v14 = (BCRYPT_KEY_HANDLE *)&(&KdcGlobalCachedECDHKeys)[j];
    if ( *v14 )
    {
      BCryptDestroyKey(*v14);
      *v14 = 0;
    }
    ECDHKey = KerbGenerateECDHKey(
                *((_DWORD *)&KerbGlobalECCNamedCurves + 18 * j),
                (BCRYPT_KEY_HANDLE *)&(&KdcGlobalCachedECDHKeys)[j]);
    if ( !ECDHKey )
    {
      v13 = (union _LARGE_INTEGER near **)v20;
      *(_QWORD *)&v20->p.cbData = KdcGlobalAllowedDHKeyLifeTime.QuadPart + a2->QuadPart;
      goto LABEL_17;
    }
    goto LABEL_36;
  }
  return ECDHKey;
}

```

## disassembly

```asm
0x180055d94  mov     [rsp+arg_8], rdx
0x180055d99  push    rbx
0x180055d9a  push    rbp
0x180055d9b  push    rsi
0x180055d9c  push    rdi
0x180055d9d  push    r12
0x180055d9f  push    r13
0x180055da1  push    r14
0x180055da3  push    r15
0x180055da5  sub     rsp, 38h
0x180055da9  xor     ebx, ebx
0x180055dab  mov     r13, r9
0x180055dae  mov     rbp, r8
0x180055db1  mov     r15, rdx
0x180055db4  test    ecx, ecx
0x180055db6  jz      loc_180055F33
0x180055dbc  cmp     cs:?KdcGlobalModpDHOnly@@3KA, ebx; ulong KdcGlobalModpDHOnly
0x180055dc2  jnz     loc_180056088
0x180055dc8  xor     esi, esi
0x180055dca  lea     rdi, __ImageBase
0x180055dd1  cmp     esi, 3
0x180055dd4  jnb     loc_180056088
0x180055dda  mov     eax, [rbp+10h]
0x180055ddd  lea     rcx, [rsi+rsi*8]
0x180055de1  mov     [rsp+78h+var_58], rcx
0x180055de6  cmp     rva dword_1800B21A8[rdi+rcx*8], eax
0x180055ded  jnz     short loc_180055E07
0x180055def  mov     rdx, [rbp+18h]; Buf2
0x180055df3  mov     r8d, eax; Size
0x180055df6  mov     rcx, rva off_1800B21B0[rdi+rcx*8]; Buf1
0x180055dfe  call    memcmp_0
0x180055e03  test    eax, eax
0x180055e05  jz      short loc_180055E0B
0x180055e07  inc     esi
0x180055e09  jmp     short loc_180055DD1
0x180055e0b  lea     rbp, ?KdcGlobalDHParametersLock@@3U_RTL_RESOURCE@@A; _RTL_RESOURCE KdcGlobalDHParametersLock
0x180055e12  mov     dl, 1; Wait
0x180055e14  mov     rcx, rbp; Resource
0x180055e17  call    cs:__imp_RtlAcquireResourceExclusive
0x180055e1d  mov     rdx, qword ptr cs:?SkewTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER SkewTime ...
0x180055e24  lea     r8, rva ?KdcGlobalECDHKeyExpirationTime@@3PAT_LARGE_INTEGER@@A[rdi]; _LARGE_INTEGER near * KdcGlobalECDHKeyExpirationTime ...
0x180055e2b  add     rdx, [r15]
0x180055e2e  lea     r8, [r8+rsi*8]
0x180055e32  lea     r12, WPP_GLOBAL_Control
0x180055e39  mov     [rsp+78h+var_50], r8
0x180055e3e  mov     r15d, 100000h
0x180055e44  cmp     rdx, [r8]
0x180055e47  jle     loc_180055ED6
0x180055e4d  mov     rcx, rbp; Resource
0x180055e50  call    cs:__imp_RtlConvertSharedToExclusive
0x180055e56  mov     rcx, cs:WPP_GLOBAL_Control
0x180055e5d  cmp     rcx, r12
0x180055e60  jz      short loc_180055E80
0x180055e62  test    [rcx+1Ch], r15d
0x180055e66  jz      short loc_180055E80
0x180055e68  mov     rcx, [rcx+10h]
0x180055e6c  lea     r8, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids
0x180055e73  mov     edx, 52h ; 'R'
0x180055e78  mov     r9d, esi
0x180055e7b  call    WPP_SF_d
0x180055e80  lea     r14, rva ?KdcGlobalCachedECDHKeys@@3PAPEAXA[rdi]; void * near * KdcGlobalCachedECDHKeys ...
0x180055e87  lea     r14, [r14+rsi*8]
0x180055e8b  mov     rcx, [r14]; hKey
0x180055e8e  test    rcx, rcx
0x180055e91  jz      short loc_180055E9C
0x180055e93  call    cs:__imp_BCryptDestroyKey
0x180055e99  mov     [r14], rbx
0x180055e9c  mov     rcx, [rsp+78h+var_58]
0x180055ea1  mov     rdx, r14; phKey
0x180055ea4  mov     ecx, rva ?KerbGlobalECCNamedCurves@@3PAU_KERB_ECC_CURVE_INFO@@A[rdi+rcx*8]; dwLength
0x180055eab  call    ?KerbGenerateECDHKey@@YAJKPEAPEAX@Z; KerbGenerateECDHKey(ulong,void * *)
0x180055eb0  mov     ebx, eax
0x180055eb2  test    eax, eax
0x180055eb4  jnz     loc_18005607F
0x180055eba  mov     rcx, [rsp+78h+arg_8]
0x180055ec2  mov     r8, [rsp+78h+var_50]
0x180055ec7  mov     rdx, [rcx]
0x180055eca  add     rdx, cs:?KdcGlobalAllowedDHKeyLifeTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER KdcGlobalAllowedDHKeyLifeTime
0x180055ed1  mov     [r8], rdx
0x180055ed4  jmp     short loc_180055EE1
0x180055ed6  lea     r14, rva ?KdcGlobalCachedECDHKeys@@3PAPEAXA[rdi]; void * near * KdcGlobalCachedECDHKeys ...
0x180055edd  lea     r14, [r14+rsi*8]
0x180055ee1  mov     eax, 80h
0x180055ee6  lea     rcx, [r13+1Ch]
0x180055eea  or      [r13+0], ax
0x180055eef  xor     edx, edx
0x180055ef1  call    KerbConvertLargeIntToGeneralizedTime
0x180055ef6  mov     rcx, cs:WPP_GLOBAL_Control
0x180055efd  cmp     rcx, r12
0x180055f00  jz      short loc_180055F20
0x180055f02  test    [rcx+1Ch], r15d
0x180055f06  jz      short loc_180055F20
0x180055f08  mov     rcx, [rcx+10h]
0x180055f0c  lea     r8, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids
0x180055f13  mov     edx, 53h ; 'S'
0x180055f18  mov     r9d, esi
0x180055f1b  call    WPP_SF_d
0x180055f20  mov     rax, [rsp+78h+arg_30]
0x180055f28  mov     rdx, [r14]
0x180055f2b  mov     [rax], rdx
0x180055f2e  jmp     loc_18005607F
0x180055f33  xor     esi, esi
0x180055f35  lea     rdi, __ImageBase
0x180055f3c  cmp     esi, 2
0x180055f3f  jnb     loc_180056088
0x180055f45  mov     rdx, [rsp+78h+arg_20]; struct _CERT_X942_DH_PARAMETERS *
0x180055f4d  lea     rax, [rsi+rsi*8]
0x180055f51  lea     rax, ds:0B4480h[rax*8]
0x180055f59  add     rax, rdi
0x180055f5c  mov     rcx, rax; struct _CERT_X942_DH_PARAMETERS *
0x180055f5f  mov     [rsp+78h+var_50], rax
0x180055f64  call    ?KerbEqualDHDomainParameters@@YAHPEBU_CERT_X942_DH_PARAMETERS@@0@Z; KerbEqualDHDomainParameters(_CERT_X942_DH_PARAMETERS const *,_CERT_X942_DH_PARAMETERS const *)
0x180055f69  test    eax, eax
0x180055f6b  jnz     short loc_180055F71
0x180055f6d  inc     esi
0x180055f6f  jmp     short loc_180055F3C
0x180055f71  mov     rcx, cs:WPP_GLOBAL_Control
0x180055f78  lea     r12, WPP_GLOBAL_Control
0x180055f7f  mov     r15d, 100000h
0x180055f85  cmp     rcx, r12
0x180055f88  jz      short loc_180055FA8
0x180055f8a  test    [rcx+1Ch], r15d
0x180055f8e  jz      short loc_180055FA8
0x180055f90  mov     rcx, [rcx+10h]
0x180055f94  lea     r8, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids
0x180055f9b  mov     edx, 54h ; 'T'
0x180055fa0  mov     r9d, esi
0x180055fa3  call    WPP_SF_d
0x180055fa8  lea     rbp, ?KdcGlobalDHParametersLock@@3U_RTL_RESOURCE@@A; _RTL_RESOURCE KdcGlobalDHParametersLock
0x180055faf  mov     dl, 1; Wait
0x180055fb1  mov     rcx, rbp; Resource
0x180055fb4  call    cs:__imp_RtlAcquireResourceExclusive
0x180055fba  mov     rcx, [rsp+78h+arg_8]
0x180055fc2  lea     rdx, rva ?KdcGlobalDHKeyExpirationTime@@3PAT_LARGE_INTEGER@@A[rdi]; _LARGE_INTEGER near * KdcGlobalDHKeyExpirationTime ...
0x180055fc9  lea     rdx, [rdx+rsi*8]
0x180055fcd  mov     [rsp+78h+var_58], rdx
0x180055fd2  mov     rcx, [rcx]
0x180055fd5  add     rcx, qword ptr cs:?SkewTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER SkewTime ...
0x180055fdc  cmp     rcx, [rdx]
0x180055fdf  jle     short loc_18005604E
0x180055fe1  mov     rcx, rbp; Resource
0x180055fe4  call    cs:__imp_RtlConvertSharedToExclusive
0x180055fea  mov     rcx, cs:WPP_GLOBAL_Control
0x180055ff1  cmp     rcx, r12
0x180055ff4  jz      short loc_180056014
0x180055ff6  test    [rcx+1Ch], r15d
0x180055ffa  jz      short loc_180056014
0x180055ffc  mov     rcx, [rcx+10h]
0x180056000  lea     r8, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids
0x180056007  mov     edx, 55h ; 'U'
0x18005600c  mov     r9d, esi
0x18005600f  call    WPP_SF_d
0x180056014  mov     rcx, [rsp+78h+var_50]; struct _CERT_X942_DH_PARAMETERS *
0x180056019  lea     rdi, [rdi+rsi*8]
0x18005601d  lea     rdi, [rdi+0B4470h]
0x180056024  mov     rdx, rdi; void **
0x180056027  call    ?KerbDHCreateBCryptKey@@YAJAEBU_CERT_X942_DH_PARAMETERS@@PEAPEAX@Z; KerbDHCreateBCryptKey(_CERT_X942_DH_PARAMETERS const &,void * *)
0x18005602c  mov     ebx, eax
0x18005602e  test    eax, eax
0x180056030  jnz     short loc_18005607F
0x180056032  mov     rax, [rsp+78h+arg_8]
0x18005603a  mov     rdx, [rsp+78h+var_58]
0x18005603f  mov     rcx, [rax]
0x180056042  add     rcx, cs:?KdcGlobalAllowedDHKeyLifeTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER KdcGlobalAllowedDHKeyLifeTime
0x180056049  mov     [rdx], rcx
0x18005604c  jmp     short loc_180056059
0x18005604e  lea     rdi, [rdi+rsi*8]
0x180056052  lea     rdi, [rdi+0B4470h]
0x180056059  mov     eax, 80h
0x18005605e  lea     rcx, [r13+1Ch]
0x180056062  or      [r13+0], ax
0x180056067  mov     r8, rdx
0x18005606a  xor     edx, edx
0x18005606c  call    KerbConvertLargeIntToGeneralizedTime
0x180056071  mov     rax, [rsp+78h+arg_28]
0x180056079  mov     rcx, [rdi]
0x18005607c  mov     [rax], rcx
0x18005607f  mov     rcx, rbp; Resource
0x180056082  call    cs:__imp_RtlReleaseResource
0x180056088  mov     eax, ebx
0x18005608a  add     rsp, 38h
0x18005608e  pop     r15
0x180056090  pop     r14
0x180056092  pop     r13
0x180056094  pop     r12
0x180056096  pop     rdi
0x180056097  pop     rsi
0x180056098  pop     rbp
0x180056099  pop     rbx
0x18005609a  retn
```
