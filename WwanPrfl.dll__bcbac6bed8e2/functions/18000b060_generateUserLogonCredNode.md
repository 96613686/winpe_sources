# _generateUserLogonCredNode

- ea: `0x18000b060`
- end: `0x18000b4a9`
- name: `_generateUserLogonCredNode`
- size: `1097`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMNode *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800092fc`

## callees

- `0x180001670`
- `0x180002034`
- `0x180009220`
- `0x18000b060`
- `0x180011f90`
- `0x180012310`
- `0x1800123d4`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2b3`
- `CRYPT32!CryptProtectData` at `0x18000b2a9`
- `CRYPT32!CryptProtectData` at `0x18000b2a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b2c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b339`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b2c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b339`

## string_xrefs

- `0x18000b0a8`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x18000b0ba`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x18000b111`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x18000b17e`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x18000b21c`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x18000b2f2`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x18000b3be`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x18000b418`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x18000b0a1`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000b188`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000b226`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000b2fc`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000b3c8`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000b422`: `http://www.microsoft.com/networking/WWAN/profile/v1`

## pseudocode

```c
__int64 __fastcall generateUserLogonCredNode(
        struct IXMLDOMDocument2 *a1,
        struct IXMLDOMNode *a2,
        __int64 a3,
        unsigned int a4)
{
  OLECHAR *v7; // rdi
  OLECHAR *v8; // r9
  unsigned int v9; // ebx
  OLECHAR *v11; // r9
  struct IXMLDOMNode *v12; // rbx
  unsigned int v13; // r15d
  OLECHAR *v14; // r9
  int v15; // eax
  unsigned int v16; // r12d
  unsigned int v17; // eax
  BYTE *v18; // r14
  __int64 v19; // rax
  unsigned int LastError; // edi
  __int64 v21; // r15
  unsigned int v22; // r14d
  OLECHAR *v23; // rcx
  OLECHAR *v24; // rax
  OLECHAR *v25; // r14
  struct IXMLDOMNode *v26; // [rsp+40h] [rbp-C0h] BYREF
  DATA_BLOB pDataOut; // [rsp+48h] [rbp-B8h] BYREF
  DATA_BLOB pDataIn; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR v29[256]; // [rsp+70h] [rbp-90h] BYREF

  v26 = 0;
  v7 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
  if ( a4 < 3 )
  {
    v8 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
    if ( a4 != 2 )
      v8 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
  }
  else
  {
    v8 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
  }
  v9 = XcAddChildElement(a1, a2, (OLECHAR *)L"UserLogonCred", v8, 0, &v26);
  if ( v9 )
  {
    if ( v26 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v26->lpVtbl->Release)(v26);
    return v9;
  }
  if ( a4 < 3 )
  {
    v11 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
    if ( a4 != 2 )
      v11 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
  }
  else
  {
    v11 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
  }
  v12 = v26;
  v13 = XcAddChildElement(a1, v26, (OLECHAR *)L"UserName", v11, (OLECHAR *)(a3 + 210), 0);
  if ( v13 )
  {
    if ( v12 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v12->lpVtbl->Release)(v12);
    return v13;
  }
  if ( *(_DWORD *)(a3 + 4) )
  {
    if ( a4 < 3 )
    {
      v14 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
      if ( a4 != 2 )
        v14 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
    }
    else
    {
      v14 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
    }
    v13 = XcAddChildElementEnum(
            a1,
            v12,
            (OLECHAR *)L"IgnorePassword",
            v14,
            1u,
            (const struct _XC_STRING_VALUE_MAPPING *)&off_180015490,
            4u);
    if ( v13 )
    {
      if ( v12 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v12->lpVtbl->Release)(v12);
      return v13;
    }
  }
  v15 = *(_DWORD *)(a3 + 724);
  if ( v15 && (*(_BYTE *)a3 & 4) != 0 )
  {
    v16 = *(_DWORD *)(a3 + 1248);
    if ( v15 == 1 )
    {
      if ( !v16 )
      {
        *(&pDataIn.cbData + 1) = 0;
        *(_QWORD *)&pDataOut.cbData = 0;
        pDataOut.pbData = 0;
        v18 = (BYTE *)(a3 + 728);
        v19 = -1;
        do
          ++v19;
        while ( *(_WORD *)&v18[2 * v19] );
        pDataIn.cbData = 2 * v19;
        pDataIn.pbData = v18;
        if ( !CryptProtectData(&pDataIn, 0, 0, 0, 0, 0, &pDataOut) )
        {
          LastError = GetLastError();
          if ( pDataOut.pbData )
            LocalFree(pDataOut.pbData);
          if ( v12 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v12->lpVtbl->Release)(v12);
          return LastError;
        }
        if ( a4 < 3 )
        {
          v7 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
          if ( a4 != 2 )
            v7 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
        }
        LastError = XcAddChildElementHexBinary(a1, v12, (OLECHAR *)L"Password", v7, pDataOut.pbData, pDataOut.cbData);
        if ( pDataOut.pbData )
          LocalFree(pDataOut.pbData);
LABEL_65:
        if ( v12 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v12->lpVtbl->Release)(v12);
        return LastError;
      }
      if ( a4 < 3 )
      {
        v7 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
        if ( a4 != 2 )
          v7 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
      }
      v17 = XcAddChildElementHexBinary(
              a1,
              v12,
              (OLECHAR *)L"Password",
              v7,
              *(unsigned __int8 **)(a3 + 1256),
              *(_DWORD *)(a3 + 1248));
LABEL_64:
      LastError = v17;
      goto LABEL_65;
    }
    if ( !v16 )
    {
      v25 = (OLECHAR *)(a3 + 728);
      if ( a4 < 3 )
      {
        v7 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
        if ( a4 != 2 )
          v7 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
      }
      v17 = XcAddChildElement(a1, v12, (OLECHAR *)L"Password", v7, v25, 0);
      goto LABEL_64;
    }
    v21 = 512;
    memset_0(v29, 0, sizeof(v29));
    v22 = decryptData(*(_QWORD *)(a3 + 1256), v16, v29, 512);
    if ( !v22 )
    {
      v29[255] = 0;
      if ( a4 < 3 )
      {
        v7 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
        if ( a4 != 2 )
          v7 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
      }
      LastError = XcAddChildElement(a1, v12, (OLECHAR *)L"Password", v7, v29, 0);
      v24 = v29;
      do
      {
        *(_BYTE *)v24 = 0;
        v24 = (OLECHAR *)((char *)v24 + 1);
        --v21;
      }
      while ( v21 );
      goto LABEL_65;
    }
    v23 = v29;
    do
    {
      *(_BYTE *)v23 = 0;
      v23 = (OLECHAR *)((char *)v23 + 1);
      --v21;
    }
    while ( v21 );
    if ( v12 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v12->lpVtbl->Release)(v12);
    return v22;
  }
  else
  {
    if ( v12 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v12->lpVtbl->Release)(v12);
    return 0;
  }
}

```

