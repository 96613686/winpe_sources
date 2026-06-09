# AipGetFileSignature

- ea: `0x18000a0f8`
- end: `0x18000a5a0`
- name: `AipGetFileSignature`
- size: `1192`
- prototype: `__int64 __fastcall(HANDLE hFile, __int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180004c28`
- `0x180008c14`

## callees

- `0x1800090a0`
- `0x180009fa8`
- `0x18000a0f8`
- `0x18000a708`
- `0x18000b098`
- `0x18000c0a2`
- `0x18000c0e0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a29b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a29b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4f3`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000a35f`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000a35f`
- `WINTRUST!WinVerifyTrust` at `0x18000a1d7`
- `WINTRUST!WinVerifyTrust` at `0x18000a444`
- `WINTRUST!WinVerifyTrust` at `0x18000a1d7`
- `WINTRUST!WinVerifyTrust` at `0x18000a444`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x18000a4cb`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x18000a4cb`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x18000a3a4`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x18000a3a4`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18000a291`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18000a291`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x18000a565`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x18000a565`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x18000a577`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x18000a577`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x18000a2e5`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x18000a2e5`

## pseudocode

```c
__int64 __fastcall AipGetFileSignature(HANDLE hFile, __int64 a2, __int64 a3, __int64 a4, __int64 a5, _QWORD *a6)
{
  LONG v8; // eax
  int v9; // ebx
  signed int v10; // eax
  __int64 v11; // r8
  void (__fastcall *v12)(const wchar_t *, const wchar_t *, __int64); // rax
  const wchar_t *v13; // rdx
  const wchar_t *v14; // rcx
  HANDLE v15; // rcx
  signed int LastError; // eax
  __int64 v17; // r8
  void (__fastcall *v18)(const wchar_t *, const wchar_t *, __int64); // rax
  const wchar_t *v19; // rdx
  const wchar_t *v20; // rcx
  signed int v21; // eax
  NTSTATUS v22; // edi
  HANDLE v23; // rax
  HCATINFO v24; // rdi
  signed int v25; // eax
  __int64 v26; // r8
  signed int v27; // eax
  void (__fastcall *v28)(const wchar_t *, const wchar_t *, __int64); // rax
  const wchar_t *v29; // rdx
  const wchar_t *v30; // rcx
  DWORD pcbHash; // [rsp+30h] [rbp-D0h] BYREF
  HCATADMIN phCatAdmin; // [rsp+38h] [rbp-C8h] BYREF
  HCATINFO phPrevCatInfo; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD pWVTData[6]; // [rsp+50h] [rbp-B0h] BYREF
  int v36; // [rsp+68h] [rbp-98h]
  int v37; // [rsp+6Ch] [rbp-94h]
  int v38; // [rsp+70h] [rbp-90h]
  _QWORD *v39; // [rsp+78h] [rbp-88h]
  int v40; // [rsp+80h] [rbp-80h]
  HANDLE hStateData; // [rsp+88h] [rbp-78h]
  int v42; // [rsp+98h] [rbp-68h]
  _QWORD v43[4]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v44[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v45; // [rsp+E0h] [rbp-20h]
  HANDLE v46; // [rsp+F0h] [rbp-10h]
  BYTE *v47; // [rsp+F8h] [rbp-8h]
  DWORD v48; // [rsp+100h] [rbp+0h]
  __int64 v49; // [rsp+104h] [rbp+4h]
  __int64 v50; // [rsp+10Ch] [rbp+Ch]
  int v51; // [rsp+114h] [rbp+14h]
  CATALOG_INFO psCatInfo; // [rsp+120h] [rbp+20h] BYREF
  BYTE pbHash[32]; // [rsp+330h] [rbp+230h] BYREF

  memset_0(v44, 0, 0x48u);
  phPrevCatInfo = 0;
  pcbHash = 32;
  phCatAdmin = 0;
  memset_0(&psCatInfo, 0, sizeof(psCatInfo));
  memset_0(pWVTData, 0, 0x58u);
  v43[0] = 32;
  v38 = 1;
  v40 = 1;
  v37 = 1;
  v43[3] = 0;
  v43[2] = hFile;
  v43[1] = a2;
  pWVTData[0] = 88;
  v36 = 2;
  v39 = v43;
  v42 = 4224;
  v8 = WinVerifyTrust(HWND_MESSAGE|0x2LL, (GUID *)&pgActionID, pWVTData);
  v9 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v11 = (unsigned __int16)v8 | 0xC0070000;
    else
      v11 = (unsigned int)v8;
    v12 = (void (__fastcall *)(const wchar_t *, const wchar_t *, __int64))g_AiLogFunctionCallErrorEvent;
    if ( g_AiLogFunctionCallErrorEvent )
    {
      v13 = L">@";
      v14 = L"&(";
      goto LABEL_13;
    }
  }
  else
  {
    v10 = AipVerifyFileSignatureSystem(pWVTData);
    v9 = v10;
    if ( v10 )
    {
      v11 = v10 > 0 ? (unsigned __int16)v10 | 0xC0070000 : (unsigned int)v10;
      v12 = (void (__fastcall *)(const wchar_t *, const wchar_t *, __int64))g_AiLogFunctionCallErrorEvent;
      if ( g_AiLogFunctionCallErrorEvent )
      {
        v13 = L"8:";
        v14 = L"&(";
LABEL_13:
        v12(v14, v13, v11);
      }
    }
  }
  v15 = hStateData;
  if ( hStateData )
  {
    AipAddCertsToCertStore(hStateData);
    v15 = hStateData;
  }
  if ( !v9 )
  {
    *a6 = v15;
    goto LABEL_63;
  }
  AipFreeFileSignature(v15);
  if ( !CryptCATAdminCalcHashFromFileHandle(hFile, &pcbHash, pbHash, 0) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v17 = (unsigned __int16)LastError | 0xC0070000;
    else
      v17 = (unsigned int)LastError;
    v18 = (void (__fastcall *)(const wchar_t *, const wchar_t *, __int64))g_AiLogFunctionCallErrorEvent;
    if ( !g_AiLogFunctionCallErrorEvent )
      goto LABEL_63;
    v19 = L"FH";
    v20 = L"&(";
    goto LABEL_24;
  }
  if ( !CryptCATAdminAcquireContext(&phCatAdmin, 0, 0) )
  {
    v21 = GetLastError();
    v9 = v21;
    if ( v21 > 0 )
      v17 = (unsigned __int16)v21 | 0xC0070000;
    else
      v17 = (unsigned int)v21;
    v18 = (void (__fastcall *)(const wchar_t *, const wchar_t *, __int64))g_AiLogFunctionCallErrorEvent;
    if ( !g_AiLogFunctionCallErrorEvent )
      goto LABEL_63;
    v19 = L"68";
    v20 = L"&(";
LABEL_24:
    v18(v20, v19, v17);
    goto LABEL_63;
  }
  if ( a5 && (v22 = AiGetCatalogLastWriteTime(a5 + 40), v22 < 0) )
  {
    if ( g_AiLogFunctionCallErrorEvent )
      g_AiLogFunctionCallErrorEvent(L"&(", L"24", (unsigned int)v22);
    v9 = RtlNtStatusToDosErrorNoTeb(v22);
    if ( v9 == 317 )
      v9 = v22;
  }
  else
  {
    for ( phPrevCatInfo = 0; ; phPrevCatInfo = v24 )
    {
      v24 = CryptCATAdminEnumCatalogFromHash(phCatAdmin, pbHash, pcbHash, 0, &phPrevCatInfo);
      if ( !v24 )
      {
        v25 = GetLastError();
        v9 = v25;
        if ( v25 > 0 )
          v26 = (unsigned __int16)v25 | 0xC0070000;
        else
          v26 = (unsigned int)v25;
        v28 = (void (__fastcall *)(const wchar_t *, const wchar_t *, __int64))g_AiLogFunctionCallErrorEvent;
        if ( g_AiLogFunctionCallErrorEvent )
        {
          v29 = L"@B";
          v30 = L"&(";
          goto LABEL_60;
        }
        goto LABEL_61;
      }
      memset_0(psCatInfo.wszCatalogFile, 0, sizeof(psCatInfo.wszCatalogFile));
      psCatInfo.cbStruct = 524;
      if ( !CryptCATCatalogInfoFromContext(v24, &psCatInfo, 0) )
        break;
      memset_0(pWVTData, 0, 0x58u);
      v44[0] = 72;
      v44[1] = psCatInfo.wszCatalogFile;
      v49 = 0;
      v47 = pbHash;
      v48 = pcbHash;
      v50 = 0;
      v36 = 2;
      v38 = 2;
      v39 = v44;
      v40 = 1;
      v37 = 1;
      v51 = 0;
      v45 = 0;
      v46 = hFile;
      pWVTData[0] = 88;
      v42 = 4224;
      v9 = WinVerifyTrust(HWND_MESSAGE|0x2LL, (GUID *)&pgActionID, pWVTData);
      v23 = hStateData;
      if ( hStateData )
      {
        AipAddCertsToCertStore(hStateData);
        v23 = hStateData;
      }
      if ( !v9 )
      {
        *a6 = v23;
        goto LABEL_61;
      }
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0xC0070000;
      if ( g_AiLogFunctionCallErrorEvent )
        g_AiLogFunctionCallErrorEvent(L"&(", L"DF", (unsigned int)v9);
      AipFreeFileSignature(hStateData);
    }
    v27 = GetLastError();
    v9 = v27;
    if ( v27 > 0 )
      v26 = (unsigned __int16)v27 | 0xC0070000;
    else
      v26 = (unsigned int)v27;
    v28 = (void (__fastcall *)(const wchar_t *, const wchar_t *, __int64))g_AiLogFunctionCallErrorEvent;
    if ( g_AiLogFunctionCallErrorEvent )
    {
      v29 = L"<>";
      v30 = L"&(";
LABEL_60:
      v28(v30, v29, v26);
    }
LABEL_61:
    if ( v24 )
      CryptCATAdminReleaseCatalogContext(phCatAdmin, v24, 0);
  }
LABEL_63:
  if ( phCatAdmin )
    CryptCATAdminReleaseContext(phCatAdmin, 0);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000a0f8  push    rbp
0x18000a0fa  push    rbx
0x18000a0fb  push    rsi
0x18000a0fc  push    rdi
0x18000a0fd  push    r12
0x18000a0ff  push    r14
0x18000a101  push    r15
0x18000a103  lea     rbp, [rsp-260h]
0x18000a10b  sub     rsp, 360h
0x18000a112  mov     rax, cs:__security_cookie
0x18000a119  xor     rax, rsp
0x18000a11c  mov     [rbp+290h+var_40], rax
0x18000a123  mov     rsi, [rbp+290h+arg_20]
0x18000a12a  mov     rbx, rdx
0x18000a12d  mov     r14, [rbp+290h+arg_28]
0x18000a134  xor     edx, edx; Val
0x18000a136  mov     r12, rcx
0x18000a139  mov     r15, r9
0x18000a13c  lea     rcx, [rbp+290h+var_2C0]; void *
0x18000a140  lea     r8d, [rdx+48h]; Size
0x18000a144  call    memset_0
0x18000a149  mov     edi, 20h ; ' '
0x18000a14e  mov     [rsp+390h+var_350], 0
0x18000a157  xor     edx, edx; Val
0x18000a159  mov     [rsp+390h+pcbHash], edi
0x18000a15d  mov     r8d, 20Ch; Size
0x18000a163  mov     [rsp+390h+phCatAdmin], 0
0x18000a16c  lea     rcx, [rbp+290h+psCatInfo]; void *
0x18000a170  call    memset_0
0x18000a175  xor     edx, edx; Val
0x18000a177  lea     r8d, [rdi+38h]; Size
0x18000a17b  lea     rcx, [rsp+390h+pWVTData]; void *
0x18000a180  call    memset_0
0x18000a185  lea     ecx, [rdi-1Fh]
0x18000a188  mov     [rbp+290h+var_2E0], rdi
0x18000a18c  mov     [rsp+390h+var_320], ecx
0x18000a190  lea     rax, [rbp+290h+var_2E0]
0x18000a194  mov     [rbp+290h+var_310], ecx
0x18000a197  lea     r8, [rsp+390h+pWVTData]; pWVTData
0x18000a19c  mov     [rsp+390h+var_324], ecx
0x18000a1a0  lea     rdx, pgActionID; pgActionID
0x18000a1a7  or      rcx, 0FFFFFFFFFFFFFFFFh; hwnd
0x18000a1ab  mov     [rbp+290h+var_2C8], 0
0x18000a1b3  mov     [rbp+290h+var_2D0], r12
0x18000a1b7  mov     [rbp+290h+var_2D8], rbx
0x18000a1bb  mov     [rsp+390h+pWVTData], 58h ; 'X'
0x18000a1c3  mov     [rsp+390h+var_328], 2
0x18000a1cb  mov     [rsp+390h+var_318], rax
0x18000a1d0  mov     [rbp+290h+var_2F8], 1080h
0x18000a1d7  call    cs:__imp_WinVerifyTrust
0x18000a1dd  mov     ebx, eax
0x18000a1df  mov     edi, 0C0070000h
0x18000a1e4  test    eax, eax
0x18000a1e6  jnz     short loc_18000A222
0x18000a1e8  lea     rcx, [rsp+390h+pWVTData]
0x18000a1ed  call    AipVerifyFileSignatureSystem
0x18000a1f2  mov     ebx, eax
0x18000a1f4  test    eax, eax
0x18000a1f6  jz      short loc_18000A24F
0x18000a1f8  jg      short loc_18000A1FF
0x18000a1fa  mov     r8d, eax
0x18000a1fd  jmp     short loc_18000A206
0x18000a1ff  movzx   r8d, ax
0x18000a203  or      r8d, edi
0x18000a206  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x18000a20d  test    rax, rax
0x18000a210  jz      short loc_18000A24F
0x18000a212  lea     rdx, a8_0; "8:"
0x18000a219  lea     rcx, asc_18000F030; "&("
0x18000a220  jmp     short loc_18000A24A
0x18000a222  jg      short loc_18000A229
0x18000a224  mov     r8d, eax
0x18000a227  jmp     short loc_18000A230
0x18000a229  movzx   r8d, ax
0x18000a22d  or      r8d, edi
0x18000a230  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x18000a237  test    rax, rax
0x18000a23a  jz      short loc_18000A24F
0x18000a23c  lea     rdx, asc_18000F020; ">@"
0x18000a243  lea     rcx, asc_18000F010; "&("
0x18000a24a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a24f  mov     rcx, [rbp+290h+hStateData]; hStateData
0x18000a253  test    rcx, rcx
0x18000a256  jz      short loc_18000A26E
0x18000a258  xor     edx, edx
0x18000a25a  mov     r9, rsi
0x18000a25d  test    ebx, ebx
0x18000a25f  mov     r8, r15
0x18000a262  setnz   dl
0x18000a265  call    AipAddCertsToCertStore
0x18000a26a  mov     rcx, [rbp+290h+hStateData]
0x18000a26e  test    ebx, ebx
0x18000a270  jnz     short loc_18000A27A
0x18000a272  mov     [r14], rcx
0x18000a275  jmp     loc_18000A56B
0x18000a27a  call    AipFreeFileSignature
0x18000a27f  xor     r9d, r9d; dwFlags
0x18000a282  lea     r8, [rbp+290h+pbHash]; pbHash
0x18000a289  lea     rdx, [rsp+390h+pcbHash]; pcbHash
0x18000a28e  mov     rcx, r12; hFile
0x18000a291  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle
0x18000a297  test    eax, eax
0x18000a299  jnz     short loc_18000A2DB
0x18000a29b  call    cs:__imp_GetLastError
0x18000a2a1  mov     ebx, eax
0x18000a2a3  test    eax, eax
0x18000a2a5  jg      short loc_18000A2AC
0x18000a2a7  mov     r8d, eax
0x18000a2aa  jmp     short loc_18000A2B3
0x18000a2ac  movzx   r8d, ax
0x18000a2b0  or      r8d, edi
0x18000a2b3  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x18000a2ba  test    rax, rax
0x18000a2bd  jz      loc_18000A56B
0x18000a2c3  lea     rdx, aFh; "FH"
0x18000a2ca  lea     rcx, asc_18000EFF0; "&("
0x18000a2d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2d6  jmp     loc_18000A56B
0x18000a2db  xor     r8d, r8d; dwFlags
0x18000a2de  lea     rcx, [rsp+390h+phCatAdmin]; phCatAdmin
0x18000a2e3  xor     edx, edx; pgSubsystem
0x18000a2e5  call    cs:__imp_CryptCATAdminAcquireContext
0x18000a2eb  test    eax, eax
0x18000a2ed  jnz     short loc_18000A327
0x18000a2ef  call    cs:__imp_GetLastError
0x18000a2f5  mov     ebx, eax
0x18000a2f7  test    eax, eax
0x18000a2f9  jg      short loc_18000A300
0x18000a2fb  mov     r8d, eax
0x18000a2fe  jmp     short loc_18000A307
0x18000a300  movzx   r8d, ax
0x18000a304  or      r8d, edi
0x18000a307  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x18000a30e  test    rax, rax
0x18000a311  jz      loc_18000A56B
0x18000a317  lea     rdx, a68; "68"
0x18000a31e  lea     rcx, asc_18000EFD0; "&("
0x18000a325  jmp     short loc_18000A2D1
0x18000a327  test    rsi, rsi
0x18000a32a  jz      short loc_18000A374
0x18000a32c  lea     rcx, [rsi+28h]
0x18000a330  call    AiGetCatalogLastWriteTime
0x18000a335  mov     edi, eax
0x18000a337  test    eax, eax
0x18000a339  jns     short loc_18000A374
0x18000a33b  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x18000a342  test    rax, rax
0x18000a345  jz      short loc_18000A35D
0x18000a347  mov     r8d, edi
0x18000a34a  lea     rdx, a24_6; "24"
0x18000a351  lea     rcx, asc_18000EFB0; "&("
0x18000a358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a35d  mov     ecx, edi; Status
0x18000a35f  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18000a365  cmp     eax, 13Dh
0x18000a36a  mov     ebx, eax
0x18000a36c  cmovz   ebx, edi
0x18000a36f  jmp     loc_18000A56B
0x18000a374  mov     [rsp+390h+var_350], 0
0x18000a37d  jmp     loc_18000A4AD
0x18000a382  xor     edx, edx; Val
0x18000a384  lea     rcx, [rbp+290h+psCatInfo.wszCatalogFile]; void *
0x18000a388  mov     r8d, 208h; Size
0x18000a38e  call    memset_0
0x18000a393  xor     r8d, r8d; dwFlags
0x18000a396  mov     [rbp+290h+psCatInfo.cbStruct], 20Ch
0x18000a39d  lea     rdx, [rbp+290h+psCatInfo]; psCatInfo
0x18000a3a1  mov     rcx, rdi; hCatInfo
0x18000a3a4  call    cs:__imp_CryptCATCatalogInfoFromContext
0x18000a3aa  test    eax, eax
0x18000a3ac  jz      loc_18000A4F3
0x18000a3b2  mov     ebx, 58h ; 'X'
0x18000a3b7  lea     rcx, [rsp+390h+pWVTData]; void *
0x18000a3bc  mov     r8d, ebx; Size
0x18000a3bf  xor     edx, edx; Val
0x18000a3c1  call    memset_0
0x18000a3c6  lea     rax, [rbp+290h+psCatInfo.wszCatalogFile]
0x18000a3ca  mov     [rbp+290h+var_2C0], 48h ; 'H'
0x18000a3d2  mov     [rbp+290h+var_2B8], rax
0x18000a3d6  lea     r8, [rsp+390h+pWVTData]; pWVTData
0x18000a3db  lea     rax, [rbp+290h+pbHash]
0x18000a3e2  mov     [rbp+290h+var_28C], 0
0x18000a3ea  mov     [rbp+290h+var_298], rax
0x18000a3ee  lea     rdx, pgActionID; pgActionID
0x18000a3f5  mov     eax, [rsp+390h+pcbHash]
0x18000a3f9  xorps   xmm0, xmm0
0x18000a3fc  mov     [rbp+290h+var_290], eax
0x18000a3ff  or      rcx, 0FFFFFFFFFFFFFFFFh; hwnd
0x18000a403  lea     eax, [rbx-56h]
0x18000a406  mov     [rbp+290h+var_284], 0
0x18000a40e  mov     [rsp+390h+var_328], eax
0x18000a412  mov     [rsp+390h+var_320], eax
0x18000a416  lea     rax, [rbp+290h+var_2C0]
0x18000a41a  mov     [rsp+390h+var_318], rax
0x18000a41f  lea     eax, [rbx-57h]
0x18000a422  mov     [rbp+290h+var_310], eax
0x18000a425  mov     [rsp+390h+var_324], eax
0x18000a429  mov     [rbp+290h+var_27C], 0
0x18000a430  movdqa  [rbp+290h+var_2B0], xmm0
0x18000a435  mov     [rbp+290h+var_2A0], r12
0x18000a439  mov     [rsp+390h+pWVTData], ebx
0x18000a43d  mov     [rbp+290h+var_2F8], 1080h
0x18000a444  call    cs:__imp_WinVerifyTrust
0x18000a44a  mov     ebx, eax
0x18000a44c  mov     rax, [rbp+290h+hStateData]
0x18000a450  test    rax, rax
0x18000a453  jz      short loc_18000A46E
0x18000a455  xor     edx, edx
0x18000a457  mov     r9, rsi
0x18000a45a  test    ebx, ebx
0x18000a45c  mov     r8, r15
0x18000a45f  mov     rcx, rax; hStateData
0x18000a462  setnz   dl
0x18000a465  call    AipAddCertsToCertStore
0x18000a46a  mov     rax, [rbp+290h+hStateData]
0x18000a46e  test    ebx, ebx
0x18000a470  jz      short loc_18000A4EE
0x18000a472  jle     short loc_18000A47D
0x18000a474  movzx   ebx, bx
0x18000a477  or      ebx, 0C0070000h
0x18000a47d  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x18000a484  test    rax, rax
0x18000a487  jz      short loc_18000A49F
0x18000a489  mov     r8d, ebx
0x18000a48c  lea     rdx, aDf_0; "DF"
0x18000a493  lea     rcx, asc_18000EF50; "&("
0x18000a49a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a49f  mov     rcx, [rbp+290h+hStateData]
0x18000a4a3  call    AipFreeFileSignature
0x18000a4a8  mov     [rsp+390h+var_350], rdi
0x18000a4ad  mov     r8d, [rsp+390h+pcbHash]; cbHash
0x18000a4b2  lea     rax, [rsp+390h+var_350]
0x18000a4b7  mov     rcx, [rsp+390h+phCatAdmin]; hCatAdmin
0x18000a4bc  lea     rdx, [rbp+290h+pbHash]; pbHash
0x18000a4c3  xor     r9d, r9d; dwFlags
0x18000a4c6  mov     [rsp+390h+phPrevCatInfo], rax; phPrevCatInfo
0x18000a4cb  call    cs:__imp_CryptCATAdminEnumCatalogFromHash
0x18000a4d1  mov     rdi, rax
0x18000a4d4  test    rax, rax
0x18000a4d7  jnz     loc_18000A382
0x18000a4dd  call    cs:__imp_GetLastError
0x18000a4e3  mov     ebx, eax
0x18000a4e5  test    eax, eax
0x18000a4e7  jg      short loc_18000A52B
0x18000a4e9  mov     r8d, eax
0x18000a4ec  jmp     short loc_18000A536
0x18000a4ee  mov     [r14], rax
0x18000a4f1  jmp     short loc_18000A555
0x18000a4f3  call    cs:__imp_GetLastError
0x18000a4f9  mov     ebx, eax
0x18000a4fb  test    eax, eax
0x18000a4fd  jg      short loc_18000A504
0x18000a4ff  mov     r8d, eax
0x18000a502  jmp     short loc_18000A50F
0x18000a504  movzx   r8d, ax
0x18000a508  or      r8d, 0C0070000h
0x18000a50f  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x18000a516  test    rax, rax
0x18000a519  jz      short loc_18000A555
0x18000a51b  lea     rdx, asc_18000EF80; "<>"
0x18000a522  lea     rcx, asc_18000EF70; "&("
0x18000a529  jmp     short loc_18000A550
0x18000a52b  movzx   r8d, ax
0x18000a52f  or      r8d, 0C0070000h
0x18000a536  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x18000a53d  test    rax, rax
0x18000a540  jz      short loc_18000A555
0x18000a542  lea     rdx, aB; "@B"
0x18000a549  lea     rcx, asc_18000EF90; "&("
0x18000a550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a555  test    rdi, rdi
0x18000a558  jz      short loc_18000A56B
0x18000a55a  mov     rcx, [rsp+390h+phCatAdmin]; hCatAdmin
0x18000a55f  xor     r8d, r8d; dwFlags
0x18000a562  mov     rdx, rdi; hCatInfo
0x18000a565  call    cs:__imp_CryptCATAdminReleaseCatalogContext
0x18000a56b  mov     rcx, [rsp+390h+phCatAdmin]; hCatAdmin
0x18000a570  test    rcx, rcx
0x18000a573  jz      short loc_18000A57D
0x18000a575  xor     edx, edx; dwFlags
0x18000a577  call    cs:__imp_CryptCATAdminReleaseContext
0x18000a57d  mov     eax, ebx
0x18000a57f  mov     rcx, [rbp+290h+var_40]
0x18000a586  xor     rcx, rsp; StackCookie
0x18000a589  call    __security_check_cookie
0x18000a58e  add     rsp, 360h
0x18000a595  pop     r15
0x18000a597  pop     r14
0x18000a599  pop     r12
0x18000a59b  pop     rdi
0x18000a59c  pop     rsi
0x18000a59d  pop     rbx
0x18000a59e  pop     rbp
0x18000a59f  retn
```
