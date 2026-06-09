# BCryptExportKey

- ea: `0x180009ba0`
- end: `0x18000a067`
- name: `BCryptExportKey`
- size: `1223`
- prototype: `NTSTATUS __stdcall(BCRYPT_KEY_HANDLE hKey, BCRYPT_KEY_HANDLE hExportKey, LPCWSTR pszBlobType, PUCHAR pbOutput, ULONG cbOutput, ULONG *pcbResult, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180005060`
- `0x180007a7c`
- `0x180009740`
- `0x180009ba0`
- `0x18000e368`
- `0x18000e628`
- `0x18000e910`
- `0x18000edac`
- `0x18000f1fc`
- `0x18000f4b8`
- `0x18001b7b5`
- `0x18001c010`

## string_xrefs

- `0x180009dcb`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180009e15`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180009e55`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180009ed3`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptExportKey(
        BCRYPT_KEY_HANDLE hKey,
        BCRYPT_KEY_HANDLE hExportKey,
        LPCWSTR pszBlobType,
        PUCHAR pbOutput,
        ULONG cbOutput,
        ULONG *pcbResult,
        ULONG dwFlags)
{
  BCRYPT_KEY_HANDLE v9; // rsi
  _QWORD *v11; // r10
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 v15; // r10
  __int64 v16; // r14
  __int64 v17; // rdx
  __int64 (__fastcall *v18)(_QWORD, BCRYPT_KEY_HANDLE, LPCWSTR, PUCHAR, ULONG, ULONG *, ULONG); // rdi
  __int64 v19; // rbp
  int v20; // eax
  NTSTATUS v21; // ebx
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r10
  __int64 v27; // r9
  __int64 v28; // rcx
  __int64 v29; // rcx
  int pcbResulta; // [rsp+C8h] [rbp+30h]

  v9 = hExportKey;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_qqSqdqD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)hExportKey,
      (unsigned int)&WPP_GLOBAL_Control,
      (_DWORD)hKey,
      (char)hExportKey,
      (__int64)pszBlobType,
      (char)pbOutput,
      cbOutput,
      (char)pcbResult,
      dwFlags);
    v11 = WPP_GLOBAL_Control;
  }
  if ( pcbResult && pszBlobType )
  {
    v13 = ValidateBaseKeyHandle(hKey);
    v16 = v13;
    if ( !v13 )
    {
      v27 = 4358;
      goto LABEL_43;
    }
    v17 = *(_QWORD *)(v13 + 8);
    switch ( *(_DWORD *)(v17 + 36) )
    {
      case 1:
        v18 = *(__int64 (__fastcall **)(_QWORD, BCRYPT_KEY_HANDLE, LPCWSTR, PUCHAR, ULONG, ULONG *, ULONG))(v17 + 120);
        goto LABEL_12;
      case 3:
        goto LABEL_11;
      case 4:
        v18 = *(__int64 (__fastcall **)(_QWORD, BCRYPT_KEY_HANDLE, LPCWSTR, PUCHAR, ULONG, ULONG *, ULONG))(v17 + 136);
LABEL_12:
        pcbResulta = 0;
        if ( !v9 )
        {
          v19 = 0;
LABEL_14:
          if ( !wcscmp_0(pszBlobType, L"CAPIPUBLICBLOB") || !wcscmp_0(pszBlobType, L"CAPIPRIVATEBLOB") )
          {
            v20 = ExportLegacyRsaKey(
                    v18,
                    *(_QWORD *)(v16 + 16),
                    v9,
                    pszBlobType,
                    pbOutput,
                    cbOutput,
                    pcbResult,
                    dwFlags);
            v21 = v20;
            if ( v20 >= 0 )
              return v21;
            v27 = 4466;
          }
          else if ( !wcscmp_0(pszBlobType, L"RSAFULLPRIVATEBLOB") )
          {
            v20 = ExportFullRsaKey(
                    (_DWORD)v18,
                    *(_QWORD *)(v16 + 16),
                    (_DWORD)v9,
                    (_DWORD)pbOutput,
                    cbOutput,
                    (__int64)pcbResult,
                    dwFlags);
            v21 = v20;
            if ( v20 >= 0 )
              return v21;
            v27 = 4486;
          }
          else if ( !wcscmp_0(pszBlobType, L"CAPIDSAPUBLICBLOB")
                 || !wcscmp_0(pszBlobType, L"CAPIDSAPRIVATEBLOB")
                 || !wcscmp_0(pszBlobType, L"V2CAPIDSAPUBLICBLOB")
                 || !wcscmp_0(pszBlobType, L"V2CAPIDSAPRIVATEBLOB") )
          {
            v20 = ExportLegacyDsaKey(
                    v18,
                    *(_QWORD *)(v16 + 16),
                    v9,
                    pszBlobType,
                    pbOutput,
                    cbOutput,
                    pcbResult,
                    dwFlags);
            v21 = v20;
            if ( v20 >= 0 )
              return v21;
            v27 = 4517;
          }
          else if ( !wcscmp_0(pszBlobType, L"CAPIDHPUBLICBLOB") || !wcscmp_0(pszBlobType, L"CAPIDHPRIVATEBLOB") )
          {
            v20 = ExportLegacyDhKey(v18, *(_QWORD *)(v16 + 16), v9, pszBlobType, pbOutput, cbOutput, pcbResult, dwFlags);
            v21 = v20;
            if ( v20 >= 0 )
              return v21;
            v27 = 4548;
          }
          else if ( pcbResulta == 1 )
          {
            v20 = RouterAesKeyWrap(v16, v19, pbOutput, cbOutput, pcbResult);
            v21 = v20;
            if ( v20 >= 0 )
              return v21;
            v27 = 4562;
          }
          else
          {
            v20 = v18(*(_QWORD *)(v16 + 16), v9, pszBlobType, pbOutput, cbOutput, pcbResult, dwFlags);
            v21 = v20;
            if ( v20 >= 0 )
              return v21;
            v27 = 4577;
          }
          v28 = (unsigned int)v20;
LABEL_45:
          DebugTraceError(v28, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v27);
          return v21;
        }
        v23 = ValidateBaseKeyHandle(v9);
        v19 = v23;
        if ( !v23 )
        {
          v21 = -1073741816;
          if ( v26 != v25 && (*(_BYTE *)(v26 + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *(_QWORD *)(v26 + 16),
              v24,
              v25,
              (unsigned int)"Status",
              8,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
              54);
          return v21;
        }
        v29 = *(_QWORD *)(v23 + 8);
        if ( *(_DWORD *)(v29 + 36) == 1 )
        {
          if ( *(_QWORD *)(v29 + 40) != *(_QWORD *)(v24 + 40) )
          {
            if ( wcscmp_0(pszBlobType, L"Rfc3565KeyWrapBlob") )
            {
              v21 = -1073741811;
              v27 = 4432;
              v28 = 3221225485LL;
              goto LABEL_45;
            }
            pcbResulta = 1;
          }
          v9 = *(BCRYPT_KEY_HANDLE *)(v19 + 16);
          goto LABEL_14;
        }
        v27 = 4415;
LABEL_43:
        v21 = -1073741816;
        v28 = 3221225480LL;
        goto LABEL_45;
      case 5:
        goto LABEL_11;
      case 7:
        v18 = *(__int64 (__fastcall **)(_QWORD, BCRYPT_KEY_HANDLE, LPCWSTR, PUCHAR, ULONG, ULONG *, ULONG))(v17 + 112);
        goto LABEL_12;
      case 8:
LABEL_11:
        v18 = *(__int64 (__fastcall **)(_QWORD, BCRYPT_KEY_HANDLE, LPCWSTR, PUCHAR, ULONG, ULONG *, ULONG))(v17 + 128);
        goto LABEL_12;
    }
    v21 = -1073741637;
    if ( v15 != v14 && (*(_BYTE *)(v15 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(v15 + 16),
        v17,
        v14,
        (unsigned int)"Status",
        187,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        42);
  }
  else
  {
    v21 = -1073741811;
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        v11[2],
        (_DWORD)hExportKey,
        (unsigned int)&WPP_GLOBAL_Control,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        253);
  }
  return v21;
}

```

