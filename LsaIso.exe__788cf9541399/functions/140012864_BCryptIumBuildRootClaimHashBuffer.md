# BCryptIumBuildRootClaimHashBuffer

- ea: `0x140012864`
- end: `0x140012aa3`
- name: `BCryptIumBuildRootClaimHashBuffer`
- size: `575`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140013700`

## callees

- `0x140012864`
- `0x1400377b8`
- `0x140037b10`
- `0x140038d10`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x14001295a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x14001295a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140012a72`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140012a7b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140012a72`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140012a7b`
- `IUMBASE!GetSignedReport` at `0x1400129aa`
- `IUMBASE!GetSignedReport` at `0x1400129aa`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140012906`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140012906`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x140012a69`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x140012a69`
- `bcrypt!BCryptGetProperty` at `0x140012941`
- `bcrypt!BCryptGetProperty` at `0x140012941`

## string_xrefs

- `0x140012a22`: `onecore\ds\security\cryptoapi\ncrypt\ium\trustlet\bcryptiumkeyattest.cxx`
- `0x140012a52`: `onecore\ds\security\cryptoapi\ncrypt\ium\trustlet\bcryptiumkeyattest.cxx`

## pseudocode

```c
__int64 __fastcall BCryptIumBuildRootClaimHashBuffer(__int64 a1, int a2, HLOCAL *a3, _DWORD *a4, __int64 *a5)
{
  HLOCAL v7; // rdi
  __int64 v8; // rcx
  void *v9; // r14
  ULONG v10; // r12d
  UCHAR *v11; // r13
  NTSTATUS Property; // eax
  unsigned int SignedReport; // ebx
  __int64 v14; // r8
  __int64 v15; // rcx
  HLOCAL v16; // rax
  int v17; // eax
  UCHAR pbOutput[4]; // [rsp+50h] [rbp-51h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp-49h] BYREF
  ULONG pcbResult; // [rsp+60h] [rbp-41h] BYREF
  int v22; // [rsp+64h] [rbp-3Dh]
  HLOCAL hMem; // [rsp+68h] [rbp-39h]
  __int64 v24; // [rsp+70h] [rbp-31h] BYREF
  _QWORD v25[2]; // [rsp+78h] [rbp-29h] BYREF
  UCHAR pbInput[16]; // [rsp+88h] [rbp-19h] BYREF
  unsigned __int64 v27; // [rsp+98h] [rbp-9h]

  v22 = a2;
  v25[1] = a1;
  phAlgorithm = 0;
  v7 = 0;
  v8 = *a5;
  v9 = 0;
  pcbResult = 0;
  v24 = 0;
  v25[0] = 0;
  hMem = 0;
  *(_DWORD *)pbOutput = 0;
  if ( v8 )
  {
    v10 = *(_DWORD *)v8;
    v11 = *(UCHAR **)(v8 + 8);
  }
  else
  {
    v10 = 0;
    v11 = 0;
  }
  v27 = 0;
  *(_OWORD *)pbInput = 0;
  if ( !a4 || !a3 )
  {
    SignedReport = -1073741595;
    v14 = 425;
    goto LABEL_20;
  }
  *a4 = 0;
  *a3 = 0;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  SignedReport = Property;
  if ( Property < 0 )
  {
    v14 = 439;
LABEL_8:
    v15 = (unsigned int)Property;
LABEL_21:
    VBS_ATTEST_TRACE_ERROR_IN(
      v15,
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\trustlet\\bcryptiumkeyattest.cxx",
      v14);
    goto LABEL_22;
  }
  Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
  SignedReport = Property;
  if ( Property < 0 )
  {
    v14 = 452;
    goto LABEL_8;
  }
  v16 = LocalAlloc(0, *(unsigned int *)pbOutput);
  v9 = v16;
  if ( !v16 )
  {
    SignedReport = -1073741801;
    v14 = 462;
LABEL_20:
    v15 = SignedReport;
    goto LABEL_21;
  }
  SignedReport = GetSignedReport(32780, 32780, v16, *(unsigned int *)pbOutput, 0, &v24, 0, v25, 1);
  if ( (int)(SignedReport + 0x80000000) >= 0 && SignedReport != -805306333 )
  {
    v14 = 478;
    goto LABEL_20;
  }
  *(_DWORD *)&pbInput[8] = v22;
  v27 = __PAIR64__(v25[0], v24);
  *(_QWORD *)pbInput = 1212371542;
  *(_DWORD *)&pbInput[12] = v10;
  v17 = VBSAttestationBuildRootClaimHashBuffer(phAlgorithm, v11, v10, pbInput);
  SignedReport = v17;
  if ( v17 >= 0 )
  {
    *a3 = hMem;
    *a4 = *(_DWORD *)pbOutput;
  }
  else
  {
    VBS_ATTEST_TRACE_ERROR_IN(
      (unsigned int)v17,
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\trustlet\\bcryptiumkeyattest.cxx",
      499);
    v7 = hMem;
  }
LABEL_22:
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  LocalFree(v7);
  LocalFree(v9);
  return SignedReport;
}

```

