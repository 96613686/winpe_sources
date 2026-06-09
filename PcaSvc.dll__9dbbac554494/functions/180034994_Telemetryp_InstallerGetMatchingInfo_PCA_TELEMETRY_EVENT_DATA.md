# Telemetryp_InstallerGetMatchingInfo(_PCA_TELEMETRY_EVENT_DATA *)

- ea: `0x180034994`
- end: `0x180034eb1`
- name: `?Telemetryp_InstallerGetMatchingInfo@@YAKPEAU_PCA_TELEMETRY_EVENT_DATA@@@Z`
- size: `1309`
- prototype: `unsigned int __fastcall(struct _PCA_TELEMETRY_EVENT_DATA *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x18001e6ec`

## callees

- `0x18000c018`
- `0x18000cb44`
- `0x18000dcc0`
- `0x180012920`
- `0x180013334`
- `0x1800133c0`
- `0x180034994`
- `0x180034eb8`
- `0x18004df9c`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180034e49`
- `msvcrt!wcscat_s` at `0x180034e72`
- `msvcrt!wcscat_s` at `0x180034e49`
- `msvcrt!wcscat_s` at `0x180034e72`
- `msvcrt!wcscpy_s` at `0x180034e36`
- `msvcrt!wcscpy_s` at `0x180034e36`
- `msvcrt!_wcsicmp` at `0x1800349e6`
- `msvcrt!_wcsicmp` at `0x180034a8d`
- `msvcrt!_wcsicmp` at `0x180034b0a`
- `msvcrt!_wcsicmp` at `0x180034b87`
- `msvcrt!_wcsicmp` at `0x180034c1e`
- `msvcrt!_wcsicmp` at `0x1800349e6`
- `msvcrt!_wcsicmp` at `0x180034a8d`
- `msvcrt!_wcsicmp` at `0x180034b0a`
- `msvcrt!_wcsicmp` at `0x180034b87`
- `msvcrt!_wcsicmp` at `0x180034c1e`

## string_xrefs

- `0x180034bce`: `Telemetryp_InstallerGetMatchingInfo`
- `0x180034c60`: `Telemetryp_InstallerGetMatchingInfo`
- `0x180034e93`: `Telemetryp_InstallerGetMatchingInfo`
- `0x180034c98`: `InstallShield_`
- `0x180034ce9`: `InstallShield_`
- `0x180034d5f`: `InstallShield_`
- `0x180034e4f`: `MsiPackageCode`
- `0x180034df5`: `MsiProductCode`
- `0x180034a2a`: `Failed to copy name [%d]`

## pseudocode

```c
__int64 __fastcall Telemetryp_InstallerGetMatchingInfo(struct _PCA_TELEMETRY_EVENT_DATA *a1)
{
  unsigned __int64 v1; // rbx
  unsigned __int64 *v2; // rdi
  const wchar_t **v4; // rax
  const wchar_t *Value; // rax
  size_t *v6; // r8
  char *v7; // rbp
  unsigned int v8; // ebx
  unsigned __int64 i; // rbx
  const wchar_t **v10; // rax
  const unsigned __int16 *v11; // rax
  unsigned int v12; // eax
  unsigned __int64 j; // rbx
  const wchar_t **v14; // rax
  const unsigned __int16 *v15; // rax
  unsigned int v16; // eax
  unsigned __int64 k; // rbx
  const wchar_t **v18; // rax
  const unsigned __int16 *v19; // rax
  unsigned int v20; // eax
  unsigned __int64 m; // rbp
  const wchar_t **v22; // rax
  const unsigned __int16 *v23; // rax
  unsigned int v24; // eax
  wchar_t *v25; // rsi
  const unsigned __int16 *v26; // rax
  const unsigned __int16 *v27; // rsi
  const unsigned __int16 *v28; // rax
  unsigned int v29; // eax
  const unsigned __int16 *v30; // rax
  unsigned int v31; // eax
  wchar_t *v32; // rbp
  const wchar_t *v33; // rax
  const wchar_t *v34; // rax
  size_t v36; // [rsp+20h] [rbp-48h]
  __int64 v37; // [rsp+20h] [rbp-48h]

  v1 = 0;
  v2 = (unsigned __int64 *)((char *)a1 + 4072);
  while ( 1 )
  {
    if ( v1 >= v2[2] )
      goto LABEL_77;
    if ( !is_mul_ok(v2[1], v1) || (v4 = (const wchar_t **)(v2[5] + v2[1] * v1), (unsigned __int64)v4 < v2[5]) )
      v4 = 0;
    if ( !_wcsicmp(*v4, L"LongName") )
      break;
    ++v1;
  }
  Value = RtlNameValueArray::GetValue((RtlNameValueArray *)v2, v1);
  if ( !Value )
  {
LABEL_77:
    v8 = 2;
    AslLogCallPrintf(
      1,
      (unsigned int)"Telemetryp_InstallerGetMatchingInfo",
      1353,
      (unsigned int)"Failed to get ExeName attribute [%d]",
      2);
    return v8;
  }
  v7 = (char *)a1 + 64;
  if ( StringCopyWorkerW((STRSAFE_LPWSTR)a1 + 32, 0x104u, v6, Value, v36) < 0 )
  {
    v8 = 122;
    LODWORD(v37) = 122;
    AslLogCallPrintf(
      1,
      (unsigned int)"Telemetryp_InstallerGetMatchingInfo",
      1348,
      (unsigned int)"Failed to copy name [%d]",
      v37);
    return v8;
  }
  if ( *((_DWORD *)a1 + 1296) == 1 )
  {
    *((_DWORD *)a1 + 276) = -1;
    *((_DWORD *)a1 + 277) = -1;
    *((_QWORD *)a1 + 499) |= 0x40000000uLL;
    v32 = (wchar_t *)((char *)a1 + 584);
    *((_WORD *)a1 + 292) = 0;
    v33 = RtlNameValueArray::GetValue((RtlNameValueArray *)v2, 0, (wchar_t *)L"MsiProductCode");
    if ( v33 )
    {
      wcscpy_s(v32, 0x104u, v33);
      wcscat_s(v32, 0x104u, L";");
    }
    v34 = RtlNameValueArray::GetValue((RtlNameValueArray *)v2, 0, (wchar_t *)L"MsiPackageCode");
    if ( v34 )
      wcscat_s(v32, 0x104u, v34);
    return 0;
  }
  if ( *((_DWORD *)a1 + 1296) != 2 )
  {
    for ( i = 0; i < v2[2]; ++i )
    {
      if ( !is_mul_ok(v2[1], i) || (v10 = (const wchar_t **)(v2[5] + v2[1] * i), (unsigned __int64)v10 < v2[5]) )
        v10 = 0;
      if ( !_wcsicmp(*v10, L"Size") )
      {
        v11 = RtlNameValueArray::GetValue((RtlNameValueArray *)v2, i);
        if ( v11 )
        {
          v12 = PcaUtilityStringToUInt32((unsigned int *)a1 + 276, v11);
          v8 = v12;
          if ( v12 )
          {
            LODWORD(v37) = v12;
            AslLogCallPrintf(
              1,
              (unsigned int)"Telemetryp_InstallerGetMatchingInfo",
              1487,
              (unsigned int)"Failed to assign Size [%d]",
              v37);
            return v8;
          }
        }
        break;
      }
    }
    for ( j = 0; j < v2[2]; ++j )
    {
      if ( !is_mul_ok(v2[1], j) || (v14 = (const wchar_t **)(v2[5] + v2[1] * j), (unsigned __int64)v14 < v2[5]) )
        v14 = 0;
      if ( !_wcsicmp(*v14, L"CrcChecksum") )
      {
        v15 = RtlNameValueArray::GetValue((RtlNameValueArray *)v2, j);
        if ( v15 )
        {
          v16 = PcaUtilityStringToUInt32((unsigned int *)a1 + 277, v15);
          v8 = v16;
          if ( v16 )
          {
            LODWORD(v37) = v16;
            AslLogCallPrintf(
              1,
              (unsigned int)"Telemetryp_InstallerGetMatchingInfo",
              1500,
              (unsigned int)"Failed to assign CrcChecksum [%d]",
              v37);
            return v8;
          }
        }
        break;
      }
    }
    for ( k = 0; k < v2[2]; ++k )
    {
      if ( !is_mul_ok(v2[1], k) || (v18 = (const wchar_t **)(v2[5] + v2[1] * k), (unsigned __int64)v18 < v2[5]) )
        v18 = 0;
      if ( !_wcsicmp(*v18, L"PeChecksum") )
      {
        v19 = RtlNameValueArray::GetValue((RtlNameValueArray *)v2, k);
        goto LABEL_42;
      }
    }
    v19 = 0;
LABEL_42:
    v20 = PcaUtilityStringToUInt32((unsigned int *)a1 + 280, v19);
    if ( v20 )
    {
      LODWORD(v37) = v20;
      AslLogCallPrintf(
        2,
        (unsigned int)"Telemetryp_InstallerGetMatchingInfo",
        1512,
        (unsigned int)"Failed to assign PeChecksum [%d]",
        v37);
      *((_BYTE *)a1 + 1124) &= ~2u;
    }
    else
    {
      *((_BYTE *)a1 + 1124) |= 2u;
    }
    for ( m = 0; m < v2[2]; ++m )
    {
      if ( !is_mul_ok(v2[1], m) || (v22 = (const wchar_t **)(v2[5] + v2[1] * m), (unsigned __int64)v22 < v2[5]) )
        v22 = 0;
      if ( !_wcsicmp(*v22, L"BinFileVersion") )
      {
        v23 = RtlNameValueArray::GetValue((RtlNameValueArray *)v2, m);
        goto LABEL_54;
      }
    }
    v23 = 0;
LABEL_54:
    v24 = PcaUtilityVersionStringToUInt64((unsigned __int64 *)a1 + 139, v23);
    if ( v24 )
    {
      LODWORD(v37) = v24;
      AslLogCallPrintf(
        2,
        (unsigned int)"Telemetryp_InstallerGetMatchingInfo",
        1525,
        (unsigned int)"Failed to assign BinFileVersion [%d]",
        v37);
      *((_BYTE *)a1 + 1124) &= ~1u;
    }
    else
    {
      *((_BYTE *)a1 + 1124) |= 1u;
    }
    return 0;
  }
  *((_WORD *)a1 + 292) = 0;
  v25 = 0;
  v26 = RtlNameValueArray::GetValue((RtlNameValueArray *)v2, (wchar_t *)L"InstallShield_", (wchar_t *)L"Name");
  if ( !v26 )
  {
LABEL_67:
    v28 = RtlNameValueArray::GetValue((RtlNameValueArray *)v2, v25, (wchar_t *)L"Size");
    if ( v28 )
    {
      v29 = PcaUtilityStringToUInt32((unsigned int *)v7 + 260, v28);
      v8 = v29;
      if ( v29 )
      {
        LODWORD(v37) = v29;
        AslLogCallPrintf(
          1,
          (unsigned int)"Telemetryp_InstallerGetMatchingInfo",
          1453,
          (unsigned int)"Failed to assign Size [%d]",
          v37);
        return v8;
      }
    }
    v30 = RtlNameValueArray::GetValue((RtlNameValueArray *)v2, v25, (wchar_t *)L"CrcChecksum");
    if ( v30 )
    {
      v31 = PcaUtilityStringToUInt32((unsigned int *)v7 + 261, v30);
      v8 = v31;
      if ( v31 )
      {
        LODWORD(v37) = v31;
        AslLogCallPrintf(
          1,
          (unsigned int)"Telemetryp_InstallerGetMatchingInfo",
          1466,
          (unsigned int)"Failed to assign CrcChecksum [%d]",
          v37);
        return v8;
      }
    }
    return 0;
  }
  if ( (int)StringCchCopyW((unsigned __int16 *)v7 + 260, 0x104u, v26) >= 0 )
  {
    v27 = RtlNameValueArray::GetValue((RtlNameValueArray *)v2, (wchar_t *)L"InstallShield_", (wchar_t *)L"LongName");
    if ( v27 )
    {
      if ( StringCchCatW((unsigned __int16 *)v7 + 260, 0x104u, L";") < 0 )
      {
        v8 = 122;
        LODWORD(v37) = 122;
        AslLogCallPrintf(
          1,
          (unsigned int)"Telemetryp_InstallerGetMatchingInfo",
          1429,
          (unsigned int)"Failed to cat alt name [%d]",
          v37);
        return v8;
      }
      if ( StringCchCatW((unsigned __int16 *)v7 + 260, 0x104u, v27) < 0 )
      {
        v8 = 122;
        LODWORD(v37) = 122;
        AslLogCallPrintf(
          1,
          (unsigned int)"Telemetryp_InstallerGetMatchingInfo",
          1437,
          (unsigned int)"Failed to cat alt name [%d]",
          v37);
        return v8;
      }
    }
    v25 = (wchar_t *)L"InstallShield_";
    goto LABEL_67;
  }
  v8 = 122;
  LODWORD(v37) = 122;
  AslLogCallPrintf(
    1,
    (unsigned int)"Telemetryp_InstallerGetMatchingInfo",
    1418,
    (unsigned int)"Failed to set alt name [%d]",
    v37);
  return v8;
}

