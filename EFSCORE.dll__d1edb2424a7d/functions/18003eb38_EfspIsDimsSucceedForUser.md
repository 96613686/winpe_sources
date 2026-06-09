# EfspIsDimsSucceedForUser

- ea: `0x18003eb38`
- end: `0x18003ee38`
- name: `EfspIsDimsSucceedForUser`
- size: `768`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800392a0`

## callees

- `0x18000b7f8`
- `0x18000b884`
- `0x18003eb38`
- `0x180063698`
- `0x1800d87ac`
- `0x1800dddf0`
- `0x1800ddeb0`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ed4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ed82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ed4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ed82`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003ed43`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003ed43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003ed29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003ed29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003edeb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003edeb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003ed11`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003ed11`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003ed78`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003ed78`
- `SspiCli!LsaFreeReturnBuffer` at `0x18003eddc`
- `SspiCli!LsaFreeReturnBuffer` at `0x18003eddc`
- `SspiCli!LsaGetLogonSessionData` at `0x18003ed9a`
- `SspiCli!LsaGetLogonSessionData` at `0x18003ed9a`

## pseudocode

```c
__int64 __fastcall EfspIsDimsSucceedForUser(__int64 a1)
{
  __int64 v2; // rcx
  unsigned int v3; // r15d
  __int64 v4; // rax
  unsigned __int64 v5; // rsi
  unsigned __int16 *p_ReturnLength; // rbx
  unsigned __int64 v7; // rdi
  __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // rsp
  void *v11; // rsp
  unsigned __int16 *v12; // rax
  int v13; // r8d
  char v14; // si
  __int64 *v15; // rdx
  int v16; // eax
  int ValueW; // eax
  HANDLE CurrentThread; // rax
  __int64 v20; // [rsp+0h] [rbp-40h] BYREF
  DWORD ReturnLength; // [rsp+40h] [rbp+0h] BYREF
  PSECURITY_LOGON_SESSION_DATA ppLogonSessionData; // [rsp+48h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+10h] BYREF
  LARGE_INTEGER pvData[2]; // [rsp+58h] [rbp+18h] BYREF
  int TokenInformation; // [rsp+68h] [rbp+28h] BYREF
  _LUID LogonId[2]; // [rsp+6Ch] [rbp+2Ch] BYREF
  __int128 v27; // [rsp+7Ch] [rbp+3Ch]
  __int128 v28; // [rsp+8Ch] [rbp+4Ch]
  int v29; // [rsp+9Ch] [rbp+5Ch]

  ReturnLength = 8;
  pvData[0].QuadPart = 0;
  TokenHandle = 0;
  ppLogonSessionData = 0;
  v2 = *(_QWORD *)(a1 + 24);
  v3 = 0;
  TokenInformation = 0;
  v29 = 0;
  *(_OWORD *)&LogonId[0].LowPart = 0;
  v27 = 0;
  v28 = 0;
  if ( v2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)(v2 + 2 * v4) );
    v5 = v4 + 51;
    p_ReturnLength = 0;
    v7 = 2 * (v4 + 51);
    if ( !v7
      || v7 > g_ulMaxStackAllocSize
      || v7 + g_ulAdditionalProbeSize + 8 < v7
      || !(unsigned int)VerifyStackAvailable() )
    {
      goto LABEL_46;
    }
    v8 = v7 + 23;
    if ( v7 + 23 <= v7 + 8 )
      v8 = 0xFFFFFFFFFFFFFF0LL;
    v9 = v8 & 0xFFFFFFFFFFFFFFF0uLL;
    v10 = alloca(v9);
    v11 = alloca(v9);
    p_ReturnLength = (unsigned __int16 *)&ReturnLength;
    if ( &v20 == (__int64 *)-64LL
      || (ReturnLength = 1801679955, (p_ReturnLength = (unsigned __int16 *)&ppLogonSessionData) == 0) )
    {
LABEL_46:
      if ( v7 + 8 >= v7 )
      {
        v12 = (unsigned __int16 *)((__int64 (*)(void))g_pfnAllocate)();
        p_ReturnLength = v12;
        if ( v12 )
        {
          *(_DWORD *)v12 = 1885431112;
          p_ReturnLength = v12 + 4;
        }
      }
    }
    if ( !p_ReturnLength )
    {
      v13 = 2 * v5;
      v14 = 116;
      v15 = EFS_ERROR_MEMORY;
LABEL_17:
      v16 = fnEfsLogTrace1(g_hPublisher, (_DWORD)v15, v13, 12, v14);
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v16, 12, v14);
      goto LABEL_36;
    }
    ValueW = StringCchCopyW(p_ReturnLength, v5, *(const unsigned __int16 **)(a1 + 24));
    if ( ValueW < 0 )
    {
      v14 = 123;
LABEL_20:
      v13 = ValueW;
      v15 = (__int64 *)&EFS_API_ERROR;
      goto LABEL_17;
    }
    ValueW = StringCchCatW(p_ReturnLength, v5, L"\\Software\\Microsoft\\Windows NT\\CurrentVersion\\DIMS");
    if ( ValueW < 0 )
    {
      v14 = -126;
      goto LABEL_20;
    }
    ValueW = RegGetValueW(HKEY_USERS, p_ReturnLength, L"LastSucceedTimestamp", 0x40u, 0, pvData, &ReturnLength);
    if ( ValueW || ReturnLength != 8 )
    {
      v14 = -115;
      goto LABEL_20;
    }
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
    {
      ValueW = GetLastError();
      v14 = -103;
      goto LABEL_20;
    }
    if ( !GetTokenInformation(TokenHandle, TokenStatistics, &TokenInformation, 0x38u, &ReturnLength) )
    {
      ValueW = GetLastError();
      v14 = -94;
      goto LABEL_20;
    }
    ValueW = LsaGetLogonSessionData((PLUID)&LogonId[0].HighPart, &ppLogonSessionData);
    if ( ValueW || !ppLogonSessionData )
    {
      v14 = -87;
      goto LABEL_20;
    }
    if ( pvData[0].QuadPart >= ppLogonSessionData->LogonTime.QuadPart )
      v3 = 1;
  }
  else
  {
    p_ReturnLength = 0;
  }