## disassembly

```asm
0x180009ba0  push    rbx
0x180009ba2  push    rbp
0x180009ba3  push    rsi
0x180009ba4  push    rdi
0x180009ba5  push    r12
0x180009ba7  push    r13
0x180009ba9  push    r14
0x180009bab  push    r15
0x180009bad  sub     rsp, 58h
0x180009bb1  mov     r12, r9
0x180009bb4  mov     rbx, r8
0x180009bb7  mov     rsi, rdx
0x180009bba  mov     rdi, rcx
0x180009bbd  mov     r10, cs:WPP_GLOBAL_Control
0x180009bc4  lea     r8, WPP_GLOBAL_Control
0x180009bcb  mov     r15, [rsp+98h+pcbResult]
0x180009bd3  mov     r13d, [rsp+98h+cbOutput]
0x180009bdb  cmp     r10, r8
0x180009bde  jz      short loc_180009BEB
0x180009be0  test    byte ptr [r10+1Ch], 4
0x180009be5  jnz     loc_180009E6E
0x180009beb  test    r15, r15
0x180009bee  jz      loc_180009DF4
0x180009bf4  test    rbx, rbx
0x180009bf7  jz      loc_180009DF4
0x180009bfd  mov     rcx, rdi
0x180009c00  call    ValidateBaseKeyHandle
0x180009c05  mov     r14, rax
0x180009c08  test    rax, rax
0x180009c0b  jz      loc_180009EB1
0x180009c11  mov     rdx, [rax+8]
0x180009c15  mov     ecx, [rdx+24h]
0x180009c18  sub     ecx, 1
0x180009c1b  jz      loc_180009D7A
0x180009c21  sub     ecx, 2
0x180009c24  jz      short loc_180009C38
0x180009c26  sub     ecx, 1
0x180009c29  jnz     loc_180009D83
0x180009c2f  mov     rdi, [rdx+88h]
0x180009c36  jmp     short loc_180009C3F
0x180009c38  mov     rdi, [rdx+80h]
0x180009c3f  mov     dword ptr [rsp+98h+pcbResult], 0
0x180009c4a  test    rsi, rsi
0x180009c4d  jnz     loc_180009D9E
0x180009c53  xor     ebp, ebp
0x180009c55  lea     rdx, aCapipublicblob; "CAPIPUBLICBLOB"
0x180009c5c  mov     rcx, rbx; String1
0x180009c5f  call    wcscmp_0
0x180009c64  test    eax, eax
0x180009c66  jz      loc_18000A02C
0x180009c6c  lea     rdx, aCapiprivateblo; "CAPIPRIVATEBLOB"
0x180009c73  mov     rcx, rbx; String1
0x180009c76  call    wcscmp_0
0x180009c7b  test    eax, eax
0x180009c7d  jz      loc_18000A02C
0x180009c83  lea     rdx, aRsafullprivate; "RSAFULLPRIVATEBLOB"
0x180009c8a  mov     rcx, rbx; String1
0x180009c8d  call    wcscmp_0
0x180009c92  test    eax, eax
0x180009c94  jz      loc_180009F38
0x180009c9a  lea     rdx, aCapidsapublicb; "CAPIDSAPUBLICBLOB"
0x180009ca1  mov     rcx, rbx; String1
0x180009ca4  call    wcscmp_0
0x180009ca9  test    eax, eax
0x180009cab  jz      loc_180009FEB
0x180009cb1  lea     rdx, aCapidsaprivate; "CAPIDSAPRIVATEBLOB"
0x180009cb8  mov     rcx, rbx; String1
0x180009cbb  call    wcscmp_0
0x180009cc0  test    eax, eax
0x180009cc2  jz      loc_180009FEB
0x180009cc8  lea     rdx, aV2capidsapubli; "V2CAPIDSAPUBLICBLOB"
0x180009ccf  mov     rcx, rbx; String1
0x180009cd2  call    wcscmp_0
0x180009cd7  test    eax, eax
0x180009cd9  jz      loc_180009FEB
0x180009cdf  lea     rdx, aV2capidsapriva; "V2CAPIDSAPRIVATEBLOB"
0x180009ce6  mov     rcx, rbx; String1
0x180009ce9  call    wcscmp_0
0x180009cee  test    eax, eax
0x180009cf0  jz      loc_180009FEB
0x180009cf6  lea     rdx, aCapidhpublicbl; "CAPIDHPUBLICBLOB"
0x180009cfd  mov     rcx, rbx; String1
0x180009d00  call    wcscmp_0
0x180009d05  test    eax, eax
0x180009d07  jz      loc_180009FAA
0x180009d0d  lea     rdx, aCapidhprivateb; "CAPIDHPRIVATEBLOB"
0x180009d14  mov     rcx, rbx; String1
0x180009d17  call    wcscmp_0
0x180009d1c  test    eax, eax
0x180009d1e  jz      loc_180009FAA
0x180009d24  cmp     dword ptr [rsp+98h+pcbResult], 1
0x180009d2c  jz      loc_180009F74
0x180009d32  mov     eax, [rsp+98h+dwFlags]
0x180009d39  mov     r9, r12
0x180009d3c  mov     rcx, [r14+10h]
0x180009d40  mov     r8, rbx
0x180009d43  mov     dword ptr [rsp+98h+var_68], eax
0x180009d47  mov     rdx, rsi
0x180009d4a  mov     [rsp+98h+var_70], r15
0x180009d4f  mov     rax, rdi
0x180009d52  mov     dword ptr [rsp+98h+var_78], r13d
0x180009d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d5c  mov     ebx, eax
0x180009d5e  test    eax, eax
0x180009d60  js      loc_180009F9F
0x180009d66  mov     eax, ebx
0x180009d68  add     rsp, 58h
0x180009d6c  pop     r15
0x180009d6e  pop     r14
0x180009d70  pop     r13
0x180009d72  pop     r12
0x180009d74  pop     rdi
0x180009d75  pop     rsi
0x180009d76  pop     rbp
0x180009d77  pop     rbx
0x180009d78  retn
0x180009d7a  mov     rdi, [rdx+78h]
0x180009d7e  jmp     loc_180009C3F
0x180009d83  sub     ecx, 1
0x180009d86  jz      loc_180009C38
0x180009d8c  sub     ecx, 2
0x180009d8f  jnz     loc_180009E2B
0x180009d95  mov     rdi, [rdx+70h]
0x180009d99  jmp     loc_180009C3F
0x180009d9e  mov     rcx, rsi
0x180009da1  call    ValidateBaseKeyHandle
0x180009da6  mov     rbp, rax
0x180009da9  test    rax, rax
0x180009dac  jnz     loc_180009EEB
0x180009db2  mov     ebx, 0C0000008h
0x180009db7  cmp     r10, r8
0x180009dba  jz      short loc_180009D66
0x180009dbc  test    byte ptr [r10+1Ch], 1
0x180009dc1  jz      short loc_180009D66
0x180009dc3  mov     dword ptr [rsp+98h+var_68], 1136h
0x180009dcb  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009dd2  mov     [rsp+98h+var_70], rax
0x180009dd7  mov     dword ptr [rsp+98h+var_78], 0C0000008h
0x180009ddf  mov     rcx, [r10+10h]
0x180009de3  lea     r9, aStatus; "Status"
0x180009dea  call    WPP_SF_sDsd
0x180009def  jmp     loc_180009D66
0x180009df4  mov     ebx, 0C000000Dh
0x180009df9  cmp     r10, r8
0x180009dfc  jz      loc_180009D66
0x180009e02  test    byte ptr [r10+1Ch], 1
0x180009e07  jz      loc_180009D66
0x180009e0d  mov     dword ptr [rsp+98h+var_68], 10FDh
0x180009e15  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009e1c  mov     [rsp+98h+var_70], rax
0x180009e21  mov     dword ptr [rsp+98h+var_78], 0C000000Dh
0x180009e29  jmp     short loc_180009DDF
0x180009e2b  cmp     ecx, 1
0x180009e2e  jz      loc_180009C38
0x180009e34  mov     ebx, 0C00000BBh
0x180009e39  cmp     r10, r8
0x180009e3c  jz      loc_180009D66
0x180009e42  test    byte ptr [r10+1Ch], 1
0x180009e47  jz      loc_180009D66
0x180009e4d  mov     dword ptr [rsp+98h+var_68], 112Ah
0x180009e55  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009e5c  mov     [rsp+98h+var_70], rax
0x180009e61  mov     dword ptr [rsp+98h+var_78], 0C00000BBh
0x180009e69  jmp     loc_180009DDF
0x180009e6e  mov     eax, [rsp+98h+dwFlags]
0x180009e75  mov     r9, rdi
0x180009e78  mov     rcx, [r10+10h]
0x180009e7c  mov     [rsp+98h+var_50], eax
0x180009e80  mov     [rsp+98h+var_58], r15
0x180009e85  mov     [rsp+98h+var_60], r13d
0x180009e8a  mov     [rsp+98h+var_68], r12
0x180009e8f  mov     [rsp+98h+var_70], rbx
0x180009e94  mov     [rsp+98h+var_78], rsi
0x180009e99  call    WPP_SF_qqSqdqD
0x180009e9e  mov     r10, cs:WPP_GLOBAL_Control
0x180009ea5  lea     r8, WPP_GLOBAL_Control
0x180009eac  jmp     loc_180009BEB
0x180009eb1  mov     r9d, 1106h
0x180009eb7  jmp     short loc_180009EBF
0x180009eb9  mov     r9d, 113Fh
0x180009ebf  mov     ebx, 0C0000008h
0x180009ec4  mov     ecx, 0C0000008h
0x180009ec9  jmp     short loc_180009ED3
0x180009ecb  mov     r9d, 1172h
0x180009ed1  mov     ecx, eax
0x180009ed3  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009eda  lea     rdx, aStatus; "Status"
0x180009ee1  call    DebugTraceError
0x180009ee6  jmp     loc_180009D66
0x180009eeb  mov     rcx, [rax+8]
0x180009eef  cmp     dword ptr [rcx+24h], 1
0x180009ef3  jnz     short loc_180009EB9
0x180009ef5  mov     rax, [rdx+28h]
0x180009ef9  cmp     [rcx+28h], rax
0x180009efd  jz      short loc_180009F1D
0x180009eff  lea     rdx, aRfc3565keywrap; "Rfc3565KeyWrapBlob"
0x180009f06  mov     rcx, rbx; String1
0x180009f09  call    wcscmp_0
0x180009f0e  test    eax, eax
0x180009f10  jnz     short loc_180009F26
0x180009f12  mov     dword ptr [rsp+98h+pcbResult], 1
0x180009f1d  mov     rsi, [rbp+10h]
0x180009f21  jmp     loc_180009C55
0x180009f26  mov     ebx, 0C000000Dh
0x180009f2b  mov     r9d, 1150h
0x180009f31  mov     ecx, 0C000000Dh
0x180009f36  jmp     short loc_180009ED3
0x180009f38  mov     eax, [rsp+98h+dwFlags]
0x180009f3f  mov     r9, r12
0x180009f42  mov     rdx, [r14+10h]
0x180009f46  mov     r8, rsi
0x180009f49  mov     dword ptr [rsp+98h+var_68], eax
0x180009f4d  mov     rcx, rdi
0x180009f50  mov     [rsp+98h+var_70], r15
0x180009f55  mov     dword ptr [rsp+98h+var_78], r13d
0x180009f5a  call    ExportFullRsaKey
0x180009f5f  mov     ebx, eax
0x180009f61  test    eax, eax
0x180009f63  jns     loc_180009D66
0x180009f69  mov     r9d, 1186h
0x180009f6f  jmp     loc_180009ED1
0x180009f74  mov     r9d, r13d
0x180009f77  mov     [rsp+98h+var_78], r15
0x180009f7c  mov     r8, r12
0x180009f7f  mov     rdx, rbp
0x180009f82  mov     rcx, r14
0x180009f85  call    RouterAesKeyWrap
0x180009f8a  mov     ebx, eax
0x180009f8c  test    eax, eax
0x180009f8e  jns     loc_180009D66
0x180009f94  mov     r9d, 11D2h
0x180009f9a  jmp     loc_180009ED1
0x180009f9f  mov     r9d, 11E1h
0x180009fa5  jmp     loc_180009ED1
0x180009faa  mov     eax, [rsp+98h+dwFlags]
0x180009fb1  mov     r9, rbx
0x180009fb4  mov     rdx, [r14+10h]
0x180009fb8  mov     r8, rsi
0x180009fbb  mov     [rsp+98h+var_60], eax
0x180009fbf  mov     rcx, rdi
0x180009fc2  mov     [rsp+98h+var_68], r15
0x180009fc7  mov     dword ptr [rsp+98h+var_70], r13d
0x180009fcc  mov     [rsp+98h+var_78], r12
0x180009fd1  call    ExportLegacyDhKey
0x180009fd6  mov     ebx, eax
0x180009fd8  test    eax, eax
0x180009fda  jns     loc_180009D66
0x180009fe0  mov     r9d, 11C4h
0x180009fe6  jmp     loc_180009ED1
0x180009feb  mov     eax, [rsp+98h+dwFlags]
0x180009ff2  mov     r9, rbx
0x180009ff5  mov     rdx, [r14+10h]
0x180009ff9  mov     r8, rsi
0x180009ffc  mov     [rsp+98h+var_60], eax
0x18000a000  mov     rcx, rdi
0x18000a003  mov     [rsp+98h+var_68], r15
0x18000a008  mov     dword ptr [rsp+98h+var_70], r13d
0x18000a00d  mov     [rsp+98h+var_78], r12
0x18000a012  call    ExportLegacyDsaKey
0x18000a017  mov     ebx, eax
0x18000a019  test    eax, eax
0x18000a01b  jns     loc_180009D66
0x18000a021  mov     r9d, 11A5h
0x18000a027  jmp     loc_180009ED1
0x18000a02c  mov     eax, [rsp+98h+dwFlags]
0x18000a033  mov     r9, rbx
0x18000a036  mov     rdx, [r14+10h]
0x18000a03a  mov     r8, rsi
0x18000a03d  mov     [rsp+98h+var_60], eax
0x18000a041  mov     rcx, rdi
0x18000a044  mov     [rsp+98h+var_68], r15
0x18000a049  mov     dword ptr [rsp+98h+var_70], r13d
0x18000a04e  mov     [rsp+98h+var_78], r12
0x18000a053  call    ExportLegacyRsaKey
0x18000a058  mov     ebx, eax
0x18000a05a  test    eax, eax
0x18000a05c  jns     loc_180009D66
0x18000a062  jmp     loc_180009ECB
```
