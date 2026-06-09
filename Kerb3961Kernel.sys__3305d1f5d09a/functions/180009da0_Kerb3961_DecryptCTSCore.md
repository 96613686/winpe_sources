# Kerb3961::DecryptCTSCore

- ea: `0x180009da0`
- end: `0x18000a03c`
- name: `Kerb3961::DecryptCTSCore`
- size: `668`
- prototype: `NTSTATUS *__fastcall(NTSTATUS *, UCHAR *, void *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180009c48`

## callees

- `0x180001684`
- `0x180003a38`
- `0x180003a54`
- `0x180005b1c`
- `0x180009da0`
- `0x1800118cc`
- `0x180011b40`
- `0x180012300`

## import_xrefs

- `cng!BCryptDecrypt` at `0x180009ec1`
- `cng!BCryptDecrypt` at `0x180009f5e`
- `cng!BCryptDecrypt` at `0x180009fc8`
- `cng!BCryptDecrypt` at `0x180009ec1`
- `cng!BCryptDecrypt` at `0x180009f5e`
- `cng!BCryptDecrypt` at `0x180009fc8`

## string_xrefs

- `0x180009e1a`: `finalBlockCopy`
- `0x180009fdc`: `BCryptDecrypt(key, finalBlockCopy.buffer, static_cast<uint32_t>(finalBlockCopy.length), nullptr, IV.buffer, static_cast<uint32_t>(IV.length), finalBlockCopy.buffer, static_cast<uint32_t>(finalBlockCopy.length), &returnLength, 0)`

## pseudocode