LABEL_36:
  if ( ppLogonSessionData )
    LsaFreeReturnBuffer(ppLogonSessionData);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( p_ReturnLength && *((_DWORD *)p_ReturnLength - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  return v3;
}

```

## disassembly

```asm
0x18003eb38  push    rbp
0x18003eb3a  push    rdi
0x18003eb3b  push    r12
0x18003eb3d  push    r14
0x18003eb3f  push    r15
0x18003eb41  sub     rsp, 0B0h
0x18003eb48  lea     rbp, [rsp+40h]
0x18003eb4d  mov     [rbp+90h+arg_8], rbx
0x18003eb54  mov     [rbp+90h+arg_10], rsi
0x18003eb5b  mov     rax, cs:__security_cookie
0x18003eb62  xor     rax, rbp
0x18003eb65  mov     [rbp+90h+var_30], rax
0x18003eb69  xor     r12d, r12d
0x18003eb6c  mov     [rbp+90h+ReturnLength], 8
0x18003eb73  xorps   xmm0, xmm0
0x18003eb76  mov     qword ptr [rbp+90h+var_78], r12
0x18003eb7a  xor     eax, eax
0x18003eb7c  mov     [rbp+90h+TokenHandle], r12
0x18003eb80  mov     r14, rcx
0x18003eb83  mov     [rbp+90h+ppLogonSessionData], r12
0x18003eb87  mov     rcx, [rcx+18h]
0x18003eb8b  mov     r15d, r12d
0x18003eb8e  mov     [rbp+90h+TokenInformation], r12d
0x18003eb92  mov     [rbp+90h+var_34], eax
0x18003eb95  movups  xmmword ptr [rbp+90h+LogonId.LowPart], xmm0
0x18003eb99  movups  [rbp+90h+var_54], xmm0
0x18003eb9d  movups  [rbp+90h+var_44], xmm0
0x18003eba1  test    rcx, rcx
0x18003eba4  jz      loc_18003EDD0
0x18003ebaa  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003ebae  inc     rax
0x18003ebb1  cmp     [rcx+rax*2], r12w
0x18003ebb6  jnz     short loc_18003EBAE
0x18003ebb8  lea     rsi, [rax+33h]
0x18003ebbc  mov     rbx, r12
0x18003ebbf  lea     rdi, [rsi+rsi]
0x18003ebc3  test    rdi, rdi
0x18003ebc6  jz      short loc_18003EC29
0x18003ebc8  cmp     rdi, cs:g_ulMaxStackAllocSize
0x18003ebcf  ja      short loc_18003EC29
0x18003ebd1  mov     rcx, cs:g_ulAdditionalProbeSize
0x18003ebd8  add     rcx, 8
0x18003ebdc  add     rcx, rdi
0x18003ebdf  cmp     rcx, rdi
0x18003ebe2  jb      short loc_18003EC29
0x18003ebe4  call    VerifyStackAvailable
0x18003ebe9  test    eax, eax
0x18003ebeb  jz      short loc_18003EC29
0x18003ebed  lea     rax, [rdi+8]
0x18003ebf1  lea     rcx, [rax+0Fh]
0x18003ebf5  cmp     rcx, rax
0x18003ebf8  ja      short loc_18003EC04
0x18003ebfa  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18003ec04  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18003ec08  mov     rax, rcx
0x18003ec0b  call    _alloca_probe
0x18003ec10  sub     rsp, rcx
0x18003ec13  lea     rbx, [rsp+0D0h+ReturnLength]
0x18003ec18  test    rbx, rbx
0x18003ec1b  jz      short loc_18003EC29
0x18003ec1d  mov     dword ptr [rbx], 6B637453h
0x18003ec23  add     rbx, 8
0x18003ec27  jnz     short loc_18003EC50
0x18003ec29  lea     rcx, [rdi+8]
0x18003ec2d  cmp     rcx, rdi
0x18003ec30  jb      short loc_18003EC50
0x18003ec32  mov     rax, cs:g_pfnAllocate
0x18003ec39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ec3e  mov     rbx, rax
0x18003ec41  test    rax, rax
0x18003ec44  jz      short loc_18003EC50
0x18003ec46  mov     dword ptr [rax], 70616548h
0x18003ec4c  add     rbx, 8
0x18003ec50  test    rbx, rbx
0x18003ec53  jnz     short loc_18003EC9D
0x18003ec55  lea     r8d, [rsi+rsi]
0x18003ec59  mov     esi, 0D74h
0x18003ec5e  lea     edi, [rbx+0Ch]
0x18003ec61  lea     rdx, EFS_ERROR_MEMORY
0x18003ec68  mov     rcx, cs:g_hPublisher
0x18003ec6f  mov     r9d, edi
0x18003ec72  mov     dword ptr [rsp+0D0h+pdwType], esi
0x18003ec76  call    fnEfsLogTrace1
0x18003ec7b  mov     rcx, cs:g_hPublisher
0x18003ec82  lea     rdx, EFS_TRACE_ERROR
0x18003ec89  mov     r9d, edi
0x18003ec8c  mov     dword ptr [rsp+0D0h+pdwType], esi
0x18003ec90  mov     r8d, eax
0x18003ec93  call    fnEfsLogTrace1
0x18003ec98  jmp     loc_18003EDD3
0x18003ec9d  mov     r8, [r14+18h]; unsigned __int16 *
0x18003eca1  mov     rdx, rsi; unsigned __int64
0x18003eca4  mov     rcx, rbx; unsigned __int16 *
0x18003eca7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003ecac  test    eax, eax
0x18003ecae  jns     short loc_18003ECC6
0x18003ecb0  mov     esi, 0D7Bh
0x18003ecb5  mov     edi, 0Ch
0x18003ecba  mov     r8d, eax
0x18003ecbd  lea     rdx, EFS_API_ERROR
0x18003ecc4  jmp     short loc_18003EC68
0x18003ecc6  lea     r8, aSoftwareMicros_5; "\\Software\\Microsoft\\Windows NT\\Curr"...
0x18003eccd  mov     rdx, rsi; unsigned __int64
0x18003ecd0  mov     rcx, rbx; unsigned __int16 *
0x18003ecd3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003ecd8  test    eax, eax
0x18003ecda  jns     short loc_18003ECE3
0x18003ecdc  mov     esi, 0D82h
0x18003ece1  jmp     short loc_18003ECB5
0x18003ece3  lea     rax, [rbp+90h+ReturnLength]
0x18003ece7  mov     r9d, 40h ; '@'; dwFlags
0x18003eced  mov     [rsp+0D0h+pcbData], rax; pcbData
0x18003ecf2  lea     r8, aLastsucceedtim; "LastSucceedTimestamp"
0x18003ecf9  lea     rax, [rbp+90h+var_78]
0x18003ecfd  mov     rdx, rbx; lpSubKey
0x18003ed00  mov     [rsp+0D0h+pvData], rax; pvData
0x18003ed05  mov     rcx, 0FFFFFFFF80000003h; hkey
0x18003ed0c  mov     [rsp+0D0h+pdwType], r12; pdwType
0x18003ed11  call    cs:__imp_RegGetValueW
0x18003ed17  test    eax, eax
0x18003ed19  jnz     loc_18003EDC6
0x18003ed1f  cmp     [rbp+90h+ReturnLength], 8
0x18003ed23  jnz     loc_18003EDC6
0x18003ed29  call    cs:__imp_GetCurrentThread
0x18003ed2f  mov     esi, 1
0x18003ed34  lea     r9, [rbp+90h+TokenHandle]; TokenHandle
0x18003ed38  mov     rcx, rax; ThreadHandle
0x18003ed3b  mov     r8d, esi; OpenAsSelf
0x18003ed3e  lea     edi, [rsi+0Bh]
0x18003ed41  mov     edx, edi; DesiredAccess
0x18003ed43  call    cs:__imp_OpenThreadToken
0x18003ed49  test    eax, eax
0x18003ed4b  jnz     short loc_18003ED5D
0x18003ed4d  call    cs:__imp_GetLastError
0x18003ed53  mov     esi, 0D99h
0x18003ed58  jmp     loc_18003ECBA
0x18003ed5d  mov     rcx, [rbp+90h+TokenHandle]; TokenHandle
0x18003ed61  lea     rax, [rbp+90h+ReturnLength]
0x18003ed65  mov     r9d, 38h ; '8'; TokenInformationLength
0x18003ed6b  mov     [rsp+0D0h+pdwType], rax; ReturnLength
0x18003ed70  lea     r8, [rbp+90h+TokenInformation]; TokenInformation
0x18003ed74  lea     edx, [r9-2Eh]; TokenInformationClass
0x18003ed78  call    cs:__imp_GetTokenInformation
0x18003ed7e  test    eax, eax
0x18003ed80  jnz     short loc_18003ED92
0x18003ed82  call    cs:__imp_GetLastError
0x18003ed88  mov     esi, 0DA2h
0x18003ed8d  jmp     loc_18003ECBA
0x18003ed92  lea     rdx, [rbp+90h+ppLogonSessionData]; ppLogonSessionData
0x18003ed96  lea     rcx, [rbp+90h+LogonId.HighPart]; LogonId
0x18003ed9a  call    cs:__imp_LsaGetLogonSessionData
0x18003eda0  test    eax, eax
0x18003eda2  jnz     short loc_18003EDBC
0x18003eda4  mov     rcx, [rbp+90h+ppLogonSessionData]
0x18003eda8  test    rcx, rcx
0x18003edab  jz      short loc_18003EDBC
0x18003edad  mov     rax, [rcx+50h]
0x18003edb1  cmp     qword ptr [rbp+90h+var_78], rax
0x18003edb5  jl      short loc_18003EDD3
0x18003edb7  mov     r15d, esi
0x18003edba  jmp     short loc_18003EDD3
0x18003edbc  mov     esi, 0DA9h
0x18003edc1  jmp     loc_18003ECBA
0x18003edc6  mov     esi, 0D8Dh
0x18003edcb  jmp     loc_18003ECB5
0x18003edd0  mov     rbx, r12
0x18003edd3  mov     rcx, [rbp+90h+ppLogonSessionData]; Buffer
0x18003edd7  test    rcx, rcx
0x18003edda  jz      short loc_18003EDE2
0x18003eddc  call    cs:__imp_LsaFreeReturnBuffer
0x18003ede2  mov     rcx, [rbp+90h+TokenHandle]; hObject
0x18003ede6  test    rcx, rcx
0x18003ede9  jz      short loc_18003EDF1
0x18003edeb  call    cs:__imp_CloseHandle
0x18003edf1  test    rbx, rbx
0x18003edf4  jz      short loc_18003EE0E
0x18003edf6  lea     rcx, [rbx-8]
0x18003edfa  cmp     dword ptr [rcx], 70616548h
0x18003ee00  jnz     short loc_18003EE0E
0x18003ee02  mov     rax, cs:g_pfnFree
0x18003ee09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ee0e  mov     eax, r15d
0x18003ee11  mov     rcx, [rbp+90h+var_30]
0x18003ee15  xor     rcx, rbp; StackCookie
0x18003ee18  call    __security_check_cookie
0x18003ee1d  mov     rbx, [rbp+90h+arg_8]
0x18003ee24  mov     rsi, [rbp+90h+arg_10]
0x18003ee2b  lea     rsp, [rbp+70h]
0x18003ee2f  pop     r15
0x18003ee31  pop     r14
0x18003ee33  pop     r12
0x18003ee35  pop     rdi
0x18003ee36  pop     rbp
0x18003ee37  retn
```
