# BCryptIumBuildIdentityClaimHashBuffer

- ea: `0x14001260c`
- end: `0x14001285c`
- name: `BCryptIumBuildIdentityClaimHashBuffer`
- size: `592`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140013124`

## callees

- `0x14001260c`
- `0x14003753c`
- `0x140037b10`
- `0x140038d10`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140012834`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140012834`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1400126dd`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1400126dd`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x14001282b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x14001282b`
- `bcrypt!BCryptGetProperty` at `0x140012719`
- `bcrypt!BCryptGetProperty` at `0x140012758`
- `bcrypt!BCryptGetProperty` at `0x140012719`
- `bcrypt!BCryptGetProperty` at `0x140012758`

## string_xrefs

- `0x1400127e4`: `onecore\ds\security\cryptoapi\ncrypt\ium\trustlet\bcryptiumkeyattest.cxx`
- `0x140012814`: `onecore\ds\security\cryptoapi\ncrypt\ium\trustlet\bcryptiumkeyattest.cxx`

## pseudocode

```c
__int64 __fastcall BCryptIumBuildIdentityClaimHashBuffer(
        void *a1,
        __int64 a2,
        int a3,
        UCHAR *a4,
        unsigned int a5,
        UCHAR *a6,
        unsigned int a7,
        HLOCAL *a8,
        _DWORD *a9,
        _QWORD *a10)
{
  HLOCAL v10; // rsi
  int *v11; // rax
  int v12; // r12d
  UCHAR *v13; // r13
  unsigned int v14; // ebx
  __int64 v15; // r8
  __int64 v16; // rax
  UCHAR *v17; // r14
  NTSTATUS Property; // eax
  __int64 v19; // rcx
  unsigned int v20; // ecx
  int v21; // eax
  UCHAR pbOutput[4]; // [rsp+50h] [rbp-81h] BYREF
  UCHAR v24[4]; // [rsp+54h] [rbp-7Dh] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp-79h] BYREF
  ULONG pcbResult; // [rsp+60h] [rbp-71h] BYREF
  ULONG v27; // [rsp+64h] [rbp-6Dh] BYREF
  int v28; // [rsp+68h] [rbp-69h]
  HLOCAL hMem; // [rsp+70h] [rbp-61h]
  BCRYPT_HANDLE hObject; // [rsp+78h] [rbp-59h]
  _QWORD *v31; // [rsp+80h] [rbp-51h]
  PUCHAR v32; // [rsp+88h] [rbp-49h]
  PUCHAR v33; // [rsp+90h] [rbp-41h]
  __int64 v34; // [rsp+98h] [rbp-39h]
  UCHAR pbInput[16]; // [rsp+A0h] [rbp-31h] BYREF
  __int128 v36; // [rsp+B0h] [rbp-21h]

  hObject = a1;
  v34 = a2;
  v33 = a6;
  v10 = 0;
  v32 = a4;
  v11 = (int *)*a10;
  v28 = a3;
  v31 = a10;
  phAlgorithm = 0;
  pcbResult = 0;
  *(_DWORD *)v24 = 0;
  v27 = 0;
  hMem = 0;
  *(_DWORD *)pbOutput = 0;
  if ( v11 )
  {
    v12 = *v11;
    v13 = (UCHAR *)*((_QWORD *)v11 + 1);
  }
  else
  {
    v12 = 0;
    v13 = 0;
  }
  *(_OWORD *)pbInput = 0;
  v36 = 0;
  if ( !a9 )
  {
    v14 = -1073741595;
    v15 = 554;
LABEL_21:
    v19 = v14;
    goto LABEL_22;
  }
  *a9 = 0;
  v16 = a10[1];
  if ( !v16 || (v17 = *(UCHAR **)(v16 + 8)) == 0 )
  {
    v14 = -1073741811;
    v15 = 568;
    goto LABEL_21;
  }
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, *(LPCWSTR *)(v16 + 8), 0, 0);
  v14 = Property;
  if ( Property >= 0 )
  {
    Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
    v14 = Property;
    if ( Property >= 0 )
    {
      if ( a8 )
      {
        Property = BCryptGetProperty(hObject, L"SignatureLength", v24, 4u, &v27, 0);
        v14 = Property;
        if ( Property < 0 )
        {
          v15 = 611;
          goto LABEL_10;
        }
        *(_DWORD *)&pbInput[8] = v28;
        *(_QWORD *)pbInput = 1212369238;
        v20 = *(_DWORD *)v31[1];
        *((_QWORD *)&v36 + 1) = __PAIR64__(*(unsigned int *)v24, a7);
        *(_QWORD *)&v36 = __PAIR64__(a5, v20);
        *(_DWORD *)&pbInput[12] = v12;
        v21 = VBSAttestationBuildIdentityClaimHashBuffer(phAlgorithm, v13, v17, v33, v32, pbInput);
        v14 = v21;
        if ( v21 < 0 )
        {
          VBS_ATTEST_TRACE_ERROR_IN(
            (unsigned int)v21,
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\trustlet\\bcryptiumkeyattest.cxx",
            635);
          v10 = hMem;
          goto LABEL_23;
        }
        *a8 = hMem;
      }
      *a9 = *(_DWORD *)pbOutput;
      goto LABEL_23;
    }
    v15 = 592;
  }
  else
  {
    v15 = 579;
  }
LABEL_10:
  v19 = (unsigned int)Property;
LABEL_22:
  VBS_ATTEST_TRACE_ERROR_IN(v19, "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\trustlet\\bcryptiumkeyattest.cxx", v15);
LABEL_23:
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  LocalFree(v10);
  return v14;
}

```