## disassembly

```asm
0x18000b060  mov     [rsp-8+arg_18], rbx
0x18000b065  push    rbp
0x18000b066  push    rsi
0x18000b067  push    rdi
0x18000b068  push    r12
0x18000b06a  push    r13
0x18000b06c  push    r14
0x18000b06e  push    r15
0x18000b070  lea     rbp, [rsp-180h]
0x18000b078  sub     rsp, 280h
0x18000b07f  mov     rax, cs:__security_cookie
0x18000b086  xor     rax, rsp
0x18000b089  mov     [rbp+1B0h+var_40], rax
0x18000b090  mov     esi, r9d
0x18000b093  mov     r14, r8
0x18000b096  mov     r13, rcx
0x18000b099  xor     r12d, r12d
0x18000b09c  mov     [rsp+2B0h+var_270], r12
0x18000b0a1  lea     r15, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18000b0a8  lea     rdi, aHttpWwwMicroso_6; "http://www.microsoft.com/networking/WWA"...
0x18000b0af  cmp     r9d, 3
0x18000b0b3  jb      short loc_18000B0BA
0x18000b0b5  mov     r9, rdi
0x18000b0b8  jmp     short loc_18000B0C8
0x18000b0ba  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x18000b0c1  cmp     esi, 2
0x18000b0c4  cmovnz  r9, r15; OLECHAR *
0x18000b0c8  lea     rax, [rsp+2B0h+var_270]
0x18000b0cd  mov     qword ptr [rsp+2B0h+dwFlags], rax; struct IXMLDOMNode **
0x18000b0d2  mov     [rsp+2B0h+pPromptStruct], r12; OLECHAR *
0x18000b0d7  lea     r8, aUserlogoncred; "UserLogonCred"
0x18000b0de  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000b0e3  mov     ebx, eax
0x18000b0e5  test    eax, eax
0x18000b0e7  jz      short loc_18000B107
0x18000b0e9  mov     rcx, [rsp+2B0h+var_270]
0x18000b0ee  test    rcx, rcx
0x18000b0f1  jz      short loc_18000B100
0x18000b0f3  mov     rdx, [rcx]
0x18000b0f6  mov     rax, [rdx+10h]
0x18000b0fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0ff  nop
0x18000b100  mov     eax, ebx
0x18000b102  jmp     loc_18000B47F
0x18000b107  cmp     esi, 3
0x18000b10a  jb      short loc_18000B111
0x18000b10c  mov     r9, rdi
0x18000b10f  jmp     short loc_18000B11F
0x18000b111  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x18000b118  cmp     esi, 2
0x18000b11b  cmovnz  r9, r15; OLECHAR *
0x18000b11f  lea     rax, [r14+0D2h]
0x18000b126  mov     qword ptr [rsp+2B0h+dwFlags], r12; struct IXMLDOMNode **
0x18000b12b  mov     [rsp+2B0h+pPromptStruct], rax; OLECHAR *
0x18000b130  lea     r8, aUsername; "UserName"
0x18000b137  mov     rbx, [rsp+2B0h+var_270]
0x18000b13c  mov     rdx, rbx; struct IXMLDOMNode *
0x18000b13f  mov     rcx, r13; struct IXMLDOMDocument2 *
0x18000b142  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000b147  mov     r15d, eax
0x18000b14a  test    eax, eax
0x18000b14c  jz      short loc_18000B16B
0x18000b14e  test    rbx, rbx
0x18000b151  jz      short loc_18000B163
0x18000b153  mov     rcx, [rbx]
0x18000b156  mov     rax, [rcx+10h]
0x18000b15a  mov     rcx, rbx
0x18000b15d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b162  nop
0x18000b163  mov     eax, r15d
0x18000b166  jmp     loc_18000B47F
0x18000b16b  xor     r15d, r15d
0x18000b16e  cmp     [r14+4], r15d
0x18000b172  jz      short loc_18000B1E2
0x18000b174  cmp     esi, 3
0x18000b177  jb      short loc_18000B17E
0x18000b179  mov     r9, rdi
0x18000b17c  jmp     short loc_18000B193
0x18000b17e  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x18000b185  cmp     esi, 2
0x18000b188  lea     rax, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18000b18f  cmovnz  r9, rax; OLECHAR *
0x18000b193  mov     dword ptr [rsp+2B0h+pDataOut], 4; struct IXMLDOMNode **
0x18000b19b  lea     rax, off_180015490; "true"
0x18000b1a2  mov     qword ptr [rsp+2B0h+dwFlags], rax; struct _XC_STRING_VALUE_MAPPING *
0x18000b1a7  mov     dword ptr [rsp+2B0h+pPromptStruct], 1; unsigned int
0x18000b1af  lea     r8, aIgnorepassword; "IgnorePassword"
0x18000b1b6  mov     rdx, rbx; struct IXMLDOMNode *
0x18000b1b9  mov     rcx, r13; struct IXMLDOMDocument2 *
0x18000b1bc  call    ?XcAddChildElementEnum@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEBU_XC_STRING_VALUE_MAPPING@@KPEAPEAU2@@Z; XcAddChildElementEnum(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,_XC_STRING_VALUE_MAPPING const *,ulong,IXMLDOMNode * *)
0x18000b1c1  mov     r15d, eax
0x18000b1c4  test    eax, eax
0x18000b1c6  jz      short loc_18000B1DF
0x18000b1c8  test    rbx, rbx
0x18000b1cb  jz      short loc_18000B1DD
0x18000b1cd  mov     rcx, [rbx]
0x18000b1d0  mov     rax, [rcx+10h]
0x18000b1d4  mov     rcx, rbx
0x18000b1d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1dc  nop
0x18000b1dd  jmp     short loc_18000B163
0x18000b1df  xor     r15d, r15d
0x18000b1e2  mov     eax, [r14+2D4h]
0x18000b1e9  test    eax, eax
0x18000b1eb  jz      loc_18000B468
0x18000b1f1  test    byte ptr [r14], 4
0x18000b1f5  jz      loc_18000B468
0x18000b1fb  mov     r12d, [r14+4E0h]
0x18000b202  cmp     eax, 1
0x18000b205  jnz     loc_18000B344
0x18000b20b  test    r12d, r12d
0x18000b20e  jz      short loc_18000B255
0x18000b210  mov     rax, [r14+4E8h]
0x18000b217  cmp     esi, 3
0x18000b21a  jnb     short loc_18000B231
0x18000b21c  lea     rdi, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x18000b223  cmp     esi, 2
0x18000b226  lea     rcx, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18000b22d  cmovnz  rdi, rcx
0x18000b231  mov     [rsp+2B0h+dwFlags], r12d; unsigned int
0x18000b236  mov     [rsp+2B0h+pPromptStruct], rax; unsigned __int8 *
0x18000b23b  mov     r9, rdi; OLECHAR *
0x18000b23e  lea     r8, aPassword; "Password"
0x18000b245  mov     rdx, rbx; struct IXMLDOMNode *
0x18000b248  mov     rcx, r13; struct IXMLDOMDocument2 *
0x18000b24b  call    ?XcAddChildElementHexBinary@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2PEAEKPEAPEAU2@@Z; XcAddChildElementHexBinary(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,uchar *,ulong,IXMLDOMNode * *)
0x18000b250  jmp     loc_18000B44C
0x18000b255  mov     dword ptr [rsp+2B0h+pDataIn+4], r15d
0x18000b25a  mov     qword ptr [rsp+2B0h+var_268.cbData], 0
0x18000b263  mov     [rsp+2B0h+var_268.pbData], r15
0x18000b268  add     r14, 2D8h
0x18000b26f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b273  inc     rax
0x18000b276  cmp     [r14+rax*2], r15w
0x18000b27b  jnz     short loc_18000B273
0x18000b27d  add     eax, eax
0x18000b27f  mov     [rsp+2B0h+pDataIn.cbData], eax
0x18000b283  mov     [rsp+2B0h+pDataIn.pbData], r14
0x18000b288  lea     rax, [rsp+2B0h+var_268]
0x18000b28d  mov     [rsp+2B0h+pDataOut], rax; struct IXMLDOMNode **
0x18000b292  mov     [rsp+2B0h+dwFlags], r15d; dwFlags
0x18000b297  mov     [rsp+2B0h+pPromptStruct], r15; pPromptStruct
0x18000b29c  xor     r9d, r9d; pvReserved
0x18000b29f  xor     r8d, r8d; pOptionalEntropy
0x18000b2a2  xor     edx, edx; szDataDescr
0x18000b2a4  lea     rcx, [rsp+2B0h+pDataIn]; pDataIn
0x18000b2a9  call    cs:__imp_CryptProtectData
0x18000b2af  test    eax, eax
0x18000b2b1  jnz     short loc_18000B2E8
0x18000b2b3  call    cs:__imp_GetLastError
0x18000b2b9  mov     edi, eax
0x18000b2bb  mov     rcx, [rsp+2B0h+var_268.pbData]; hMem
0x18000b2c0  test    rcx, rcx
0x18000b2c3  jz      short loc_18000B2CC
0x18000b2c5  call    cs:__imp_LocalFree
0x18000b2cb  nop
0x18000b2cc  test    rbx, rbx
0x18000b2cf  jz      short loc_18000B2E1
0x18000b2d1  mov     rax, [rbx]
0x18000b2d4  mov     rcx, rbx
0x18000b2d7  mov     rax, [rax+10h]
0x18000b2db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2e0  nop
0x18000b2e1  mov     eax, edi
0x18000b2e3  jmp     loc_18000B47F
0x18000b2e8  mov     rcx, [rsp+2B0h+var_268.pbData]
0x18000b2ed  cmp     esi, 3
0x18000b2f0  jnb     short loc_18000B307
0x18000b2f2  lea     rdi, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x18000b2f9  cmp     esi, 2
0x18000b2fc  lea     rax, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18000b303  cmovnz  rdi, rax
0x18000b307  mov     eax, [rsp+2B0h+var_268.cbData]
0x18000b30b  mov     [rsp+2B0h+dwFlags], eax; unsigned int
0x18000b30f  mov     [rsp+2B0h+pPromptStruct], rcx; unsigned __int8 *
0x18000b314  mov     r9, rdi; OLECHAR *
0x18000b317  lea     r8, aPassword; "Password"
0x18000b31e  mov     rdx, rbx; struct IXMLDOMNode *
0x18000b321  mov     rcx, r13; struct IXMLDOMDocument2 *
0x18000b324  call    ?XcAddChildElementHexBinary@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2PEAEKPEAPEAU2@@Z; XcAddChildElementHexBinary(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,uchar *,ulong,IXMLDOMNode * *)
0x18000b329  mov     edi, eax
0x18000b32b  mov     rcx, [rsp+2B0h+var_268.pbData]; hMem
0x18000b330  test    rcx, rcx
0x18000b333  jz      loc_18000B44E
0x18000b339  call    cs:__imp_LocalFree
0x18000b33f  jmp     loc_18000B44E
0x18000b344  test    r12d, r12d
0x18000b347  jz      loc_18000B40C
0x18000b34d  mov     r15d, 200h
0x18000b353  mov     r8d, r15d; Size
0x18000b356  xor     edx, edx; Val
0x18000b358  lea     rcx, [rsp+2B0h+var_240]; void *
0x18000b35d  call    memset_0
0x18000b362  mov     r9d, r15d
0x18000b365  lea     r8, [rsp+2B0h+var_240]
0x18000b36a  mov     edx, r12d
0x18000b36d  mov     rcx, [r14+4E8h]
0x18000b374  call    _decryptData
0x18000b379  mov     r14d, eax
0x18000b37c  xor     r12d, r12d
0x18000b37f  test    eax, eax
0x18000b381  jz      short loc_18000B3B1
0x18000b383  lea     rcx, [rsp+2B0h+var_240]
0x18000b388  mov     [rcx], r12b
0x18000b38b  inc     rcx
0x18000b38e  sub     r15, 1
0x18000b392  jnz     short loc_18000B388
0x18000b394  test    rbx, rbx
0x18000b397  jz      short loc_18000B3A9
0x18000b399  mov     rax, [rbx]
0x18000b39c  mov     rcx, rbx
0x18000b39f  mov     rax, [rax+10h]
0x18000b3a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3a8  nop
0x18000b3a9  mov     eax, r14d
0x18000b3ac  jmp     loc_18000B47F
0x18000b3b1  mov     [rbp+1B0h+var_42], r12w
0x18000b3b9  cmp     esi, 3
0x18000b3bc  jnb     short loc_18000B3D3
0x18000b3be  lea     rdi, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x18000b3c5  cmp     esi, 2
0x18000b3c8  lea     rax, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18000b3cf  cmovnz  rdi, rax
0x18000b3d3  mov     qword ptr [rsp+2B0h+dwFlags], r12; struct IXMLDOMNode **
0x18000b3d8  lea     rax, [rsp+2B0h+var_240]
0x18000b3dd  mov     [rsp+2B0h+pPromptStruct], rax; OLECHAR *
0x18000b3e2  mov     r9, rdi; OLECHAR *
0x18000b3e5  lea     r8, aPassword; "Password"
0x18000b3ec  mov     rdx, rbx; struct IXMLDOMNode *
0x18000b3ef  mov     rcx, r13; struct IXMLDOMDocument2 *
0x18000b3f2  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000b3f7  mov     edi, eax
0x18000b3f9  lea     rax, [rsp+2B0h+var_240]
0x18000b3fe  mov     [rax], r12b
0x18000b401  inc     rax
0x18000b404  sub     r15, 1
0x18000b408  jnz     short loc_18000B3FE
0x18000b40a  jmp     short loc_18000B44E
0x18000b40c  add     r14, 2D8h
0x18000b413  cmp     esi, 3
0x18000b416  jnb     short loc_18000B42D
0x18000b418  lea     rdi, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x18000b41f  cmp     esi, 2
0x18000b422  lea     rax, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18000b429  cmovnz  rdi, rax
0x18000b42d  mov     qword ptr [rsp+2B0h+dwFlags], r15; struct IXMLDOMNode **
0x18000b432  mov     [rsp+2B0h+pPromptStruct], r14; OLECHAR *
0x18000b437  mov     r9, rdi; OLECHAR *
0x18000b43a  lea     r8, aPassword; "Password"
0x18000b441  mov     rdx, rbx; struct IXMLDOMNode *
0x18000b444  mov     rcx, r13; struct IXMLDOMDocument2 *
0x18000b447  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000b44c  mov     edi, eax
0x18000b44e  test    rbx, rbx
0x18000b451  jz      short loc_18000B463
0x18000b453  mov     rax, [rbx]
0x18000b456  mov     rcx, rbx
0x18000b459  mov     rax, [rax+10h]
0x18000b45d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b462  nop
0x18000b463  jmp     loc_18000B2E1
0x18000b468  test    rbx, rbx
0x18000b46b  jz      short loc_18000B47D
0x18000b46d  mov     rax, [rbx]
0x18000b470  mov     rcx, rbx
0x18000b473  mov     rax, [rax+10h]
0x18000b477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b47c  nop
0x18000b47d  xor     eax, eax
0x18000b47f  mov     rcx, [rbp+1B0h+var_40]
0x18000b486  xor     rcx, rsp; StackCookie
0x18000b489  call    __security_check_cookie
0x18000b48e  mov     rbx, [rsp+2B0h+arg_18]
0x18000b496  add     rsp, 280h
0x18000b49d  pop     r15
0x18000b49f  pop     r14
0x18000b4a1  pop     r13
0x18000b4a3  pop     r12
0x18000b4a5  pop     rdi
0x18000b4a6  pop     rsi
0x18000b4a7  pop     rbp
0x18000b4a8  retn
```