```c
NTSTATUS *__fastcall Kerb3961::DecryptCTSCore(NTSTATUS *a1, UCHAR *a2, void *a3, __int64 a4, _QWORD *a5)
{
  unsigned __int64 cbOutput; // r12
  char *v8; // r15
  int v9; // r8d
  NTSTATUS v10; // ebx
  char *v11; // rcx
  PUCHAR v12; // rcx
  UCHAR *pbOutput; // r13
  int v14; // r8d
  NTSTATUS v15; // ebx
  PUCHAR v16; // rcx
  __int64 v17; // r14
  PUCHAR v18; // rbx
  NTSTATUS v19; // eax
  const unsigned __int16 *v20; // rdx
  int v21; // r8d
  NTSTATUS v22; // esi
  __int64 v23; // rsi
  BCRYPT_KEY_HANDLE v24; // r13
  __int64 v25; // r14
  PUCHAR v26; // rbx
  NTSTATUS v27; // eax
  int v28; // r8d
  NTSTATUS v29; // esi
  ULONG pcbResult; // [rsp+50h] [rbp-81h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+58h] [rbp-79h]
  ULONG cbIV[2]; // [rsp+60h] [rbp-71h] BYREF
  PUCHAR pbIV; // [rsp+68h] [rbp-69h]
  char *v35; // [rsp+70h] [rbp-61h]
  ULONG v36[2]; // [rsp+80h] [rbp-51h] BYREF
  PUCHAR v37; // [rsp+88h] [rbp-49h]
  char *v38; // [rsp+90h] [rbp-41h]
  _QWORD *v39; // [rsp+98h] [rbp-39h]
  __int64 v40; // [rsp+A0h] [rbp-31h]
  char v41[16]; // [rsp+A8h] [rbp-29h] BYREF
  ULONG cbInput[2]; // [rsp+B8h] [rbp-19h] BYREF
  PUCHAR pbInput; // [rsp+C0h] [rbp-11h]
  void *Src; // [rsp+D0h] [rbp-1h]

  hKey = a3;
  v40 = a4;
  v39 = a5;
  pbIV = a2;
  cbOutput = *a5 - 1LL - (*a5 - 1LL) % (unsigned __int64)a2;
  v8 = (char *)(*a5 - cbOutput);
  *(_QWORD *)cbIV = cbOutput - (_QWORD)a2;
  v35 = v8;
  Kerb3961::Split<3>(v41, a5, cbIV);
  Kerb3961::CopyBuffer(v36, cbInput);
  v10 = (int)v38;
  if ( (int)v38 < 0 )
  {
    v11 = "finalBlockCopy";
LABEL_3:
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v11, (const char *)(unsigned int)v10, v9);
    *a1 = v10;
    goto LABEL_4;
  }
  pbOutput = pbInput;
  pcbResult = 0;
  if ( v8 != (char *)a2 )
  {
    Kerb3961::MakeBuffer(cbIV);
    v15 = (int)v35;
    if ( (int)v35 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"zeroIV",
        (const char *)(unsigned int)v35,
        v14);
      v16 = pbIV;
      *a1 = v15;
      if ( !v16 )
        goto LABEL_4;
      goto LABEL_9;
    }
    v17 = *(_QWORD *)cbInput;
    v18 = pbIV;
    v19 = BCryptDecrypt(hKey, pbOutput, cbInput[0], 0, pbIV, cbIV[0], pbOutput, cbInput[0], &pcbResult, 0);
    v22 = v19;
    if ( v19 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"BCryptDecrypt(key, finalBlock.buffer, static_cast<uint32_t>(finalBlock.length), nul"
                                     "lptr, zeroIV.buffer, static_cast<uint32_t>(zeroIV.length), finalBlock.buffer, stati"
                                     "c_cast<uint32_t>(finalBlock.length), &returnLength, 0)",
        (const char *)(unsigned int)v19,
        v21);
      *a1 = v22;
      if ( !v18 )
      {
LABEL_4:
        v12 = v37;
        if ( v37 )
          goto LABEL_25;
        return a1;
      }
      v16 = v18;
LABEL_9:
      Kerb3961Free(v16);
      goto LABEL_4;
    }
    if ( pcbResult != v17 )
      goto LABEL_27;
    if ( v18 )
      Kerb3961Free(v18);
  }
  memmove(pbOutput, Src, (size_t)v8);
  v23 = v40;
  v24 = hKey;
  v10 = BCryptDecrypt(
          hKey,
          (PUCHAR)v39[1],
          cbOutput,
          0,
          *(PUCHAR *)(v40 + 8),
          *(_DWORD *)v40,
          (PUCHAR)v39[1],
          cbOutput,
          &pcbResult,
          0);
  if ( v10 < 0 )
  {
    v11 = "BCryptDecrypt(key, data.buffer, static_cast<uint32_t>(nonFinalBlockSize), nullptr, IV.buffer, static_cast<uint"
          "32_t>(IV.length), data.buffer, static_cast<uint32_t>(nonFinalBlockSize), &returnLength, 0)";
    goto LABEL_3;
  }
  if ( pcbResult != cbOutput )
    goto LABEL_27;
  v25 = *(_QWORD *)v36;
  v26 = v37;
  v27 = BCryptDecrypt(v24, v37, v36[0], 0, *(PUCHAR *)(v23 + 8), *(_DWORD *)v23, v37, v36[0], &pcbResult, 0);
  v29 = v27;
  if ( v27 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"BCryptDecrypt(key, finalBlockCopy.buffer, static_cast<uint32_t>(finalBlockCopy.length"
                                   "), nullptr, IV.buffer, static_cast<uint32_t>(IV.length), finalBlockCopy.buffer, stati"
                                   "c_cast<uint32_t>(finalBlockCopy.length), &returnLength, 0)",
      (const char *)(unsigned int)v27,
      v28);
    *a1 = v29;
    goto LABEL_23;
  }
  if ( pcbResult != v25 )
LABEL_27:
    Kerb3961::ConsistencyFail(
      (Kerb3961 *)L"Decrypted text shorter than expected.  DecryptCTS is only for use with CBC mode algorithm handles.",
      v20);
  memmove(Src, v26, (size_t)v8);
  *a1 = 0;
LABEL_23:
  if ( v26 )
  {
    v12 = v26;
LABEL_25:
    Kerb3961Free(v12);
  }
  return a1;
}

```

## disassembly

