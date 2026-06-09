# IsInFrameServerProcess

- ea: `0x18017c198`
- end: `0x18017c597`
- name: `IsInFrameServerProcess`
- size: `1023`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800cad7c`

## callees

- `0x180050d6c`
- `0x18009efc4`
- `0x180124598`
- `0x1801566ac`
- `0x18017c198`
- `0x18017c5a0`
- `0x180258390`
- `0x180258480`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017c2b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017c3ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017c463`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017c2b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017c3ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017c463`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18017c1fa`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18017c2a5`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18017c1fa`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18017c2a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017c2fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017c528`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017c2fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017c528`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18017c4de`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18017c4fe`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18017c4de`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18017c4fe`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18017c4a3`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18017c4bb`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18017c4a3`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18017c4bb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18017c33f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18017c3f5`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18017c54a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18017c55f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18017c33f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18017c3f5`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18017c54a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18017c55f`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18017c39d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18017c453`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18017c39d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18017c453`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18017c31e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18017c31e`

## pseudocode

```c
char __fastcall IsInFrameServerProcess(_BYTE *a1)
{
  char v2; // di
  WCHAR *v3; // rbx
  DWORD EnvironmentVariableW; // esi
  DWORD v5; // esi
  WCHAR **unique; // rax
  void *v7; // rcx
  signed int LastError; // eax
  bool v9; // sf
  __int64 v10; // rdx
  HLOCAL v11; // rsi
  PSID v12; // rsi
  bool v13; // sf
  PSID v14; // rsi
  bool v15; // sf
  void *Block; // [rsp+60h] [rbp+7h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp+Fh] BYREF
  PSID pSid1; // [rsp+70h] [rbp+17h] BYREF
  PSID pSid; // [rsp+78h] [rbp+1Fh] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+80h] [rbp+27h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  pSid = 0;
  pSid1 = 0;
  v2 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v3 = 0;
  hMem = 0;
  if ( a1 )
    *a1 = 0;
  EnvironmentVariableW = GetEnvironmentVariableW(L"_FSENVOPT", 0, 0);
  if ( EnvironmentVariableW )
  {
    if ( (unsigned __int8)byte_1803CECED >= 8u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 92, &WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids);
    v5 = EnvironmentVariableW + 1;
    unique = (WCHAR **)wil::make_unique_nothrow<unsigned short [0]>(&Block, v5);
    v3 = *unique;
    *unique = 0;
    v7 = Block;
    Block = 0;
    if ( v7 )
      operator delete(v7);
    if ( !v3 )
    {
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          93,
          &WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids,
          0,
          -2147024882);
      goto LABEL_48;
    }
    if ( !GetEnvironmentVariableW(L"_FSENVOPT", v3, v5) )
    {
      LastError = GetLastError();
      v9 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v9 = LastError < 0;
      }
      if ( v9 )
      {
        if ( !g_wppLevels )
          goto LABEL_48;
        v10 = 94;
        goto LABEL_18;
      }
    }
    v11 = hMem;
    if ( hMem )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&Block);
      LocalFree(v11);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&Block);
    }
    hMem = 0;
    ConvertStringSidToSidW(v3, &hMem);
  }
  v12 = pSid;
  if ( pSid )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&Block);
    FreeSid(v12);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&Block);
  }
  pSid = 0;
  if ( !AllocateAndInitializeSid(
          &pIdentifierAuthority,
          6u,
          0x50u,
          0xE967CCF4,
          0x7D6A138Du,
          0xB5A1A4F6,
          0x6BFBC5BAu,
          0x2E2D1C23u,
          0,
          0,
          &pSid) )
  {
    LastError = GetLastError();
    v13 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v13 = LastError < 0;
    }
    if ( v13 )
    {
      if ( !g_wppLevels )
        goto LABEL_48;
      v10 = 95;
      goto LABEL_18;
    }
  }
  v14 = pSid1;
  if ( pSid1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&Block);
    FreeSid(v14);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&Block);
  }
  pSid1 = 0;
  if ( !AllocateAndInitializeSid(
          &pIdentifierAuthority,
          6u,
          0x50u,
          0xA320C60B,
          0x8E5BF9Du,
          0xA3D9D00D,
          0xE67373FA,
          0xC7213178,
          0,
          0,
          &pSid1) )
  {
    LastError = GetLastError();
    v15 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v15 = LastError < 0;
    }
    if ( v15 )
    {
      if ( !g_wppLevels )
        goto LABEL_48;
      v10 = 96;
LABEL_18:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        &WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids,
        0,
        LastError);
      goto LABEL_48;
    }
  }
  if ( hMem )
  {
    if ( !EqualSid(pSid, hMem) && !EqualSid(pSid1, hMem) )
      goto LABEL_48;
LABEL_41:
    v2 = 1;
    goto LABEL_48;
  }
  LODWORD(Block) = 0;
  if ( CheckTokenMembership(0, pSid, (PBOOL)&Block) && (_DWORD)Block )
    goto LABEL_41;
  if ( CheckTokenMembership(0, pSid1, (PBOOL)&Block) )
  {
    if ( (_DWORD)Block )
    {
      v2 = 1;
      if ( a1 )
        *a1 = 1;
    }
  }
