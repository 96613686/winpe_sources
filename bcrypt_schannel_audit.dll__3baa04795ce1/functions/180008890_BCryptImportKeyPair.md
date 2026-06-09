# BCryptImportKeyPair

- ea: `0x180008890`
- end: `0x180009091`
- name: `BCryptImportKeyPair`
- size: `2049`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE hAlgorithm, BCRYPT_KEY_HANDLE hImportKey, LPCWSTR pszBlobType, BCRYPT_KEY_HANDLE *phKey, PUCHAR pbInput, ULONG cbInput, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004200`
- `0x180005060`
- `0x180006bd0`
- `0x180007a7c`
- `0x180008890`
- `0x180009430`
- `0x180009454`
- `0x180009740`
- `0x18000df40`
- `0x18000e7fc`
- `0x180012318`
- `0x180015730`
- `0x1800180d8`
- `0x180018270`
- `0x18001b7b5`
- `0x18001c010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180008915`
- `ntdll!RtlAllocateHeap` at `0x180008915`

## string_xrefs

- `0x180008af6`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180008b3e`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180008bd4`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180008cde`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180008d94`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180008fb8`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180008ffe`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000903c`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000906f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180008ab0`: `onecore\ds\security\cryptoapi\ncrypt\translate\bcrypttranslate.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptImportKeyPair(
        BCRYPT_ALG_HANDLE hAlgorithm,
        BCRYPT_KEY_HANDLE hImportKey,
        LPCWSTR pszBlobType,
        BCRYPT_KEY_HANDLE *phKey,
        PUCHAR pbInput,
        ULONG cbInput,
        ULONG dwFlags)
{
  const wchar_t *v8; // rsi
  int v11; // edx
  __int64 v12; // rbx
  char *Heap; // rax
  char *v14; // rdi
  __int64 v15; // rbp
  int v16; // eax
  __int64 (__fastcall *v17)(_QWORD, __int64, const wchar_t *, char *, PUCHAR, ULONG, ULONG); // rax
  __int64 v18; // r13
  PUCHAR v19; // rax
  int v20; // eax
  int v21; // esi
  int v23; // edx
  int v24; // r8d
  _QWORD *v25; // rcx
  int v26; // eax
  int v27; // eax
  int v28; // edx
  unsigned int v29; // eax
  ULONG v30; // esi
  int v31; // eax
  int v32; // edx
  __int64 v33; // rax
  int v34; // edx
  __int64 v35; // r13
  ULONG v36; // esi
  int v37; // eax
  __int64 v38; // r12
  int v39; // eax
  int v40; // ecx
  __int64 v41; // rcx
  ULONG v42; // esi
  ULONG v43; // esi
  ULONG v44; // esi
  ULONG v45; // [rsp+50h] [rbp-38h] BYREF
  __int64 (__fastcall *v46)(_QWORD, __int64, const wchar_t *, char *, PUCHAR, ULONG, ULONG); // [rsp+58h] [rbp-30h]

  v45 = 0;
  v8 = pszBlobType;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_qqSqqdD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)hImportKey,
      (_DWORD)pszBlobType,
      (_DWORD)hAlgorithm,
      (char)hImportKey,
      (__int64)pszBlobType,
      (char)phKey,
      (char)pbInput,
      cbInput,
      dwFlags);
  v12 = ValidateBaseAlgHandle(hAlgorithm);
  if ( v12 )
  {
    if ( phKey && v8 )
    {
      Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x20u);
      v14 = Heap;
      if ( !Heap )
      {
        v21 = -1073741801;
        DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
        return v21;
      }
      v15 = 0;
      *(_DWORD *)Heap = 32;
      *((_DWORD *)Heap + 1) = 1431655762;
      *((_QWORD *)Heap + 1) = v12;
      v16 = *(_DWORD *)(v12 + 36);
      if ( v16 != 3 )
      {
        v26 = v16 - 4;
        if ( !v26 )
        {
          v17 = *(__int64 (__fastcall **)(_QWORD, __int64, const wchar_t *, char *, PUCHAR, ULONG, ULONG))(v12 + 128);
LABEL_10:
          v18 = 0;
          v46 = v17;
          if ( hImportKey )
          {
            v33 = ValidateBaseKeyHandle(hImportKey);
            v35 = v33;
            if ( !v33 )
            {
              v21 = -1073741816;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v34,
                  (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
                  (unsigned int)"Status",
                  8,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
                  70);
              }
              goto LABEL_41;
            }
            v38 = *(_QWORD *)(v33 + 8);
            v39 = wcscmp_0(v8, L"PKCS11RsaAesWrapBlob");
            v40 = 3;
            if ( v39 )
              v40 = 1;
            if ( !v38 )
            {
              v21 = -1073739510;
              v41 = 3221227786LL;
              goto LABEL_86;
            }
            if ( *(_DWORD *)(v38 + 36) != v40 )
            {
              v21 = -1073741816;
              v41 = 3221225480LL;
              goto LABEL_86;
            }
            if ( *(_QWORD *)(v38 + 40) != *(_QWORD *)(v12 + 40) )
            {
              v21 = -1073741788;
              v41 = 3221225508LL;
              goto LABEL_86;
            }
            v18 = *(_QWORD *)(v35 + 16);
          }
          if ( wcscmp_0(v8, L"RSAFULLPRIVATEBLOB") )
          {
            if ( wcscmp_0(v8, L"CAPIPRIVATEBLOB") )
            {
              if ( !wcscmp_0(v8, L"CAPIDSAPRIVATEBLOB") )
              {
                v29 = ConvertLegacyDsaPrivateBlob(pbInput, cbInput, 0, 0, &v45);
                v21 = v29;
                if ( v29 )
                  goto LABEL_83;
                v42 = v45;
                v15 = SafeAllocaAllocateFromHeap(v45);
                if ( !v15 )
                  goto LABEL_81;
                v29 = ConvertLegacyDsaPrivateBlob(pbInput, cbInput, v15, v42, &v45);
                v21 = v29;
                if ( v29 )
                  goto LABEL_83;
              }
              else
              {
                if ( !wcscmp_0(v8, L"CAPIDHPRIVATEBLOB") )
                {
                  v29 = ConvertLegacyDhPrivateBlob(pbInput, cbInput, 0, 0, &v45);
                  v21 = v29;
                  if ( v29 )
                    goto LABEL_83;
                  v43 = v45;
                  v15 = SafeAllocaAllocateFromHeap(v45);
                  if ( !v15 )
                    goto LABEL_81;
                  v29 = ConvertLegacyDhPrivateBlob(pbInput, cbInput, v15, v43, &v45);
                  v21 = v29;
                  if ( v29 )
                    goto LABEL_83;
                  v8 = L"DHPRIVATEBLOB";
                  cbInput = v45;
                  v19 = (PUCHAR)v15;
LABEL_17:
                  v20 = v46(*(_QWORD *)(v12 + 24), v18, v8, v14 + 16, v19, cbInput, dwFlags);
                  v21 = v20;
                  if ( v20 >= 0 )
                  {
                    *phKey = v14;
                    v14 = 0;
                    v21 = 0;
                    goto LABEL_19;
                  }
                  goto LABEL_85;
                }
                if ( wcscmp_0(v8, L"V2CAPIDSAPRIVATEBLOB") )
                {
                  v19 = pbInput;
                  goto LABEL_17;
                }
                v27 = ConvertLegacyDsaV2PrivateBlob(pbInput, cbInput, 0, 0, &v45);
                v21 = v27;
                if ( v27 )
                {
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    WPP_SF_sDsd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      v28,
                      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
                      (unsigned int)"Status",
                      v27,
                      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
                      43);
                  }
                  goto LABEL_40;
                }
                v44 = v45;
                v15 = SafeAllocaAllocateFromHeap(v45);
                if ( !v15 )
                {
LABEL_81:
                  v21 = -1073741801;
                  DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
                  goto LABEL_41;
                }
                v29 = ConvertLegacyDsaV2PrivateBlob(pbInput, cbInput, v15, v44, &v45);
                v21 = v29;
                if ( v29 )
                {
LABEL_83:
                  DebugTraceError(v29, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
                  goto LABEL_40;
                }
              }
              v8 = L"DSAPRIVATEBLOB";
              cbInput = v45;
              v19 = (PUCHAR)v15;
              goto LABEL_17;
            }
            v29 = ConvertLegacyRsaPrivateBlob(pbInput, cbInput, 0, 0, &v45);
            v21 = v29;
            if ( v29 )
              goto LABEL_83;
            v30 = v45;
            v15 = SafeAllocaAllocateFromHeap(v45);
            if ( !v15 )
              goto LABEL_81;
            v31 = ConvertLegacyRsaPrivateBlob(pbInput, cbInput, v15, v30, &v45);
            v21 = v31;
            if ( v31 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v32,
                  (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
                  (unsigned int)"Status",
                  v31,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
                  185);
              }
LABEL_40:
              if ( v21 >= 0 )
              {
LABEL_19:
                _InterlockedIncrement((volatile signed __int32 *)(v12 + 16));
                if ( !v14 )
                  goto LABEL_20;
              }
LABEL_41:
              MSCryptFree(v14);
LABEL_20:
              if ( v15 )
                MSCryptFree(v15);
              return v21;
            }
LABEL_54:
            v8 = L"RSAPRIVATEBLOB";
            cbInput = v45;
            v19 = (PUCHAR)v15;
            goto LABEL_17;
          }
          v45 = 0;
          v21 = VerifyRsaFullPrivateBlob(pbInput, cbInput, &v45);
          if ( v21 < 0 )
          {
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v23,
                  v24,
                  (unsigned int)"Status",
                  v21,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c",
                  73);
                v25 = WPP_GLOBAL_Control;
              }
              if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 1) != 0 )
                WPP_SF_sDsd(
                  v25[2],
                  v23,
                  (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
                  (unsigned int)"Status",
                  v21,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
                  117);
            }
            goto LABEL_41;
          }
          v36 = v45;
          v15 = SafeAllocaAllocateFromHeap(v45);
          if ( v15 )
          {
            v20 = ConvertRsaFullPrivateBlob(pbInput, cbInput, v15, v36, &v45);
            v21 = v20;
            if ( v20 < 0 )
            {
LABEL_85:
              v41 = (unsigned int)v20;
              goto LABEL_86;
            }
            goto LABEL_54;
          }
          v21 = -1073741801;
          v41 = 3221225495LL;
