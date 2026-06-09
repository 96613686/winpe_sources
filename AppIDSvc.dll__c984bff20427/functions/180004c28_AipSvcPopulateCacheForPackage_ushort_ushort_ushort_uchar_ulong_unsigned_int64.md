# AipSvcPopulateCacheForPackage(ushort *,ushort * *,ushort * *,uchar * *,ulong *,unsigned __int64 *)

- ea: `0x180004c28`
- end: `0x18000514b`
- name: `?AipSvcPopulateCacheForPackage@@YAJPEAGPEAPEAG1PEAPEAEPEAKPEA_K@Z`
- size: `1315`
- prototype: `__int64 __fastcall(PCWSTR packageFullName, unsigned __int16 **, unsigned __int16 **, unsigned __int8 **, unsigned int *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x18000b5b0`

## callees

- `0x180004c28`
- `0x180005154`
- `0x18000880c`
- `0x180009940`
- `0x180009fa8`
- `0x18000a0f8`
- `0x18000ab9c`
- `0x18000af10`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d5f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004d4d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004d4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800050f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800050f4`
- `RPCRT4!RpcRevertToSelf` at `0x180004ce5`
- `RPCRT4!RpcRevertToSelf` at `0x180004ce5`
- `RPCRT4!RpcImpersonateClient` at `0x180004c8c`
- `RPCRT4!RpcImpersonateClient` at `0x180004c8c`
- `ntdll!RtlFreeHeap` at `0x180004f5b`
- `ntdll!RtlFreeHeap` at `0x180005052`
- `ntdll!RtlFreeHeap` at `0x1800050ce`
- `ntdll!RtlFreeHeap` at `0x1800050e6`
- `ntdll!RtlFreeHeap` at `0x180005116`
- `ntdll!RtlFreeHeap` at `0x18000512f`
- `ntdll!RtlFreeHeap` at `0x180004f5b`
- `ntdll!RtlFreeHeap` at `0x180005052`
- `ntdll!RtlFreeHeap` at `0x1800050ce`
- `ntdll!RtlFreeHeap` at `0x1800050e6`
- `ntdll!RtlFreeHeap` at `0x180005116`
- `ntdll!RtlFreeHeap` at `0x18000512f`
- `ntdll!RtlUpcaseUnicodeString` at `0x180004f04`
- `ntdll!RtlUpcaseUnicodeString` at `0x180004ffb`
- `ntdll!RtlUpcaseUnicodeString` at `0x180004f04`
- `ntdll!RtlUpcaseUnicodeString` at `0x180004ffb`
- `ntdll!RtlInitUnicodeString` at `0x180004ef3`
- `ntdll!RtlInitUnicodeString` at `0x180004fea`
- `ntdll!RtlInitUnicodeString` at `0x180004ef3`
- `ntdll!RtlInitUnicodeString` at `0x180004fea`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x180004e0e`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x180004e0e`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x180004dfe`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x180004dfe`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x180004dde`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x180004dde`

## pseudocode

```c
__int64 __fastcall AipSvcPopulateCacheForPackage(
        PCWSTR packageFullName,
        unsigned __int16 **a2,
        unsigned __int16 **a3,
        unsigned __int8 **a4,
        unsigned int *a5,
        unsigned __int64 *a6)
{
  const WCHAR *v7; // rsi
  struct PACKAGE_ID *v8; // rdi
  unsigned __int8 *v9; // r12
  unsigned int v10; // r13d
  DWORD LastError; // eax
  signed int AppxSignatureFile; // ebx
  void (__fastcall *v13)(const wchar_t *, const wchar_t *, _QWORD); // rax
  __int64 FileW; // r15
  const wchar_t *v15; // rdx
  const wchar_t *v16; // rcx
  DWORD v17; // eax
  int FileSignature; // eax
  int v19; // ebx
  CRYPT_PROVIDER_DATA *v20; // rax
  CRYPT_PROVIDER_SGNR *ProvSignerFromChain; // rax
  CRYPT_PROVIDER_CERT *ProvCertFromChain; // rax
  int PublicKey; // eax
  int v24; // ebx
  __int64 v25; // rbx
  unsigned __int64 v26; // rbx
  WCHAR *v27; // rax
  const WCHAR *v28; // r9
  unsigned __int64 v29; // rbx
  __int64 v30; // rsi
  PWSTR name; // rdx
  __int64 v32; // rcx
  WCHAR *v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // rbx
  unsigned __int64 v36; // rbx
  WCHAR *v37; // rax
  const WCHAR *v38; // r8
  unsigned __int64 v39; // rbx
  PWSTR publisher; // rcx
  WCHAR *v41; // rcx
  __int64 v42; // rdx
  unsigned int v44; // [rsp+48h] [rbp-59h] BYREF
  PVOID P; // [rsp+50h] [rbp-51h]
  HANDLE hStateData; // [rsp+58h] [rbp-49h] BYREF
  struct PACKAGE_ID *v47; // [rsp+60h] [rbp-41h]
  unsigned __int8 *v48; // [rsp+68h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-29h] BYREF
  UNICODE_STRING SourceString; // [rsp+88h] [rbp-19h] BYREF
  _OWORD v51[5]; // [rsp+98h] [rbp-9h] BYREF

  P = 0;
  hStateData = 0;
  v47 = 0;
  v7 = 0;
  v48 = 0;
  SourceString = 0;
  v8 = 0;
  v9 = 0;
  DestinationString = 0;
  v10 = 0;
  v44 = 0;
  v51[0] = 0;
  if ( RpcImpersonateClient(0) )
  {
    LastError = GetLastError();
    AppxSignatureFile = LastError;
    if ( LastError )
      AppxSignatureFile = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    AppxSignatureFile = AipGetAppxSignatureFile(packageFullName);
    if ( AppxSignatureFile < 0 && g_AiLogFunctionCallErrorEvent )
      g_AiLogFunctionCallErrorEvent(L",.", L".0", (unsigned int)AppxSignatureFile);
    RpcRevertToSelf();
    v8 = v47;
    v7 = (const WCHAR *)P;
  }
  if ( AppxSignatureFile < 0 )
  {
    v13 = (void (__fastcall *)(const wchar_t *, const wchar_t *, _QWORD))g_AiLogFunctionCallErrorEvent;
    FileW = -1;
    if ( !g_AiLogFunctionCallErrorEvent )
      goto LABEL_67;
    v15 = L",.";
    v16 = L":<";
    goto LABEL_11;
  }
  FileW = (__int64)CreateFileW(v7, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( FileW != -1 )
  {
    FileSignature = AipGetFileSignature((HANDLE)FileW, 0, (__int64)&hStateData);
    if ( FileSignature )
    {
      v19 = (unsigned __int16)FileSignature;
      v13 = (void (__fastcall *)(const wchar_t *, const wchar_t *, _QWORD))g_AiLogFunctionCallErrorEvent;
      AppxSignatureFile = v19 | 0x80070000;
      if ( !g_AiLogFunctionCallErrorEvent )
        goto LABEL_67;
      v15 = L"&(";
      v16 = L":<";
    }
    else
    {
      v20 = WTHelperProvDataFromStateData(hStateData);
      if ( !v20
        || (ProvSignerFromChain = WTHelperGetProvSignerFromChain(v20, 0, 0, 0)) == 0
        || (ProvCertFromChain = WTHelperGetProvCertFromChain(ProvSignerFromChain, 0)) == 0 )
      {
        AppxSignatureFile = -1073741811;
        goto LABEL_67;
      }
      PublicKey = AipCertGetPublicKey(ProvCertFromChain->pCert, &v48, &v44);
      if ( !PublicKey )
      {
        v9 = v48;
        v10 = v44;
        goto LABEL_27;
      }
      v24 = (unsigned __int16)PublicKey;
      v13 = (void (__fastcall *)(const wchar_t *, const wchar_t *, _QWORD))g_AiLogFunctionCallErrorEvent;
      AppxSignatureFile = v24 | 0x80070000;
      if ( !g_AiLogFunctionCallErrorEvent )
        goto LABEL_67;
      v15 = L"$&";
      v16 = L":<";
    }
LABEL_11:
    v13(v16, v15, (unsigned int)AppxSignatureFile);
    goto LABEL_67;
  }
  v17 = GetLastError();
  AppxSignatureFile = v17;
  if ( !v17 )
    goto LABEL_67;
  if ( v17 != 2 )
  {
    AppxSignatureFile = (unsigned __int16)v17 | 0x80070000;
    goto LABEL_67;
  }
LABEL_27:
  v25 = -1;
  do
    ++v25;
  while ( v8->name[v25] );
  v26 = 2 * v25 + 2;
  v27 = (WCHAR *)AiAlloc(v26);
  v28 = v27;
  if ( !v27 )
  {
LABEL_30:
    AppxSignatureFile = -1073741801;
    goto LABEL_67;
  }
  v29 = v26 >> 1;
  v30 = 2147483646;
  if ( v29 )
  {
    if ( v29 <= 0x7FFFFFFF )
    {
      name = v8->name;
      v32 = 2147483646;
      do
      {
        if ( !v32 )
          break;
        if ( !*name )
          break;
        *v27++ = *name++;
        --v32;
        --v29;
      }
      while ( v29 );
      v33 = v27 - 1;
      if ( v29 )
        v33 = v27;
      *v33 = 0;
    }
    else
    {
      *v27 = 0;
    }
  }
  RtlInitUnicodeString(&DestinationString, v28);
  RtlUpcaseUnicodeString(&DestinationString, &DestinationString, 0);
  AppxSignatureFile = AiEncodeAttributeString(&DestinationString, v34, v51);
  if ( AppxSignatureFile >= 0 )
  {
    if ( *((_QWORD *)&v51[0] + 1) )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString.Buffer);
      DestinationString = (struct _UNICODE_STRING)v51[0];
    }
    v35 = -1;
    do
      ++v35;
    while ( v8->publisher[v35] );
    v36 = 2 * v35 + 2;
    v37 = (WCHAR *)AiAlloc(v36);
    v38 = v37;
    if ( !v37 )
      goto LABEL_30;
    v39 = v36 >> 1;
    if ( v39 )
    {
      if ( v39 <= 0x7FFFFFFF )
      {
        publisher = v8->publisher;
        do
        {
          if ( !v30 )
            break;
          if ( !*publisher )
            break;
          *v37++ = *publisher++;
          --v30;
          --v39;
        }
        while ( v39 );
        v41 = v37 - 1;
        if ( v39 )
          v41 = v37;
        *v41 = 0;
      }
      else
      {
        *v37 = 0;
      }
    }
    RtlInitUnicodeString(&SourceString, v38);
    RtlUpcaseUnicodeString(&SourceString, &SourceString, 0);
    AppxSignatureFile = AiEncodeAttributeString(&SourceString, v42, v51);
    if ( AppxSignatureFile >= 0 )
    {
      if ( *((_QWORD *)&v51[0] + 1) )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, SourceString.Buffer);
        SourceString = (UNICODE_STRING)v51[0];
      }
      *a3 = DestinationString.Buffer;
      *a2 = SourceString.Buffer;
      *a6 = v8->version.Version;
      if ( v9 )
      {
        *a4 = v9;
        *a5 = v10;
        AipSvcSetEntryInAppxCache(packageFullName, &SourceString, &DestinationString, v8, v9, v10);
      }
      DestinationString.Buffer = 0;
      SourceString.Buffer = 0;
    }
    else
    {
      v13 = (void (__fastcall *)(const wchar_t *, const wchar_t *, _QWORD))g_AiLogFunctionCallErrorEvent;
      if ( g_AiLogFunctionCallErrorEvent )
      {
        v15 = L".0";
        v16 = L":<";
        goto LABEL_11;
      }
    }
  }
  else
  {
    v13 = (void (__fastcall *)(const wchar_t *, const wchar_t *, _QWORD))g_AiLogFunctionCallErrorEvent;
    if ( g_AiLogFunctionCallErrorEvent )
    {
      v15 = L".0";
      v16 = L":<";
      goto LABEL_11;
    }
  }
