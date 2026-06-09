# CmsRollbackProtection::ValidateAndAttestMountMeasurementsImpl(CmsVolume const &,SmsCheckpointRecord const &,CmsPCRHelper &,bool &,bool &,bool &)

- ea: `0x14012a2c8`
- end: `0x14012aa7e`
- name: `?ValidateAndAttestMountMeasurementsImpl@CmsRollbackProtection@@IEAAJAEBVCmsVolume@@AEBUSmsCheckpointRecord@@AEAVCmsPCRHelper@@AEA_N33@Z`
- size: `1974`
- prototype: `__int64 __usercall@<rax>(CmsRollbackProtection *__hidden this@<rcx>, const struct CmsVolume *@<rdx>, const struct SmsCheckpointRecord *@<r8>, struct CmsPCRHelper *@<r9>, bool *, bool *, bool *)`
- caller_count: `1`
- callee_count: `21`
- tags: `installer_update`

## callers

- `0x14012a0ec`

## callees

- `0x140004870`
- `0x1400057e0`
- `0x1400248f0`
- `0x14007eba8`
- `0x1400830cc`
- `0x1400830f4`
- `0x140083a24`
- `0x14008baf0`
- `0x1400a3208`
- `0x1400aad18`
- `0x1400aadec`
- `0x14012998c`
- `0x140129a70`
- `0x140129bfc`
- `0x140129e48`
- `0x140129ea8`
- `0x140129f04`
- `0x14012a024`
- `0x14012a088`
- `0x14012a2c8`
- `0x1401b9010`

## string_xrefs