```

## disassembly

```asm
0x180034994  push    rbx
0x180034996  push    rbp
0x180034997  push    rsi
0x180034998  push    rdi
0x180034999  push    r12
0x18003499b  push    r15
0x18003499d  sub     rsp, 38h
0x1800349a1  xor     ebx, ebx
0x1800349a3  lea     rdi, [rcx+0FE8h]
0x1800349aa  mov     rsi, rcx
0x1800349ad  lea     r15d, [rbx+1]
0x1800349b1  cmp     rbx, [rdi+10h]
0x1800349b5  jnb     loc_180034E7D
0x1800349bb  mov     rax, rbx
0x1800349be  mov     [rsp+68h+arg_0], 0
0x1800349c7  mul     qword ptr [rdi+8]
0x1800349cb  test    rdx, rdx
0x1800349ce  jnz     short loc_1800349DA
0x1800349d0  add     rax, [rdi+28h]
0x1800349d4  cmp     rax, [rdi+28h]
0x1800349d8  jnb     short loc_1800349DC
0x1800349da  xor     eax, eax
0x1800349dc  mov     rcx, [rax]; String1
0x1800349df  lea     rdx, aLongname; "LongName"
0x1800349e6  call    cs:__imp__wcsicmp
0x1800349ec  test    eax, eax
0x1800349ee  jz      short loc_1800349F5
0x1800349f0  add     rbx, r15
0x1800349f3  jmp     short loc_1800349B1
0x1800349f5  mov     rdx, rbx; unsigned __int64
0x1800349f8  mov     rcx, rdi; this
0x1800349fb  call    ?GetValue@RtlNameValueArray@@QEBAPEBG_K@Z; RtlNameValueArray::GetValue(unsigned __int64)
0x180034a00  test    rax, rax
0x180034a03  jz      loc_180034E7D
0x180034a09  lea     rbp, [rsi+40h]
0x180034a0d  mov     r12d, 104h
0x180034a13  mov     edx, r12d; cchDest
0x180034a16  mov     rcx, rbp; pszDest
0x180034a19  mov     r9, rax; pszSrc
0x180034a1c  call    StringCopyWorkerW
0x180034a21  test    eax, eax
0x180034a23  jns     short loc_180034A42
0x180034a25  mov     eax, 7Ah ; 'z'
0x180034a2a  lea     r9, aFailedToCopyNa; "Failed to copy name [%d]"
0x180034a31  mov     ebx, eax
0x180034a33  mov     dword ptr [rsp+68h+var_48], eax
0x180034a37  mov     r8d, 544h
0x180034a3d  jmp     loc_180034E93
0x180034a42  mov     ecx, [rsi+1440h]
0x180034a48  sub     ecx, r15d
0x180034a4b  jz      loc_180034DF2
0x180034a51  cmp     ecx, r15d
0x180034a54  jz      loc_180034C85
0x180034a5a  xor     ebx, ebx
0x180034a5c  cmp     rbx, [rdi+10h]
0x180034a60  jnb     short loc_180034AD7
0x180034a62  mov     rax, rbx
0x180034a65  mov     [rsp+68h+arg_0], 0
0x180034a6e  mul     qword ptr [rdi+8]
0x180034a72  test    rdx, rdx
0x180034a75  jnz     short loc_180034A81
0x180034a77  add     rax, [rdi+28h]
0x180034a7b  cmp     rax, [rdi+28h]
0x180034a7f  jnb     short loc_180034A83
0x180034a81  xor     eax, eax
0x180034a83  mov     rcx, [rax]; String1
0x180034a86  lea     rdx, aSize; "Size"
0x180034a8d  call    cs:__imp__wcsicmp
0x180034a93  test    eax, eax
0x180034a95  jz      short loc_180034A9C
0x180034a97  add     rbx, r15
0x180034a9a  jmp     short loc_180034A5C
0x180034a9c  mov     rdx, rbx; unsigned __int64
0x180034a9f  mov     rcx, rdi; this
0x180034aa2  call    ?GetValue@RtlNameValueArray@@QEBAPEBG_K@Z; RtlNameValueArray::GetValue(unsigned __int64)
0x180034aa7  test    rax, rax
0x180034aaa  jz      short loc_180034AD7
0x180034aac  lea     rcx, [rsi+450h]; unsigned int *
0x180034ab3  mov     rdx, rax; unsigned __int16 *
0x180034ab6  call    ?PcaUtilityStringToUInt32@@YAKPEAIPEBG@Z; PcaUtilityStringToUInt32(uint *,ushort const *)
0x180034abb  mov     ebx, eax
0x180034abd  test    eax, eax
0x180034abf  jz      short loc_180034AD7
0x180034ac1  mov     dword ptr [rsp+68h+var_48], eax
0x180034ac5  lea     r9, aFailedToAssign_2; "Failed to assign Size [%d]"
0x180034acc  mov     r8d, 5CFh
0x180034ad2  jmp     loc_180034E93
0x180034ad7  xor     ebx, ebx
0x180034ad9  cmp     rbx, [rdi+10h]
0x180034add  jnb     short loc_180034B54
0x180034adf  mov     rax, rbx
0x180034ae2  mov     [rsp+68h+arg_0], 0
0x180034aeb  mul     qword ptr [rdi+8]
0x180034aef  test    rdx, rdx
0x180034af2  jnz     short loc_180034AFE
0x180034af4  add     rax, [rdi+28h]
0x180034af8  cmp     rax, [rdi+28h]
0x180034afc  jnb     short loc_180034B00
0x180034afe  xor     eax, eax
0x180034b00  mov     rcx, [rax]; String1
0x180034b03  lea     rdx, aCrcchecksum; "CrcChecksum"
0x180034b0a  call    cs:__imp__wcsicmp
0x180034b10  test    eax, eax
0x180034b12  jz      short loc_180034B19
0x180034b14  add     rbx, r15
0x180034b17  jmp     short loc_180034AD9
0x180034b19  mov     rdx, rbx; unsigned __int64
0x180034b1c  mov     rcx, rdi; this
0x180034b1f  call    ?GetValue@RtlNameValueArray@@QEBAPEBG_K@Z; RtlNameValueArray::GetValue(unsigned __int64)
0x180034b24  test    rax, rax
0x180034b27  jz      short loc_180034B54
0x180034b29  lea     rcx, [rsi+454h]; unsigned int *
0x180034b30  mov     rdx, rax; unsigned __int16 *
0x180034b33  call    ?PcaUtilityStringToUInt32@@YAKPEAIPEBG@Z; PcaUtilityStringToUInt32(uint *,ushort const *)
0x180034b38  mov     ebx, eax
0x180034b3a  test    eax, eax
0x180034b3c  jz      short loc_180034B54
0x180034b3e  mov     dword ptr [rsp+68h+var_48], eax
0x180034b42  lea     r9, aFailedToAssign_0; "Failed to assign CrcChecksum [%d]"
0x180034b49  mov     r8d, 5DCh
0x180034b4f  jmp     loc_180034E93
0x180034b54  xor     ebx, ebx
0x180034b56  cmp     rbx, [rdi+10h]
0x180034b5a  jnb     short loc_180034BA3
0x180034b5c  mov     rax, rbx
0x180034b5f  mov     [rsp+68h+arg_0], 0
0x180034b68  mul     qword ptr [rdi+8]
0x180034b6c  test    rdx, rdx
0x180034b6f  jnz     short loc_180034B7B
0x180034b71  add     rax, [rdi+28h]
0x180034b75  cmp     rax, [rdi+28h]
0x180034b79  jnb     short loc_180034B7D
0x180034b7b  xor     eax, eax
0x180034b7d  mov     rcx, [rax]; String1
0x180034b80  lea     rdx, aPechecksum; "PeChecksum"
0x180034b87  call    cs:__imp__wcsicmp
0x180034b8d  test    eax, eax
0x180034b8f  jz      short loc_180034B96
0x180034b91  add     rbx, r15
0x180034b94  jmp     short loc_180034B56
0x180034b96  mov     rdx, rbx; unsigned __int64
0x180034b99  mov     rcx, rdi; this
0x180034b9c  call    ?GetValue@RtlNameValueArray@@QEBAPEBG_K@Z; RtlNameValueArray::GetValue(unsigned __int64)
0x180034ba1  jmp     short loc_180034BA5
0x180034ba3  xor     eax, eax
0x180034ba5  lea     rcx, [rsi+460h]; unsigned int *
0x180034bac  mov     rdx, rax; unsigned __int16 *
0x180034baf  call    ?PcaUtilityStringToUInt32@@YAKPEAIPEBG@Z; PcaUtilityStringToUInt32(uint *,ushort const *)
0x180034bb4  mov     ebx, 2
0x180034bb9  test    eax, eax
0x180034bbb  jz      short loc_180034BE5
0x180034bbd  lea     r9, aFailedToAssign; "Failed to assign PeChecksum [%d]"
0x180034bc4  mov     dword ptr [rsp+68h+var_48], eax
0x180034bc8  mov     r8d, 5E8h
0x180034bce  lea     rdx, aTelemetrypInst_0; "Telemetryp_InstallerGetMatchingInfo"
0x180034bd5  mov     ecx, ebx
0x180034bd7  call    AslLogCallPrintf
0x180034bdc  and     byte ptr [rsi+464h], 0FDh
0x180034be3  jmp     short loc_180034BEB
0x180034be5  or      [rsi+464h], bl
0x180034beb  xor     ebp, ebp
0x180034bed  cmp     rbp, [rdi+10h]
0x180034bf1  jnb     short loc_180034C3A
0x180034bf3  mov     rax, rbp
0x180034bf6  mov     [rsp+68h+arg_0], 0
0x180034bff  mul     qword ptr [rdi+8]
0x180034c03  test    rdx, rdx
0x180034c06  jnz     short loc_180034C12
0x180034c08  add     rax, [rdi+28h]
0x180034c0c  cmp     rax, [rdi+28h]
0x180034c10  jnb     short loc_180034C14
0x180034c12  xor     eax, eax
0x180034c14  mov     rcx, [rax]; String1
0x180034c17  lea     rdx, aBinfileversion; "BinFileVersion"
0x180034c1e  call    cs:__imp__wcsicmp
0x180034c24  test    eax, eax
0x180034c26  jz      short loc_180034C2D
0x180034c28  add     rbp, r15
0x180034c2b  jmp     short loc_180034BED
0x180034c2d  mov     rdx, rbp; unsigned __int64
0x180034c30  mov     rcx, rdi; this
0x180034c33  call    ?GetValue@RtlNameValueArray@@QEBAPEBG_K@Z; RtlNameValueArray::GetValue(unsigned __int64)
0x180034c38  jmp     short loc_180034C3C
0x180034c3a  xor     eax, eax
0x180034c3c  lea     rcx, [rsi+458h]; unsigned __int64 *
0x180034c43  mov     rdx, rax; unsigned __int16 *
0x180034c46  call    ?PcaUtilityVersionStringToUInt64@@YAKPEA_KPEBG@Z; PcaUtilityVersionStringToUInt64(unsigned __int64 *,ushort const *)
0x180034c4b  test    eax, eax
0x180034c4d  jz      short loc_180034C7C
0x180034c4f  lea     r9, aFailedToAssign_1; "Failed to assign BinFileVersion [%d]"
0x180034c56  mov     dword ptr [rsp+68h+var_48], eax
0x180034c5a  mov     r8d, 5F5h
0x180034c60  lea     rdx, aTelemetrypInst_0; "Telemetryp_InstallerGetMatchingInfo"
0x180034c67  mov     ecx, ebx
0x180034c69  call    AslLogCallPrintf
0x180034c6e  and     byte ptr [rsi+464h], 0FEh
0x180034c75  xor     ebx, ebx
0x180034c77  jmp     loc_180034EA2
0x180034c7c  or      [rsi+464h], r15b
0x180034c83  jmp     short loc_180034C75
0x180034c85  xor     eax, eax
0x180034c87  lea     rbx, [rbp+208h]
0x180034c8e  lea     r8, aName; "Name"
0x180034c95  mov     [rbx], ax
0x180034c98  lea     rdx, aInstallshield; "InstallShield_"
0x180034c9f  mov     rcx, rdi; this
0x180034ca2  xor     esi, esi
0x180034ca4  call    ?GetValue@RtlNameValueArray@@QEBAPEBGPEBG0@Z; RtlNameValueArray::GetValue(ushort const *,ushort const *)
0x180034ca9  test    rax, rax
0x180034cac  jz      loc_180034D66
0x180034cb2  mov     r8, rax; unsigned __int16 *
0x180034cb5  mov     rdx, r12; unsigned __int64
0x180034cb8  mov     rcx, rbx; unsigned __int16 *
0x180034cbb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180034cc0  test    eax, eax
0x180034cc2  jns     short loc_180034CDF
0x180034cc4  lea     eax, [rsi+7Ah]
0x180034cc7  mov     r8d, 58Ah
0x180034ccd  mov     ebx, eax
0x180034ccf  mov     dword ptr [rsp+68h+var_48], eax
0x180034cd3  lea     r9, aFailedToSetAlt; "Failed to set alt name [%d]"
0x180034cda  jmp     loc_180034E93
0x180034cdf  lea     r8, aLongname; "LongName"
0x180034ce6  mov     rcx, rdi; this
0x180034ce9  lea     rdx, aInstallshield; "InstallShield_"
0x180034cf0  call    ?GetValue@RtlNameValueArray@@QEBAPEBGPEBG0@Z; RtlNameValueArray::GetValue(ushort const *,ushort const *)
0x180034cf5  mov     rsi, rax
0x180034cf8  test    rax, rax
0x180034cfb  jz      short loc_180034D5F
0x180034cfd  lea     r8, asc_18011A0E8; ";"
0x180034d04  mov     rdx, r12; unsigned __int64
0x180034d07  mov     rcx, rbx; unsigned __int16 *
0x180034d0a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180034d0f  test    eax, eax
0x180034d11  jns     short loc_180034D30
0x180034d13  mov     eax, 7Ah ; 'z'
0x180034d18  lea     r9, aFailedToCatAlt; "Failed to cat alt name [%d]"
0x180034d1f  mov     ebx, eax
0x180034d21  mov     dword ptr [rsp+68h+var_48], eax
0x180034d25  mov     r8d, 595h
0x180034d2b  jmp     loc_180034E93
0x180034d30  mov     r8, rsi; unsigned __int16 *
0x180034d33  mov     rdx, r12; unsigned __int64
0x180034d36  mov     rcx, rbx; unsigned __int16 *
0x180034d39  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180034d3e  test    eax, eax
0x180034d40  jns     short loc_180034D5F
0x180034d42  mov     eax, 7Ah ; 'z'
0x180034d47  lea     r9, aFailedToCatAlt; "Failed to cat alt name [%d]"
0x180034d4e  mov     ebx, eax
0x180034d50  mov     dword ptr [rsp+68h+var_48], eax
0x180034d54  mov     r8d, 59Dh
0x180034d5a  jmp     loc_180034E93
0x180034d5f  lea     rsi, aInstallshield; "InstallShield_"
0x180034d66  lea     r8, aSize; "Size"
0x180034d6d  mov     rdx, rsi; String2
0x180034d70  mov     rcx, rdi; this
0x180034d73  call    ?GetValue@RtlNameValueArray@@QEBAPEBGPEBG0@Z; RtlNameValueArray::GetValue(ushort const *,ushort const *)
0x180034d78  test    rax, rax
0x180034d7b  jz      short loc_180034DA8
0x180034d7d  lea     rcx, [rbp+410h]; unsigned int *
0x180034d84  mov     rdx, rax; unsigned __int16 *
0x180034d87  call    ?PcaUtilityStringToUInt32@@YAKPEAIPEBG@Z; PcaUtilityStringToUInt32(uint *,ushort const *)
0x180034d8c  mov     ebx, eax
0x180034d8e  test    eax, eax
0x180034d90  jz      short loc_180034DA8
0x180034d92  mov     dword ptr [rsp+68h+var_48], eax
0x180034d96  lea     r9, aFailedToAssign_2; "Failed to assign Size [%d]"
0x180034d9d  mov     r8d, 5ADh
0x180034da3  jmp     loc_180034E93
0x180034da8  lea     r8, aCrcchecksum; "CrcChecksum"
0x180034daf  mov     rdx, rsi; String2
0x180034db2  mov     rcx, rdi; this
0x180034db5  call    ?GetValue@RtlNameValueArray@@QEBAPEBGPEBG0@Z; RtlNameValueArray::GetValue(ushort const *,ushort const *)
0x180034dba  test    rax, rax
0x180034dbd  jz      loc_180034C75
0x180034dc3  lea     rcx, [rbp+414h]; unsigned int *
0x180034dca  mov     rdx, rax; unsigned __int16 *
0x180034dcd  call    ?PcaUtilityStringToUInt32@@YAKPEAIPEBG@Z; PcaUtilityStringToUInt32(uint *,ushort const *)
0x180034dd2  mov     ebx, eax
0x180034dd4  test    eax, eax
0x180034dd6  jz      loc_180034C75
0x180034ddc  mov     dword ptr [rsp+68h+var_48], eax
0x180034de0  lea     r9, aFailedToAssign_0; "Failed to assign CrcChecksum [%d]"
0x180034de7  mov     r8d, 5BAh
0x180034ded  jmp     loc_180034E93
0x180034df2  or      eax, 0FFFFFFFFh
0x180034df5  lea     r8, aMsiproductcode; "MsiProductCode"
0x180034dfc  mov     [rbp+410h], eax
0x180034e02  xor     edx, edx; String2
0x180034e04  mov     [rbp+414h], eax
0x180034e0a  mov     rcx, rdi; this
0x180034e0d  bts     qword ptr [rsi+0F98h], 1Eh
0x180034e16  xor     eax, eax
0x180034e18  add     rbp, 208h
0x180034e1f  mov     [rbp+0], ax
0x180034e23  call    ?GetValue@RtlNameValueArray@@QEBAPEBGPEBG0@Z; RtlNameValueArray::GetValue(ushort const *,ushort const *)
0x180034e28  test    rax, rax
0x180034e2b  jz      short loc_180034E4F
0x180034e2d  mov     r8, rax; Source
  ... truncated ...
```
