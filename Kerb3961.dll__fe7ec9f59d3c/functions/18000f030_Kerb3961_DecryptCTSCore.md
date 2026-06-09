# Kerb3961::DecryptCTSCore

- ea: `0x18000f030`
- end: `0x18000f2bf`
- name: `Kerb3961::DecryptCTSCore`
- size: `655`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18000eee8`

## callees

- `0x180001d64`
- `0x180002fc0`
- `0x1800033f4`
- `0x1800047e4`
- `0x18000712c`
- `0x18000901c`
- `0x18000f030`
- `0x18001d360`

## import_xrefs

- `bcrypt!BCryptDecrypt` at `0x18000f153`
- `bcrypt!BCryptDecrypt` at `0x18000f1ec`
- `bcrypt!BCryptDecrypt` at `0x18000f250`
- `bcrypt!BCryptDecrypt` at `0x18000f153`
- `bcrypt!BCryptDecrypt` at `0x18000f1ec`
- `bcrypt!BCryptDecrypt` at `0x18000f250`

## string_xrefs

- `0x18000f0aa`: `finalBlockCopy`
- `0x18000f25e`: `BCryptDecrypt(key, finalBlockCopy.buffer, static_cast<uint32_t>(finalBlockCopy.length), nullptr, IV.buffer, static_cast<uint32_t>(IV.length), finalBlockCopy.buffer, static_cast<uint32_t>(finalBlockCopy.length), &returnLength, 0)`

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
      operator delete(v16, 0);
      goto LABEL_4;
    }
    if ( pcbResult != v17 )
      goto LABEL_27;
    if ( v18 )
      operator delete(v18, 0);
  }
  memcpy_0(pbOutput, Src, (size_t)v8);
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
  memcpy_0(Src, v26, (size_t)v8);
  *a1 = 0;
LABEL_23:
  if ( v26 )
  {
    v12 = v26;
LABEL_25:
    operator delete(v12, 0);
  }
  return a1;
}

```

## disassembly