LABEL_67:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  AipFreeFileSignature(hStateData);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString.Buffer);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, SourceString.Buffer);
  return (unsigned int)AppxSignatureFile;
}

```

## disassembly

```asm
0x180004c28  mov     rax, rsp
0x180004c2b  mov     [rax+20h], r9
0x180004c2f  mov     [rax+18h], r8
0x180004c33  mov     [rax+10h], rdx
0x180004c37  mov     [rax+8], rcx
0x180004c3b  push    rbp
0x180004c3c  push    rbx
0x180004c3d  push    rsi
0x180004c3e  push    rdi
0x180004c3f  push    r12
0x180004c41  push    r13
0x180004c43  push    r14
0x180004c45  push    r15
0x180004c47  lea     rbp, [rax-4Fh]
0x180004c4b  sub     rsp, 0A8h
0x180004c52  xor     r14d, r14d
0x180004c55  xorps   xmm0, xmm0
0x180004c58  mov     rbx, rcx
0x180004c5b  mov     [rbp+47h+P], r14
0x180004c5f  xorps   xmm1, xmm1
0x180004c62  mov     [rbp+47h+hStateData], r14
0x180004c66  xor     ecx, ecx; BindingHandle
0x180004c68  mov     [rbp+47h+var_88], r14
0x180004c6c  mov     esi, r14d
0x180004c6f  mov     [rbp+47h+var_80], r14
0x180004c73  movups  xmmword ptr [rbp+47h+SourceString.Length], xmm0
0x180004c77  mov     edi, r14d
0x180004c7a  mov     r12d, r14d
0x180004c7d  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm1
0x180004c81  mov     r13d, r14d
0x180004c84  mov     [rbp+47h+var_A0], r14d
0x180004c88  movups  [rbp+47h+var_50], xmm0
0x180004c8c  call    cs:__imp_RpcImpersonateClient
0x180004c92  test    eax, eax
0x180004c94  jz      short loc_180004CAD
0x180004c96  call    cs:__imp_GetLastError
0x180004c9c  mov     ebx, eax
0x180004c9e  test    eax, eax
0x180004ca0  jz      short loc_180004CF3
0x180004ca2  movzx   ebx, ax
0x180004ca5  or      ebx, 80070000h
0x180004cab  jmp     short loc_180004CF3
0x180004cad  lea     r8, [rbp+47h+P]
0x180004cb1  mov     rcx, rbx; packageFullName
0x180004cb4  lea     rdx, [rbp+47h+var_88]
0x180004cb8  call    AipGetAppxSignatureFile
0x180004cbd  mov     ebx, eax
0x180004cbf  test    eax, eax
0x180004cc1  jns     short loc_180004CE5
0x180004cc3  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x180004cca  test    rax, rax
0x180004ccd  jz      short loc_180004CE5
0x180004ccf  mov     r8d, ebx
0x180004cd2  lea     rdx, a0; ".0"
0x180004cd9  lea     rcx, asc_18000EDC0; ",."
0x180004ce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ce5  call    cs:__imp_RpcRevertToSelf
0x180004ceb  mov     rdi, [rbp+47h+var_88]
0x180004cef  mov     rsi, [rbp+47h+P]
0x180004cf3  test    ebx, ebx
0x180004cf5  jns     short loc_180004D29
0x180004cf7  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x180004cfe  or      r14, 0FFFFFFFFFFFFFFFFh
0x180004d02  mov     r15, r14
0x180004d05  test    rax, rax
0x180004d08  jz      loc_1800050BB
0x180004d0e  lea     rdx, asc_18000EDB0; ",."
0x180004d15  lea     rcx, asc_18000EDA0; ":<"
0x180004d1c  mov     r8d, ebx
0x180004d1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d24  jmp     loc_1800050BB
0x180004d29  xor     r9d, r9d; lpSecurityAttributes
0x180004d2c  mov     [rsp+30h], r14; hTemplateFile
0x180004d31  mov     [rsp+0E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180004d39  mov     edx, 80000000h; dwDesiredAccess
0x180004d3e  mov     rcx, rsi; lpFileName
0x180004d41  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x180004d49  lea     r8d, [r9+1]; dwShareMode
0x180004d4d  call    cs:__imp_CreateFileW
0x180004d53  or      r14, 0FFFFFFFFFFFFFFFFh
0x180004d57  mov     r15, rax
0x180004d5a  cmp     rax, r14
0x180004d5d  jnz     short loc_180004D88
0x180004d5f  call    cs:__imp_GetLastError
0x180004d65  xor     esi, esi
0x180004d67  mov     ebx, eax
0x180004d69  test    eax, eax
0x180004d6b  jz      loc_1800050BB
0x180004d71  cmp     eax, 2
0x180004d74  jz      loc_180004E62
0x180004d7a  movzx   ebx, ax
0x180004d7d  or      ebx, 80070000h
0x180004d83  jmp     loc_1800050BB
0x180004d88  mov     r9, cs:?AiSvcDriverHandle@@3PEAXEA; void * AiSvcDriverHandle
0x180004d8f  lea     rax, [rbp+47h+hStateData]
0x180004d93  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax; __int64
0x180004d98  mov     rdx, rsi
0x180004d9b  mov     rcx, r15; hFile
0x180004d9e  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r12; __int64
0x180004da3  call    AipGetFileSignature
0x180004da8  xor     esi, esi
0x180004daa  test    eax, eax
0x180004dac  jz      short loc_180004DDA
0x180004dae  movzx   ebx, ax
0x180004db1  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x180004db8  or      ebx, 80070000h
0x180004dbe  test    rax, rax
0x180004dc1  jz      loc_1800050BB
0x180004dc7  lea     rdx, asc_18000ED90; "&("
0x180004dce  lea     rcx, asc_18000ED80; ":<"
0x180004dd5  jmp     loc_180004D1C
0x180004dda  mov     rcx, [rbp+47h+hStateData]; hStateData
0x180004dde  call    cs:__imp_WTHelperProvDataFromStateData
0x180004de4  test    rax, rax
0x180004de7  jnz     short loc_180004DF3
0x180004de9  mov     ebx, 0C000000Dh
0x180004dee  jmp     loc_1800050BB
0x180004df3  xor     r9d, r9d; idxCounterSigner
0x180004df6  xor     r8d, r8d; fCounterSigner
0x180004df9  xor     edx, edx; idxSigner
0x180004dfb  mov     rcx, rax; pProvData
0x180004dfe  call    cs:__imp_WTHelperGetProvSignerFromChain
0x180004e04  test    rax, rax
0x180004e07  jz      short loc_180004DE9
0x180004e09  xor     edx, edx; idxCert
0x180004e0b  mov     rcx, rax; pSgnr
0x180004e0e  call    cs:__imp_WTHelperGetProvCertFromChain
0x180004e14  test    rax, rax
0x180004e17  jz      short loc_180004DE9
0x180004e19  mov     rcx, [rax+8]
0x180004e1d  lea     r8, [rbp+47h+var_A0]
0x180004e21  lea     rdx, [rbp+47h+var_80]
0x180004e25  call    AipCertGetPublicKey
0x180004e2a  test    eax, eax
0x180004e2c  jz      short loc_180004E5A
0x180004e2e  movzx   ebx, ax
0x180004e31  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x180004e38  or      ebx, 80070000h
0x180004e3e  test    rax, rax
0x180004e41  jz      loc_1800050BB
0x180004e47  lea     rdx, asc_18000ED70; "$&"
0x180004e4e  lea     rcx, asc_18000ED60; ":<"
0x180004e55  jmp     loc_180004D1C
0x180004e5a  mov     r12, [rbp+47h+var_80]
0x180004e5e  mov     r13d, [rbp+47h+var_A0]
0x180004e62  mov     rax, [rdi+10h]
0x180004e66  mov     rbx, r14
0x180004e69  inc     rbx
0x180004e6c  cmp     [rax+rbx*2], si
0x180004e70  jnz     short loc_180004E69
0x180004e72  lea     rbx, ds:2[rbx*2]
0x180004e7a  mov     rcx, rbx
0x180004e7d  call    AiAlloc
0x180004e82  mov     r9, rax
0x180004e85  test    rax, rax
0x180004e88  jnz     short loc_180004E94
0x180004e8a  mov     ebx, 0C0000017h
0x180004e8f  jmp     loc_1800050BB
0x180004e94  shr     rbx, 1
0x180004e97  mov     esi, 7FFFFFFEh
0x180004e9c  jz      short loc_180004EEC
0x180004e9e  cmp     rbx, 7FFFFFFFh
0x180004ea5  jbe     short loc_180004EAF
0x180004ea7  xor     eax, eax
0x180004ea9  mov     [r9], ax
0x180004ead  jmp     short loc_180004EEC
0x180004eaf  mov     rdx, [rdi+10h]
0x180004eb3  mov     rcx, rsi
0x180004eb6  xor     r10d, r10d
0x180004eb9  test    rcx, rcx
0x180004ebc  jz      short loc_180004EDD
0x180004ebe  movzx   r8d, word ptr [rdx]
0x180004ec2  test    r8w, r8w
0x180004ec6  jz      short loc_180004EDD
0x180004ec8  mov     [rax], r8w
0x180004ecc  add     rdx, 2
0x180004ed0  add     rax, 2
0x180004ed4  dec     rcx
0x180004ed7  sub     rbx, 1
0x180004edb  jnz     short loc_180004EB9
0x180004edd  test    rbx, rbx
0x180004ee0  lea     rcx, [rax-2]
0x180004ee4  cmovnz  rcx, rax
0x180004ee8  mov     [rcx], r10w
0x180004eec  mov     rdx, r9; SourceString
0x180004eef  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x180004ef3  call    cs:__imp_RtlInitUnicodeString
0x180004ef9  xor     r8d, r8d; AllocateDestinationString
0x180004efc  lea     rdx, [rbp+47h+DestinationString]; SourceString
0x180004f00  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x180004f04  call    cs:__imp_RtlUpcaseUnicodeString
0x180004f0a  lea     r8, [rbp+47h+var_50]
0x180004f0e  lea     rcx, [rbp+47h+DestinationString]
0x180004f12  call    AiEncodeAttributeString
0x180004f17  xor     ecx, ecx
0x180004f19  mov     ebx, eax
0x180004f1b  test    eax, eax
0x180004f1d  jns     short loc_180004F42
0x180004f1f  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x180004f26  test    rax, rax
0x180004f29  jz      loc_1800050BB
0x180004f2f  lea     rdx, a0_0; ".0"
0x180004f36  lea     rcx, asc_18000ED40; ":<"
0x180004f3d  jmp     loc_180004D1C
0x180004f42  cmp     qword ptr [rbp+47h+var_50+8], rcx
0x180004f46  jz      short loc_180004F6C
0x180004f48  mov     rcx, gs:60h
0x180004f51  xor     edx, edx; Flags
0x180004f53  mov     r8, [rbp+47h+DestinationString.Buffer]; P
0x180004f57  mov     rcx, [rcx+30h]; HeapHandle
0x180004f5b  call    cs:__imp_RtlFreeHeap
0x180004f61  movaps  xmm0, [rbp+47h+var_50]
0x180004f65  xor     ecx, ecx
0x180004f67  movdqa  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x180004f6c  mov     rax, [rdi+18h]
0x180004f70  mov     rbx, r14
0x180004f73  inc     rbx
0x180004f76  cmp     [rax+rbx*2], cx
0x180004f7a  jnz     short loc_180004F73
0x180004f7c  lea     rbx, ds:2[rbx*2]
0x180004f84  mov     rcx, rbx
0x180004f87  call    AiAlloc
0x180004f8c  xor     r9d, r9d
0x180004f8f  mov     r8, rax
0x180004f92  test    rax, rax
0x180004f95  jz      loc_180004E8A
0x180004f9b  shr     rbx, 1
0x180004f9e  jz      short loc_180004FE3
0x180004fa0  cmp     rbx, 7FFFFFFFh
0x180004fa7  jbe     short loc_180004FAF
0x180004fa9  mov     [rax], r9w
0x180004fad  jmp     short loc_180004FE3
0x180004faf  mov     rcx, [rdi+18h]
0x180004fb3  test    rsi, rsi
0x180004fb6  jz      short loc_180004FD4
0x180004fb8  movzx   edx, word ptr [rcx]
0x180004fbb  test    dx, dx
0x180004fbe  jz      short loc_180004FD4
0x180004fc0  mov     [rax], dx
0x180004fc3  add     rcx, 2
0x180004fc7  add     rax, 2
0x180004fcb  dec     rsi
0x180004fce  sub     rbx, 1
0x180004fd2  jnz     short loc_180004FB3
0x180004fd4  test    rbx, rbx
0x180004fd7  lea     rcx, [rax-2]
0x180004fdb  cmovnz  rcx, rax
0x180004fdf  mov     [rcx], r9w
0x180004fe3  mov     rdx, r8; SourceString
0x180004fe6  lea     rcx, [rbp+47h+SourceString]; DestinationString
0x180004fea  call    cs:__imp_RtlInitUnicodeString
0x180004ff0  xor     r8d, r8d; AllocateDestinationString
0x180004ff3  lea     rdx, [rbp+47h+SourceString]; SourceString
0x180004ff7  lea     rcx, [rbp+47h+SourceString]; DestinationString
0x180004ffb  call    cs:__imp_RtlUpcaseUnicodeString
0x180005001  lea     r8, [rbp+47h+var_50]
0x180005005  lea     rcx, [rbp+47h+SourceString]
0x180005009  call    AiEncodeAttributeString
0x18000500e  xor     esi, esi
0x180005010  mov     ebx, eax
0x180005012  test    eax, eax
0x180005014  jns     short loc_180005039
0x180005016  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x18000501d  test    rax, rax
0x180005020  jz      loc_1800050BB
0x180005026  lea     rdx, a0_1; ".0"
0x18000502d  lea     rcx, asc_18000ED20; ":<"
0x180005034  jmp     loc_180004D1C
0x180005039  cmp     qword ptr [rbp+47h+var_50+8], rsi
0x18000503d  jz      short loc_180005061
0x18000503f  mov     rcx, gs:60h
0x180005048  xor     edx, edx; Flags
0x18000504a  mov     r8, [rbp+47h+SourceString.Buffer]; P
0x18000504e  mov     rcx, [rcx+30h]; HeapHandle
0x180005052  call    cs:__imp_RtlFreeHeap
0x180005058  movaps  xmm0, [rbp+47h+var_50]
0x18000505c  movdqa  xmmword ptr [rbp+47h+SourceString.Length], xmm0
0x180005061  mov     rcx, [rbp+47h+arg_10]
0x180005065  mov     rax, [rbp+47h+DestinationString.Buffer]
0x180005069  mov     [rcx], rax
0x18000506c  mov     rcx, [rbp+47h+arg_8]
0x180005070  mov     rax, [rbp+47h+SourceString.Buffer]
0x180005074  mov     [rcx], rax
0x180005077  mov     rax, [rbp+47h+arg_28]
0x18000507b  mov     rcx, [rdi+8]
0x18000507f  mov     [rax], rcx
0x180005082  test    r12, r12
0x180005085  jz      short loc_1800050B3
0x180005087  mov     rax, [rbp+47h+arg_18]
0x18000508b  lea     r8, [rbp+47h+DestinationString]; struct _UNICODE_STRING *
0x18000508f  mov     rcx, [rbp+47h+lpSubKey]; lpSubKey
0x180005093  lea     rdx, [rbp+47h+SourceString]; struct _UNICODE_STRING *
0x180005097  mov     [rsp+0E0h+dwFlagsAndAttributes], r13d; unsigned int
0x18000509c  mov     r9, rdi; struct PACKAGE_ID *
0x18000509f  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r12; unsigned __int8 *
0x1800050a4  mov     [rax], r12
0x1800050a7  mov     rax, [rbp+47h+arg_20]
0x1800050ab  mov     [rax], r13d
0x1800050ae  call    ?AipSvcSetEntryInAppxCache@@YAJPEAGPEAU_UNICODE_STRING@@1PEAUPACKAGE_ID@@PEAEK@Z; AipSvcSetEntryInAppxCache(ushort *,_UNICODE_STRING *,_UNICODE_STRING *,PACKAGE_ID *,uchar *,ulong)
0x1800050b3  mov     [rbp+47h+DestinationString.Buffer], rsi
  ... truncated ...
```