## disassembly

```asm
0x140012864  push    rbp
0x140012866  push    rbx
0x140012867  push    rsi
0x140012868  push    rdi
0x140012869  push    r12
0x14001286b  push    r13
0x14001286d  push    r14
0x14001286f  push    r15
0x140012871  lea     rbp, [rsp-17h]
0x140012876  sub     rsp, 0B8h
0x14001287d  mov     rax, cs:__security_cookie
0x140012884  xor     rax, rsp
0x140012887  mov     [rbp+4Fh+var_50], rax
0x14001288b  mov     rax, [rbp+4Fh+arg_20]
0x14001288f  mov     r15, r9
0x140012892  mov     [rbp+4Fh+var_8C], edx
0x140012895  mov     rsi, r8
0x140012898  xor     edx, edx
0x14001289a  mov     [rbp+4Fh+var_70], rcx
0x14001289e  mov     [rbp+4Fh+phAlgorithm], rdx
0x1400128a2  mov     edi, edx
0x1400128a4  mov     rcx, [rax]
0x1400128a7  mov     r14d, edx
0x1400128aa  mov     [rbp+4Fh+var_90], edx
0x1400128ad  mov     [rbp+4Fh+var_80], rdx
0x1400128b1  mov     [rbp+4Fh+var_78], rdx
0x1400128b5  mov     [rbp+4Fh+hMem], rdx
0x1400128b9  mov     dword ptr [rbp+4Fh+pbOutput], edx
0x1400128bc  test    rcx, rcx
0x1400128bf  jz      short loc_1400128CA
0x1400128c1  mov     r12d, [rcx]
0x1400128c4  mov     r13, [rcx+8]
0x1400128c8  jmp     short loc_1400128D0
0x1400128ca  mov     r12d, edx
0x1400128cd  mov     r13, rdx
0x1400128d0  xor     eax, eax
0x1400128d2  xorps   xmm0, xmm0
0x1400128d5  mov     [rbp+4Fh+var_58], rax
0x1400128d9  movups  xmmword ptr [rbp+4Fh+var_68], xmm0
0x1400128dd  test    r15, r15
0x1400128e0  jz      loc_140012A45
0x1400128e6  test    rsi, rsi
0x1400128e9  jz      loc_140012A45
0x1400128ef  mov     [r9], edx
0x1400128f2  lea     rcx, [rbp+4Fh+phAlgorithm]; phAlgorithm
0x1400128f6  mov     [r8], rdx
0x1400128f9  xor     r9d, r9d; dwFlags
0x1400128fc  xor     r8d, r8d; pszImplementation
0x1400128ff  lea     rdx, aSha256; "SHA256"
0x140012906  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14001290c  mov     ebx, eax
0x14001290e  test    eax, eax
0x140012910  jns     short loc_14001291F
0x140012912  mov     r8d, 1B7h
0x140012918  mov     ecx, eax
0x14001291a  jmp     loc_140012A52
0x14001291f  mov     rcx, [rbp+4Fh+phAlgorithm]; hObject
0x140012923  lea     rax, [rbp+4Fh+var_90]
0x140012927  mov     [rsp+0F0h+dwFlags], edi; dwFlags
0x14001292b  lea     r8, [rbp+4Fh+pbOutput]; pbOutput
0x14001292f  mov     r9d, 4; cbOutput
0x140012935  mov     [rsp+0F0h+pcbResult], rax; pcbResult
0x14001293a  lea     rdx, aHashdigestleng; "HashDigestLength"
0x140012941  call    cs:__imp_BCryptGetProperty
0x140012947  mov     ebx, eax
0x140012949  test    eax, eax
0x14001294b  jns     short loc_140012955
0x14001294d  mov     r8d, 1C4h
0x140012953  jmp     short loc_140012918
0x140012955  mov     edx, dword ptr [rbp+4Fh+pbOutput]; uBytes
0x140012958  xor     ecx, ecx; uFlags
0x14001295a  call    cs:__imp_LocalAlloc
0x140012960  mov     r14, rax
0x140012963  test    rax, rax
0x140012966  jnz     short loc_140012978
0x140012968  mov     ebx, 0C0000017h
0x14001296d  mov     r8d, 1CEh
0x140012973  jmp     loc_140012A50
0x140012978  mov     r9d, dword ptr [rbp+4Fh+pbOutput]
0x14001297c  lea     rax, [rbp+4Fh+var_78]
0x140012980  mov     [rsp+0F0h+var_B0], 1
0x140012988  mov     ecx, 800Ch
0x14001298d  mov     [rsp+0F0h+var_B8], rax
0x140012992  mov     r8, r14
0x140012995  lea     rax, [rbp+4Fh+var_80]
0x140012999  mov     [rsp+0F0h+pbInput], rdi
0x14001299e  mov     qword ptr [rsp+0F0h+dwFlags], rax
0x1400129a3  mov     edx, ecx
0x1400129a5  mov     [rsp+0F0h+pcbResult], rdi
0x1400129aa  call    cs:__imp_GetSignedReport
0x1400129b0  mov     ecx, 80000000h
0x1400129b5  mov     ebx, eax
0x1400129b7  add     eax, ecx
0x1400129b9  test    ecx, eax
0x1400129bb  jnz     short loc_1400129D0
0x1400129bd  cmp     ebx, 0D0000023h
0x1400129c3  jz      short loc_1400129D0
0x1400129c5  mov     r8d, 1DEh
0x1400129cb  jmp     loc_140012A50
0x1400129d0  mov     eax, [rbp+4Fh+var_8C]
0x1400129d3  lea     r8, [rbp+4Fh+pbOutput]
0x1400129d7  mov     r9, [rbp+4Fh+var_70]
0x1400129db  lea     rdx, [rbp+4Fh+hMem]
0x1400129df  mov     rcx, [rbp+4Fh+phAlgorithm]; hObject
0x1400129e3  mov     dword ptr [rbp+4Fh+var_68+8], eax
0x1400129e6  mov     eax, dword ptr [rbp+4Fh+var_80]
0x1400129e9  mov     dword ptr [rbp+4Fh+var_58], eax
0x1400129ec  mov     eax, dword ptr [rbp+4Fh+var_78]
0x1400129ef  mov     dword ptr [rbp+4Fh+var_58+4], eax
0x1400129f2  lea     rax, [rbp+4Fh+var_68]
0x1400129f6  mov     [rsp+0F0h+pbInput], rax; pbInput
0x1400129fb  mov     [rsp+0F0h+dwFlags], r12d; cbInput
0x140012a00  mov     [rsp+0F0h+pcbResult], r13; PUCHAR
0x140012a05  mov     qword ptr [rbp+4Fh+var_68], 48435256h
0x140012a0d  mov     dword ptr [rbp+4Fh+var_68+0Ch], r12d
0x140012a11  call    VBSAttestationBuildRootClaimHashBuffer
0x140012a16  mov     ebx, eax
0x140012a18  test    eax, eax
0x140012a1a  jns     short loc_140012A36
0x140012a1c  mov     r8d, 1F3h
0x140012a22  lea     rdx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x140012a29  mov     ecx, eax
0x140012a2b  call    VBS_ATTEST_TRACE_ERROR_IN
0x140012a30  mov     rdi, [rbp+4Fh+hMem]
0x140012a34  jmp     short loc_140012A5E
0x140012a36  mov     rax, [rbp+4Fh+hMem]
0x140012a3a  mov     [rsi], rax
0x140012a3d  mov     eax, dword ptr [rbp+4Fh+pbOutput]
0x140012a40  mov     [r15], eax
0x140012a43  jmp     short loc_140012A5E
0x140012a45  mov     ebx, 0C00000E5h
0x140012a4a  mov     r8d, 1A9h
0x140012a50  mov     ecx, ebx
0x140012a52  lea     rdx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x140012a59  call    VBS_ATTEST_TRACE_ERROR_IN
0x140012a5e  mov     rcx, [rbp+4Fh+phAlgorithm]; hAlgorithm
0x140012a62  test    rcx, rcx
0x140012a65  jz      short loc_140012A6F
0x140012a67  xor     edx, edx; dwFlags
0x140012a69  call    cs:__imp_BCryptCloseAlgorithmProvider
0x140012a6f  mov     rcx, rdi; hMem
0x140012a72  call    cs:__imp_LocalFree
0x140012a78  mov     rcx, r14; hMem
0x140012a7b  call    cs:__imp_LocalFree
0x140012a81  mov     eax, ebx
0x140012a83  mov     rcx, [rbp+4Fh+var_50]
0x140012a87  xor     rcx, rsp; StackCookie
0x140012a8a  call    __security_check_cookie
0x140012a8f  add     rsp, 0B8h
0x140012a96  pop     r15
0x140012a98  pop     r14
0x140012a9a  pop     r13
0x140012a9c  pop     r12
0x140012a9e  pop     rdi
0x140012a9f  pop     rsi
0x140012aa0  pop     rbx
0x140012aa1  pop     rbp
0x140012aa2  retn
```