```asm
0x18000f030  push    rbp
0x18000f032  push    rbx
0x18000f033  push    rsi
0x18000f034  push    rdi
0x18000f035  push    r12
0x18000f037  push    r13
0x18000f039  push    r14
0x18000f03b  push    r15
0x18000f03d  lea     rbp, [rsp-17h]
0x18000f042  sub     rsp, 0E8h
0x18000f049  mov     rsi, rdx
0x18000f04c  mov     [rbp+4Fh+hKey], r8
0x18000f050  mov     rdi, rcx
0x18000f053  mov     [rbp+4Fh+var_80], r9
0x18000f057  mov     rcx, [rbp+4Fh+arg_20]
0x18000f05b  lea     r8, [rbp+4Fh+var_C0]
0x18000f05f  xor     edx, edx
0x18000f061  mov     [rbp+4Fh+var_88], rcx
0x18000f065  mov     [rbp+4Fh+var_B8], rsi
0x18000f069  mov     r15, [rcx]
0x18000f06c  lea     r12, [r15-1]
0x18000f070  mov     rax, r12
0x18000f073  div     rsi
0x18000f076  sub     r12, rdx
0x18000f079  mov     rdx, rcx
0x18000f07c  mov     rax, r12
0x18000f07f  lea     rcx, [rbp+4Fh+var_78]
0x18000f083  sub     rax, rsi
0x18000f086  sub     r15, r12
0x18000f089  mov     qword ptr [rbp+4Fh+var_C0], rax
0x18000f08d  mov     [rbp+4Fh+var_B0], r15
0x18000f091  call    ??$Split@$02@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$02@utl@@AEBUMutableBinary@0@U?$array@_K$02@2@@Z; Kerb3961::Split<3>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,3>)
0x18000f096  lea     rdx, [rbp+4Fh+cbInput]
0x18000f09a  lea     rcx, [rbp+4Fh+var_A0]
0x18000f09e  call    ?CopyBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@@Z; Kerb3961::CopyBuffer(Kerb3961::ReadOnlyBinary const &)
0x18000f0a3  mov     ebx, dword ptr [rbp+4Fh+var_90]
0x18000f0a6  test    ebx, ebx
0x18000f0a8  jns     short loc_18000F0CC
0x18000f0aa  lea     rcx, aFinalblockcopy; "finalBlockCopy"
0x18000f0b1  mov     edx, ebx; char *
0x18000f0b3  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000f0b8  mov     [rdi], ebx
0x18000f0ba  mov     rcx, [rbp+4Fh+var_98]
0x18000f0be  test    rcx, rcx
0x18000f0c1  jz      loc_18000F29B
0x18000f0c7  jmp     loc_18000F294
0x18000f0cc  mov     r13, [rbp+4Fh+pbInput]
0x18000f0d0  mov     [rsp+120h+var_D0], 0
0x18000f0d8  cmp     r15, rsi
0x18000f0db  jz      loc_18000F199
0x18000f0e1  mov     rdx, rsi
0x18000f0e4  lea     rcx, [rbp+4Fh+var_C0]
0x18000f0e8  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x18000f0ed  mov     ebx, dword ptr [rbp+4Fh+var_B0]
0x18000f0f0  test    ebx, ebx
0x18000f0f2  jns     short loc_18000F116
0x18000f0f4  mov     edx, ebx; char *
0x18000f0f6  lea     rcx, aZeroiv; "zeroIV"
0x18000f0fd  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000f102  mov     rcx, [rbp+4Fh+var_B8]; void *
0x18000f106  mov     [rdi], ebx
0x18000f108  test    rcx, rcx
0x18000f10b  jz      short loc_18000F0BA
0x18000f10d  xor     edx, edx; struct std::nothrow_t *
0x18000f10f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f114  jmp     short loc_18000F0BA
0x18000f116  mov     r14, qword ptr [rbp+4Fh+cbInput]
0x18000f11a  lea     rax, [rsp+120h+var_D0]
0x18000f11f  mov     rbx, [rbp+4Fh+var_B8]
0x18000f123  xor     r9d, r9d; pPaddingInfo
0x18000f126  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18000f12a  mov     r8d, r14d; cbInput
0x18000f12d  mov     [rsp+120h+dwFlags], 0; dwFlags
0x18000f135  mov     rdx, r13; pbInput
0x18000f138  mov     [rsp+120h+pcbResult], rax; pcbResult
0x18000f13d  mov     eax, [rbp+4Fh+var_C0]
0x18000f140  mov     [rsp+120h+cbOutput], r14d; cbOutput
0x18000f145  mov     [rsp+120h+pbOutput], r13; pbOutput
0x18000f14a  mov     [rsp+120h+cbIV], eax; cbIV
0x18000f14e  mov     [rsp+120h+pbIV], rbx; pbIV
0x18000f153  call    cs:__imp_BCryptDecrypt
0x18000f159  mov     esi, eax
0x18000f15b  test    eax, eax
0x18000f15d  jns     short loc_18000F17D
0x18000f15f  mov     edx, eax; char *
0x18000f161  lea     rcx, aBcryptdecryptK_0; "BCryptDecrypt(key, finalBlock.buffer, s"...
0x18000f168  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000f16d  mov     [rdi], esi
0x18000f16f  test    rbx, rbx
0x18000f172  jz      loc_18000F0BA
0x18000f178  mov     rcx, rbx
0x18000f17b  jmp     short loc_18000F10D
0x18000f17d  mov     eax, [rsp+120h+var_D0]
0x18000f181  cmp     rax, r14
0x18000f184  jnz     loc_18000F2B2
0x18000f18a  test    rbx, rbx
0x18000f18d  jz      short loc_18000F199
0x18000f18f  xor     edx, edx; struct std::nothrow_t *
0x18000f191  mov     rcx, rbx; void *
0x18000f194  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f199  mov     rdx, [rbp+4Fh+Src]; Src
0x18000f19d  mov     r8, r15; Size
0x18000f1a0  mov     rcx, r13; void *
0x18000f1a3  call    memcpy_0
0x18000f1a8  mov     rsi, [rbp+4Fh+var_80]
0x18000f1ac  lea     rax, [rsp+120h+var_D0]
0x18000f1b1  mov     rdx, [rbp+4Fh+var_88]
0x18000f1b5  xor     r9d, r9d; pPaddingInfo
0x18000f1b8  mov     r13, [rbp+4Fh+hKey]
0x18000f1bc  mov     r8d, r12d; cbInput
0x18000f1bf  mov     [rsp+120h+dwFlags], 0; dwFlags
0x18000f1c7  mov     rcx, r13; hKey
0x18000f1ca  mov     [rsp+120h+pcbResult], rax; pcbResult
0x18000f1cf  mov     eax, [rsi]
0x18000f1d1  mov     rdx, [rdx+8]; pbInput
0x18000f1d5  mov     [rsp+120h+cbOutput], r12d; cbOutput
0x18000f1da  mov     [rsp+120h+pbOutput], rdx; pbOutput
0x18000f1df  mov     [rsp+120h+cbIV], eax; cbIV
0x18000f1e3  mov     rax, [rsi+8]
0x18000f1e7  mov     [rsp+120h+pbIV], rax; pbIV
0x18000f1ec  call    cs:__imp_BCryptDecrypt
0x18000f1f2  mov     ebx, eax
0x18000f1f4  test    eax, eax
0x18000f1f6  jns     short loc_18000F204
0x18000f1f8  lea     rcx, aBcryptdecryptK_1; "BCryptDecrypt(key, data.buffer, static_"...
0x18000f1ff  jmp     loc_18000F0B1
0x18000f204  mov     eax, [rsp+120h+var_D0]
0x18000f208  cmp     rax, r12
0x18000f20b  jnz     loc_18000F2B2
0x18000f211  mov     r14, qword ptr [rbp+4Fh+var_A0]
0x18000f215  lea     rax, [rsp+120h+var_D0]
0x18000f21a  mov     rbx, [rbp+4Fh+var_98]
0x18000f21e  xor     r9d, r9d; pPaddingInfo
0x18000f221  mov     [rsp+120h+dwFlags], 0; dwFlags
0x18000f229  mov     r8d, r14d; cbInput
0x18000f22c  mov     [rsp+120h+pcbResult], rax; pcbResult
0x18000f231  mov     rdx, rbx; pbInput
0x18000f234  mov     eax, [rsi]
0x18000f236  mov     rcx, r13; hKey
0x18000f239  mov     [rsp+120h+cbOutput], r14d; cbOutput
0x18000f23e  mov     [rsp+120h+pbOutput], rbx; pbOutput
0x18000f243  mov     [rsp+120h+cbIV], eax; cbIV
0x18000f247  mov     rax, [rsi+8]
0x18000f24b  mov     [rsp+120h+pbIV], rax; pbIV
0x18000f250  call    cs:__imp_BCryptDecrypt
0x18000f256  mov     esi, eax
0x18000f258  test    eax, eax
0x18000f25a  jns     short loc_18000F26E
0x18000f25c  mov     edx, eax; char *
0x18000f25e  lea     rcx, aBcryptdecryptK; "BCryptDecrypt(key, finalBlockCopy.buffe"...
0x18000f265  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000f26a  mov     [rdi], esi
0x18000f26c  jmp     short loc_18000F28C
0x18000f26e  mov     eax, [rsp+120h+var_D0]
0x18000f272  cmp     rax, r14
0x18000f275  jnz     short loc_18000F2B2
0x18000f277  mov     rcx, [rbp+4Fh+Src]; void *
0x18000f27b  mov     r8, r15; Size
0x18000f27e  mov     rdx, rbx; Src
0x18000f281  call    memcpy_0
0x18000f286  mov     dword ptr [rdi], 0
0x18000f28c  test    rbx, rbx
0x18000f28f  jz      short loc_18000F29B
0x18000f291  mov     rcx, rbx; void *
0x18000f294  xor     edx, edx; struct std::nothrow_t *
0x18000f296  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f29b  mov     rax, rdi
0x18000f29e  add     rsp, 0E8h
0x18000f2a5  pop     r15
0x18000f2a7  pop     r14
0x18000f2a9  pop     r13
0x18000f2ab  pop     r12
0x18000f2ad  pop     rdi
0x18000f2ae  pop     rsi
0x18000f2af  pop     rbx
0x18000f2b0  pop     rbp
0x18000f2b1  retn
0x18000f2b2  lea     rcx, aDecryptedTextS; "Decrypted text shorter than expected.  "...
0x18000f2b9  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