```asm
0x180009da0  push    rbp
0x180009da2  push    rbx
0x180009da3  push    rsi
0x180009da4  push    rdi
0x180009da5  push    r12
0x180009da7  push    r13
0x180009da9  push    r14
0x180009dab  push    r15
0x180009dad  lea     rbp, [rsp-17h]
0x180009db2  sub     rsp, 0E8h
0x180009db9  mov     rsi, rdx
0x180009dbc  mov     [rbp+4Fh+hKey], r8
0x180009dc0  mov     rdi, rcx
0x180009dc3  mov     [rbp+4Fh+var_80], r9
0x180009dc7  mov     rcx, [rbp+4Fh+arg_20]
0x180009dcb  lea     r8, [rbp+4Fh+var_C0]
0x180009dcf  xor     edx, edx
0x180009dd1  mov     [rbp+4Fh+var_88], rcx
0x180009dd5  mov     [rbp+4Fh+var_B8], rsi
0x180009dd9  mov     r15, [rcx]
0x180009ddc  lea     r12, [r15-1]
0x180009de0  mov     rax, r12
0x180009de3  div     rsi
0x180009de6  sub     r12, rdx
0x180009de9  mov     rdx, rcx
0x180009dec  mov     rax, r12
0x180009def  lea     rcx, [rbp+4Fh+var_78]
0x180009df3  sub     rax, rsi
0x180009df6  sub     r15, r12
0x180009df9  mov     qword ptr [rbp+4Fh+var_C0], rax
0x180009dfd  mov     [rbp+4Fh+var_B0], r15
0x180009e01  call    ??$Split@$02@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$02@utl@@AEBUMutableBinary@0@U?$array@_K$02@2@@Z; Kerb3961::Split<3>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,3>)
0x180009e06  lea     rdx, [rbp+4Fh+cbInput]
0x180009e0a  lea     rcx, [rbp+4Fh+var_A0]
0x180009e0e  call    ?CopyBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@@Z; Kerb3961::CopyBuffer(Kerb3961::ReadOnlyBinary const &)
0x180009e13  mov     ebx, dword ptr [rbp+4Fh+var_90]
0x180009e16  test    ebx, ebx
0x180009e18  jns     short loc_180009E3C
0x180009e1a  lea     rcx, aFinalblockcopy; "finalBlockCopy"
0x180009e21  mov     edx, ebx; char *
0x180009e23  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180009e28  mov     [rdi], ebx
0x180009e2a  mov     rcx, [rbp+4Fh+var_98]
0x180009e2e  test    rcx, rcx
0x180009e31  jz      loc_18000A017
0x180009e37  jmp     loc_18000A012
0x180009e3c  mov     r13, [rbp+4Fh+pbInput]
0x180009e40  mov     [rsp+120h+var_D0], 0
0x180009e48  cmp     r15, rsi
0x180009e4b  jz      loc_180009F0B
0x180009e51  mov     rdx, rsi
0x180009e54  lea     rcx, [rbp+4Fh+var_C0]
0x180009e58  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x180009e5d  mov     ebx, dword ptr [rbp+4Fh+var_B0]
0x180009e60  test    ebx, ebx
0x180009e62  jns     short loc_180009E84
0x180009e64  mov     edx, ebx; char *
0x180009e66  lea     rcx, aZeroiv; "zeroIV"
0x180009e6d  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180009e72  mov     rcx, [rbp+4Fh+var_B8]
0x180009e76  mov     [rdi], ebx
0x180009e78  test    rcx, rcx
0x180009e7b  jz      short loc_180009E2A
0x180009e7d  call    Kerb3961Free
0x180009e82  jmp     short loc_180009E2A
0x180009e84  mov     r14, qword ptr [rbp+4Fh+cbInput]
0x180009e88  lea     rax, [rsp+120h+var_D0]
0x180009e8d  mov     rbx, [rbp+4Fh+var_B8]
0x180009e91  xor     r9d, r9d; pPaddingInfo
0x180009e94  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180009e98  mov     r8d, r14d; cbInput
0x180009e9b  mov     [rsp+120h+dwFlags], 0; dwFlags
0x180009ea3  mov     rdx, r13; pbInput
0x180009ea6  mov     [rsp+120h+pcbResult], rax; pcbResult
0x180009eab  mov     eax, [rbp+4Fh+var_C0]
0x180009eae  mov     [rsp+120h+cbOutput], r14d; cbOutput
0x180009eb3  mov     [rsp+120h+pbOutput], r13; pbOutput
0x180009eb8  mov     [rsp+120h+cbIV], eax; cbIV
0x180009ebc  mov     [rsp+120h+pbIV], rbx; pbIV
0x180009ec1  call    cs:__imp_BCryptDecrypt
0x180009ec8  nop     dword ptr [rax+rax+00h]
0x180009ecd  mov     esi, eax
0x180009ecf  test    eax, eax
0x180009ed1  jns     short loc_180009EF1
0x180009ed3  mov     edx, eax; char *
0x180009ed5  lea     rcx, aBcryptdecryptK_0; "BCryptDecrypt(key, finalBlock.buffer, s"...
0x180009edc  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180009ee1  mov     [rdi], esi
0x180009ee3  test    rbx, rbx
0x180009ee6  jz      loc_180009E2A
0x180009eec  mov     rcx, rbx
0x180009eef  jmp     short loc_180009E7D
0x180009ef1  mov     eax, [rsp+120h+var_D0]
0x180009ef5  cmp     rax, r14
0x180009ef8  jnz     loc_18000A02F
0x180009efe  test    rbx, rbx
0x180009f01  jz      short loc_180009F0B
0x180009f03  mov     rcx, rbx
0x180009f06  call    Kerb3961Free
0x180009f0b  mov     rdx, [rbp+4Fh+Src]; Src
0x180009f0f  mov     r8, r15; Size
0x180009f12  mov     rcx, r13; void *
0x180009f15  call    memmove
0x180009f1a  mov     rsi, [rbp+4Fh+var_80]
0x180009f1e  lea     rax, [rsp+120h+var_D0]
0x180009f23  mov     rdx, [rbp+4Fh+var_88]
0x180009f27  xor     r9d, r9d; pPaddingInfo
0x180009f2a  mov     r13, [rbp+4Fh+hKey]
0x180009f2e  mov     r8d, r12d; cbInput
0x180009f31  mov     [rsp+120h+dwFlags], 0; dwFlags
0x180009f39  mov     rcx, r13; hKey
0x180009f3c  mov     [rsp+120h+pcbResult], rax; pcbResult
0x180009f41  mov     eax, [rsi]
0x180009f43  mov     rdx, [rdx+8]; pbInput
0x180009f47  mov     [rsp+120h+cbOutput], r12d; cbOutput
0x180009f4c  mov     [rsp+120h+pbOutput], rdx; pbOutput
0x180009f51  mov     [rsp+120h+cbIV], eax; cbIV
0x180009f55  mov     rax, [rsi+8]
0x180009f59  mov     [rsp+120h+pbIV], rax; pbIV
0x180009f5e  call    cs:__imp_BCryptDecrypt
0x180009f65  nop     dword ptr [rax+rax+00h]
0x180009f6a  mov     ebx, eax
0x180009f6c  test    eax, eax
0x180009f6e  jns     short loc_180009F7C
0x180009f70  lea     rcx, aBcryptdecryptK_1; "BCryptDecrypt(key, data.buffer, static_"...
0x180009f77  jmp     loc_180009E21
0x180009f7c  mov     eax, [rsp+120h+var_D0]
0x180009f80  cmp     rax, r12
0x180009f83  jnz     loc_18000A02F
0x180009f89  mov     r14, qword ptr [rbp+4Fh+var_A0]
0x180009f8d  lea     rax, [rsp+120h+var_D0]
0x180009f92  mov     rbx, [rbp+4Fh+var_98]
0x180009f96  xor     r9d, r9d; pPaddingInfo
0x180009f99  mov     [rsp+120h+dwFlags], 0; dwFlags
0x180009fa1  mov     r8d, r14d; cbInput
0x180009fa4  mov     [rsp+120h+pcbResult], rax; pcbResult
0x180009fa9  mov     rdx, rbx; pbInput
0x180009fac  mov     eax, [rsi]
0x180009fae  mov     rcx, r13; hKey
0x180009fb1  mov     [rsp+120h+cbOutput], r14d; cbOutput
0x180009fb6  mov     [rsp+120h+pbOutput], rbx; pbOutput
0x180009fbb  mov     [rsp+120h+cbIV], eax; cbIV
0x180009fbf  mov     rax, [rsi+8]
0x180009fc3  mov     [rsp+120h+pbIV], rax; pbIV
0x180009fc8  call    cs:__imp_BCryptDecrypt
0x180009fcf  nop     dword ptr [rax+rax+00h]
0x180009fd4  mov     esi, eax
0x180009fd6  test    eax, eax
0x180009fd8  jns     short loc_180009FEC
0x180009fda  mov     edx, eax; char *
0x180009fdc  lea     rcx, aBcryptdecryptK; "BCryptDecrypt(key, finalBlockCopy.buffe"...
0x180009fe3  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180009fe8  mov     [rdi], esi
0x180009fea  jmp     short loc_18000A00A
0x180009fec  mov     eax, [rsp+120h+var_D0]
0x180009ff0  cmp     rax, r14
0x180009ff3  jnz     short loc_18000A02F
0x180009ff5  mov     rcx, [rbp+4Fh+Src]; void *
0x180009ff9  mov     r8, r15; Size
0x180009ffc  mov     rdx, rbx; Src
0x180009fff  call    memmove
0x18000a004  mov     dword ptr [rdi], 0
0x18000a00a  test    rbx, rbx
0x18000a00d  jz      short loc_18000A017
0x18000a00f  mov     rcx, rbx
0x18000a012  call    Kerb3961Free
0x18000a017  mov     rax, rdi
0x18000a01a  add     rsp, 0E8h
0x18000a021  pop     r15
0x18000a023  pop     r14
0x18000a025  pop     r13
0x18000a027  pop     r12
0x18000a029  pop     rdi
0x18000a02a  pop     rsi
0x18000a02b  pop     rbx
0x18000a02c  pop     rbp
0x18000a02d  retn
0x18000a02f  lea     rcx, aDecryptedTextS; "Decrypted text shorter than expected.  "...
0x18000a036  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
