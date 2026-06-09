# Windows::Trust::VerifySelfSignedFile(ushort const *,bool)

- ea: `0x180067558`
- end: `0x18006773c`
- name: `?VerifySelfSignedFile@Trust@Windows@@YA_NPEBG_N@Z`
- size: `484`
- prototype: `bool __fastcall(Windows::Trust *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180058e50`
- `0x180059970`

## callees

- `0x180007660`
- `0x1800209fc`
- `0x1800239f4`
- `0x1800674cc`
- `0x180067558`

## import_xrefs

- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x1800676a6`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x1800676a6`
- `WINTRUST!WinVerifyTrust` at `0x180067619`
- `WINTRUST!WinVerifyTrust` at `0x180067656`
- `WINTRUST!WinVerifyTrust` at `0x1800676f8`
- `WINTRUST!WinVerifyTrust` at `0x180067619`
- `WINTRUST!WinVerifyTrust` at `0x180067656`
- `WINTRUST!WinVerifyTrust` at `0x1800676f8`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x18006763a`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x18006763a`

## string_xrefs

- `0x180067667`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\common\trust.cpp`
- `0x180067709`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\common\trust.cpp`
- `0x180067727`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\common\trust.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall Windows::Trust::VerifySelfSignedFile(Windows::Trust *this, const unsigned __int16 *a2)
{
  bool v2; // bl
  CRYPT_PROVIDER_DATA *v3; // rax
  unsigned int v4; // eax
  CRYPT_PROVIDER_SGNR *ProvSignerFromChain; // rax
  unsigned int v7; // r8d
  const CERT_CHAIN_CONTEXT *pChainContext; // rdi
  unsigned int v9; // r8d
  unsigned int v10; // r8d
  unsigned int v11; // eax
  _QWORD pWVTData[3]; // [rsp+20h] [rbp-59h] BYREF
  int v13; // [rsp+38h] [rbp-41h]
  int v14; // [rsp+3Ch] [rbp-3Dh]
  __int64 v15; // [rsp+40h] [rbp-39h]
  _QWORD *v16; // [rsp+48h] [rbp-31h]
  __int64 v17; // [rsp+50h] [rbp-29h]
  HANDLE hStateData; // [rsp+58h] [rbp-21h]
  __int64 v19; // [rsp+60h] [rbp-19h]
  __int64 v20; // [rsp+68h] [rbp-11h]
  __int64 v21; // [rsp+70h] [rbp-9h]
  _QWORD v22[2]; // [rsp+80h] [rbp+7h] BYREF
  __int128 v23; // [rsp+90h] [rbp+17h]
  _QWORD *v24; // [rsp+A0h] [rbp+27h]
  GUID *p_pgActionID; // [rsp+A8h] [rbp+2Fh]
  char v26; // [rsp+B0h] [rbp+37h]
  GUID pgActionID; // [rsp+B8h] [rbp+3Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  if ( !this )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\common\\trust.cpp",
      (const char *)0x80070057LL,
      pWVTData[0]);
  v22[0] = 32;
  v22[1] = this;
  v23 = 0;
  pWVTData[0] = 88;
  v15 = 1;
  v17 = 1;
  v21 = 0;
  pWVTData[1] = 0;
  pWVTData[2] = 0;
  v13 = 2;
  v2 = 1;
  v14 = 1;
  v20 = 4160;
  v16 = v22;
  hStateData = 0;
  v19 = 0;
  pgActionID.Data1 = -62579690;
  *(_DWORD *)&pgActionID.Data2 = 298953845;
  *(_DWORD *)pgActionID.Data4 = -1073694540;
  *(_DWORD *)&pgActionID.Data4[4] = -1603357105;
  if ( WinVerifyTrust(HWND_MESSAGE|0x2LL, &pgActionID, pWVTData) )
    return 0;
  v24 = pWVTData;
  p_pgActionID = &pgActionID;
  v26 = 1;
  v3 = WTHelperProvDataFromStateData(hStateData);
  if ( !v3 || (ProvSignerFromChain = WTHelperGetProvSignerFromChain(v3, 0, 0, 0)) == 0 )
  {
    LODWORD(v17) = 2;
    v4 = WinVerifyTrust(0, &pgActionID, pWVTData);
    if ( v4 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x5A,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\common\\trust.cpp",
        (const char *)v4,
        pWVTData[0]);
    return 0;
  }
  pChainContext = ProvSignerFromChain->pChainContext;
  if ( !Windows::Trust::VerifyCertificateChain(pChainContext, (const struct _CERT_CHAIN_CONTEXT *const)0x10000, v7)
    && !Windows::Trust::VerifyCertificateChain(pChainContext, 0, v9) )
  {
    v2 = Windows::Trust::VerifyCertificateChain(pChainContext, (const struct _CERT_CHAIN_CONTEXT *const)0x20000, v10);
  }
  LODWORD(v17) = 2;
  v11 = WinVerifyTrust(0, &pgActionID, pWVTData);
  if ( v11 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x5A,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\common\\trust.cpp",
      (const char *)v11,
      pWVTData[0]);
  return v2;
}