LABEL_86:
          DebugTraceError(v41, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
          goto LABEL_41;
        }
        v37 = v26 - 1;
        if ( v37 && v37 != 3 )
        {
          v21 = -1073741637;
          goto LABEL_41;
        }
      }
      v17 = *(__int64 (__fastcall **)(_QWORD, __int64, const wchar_t *, char *, PUCHAR, ULONG, ULONG))(v12 + 120);
      goto LABEL_10;
    }
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
    return -1073741811;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        250);
    return -1073741816;
  }
}

```

## disassembly

```asm
0x180008890  mov     [rsp+arg_10], rbx
0x180008895  push    rsi
0x180008896  push    rdi
0x180008897  push    r12
0x180008899  push    r14
0x18000889b  push    r15
0x18000889d  sub     rsp, 60h
0x1800088a1  mov     r15, r9
0x1800088a4  mov     [rsp+88h+var_38], 0
0x1800088ac  mov     rsi, r8
0x1800088af  mov     r12, rdx
0x1800088b2  mov     rbx, rcx
0x1800088b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800088bc  lea     rdi, WPP_GLOBAL_Control
0x1800088c3  mov     r14, [rsp+88h+pbInput]
0x1800088cb  cmp     rcx, rdi
0x1800088ce  jz      short loc_1800088DA
0x1800088d0  test    byte ptr [rcx+1Ch], 4
0x1800088d4  jnz     loc_180008D53
0x1800088da  mov     rcx, rbx
0x1800088dd  call    ValidateBaseAlgHandle
0x1800088e2  mov     rbx, rax
0x1800088e5  test    rax, rax
0x1800088e8  jz      loc_180008B23
0x1800088ee  test    r15, r15
0x1800088f1  jz      loc_180009069
0x1800088f7  test    rsi, rsi
0x1800088fa  jz      loc_180009069
0x180008900  mov     rcx, gs:60h
0x180008909  xor     edx, edx; Flags
0x18000890b  mov     r8d, 20h ; ' '; Size
0x180008911  mov     rcx, [rcx+30h]; HeapHandle
0x180008915  call    cs:__imp_RtlAllocateHeap
0x18000891c  nop     dword ptr [rax+rax+00h]
0x180008921  mov     rdi, rax
0x180008924  test    rax, rax
0x180008927  jz      loc_180008D8E
0x18000892d  mov     [rsp+88h+arg_0], rbp
0x180008935  xor     ebp, ebp
0x180008937  mov     dword ptr [rax], 20h ; ' '
0x18000893d  mov     dword ptr [rax+4], 55555552h
0x180008944  mov     [rax+8], rbx
0x180008948  mov     eax, [rbx+24h]
0x18000894b  mov     [rsp+88h+arg_8], r13
0x180008953  cmp     eax, 3
0x180008956  jnz     loc_180008B6D
0x18000895c  mov     rax, [rbx+78h]
0x180008960  xor     r13d, r13d
0x180008963  mov     [rsp+88h+var_30], rax
0x180008968  test    r12, r12
0x18000896b  jnz     loc_180008C9C
0x180008971  lea     rdx, aRsafullprivate; "RSAFULLPRIVATEBLOB"
0x180008978  mov     rcx, rsi; String1
0x18000897b  call    wcscmp_0
0x180008980  test    eax, eax
0x180008982  jz      loc_180008A69
0x180008988  lea     rdx, aCapiprivateblo; "CAPIPRIVATEBLOB"
0x18000898f  mov     rcx, rsi; String1
0x180008992  call    wcscmp_0
0x180008997  test    eax, eax
0x180008999  jz      loc_180008C05
0x18000899f  lea     rdx, aCapidsaprivate; "CAPIDSAPRIVATEBLOB"
0x1800089a6  mov     rcx, rsi; String1
0x1800089a9  call    wcscmp_0
0x1800089ae  test    eax, eax
0x1800089b0  jz      loc_180008E89
0x1800089b6  lea     rdx, aCapidhprivateb; "CAPIDHPRIVATEBLOB"
0x1800089bd  mov     rcx, rsi; String1
0x1800089c0  call    wcscmp_0
0x1800089c5  test    eax, eax
0x1800089c7  jz      loc_180008F0B
0x1800089cd  lea     rdx, aV2capidsapriva; "V2CAPIDSAPRIVATEBLOB"
0x1800089d4  mov     rcx, rsi; String1
0x1800089d7  call    wcscmp_0
0x1800089dc  test    eax, eax
0x1800089de  jz      loc_180008B82
0x1800089e4  mov     rax, r14
0x1800089e7  mov     ecx, [rsp+88h+dwFlags]
0x1800089ee  lea     r9, [rdi+10h]
0x1800089f2  mov     dword ptr [rsp+88h+var_58], ecx
0x1800089f6  mov     r8, rsi
0x1800089f9  mov     ecx, [rsp+88h+cbInput]
0x180008a00  mov     rdx, r13
0x180008a03  mov     dword ptr [rsp+88h+var_60], ecx
0x180008a07  mov     rcx, [rbx+18h]
0x180008a0b  mov     [rsp+88h+var_68], rax
0x180008a10  mov     rax, [rsp+88h+var_30]
0x180008a15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a1a  mov     esi, eax
0x180008a1c  test    eax, eax
0x180008a1e  js      loc_180009034
0x180008a24  mov     [r15], rdi
0x180008a27  xor     edi, edi
0x180008a29  xor     esi, esi
0x180008a2b  lock inc dword ptr [rbx+10h]
0x180008a2f  test    rdi, rdi
0x180008a32  jnz     loc_18000904F
0x180008a38  mov     r13, [rsp+88h+arg_8]
0x180008a40  test    rbp, rbp
0x180008a43  jnz     loc_18000905C
0x180008a49  mov     rbp, [rsp+88h+arg_0]
0x180008a51  mov     eax, esi
0x180008a53  mov     rbx, [rsp+88h+arg_10]
0x180008a5b  add     rsp, 60h
0x180008a5f  pop     r15
0x180008a61  pop     r14
0x180008a63  pop     r12
0x180008a65  pop     rdi
0x180008a66  pop     rsi
0x180008a67  retn
0x180008a69  mov     r12d, [rsp+88h+cbInput]
0x180008a71  lea     r8, [rsp+88h+var_38]
0x180008a76  mov     edx, r12d
0x180008a79  mov     [rsp+88h+var_38], ebp
0x180008a7d  mov     rcx, r14
0x180008a80  call    VerifyRsaFullPrivateBlob
0x180008a85  mov     esi, eax
0x180008a87  test    eax, eax
0x180008a89  jns     loc_180008CF7
0x180008a8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a96  lea     r15, WPP_GLOBAL_Control
0x180008a9d  cmp     rcx, r15
0x180008aa0  jz      loc_18000904F
0x180008aa6  test    byte ptr [rcx+1Ch], 1
0x180008aaa  jz      short loc_180008ADB
0x180008aac  mov     rcx, [rcx+10h]
0x180008ab0  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008ab7  mov     dword ptr [rsp+88h+var_58], 449h
0x180008abf  lea     r9, aStatus; "Status"
0x180008ac6  mov     [rsp+88h+var_60], rax
0x180008acb  mov     dword ptr [rsp+88h+var_68], esi
0x180008acf  call    WPP_SF_sDsd
0x180008ad4  mov     rcx, cs:WPP_GLOBAL_Control
0x180008adb  cmp     rcx, r15
0x180008ade  jz      loc_18000904F
0x180008ae4  test    byte ptr [rcx+1Ch], 1
0x180008ae8  jz      loc_18000904F
0x180008aee  mov     dword ptr [rsp+88h+var_58], 1375h
0x180008af6  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008afd  mov     [rsp+88h+var_60], r8
0x180008b02  mov     dword ptr [rsp+88h+var_68], esi
0x180008b06  mov     rcx, [rcx+10h]
0x180008b0a  lea     r9, aStatus; "Status"
0x180008b11  call    WPP_SF_sDsd
0x180008b16  mov     rcx, rdi
0x180008b19  call    MSCryptFree
0x180008b1e  jmp     loc_180008A38
0x180008b23  mov     esi, 0C0000008h
0x180008b28  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b2f  cmp     rcx, rdi
0x180008b32  jz      short loc_180008B66
0x180008b34  test    byte ptr [rcx+1Ch], 1
0x180008b38  jz      short loc_180008B66
0x180008b3a  mov     rcx, [rcx+10h]
0x180008b3e  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008b45  mov     dword ptr [rsp+88h+var_58], 12FAh
0x180008b4d  lea     r9, aStatus; "Status"
0x180008b54  mov     [rsp+88h+var_60], r8
0x180008b59  mov     dword ptr [rsp+88h+var_68], 0C0000008h
0x180008b61  call    WPP_SF_sDsd
0x180008b66  mov     eax, esi
0x180008b68  jmp     loc_180008A53
0x180008b6d  sub     eax, 4
0x180008b70  jnz     loc_180008DB6
0x180008b76  mov     rax, [rbx+80h]
0x180008b7d  jmp     loc_180008960
0x180008b82  mov     r12d, [rsp+88h+cbInput]
0x180008b8a  lea     rax, [rsp+88h+var_38]
0x180008b8f  mov     edx, r12d
0x180008b92  mov     [rsp+88h+var_68], rax
0x180008b97  xor     r9d, r9d
0x180008b9a  xor     r8d, r8d
0x180008b9d  mov     rcx, r14
0x180008ba0  call    ConvertLegacyDsaV2PrivateBlob
0x180008ba5  mov     esi, eax
0x180008ba7  test    eax, eax
0x180008ba9  jz      loc_180008F9F
0x180008baf  mov     rcx, cs:WPP_GLOBAL_Control
0x180008bb6  lea     r15, WPP_GLOBAL_Control
0x180008bbd  cmp     rcx, r15
0x180008bc0  jz      short loc_180008BF0
0x180008bc2  test    byte ptr [rcx+1Ch], 1
0x180008bc6  jz      short loc_180008BF0
0x180008bc8  mov     dword ptr [rsp+88h+var_58], 142Bh
0x180008bd0  mov     rcx, [rcx+10h]
0x180008bd4  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008bdb  mov     [rsp+88h+var_60], r8
0x180008be0  lea     r9, aStatus; "Status"
0x180008be7  mov     dword ptr [rsp+88h+var_68], eax
0x180008beb  call    WPP_SF_sDsd
0x180008bf0  test    esi, esi
0x180008bf2  jns     loc_180008A2B
0x180008bf8  mov     rcx, rdi
0x180008bfb  call    MSCryptFree
0x180008c00  jmp     loc_180008A38
0x180008c05  mov     r12d, [rsp+88h+cbInput]
0x180008c0d  lea     rax, [rsp+88h+var_38]
0x180008c12  mov     edx, r12d
0x180008c15  mov     [rsp+88h+var_68], rax
0x180008c1a  xor     r9d, r9d
0x180008c1d  xor     r8d, r8d
0x180008c20  mov     rcx, r14
0x180008c23  call    ConvertLegacyRsaPrivateBlob
0x180008c28  mov     esi, eax
0x180008c2a  test    eax, eax
0x180008c2c  jnz     loc_180008E73
0x180008c32  mov     esi, [rsp+88h+var_38]
0x180008c36  mov     ecx, esi
0x180008c38  call    SafeAllocaAllocateFromHeap
0x180008c3d  mov     rbp, rax
0x180008c40  test    rax, rax
0x180008c43  jz      loc_180008E7E
0x180008c49  lea     rax, [rsp+88h+var_38]
0x180008c4e  mov     r9d, esi
0x180008c51  mov     r8, rbp
0x180008c54  mov     [rsp+88h+var_68], rax
0x180008c59  mov     edx, r12d
0x180008c5c  mov     rcx, r14
0x180008c5f  call    ConvertLegacyRsaPrivateBlob
0x180008c64  mov     esi, eax
0x180008c66  test    eax, eax
0x180008c68  jz      loc_180008D37
0x180008c6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c75  lea     r15, WPP_GLOBAL_Control
0x180008c7c  cmp     rcx, r15
0x180008c7f  jz      loc_180008BF0
0x180008c85  test    byte ptr [rcx+1Ch], 1
0x180008c89  jz      loc_180008BF0
0x180008c8f  mov     dword ptr [rsp+88h+var_58], 13B9h
0x180008c97  jmp     loc_180008BD0
0x180008c9c  mov     rcx, r12
0x180008c9f  call    ValidateBaseKeyHandle
0x180008ca4  mov     r13, rax
0x180008ca7  test    rax, rax
0x180008caa  jnz     loc_180008DD2
0x180008cb0  mov     esi, 0C0000008h
0x180008cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180008cbc  lea     r15, WPP_GLOBAL_Control
0x180008cc3  cmp     rcx, r15
0x180008cc6  jz      loc_18000904F
0x180008ccc  test    byte ptr [rcx+1Ch], 1
0x180008cd0  jz      loc_18000904F
0x180008cd6  mov     dword ptr [rsp+88h+var_58], 1346h
0x180008cde  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008ce5  mov     [rsp+88h+var_60], r8
0x180008cea  mov     dword ptr [rsp+88h+var_68], 0C0000008h
0x180008cf2  jmp     loc_180008B06
0x180008cf7  mov     esi, [rsp+88h+var_38]
0x180008cfb  mov     ecx, esi
0x180008cfd  mov     [rsp+88h+var_38], esi
0x180008d01  call    SafeAllocaAllocateFromHeap
0x180008d06  mov     rbp, rax
0x180008d09  test    rax, rax
0x180008d0c  jz      loc_180008E53
0x180008d12  lea     rax, [rsp+88h+var_38]
0x180008d17  mov     r9d, esi
0x180008d1a  mov     r8, rbp
0x180008d1d  mov     [rsp+88h+var_68], rax
0x180008d22  mov     edx, r12d
0x180008d25  mov     rcx, r14
0x180008d28  call    ConvertRsaFullPrivateBlob
0x180008d2d  mov     esi, eax
0x180008d2f  test    eax, eax
0x180008d31  js      loc_180008E68
0x180008d37  mov     r9d, [rsp+88h+var_38]
0x180008d3c  lea     rsi, aRsaprivateblob; "RSAPRIVATEBLOB"
0x180008d43  mov     [rsp+88h+cbInput], r9d
0x180008d4b  mov     rax, rbp
0x180008d4e  jmp     loc_1800089E7
0x180008d53  mov     eax, [rsp+88h+dwFlags]
0x180008d5a  mov     r9, rbx
0x180008d5d  mov     rcx, [rcx+10h]
0x180008d61  mov     [rsp+88h+var_40], eax
0x180008d65  mov     eax, [rsp+88h+cbInput]
0x180008d6c  mov     [rsp+88h+var_48], eax
0x180008d70  mov     [rsp+88h+var_50], r14
0x180008d75  mov     [rsp+88h+var_58], r15
0x180008d7a  mov     [rsp+88h+var_60], rsi
0x180008d7f  mov     [rsp+88h+var_68], r12
0x180008d84  call    WPP_SF_qqSqqdD
0x180008d89  jmp     loc_1800088DA
0x180008d8e  mov     r9d, 131Ch
0x180008d94  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008d9b  lea     rdx, aStatus; "Status"
0x180008da2  mov     ecx, 0C0000017h
0x180008da7  mov     esi, 0C0000017h
0x180008dac  call    DebugTraceError
0x180008db1  jmp     loc_180008A51
0x180008db6  sub     eax, 1
0x180008db9  jz      loc_18000895C
0x180008dbf  cmp     eax, 3
0x180008dc2  jz      loc_18000895C
0x180008dc8  mov     esi, 0C00000BBh
0x180008dcd  jmp     loc_18000904F
0x180008dd2  mov     r12, [rax+8]
0x180008dd6  lea     rdx, aPkcs11rsaaeswr; "PKCS11RsaAesWrapBlob"
0x180008ddd  mov     rcx, rsi; String1
0x180008de0  call    wcscmp_0
0x180008de5  test    eax, eax
0x180008de7  mov     ecx, 3
  ... truncated ...
```
