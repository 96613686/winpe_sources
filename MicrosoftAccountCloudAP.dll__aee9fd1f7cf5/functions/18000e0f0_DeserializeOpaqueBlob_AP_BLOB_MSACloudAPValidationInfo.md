# DeserializeOpaqueBlob(_AP_BLOB *,MSACloudAPValidationInfo * *)

- ea: `0x18000e0f0`
- end: `0x18000e55e`
- name: `?DeserializeOpaqueBlob@@YAJPEAU_AP_BLOB@@PEAPEAUMSACloudAPValidationInfo@@@Z`
- size: `1134`
- prototype: `__int64 __fastcall(struct _AP_BLOB *, struct MSACloudAPValidationInfo **)`
- caller_count: `6`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180012be8`
- `0x180013148`
- `0x180013cd4`
- `0x1800141a0`
- `0x18001495c`
- `0x180014ff0`

## callees

- `0x180007eb8`
- `0x180008440`
- `0x18000baac`
- `0x18000d980`
- `0x18000deac`
- `0x18000dfd4`
- `0x18000e0f0`
- `0x18000fcf4`
- `0x180010064`
- `0x18001143c`
- `0x180011540`

## string_xrefs

- `0x18000e141`: `onecoreuap\ds\ext\live\identity\cloudapplugin\utils.cpp`
- `0x18000e11d`: `DeserializeOpaqueBlob`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DeserializeOpaqueBlob(struct _AP_BLOB *a1, struct MSACloudAPValidationInfo **a2)
{
  _DWORD *v4; // rsi
  __int64 v5; // r14
  int v6; // ebx
  errno_t v7; // eax
  __int64 v8; // rbx
  void *v9; // r15
  errno_t v10; // eax
  unsigned __int64 v11; // rbx
  void *v12; // r15
  errno_t v13; // eax
  __int64 v14; // rdi
  errno_t v15; // eax
  __int64 v16; // rbx
  void *v17; // r15
  errno_t v18; // eax
  int v19; // eax
  unsigned __int64 v20; // rbx
  void *v21; // r15
  errno_t v22; // eax
  unsigned __int64 v23; // rbx
  void *v24; // r15
  errno_t v25; // eax
  unsigned __int64 v26; // rbx
  void *v27; // r15
  errno_t v28; // eax
  _DWORD *v30; // [rsp+20h] [rbp-48h] BYREF
  __int64 v31; // [rsp+28h] [rbp-40h]
  __int64 v32; // [rsp+30h] [rbp-38h]
  _QWORD v33[6]; // [rsp+38h] [rbp-30h] BYREF
  int v34; // [rsp+B0h] [rbp+48h] BYREF

  v34 = 0;
  v32 = 0;
  v31 = 0;
  v33[0] = "DeserializeOpaqueBlob";
  v33[1] = &v34;
  v33[2] = 0;
  v33[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\utils.cpp",
    "DeserializeOpaqueBlob",
    (const char *)0x161,
    0,
    0);
  if ( !a1 || !*((_QWORD *)a1 + 1) || *(_DWORD *)a1 <= 0x38u || !a2 )
    goto LABEL_32;
  *a2 = 0;
  v4 = LiveAllocate(0xF8u);
  Auto<MSACloudAPValidationInfo *,ValidationInfoFunctor,DummyContext>::Clear(&v30);
  v30 = v4;
  if ( !v4 )
    goto LABEL_31;
  v5 = *((_QWORD *)a1 + 1);
  if ( *(_DWORD *)v5 == 2 )
  {
    *v4 = 2;
    v6 = ValidateCachedLogonInfo((struct _LiveSerializedValidationInfo *)v5, *(_DWORD *)a1);
    v34 = v6;
    if ( v6 < 0 )
      goto LABEL_34;
    v4[1] = *(_DWORD *)(v5 + 12);
    if ( *(_DWORD *)(v5 + 36) < 0x80u )
    {
      v7 = memcpy_s_0(v4 + 2, 0x40u, (const void *const)(v5 + *(unsigned int *)(v5 + 32)), *(unsigned int *)(v5 + 36));
      v6 = LiveMapHResultToNtStatus(v7 != 0 ? 0x8000FFFF : 0);
      v34 = v6;
      if ( v6 < 0 )
        goto LABEL_34;
      *(_WORD *)((char *)v4 + (*(_DWORD *)(v5 + 36) & 0xFFFFFFFE) + 8) = 0;
      v8 = *(unsigned int *)(v5 + 60);
      v9 = LiveAllocate(v8 + 2);
      Auto<_UnsignedProofOfPossessionTokenParameter *,LiveMemoryFunctor<_UnsignedProofOfPossessionTokenParameter *>,DummyContext>::Clear(v4 + 34);
      *((_QWORD *)v4 + 17) = v9;
      *((_QWORD *)v4 + 18) = v8;
      if ( v9 )
      {
        v10 = memcpy_s_0(
                v9,
                *(unsigned int *)(v5 + 60),
                (const void *const)(v5 + *(unsigned int *)(v5 + 56)),
                *(unsigned int *)(v5 + 60));
        v6 = LiveMapHResultToNtStatus(v10 != 0 ? 0x8000FFFF : 0);
        v34 = v6;
        if ( v6 < 0 )
          goto LABEL_34;
        *((_QWORD *)v4 + 18) = *(unsigned int *)(v5 + 60);
        v4[46] = *(_DWORD *)(v5 + 68);
        v11 = *(unsigned int *)(v5 + 68);
        v12 = LiveAllocate(v11);
        Auto<_UnsignedProofOfPossessionTokenParameter *,LiveMemoryFunctor<_UnsignedProofOfPossessionTokenParameter *>,DummyContext>::Clear(v4 + 40);
        *((_QWORD *)v4 + 20) = v12;
        *((_QWORD *)v4 + 21) = v11;
        if ( v12 )
        {
          v13 = memcpy_s_0(
                  v12,
                  *(unsigned int *)(v5 + 68),
                  (const void *const)(v5 + *(unsigned int *)(v5 + 64)),
                  *(unsigned int *)(v5 + 68));
          v6 = LiveMapHResultToNtStatus(v13 != 0 ? 0x8000FFFF : 0);
          v34 = v6;
          if ( v6 >= 0 )
          {
            *((_QWORD *)v4 + 21) = *(unsigned int *)(v5 + 68);
LABEL_30:
            v30 = 0;
            v31 = 0;
            *a2 = (struct MSACloudAPValidationInfo *)v4;
            v6 = v34;
            goto LABEL_34;
          }
          goto LABEL_34;
        }
      }
      goto LABEL_31;
    }
LABEL_32:
    v6 = -1073741811;
    goto LABEL_33;
  }
  if ( *(_DWORD *)v5 != 3 )
    goto LABEL_32;
  *v4 = 3;
  v14 = *((_QWORD *)a1 + 1);
  v6 = ValidateOpaqueInfo((struct _MSACloudAPSerializedValidationInfo *)v14, *(_DWORD *)a1);
  v34 = v6;
  if ( v6 < 0 )
    goto LABEL_34;
  v4[1] = *(_DWORD *)(v5 + 12);
  if ( *(_DWORD *)(v14 + 20) >= 0x80u )
    goto LABEL_32;
  v15 = memcpy_s_0(v4 + 2, 0x40u, (const void *const)(v14 + *(unsigned int *)(v14 + 16)), *(unsigned int *)(v14 + 20));
  v6 = LiveMapHResultToNtStatus(v15 != 0 ? 0x8000FFFF : 0);
  v34 = v6;
  if ( v6 < 0 )
    goto LABEL_34;
  *(_WORD *)((char *)v4 + (*(_DWORD *)(v14 + 20) & 0xFFFFFFFE) + 8) = 0;
  v16 = *(unsigned int *)(v14 + 28);
  v17 = LiveAllocate(v16 + 2);
  Auto<_UnsignedProofOfPossessionTokenParameter *,LiveMemoryFunctor<_UnsignedProofOfPossessionTokenParameter *>,DummyContext>::Clear(v4 + 34);
  *((_QWORD *)v4 + 17) = v17;
  *((_QWORD *)v4 + 18) = v16;
  if ( !v17 )
    goto LABEL_31;
  v18 = memcpy_s_0(
          v17,
          *(unsigned int *)(v14 + 28),
          (const void *const)(v14 + *(unsigned int *)(v14 + 24)),
          *(unsigned int *)(v14 + 28));
  v6 = LiveMapHResultToNtStatus(v18 != 0 ? 0x8000FFFF : 0);
  v34 = v6;
  if ( v6 < 0 )
    goto LABEL_34;
  *((_QWORD *)v4 + 18) = *(unsigned int *)(v14 + 28);
  v19 = *(_DWORD *)(v14 + 36);
  v4[46] = v19;
  if ( v19 )
  {
    v20 = *(unsigned int *)(v14 + 36);
    v21 = LiveAllocate(v20);
    Auto<_UnsignedProofOfPossessionTokenParameter *,LiveMemoryFunctor<_UnsignedProofOfPossessionTokenParameter *>,DummyContext>::Clear(v4 + 40);
    *((_QWORD *)v4 + 20) = v21;
    *((_QWORD *)v4 + 21) = v20;
    if ( v21 )
    {
      v22 = memcpy_s_0(
              v21,
              *(unsigned int *)(v14 + 36),
              (const void *const)(v14 + *(unsigned int *)(v14 + 32)),
              *(unsigned int *)(v14 + 36));
      v6 = LiveMapHResultToNtStatus(v22 != 0 ? 0x8000FFFF : 0);
      v34 = v6;
      if ( v6 < 0 )
        goto LABEL_34;
      *((_QWORD *)v4 + 21) = *(unsigned int *)(v14 + 36);
      goto LABEL_25;
    }
LABEL_31:
    v6 = -1073741670;
LABEL_33:
    v34 = v6;
    goto LABEL_34;
  }
LABEL_25:
  v4[54] = *(_DWORD *)(v14 + 44);
  v23 = *(unsigned int *)(v14 + 44);
  v24 = LiveAllocate(v23);
  Auto<_UnsignedProofOfPossessionTokenParameter *,LiveMemoryFunctor<_UnsignedProofOfPossessionTokenParameter *>,DummyContext>::Clear(v4 + 48);
  *((_QWORD *)v4 + 24) = v24;
  *((_QWORD *)v4 + 25) = v23;
  if ( !v24 )
    goto LABEL_31;
  v25 = memcpy_s_0(
          v24,
          *(unsigned int *)(v14 + 44),
          (const void *const)(v14 + *(unsigned int *)(v14 + 40)),
          *(unsigned int *)(v14 + 44));
  v6 = LiveMapHResultToNtStatus(v25 != 0 ? 0x8000FFFF : 0);
  v34 = v6;
  if ( v6 < 0 )
    goto LABEL_34;
  *((_QWORD *)v4 + 25) = *(unsigned int *)(v14 + 44);
  v26 = *(unsigned int *)(v14 + 52);
  v27 = LiveAllocate(v26);
  Auto<_UnsignedProofOfPossessionTokenParameter *,LiveMemoryFunctor<_UnsignedProofOfPossessionTokenParameter *>,DummyContext>::Clear(v4 + 56);
  *((_QWORD *)v4 + 28) = v27;
  *((_QWORD *)v4 + 29) = v26;
  if ( !v27 )
    goto LABEL_31;
  v28 = memcpy_s_0(
          v27,
          *(unsigned int *)(v14 + 52),
          (const void *const)(v14 + *(unsigned int *)(v14 + 48)),
          *(unsigned int *)(v14 + 52));
  v6 = LiveMapHResultToNtStatus(v28 != 0 ? 0x8000FFFF : 0);
  v34 = v6;
  if ( v6 >= 0 )
  {
    *((_QWORD *)v4 + 29) = *(unsigned int *)(v14 + 52);
    goto LABEL_30;
  }
LABEL_34:
  CTraceFuncW<long>::~CTraceFuncW<long>(v33);
  Auto<MSACloudAPValidationInfo *,ValidationInfoFunctor,DummyContext>::~Auto<MSACloudAPValidationInfo *,ValidationInfoFunctor,DummyContext>(&v30);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000e0f0  push    rbp
0x18000e0f2  push    rbx
0x18000e0f3  push    rsi
0x18000e0f4  push    rdi
0x18000e0f5  push    r12
0x18000e0f7  push    r13
0x18000e0f9  push    r14
0x18000e0fb  push    r15
0x18000e0fd  mov     rbp, rsp
0x18000e100  sub     rsp, 68h
0x18000e104  mov     r13, rdx
0x18000e107  mov     rbx, rcx
0x18000e10a  xor     r15d, r15d
0x18000e10d  mov     [rbp+arg_0], r15d
0x18000e111  mov     [rbp+var_48], r15
0x18000e115  mov     [rbp+var_38], r15
0x18000e119  mov     [rbp+var_40], r15
0x18000e11d  lea     rdx, aDeserializeopa; "DeserializeOpaqueBlob"
0x18000e124  mov     [rbp+var_30], rdx
0x18000e128  lea     rax, [rbp+arg_0]
0x18000e12c  mov     [rbp+var_28], rax
0x18000e130  mov     [rbp+var_20], r15
0x18000e134  mov     [rbp+var_18], r15
0x18000e138  xor     r9d, r9d; unsigned int
0x18000e13b  mov     r8d, 161h; char *
0x18000e141  lea     rcx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x18000e148  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18000e14d  nop
0x18000e14e  test    rbx, rbx
0x18000e151  jz      loc_18000E530
0x18000e157  cmp     [rbx+8], r15
0x18000e15b  jz      loc_18000E530
0x18000e161  cmp     dword ptr [rbx], 38h ; '8'
0x18000e164  jbe     loc_18000E530
0x18000e16a  test    r13, r13
0x18000e16d  jz      loc_18000E530
0x18000e173  mov     [r13+0], r15
0x18000e177  mov     ecx, 0F8h; unsigned __int64
0x18000e17c  call    ?LiveAllocate@@YAPEAX_K@Z; LiveAllocate(unsigned __int64)
0x18000e181  mov     rsi, rax
0x18000e184  lea     rcx, [rbp+var_48]
0x18000e188  call    ?Clear@?$Auto@PEAUMSACloudAPValidationInfo@@VValidationInfoFunctor@@VDummyContext@@@@QEAAXXZ; Auto<MSACloudAPValidationInfo *,ValidationInfoFunctor,DummyContext>::Clear(void)
0x18000e18d  mov     [rbp+var_48], rsi
0x18000e191  test    rsi, rsi
0x18000e194  jz      loc_18000E529
0x18000e19a  mov     r14, [rbx+8]
0x18000e19e  cmp     dword ptr [r14], 2
0x18000e1a2  jnz     loc_18000E2F8
0x18000e1a8  mov     dword ptr [rsi], 2
0x18000e1ae  mov     edx, [rbx]; unsigned int
0x18000e1b0  mov     rcx, r14; struct _LiveSerializedValidationInfo *
0x18000e1b3  call    ?ValidateCachedLogonInfo@@YAJPEAU_LiveSerializedValidationInfo@@K@Z; ValidateCachedLogonInfo(_LiveSerializedValidationInfo *,ulong)
0x18000e1b8  mov     ebx, eax
0x18000e1ba  mov     [rbp+arg_0], eax
0x18000e1bd  test    eax, eax
0x18000e1bf  js      loc_18000E538
0x18000e1c5  mov     eax, [r14+0Ch]
0x18000e1c9  mov     [rsi+4], eax
0x18000e1cc  cmp     dword ptr [r14+24h], 80h
0x18000e1d4  jnb     loc_18000E530
0x18000e1da  mov     r9d, [r14+24h]; SourceSize
0x18000e1de  mov     r8d, [r14+20h]
0x18000e1e2  add     r8, r14; Source
0x18000e1e5  lea     edx, [r15+40h]; DestinationSize
0x18000e1e9  lea     rcx, [rsi+8]; Destination
0x18000e1ed  call    memcpy_s_0
0x18000e1f2  neg     eax
0x18000e1f4  sbb     ecx, ecx
0x18000e1f6  mov     r12d, 8000FFFFh
0x18000e1fc  and     ecx, r12d; int
0x18000e1ff  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x18000e204  mov     ebx, eax
0x18000e206  mov     [rbp+arg_0], eax
0x18000e209  test    eax, eax
0x18000e20b  js      loc_18000E538
0x18000e211  mov     ecx, [r14+24h]
0x18000e215  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18000e219  mov     [rcx+rsi+8], r15w
0x18000e21f  lea     rdi, [rsi+88h]
0x18000e226  mov     ebx, [r14+3Ch]
0x18000e22a  lea     rcx, [rbx+2]; unsigned __int64
0x18000e22e  call    ?LiveAllocate@@YAPEAX_K@Z; LiveAllocate(unsigned __int64)
0x18000e233  mov     r15, rax
0x18000e236  mov     rcx, rdi
0x18000e239  call    ?Clear@?$Auto@PEAU_UnsignedProofOfPossessionTokenParameter@@V?$LiveMemoryFunctor@PEAU_UnsignedProofOfPossessionTokenParameter@@@@VDummyContext@@@@QEAAXXZ; Auto<_UnsignedProofOfPossessionTokenParameter *,LiveMemoryFunctor<_UnsignedProofOfPossessionTokenParameter *>,DummyContext>::Clear(void)
0x18000e23e  mov     [rdi], r15
0x18000e241  mov     [rdi+8], rbx
0x18000e245  test    r15, r15
0x18000e248  jz      loc_18000E529
0x18000e24e  mov     edx, [r14+3Ch]; DestinationSize
0x18000e252  mov     r8d, [r14+38h]
0x18000e256  add     r8, r14; Source
0x18000e259  mov     r9d, edx; SourceSize
0x18000e25c  mov     rcx, r15; Destination
0x18000e25f  call    memcpy_s_0
0x18000e264  neg     eax
0x18000e266  sbb     ecx, ecx
0x18000e268  and     ecx, r12d; int
0x18000e26b  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x18000e270  mov     ebx, eax
0x18000e272  mov     [rbp+arg_0], eax
0x18000e275  test    eax, eax
0x18000e277  js      loc_18000E538
0x18000e27d  mov     eax, [r14+3Ch]
0x18000e281  mov     [rdi+8], rax
0x18000e285  mov     eax, [r14+44h]
0x18000e289  mov     [rsi+0B8h], eax
0x18000e28f  lea     rdi, [rsi+0A0h]
0x18000e296  mov     ebx, [r14+44h]
0x18000e29a  mov     ecx, ebx; unsigned __int64
0x18000e29c  call    ?LiveAllocate@@YAPEAX_K@Z; LiveAllocate(unsigned __int64)
0x18000e2a1  mov     r15, rax
0x18000e2a4  mov     rcx, rdi
0x18000e2a7  call    ?Clear@?$Auto@PEAU_UnsignedProofOfPossessionTokenParameter@@V?$LiveMemoryFunctor@PEAU_UnsignedProofOfPossessionTokenParameter@@@@VDummyContext@@@@QEAAXXZ; Auto<_UnsignedProofOfPossessionTokenParameter *,LiveMemoryFunctor<_UnsignedProofOfPossessionTokenParameter *>,DummyContext>::Clear(void)
0x18000e2ac  mov     [rdi], r15
0x18000e2af  mov     [rdi+8], rbx
0x18000e2b3  test    r15, r15
0x18000e2b6  jz      loc_18000E529
0x18000e2bc  mov     edx, [r14+44h]; DestinationSize
0x18000e2c0  mov     r8d, [r14+40h]
0x18000e2c4  add     r8, r14; Source
0x18000e2c7  mov     r9d, edx; SourceSize
0x18000e2ca  mov     rcx, r15; Destination
0x18000e2cd  call    memcpy_s_0
0x18000e2d2  neg     eax
0x18000e2d4  sbb     ecx, ecx
0x18000e2d6  and     ecx, r12d; int
0x18000e2d9  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x18000e2de  mov     ebx, eax
0x18000e2e0  mov     [rbp+arg_0], eax
0x18000e2e3  test    eax, eax
0x18000e2e5  js      loc_18000E538
0x18000e2eb  mov     eax, [r14+44h]
0x18000e2ef  mov     [rdi+8], rax
0x18000e2f3  jmp     loc_18000E510
0x18000e2f8  cmp     dword ptr [r14], 3
0x18000e2fc  jnz     loc_18000E530
0x18000e302  mov     dword ptr [rsi], 3
0x18000e308  mov     rdi, [rbx+8]
0x18000e30c  mov     edx, [rbx]; unsigned int
0x18000e30e  mov     rcx, rdi; struct _MSACloudAPSerializedValidationInfo *
0x18000e311  call    ?ValidateOpaqueInfo@@YAJPEAU_MSACloudAPSerializedValidationInfo@@K@Z; ValidateOpaqueInfo(_MSACloudAPSerializedValidationInfo *,ulong)
0x18000e316  mov     ebx, eax
0x18000e318  mov     [rbp+arg_0], eax
0x18000e31b  test    eax, eax
0x18000e31d  js      loc_18000E538
0x18000e323  mov     eax, [r14+0Ch]
0x18000e327  mov     [rsi+4], eax
0x18000e32a  cmp     dword ptr [rdi+14h], 80h
0x18000e331  jnb     loc_18000E530
0x18000e337  mov     r9d, [rdi+14h]; SourceSize
0x18000e33b  mov     r8d, [rdi+10h]
0x18000e33f  add     r8, rdi; Source
0x18000e342  mov     edx, 40h ; '@'; DestinationSize
0x18000e347  lea     rcx, [rsi+8]; Destination
0x18000e34b  call    memcpy_s_0
0x18000e350  neg     eax
0x18000e352  sbb     ecx, ecx
0x18000e354  mov     r12d, 8000FFFFh
0x18000e35a  and     ecx, r12d; int
0x18000e35d  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x18000e362  mov     ebx, eax
0x18000e364  mov     [rbp+arg_0], eax
0x18000e367  test    eax, eax
0x18000e369  js      loc_18000E538
0x18000e36f  mov     ecx, [rdi+14h]
0x18000e372  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18000e376  mov     [rcx+rsi+8], r15w
0x18000e37c  lea     r14, [rsi+88h]
0x18000e383  mov     ebx, [rdi+1Ch]
0x18000e386  lea     rcx, [rbx+2]; unsigned __int64
0x18000e38a  call    ?LiveAllocate@@YAPEAX_K@Z; LiveAllocate(unsigned __int64)
0x18000e38f  mov     r15, rax
0x18000e392  mov     rcx, r14
0x18000e395  call    ?Clear@?$Auto@PEAU_UnsignedProofOfPossessionTokenParameter@@V?$LiveMemoryFunctor@PEAU_UnsignedProofOfPossessionTokenParameter@@@@VDummyContext@@@@QEAAXXZ; Auto<_UnsignedProofOfPossessionTokenParameter *,LiveMemoryFunctor<_UnsignedProofOfPossessionTokenParameter *>,DummyContext>::Clear(void)
0x18000e39a  mov     [r14], r15
0x18000e39d  mov     [r14+8], rbx
0x18000e3a1  test    r15, r15
0x18000e3a4  jz      loc_18000E529
0x18000e3aa  mov     edx, [rdi+1Ch]; DestinationSize
0x18000e3ad  mov     r8d, [rdi+18h]
0x18000e3b1  add     r8, rdi; Source
0x18000e3b4  mov     r9d, edx; SourceSize
0x18000e3b7  mov     rcx, r15; Destination
0x18000e3ba  call    memcpy_s_0
0x18000e3bf  neg     eax
0x18000e3c1  sbb     ecx, ecx
0x18000e3c3  and     ecx, r12d; int
0x18000e3c6  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x18000e3cb  mov     ebx, eax
0x18000e3cd  mov     [rbp+arg_0], eax
0x18000e3d0  test    eax, eax
0x18000e3d2  js      loc_18000E538
0x18000e3d8  mov     eax, [rdi+1Ch]
0x18000e3db  mov     [r14+8], rax
0x18000e3df  mov     eax, [rdi+24h]
0x18000e3e2  mov     [rsi+0B8h], eax
0x18000e3e8  test    eax, eax
0x18000e3ea  jz      short loc_18000E44D
0x18000e3ec  lea     r14, [rsi+0A0h]
0x18000e3f3  mov     ebx, [rdi+24h]
0x18000e3f6  mov     ecx, ebx; unsigned __int64
0x18000e3f8  call    ?LiveAllocate@@YAPEAX_K@Z; LiveAllocate(unsigned __int64)
0x18000e3fd  mov     r15, rax
0x18000e400  mov     rcx, r14
0x18000e403  call    ?Clear@?$Auto@PEAU_UnsignedProofOfPossessionTokenParameter@@V?$LiveMemoryFunctor@PEAU_UnsignedProofOfPossessionTokenParameter@@@@VDummyContext@@@@QEAAXXZ; Auto<_UnsignedProofOfPossessionTokenParameter *,LiveMemoryFunctor<_UnsignedProofOfPossessionTokenParameter *>,DummyContext>::Clear(void)
0x18000e408  mov     [r14], r15
0x18000e40b  mov     [r14+8], rbx
0x18000e40f  test    r15, r15
0x18000e412  jz      loc_18000E529
0x18000e418  mov     edx, [rdi+24h]; DestinationSize
0x18000e41b  mov     r8d, [rdi+20h]
0x18000e41f  add     r8, rdi; Source
0x18000e422  mov     r9d, edx; SourceSize
0x18000e425  mov     rcx, r15; Destination
0x18000e428  call    memcpy_s_0
0x18000e42d  neg     eax
0x18000e42f  sbb     ecx, ecx
0x18000e431  and     ecx, r12d; int
0x18000e434  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x18000e439  mov     ebx, eax
0x18000e43b  mov     [rbp+arg_0], eax
0x18000e43e  test    eax, eax
0x18000e440  js      loc_18000E538
0x18000e446  mov     eax, [rdi+24h]
0x18000e449  mov     [r14+8], rax
0x18000e44d  mov     eax, [rdi+2Ch]
0x18000e450  mov     [rsi+0D8h], eax
0x18000e456  lea     r14, [rsi+0C0h]
0x18000e45d  mov     ebx, [rdi+2Ch]
0x18000e460  mov     ecx, ebx; unsigned __int64
0x18000e462  call    ?LiveAllocate@@YAPEAX_K@Z; LiveAllocate(unsigned __int64)
0x18000e467  mov     r15, rax
0x18000e46a  mov     rcx, r14
0x18000e46d  call    ?Clear@?$Auto@PEAU_UnsignedProofOfPossessionTokenParameter@@V?$LiveMemoryFunctor@PEAU_UnsignedProofOfPossessionTokenParameter@@@@VDummyContext@@@@QEAAXXZ; Auto<_UnsignedProofOfPossessionTokenParameter *,LiveMemoryFunctor<_UnsignedProofOfPossessionTokenParameter *>,DummyContext>::Clear(void)
0x18000e472  mov     [r14], r15
0x18000e475  mov     [r14+8], rbx
0x18000e479  test    r15, r15
0x18000e47c  jz      loc_18000E529
0x18000e482  mov     edx, [rdi+2Ch]; DestinationSize
0x18000e485  mov     r8d, [rdi+28h]
0x18000e489  add     r8, rdi; Source
0x18000e48c  mov     r9d, edx; SourceSize
0x18000e48f  mov     rcx, r15; Destination
0x18000e492  call    memcpy_s_0
0x18000e497  neg     eax
0x18000e499  sbb     ecx, ecx
0x18000e49b  and     ecx, r12d; int
0x18000e49e  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x18000e4a3  mov     ebx, eax
0x18000e4a5  mov     [rbp+arg_0], eax
0x18000e4a8  test    eax, eax
0x18000e4aa  js      loc_18000E538
0x18000e4b0  mov     eax, [rdi+2Ch]
0x18000e4b3  mov     [r14+8], rax
0x18000e4b7  lea     r14, [rsi+0E0h]
0x18000e4be  mov     ebx, [rdi+34h]
0x18000e4c1  mov     ecx, ebx; unsigned __int64
0x18000e4c3  call    ?LiveAllocate@@YAPEAX_K@Z; LiveAllocate(unsigned __int64)
0x18000e4c8  mov     r15, rax
0x18000e4cb  mov     rcx, r14
0x18000e4ce  call    ?Clear@?$Auto@PEAU_UnsignedProofOfPossessionTokenParameter@@V?$LiveMemoryFunctor@PEAU_UnsignedProofOfPossessionTokenParameter@@@@VDummyContext@@@@QEAAXXZ; Auto<_UnsignedProofOfPossessionTokenParameter *,LiveMemoryFunctor<_UnsignedProofOfPossessionTokenParameter *>,DummyContext>::Clear(void)
0x18000e4d3  mov     [r14], r15
0x18000e4d6  mov     [r14+8], rbx
0x18000e4da  test    r15, r15
0x18000e4dd  jz      short loc_18000E529
0x18000e4df  mov     edx, [rdi+34h]; DestinationSize
0x18000e4e2  mov     r8d, [rdi+30h]
0x18000e4e6  add     r8, rdi; Source
0x18000e4e9  mov     r9d, edx; SourceSize
0x18000e4ec  mov     rcx, r15; Destination
0x18000e4ef  call    memcpy_s_0
0x18000e4f4  neg     eax
0x18000e4f6  sbb     ecx, ecx
0x18000e4f8  and     ecx, r12d; int
0x18000e4fb  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x18000e500  mov     ebx, eax
0x18000e502  mov     [rbp+arg_0], eax
0x18000e505  test    eax, eax
0x18000e507  js      short loc_18000E538
0x18000e509  mov     eax, [rdi+34h]
0x18000e50c  mov     [r14+8], rax
0x18000e510  mov     [rbp+var_48], 0
0x18000e518  mov     [rbp+var_40], 0
0x18000e520  mov     [r13+0], rsi
0x18000e524  mov     ebx, [rbp+arg_0]
0x18000e527  jmp     short loc_18000E538
0x18000e529  mov     ebx, 0C000009Ah
0x18000e52e  jmp     short loc_18000E535
0x18000e530  mov     ebx, 0C000000Dh
0x18000e535  mov     [rbp+arg_0], ebx
0x18000e538  lea     rcx, [rbp+var_30]
0x18000e53c  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18000e541  nop
0x18000e542  lea     rcx, [rbp+var_48]
0x18000e546  call    ??1?$Auto@PEAUMSACloudAPValidationInfo@@VValidationInfoFunctor@@VDummyContext@@@@QEAA@XZ; Auto<MSACloudAPValidationInfo *,ValidationInfoFunctor,DummyContext>::~Auto<MSACloudAPValidationInfo *,ValidationInfoFunctor,DummyContext>(void)
0x18000e54b  mov     eax, ebx
0x18000e54d  add     rsp, 68h
0x18000e551  pop     r15
0x18000e553  pop     r14
  ... truncated ...
```
