# AipGetFileSignature

- ea: `0x180007d68`
- end: `0x180008186`
- name: `AipGetFileSignature`
- size: `1054`
- prototype: `__int64 __fastcall(HANDLE hFile, __int64, __int64, __int64, int, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800074a0`

## callees

- `0x180007ccc`
- `0x180007d68`
- `0x1800082ec`
- `0x18000957a`
- `0x1800095c0`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007eef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007eef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080d7`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x180007fab`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x180007fab`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x1800080ab`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x1800080ab`
- `WINTRUST!WinVerifyTrust` at `0x180007e46`
- `WINTRUST!WinVerifyTrust` at `0x18000804a`
- `WINTRUST!WinVerifyTrust` at `0x180007e46`
- `WINTRUST!WinVerifyTrust` at `0x18000804a`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x180008141`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x180008141`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x180008153`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x180008153`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x180007f39`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x180007f39`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x180007ee5`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x180007ee5`

## pseudocode

```c
__int64 __fastcall AipGetFileSignature(HANDLE hFile, __int64 a2, __int64 a3, __int64 a4, int a5, _QWORD *a6)
{
  int v8; // eax
  int v9; // eax
  unsigned int v10; // ebx
  void (__fastcall *v11)(const wchar_t *, const wchar_t *, __int64); // rax
  __int64 v12; // r8
  const wchar_t *v13; // rdx
  const wchar_t *v14; // rcx
  signed int LastError; // eax
  __int64 v16; // r8
  void (__fastcall *v17)(const wchar_t *, const wchar_t *, __int64); // rax
  const wchar_t *v18; // rdx
  const wchar_t *v19; // rcx
  signed int v20; // eax
  LONG v21; // eax
  HCATINFO v22; // rsi
  signed int v23; // eax
  __int64 v24; // r8
  signed int v25; // eax
  void (__fastcall *v26)(const wchar_t *, const wchar_t *, __int64); // rax
  const wchar_t *v27; // rdx
  const wchar_t *v28; // rcx
  DWORD pcbHash; // [rsp+30h] [rbp-D0h] BYREF
  HCATADMIN phCatAdmin; // [rsp+38h] [rbp-C8h] BYREF
  HCATINFO phPrevCatInfo; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD pWVTData[6]; // [rsp+50h] [rbp-B0h] BYREF
  int v34; // [rsp+68h] [rbp-98h]
  int v35; // [rsp+6Ch] [rbp-94h]
  int v36; // [rsp+70h] [rbp-90h]
  _QWORD *v37; // [rsp+78h] [rbp-88h]
  int v38; // [rsp+80h] [rbp-80h]
  __int64 v39; // [rsp+88h] [rbp-78h]
  int v40; // [rsp+98h] [rbp-68h]
  _QWORD v41[4]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v42[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v43; // [rsp+E0h] [rbp-20h]
  HANDLE v44; // [rsp+F0h] [rbp-10h]
  BYTE *v45; // [rsp+F8h] [rbp-8h]
  DWORD v46; // [rsp+100h] [rbp+0h]
  __int64 v47; // [rsp+104h] [rbp+4h]
  __int64 v48; // [rsp+10Ch] [rbp+Ch]
  int v49; // [rsp+114h] [rbp+14h]
  CATALOG_INFO psCatInfo; // [rsp+120h] [rbp+20h] BYREF
  BYTE pbHash[32]; // [rsp+330h] [rbp+230h] BYREF

  memset_0(v42, 0, 0x48u);
  phPrevCatInfo = 0;
  pcbHash = 32;
  phCatAdmin = 0;
  memset_0(&psCatInfo, 0, sizeof(psCatInfo));
  memset_0(pWVTData, 0, 0x58u);
  v41[0] = 32;
  v41[3] = 0;
  v37 = v41;
  v41[2] = hFile;
  v41[1] = a2;
  pWVTData[0] = 88;
  v34 = 2;
  v36 = 1;
  v38 = 1;
  v35 = 1;
  v40 = 4224;
  v8 = WinVerifyTrust(HWND_MESSAGE|0x2LL, (GUID *)&pgActionID, pWVTData);
  if ( v8 )
  {
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0xC0070000;
    if ( g_AiLogFunctionCallErrorEvent )
    {
      v12 = (unsigned int)v8;
      v13 = L">@";
      v11 = (void (__fastcall *)(const wchar_t *, const wchar_t *, __int64))g_AiLogFunctionCallErrorEvent;
      v14 = L"&(";
      goto LABEL_12;
    }
  }
  else
  {
    v9 = AipVerifyFileSignatureSystem(pWVTData);
    v10 = v9;
    if ( !v9 )
    {
      *a6 = v39;
      goto LABEL_49;
    }
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0xC0070000;
    v11 = (void (__fastcall *)(const wchar_t *, const wchar_t *, __int64))g_AiLogFunctionCallErrorEvent;
    if ( g_AiLogFunctionCallErrorEvent )
    {
      v12 = v10;
      v13 = L"8:";
      v14 = L"&(";
LABEL_12:
      v11(v14, v13, v12);
    }
  }
  AipFreeFileSignature(v39);
  if ( !CryptCATAdminCalcHashFromFileHandle(hFile, &pcbHash, pbHash, 0) )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0xC0070000;
    else
      v16 = (unsigned int)LastError;
    v17 = (void (__fastcall *)(const wchar_t *, const wchar_t *, __int64))g_AiLogFunctionCallErrorEvent;
    if ( !g_AiLogFunctionCallErrorEvent )
      goto LABEL_49;
    v18 = L"FH";
    v19 = L"&(";
    goto LABEL_19;
  }
  if ( !CryptCATAdminAcquireContext(&phCatAdmin, 0, 0) )
  {
    v20 = GetLastError();
    v10 = v20;
    if ( v20 > 0 )
      v16 = (unsigned __int16)v20 | 0xC0070000;
    else
      v16 = (unsigned int)v20;
    v17 = (void (__fastcall *)(const wchar_t *, const wchar_t *, __int64))g_AiLogFunctionCallErrorEvent;
    if ( !g_AiLogFunctionCallErrorEvent )
      goto LABEL_49;
    v18 = L"68";
    v19 = L"&(";
LABEL_19:
    v17(v19, v18, v16);
    goto LABEL_49;
  }
  for ( phPrevCatInfo = 0; ; phPrevCatInfo = v22 )
  {
    v22 = CryptCATAdminEnumCatalogFromHash(phCatAdmin, pbHash, pcbHash, 0, &phPrevCatInfo);
    if ( !v22 )
    {
      v23 = GetLastError();
      v10 = v23;
      if ( v23 > 0 )
        v24 = (unsigned __int16)v23 | 0xC0070000;
      else
        v24 = (unsigned int)v23;
      v26 = (void (__fastcall *)(const wchar_t *, const wchar_t *, __int64))g_AiLogFunctionCallErrorEvent;
      if ( g_AiLogFunctionCallErrorEvent )
      {
        v27 = L"@B";
        v28 = L"&(";
        goto LABEL_46;
      }
      goto LABEL_47;
    }
    memset_0(psCatInfo.wszCatalogFile, 0, sizeof(psCatInfo.wszCatalogFile));
    psCatInfo.cbStruct = 524;
    if ( !CryptCATCatalogInfoFromContext(v22, &psCatInfo, 0) )
      break;
    memset_0(pWVTData, 0, 0x58u);
    v42[0] = 72;
    v42[1] = psCatInfo.wszCatalogFile;
    v47 = 0;
    v45 = pbHash;
    v46 = pcbHash;
    v48 = 0;
    v34 = 2;
    v36 = 2;
    v37 = v42;
    v49 = 0;
    v43 = 0;
    v44 = hFile;
    pWVTData[0] = 88;
    v38 = 1;
    v35 = 1;
    v40 = 4224;
    v21 = WinVerifyTrust(HWND_MESSAGE|0x2LL, (GUID *)&pgActionID, pWVTData);
    v10 = v21;
    if ( !v21 )
    {
      *a6 = v39;
      goto LABEL_47;
    }
    if ( v21 > 0 )
      v10 = (unsigned __int16)v21 | 0xC0070000;
    if ( g_AiLogFunctionCallErrorEvent )
      g_AiLogFunctionCallErrorEvent(L"&(", L"DF", v10);
    AipFreeFileSignature(v39);
  }
  v25 = GetLastError();
  v10 = v25;
  if ( v25 > 0 )
    v24 = (unsigned __int16)v25 | 0xC0070000;
  else
    v24 = (unsigned int)v25;
  v26 = (void (__fastcall *)(const wchar_t *, const wchar_t *, __int64))g_AiLogFunctionCallErrorEvent;
  if ( g_AiLogFunctionCallErrorEvent )
  {
    v27 = L"<>";
    v28 = L"&(";
LABEL_46:
    v26(v28, v27, v24);
  }
LABEL_47:
  if ( v22 )
    CryptCATAdminReleaseCatalogContext(phCatAdmin, v22, 0);
LABEL_49:
  if ( phCatAdmin )
    CryptCATAdminReleaseContext(phCatAdmin, 0);
  return v10;
}