- `0x14012a71c`: `STATUS_VOLUME_ROLLBACK_DETECTED`
- `0x14012aa5b`: `STATUS_VOLUME_ROLLBACK_DETECTED`
- `0x14012a351`: `minkernel\fs\minstore\cmsrollbackprotection.cpp`
- `0x14012a3cc`: `minkernel\fs\minstore\cmsrollbackprotection.cpp`
- `0x14012a4eb`: `minkernel\fs\minstore\cmsrollbackprotection.cpp`
- `0x14012a62e`: `minkernel\fs\minstore\cmsrollbackprotection.cpp`
- `0x14012a6e0`: `minkernel\fs\minstore\cmsrollbackprotection.cpp`
- `0x14012a730`: `minkernel\fs\minstore\cmsrollbackprotection.cpp`
- `0x14012a796`: `minkernel\fs\minstore\cmsrollbackprotection.cpp`
- `0x14012a80f`: `minkernel\fs\minstore\cmsrollbackprotection.cpp`
- `0x14012a846`: `minkernel\fs\minstore\cmsrollbackprotection.cpp`
- `0x14012a872`: `minkernel\fs\minstore\cmsrollbackprotection.cpp`
- `0x14012a916`: `minkernel\fs\minstore\cmsrollbackprotection.cpp`
- `0x14012aa62`: `minkernel\fs\minstore\cmsrollbackprotection.cpp`
- `0x14012a3a2`: `BootVolumeRollbackProtectionGUID`
- `0x14012a32f`: `FailMountOnRollbackProtectionMismatch`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CmsRollbackProtection::ValidateAndAttestMountMeasurementsImpl(
        CmsRollbackProtection *this,
        const struct CmsVolume *a2,
        const struct SmsCheckpointRecord *a3,
        struct CmsPCRHelper *a4,
        bool *a5,
        bool *a6,
        bool *a7)
{
  int Variable; // eax
  char v12; // al
  int v13; // eax
  __int64 v14; // r8
  unsigned __int64 v15; // rdx
  char *v16; // rdi
  __int64 v17; // rax
  __int64 v18; // r8
  bool *v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 (__fastcall *v22)(__int64, __int64, bool **); // rax
  int v23; // eax
  int v24; // ebx
  __int64 v25; // rdx
  CmsChecksum *v26; // r9
  __int64 DigestSize; // rbx
  __int64 v28; // rdx
  __int64 v29; // r9
  bool *v30; // rbx
  int v31; // eax
  bool v32; // cl
  __int64 v33; // rdx
  int v34; // eax
  char v35; // r12
  unsigned int v36; // eax
  __int64 v37; // r8
  __m128i *v38; // r9
  __int64 v39; // rdx
  int v40; // eax
  int v41; // eax
  char v42; // r15
  bool *v43; // rcx
  unsigned __int64 v44; // rdx
  unsigned __int64 v45; // r8
  _QWORD *unique; // rax
  size_t v48; // r9
  CmsRollbackProtection *v49; // rcx
  int v50; // [rsp+20h] [rbp-B1h]
  int v51; // [rsp+20h] [rbp-B1h]
  const char *v52; // [rsp+28h] [rbp-A9h]
  bool v53; // [rsp+30h] [rbp-A1h] BYREF
  char v54; // [rsp+31h] [rbp-A0h]
  char v55; // [rsp+32h] [rbp-9Fh]
  char v56; // [rsp+33h] [rbp-9Eh]
  __m128i *v57; // [rsp+40h] [rbp-91h] BYREF
  __int64 v58; // [rsp+48h] [rbp-89h]
  bool *v59; // [rsp+50h] [rbp-81h] BYREF
  bool *v60; // [rsp+58h] [rbp-79h] BYREF
  bool *v61; // [rsp+60h] [rbp-71h] BYREF
  __int64 v62; // [rsp+68h] [rbp-69h]
  bool *v63; // [rsp+70h] [rbp-61h] BYREF
  __int64 v64; // [rsp+78h] [rbp-59h]
  __int64 v65; // [rsp+80h] [rbp-51h]
  __m128i si128; // [rsp+88h] [rbp-49h] BYREF
  __int128 v67; // [rsp+98h] [rbp-39h]
  int v68; // [rsp+A8h] [rbp-29h]
  __int128 v69; // [rsp+B0h] [rbp-21h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+47h]

  v59 = a5;
  v60 = a6;
  v55 = 1;
  v61 = a5;
  v62 = 1;
  Variable = CmsFwEnvVariable::GetVariable(
               *((_QWORD *)a2 + 6),
               (unsigned int)L"FailMountOnRollbackProtectionMismatch",
               (unsigned int)&v61,
               0,
               0);
  if ( Variable != -1073741275 )
  {
    if ( Variable >= 0 )
      v55 = 0;
    else
      wil::details::in1diag3::_Log_NtStatus(
        retaddr,
        (void *)0x36,
        (unsigned int)"minkernel\\fs\\minstore\\cmsrollbackprotection.cpp",
        (const char *)(unsigned int)Variable,
        v50);
  }
  v69 = 0;
  v12 = 0;
  v54 = 0;
  *a6 = 1;
  if ( (*((_DWORD *)a2 + 821) & 0x200000) != 0 )
  {
    v61 = (bool *)&v69;
    v62 = 16;
    v13 = CmsFwEnvVariable::GetVariable(
            *((_QWORD *)a2 + 6),
            (unsigned int)L"BootVolumeRollbackProtectionGUID",
            (unsigned int)&v61,
            0,
            0);
    if ( v13 == -1073741275 )
    {
      v12 = 1;
      v54 = 1;
    }
    else
    {
      if ( v13 >= 0 )
        *a6 = 0;
      else
        wil::details::in1diag3::_Log_NtStatus(
          retaddr,
          (void *)0x4D,
          (unsigned int)"minkernel\\fs\\minstore\\cmsrollbackprotection.cpp",
          (const char *)(unsigned int)v13,
          v50);
      v12 = 0;
    }
  }
  if ( (*((_DWORD *)a3 + 30) & 0x400) == 0 || !*((_DWORD *)a3 + 40) )
  {
    *a7 = 0;
    if ( (*((_DWORD *)a2 + 821) & 0x200000) != 0 && !v12 )
    {
      v33 = 86;
      goto LABEL_107;
    }
    return 0;
  }
  *a7 = 1;
  v14 = *((unsigned int *)a3 + 39);
  v15 = *((unsigned int *)a3 + 40);
  if ( v15 + v14 > *((unsigned int *)a2 + 17) || v15 < 0x50 )
    goto LABEL_103;
  v16 = (char *)a3 + v14;
  v17 = *(unsigned int *)((char *)a3 + v14 + 68);
  if ( (_DWORD)v17 )
  {
    if ( *((_DWORD *)v16 + 16) < 0x50u )
      goto LABEL_103;
    v18 = *(unsigned int *)((char *)a3 + v14 + 68);
    v65 = v17;
    if ( v17 + (unsigned __int64)*((unsigned int *)v16 + 16) > v15 )
      goto LABEL_103;
  }
  else
  {
    v18 = 0;
    v65 = v17;
  }
  if ( *((_DWORD *)v16 + 19)
    && (*((_DWORD *)v16 + 18) < 0x50u
     || *((unsigned int *)v16 + 19) + (unsigned __int64)*((unsigned int *)v16 + 18) > v15) )
  {
LABEL_103:
    v33 = 94;
    goto LABEL_107;
  }
  v19 = (bool *)&v16[*((unsigned int *)v16 + 16)];
  v61 = v19;
  v20 = *(_QWORD *)a4;
  if ( !*(_QWORD *)a4
    || (v21 = *(_QWORD *)(v20 + 24)) == 0
    || (v22 = *(__int64 (__fastcall **)(__int64, __int64, bool **))(v21 + 760)) == 0
    || (v63 = v19, v64 = v18, v23 = v22(v20, 327732, &v63), v24 = v23, v23 >= 0) )
  {
    if ( *((_DWORD *)v16 + 19) )
    {
      v26 = (CmsChecksum *)*((_QWORD *)a2 + 427);
      si128 = 0;
      v67 = 0;
      v68 = 0;
      si128.m128i_i16[0] = *((_WORD *)v26 + 4);
      DigestSize = CmsChecksum::GetDigestSize(v26);
      v63 = (bool *)&si128.m128i_i8[2];
      v64 = DigestSize;
      v57 = (__m128i *)&v16[*((unsigned int *)v16 + 18)];
      v58 = v28;
      (*(void (__fastcall **)(__int64, __m128i **, bool **))(*(_QWORD *)v29 + 24LL))(v29, &v57, &v63);
      v57 = &si128;
      v58 = DigestSize + 2;
      v24 = CmsPCRHelper::Attest<327733>(a4, &v57);
      if ( v24 < 0 )
      {
        v25 = 122;
        goto LABEL_28;
      }
    }
    if ( *((_QWORD *)v16 + 1) != *((_QWORD *)a2 + 402) || *((_QWORD *)v16 + 2) != *((_QWORD *)a2 + 403) )
    {
      v33 = 125;
      goto LABEL_107;
    }
    v24 = CmsRollbackProtection::SetRollbackGUID(this, (const struct _GUID *)(v16 + 24));
    if ( v24 < 0 )
    {
      v25 = 127;
      goto LABEL_28;
    }
    v53 = 1;
    v57 = (__m128i *)&v53;
    v58 = 1;
    v30 = 0;
    v31 = CmsFwEnvVariable::GetVariable(*((_QWORD *)a2 + 6), *((_QWORD *)this + 4), (unsigned int)&v57, 0, 0);
    if ( v31 == -1073741275 )
    {
      v56 = 1;
      v32 = v16[4] & 1;
      v53 = v32;
    }
    else
    {
      v56 = 0;
      if ( v31 >= 0 )
        *a6 = 0;
      else
        wil::details::in1diag3::_Log_NtStatus(
          retaddr,
          (void *)0x92,
          (unsigned int)"minkernel\\fs\\minstore\\cmsrollbackprotection.cpp",
          (const char *)(unsigned int)v31,
          v51);
      v32 = v53;
    }
    if ( v55 )
      *v59 = v32;
    if ( v32 != (v16[4] & 1) )
    {
      v33 = 154;
LABEL_107:
      v24 = -1073740573;
      wil::details::in1diag3::Return_NtStatusMsg(
        retaddr,
        (void *)v33,
        (unsigned int)"minkernel\\fs\\minstore\\cmsrollbackprotection.cpp",
        (const char *)0xC00004E3LL,
        (int)"STATUS_VOLUME_ROLLBACK_DETECTED",
        v52);
      return (unsigned int)v24;
    }
    if ( (*((_DWORD *)a2 + 821) & 0x200000) != 0 && !v54 && v69 != *(_OWORD *)(v16 + 24) )
    {
      v33 = 162;
      goto LABEL_107;
    }
    si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    *(_QWORD *)&v67 = -1;
    v34 = CmsFwEnvVariable::GetVariable(*((_QWORD *)a2 + 6), *((_QWORD *)this + 8), &si128);
    if ( v34 == -1073741275 )
    {
      v35 = 1;
LABEL_63:
      utl::vector<enum utl::byte,utl::allocator<enum utl::byte>>::_Uninit(&si128);
      v59 = 0;
      v57 = (__m128i *)&v59;
      v58 = 8;
      v41 = CmsFwEnvVariable::GetVariable(*((_QWORD *)a2 + 6), *((_QWORD *)this + 12), (unsigned int)&v57, 0, 0);
      if ( v41 == -1073741275 )
      {
        v42 = 1;
      }
      else
      {
        v42 = 0;
        if ( v41 >= 0 )
        {
          *v60 = 0;
          v43 = v59;
          if ( (unsigned __int64)v59 < *((_QWORD *)v16 + 6) )
          {
            wil::details::in1diag3::_Log_NtStatus(
              retaddr,
              (void *)0xCF,
              (unsigned int)"minkernel\\fs\\minstore\\cmsrollbackprotection.cpp",
              (const char *)0xC0000095LL,
              v50);
            v43 = v59;
          }
          else
          {
            v30 = &v59[-*((_QWORD *)v16 + 6)];
          }
          v44 = (unsigned __int64)&v43[*((_QWORD *)v16 + 7)];
          if ( v44 < (unsigned __int64)v43 )
          {
            wil::details::in1diag3::_Log_NtStatus(
              retaddr,
              (void *)0xD3,
              (unsigned int)"minkernel\\fs\\minstore\\cmsrollbackprotection.cpp",
              (const char *)0xC0000095LL,
              v50);
            v44 = -1;
          }
          if ( *((_QWORD *)a3 + 12) < (unsigned __int64)v30 )
          {
            v33 = 215;
            goto LABEL_107;
          }
          if ( *((_QWORD *)a3 + 12) > v44 )
          {
            v33 = 216;
            goto LABEL_107;
          }
        }
        else
        {
          wil::details::in1diag3::_Log_NtStatus(
            retaddr,
            (void *)0xCA,
            (unsigned int)"minkernel\\fs\\minstore\\cmsrollbackprotection.cpp",
            (const char *)(unsigned int)v41,
            v50);
        }
      }
      if ( v35 != v42 )
      {
        v33 = 226;
        goto LABEL_107;
      }
      v45 = *((unsigned int *)v16 + 17) + (unsigned __int64)*((unsigned int *)v16 + 16);
      if ( v45 <= *((unsigned int *)v16 + 18) + (unsigned __int64)*((unsigned int *)v16 + 19) )
        v45 = *((unsigned int *)v16 + 18) + (unsigned __int64)*((unsigned int *)v16 + 19);
      if ( v45 < 0x50 )
        v45 = 80;
      unique = tlx::make_unique_oversize<SmsPersistentRollbackProtectionInformation,,0>(&v60, v45);
      utl::unique_ptr<SmsCheckpointRecord,tlx::generic_delete<SmsCheckpointRecord,tlx::operator_delete_deallocate>>::operator=(
        (char *)this + 128,
        unique);
      utl::unique_ptr<SmsPersistentRollbackProtectionInformation,tlx::generic_delete<SmsPersistentRollbackProtectionInformation,tlx::operator_delete_deallocate>>::~unique_ptr<SmsPersistentRollbackProtectionInformation,tlx::generic_delete<SmsPersistentRollbackProtectionInformation,tlx::operator_delete_deallocate>>(&v60);
      if ( !*((_QWORD *)this + 16) )
      {
        wil::details::in1diag3::Return_NtStatusMsg(
          retaddr,
          (void *)0xE9,
          (unsigned int)"minkernel\\fs\\minstore\\cmsrollbackprotection.cpp",
          (const char *)0xC000009ALL,
          (int)"STATUS_INSUFFICIENT_RESOURCES",
          v52);
        return 3221225626LL;
      }
      v48 = *((unsigned int *)v16 + 17) + (unsigned __int64)*((unsigned int *)v16 + 16);
      if ( v48 <= *((unsigned int *)v16 + 18) + (unsigned __int64)*((unsigned int *)v16 + 19) )
        v48 = *((unsigned int *)v16 + 18) + (unsigned __int64)*((unsigned int *)v16 + 19);
      if ( v48 < 0x50 )
        v48 = 80;
      memcpy_0(*((void **)this + 16), v16, v48);
      if ( v56 )
      {
        v24 = CmsRollbackProtection::SetVolumeFailMountOnMismatchFwVariable(this, a2, v53);
        if ( v24 < 0 )
        {
          v25 = 237;
          goto LABEL_28;
        }
      }
      if ( v35 )
      {
        v57 = (__m128i *)v61;
        v58 = v65;
        v24 = CmsRollbackProtection::SetFrozenChecksumFwVariable(this, a2, &v57);
        if ( v24 < 0 )
        {
          v25 = 241;
          goto LABEL_28;
        }
      }
      if ( v42 )
      {
        v24 = CmsRollbackProtection::SetVirtualClockFwVariable(this, a2, *((_QWORD *)a3 + 12));
        if ( v24 < 0 )
        {
          v25 = 245;
          goto LABEL_28;
        }
      }
      if ( v54 )
      {
        v24 = CmsRollbackProtection::SetBootVolumeGuidFwVariable(v49, a2, (const struct _GUID *)(v16 + 24));
        if ( v24 < 0 )
        {
          v25 = 250;
          goto LABEL_28;
        }
      }
      *((_BYTE *)this + 24) = 1;
      return 0;
    }
    v35 = 0;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::_Log_NtStatus(
        retaddr,
        (void *)0xB2,
        (unsigned int)"minkernel\\fs\\minstore\\cmsrollbackprotection.cpp",
        (const char *)(unsigned int)v34,
        v51);
      goto LABEL_63;
    }
    *v60 = 0;
    v36 = CmsChecksum::GetDigestSize(*((CmsChecksum **)this + 2));
    if ( v37 == v36 )
    {
      v57 = v38;
      v58 = v37;
      v63 = v61;
      v64 = v65;
      v40 = CmsChecksum::ChecksumsMatch(*((_QWORD *)this + 2), &v63, &v57);
      v24 = v40;
      if ( v40 != -1073740688 )
      {
        if ( v40 >= 0 )
        {
          v30 = 0;
          goto LABEL_63;
        }
        wil::details::in1diag3::Return_NtStatus(
          retaddr,
          (void *)0xB9,
          (unsigned int)"minkernel\\fs\\minstore\\cmsrollbackprotection.cpp",
          (const char *)(unsigned int)v40,
          v51);
LABEL_57:
        utl::vector<enum utl::byte,utl::allocator<enum utl::byte>>::_Uninit(&si128);
        return (unsigned int)v24;
      }
      v39 = 184;
    }
    else
    {
      v39 = 181;
    }
    v24 = -1073740573;
    wil::details::in1diag3::Return_NtStatusMsg(
      retaddr,
      (void *)v39,
      (unsigned int)"minkernel\\fs\\minstore\\cmsrollbackprotection.cpp",
      (const char *)0xC00004E3LL,
      (int)"STATUS_VOLUME_ROLLBACK_DETECTED",
      v52);
    goto LABEL_57;
  }
  wil::details::in1diag3::Return_NtStatus(
    retaddr,
    (void *)0x37,
    (unsigned int)"minkernel\\fs\\minstore\\MinStorePCRAttestation.hpp",
    (const char *)(unsigned int)v23,
    v50);
  v25 = 102;