LABEL_48:
  if ( hMem )
    LocalFree(hMem);
  if ( v3 )
    operator delete(v3);
  if ( pSid1 )
    FreeSid(pSid1);
  if ( pSid )
    FreeSid(pSid);
  return v2;
}

```

## disassembly

```asm
0x18017c198  mov     [rsp-8+arg_8], rbx
0x18017c19d  mov     [rsp-8+arg_10], rsi
0x18017c1a2  push    rbp
0x18017c1a3  push    rdi
0x18017c1a4  push    r12
0x18017c1a6  push    r14
0x18017c1a8  push    r15
0x18017c1aa  lea     rbp, [rsp-37h]
0x18017c1af  sub     rsp, 90h
0x18017c1b6  mov     rax, cs:__security_cookie
0x18017c1bd  xor     rax, rsp
0x18017c1c0  mov     [rbp+57h+var_28], rax
0x18017c1c4  xor     r15d, r15d
0x18017c1c7  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18017c1cd  mov     [rbp+57h+pSid], r15
0x18017c1d1  mov     r14, rcx
0x18017c1d4  mov     [rbp+57h+pSid1], r15
0x18017c1d8  mov     dil, r15b
0x18017c1db  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r15d
0x18017c1df  mov     ebx, r15d
0x18017c1e2  mov     [rbp+57h+hMem], r15
0x18017c1e6  test    rcx, rcx
0x18017c1e9  jz      short loc_18017C1EE
0x18017c1eb  mov     [rcx], r15b
0x18017c1ee  xor     r8d, r8d; nSize
0x18017c1f1  lea     rcx, Name; "_FSENVOPT"
0x18017c1f8  xor     edx, edx; lpBuffer
0x18017c1fa  call    cs:__imp_GetEnvironmentVariableW
0x18017c201  nop     dword ptr [rax+rax+00h]
0x18017c206  lea     r12, WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids
0x18017c20d  mov     esi, eax
0x18017c20f  test    eax, eax
0x18017c211  jz      loc_18017C32A
0x18017c217  cmp     cs:byte_1803CECED, 8
0x18017c21e  jb      short loc_18017C23B
0x18017c220  mov     rcx, cs:WPP_GLOBAL_Control
0x18017c227  mov     edx, 5Ch ; '\'
0x18017c22c  mov     r8, r12
0x18017c22f  mov     rcx, [rcx+0D8h]
0x18017c236  call    WPP_SF_
0x18017c23b  inc     esi
0x18017c23d  lea     rcx, [rbp+57h+Block]
0x18017c241  mov     edx, esi
0x18017c243  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x18017c248  mov     rbx, [rax]
0x18017c24b  mov     [rax], r15
0x18017c24e  mov     rcx, [rbp+57h+Block]; Block
0x18017c252  mov     [rbp+57h+Block], r15
0x18017c256  test    rcx, rcx
0x18017c259  jz      short loc_18017C260
0x18017c25b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18017c260  test    rbx, rbx
0x18017c263  jnz     short loc_18017C298
0x18017c265  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18017c26c  jb      loc_18017C51F
0x18017c272  lea     edx, [rbx+5Dh]
0x18017c275  mov     [rsp+0B0h+nSubAuthority2], 8007000Eh
0x18017c27d  mov     rcx, cs:WPP_GLOBAL_Control
0x18017c284  xor     r9d, r9d
0x18017c287  mov     r8, r12
0x18017c28a  mov     rcx, [rcx+10h]
0x18017c28e  call    WPP_SF_qD
0x18017c293  jmp     loc_18017C51F
0x18017c298  mov     r8d, esi; nSize
0x18017c29b  lea     rcx, Name; "_FSENVOPT"
0x18017c2a2  mov     rdx, rbx; lpBuffer
0x18017c2a5  call    cs:__imp_GetEnvironmentVariableW
0x18017c2ac  nop     dword ptr [rax+rax+00h]
0x18017c2b1  test    eax, eax
0x18017c2b3  jnz     short loc_18017C2E9
0x18017c2b5  call    cs:__imp_GetLastError
0x18017c2bc  nop     dword ptr [rax+rax+00h]
0x18017c2c1  test    eax, eax
0x18017c2c3  jle     short loc_18017C2CF
0x18017c2c5  movzx   eax, ax
0x18017c2c8  or      eax, 80070000h
0x18017c2cd  test    eax, eax
0x18017c2cf  jns     short loc_18017C2E9
0x18017c2d1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18017c2d8  jb      loc_18017C51F
0x18017c2de  mov     edx, 5Eh ; '^'
0x18017c2e3  mov     [rsp+0B0h+nSubAuthority2], eax
0x18017c2e7  jmp     short loc_18017C27D
0x18017c2e9  mov     rsi, [rbp+57h+hMem]
0x18017c2ed  test    rsi, rsi
0x18017c2f0  jz      short loc_18017C313
0x18017c2f2  lea     rcx, [rbp+57h+Block]; this
0x18017c2f6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18017c2fb  mov     rcx, rsi; hMem
0x18017c2fe  call    cs:__imp_LocalFree
0x18017c305  nop     dword ptr [rax+rax+00h]
0x18017c30a  lea     rcx, [rbp+57h+Block]; this
0x18017c30e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18017c313  lea     rdx, [rbp+57h+hMem]; Sid
0x18017c317  mov     [rbp+57h+hMem], r15
0x18017c31b  mov     rcx, rbx; StringSid
0x18017c31e  call    cs:__imp_ConvertStringSidToSidW
0x18017c325  nop     dword ptr [rax+rax+00h]
0x18017c32a  mov     rsi, [rbp+57h+pSid]
0x18017c32e  test    rsi, rsi
0x18017c331  jz      short loc_18017C354
0x18017c333  lea     rcx, [rbp+57h+Block]; this
0x18017c337  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18017c33c  mov     rcx, rsi; pSid
0x18017c33f  call    cs:__imp_FreeSid
0x18017c346  nop     dword ptr [rax+rax+00h]
0x18017c34b  lea     rcx, [rbp+57h+Block]; this
0x18017c34f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18017c354  lea     rax, [rbp+57h+pSid]
0x18017c358  mov     [rbp+57h+pSid], r15
0x18017c35c  mov     [rsp+0B0h+var_60], rax; pSid
0x18017c361  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18017c365  mov     [rsp+0B0h+nSubAuthority7], r15d; nSubAuthority7
0x18017c36a  mov     r9d, 0E967CCF4h; nSubAuthority1
0x18017c370  mov     [rsp+0B0h+nSubAuthority6], r15d; nSubAuthority6
0x18017c375  mov     r8d, 50h ; 'P'; nSubAuthority0
0x18017c37b  mov     [rsp+0B0h+nSubAuthority5], 2E2D1C23h; nSubAuthority5
0x18017c383  mov     dl, 6; nSubAuthorityCount
0x18017c385  mov     [rsp+0B0h+nSubAuthority4], 6BFBC5BAh; nSubAuthority4
0x18017c38d  mov     [rsp+0B0h+nSubAuthority3], 0B5A1A4F6h; nSubAuthority3
0x18017c395  mov     [rsp+0B0h+nSubAuthority2], 7D6A138Dh; nSubAuthority2
0x18017c39d  call    cs:__imp_AllocateAndInitializeSid
0x18017c3a4  nop     dword ptr [rax+rax+00h]
0x18017c3a9  test    eax, eax
0x18017c3ab  jnz     short loc_18017C3E0
0x18017c3ad  call    cs:__imp_GetLastError
0x18017c3b4  nop     dword ptr [rax+rax+00h]
0x18017c3b9  test    eax, eax
0x18017c3bb  jle     short loc_18017C3C7
0x18017c3bd  movzx   eax, ax
0x18017c3c0  or      eax, 80070000h
0x18017c3c5  test    eax, eax
0x18017c3c7  jns     short loc_18017C3E0
0x18017c3c9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18017c3d0  jb      loc_18017C51F
0x18017c3d6  mov     edx, 5Fh ; '_'
0x18017c3db  jmp     loc_18017C2E3
0x18017c3e0  mov     rsi, [rbp+57h+pSid1]
0x18017c3e4  test    rsi, rsi
0x18017c3e7  jz      short loc_18017C40A
0x18017c3e9  lea     rcx, [rbp+57h+Block]; this
0x18017c3ed  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18017c3f2  mov     rcx, rsi; pSid
0x18017c3f5  call    cs:__imp_FreeSid
0x18017c3fc  nop     dword ptr [rax+rax+00h]
0x18017c401  lea     rcx, [rbp+57h+Block]; this
0x18017c405  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18017c40a  lea     rax, [rbp+57h+pSid1]
0x18017c40e  mov     [rbp+57h+pSid1], r15
0x18017c412  mov     [rsp+0B0h+var_60], rax; pSid
0x18017c417  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18017c41b  mov     [rsp+0B0h+nSubAuthority7], r15d; nSubAuthority7
0x18017c420  mov     r9d, 0A320C60Bh; nSubAuthority1
0x18017c426  mov     [rsp+0B0h+nSubAuthority6], r15d; nSubAuthority6
0x18017c42b  mov     r8d, 50h ; 'P'; nSubAuthority0
0x18017c431  mov     [rsp+0B0h+nSubAuthority5], 0C7213178h; nSubAuthority5
0x18017c439  mov     dl, 6; nSubAuthorityCount
0x18017c43b  mov     [rsp+0B0h+nSubAuthority4], 0E67373FAh; nSubAuthority4
0x18017c443  mov     [rsp+0B0h+nSubAuthority3], 0A3D9D00Dh; nSubAuthority3
0x18017c44b  mov     [rsp+0B0h+nSubAuthority2], 8E5BF9Dh; nSubAuthority2
0x18017c453  call    cs:__imp_AllocateAndInitializeSid
0x18017c45a  nop     dword ptr [rax+rax+00h]
0x18017c45f  test    eax, eax
0x18017c461  jnz     short loc_18017C496
0x18017c463  call    cs:__imp_GetLastError
0x18017c46a  nop     dword ptr [rax+rax+00h]
0x18017c46f  test    eax, eax
0x18017c471  jle     short loc_18017C47D
0x18017c473  movzx   eax, ax
0x18017c476  or      eax, 80070000h
0x18017c47b  test    eax, eax
0x18017c47d  jns     short loc_18017C496
0x18017c47f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18017c486  jb      loc_18017C51F
0x18017c48c  mov     edx, 60h ; '`'
0x18017c491  jmp     loc_18017C2E3
0x18017c496  mov     rdx, [rbp+57h+hMem]; pSid2
0x18017c49a  test    rdx, rdx
0x18017c49d  jz      short loc_18017C4D0
0x18017c49f  mov     rcx, [rbp+57h+pSid]; pSid1
0x18017c4a3  call    cs:__imp_EqualSid
0x18017c4aa  nop     dword ptr [rax+rax+00h]
0x18017c4af  test    eax, eax
0x18017c4b1  jnz     short loc_18017C4CB
0x18017c4b3  mov     rdx, [rbp+57h+hMem]; pSid2
0x18017c4b7  mov     rcx, [rbp+57h+pSid1]; pSid1
0x18017c4bb  call    cs:__imp_EqualSid
0x18017c4c2  nop     dword ptr [rax+rax+00h]
0x18017c4c7  test    eax, eax
0x18017c4c9  jz      short loc_18017C51F
0x18017c4cb  mov     dil, 1
0x18017c4ce  jmp     short loc_18017C51F
0x18017c4d0  mov     rdx, [rbp+57h+pSid]; SidToCheck
0x18017c4d4  lea     r8, [rbp+57h+Block]; IsMember
0x18017c4d8  xor     ecx, ecx; TokenHandle
0x18017c4da  mov     dword ptr [rbp+57h+Block], r15d
0x18017c4de  call    cs:__imp_CheckTokenMembership
0x18017c4e5  nop     dword ptr [rax+rax+00h]
0x18017c4ea  test    eax, eax
0x18017c4ec  jz      short loc_18017C4F4
0x18017c4ee  cmp     dword ptr [rbp+57h+Block], r15d
0x18017c4f2  jnz     short loc_18017C4CB
0x18017c4f4  mov     rdx, [rbp+57h+pSid1]; SidToCheck
0x18017c4f8  lea     r8, [rbp+57h+Block]; IsMember
0x18017c4fc  xor     ecx, ecx; TokenHandle
0x18017c4fe  call    cs:__imp_CheckTokenMembership
0x18017c505  nop     dword ptr [rax+rax+00h]
0x18017c50a  test    eax, eax
0x18017c50c  jz      short loc_18017C51F
0x18017c50e  cmp     dword ptr [rbp+57h+Block], r15d
0x18017c512  jz      short loc_18017C51F
0x18017c514  mov     dil, 1
0x18017c517  test    r14, r14
0x18017c51a  jz      short loc_18017C51F
0x18017c51c  mov     [r14], dil
0x18017c51f  mov     rcx, [rbp+57h+hMem]; hMem
0x18017c523  test    rcx, rcx
0x18017c526  jz      short loc_18017C534
0x18017c528  call    cs:__imp_LocalFree
0x18017c52f  nop     dword ptr [rax+rax+00h]
0x18017c534  test    rbx, rbx
0x18017c537  jz      short loc_18017C541
0x18017c539  mov     rcx, rbx; Block
0x18017c53c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18017c541  mov     rcx, [rbp+57h+pSid1]; pSid
0x18017c545  test    rcx, rcx
0x18017c548  jz      short loc_18017C556
0x18017c54a  call    cs:__imp_FreeSid
0x18017c551  nop     dword ptr [rax+rax+00h]
0x18017c556  mov     rcx, [rbp+57h+pSid]; pSid
0x18017c55a  test    rcx, rcx
0x18017c55d  jz      short loc_18017C56B
0x18017c55f  call    cs:__imp_FreeSid
0x18017c566  nop     dword ptr [rax+rax+00h]
0x18017c56b  mov     al, dil
0x18017c56e  mov     rcx, [rbp+57h+var_28]
0x18017c572  xor     rcx, rsp; StackCookie
0x18017c575  call    __security_check_cookie
0x18017c57a  lea     r11, [rsp+0B0h+var_20]
0x18017c582  mov     rbx, [r11+38h]
0x18017c586  mov     rsi, [r11+40h]
0x18017c58a  mov     rsp, r11
0x18017c58d  pop     r15
0x18017c58f  pop     r14
0x18017c591  pop     r12
0x18017c593  pop     rdi
0x18017c594  pop     rbp
0x18017c595  retn
```