```

## disassembly

```asm
0x180067558  mov     [rsp-8+arg_8], rbx
0x18006755d  mov     [rsp-8+arg_10], rdi
0x180067562  push    rbp
0x180067563  lea     rbp, [rsp-57h]
0x180067568  sub     rsp, 0D0h
0x18006756f  mov     rax, cs:__security_cookie
0x180067576  xor     rax, rsp
0x180067579  mov     [rbp+57h+var_8], rax
0x18006757d  mov     rax, [rbp+5Fh]
0x180067581  test    rcx, rcx
0x180067584  jz      loc_180067721
0x18006758a  mov     [rbp+57h+var_50], 20h ; ' '
0x180067592  mov     [rbp+57h+var_48], rcx
0x180067596  xorps   xmm0, xmm0
0x180067599  movdqu  [rbp+57h+var_40], xmm0
0x18006759e  mov     [rbp+57h+pWVTData], 58h ; 'X'
0x1800675a6  mov     [rbp+57h+var_90], 1
0x1800675ae  mov     [rbp+57h+var_80], 1
0x1800675b6  xor     eax, eax
0x1800675b8  mov     [rbp+57h+var_60], rax
0x1800675bc  mov     [rbp+57h+var_A8], rax
0x1800675c0  mov     [rbp+57h+var_A0], rax
0x1800675c4  mov     [rbp+57h+var_98], 2
0x1800675cb  lea     ebx, [rax+1]
0x1800675ce  mov     [rbp+57h+var_94], ebx
0x1800675d1  mov     [rbp+57h+var_68], 1040h
0x1800675d9  lea     rax, [rbp+57h+var_50]
0x1800675dd  mov     [rbp+57h+var_88], rax
0x1800675e1  mov     [rbp+57h+hStateData], 0
0x1800675e9  mov     [rbp+57h+var_70], 0
0x1800675f1  mov     [rbp+57h+pgActionID.Data1], 0FC451C16h
0x1800675f8  mov     dword ptr [rbp+57h+pgActionID.Data2], 11D1AC75h
0x1800675ff  mov     dword ptr [rbp+57h+pgActionID.Data4], 0C000B8B4h
0x180067606  mov     dword ptr [rbp+57h+pgActionID.Data4+4], 0A06EB64Fh
0x18006760d  lea     r8, [rbp+57h+pWVTData]; pWVTData
0x180067611  lea     rdx, [rbp+57h+pgActionID]; pgActionID
0x180067615  or      rcx, 0FFFFFFFFFFFFFFFFh; hwnd
0x180067619  call    cs:__imp_WinVerifyTrust
0x18006761f  test    eax, eax
0x180067621  jnz     short loc_180067678
0x180067623  lea     rax, [rbp+57h+pWVTData]
0x180067627  mov     [rbp+57h+var_30], rax
0x18006762b  lea     rax, [rbp+57h+pgActionID]
0x18006762f  mov     [rbp+57h+var_28], rax
0x180067633  mov     [rbp+57h+var_20], bl
0x180067636  mov     rcx, [rbp+57h+hStateData]; hStateData
0x18006763a  call    cs:__imp_WTHelperProvDataFromStateData
0x180067640  test    rax, rax
0x180067643  jnz     short loc_18006769B
0x180067645  mov     dword ptr [rbp+57h+var_80], 2
0x18006764c  lea     r8, [rbp+57h+pWVTData]; pWVTData
0x180067650  lea     rdx, [rbp+57h+pgActionID]; pgActionID
0x180067654  xor     ecx, ecx; hwnd
0x180067656  call    cs:__imp_WinVerifyTrust
0x18006765c  test    eax, eax
0x18006765e  jz      short loc_180067678
0x180067660  mov     rcx, [rbp+5Fh]; this
0x180067664  mov     r9d, eax; char *
0x180067667  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18006766e  mov     edx, 5Ah ; 'Z'; void *
0x180067673  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180067678  xor     al, al
0x18006767a  mov     rcx, [rbp+57h+var_8]
0x18006767e  xor     rcx, rsp; StackCookie
0x180067681  call    __security_check_cookie
0x180067686  lea     r11, [rsp+0D0h+var_s0]
0x18006768e  mov     rbx, [r11+18h]
0x180067692  mov     rdi, [r11+20h]
0x180067696  mov     rsp, r11
0x180067699  pop     rbp
0x18006769a  retn
0x18006769b  xor     r9d, r9d; idxCounterSigner
0x18006769e  xor     r8d, r8d; fCounterSigner
0x1800676a1  xor     edx, edx; idxSigner
0x1800676a3  mov     rcx, rax; pProvData
0x1800676a6  call    cs:__imp_WTHelperGetProvSignerFromChain
0x1800676ac  test    rax, rax
0x1800676af  jz      short loc_180067645
0x1800676b1  mov     rdi, [rax+38h]
0x1800676b5  mov     edx, 10000h; struct _CERT_CHAIN_CONTEXT *
0x1800676ba  mov     rcx, rdi; pChainContext
0x1800676bd  call    ?VerifyCertificateChain@Trust@Windows@@YA_NQEBU_CERT_CHAIN_CONTEXT@@K@Z; Windows::Trust::VerifyCertificateChain(_CERT_CHAIN_CONTEXT const * const,ulong)
0x1800676c2  test    al, al
0x1800676c4  jnz     short loc_1800676E7
0x1800676c6  xor     edx, edx; struct _CERT_CHAIN_CONTEXT *
0x1800676c8  mov     rcx, rdi; pChainContext
0x1800676cb  call    ?VerifyCertificateChain@Trust@Windows@@YA_NQEBU_CERT_CHAIN_CONTEXT@@K@Z; Windows::Trust::VerifyCertificateChain(_CERT_CHAIN_CONTEXT const * const,ulong)
0x1800676d0  test    al, al
0x1800676d2  jnz     short loc_1800676E7
0x1800676d4  mov     edx, 20000h; struct _CERT_CHAIN_CONTEXT *
0x1800676d9  mov     rcx, rdi; pChainContext
0x1800676dc  call    ?VerifyCertificateChain@Trust@Windows@@YA_NQEBU_CERT_CHAIN_CONTEXT@@K@Z; Windows::Trust::VerifyCertificateChain(_CERT_CHAIN_CONTEXT const * const,ulong)
0x1800676e1  test    al, al
0x1800676e3  jnz     short loc_1800676E7
0x1800676e5  xor     bl, bl
0x1800676e7  mov     dword ptr [rbp+57h+var_80], 2
0x1800676ee  lea     r8, [rbp+57h+pWVTData]; pWVTData
0x1800676f2  lea     rdx, [rbp+57h+pgActionID]; pgActionID
0x1800676f6  xor     ecx, ecx; hwnd
0x1800676f8  call    cs:__imp_WinVerifyTrust
0x1800676fe  test    eax, eax
0x180067700  jz      short loc_18006771A
0x180067702  mov     rcx, [rbp+5Fh]; this
0x180067706  mov     r9d, eax; char *
0x180067709  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180067710  mov     edx, 5Ah ; 'Z'; void *
0x180067715  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18006771a  mov     al, bl
0x18006771c  jmp     loc_18006767A
0x180067721  mov     r9d, 80070057h; char *
0x180067727  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18006772e  mov     edx, 3Ch ; '<'; void *
0x180067733  mov     rcx, rax; this
0x180067736  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