```

## disassembly

```asm
0x180007d68  mov     [rsp-8+arg_10], rbx
0x180007d6d  mov     [rsp-8+arg_18], rsi
0x180007d72  push    rbp
0x180007d73  push    rdi
0x180007d74  push    r13
0x180007d76  push    r14
0x180007d78  push    r15
0x180007d7a  lea     rbp, [rsp-260h]
0x180007d82  sub     rsp, 360h
0x180007d89  mov     rax, cs:__security_cookie
0x180007d90  xor     rax, rsp
0x180007d93  mov     [rbp+280h+var_30], rax
0x180007d9a  mov     r14, [rbp+280h+arg_28]
0x180007da1  mov     rbx, rdx
0x180007da4  xor     edx, edx; Val
0x180007da6  mov     r15, rcx
0x180007da9  lea     rcx, [rbp+280h+var_2B0]; void *
0x180007dad  lea     r8d, [rdx+48h]; Size
0x180007db1  call    memset_0
0x180007db6  mov     edi, 20h ; ' '
0x180007dbb  mov     [rsp+380h+var_340], 0
0x180007dc4  xor     edx, edx; Val
0x180007dc6  mov     [rsp+380h+pcbHash], edi
0x180007dca  mov     r8d, 20Ch; Size
0x180007dd0  mov     [rsp+380h+phCatAdmin], 0
0x180007dd9  lea     rcx, [rbp+280h+psCatInfo]; void *
0x180007ddd  call    memset_0
0x180007de2  lea     esi, [rdi+38h]
0x180007de5  xor     edx, edx; Val
0x180007de7  mov     r8d, esi; Size
0x180007dea  lea     rcx, [rsp+380h+pWVTData]; void *
0x180007def  call    memset_0
0x180007df4  lea     r13d, [rdi-1Fh]
0x180007df8  mov     [rbp+280h+var_2D0], rdi
0x180007dfc  lea     rax, [rbp+280h+var_2D0]
0x180007e00  mov     [rbp+280h+var_2B8], 0
0x180007e08  lea     r8, [rsp+380h+pWVTData]; pWVTData
0x180007e0d  mov     [rsp+380h+var_308], rax
0x180007e12  lea     rdx, pgActionID; pgActionID
0x180007e19  mov     [rbp+280h+var_2C0], r15
0x180007e1d  or      rcx, 0FFFFFFFFFFFFFFFFh; hwnd
0x180007e21  mov     [rbp+280h+var_2C8], rbx
0x180007e25  mov     [rsp+380h+pWVTData], esi
0x180007e29  mov     [rsp+380h+var_318], 2
0x180007e31  mov     [rsp+380h+var_310], r13d
0x180007e36  mov     [rbp+280h+var_300], r13d
0x180007e3a  mov     [rsp+380h+var_314], r13d
0x180007e3f  mov     [rbp+280h+var_2E8], 1080h
0x180007e46  call    cs:__imp_WinVerifyTrust
0x180007e4c  test    eax, eax
0x180007e4e  jnz     short loc_180007E97
0x180007e50  lea     rcx, [rsp+380h+pWVTData]
0x180007e55  call    AipVerifyFileSignatureSystem
0x180007e5a  mov     ebx, eax
0x180007e5c  test    eax, eax
0x180007e5e  jz      short loc_180007E8B
0x180007e60  mov     edi, 0C0070000h
0x180007e65  jle     short loc_180007E6C
0x180007e67  movzx   ebx, ax
0x180007e6a  or      ebx, edi
0x180007e6c  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x180007e73  test    rax, rax
0x180007e76  jz      short loc_180007ECA
0x180007e78  mov     r8d, ebx
0x180007e7b  lea     rdx, a8_0; "8:"
0x180007e82  lea     rcx, asc_18000B2C0; "&("
0x180007e89  jmp     short loc_180007EC5
0x180007e8b  mov     rax, [rbp+280h+var_2F8]
0x180007e8f  mov     [r14], rax
0x180007e92  jmp     loc_180008147
0x180007e97  mov     edi, 0C0070000h
0x180007e9c  test    eax, eax
0x180007e9e  jle     short loc_180007EA5
0x180007ea0  movzx   eax, ax
0x180007ea3  or      eax, edi
0x180007ea5  mov     r9, cs:g_AiLogFunctionCallErrorEvent
0x180007eac  test    r9, r9
0x180007eaf  jz      short loc_180007ECA
0x180007eb1  mov     r8d, eax
0x180007eb4  lea     rdx, asc_18000B2B0; ">@"
0x180007ebb  mov     rax, r9
0x180007ebe  lea     rcx, asc_18000B2A0; "&("
0x180007ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007eca  mov     rcx, [rbp+280h+var_2F8]
0x180007ece  call    AipFreeFileSignature
0x180007ed3  xor     r9d, r9d; dwFlags
0x180007ed6  lea     r8, [rbp+280h+pbHash]; pbHash
0x180007edd  lea     rdx, [rsp+380h+pcbHash]; pcbHash
0x180007ee2  mov     rcx, r15; hFile
0x180007ee5  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle
0x180007eeb  test    eax, eax
0x180007eed  jnz     short loc_180007F2F
0x180007eef  call    cs:__imp_GetLastError
0x180007ef5  mov     ebx, eax
0x180007ef7  test    eax, eax
0x180007ef9  jg      short loc_180007F00
0x180007efb  mov     r8d, eax
0x180007efe  jmp     short loc_180007F07
0x180007f00  movzx   r8d, ax
0x180007f04  or      r8d, edi
0x180007f07  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x180007f0e  test    rax, rax
0x180007f11  jz      loc_180008147
0x180007f17  lea     rdx, aFh; "FH"
0x180007f1e  lea     rcx, asc_18000B280; "&("
0x180007f25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f2a  jmp     loc_180008147
0x180007f2f  xor     r8d, r8d; dwFlags
0x180007f32  lea     rcx, [rsp+380h+phCatAdmin]; phCatAdmin
0x180007f37  xor     edx, edx; pgSubsystem
0x180007f39  call    cs:__imp_CryptCATAdminAcquireContext
0x180007f3f  test    eax, eax
0x180007f41  jnz     short loc_180007F7B
0x180007f43  call    cs:__imp_GetLastError
0x180007f49  mov     ebx, eax
0x180007f4b  test    eax, eax
0x180007f4d  jg      short loc_180007F54
0x180007f4f  mov     r8d, eax
0x180007f52  jmp     short loc_180007F5B
0x180007f54  movzx   r8d, ax
0x180007f58  or      r8d, edi
0x180007f5b  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x180007f62  test    rax, rax
0x180007f65  jz      loc_180008147
0x180007f6b  lea     rdx, a68; "68"
0x180007f72  lea     rcx, asc_18000B260; "&("
0x180007f79  jmp     short loc_180007F25
0x180007f7b  mov     [rsp+380h+var_340], 0
0x180007f84  jmp     loc_18000808D
0x180007f89  xor     edx, edx; Val
0x180007f8b  lea     rcx, [rbp+280h+psCatInfo.wszCatalogFile]; void *
0x180007f8f  mov     r8d, 208h; Size
0x180007f95  call    memset_0
0x180007f9a  xor     r8d, r8d; dwFlags
0x180007f9d  mov     [rbp+280h+psCatInfo.cbStruct], 20Ch
0x180007fa4  lea     rdx, [rbp+280h+psCatInfo]; psCatInfo
0x180007fa8  mov     rcx, rsi; hCatInfo
0x180007fab  call    cs:__imp_CryptCATCatalogInfoFromContext
0x180007fb1  test    eax, eax
0x180007fb3  jz      loc_1800080D7
0x180007fb9  mov     ebx, 58h ; 'X'
0x180007fbe  lea     rcx, [rsp+380h+pWVTData]; void *
0x180007fc3  mov     r8d, ebx; Size
0x180007fc6  xor     edx, edx; Val
0x180007fc8  call    memset_0
0x180007fcd  lea     rax, [rbp+280h+psCatInfo.wszCatalogFile]
0x180007fd1  mov     [rbp+280h+var_2B0], 48h ; 'H'
0x180007fd9  mov     [rbp+280h+var_2A8], rax
0x180007fdd  lea     r8, [rsp+380h+pWVTData]; pWVTData
0x180007fe2  lea     rax, [rbp+280h+pbHash]
0x180007fe9  mov     [rbp+280h+var_27C], 0
0x180007ff1  mov     [rbp+280h+var_288], rax
0x180007ff5  lea     rdx, pgActionID; pgActionID
0x180007ffc  mov     eax, [rsp+380h+pcbHash]
0x180008000  xorps   xmm0, xmm0
0x180008003  mov     [rbp+280h+var_280], eax
0x180008006  or      rcx, 0FFFFFFFFFFFFFFFFh; hwnd
0x18000800a  lea     eax, [rbx-56h]
0x18000800d  mov     [rbp+280h+var_274], 0
0x180008015  mov     [rsp+380h+var_318], eax
0x180008019  mov     [rsp+380h+var_310], eax
0x18000801d  lea     rax, [rbp+280h+var_2B0]
0x180008021  mov     [rsp+380h+var_308], rax
0x180008026  mov     [rbp+280h+var_26C], 0
0x18000802d  movdqa  [rbp+280h+var_2A0], xmm0
0x180008032  mov     [rbp+280h+var_290], r15
0x180008036  mov     [rsp+380h+pWVTData], ebx
0x18000803a  mov     [rbp+280h+var_300], r13d
0x18000803e  mov     [rsp+380h+var_314], r13d
0x180008043  mov     [rbp+280h+var_2E8], 1080h
0x18000804a  call    cs:__imp_WinVerifyTrust
0x180008050  mov     ebx, eax
0x180008052  test    eax, eax
0x180008054  jz      short loc_1800080CE
0x180008056  jle     short loc_18000805D
0x180008058  movzx   ebx, ax
0x18000805b  or      ebx, edi
0x18000805d  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x180008064  test    rax, rax
0x180008067  jz      short loc_18000807F
0x180008069  mov     r8d, ebx
0x18000806c  lea     rdx, aDf_0; "DF"
0x180008073  lea     rcx, asc_18000B200; "&("
0x18000807a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000807f  mov     rcx, [rbp+280h+var_2F8]
0x180008083  call    AipFreeFileSignature
0x180008088  mov     [rsp+380h+var_340], rsi
0x18000808d  mov     r8d, [rsp+380h+pcbHash]; cbHash
0x180008092  lea     rax, [rsp+380h+var_340]
0x180008097  mov     rcx, [rsp+380h+phCatAdmin]; hCatAdmin
0x18000809c  lea     rdx, [rbp+280h+pbHash]; pbHash
0x1800080a3  xor     r9d, r9d; dwFlags
0x1800080a6  mov     [rsp+380h+phPrevCatInfo], rax; phPrevCatInfo
0x1800080ab  call    cs:__imp_CryptCATAdminEnumCatalogFromHash
0x1800080b1  mov     rsi, rax
0x1800080b4  test    rax, rax
0x1800080b7  jnz     loc_180007F89
0x1800080bd  call    cs:__imp_GetLastError
0x1800080c3  mov     ebx, eax
0x1800080c5  test    eax, eax
0x1800080c7  jg      short loc_18000810B
0x1800080c9  mov     r8d, eax
0x1800080cc  jmp     short loc_180008112
0x1800080ce  mov     rax, [rbp+280h+var_2F8]
0x1800080d2  mov     [r14], rax
0x1800080d5  jmp     short loc_180008131
0x1800080d7  call    cs:__imp_GetLastError
0x1800080dd  mov     ebx, eax
0x1800080df  test    eax, eax
0x1800080e1  jg      short loc_1800080E8
0x1800080e3  mov     r8d, eax
0x1800080e6  jmp     short loc_1800080EF
0x1800080e8  movzx   r8d, ax
0x1800080ec  or      r8d, edi
0x1800080ef  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x1800080f6  test    rax, rax
0x1800080f9  jz      short loc_180008131
0x1800080fb  lea     rdx, asc_18000B230; "<>"
0x180008102  lea     rcx, asc_18000B220; "&("
0x180008109  jmp     short loc_18000812C
0x18000810b  movzx   r8d, ax
0x18000810f  or      r8d, edi
0x180008112  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x180008119  test    rax, rax
0x18000811c  jz      short loc_180008131
0x18000811e  lea     rdx, aB; "@B"
0x180008125  lea     rcx, asc_18000B240; "&("
0x18000812c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008131  test    rsi, rsi
0x180008134  jz      short loc_180008147
0x180008136  mov     rcx, [rsp+380h+phCatAdmin]; hCatAdmin
0x18000813b  xor     r8d, r8d; dwFlags
0x18000813e  mov     rdx, rsi; hCatInfo
0x180008141  call    cs:__imp_CryptCATAdminReleaseCatalogContext
0x180008147  mov     rcx, [rsp+380h+phCatAdmin]; hCatAdmin
0x18000814c  test    rcx, rcx
0x18000814f  jz      short loc_180008159
0x180008151  xor     edx, edx; dwFlags
0x180008153  call    cs:__imp_CryptCATAdminReleaseContext
0x180008159  mov     eax, ebx
0x18000815b  mov     rcx, [rbp+280h+var_30]
0x180008162  xor     rcx, rsp; StackCookie
0x180008165  call    __security_check_cookie
0x18000816a  lea     r11, [rsp+380h+var_20]
0x180008172  mov     rbx, [r11+40h]
0x180008176  mov     rsi, [r11+48h]
0x18000817a  mov     rsp, r11
0x18000817d  pop     r15
0x18000817f  pop     r14
0x180008181  pop     r13
0x180008183  pop     rdi
0x180008184  pop     rbp
0x180008185  retn
```