## disassembly

```asm
0x14001260c  push    rbp
0x14001260e  push    rbx
0x14001260f  push    rsi
0x140012610  push    rdi
0x140012611  push    r12
0x140012613  push    r13
0x140012615  push    r14
0x140012617  push    r15
0x140012619  lea     rbp, [rsp-7]
0x14001261e  sub     rsp, 0D8h
0x140012625  mov     rax, cs:__security_cookie
0x14001262c  xor     rax, rsp
0x14001262f  mov     [rbp+3Fh+var_50], rax
0x140012633  mov     rax, [rbp+3Fh+arg_28]
0x140012637  mov     r15, [rbp+3Fh+arg_38]
0x14001263e  mov     rdi, [rbp+3Fh+arg_40]
0x140012645  mov     [rbp+3Fh+hObject], rcx
0x140012649  mov     rcx, [rbp+3Fh+arg_48]
0x140012650  mov     [rbp+3Fh+var_78], rdx
0x140012654  xor     edx, edx
0x140012656  mov     [rbp+3Fh+var_80], rax
0x14001265a  mov     esi, edx
0x14001265c  mov     [rbp+3Fh+var_88], r9
0x140012660  mov     rax, [rcx]
0x140012663  mov     [rbp+3Fh+var_A8], r8d
0x140012667  mov     [rbp+3Fh+var_90], rcx
0x14001266b  mov     [rbp+3Fh+phAlgorithm], rdx
0x14001266f  mov     [rbp+3Fh+var_B0], edx
0x140012672  mov     dword ptr [rbp+3Fh+var_BC], edx
0x140012675  mov     [rbp+3Fh+var_AC], edx
0x140012678  mov     [rbp+3Fh+hMem], rdx
0x14001267c  mov     dword ptr [rsp+110h+pbOutput], edx
0x140012680  test    rax, rax
0x140012683  jz      short loc_14001268E
0x140012685  mov     r12d, [rax]
0x140012688  mov     r13, [rax+8]
0x14001268c  jmp     short loc_140012694
0x14001268e  mov     r12d, edx
0x140012691  mov     r13, rdx
0x140012694  xorps   xmm0, xmm0
0x140012697  movups  xmmword ptr [rbp+3Fh+var_70], xmm0
0x14001269b  movups  [rbp+3Fh+var_60], xmm0
0x14001269f  test    rdi, rdi
0x1400126a2  jnz     short loc_1400126B4
0x1400126a4  mov     ebx, 0C00000E5h
0x1400126a9  mov     r8d, 22Ah
0x1400126af  jmp     loc_140012812
0x1400126b4  mov     [rdi], edx
0x1400126b6  mov     rax, [rcx+8]
0x1400126ba  test    rax, rax
0x1400126bd  jz      loc_140012807
0x1400126c3  mov     r14, [rax+8]
0x1400126c7  test    r14, r14
0x1400126ca  jz      loc_140012807
0x1400126d0  xor     r9d, r9d; dwFlags
0x1400126d3  lea     rcx, [rbp+3Fh+phAlgorithm]; phAlgorithm
0x1400126d7  xor     r8d, r8d; pszImplementation
0x1400126da  mov     rdx, r14; pszAlgId
0x1400126dd  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400126e3  mov     ebx, eax
0x1400126e5  test    eax, eax
0x1400126e7  jns     short loc_1400126F6
0x1400126e9  mov     r8d, 243h
0x1400126ef  mov     ecx, eax
0x1400126f1  jmp     loc_140012814
0x1400126f6  mov     rcx, [rbp+3Fh+phAlgorithm]; hObject
0x1400126fa  lea     rax, [rbp+3Fh+var_B0]
0x1400126fe  mov     [rsp+110h+dwFlags], esi; dwFlags
0x140012702  lea     r8, [rsp+110h+pbOutput]; pbOutput
0x140012707  mov     r9d, 4; cbOutput
0x14001270d  mov     [rsp+110h+pcbResult], rax; pcbResult
0x140012712  lea     rdx, aHashdigestleng; "HashDigestLength"
0x140012719  call    cs:__imp_BCryptGetProperty
0x14001271f  mov     ebx, eax
0x140012721  test    eax, eax
0x140012723  jns     short loc_14001272D
0x140012725  mov     r8d, 250h
0x14001272b  jmp     short loc_1400126EF
0x14001272d  test    r15, r15
0x140012730  jz      loc_1400127FF
0x140012736  mov     rcx, [rbp+3Fh+hObject]; hObject
0x14001273a  lea     rax, [rbp+3Fh+var_AC]
0x14001273e  mov     [rsp+110h+dwFlags], esi; dwFlags
0x140012742  lea     r8, [rbp+3Fh+var_BC]; pbOutput
0x140012746  mov     r9d, 4; cbOutput
0x14001274c  mov     [rsp+110h+pcbResult], rax; pcbResult
0x140012751  lea     rdx, aSignaturelengt; "SignatureLength"
0x140012758  call    cs:__imp_BCryptGetProperty
0x14001275e  mov     ebx, eax
0x140012760  test    eax, eax
0x140012762  jns     short loc_14001276C
0x140012764  mov     r8d, 263h
0x14001276a  jmp     short loc_1400126EF
0x14001276c  mov     eax, dword ptr [rbp+3Fh+var_BC]
0x14001276f  lea     r8, [rsp+110h+pbOutput]
0x140012774  mov     r9, [rbp+3Fh+var_78]
0x140012778  lea     rdx, [rbp+3Fh+hMem]
0x14001277c  mov     dword ptr [rbp+3Fh+var_60+0Ch], eax
0x14001277f  mov     eax, [rbp+3Fh+var_A8]
0x140012782  mov     dword ptr [rbp+3Fh+var_70+8], eax
0x140012785  mov     rax, [rbp+3Fh+var_90]
0x140012789  mov     qword ptr [rbp+3Fh+var_70], 48434956h
0x140012791  mov     rax, [rax+8]
0x140012795  mov     ecx, [rax]
0x140012797  mov     eax, [rbp+3Fh+arg_20]
0x14001279a  mov     dword ptr [rbp+3Fh+var_60+4], eax
0x14001279d  mov     eax, [rbp+3Fh+arg_30]
0x1400127a0  mov     dword ptr [rbp+3Fh+var_60+8], eax
0x1400127a3  lea     rax, [rbp+3Fh+var_70]
0x1400127a7  mov     [rsp+110h+pbInput], rax; pbInput
0x1400127ac  mov     rax, [rbp+3Fh+var_88]
0x1400127b0  mov     [rsp+110h+var_D8], rax; PUCHAR
0x1400127b5  mov     rax, [rbp+3Fh+var_80]
0x1400127b9  mov     [rsp+110h+var_E0], rax; PUCHAR
0x1400127be  mov     dword ptr [rbp+3Fh+var_60], ecx
0x1400127c1  mov     rcx, [rbp+3Fh+phAlgorithm]; hObject
0x1400127c5  mov     qword ptr [rsp+110h+dwFlags], r14; PUCHAR
0x1400127ca  mov     [rsp+110h+pcbResult], r13; PUCHAR
0x1400127cf  mov     dword ptr [rbp+3Fh+var_70+0Ch], r12d
0x1400127d3  call    VBSAttestationBuildIdentityClaimHashBuffer
0x1400127d8  mov     ebx, eax
0x1400127da  test    eax, eax
0x1400127dc  jns     short loc_1400127F8
0x1400127de  mov     r8d, 27Bh
0x1400127e4  lea     rdx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1400127eb  mov     ecx, eax
0x1400127ed  call    VBS_ATTEST_TRACE_ERROR_IN
0x1400127f2  mov     rsi, [rbp+3Fh+hMem]
0x1400127f6  jmp     short loc_140012820
0x1400127f8  mov     rax, [rbp+3Fh+hMem]
0x1400127fc  mov     [r15], rax
0x1400127ff  mov     eax, dword ptr [rsp+110h+pbOutput]
0x140012803  mov     [rdi], eax
0x140012805  jmp     short loc_140012820
0x140012807  mov     ebx, 0C000000Dh
0x14001280c  mov     r8d, 238h
0x140012812  mov     ecx, ebx
0x140012814  lea     rdx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x14001281b  call    VBS_ATTEST_TRACE_ERROR_IN
0x140012820  mov     rcx, [rbp+3Fh+phAlgorithm]; hAlgorithm
0x140012824  test    rcx, rcx
0x140012827  jz      short loc_140012831
0x140012829  xor     edx, edx; dwFlags
0x14001282b  call    cs:__imp_BCryptCloseAlgorithmProvider
0x140012831  mov     rcx, rsi; hMem
0x140012834  call    cs:__imp_LocalFree
0x14001283a  mov     eax, ebx
0x14001283c  mov     rcx, [rbp+3Fh+var_50]
0x140012840  xor     rcx, rsp; StackCookie
0x140012843  call    __security_check_cookie
0x140012848  add     rsp, 0D8h
0x14001284f  pop     r15
0x140012851  pop     r14
0x140012853  pop     r13
0x140012855  pop     r12
0x140012857  pop     rdi
0x140012858  pop     rsi
0x140012859  pop     rbx
0x14001285a  pop     rbp
0x14001285b  retn
```