LABEL_28:
  wil::details::in1diag3::Return_NtStatus(
    retaddr,
    (void *)v25,
    (unsigned int)"minkernel\\fs\\minstore\\cmsrollbackprotection.cpp",
    (const char *)(unsigned int)v24,
    v50);
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x14012a2c8  push    rbp
0x14012a2ca  push    rbx
0x14012a2cb  push    rsi
0x14012a2cc  push    rdi
0x14012a2cd  push    r12
0x14012a2cf  push    r13
0x14012a2d1  push    r14
0x14012a2d3  push    r15
0x14012a2d5  lea     rbp, [rsp-7]
0x14012a2da  sub     rsp, 0D8h
0x14012a2e1  mov     rax, cs:__security_cookie
0x14012a2e8  xor     rax, rsp
0x14012a2eb  mov     [rbp+3Fh+var_50], rax
0x14012a2ef  mov     r15, r9
0x14012a2f2  mov     r13, r8
0x14012a2f5  mov     rsi, rdx
0x14012a2f8  mov     r14, rcx
0x14012a2fb  mov     rax, [rbp+3Fh+arg_20]
0x14012a2ff  mov     [rsp+110h+var_C0], rax
0x14012a304  mov     r12, [rbp+3Fh+arg_28]
0x14012a308  mov     [rbp+3Fh+var_B8], r12
0x14012a30c  mov     rbx, [rbp+3Fh+arg_30]
0x14012a310  mov     [rsp+110h+var_DE], 1
0x14012a315  mov     [rbp+3Fh+var_B0], rax
0x14012a319  mov     [rbp+3Fh+var_A8], 1
0x14012a321  xor     edi, edi
0x14012a323  mov     qword ptr [rsp+110h+var_F0], rdi; int
0x14012a328  xor     r9d, r9d
0x14012a32b  lea     r8, [rbp+3Fh+var_B0]
0x14012a32f  lea     rdx, aFailmountonrol; "FailMountOnRollbackProtectionMismatch"
0x14012a336  mov     rcx, [rsi+30h]
0x14012a33a  call    ?GetVariable@CmsFwEnvVariable@@SAJPEAUMS_USERMODE_DEVICE_CONTEXT@@QEBGV?$span@W4byte@utl@@$0?0@utl@@PEAW4EmsFwVariableAttributes@@PEA_K@Z; CmsFwEnvVariable::GetVariable(MS_USERMODE_DEVICE_CONTEXT *,ushort const * const,utl::span<utl::byte,-1>,EmsFwVariableAttributes *,unsigned __int64 *)
0x14012a33f  cmp     eax, 0C0000225h
0x14012a344  jz      short loc_14012A367
0x14012a346  mov     rcx, [rbp+47h]; this
0x14012a34a  test    eax, eax
0x14012a34c  jns     short loc_14012A362
0x14012a34e  mov     r9d, eax; char *
0x14012a351  lea     r8, aMinkernelFsMin_12; "minkernel\\fs\\minstore\\cmsrollbackpro"...
0x14012a358  lea     edx, [rdi+36h]; void *
0x14012a35b  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x14012a360  jmp     short loc_14012A367
0x14012a362  mov     [rsp+110h+var_DE], dil
0x14012a367  xorps   xmm0, xmm0
0x14012a36a  movups  [rbp+3Fh+var_60], xmm0
0x14012a36e  mov     al, dil
0x14012a371  mov     [rsp+110h+var_DF], al
0x14012a375  mov     byte ptr [r12], 1
0x14012a37a  test    dword ptr [rsi+0CD4h], 200000h
0x14012a384  jz      short loc_14012A3E6
0x14012a386  lea     rax, [rbp+3Fh+var_60]
0x14012a38a  mov     [rbp+3Fh+var_B0], rax
0x14012a38e  mov     [rbp+3Fh+var_A8], 10h
0x14012a396  mov     qword ptr [rsp+110h+var_F0], rdi; int
0x14012a39b  xor     r9d, r9d
0x14012a39e  lea     r8, [rbp+3Fh+var_B0]
0x14012a3a2  lea     rdx, aBootvolumeroll; "BootVolumeRollbackProtectionGUID"
0x14012a3a9  mov     rcx, [rsi+30h]
0x14012a3ad  call    ?GetVariable@CmsFwEnvVariable@@SAJPEAUMS_USERMODE_DEVICE_CONTEXT@@QEBGV?$span@W4byte@utl@@$0?0@utl@@PEAW4EmsFwVariableAttributes@@PEA_K@Z; CmsFwEnvVariable::GetVariable(MS_USERMODE_DEVICE_CONTEXT *,ushort const * const,utl::span<utl::byte,-1>,EmsFwVariableAttributes *,unsigned __int64 *)
0x14012a3b2  cmp     eax, 0C0000225h
0x14012a3b7  jnz     short loc_14012A3C1
0x14012a3b9  mov     al, 1
0x14012a3bb  mov     [rsp+110h+var_DF], al
0x14012a3bf  jmp     short loc_14012A3E6
0x14012a3c1  mov     rcx, [rbp+47h]; this
0x14012a3c5  test    eax, eax
0x14012a3c7  jns     short loc_14012A3DF
0x14012a3c9  mov     r9d, eax; char *
0x14012a3cc  lea     r8, aMinkernelFsMin_12; "minkernel\\fs\\minstore\\cmsrollbackpro"...
0x14012a3d3  mov     edx, 4Dh ; 'M'; void *
0x14012a3d8  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x14012a3dd  jmp     short loc_14012A3E3
0x14012a3df  mov     [r12], dil
0x14012a3e3  mov     al, dil
0x14012a3e6  test    dword ptr [r13+78h], 400h
0x14012a3ee  jz      loc_14012AA3E
0x14012a3f4  cmp     [r13+0A0h], edi
0x14012a3fb  jz      loc_14012AA3E
0x14012a401  mov     byte ptr [rbx], 1
0x14012a404  mov     r8d, [r13+9Ch]
0x14012a40b  mov     edx, [r13+0A0h]
0x14012a412  lea     rcx, [rdx+r8]
0x14012a416  mov     eax, [rsi+44h]
0x14012a419  cmp     rcx, rax
0x14012a41c  ja      loc_14012AA37
0x14012a422  mov     ecx, 50h ; 'P'
0x14012a427  cmp     rdx, rcx
0x14012a42a  jb      loc_14012AA37
0x14012a430  lea     rdi, [r8+r13]
0x14012a434  mov     eax, [rdi+44h]
0x14012a437  test    eax, eax
0x14012a439  jnz     short loc_14012A444
0x14012a43b  mov     r8d, eax
0x14012a43e  mov     [rbp+3Fh+var_90], rax
0x14012a442  jmp     short loc_14012A463
0x14012a444  cmp     [rdi+40h], ecx
0x14012a447  jb      loc_14012AA37
0x14012a44d  mov     r8, rax
0x14012a450  mov     [rbp+3Fh+var_90], rax
0x14012a454  mov     eax, [rdi+40h]
0x14012a457  add     rax, r8
0x14012a45a  cmp     rax, rdx
0x14012a45d  ja      loc_14012AA37
0x14012a463  cmp     dword ptr [rdi+4Ch], 0
0x14012a467  jz      short loc_14012A484
0x14012a469  cmp     [rdi+48h], ecx
0x14012a46c  jb      loc_14012AA37
0x14012a472  mov     ecx, [rdi+48h]
0x14012a475  mov     eax, [rdi+4Ch]
0x14012a478  add     rcx, rax
0x14012a47b  cmp     rcx, rdx
0x14012a47e  ja      loc_14012AA37
0x14012a484  mov     edx, [rdi+40h]
0x14012a487  add     rdx, rdi
0x14012a48a  mov     [rbp+3Fh+var_B0], rdx
0x14012a48e  mov     rcx, [r15]
0x14012a491  test    rcx, rcx
0x14012a494  jz      short loc_14012A4FC
0x14012a496  mov     rax, [rcx+18h]
0x14012a49a  test    rax, rax
0x14012a49d  jz      short loc_14012A4FC
0x14012a49f  mov     rax, [rax+2F8h]
0x14012a4a6  test    rax, rax
0x14012a4a9  jz      short loc_14012A4FC
0x14012a4ab  mov     [rbp+3Fh+var_A0], rdx
0x14012a4af  mov     [rbp+3Fh+var_98], r8
0x14012a4b3  lea     r8, [rbp+3Fh+var_A0]
0x14012a4b7  mov     edx, 50034h
0x14012a4bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14012a4c1  mov     ebx, eax
0x14012a4c3  test    eax, eax
0x14012a4c5  jns     short loc_14012A4FC
0x14012a4c7  mov     rcx, [rbp+47h]; this
0x14012a4cb  mov     r9d, eax; char *
0x14012a4ce  lea     r8, aMinkernelFsMin_3; "minkernel\\fs\\minstore\\MinStorePCRAtt"...
0x14012a4d5  mov     edx, 37h ; '7'; void *
0x14012a4da  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x14012a4df  mov     edx, 66h ; 'f'; void *
0x14012a4e4  mov     rcx, [rbp+47h]; this
0x14012a4e8  mov     r9d, ebx; char *
0x14012a4eb  lea     r8, aMinkernelFsMin_12; "minkernel\\fs\\minstore\\cmsrollbackpro"...
0x14012a4f2  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x14012a4f7  jmp     loc_14012AA7A
0x14012a4fc  mov     edx, [rdi+4Ch]
0x14012a4ff  test    rdx, rdx
0x14012a502  jz      loc_14012A595
0x14012a508  mov     r9, [rsi+0D58h]
0x14012a50f  xorps   xmm0, xmm0
0x14012a512  xor     eax, eax
0x14012a514  movups  [rbp+3Fh+var_88], xmm0
0x14012a518  movups  [rbp+3Fh+var_78], xmm0
0x14012a51c  mov     [rbp+3Fh+var_68], eax
0x14012a51f  movzx   eax, word ptr [r9+8]
0x14012a524  mov     word ptr [rbp+3Fh+var_88], ax
0x14012a528  mov     rcx, r9; this
0x14012a52b  call    ?GetDigestSize@CmsChecksum@@QEBAKXZ; CmsChecksum::GetDigestSize(void)
0x14012a530  mov     ebx, eax
0x14012a532  lea     rax, [rbp+3Fh+var_88+2]
0x14012a536  mov     [rbp+3Fh+var_A0], rax
0x14012a53a  mov     [rbp+3Fh+var_98], rbx
0x14012a53e  mov     eax, [rdi+48h]
0x14012a541  add     rax, rdi
0x14012a544  mov     [rsp+110h+var_D0], rax
0x14012a549  mov     [rsp+110h+var_C8], rdx
0x14012a54e  mov     rax, [r9]
0x14012a551  lea     r8, [rbp+3Fh+var_A0]
0x14012a555  lea     rdx, [rsp+110h+var_D0]
0x14012a55a  mov     rcx, r9
0x14012a55d  mov     rax, [rax+18h]
0x14012a561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14012a566  lea     rax, [rbp+3Fh+var_88]
0x14012a56a  mov     [rsp+110h+var_D0], rax
0x14012a56f  lea     rax, [rbx+2]
0x14012a573  mov     [rsp+110h+var_C8], rax
0x14012a578  lea     rdx, [rsp+110h+var_D0]
0x14012a57d  mov     rcx, r15
0x14012a580  call    ??$Attest@$0FAADF@@CmsPCRHelper@@QEAAJAEBV?$span@$$CBW4byte@utl@@$0?0@utl@@@Z; CmsPCRHelper::Attest<327733>(utl::span<utl::byte const,-1> const &)
0x14012a585  mov     ebx, eax
0x14012a587  test    eax, eax
0x14012a589  jns     short loc_14012A595
0x14012a58b  mov     edx, 7Ah ; 'z'
0x14012a590  jmp     loc_14012A4E4
0x14012a595  mov     rax, [rdi+8]
0x14012a599  cmp     rax, [rsi+0C90h]
0x14012a5a0  jnz     loc_14012AA30
0x14012a5a6  mov     rax, [rdi+10h]
0x14012a5aa  cmp     rax, [rsi+0C98h]
0x14012a5b1  jnz     loc_14012AA30
0x14012a5b7  lea     rdx, [rdi+18h]; struct _GUID *
0x14012a5bb  mov     rcx, r14; this
0x14012a5be  call    ?SetRollbackGUID@CmsRollbackProtection@@AEAAJAEBU_GUID@@@Z; CmsRollbackProtection::SetRollbackGUID(_GUID const &)
0x14012a5c3  mov     ebx, eax
0x14012a5c5  test    eax, eax
0x14012a5c7  jns     short loc_14012A5D3
0x14012a5c9  mov     edx, 7Fh
0x14012a5ce  jmp     loc_14012A4E4
0x14012a5d3  mov     [rsp+110h+var_E0], 1
0x14012a5d8  lea     rax, [rsp+110h+var_E0]
0x14012a5dd  mov     [rsp+110h+var_D0], rax
0x14012a5e2  mov     [rsp+110h+var_C8], 1
0x14012a5eb  xor     ebx, ebx
0x14012a5ed  mov     qword ptr [rsp+110h+var_F0], rbx; int
0x14012a5f2  xor     r9d, r9d
0x14012a5f5  lea     r8, [rsp+110h+var_D0]
0x14012a5fa  mov     rdx, [r14+20h]
0x14012a5fe  mov     rcx, [rsi+30h]
0x14012a602  call    ?GetVariable@CmsFwEnvVariable@@SAJPEAUMS_USERMODE_DEVICE_CONTEXT@@QEBGV?$span@W4byte@utl@@$0?0@utl@@PEAW4EmsFwVariableAttributes@@PEA_K@Z; CmsFwEnvVariable::GetVariable(MS_USERMODE_DEVICE_CONTEXT *,ushort const * const,utl::span<utl::byte,-1>,EmsFwVariableAttributes *,unsigned __int64 *)
0x14012a607  cmp     eax, 0C0000225h
0x14012a60c  jnz     short loc_14012A61F
0x14012a60e  mov     [rsp+110h+var_DD], 1
0x14012a613  mov     cl, [rdi+4]
0x14012a616  and     cl, 1
0x14012a619  mov     [rsp+110h+var_E0], cl
0x14012a61d  jmp     short loc_14012A649
0x14012a61f  mov     [rsp+110h+var_DD], bl
0x14012a623  mov     rcx, [rbp+47h]; this
0x14012a627  test    eax, eax
0x14012a629  jns     short loc_14012A641
0x14012a62b  mov     r9d, eax; char *
0x14012a62e  lea     r8, aMinkernelFsMin_12; "minkernel\\fs\\minstore\\cmsrollbackpro"...
0x14012a635  mov     edx, 92h; void *
0x14012a63a  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x14012a63f  jmp     short loc_14012A645
0x14012a641  mov     [r12], bl
0x14012a645  mov     cl, [rsp+110h+var_E0]
0x14012a649  cmp     [rsp+110h+var_DE], bl
0x14012a64d  jz      short loc_14012A656
0x14012a64f  mov     rax, [rsp+110h+var_C0]
0x14012a654  mov     [rax], cl
0x14012a656  mov     al, [rdi+4]
0x14012a659  and     al, 1
0x14012a65b  cmp     cl, al
0x14012a65d  jz      short loc_14012A669
0x14012a65f  mov     edx, 9Ah
0x14012a664  jmp     loc_14012AA56
0x14012a669  test    dword ptr [rsi+0CD4h], 200000h
0x14012a673  jz      short loc_14012A699
0x14012a675  cmp     [rsp+110h+var_DF], bl
0x14012a679  jnz     short loc_14012A699
0x14012a67b  mov     rax, qword ptr [rbp+3Fh+var_60]
0x14012a67f  cmp     rax, [rdi+18h]
0x14012a683  jnz     short loc_14012A68F
0x14012a685  mov     rax, qword ptr [rbp+3Fh+var_60+8]
0x14012a689  cmp     rax, [rdi+20h]
0x14012a68d  jz      short loc_14012A699
0x14012a68f  mov     edx, 0A2h
0x14012a694  jmp     loc_14012AA56
0x14012a699  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14012a6a1  movdqu  [rbp+3Fh+var_88], xmm0
0x14012a6a6  mov     qword ptr [rbp+3Fh+var_78], 0FFFFFFFFFFFFFFFFh
0x14012a6ae  lea     r8, [rbp+3Fh+var_88]
0x14012a6b2  mov     rdx, [r14+40h]
0x14012a6b6  mov     rcx, [rsi+30h]
0x14012a6ba  call    ?GetVariable@CmsFwEnvVariable@@SAJPEAUMS_USERMODE_DEVICE_CONTEXT@@QEBGAEAV?$vector@W4byte@utl@@V?$allocator@W4byte@utl@@@2@@utl@@PEAW4EmsFwVariableAttributes@@@Z; CmsFwEnvVariable::GetVariable(MS_USERMODE_DEVICE_CONTEXT *,ushort const * const,utl::vector<utl::byte,utl::allocator<utl::byte>> &,EmsFwVariableAttributes *)
0x14012a6bf  mov     r15d, 0C0000225h
0x14012a6c5  cmp     eax, r15d
0x14012a6c8  jnz     short loc_14012A6D2
0x14012a6ca  mov     r12b, 1
0x14012a6cd  jmp     loc_14012A7AB
0x14012a6d2  mov     r12b, bl
0x14012a6d5  mov     rcx, [rbp+47h]; this
0x14012a6d9  test    eax, eax
0x14012a6db  jns     short loc_14012A6F6
0x14012a6dd  mov     r9d, eax; char *
0x14012a6e0  lea     r8, aMinkernelFsMin_12; "minkernel\\fs\\minstore\\cmsrollbackpro"...
0x14012a6e7  mov     edx, 0B2h; void *
0x14012a6ec  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x14012a6f1  jmp     loc_14012A7AB
0x14012a6f6  mov     rax, [rbp+3Fh+var_B8]
0x14012a6fa  mov     [rax], bl
0x14012a6fc  mov     r8, qword ptr [rbp+3Fh+var_88+8]
0x14012a700  mov     r9, qword ptr [rbp+3Fh+var_88]
0x14012a704  sub     r8, r9
0x14012a707  mov     rcx, [r14+10h]; this
0x14012a70b  call    ?GetDigestSize@CmsChecksum@@QEBAKXZ; CmsChecksum::GetDigestSize(void)
0x14012a710  mov     edx, eax
0x14012a712  cmp     r8, rdx
0x14012a715  jz      short loc_14012A74F
0x14012a717  mov     edx, 0B5h; void *
0x14012a71c  lea     rax, aStatusVolumeRo; "STATUS_VOLUME_ROLLBACK_DETECTED"
0x14012a723  mov     ebx, 0C00004E3h
0x14012a728  mov     qword ptr [rsp+110h+var_F0], rax; int
0x14012a72d  mov     r9d, ebx; char *
0x14012a730  lea     r8, aMinkernelFsMin_12; "minkernel\\fs\\minstore\\cmsrollbackpro"...
0x14012a737  mov     rcx, [rbp+47h]; this
0x14012a73b  call    ?Return_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x14012a740  nop
0x14012a741  lea     rcx, [rbp+3Fh+var_88]
0x14012a745  call    ?_Uninit@?$vector@W4byte@utl@@V?$allocator@W4byte@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::byte,utl::allocator<utl::byte>>::_Uninit(void)
0x14012a74a  jmp     loc_14012AA7A
0x14012a74f  mov     [rsp+110h+var_D0], r9
0x14012a754  mov     [rsp+110h+var_C8], r8
0x14012a759  mov     rax, [rbp+3Fh+var_B0]
0x14012a75d  mov     [rbp+3Fh+var_A0], rax
0x14012a761  mov     rax, [rbp+3Fh+var_90]
0x14012a765  mov     [rbp+3Fh+var_98], rax
0x14012a769  lea     r8, [rsp+110h+var_D0]
0x14012a76e  lea     rdx, [rbp+3Fh+var_A0]
0x14012a772  mov     rcx, [r14+10h]
0x14012a776  call    ?ChecksumsMatch@CmsChecksum@@QEBAJV?$span@$$CBW4byte@utl@@$0?0@utl@@0@Z; CmsChecksum::ChecksumsMatch(utl::span<utl::byte const,-1>,utl::span<utl::byte const,-1>)
  ... truncated ...
```
